
------
2018-01-16 
 - Visual Studio 2017 in win10 fail to build this project again....
 - This update focus to remind me of how to use PMVS/CMVS's rebuild executable program.
 - With the help of VisualSFM, we could get a dense ply. But there is no `.patch` or `.pset` file in `models` folder.

####Use the following command.

> .\pmvs2.exe F:\shouji_test\dense.nvm.cmvs\00\ option-0000 PATCH PSET

![](.\output_image.PNG)

In `pmvs2.cc`, we find
```cpp
         << "[Optional export] PATCH PSET" << endl
         << " i.e export patch and pset: prefix option_file PATCH PSET"
         << " i.e export patch only: prefix option_file PATCH" <<endl;
```

--------------------------------

This is a modified version of CMVS/PMVS.

Main modification:
 - cross platform compilation Linux, Windows => CMake build system generator.
 - added bug fix from Nghia Ho.
 - make PLY, PSET, PATCH export faster and optional.
 - Replaced GSL simplex/lmfit with nlopt optimizer
 - Replaced image loading routines with CImg. Now PPMs are supported properly, with optional support for PNG and TIFF
 - Replaced BLAS/LAPACK with Eigen
 - Updated internal jpeg library and miniBoost
 - CMake-system now supports system boost, jpeg and other libraries if available. 
 - Replaced pthread with tinycthread to get rid of pthread.dll on Windows

Authors : 
[Original code author]  Yasutaka Furukawa http://www.cs.washington.edu/homes/furukawa/

[Initial Cmake multiplatform port ]	Pierre moulon pmoulon[AT]gmail.com

--------------------
- Web ressources : - 
--------------------
[CMVS/PMVS] http://http://grail.cs.washington.edu/software/cmvs/
[CMake version] http://opensourcephotogrammetry.blogspot.com/ https://github.com/pmoulon/CMVS-PMVS

