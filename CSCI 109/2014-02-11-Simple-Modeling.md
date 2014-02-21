---
layout: notes
title: Simple Modeling
date: 2014-02-13
category: csci

---
# Simple Modeling

* Install Emacs
* Install Python
* Always add copyright

<br>


    # Cole Townsend © 2014
    # {{Name of the work}}
    
    from ambrosia import *
    camera.shoot(scene)
    
    # Add {{Simple model name here}}
    scene.add(cone, dkGrayPlastic)
    
    # Scale in x,y,z directions
    scale.cone(.5,1,.5)
    
    # Take a screen of the image
    camera.shoot(scene)
    
    # 1. Create a group for Snowman    
    # 2. Make some spheres of something white
    # 3. Move it 50 units in -y direction
    # 4. Add it to the scene
    
    snowman = Group()
    # make head variable
    head = add(sphere,whitePlaster,translate(0,50,0)*scale(.5))
    	head.add(cone,yellowPlaster,scale(.5,1,.5),translate(0,50,0)*xRot(90)*translate(0,25,-25))
    head.translate(0,50,0)
    head.add
    
    snowman.add(sphere,whitePlaster,translate(0,-50,0))
    snowman.add(sphere,whiteplaster,translate(0,-50,0)*scale(.75)*translate(0,50,0)
    snowman.add(head)
    # Honey, I shrunk the kids. — Rick Morannis
    scene.add(snowman,scale(golden))
    camera.shoot()
    
    
## Ideas
* Create array of colors, loop through object style
	* colored pencils
	* colored paper
	
## Questions
* Can we set a local origin (origin for a group)
* Make all objects within group move from local origin?
	* Instead of moving from origin, can I move an object relative to another? Would that be useful

    
    
