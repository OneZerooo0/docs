# Common Questions

This page is meant to be a list of common questions you might have, they range from ones you might have right away, to ones you'll only ponder on after getting more familiar with mapping so it's always worth a cursory look. 

### What map is CC in?
it's in map 1 alongside all the other stations.

### How does the grid/map system work?
when you save a shuttle, you save it as a grid, when you use the shipyard console to purchase the ship, it turns the ship from a grid, to a map.

what that means is that if you're working on map 100, and saved the ship, you can just go to map 101 and loadgrid the saved ship, the ship isn't tied to a specific map.

ship files are stored as .yml files, so when you want to save your ship using the savegrid command, be sure to append .yml to the end of the ship's name when saving.

### How to find your grid's ID and save the grid
- Open the debug overlay with F3.
- Make sure your aghost is over the grid
- Under _Attached NetEntity_, look at _Grid NEntId_
- Put that ID in the `savegrid` command as shown.
- DO NOT USE THE MOUSE POS DATA.

### Where are the ship files stored?
the ones you save yourself are stored at <code>Monolith\bin\Content.Server\data</code>
while the ones already within the game are in <code>Monolith\Resources\Maps\_Mono\Shuttles</code>

### How to add more than one Object on a wall/tile?
- Place the Object down
- Right click and select View Variables
- Go to the Server Components Tab
- Search for TransformCompoent and click on it
- Look for _localPosition (NOT LocalPosition), the first value is the x coordinate, and the second is the y value
- change it in .25 increments.

this can be done for all entities. seen usually in buttons/lockers

### Is there an easier way to add more than one Object on a wall/tile?
Yes. using the placement mode of the entity spawner in the bottom right you can find placement modes used by other machines, try to experiment to see what each one does and where they can be used
