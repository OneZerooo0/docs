# Common Mistakes

This page is meant to be a list of common pitfalls for you to avoid and learn from. 

### Building the ship's front not facing north
this one happens because people assume the ship's front is asigned by the ship's console, this isn't true however, it is the grid's north that should be the ship's front, as otherwise you'd have to rotate the ship console, which in turn rotates the camera view and the controls, you don't want to redo the whole ship after you make it.

### Using the rotation field for different decal orientations
the reason why different orientations are defined rather than expecting you to use the rotation field, is because of 2 reasons:
- it's way faster than typing in 0 90 180 manually every time
- the decals are made to align only using the different decals, and they don't align with manual rotations

### Not testing the ship before PR
running a couple test flights helps illuminate MANY mistakes you've missed. you're never trully done unless you do a run of the main task your ship was designed for.

### Not using ctrl+f to find and replace all the old shuttle's name
when you're copying over the shipyard entry yml folder in Monolith\Resources\Prototypes\_Mono\Shipyard be sure to use ctrl+f to find all the mentions of the old shuttle and replace them, a lot of people miss at least one mention and end up with problems while testing their shuttle

### Not linking the air alarms to firelocks/vents/scrubbers
air alarms don't magically know what the air in the room they're in is like, they check the devices they're linked to, and close the firelocks when a warning thresholds hit

### Running in Debug Mode
running in debug mode is only really intended for debuging entities and other objects that you work on outside the game this is mostly because Debug mode ensures that whenever any error shows up; no matter how small, it will end up crashing the entire server, and mapping tools sometimes give out error messages which might lead to a crash.

### Using the shipyard consoles ship price
the PROPER way to see a ship's value is using the appraisegrid command on a newly bought ship, because the shipyard console only shows a percentage of the true shuttle's value while appraisegrid shows the true value as is.

### Using appraisegrid on an uninitialized grid
this results in a far lower value as after initializing a lot of value is added from the machines/lockers/fills/etc

### Deleting your admin ghost
did you know you can delete yourself? upon doing so you'll become a regular ghost, and as mentioned above only admin ghosts get simulated in uninitialized maps, that means you need to readmin ghost yourself

thankfully this is easy, all you need to do is teleport to an object within an initialized map using the "objects" tab in the admin menu, and then readmin ghost yourself using the admin menu again. you can now safely go back to the map you were building on using the tp command listed above

### Not using signal switches instead of signal buttons
the regular button only has one port, which activates on a press, meaning it can only send one type of signal, this can be remedied by toggle ports in the things you're linking it with but some machines like conveyors don't have such a port......

that's where signal switches come in. they have 3 ports.
- on:     sends a signal when it's turned on
- off:    sends a signal when it's turned off 
- Status: sends a signal when it switches modes
the use of signal switches can be seen within the dragoon and the surveyor, they're used for conveyors in those.

### Not using all 3 pipe layers
if you use the entity spawner menu to select pipes you'll notice you can place them in all 3 layers as opposed to the pipes givven by mappingclientsidesetup, be sure to use all 3 pipe layers as otherwise the piping will be messy, keep in mind you're allowed to screwdriver vents and scrubers to lead directly into these different layer pipes

### Picking up and droping items to reposition them
this isn't ideal, as it saves the info about the deleted entities, so delete the entity then place another down to reposition

### Using the (ghost only warp point) instead of Warp point
the warp point (ship) automatically includes the ship info, while ghost only warp point doesn't.
