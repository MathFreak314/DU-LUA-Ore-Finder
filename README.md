# DU-LUA-Ore-Finder
This is a LUA script that creates a HUD on your character which allows you to triangulate ore locations while mining

It works by creating a series of buttons along the top of your screen.  Each of which indicates a measurement from your scanning device.
These measurements coincide with the horizontal lines on your scanner.  When you have a reading that is on one of those lines you
then use alt+1 or alt+2 to move the highlighted measurment left/right (it wraps around) and once your measurement is highlighted
you use alt+3 to lock it in.

Once you have locked in 3 or more measurements it prints out a pos:: marker in the LUA chat that you can right click to set as a marker.
This is it's current best guess at where the ore is.  You keep feeding it measurements until it gets you close enough for the directional
scanner.

The search algorithm is 2-fold.
First, it creates a bounding box using your location and measurements to define a limit to where the ore can be.  It then does a quick search
within that region for the spot that best matches your measurements.  That is the point it directs you to next.  It allows for a 10% margin of error
in your measurements.  It will also give an error message letting you know if it is no longer able to define a search region, at which point you start over
and feed it different measurements in an attempt to get a vaild result.

Finally, once you have found the ore, you can use alt+9 to reset the search so you can start finding a new ore.

# Installation

1) open the code and copy it to your clipboard
2) in game, right click on the programming board, go to advanced and then "paste LUA config from clipboard"
3) this should load the code into the programming board, you know it was done correctly if circles appear at the top of your screen when activated
4) Information is given through the LUA chat, this can be accessed by hitting ENTER and selecting the LUA tab in the chat window
5) there are instructions included when you first start the program
