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

RTL Simulation
---

good_mux
---
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/e876725b-fc60-4a12-bb50-2b83821b41d6)


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/3f0f0697-22d4-417f-9ba0-f8531efa2eda)


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/d6580e7c-6598-40ad-9ef2-2dc629ae13e0)

Logic Synthesis
---

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/74a6c661-5109-41a9-8172-8ebcdfceb81e)


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/3bfdea55-0989-4cd0-ae26-38ae1bd38314)

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/0eed3e58-bd52-4cac-a3c4-e6c77c0c5930)

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/e169d20e-2db3-40d4-bd9c-ae0e71fae14d)


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/04169c8a-d52d-4aef-bd2f-394720c9f882)


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/91023dc3-f361-4df8-9210-f5c1b80cadb0)


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/c0557956-78a3-41f9-9166-30e23ad84968)


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/16fcbc0b-976d-43de-be22-d2b165a0c562)

Day:2
---
Heirachical and Flat synthesis:
---
Multiple_modules.v
---
gedit multiple_modules.v
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/5d3867bf-1e9d-419f-9156-25b3200892f4)

Hierachical
----
yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog multiple_modules.v

synth -top multiple_modules

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.li

show multiple_modules

write_verilog -noattr multiple_modules_hier.v

!gedit multiple_modules_hier.v

multiple_modules(hierachical):
---
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/44f36db8-fbe2-48ed-86da-088e06f543a9)

netlist
---
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/12a14c19-7c01-4203-ab88-755061d9b17a)

Flatten
---
yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog multiple_modules.v

synth -top multiple_modules

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.li

flatten

write_verilog -noattr multiple_modules_flat.v

!gedit multiple_modules_flat.v

multiple modules(flat):
---
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/b1e43ab3-d80a-4633-a54a-0c60602c45d0)


Netlist
---

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/13da41b4-2180-4a27-8d4e-2490fcf492ea)


Sub Module Level Synthesis:
---

yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog multiple_modules.v

synth -top sub_module1

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/f47ee4e7-e66c-4136-ae43-cb052924f3e0)


Simulation and Synthesis of Flops
---
iverilog simulation commands for asynchronous reset:

iverilog dff_asyncres.v tb_dff_asyncres.v

./a.out

gtkwave tb_dff_asyncres.vcd

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/b84ce639-216b-45ce-bbe0-0178ccd7ccdf)

Note:

1)Q goes high when the clock goes high

2)Q goes low once the asynchronous reset goes to high

Interesting Optimization:
---
1)Mul2 and Mul8
---

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/3bd5a1a2-4f72-44e8-803c-9575c07f46f4)



read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog mult_2

synth -top mul2

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/831961a2-5f0c-429c-80e6-341877d2c8e8)

show

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/7b77ce43-7905-45fa-b5fa-926470

mult_8
---

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/4e36a735-689e-4e47-9962-b4dc0d558852)

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog mult_8

synth -top mul8

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/a22f597e-01da-451d-9470-454b49531f2c)


Day 3:
---
Introduction to Logic Optimization:
---
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/bb3115db-37f1-42fd-9d3e-ef30414c7158)

ex: opt_check
---
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/a9fb5524-3008-4146-a3a9-07d629567559)

before opt
---
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog opt_check.v

synth -top opt_check

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/990fac55-392a-4391-885e-800af8d3b398)

after optimization:
---

opt_clean -purge

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/f1a024e1-53a1-430a-897b-70f491bb0d3b)







