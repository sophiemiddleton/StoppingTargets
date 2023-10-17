# StoppingTargets

This repo contains the following:

* constructStoppingTarget.cc and .hh c++ files which utilize G4 to build the chosen geometry;
* a set of .txt based geometry configurations for various target geometries;
* examples of stopping targets made of Ti, V and Li instead of Al;
* an example geom_current to show how to put the code into practice;
* globalConstants file - this is where material information is stored such as relative decay fraction and density;
* An example CeEndpoint and DIO for Vanadium plus tabulated values ;
* this documentation.

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

Mu2e/Offline requires geometries to be defined in .txt config files. These list the relevant parameters for that specific geometry. The geom_common_current.txt usually contains the parameters actually imported into the simulation. There are a number of included .txt files. At the time of this study, the current stopping target geometry was taken from geom_common_hayman_v2.txt.

If you look in the file you will see how to add the target of choice based on including the relevant text files.

## The chosen target .txt

I have added several chosen geometry .txt files. These should be fairly self-explanatory.

## Changing Stopping Target Material

The parameter physicsParams.chosenStoppingTargetMaterial dictates the stopping target material. I have included an example of how to construct a V amd Ti target.

The globalConstats.txt should be placed in Mu2eG4/test and contain parameters relevant to the stopping target materials. If you want to add something not listed here, you will need to look up these quantities and add them to this file.

## Running a simulation

If you are not changing the stopping target material you are good to run using the standard production workflow.

If you have changed the material you will need to do the following look at the CeEndpointV.fcl and DIOTailV.fcl examples. To run the latter move the supplied table to the ConditionsService/data directory.
