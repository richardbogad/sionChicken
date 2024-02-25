# The sionChicken Project

## Description
Dive into the internals of the revolutionary world of the sionChicken Project, featuring the first-ever virtual breedable 3D lifeforms within SecondLife. \
Crafted by the visionary Richard Bogad during 2008-2009, this project has set a new standard in virtual ecosystems, \
achieving massive success and even earning a nomination for the prestigious Linden Prize in 2010. \
This repository contains the latest v12 version of the lifeforms.

General information about the project can be found [here](README.md).

Please NOTE: Additional tools like the 'transport box', 'proteggtor', 'healing kit', 'radi-O-static' or the growing 'sionCorn' plants are not yet available in this repository. \
Furthermore, status display objects for the chicken and eggs are also not yet added to this repository.
The LSL scripting language was very limited, therefore object oriented design and proper unit testing was not possible.

## Setup of Primitives

Use the 'Data To Object' script to setup the primitive object appearances.

The script can be found here:
https://wiki.secondlife.com/wiki/Object_to_Data_v1.4#Data_To_Object_.28Script.29

Follow the 'Data To Object' manual to create following objects:
* data-to-object/objdef-sionChicken.txt
* data-to-object/objdef-sionChicken egg.txt
* data-to-object/objdef-sionChicken food.txt

## Setup of Scripts & Objects

In the scripts, search for the avatar key '140c69e0-beca-4dfc-b705-56efadd3be21' and change this key to your personal avatar key. \
This is necessary, because initializing scripts by owners was not allowed to fight object cloning. 

Once the objects above have been created, place the following content into their main & sub-prims:

* Object Base-Prim name 'sionChicken':
    * Script: sionChicken.Animation
    * Script: sionChicken.Brain
    * Script: sionChicken.Movation
    * Script: sionLabs.Communication
    * Script: sionLabs.Slave

    * Linked Sub-Prim name 'kopf':
        * Script: sionLabs.Slave
        * Script: sionChicken.Name

    * Linked Sub-Prim name 'schnabel':
        * Script: sionLabs.Slave

    * Linked Sub-Prim name 'rumpf':
        * Script: sionLabs.Slave

    * Linked Sub-Prim name 'fluegelL':
        * Script: sionLabs.Slave
        * Script: sionChicken.AnimFluegelL

    * Linked Sub-Prim name 'fluegelR':
        * Script: sionLabs.Slave
        * Script: sionChicken.AnimFluegelR

    * Linked Sub-Prim name 'haxiL':
        * Script: sionLabs.Slave
        * Script: sionChicken.AnimHaxiL

    * Linked Sub-Prim name 'haxiR':
        * Script: sionLabs.Slave
        * Script: sionChicken.AnimHaxiR

    * Linked Sub-Prim name 'schwanz':
        * Script: sionLabs.Slave

* Object 'sionChicken egg':
    * Script: sionChicken.Egg
    * Script: sionLabs.Communication
    * Visual Object: 'breakpart one'
    * Visual Object: 'breakpart two'
    * Visual Object: 'broken egg'

* Object 'sionChicken food':
    * Script: sionChicken.Food
    * Script: sionLabs.Communication

## License

sionChicken © 2009 by Richard Bogad is licensed under CC BY-NC-SA 4.0.
To view a copy of this license, visit http://creativecommons.org/licenses/by-nc-sa/4.0/

[CC BY-NC-SA 4.0](license.txt)

## List of Link Message Types

The following list of link message types are used for internal events.

* num 0 link finder, response
* num 10 link finder, trigger
* num 11 position
* num 12 rotation
* num 13 scale
* num 14 color
* num 20 str integer = walk animation
* num 21 str integer = wing animation
* num 30 str <anim> = start animation
* num 31 str <anim> = stop animation
* num 32 str <factor> = grow with factor str
* num 33 str <vector> = lookat
* num 34 str num = gender
* num 35 str <vector> = transmits colors, genetics
* num 40 = blood particle
* num 41 = fur particle
* num 42 = no particle
* num 50 = ???
* num 69 key <id> str <speed> = walk (intelligently) to passiv-key id, with <speed>
* num 70 key <id> str <speed> = walk (intelligently) to key id, with <speed>
* num 71 key <id> str <speed> = walk (intelligently) to key id, with <speed>
* num 72 random
* num 73 = don't walk around
* num 74 = save homepos|parcelowner|group
* num 80 = reset
* num 93 death by object
* num 94 avatar coll
* num 95 target reached
* num 110 string <vector> = egg color
* num 112 trigger name display
* num 113 set name
* num 120 bar for status display
