# StoppingTargets

This repo contains the following:

* constructStoppingTarget.cc
* a set of txt based geometry configurations for various target geometries
* an example geom_current to show how to put the code into practice
* this documentation

## constructStoppingTarget

This file should be placed in Mu2eG4/src . It contains code to build the stopping target geometry with a few optional geometry styles. The parameter "stoppingTarget.designName" decides which type of design. You have three options:

* foil - the nominal style, the user has control over the material, thickness, hole size, number of foils, radius etc.
* screen - the are two types of commercially available screen mesh the main difference is the string radii: 0.02665 mm or 0.1143 mm, the user has control of how many disks of these string mesh are present as well as the material, disk separation, presence and size of a hole, disk dimensions etc.
* cylinder - mesh based target. The geometric shape of the target is concentric cylinders.
* hexagon - mesh based target. The geometric shape of the target is a set of cylinders making a hexagonal cross-section

  
