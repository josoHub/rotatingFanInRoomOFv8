# rotatingFanInRoomOFv8
rotatingFanInRoom files adjusted to work in OpenFoam v8

This is not my project and i'm very begginer on openfoam, i just have modified some files from this tutorial https://www.youtube.com/watch?v=qtN256WJ-5I ; https://develop.openfoam.com/Development/openfoam/tree/develop/tutorials/incompressible/pimpleFoam/RAS/rotatingFanInRoom , to work with openFoam v8. Working with "openfoam-org 8.20201114-1" installed on archlinux, from https://aur.archlinux.org/packages/openfoam-org/. To undersetand how to use the files please read the wiki tutorial in the description of the above video, and read the important section below.

-----------------------------------------------------------------------
!IMPORTANT! :
-----------------------------------------------------------------------

  1 - The command surfaceFeatureExtract in openfoam v8 is changed to surfaceFeatures


  2 - If you have troubles with the mpi command used in the tutorial, run : 
  mpirun --use-hwthread-cpus -np 4 pimpleFoam -parallel > log.pimpleFoam &
  
  
  Explanation https://stackoverflow.com/questions/48835603/unable-to-use-all-cores-with-mpirun
  
  
  3 - when mpirun ends, to gather all information run: reconstructPar.
  Now run paraview correctly (see tutorial) And its done.

-------------------------------------------------------------------------------------


files changed:


  /constant/dynamicMeshDict - line 20
  
 	
  /system/decomposeParDict - lines 30-34. source https://cfd.direct/openfoam/user-guide/v8-running-applications-parallel/#dx12-86091
  
  
  /system/surfaceFeatureExtract renamed to /system/surfaceFeatures and added surfaces dictionaries to the file.

