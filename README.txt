README.txt

NOTE: This is unfinished code with incomplete documentation.  Use at your own risk. 


McMaze - proof-of-concept for perl-based maze/dungeon generator utilizing
         schematic building blocks.  This requires codewarrior0's pymclevel
         to build maze/dungeon in Minecraft map.
------------------------------------------------------------------------------

usage: ../mcmaze [-[no]flag-option | -string-option="string" | -numeric-option=number ]...

  options:

     flag options:

      diagout		write out maze diagnostics file
      rawout		write out maze raw file
      txtout		write out ascii and ansi maze files
      roomedgebuffer	require border between room and outer maze edge
      adjacentrooms	allow rooms to be adjacent to other rooms
      invertlevels	invert up/down indicators on ascii maze output
      updowndirs	allow up/down ladders in maze
      verticaldoors	allow vertical exit directions from rooms
      mazeloops		selectively create long maze loops by removing walls
      mazexoloops	selectively create maze loops by adding crossovers
      dungeonmode	limit vertical level access to one entrance per level
      startinroom	move maze starting position to room 1
      bmxswap		invert room bitmap on X axis
      bmyswap		invert room bitmap on Y axis
      bmzswap		invert room bitmap on Z axis
      bmhrotate		rotate room bitmap horizontally (1=90,2=180,3=270 degree)
      crossovers	allow hallways crossing paths over other hallways
      passthrus		allow hallways crossing through rooms
      dynstairs		allow dynamic stairs to be used in hallways
      allowfeffects	allow floor effects in hallways and rooms
      allowceffects	allow ceiling effects in hallways and rooms
      showfceffect	show floor/ceiling effects on ascii/ansi map output
      pittraps		allow pit trap generation
      showtraps		show traps on ascii/ansi map output
      deadendrmdoors	remove dead-end doors with path
      room2roompriority	prioritize room-to-room paths over room-to-hall paths
      denseroompacking	attempt to densely pack rooms on maze
      choosecorner	choose nearest corner for dense room packing movement
      debug		specify one or more times for increased verbose output

     string options:

      prefix="name"
			override default "maze" file prefix for output files
      bitmaproom="X,Y,Z,bitmap[,room-class]"
			add bitmap room at specified coordinates
      placeroom="X,Y,Z,XS,YS,ZS,room-class"
			add room of specified class and size at coordinates
      placelevel="Y,room-class"
			add a level-size room with specified class on level 'Y'
      levelclass="Y,level-class"
			adjust the level class of level 'Y'
      noroomblock="X,Y,Z,XS,YS,ZS"
			prevent random rooms from being built in specified area
      mc_schemroot="path"
			set the path to the schematic sets

     integer numeric options:

      seed		specify a random seed
      xmazesize		size of maze array X dimension
      ymazesize		size of maze array Y dimension
      zmazesize		size of maze array Z dimension
      xmaxroom		default maximum size of room, X dimension
      ymaxroom		default maximum size of room, Y dimension
      zmaxroom		default maximum size of room, Z dimension
      xminroom		default minimum size of room, X dimension
      yminroom		default minimum size of room, Y dimension
      zminroom		default minimum size of room, Z dimension
      numrooms		maximum number of rooms
      roomplacetrys	number of attempts to place random room
      minmazeloop	minimum size to consider for creating a maze loop
      deadendrmlength	length of path to remove from each dead-end
      roomtemplate	build a room template file of the room number specified
      labyrinth		set level as a labyrinth and all upper levels as tower

     floating numeric options:

      startfceffect	percentage odds of starting floor/ceiling effects
      trapodds		percentage odds of adding a non-pit trap
      pittrapodds	percentage odds of adding a pit trap
      deeppittrapodds	percentage odds of adding a deep pit trap

      see variable section in ../mcmaze for more detailed information

  examples: ../mcmaze -ymazesize=10 -dungeonmode -prefix="10leveldungeon"
	    ../mcmaze -ymazesize=1 -nocrossovers -numrooms=0 -prefix="simple2Dmaze"
	    ../mcmaze -bitmaproom="6,1,6,Arena"

