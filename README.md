<a href="https://scan.coverity.com/projects/hyperstart">
  <img alt="Coverity Scan Build Status"
       src="https://scan.coverity.com/projects/12404/badge.svg"/>
</a>

# The init Task for HyperContainer

You can get the binary installer of HyperContainer and HyperStart through [The Hyper Page](https://github.com/hyperhq/hyperd)

## Build from source 

clone this repo, and make sure you have build-essentials installed. Go into the working copy and

    > ./autogen.sh
    > ./configure
    > make

Then you can find `hyper-initrd.img` in the build directory, together with a pre-built kernel.

If you want to run hyperstart with 64-bit ARM architecture, please reconfigure with flag --with-aarch64,

    > ./configure --with-aarch64
    > make

If you want to get the boot disk file for VirtualBox, please reconfigure with flag --with-vbox,

    > ./configure --with-vbox
    > make

Then you can find `hyper-vbox-bootimage.iso` in the build directory. Booting from this iso will
bring you to the hyper world.

### Building for [Intel](https://www.intel.com) [Clear Containers](https://clearlinux.org/features/intel%C2%AE-clear-containers)

Clear Containers uses hyperstart in 'application mode', that is, not as the init process. To build hyperstart in this mode you need to pass some extra arguments to `autogen.sh`.

    > ./autogen.sh
    > ./configure --enable-daemon
