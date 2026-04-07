# List of Mapping Commands

This page is meant to be a list of all the Mapping Commands you'll need to know, and would like to know.

### mapping (mapid) [/path/to/shuttle]
creates a blank uninitialized map, makes you an admin ghost, then teleports you to it.
you can put in the path to shuttle if you want or not, if it's blank then the map will be empty and you can just use the loadgrid command to load a ship in

Examples:
- mapping 100 : it first makes you an admin ghost if you aren't already, then it (sometimes it's rather glitchy and doesn't) runs the mappingclientsidesetup command, then teleports you to map 100
- mapping 100 /Maps/_Mono/Shuttles/archer.yml : it first makes you an admin ghost if you aren't already, then it (sometimes it's rather glitchy and doesn't) runs the mappingclientsidesetup command, then teleports you to map 100 then it loads the archer shuttle into the map
- mapping 100 /test.yml : it first makes you an admin ghost if you aren't already, then it (sometimes it's rather glitchy and doesn't) runs the mappingclientsidesetup command, then teleports you to map 100 then loads the ship using the file test.yml from Monolith/bin/Content.Server/data into the map

### loadgrid (mapid) /path/to/shuttle x-position y-position
allows you to load a grid onto any map, including uninitialized maps, but without going through the shipyard console system it'll end up without the drive/cruise/park settings shuttles have.

/Maps/_Mono/Shuttles/ for ships already added to Monolith, and for ships you're saving they're in Monolith/bin/Content.Server/data

Examples:
- loadgrid 100 /Maps/_Mono/Shuttles/archer.yml : loads the surveyor shuttle into the map 100, if the map doesn't exist it does nothing
- loadgrid 100 /test.yml : loads the ship using the file test.yml from Monolith/bin/Content.Server/data into the map 100, if the map doesn't exist it does nothing

### startround
this makes the game load in ASAP, bypassing the 3 minute wait time.

### mappingclientsidesetup
this command adds a bunch of tiles/items to your actions bar, the main thing you'll use it for is deleting entities

### aghost
this command turns you into an admin ghost without having to go through the admin menu

### physics com
it shows the ships Centre Of Mass (com) as a large orange ball, if you see more than one then that means your Grid has split, due to how buggy mapping tools are just ctrl clicking out plating has a high chance of making some tiles that aren't connected to the main grid, please be sure to keep it on whenever you're modifying the ship's structure even a little bit

### tp x y (mapid)
this command allows you to teleport into any x and y coordinate into any map, say you've teleported back to FO's mapid which is always 1 to buy a ship to look at as reference, to teleport back to your grid you just add it's mapid rather than FO's 

### colornetwork (networkid) Pipe (#hexcode)
this command colors a pipe network, it needs to be Pipe with a capital P at the begining otherwise it won't work 
to find the network id, you just right click a pipe, the number you see is the network id.

it's included with other pins in the mapping general discord channel but the main colors are:  
- #990000 for scrubber networks 
- #0055cc for air distribution pipes 
- #9955cc for auxilery gas networks

### variantize (gridid)
this command adds the different variaties of tiles and adds garbage to the ship when it spawns, all ships are required to run this command before adding to the game

### fixgridatmos (gridid)
this command fixes/adds air to the tiles of the ship , run it when you're finishing up a build and everytime you edit the ship's walls/shape

### savegrid (gridid) /(shipname).yml
this one saves the ship grid into the Monolith\bin\Content.Server\data path as a file, you'll need to appemd .yml to the end of the ship's name to save as a yml file

### appraisegrid (gridid)
this one allows you to know how much is worth, you should only run it on a initialized grid.

### gridtc (gridid)
this one counts all the tiles in the grid, is used for ship size classificiation.

### mapinit (mapid)
initializes the map whose id you used, do NOT use it before you save your ship, but it'd allow you to test the ship in an empty map.

# Setting up a Ship's ID
Before you can get the ship into the shipyard console, you'll need to add a ship specific ID to refer to the ship within the files, you'll need to use these 2 following commands
### vv (gridid)
this allows you to edit the components of the ship's grid, the only thing you need to do is go to the server components tab, press "Add Component" then search for BecomesStation, once you do that, write out the next command to EDIT the ship's name.
### vvwrite /entity/(gridid)/BecomesStation/Id "(shipname)"
this allows you to change the grid's ID properly, all you need to do is replace the gridid with the ship's, and the shipname with the ship's name that will be used as it's ID

this name will only show up when you manually spawn the ship in, as the shipyard adds the name itself, so it's only a QOL addition to make autocompleting commands pick it up as something other than "grid"

# How to add a shuttle to the shipyard console
if you want the bare minimum set up, then all you need to do is add the shuttle's .yml file in Monolith\Resources\Maps\_Mono\Shuttles -or inside a folder within this file for expedition/staff shuttles-

and add a file in Monolith\Resources\Prototypes\_Mono\Shipyard, you can open one for a shuttle of a similar archetype and use it as a template, while having the guidebookPage: Null, this will make it purchusable without a guidebook entry.

keep in mind, you need to have the class and engine match the ingame ones to the letter, otherwise the ship won't show up at all

if you want to add a guidebook entry, then follow along another ship's PR and see the changed files
