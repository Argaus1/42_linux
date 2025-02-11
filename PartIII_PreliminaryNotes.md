# Cross Toolchain Preliminary Notes

Stages of this part:
- building a cross compiler and associated libraries (ch5)
- use it to built utilities isolated from host system (ch6)
- enter chroot env, construct remaining tools for final system (ch7)

## Toolchain Technical Notes

Ch5 and 6 : produce a temporary area containing a set of tools isolated from the host system. Then, we will use the CHROOT command :
> chroot() changes the root directory of the calling process to that specified in path. This directory will be used for pathnames beginning with /. The root directory is inherited by all children of the calling process.

The build process is based on **cross-compilation**. Build / host / target.
We build a cross compiler to compile our packages on our host, and then run the binaries on lfs.

ld-linux-x86-64.so.2 = dynamic loader. Provided in the glibc package. 
