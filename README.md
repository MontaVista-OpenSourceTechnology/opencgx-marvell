# Release repository for marvell-octeontx

Montavista Software, LLC. release of marvell-octeontx. 

How to use:
==========

```
git clone -b kirkstone --recursive https://github.com/MontaVista-OpenSourceTechnology/opencgx-marvell
cd opencgx-marvell
source setup.sh
```

By default, the script will create a project called project, you may change this
by adding the directory name you would like to use on the source line:

```
source setup.sh <my directory>
```

After running the top level setup.sh, you are ready to build. When starting
another session, you can source the setup.sh script in the project directory
to get started. This script will automatically source the environment for
the build tools stored under buildtools, and sources the 
poky/oe-init-build-env script.

From that point, the project should work like any other yocto based build system. So
a command like the following will build images that you can run via qemu or on a real target.

```
cd project
or
cd <my directory>
source setup.sh
bitbake core-image-minimal
runqemu marvell-octeontx nographic slirp
```

For additional information see the yocto documentaion: https://www.yoctoproject.org/docs/

directory layout:
================
```
opencgx-marvell-octeontx/
       project - bitbake project for the marvell-octeontx project build
       buildtools - build tools to provide minimal build requirement for poky builds
       layers - layers for building marvell-octeontx project
       setup.sh - project setup script  
```

The default MACHINE is marvell-octeontx, however x86-atom-64 and x86-generic are also available. 
