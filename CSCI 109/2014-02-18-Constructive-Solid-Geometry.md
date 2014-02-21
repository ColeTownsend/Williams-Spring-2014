---
layout: notes
title: Constructive Solid Geometry
date:  2014-02-18
category: csci
note-of-the-day: Finding Nemo celebrates how Pixar figured out how to work with water.
---

# Constructive Solid Geometry

### Code for the Day

#### Basic Terminal Commands
```python

# open current directory
open  . 
# open snowman
open snowman.png

```

#### Creating A Scene
```python
# Enter the scene
scene = Group()
# Enter light bulb, stage center
scene.add(cube, whitePlaster)
scene.add(bulb, translate(0, 200, 0))
camera.subject(scene)
camera.shoot()

```

#### New Scene with a Bulb and Offset Camera
```python
from ambrosia import *

# Enter the scene
scene = Group()
scene.add(bulb, translate(0, 200, 0))

scene.add(cube, whitePlaster)
camera.subject(scene)
camera.pos(translate(0,75,0))
camera.shoot()

```

#### goStones.py
```python
from ambrosia import *

# Enter the scene
scene = Group()
scene.add(bulb, translate(0, 200, 0))

# Make that Go Stone
goStone = Intersection()
goStone.add(sphere, translate(0,-30,0))
goStone.add(sphere, translate(0,30,0))
goStone.add(cylinder, scale(.75, 1, .75))

scene.add(goStone, whitePlaster)

# Create a Tool
tool = Difference()
tool.add(cylinder, xRot(-90)) # positive matter
# make the antimatter smaller
tool.add(cylinder, xRot(-90)*scale( 0.25, 0.25, 1, 0.1)*translate(40,0,0)*zRot(-45)) # antimatter

sandstone = Material()
sandstone.type('plaster')
sandstone.color( (.95, .85, .75) )

trim = Difference()
trim.add( cube, sandstone) # positive material
# carve out tool shape and sides
trim.add( tool, scale(1, 1, 1.1) translate(-50, 50, 0) ) # antimatter
trim.add( cube, scale(1,1.1,1.1)*translate(60, 0, 0)) # antimatter
trim.add( cube, scale(1.1,1,1.1)*translate(0, -60, 0)) # antimatter

# Shoot It
camera.subject(scene)
camera.pos(translate(0,75,0))
camera.shoot()

```


# To Do // Questions to Ask

* Automated task?
    * Build on save of python script
    * run file-name-here.python after save
    * Options
        * install rakefile in CS109
        * install foreman
* Making a hexagon?
    * is there a hexagon shape/prism?
    * I don't particularly want to create a hexagon by trimming a cylinder
    * 
