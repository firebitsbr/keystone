This documentation explains how to build & install Keystone on all kind of nix OS.
For Windows, see [COMPILE-WINDOWS.md](COMPILE-WINDOWS.md)


0. Dependency

CMake is required to build keystone.

- On Mac OS X, you can install "cmake" with "brew".

        $ brew install cmake

- On Ubuntu Linux, install "cmake" with:

        $ sudo apt-get install cmake


1. From the root directory of Keystone source, compile as a dynamic library
   with the following commands.

        $ mkdir build
        $ cd build
        $ ../make-share.sh

   You can also compile static a library with:

        $ mkdir build
        $ cd build
        $ ../make-lib.sh


2. Right after building, install Keystone.

        $ sudo make install

   Keystone is installed in '/usr/local', depending on your distribution (eg. Ubuntu) you might
   need to add '/usr/local/lib' to '/etc/ld.so.conf'. Then update the dynamic linker
   with:
        
        $ sudo ldconfig
   
   Besides the libraries & C header files under  thedirectory "include/keystone",
   this step also installs a tool named "kstool" on the system.
   (The source of "kstool" is in the directory "kstool/kstool")


3. Test Keystone with "kstool" like below.

        $ kstool x32 "add eax, ebx"

   Run "kstool" without any option to find out how to use this handy tool.


4. Learn more on how to code your own tools with our samples.

   For C sample code, see code in directory samples/

   For Python sample code, see code in directory bindings/python/