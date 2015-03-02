# master-thesis
KTH Master's thesis in Systems, Control and Robotics
# Install
The code for this project uses ROS Indigo.

You may need to install some additional packages to get things working.

Documentation is generated by [Doxygen](www.doxygen.org). The test framework
uses the [Google C++ Testing Framework](https://code.google.com/p/googletest/).
You can install both of these with

    sudo apt-get install doxygen libgtest-dev

As of writing (03/15) The `libgtest-dev` package on Ubuntu 14.04 does not
install libraries, only the headers. To create the library files you need to
compile them manually (code from
[here](http://www.thebigblob.com/getting-started-with-google-test-on-ubuntu/)
and
[here](http://stackoverflow.com/questions/13513905/how-to-properly-setup-googletest-on-linux)
for some pointers).

    sudo apt-get install cmake # install cmake
    cd /usr/src/gtest
    sudo cmake CMakeLists.txt
    sudo make
    
    # copy or symlink libgtest.a and libgtest_main.a to your /usr/lib folder
    sudo cp *.a /usr/lib

In the `code/test` directory there are some files which you can use to check if
things are properly configured. You can compile either with `cmake` or `g++`.

    g++ -g tests.cpp totest.cpp totest.hpp -lgtest -lpthread -o gpRun
    ./gpRun

or

    cmake CMakeLists.txt
    make
    ./runTests
