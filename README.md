# StoppingTargets

This repo contains the following:

* constructStoppingTarget.cc and .hh
* a set of txt based geometry configurations for various target geometries
* an example of a stopping target made of Ti instead of Al
* an example geom_current to show how to put the code into practice
* globalConstants file - this is where material information is stored
* An example CeEndpoint from Titanium
* this documentation

## constructStoppingTarget

There are two files that should be placed in Mu2eG4:

* constructStoppingTarget.cc
* constructStoppingTarget.hh

To use the code copy these to Mu2eG4. The first should go in src and the latter in inc.

The .cc file contains code to build the stopping target geometry in Geant4, within the Mu2e Offline environment, it was last tested in 2021. The source code offers a few optional geometry styles. The parameter "stoppingTarget.designName" decides which type of design. You have three options:

* foil - the nominal style, the user has control over the material, thickness, hole size, number of foils, radius etc.
* screen - the are two types of commercially available screen mesh the main difference is the string radii: 0.02665 mm or 0.1143 mm, the user has control of how many disks of these string mesh are present as well as the material, disk separation, presence and size of a hole, disk dimensions etc.
* cylinder - mesh based target. The geometric shape of the target is concentric cylinders.
* hexagon - mesh based target. The geometric shape of the target is a set of cylinders making a hexagonal cross-section

## The geom common current

Mu2e/Offline requires geometries to be defined in .txt config files. These list the relevant parameters for that specific geometry. The geom_common_current.txt usually contains the parameters actually imported into the simulation. There's a number of included .txt files. At the time of this study, the current stopping target geometry was taken from geom_common_hayman_v2.txt.

If you look in the file you will see how to add the target of choice based on including the relevant text files.

## The chosen target .txt

I have added several chosen geometry .txt files. These should be fairly self-explanatory.

## Changing Stopping Target Material

The parameter physicsParams.chosenStoppingTargetMaterial dictates the stopping target material. I have included an example of how to construct a Ti target.

The globalConstats.txt should be placed in Mu2eG4/test and contains parameters relevant to the stopping target materials. If you want to add something not listed here, you will need to look up these quantities and add them to this file.

## Running a simualtion

If you are not changing the stopping target material you are good to run using the standard production workflow.

If you have changed the material you will need to do the following:

* Look at the CeEndpointTi.fcl example
