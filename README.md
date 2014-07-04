ilastik-build-Linux
===================

Use buildem to compile ilastik and all its dependencies on Linux. 

As a prerequisite, the following command must be executed to install the packages needed for compilation on a Debian system like Ubuntu:
```
sudo apt-get install build-essential g++ gcc git cmake cmake-curses-gui gfortran libxext-dev libfontconfig1-dev chrpath libxt-dev libgl1-mesa-dev libxfixes-dev libxrender-dev libxcursor-dev libxrandr-dev libxinerama-dev
```


Usage:

```
> mkdir <ilastik_build_dir>
> cd <ilastik_build_dir>
> git clone https://github.com/martinsch/ilastik-build-Linux.git
> mkdir build
> cd build
> cmake ../ilastik-build-Linux -DBUILDEM_DIR=<ilastik_build_dir> -DCPLEX_ROOT_DIR=<cplex_dir>
> make help      # (Optional: View the list of targets)
> make           # or 'make -j8' for parallel builds
> make package   # to create a 'ilastik-Linux.tar.gz' binary installer
```

Note: Parallel builds (using -j8) can sometimes cause certain sub-projects (e.g. pyqt) to fail to build.  If you experience any build failures, try a non-parallel build.
The <cplex_dir> must point to the directory in which the directory with cplex libraries is located, e.g. $HOME/local
