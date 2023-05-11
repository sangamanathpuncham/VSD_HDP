Day 0:
---

Creating GitHub using GitHub.com


Installation of following Tools:

yosys

OpenSTA

ngspice 

iverilog

gtkwave

magic

yosys
-------------------------------------------------------------------------------------------------------------------------
Befor install the yosys use following



![1](https://user-images.githubusercontent.com/132802184/237009900-f1137ffa-22e2-424f-ab96-d0deaf951d55.PNG)

$ git clone https://github.com/YosysHQ/yosys.git

$ cd yosys-master 

$ sudo apt install make (If make is not installed please install it) 

$ sudo apt-get install build-essential clang bison flex \

    libreadline-dev gawk tcl-dev libffi-dev git \
    
    graphviz xdot pkg-config python3 libboost-system-dev \
    
    libboost-python-dev libboost-filesystem-dev zlib1g-dev
    
$ make 

$ sudo make install


![5](https://user-images.githubusercontent.com/132802184/237016792-16691208-6beb-40e9-b807-0ef341daaca6.PNG)

OpenSTA
---
To install cmake for other than 18.04 version

$ wget -O - https://apt.kitware.com/keys/kitware-archive-latest.asc 2>/dev/null | sudo apt-key add -

$ sudo apt-add-repository 'deb https://apt.kitware.com/ubuntu/ bionic main'

$ sudo apt-get update

$ sudo apt-get upgrade


$ sudo apt install swig

$ git clone https://github.com/The-OpenROAD-Project/OpenSTA.git

$ cd OpenSTA

$ mkdir build

$ cd build

$ cmake ..

$ make


![6](https://user-images.githubusercontent.com/132802184/237019425-50a85b13-7c6d-4b17-b306-8c69bb2e0576.PNG)


ngspice
---


After downloading the tarball from https://sourceforge.net/projects/ngspice/files/ to a local directory, unpack it using:

$ tar -zxvf ngspice-37.tar.gz

$ cd ngspice-37

$ mkdir release

$ cd release

$ ../configure  --with-x --with-readline=yes --disable-debug

$ make

$ sudo make install


![4](https://user-images.githubusercontent.com/132802184/237011374-3b109c30-21bc-43f8-bf81-eb503ee57da0.PNG)


Iverilog
---
Steps to install iverilog

sudo apt-get install iverilog


gtkwave
---

Steps to install gtkwave

sudo apt update

sudo apt install gtkwave

magic
---
$   sudo apt-get install m4

$   sudo apt-get install tcsh

$   sudo apt-get install csh

$   sudo apt-get install libx11-dev

$   sudo apt-get install tcl-dev tk-dev

$   sudo apt-get install libcairo2-dev

$   sudo apt-get install mesa-common-dev libglu1-mesa-dev

$   sudo apt-get install libncurses-dev

Day:1
----

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/96f91d78-ebe6-4af2-8d49-b05b0421567a)


good_mux
---
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/e876725b-fc60-4a12-bb50-2b83821b41d6)


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/3f0f0697-22d4-417f-9ba0-f8531efa2eda)


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/d6580e7c-6598-40ad-9ef2-2dc629ae13e0)









