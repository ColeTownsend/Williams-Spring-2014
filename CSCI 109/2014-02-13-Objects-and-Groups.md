---
layout: notes
title: Objects and Groups
date: 2014-02-13
category: csci
note-of-the-day: camelCase all yo shit.
---

# Objects and Groups

```python
# © 2014 Cole Townsendæ
# {{Name of the work}}

from ambrosia import *

# set nose size
noseSize=1
# Add an orange material aka color((1,.5,0))
orangePlaster= Material()
orangePlaster.type('plaster').color(orange)

# create head group, add a sphere to it and scale
head=Group()
head.add(sphere,whitePlaster)
# add a nose, move it 50 unites up, scale it, and scale it down to 50 units
head.add(cone,orangePlaster,translate(0,50,0)*scale(0.24,1,0.24)*scale(noseSize)*xRot(-90)*translate(0,0,-45))
head.translate(0,50,0)
head.scale(0.5)

# Create a snowman group for the body add two body spheres as well as the head
snowman = Group()
snowman.add(sphere,whitePlaster,translate(0,50,0))
snowman.add(sphere,whitePlaster,translate(0,50,0)*scale(.75)*translate(0,100,0))
snowman.add(head,whitePlaster,translate(0,175,0))
# add a second head, move it up an additional 50
# only cone is purple because head is part of a group
snowman.add(head,purplePlaster,translate(0,225,0)*yRot(180))

# Add snowman to the scene, rotate it. Shoot it.
scene.add(snowman,scale(golden)*yRot(-90))
camera.shoot()
```

## Notes
* Camelcase
    * camelCase everything
* Colors
    * `yellow = (1,1,0)`
    * `orange = (1,0.5,0)`
    * `red = (1,0,0)`
* Materials
    * when assigned early, these become static
    * when not assigned, we can change them


## Question of the Day
What is the `.bash profile` setting for Duane? 

    

