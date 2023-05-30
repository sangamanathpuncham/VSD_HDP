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

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/6d08f2ca-b09c-4da3-b8f6-aadf8f7fa3d8)


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/990fac55-392a-4391-885e-800af8d3b398)

after optimization:
---

opt_clean -purge

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/cfab2a2b-563c-43e5-b4cc-9b27bdc79247)


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/f1a024e1-53a1-430a-897b-70f491bb0d3b)

opt_check2.v
---
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/07c15588-5703-4a06-9413-9fc755a47b8e)


read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog opt_check2.v

synth -top opt_check2

opt_clean -purge

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/53cebc83-867a-4397-9ab2-9437bbba32f3)

opt_check3
---
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/8bfecffa-b1e6-4e5e-bbf4-80b9a139143d)

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog opt_check3.v

synth -top opt_check3

opt_clean -purge

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/0d5f6157-0847-4dda-a531-04ec13f17a85)

multiple_modules_opt
---

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/8f96e651-5548-4089-817b-b849d848650b)

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog multiple_modules_opt.v

synth -top multiple_modules_opt

flatten

opt_clean -purge

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/3baa1698-bcd2-4f9b-af52-9cdd29bb5e91)



![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/49a1d6ba-aff8-4b63-a6cb-80275a87e1c2)


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/22b32399-5bc5-4eaa-8688-360f104c1ca5)


iverilog dff_cont1.v tb_dff_const1.v

./a.out

gtkwave dff_cont1.vcd

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/2608850c-5832-4a57-b558-98d5e5076f11)

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/4bbfc827-b072-4bdd-ae7b-4af7d841ecc9)

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog dff_const1.v

synth -top dff_const1

dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/21190cea-e9ec-4c65-98b0-48a1d601e3e7)


dff_const2
---

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/b812d30b-bdbf-4cc8-b142-b0be1168264b)


dff_const3
---

iverilog dff_cont1.v tb_dff_const3.v

./a.out

gtkwave dff_cont3.vcd


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/858c61bb-7f1d-4529-80ac-516a2f1f4c16)


read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog dff_const3.v

synth -top dff_const3

dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/a6cc9741-c74b-4b2b-a643-a6205ad0e374)


Seq optimization unused outputs
----

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/12776c5b-ee47-4c0e-9fdc-cfc9c12bb607)

counter_opt1
---

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog counter_opt1.v

synth -top counter_opt

dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/b3ecf6a8-d07d-4a73-80dd-ca5397174cfd)

counter_opt
---

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/43a54a01-4e13-4e26-abef-c848499413dc)


Day 4:
---

Gate lavel simulation and Synthesis simulation mismatch:
----
simulation mismatch due to activity signal in the @always(.....)

1)Ternary_operator:
---
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/900a4416-a53b-47a1-a1df-5dab31f11482)

iverilog ternary_operator_mux.v tb_ternary_operator_mux.v

./a.out

gtkwave tb_ternary_operator_mux.vcd

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/818de844-cc46-4876-85fc-8f60d9c944ea)


read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog ternary_operator_mux.v

synth -top ternary_operator_mux

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

write_verilog -noattr ternary_operator_net.v

show


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/772b5404-8d24-4fe6-a786-250686bf8063)

Gate level simulation:
---

setup required:
---

iverilog ../my_lib/verilog_model/primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v ternary_operator_net.v tb_ternary_operator_mux.v

./a.out

 gtkwave tb_ternary_operator_mux.vcd

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/f787159d-534e-4068-8f9d-63516af0bba8)

2)Bad_mux
---

iverilog bad_mux.v tb_bad_mux.v

./a.out

gtkwave tb_bad_mux.vcd

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/31efbb5d-db60-4055-9617-017ae4d74aed)

yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog bad_mux.v

synth -top bad_mux

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

write_verilog -noattr bad_mux_net1.v


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/f461ea88-eb0d-4f5c-bef8-a7f52ca5bf81)

GLS
---

 iverilog ../my_lib/verilog_model/primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v bad_mux_net1.v tb_bad_mux.v

 ./a.out

 gtkwave tb_bad_mux.vcd
 
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/8ac34205-5fdf-4354-b167-3f4cc35dfd0b)


> Mismatch is due to blocking statement

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/e473f824-5a9d-4eb7-a3f0-75d5f11c17bc)

iverilog blocking_caveat.v tb_block_caveat.v

./a.out

gtkwave tb_blocking_caveat.vcd

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/0d2e412b-e585-40f5-80f9-3dc5838a17ce)

GLS
---

iverilog ../my_lib/verilog_model/primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v blocking_caveat_net.v tb_blocking_caveat.v

./a.out

gtkwave tb_blocking_caveat.vcd

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/de6a1dbb-0bda-4f37-b815-504e1b9b155c)


Day:5
---
IF,CASE,FOR Loops for the Generate:
----

Both if and case statement inferes the mux but incomplete case and if gives raise to the latch formation.


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/865a5238-f1d2-410b-a707-b22c9e2c6c67)


Incomplete if :
---

1)incomp_if

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/1ee4852c-f355-4c94-8fb6-5d28f6547152)

iverilog incomp_if.v tb_incomp_if.v

./a.out

 gtkwave tb_incomp_if.vcd

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/042b698e-ca6d-4ef6-b34b-fdba86576dd8)

yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

 read_verilog incomp_if.v
 
 synth -top incomp_if
 
 abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
 
 show
  
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/e9282d34-d3d2-4124-a961-91fd8cac18f8)

2)incomp_if2

iverilog incomp_if.v tb_incomp_if.v

./a.out

gtkwave tb_incomp_if.vcd

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/93840160-d792-4498-a8f7-cf917dc95b44)

yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

 read_verilog incomp_if2.v
 
 synth -top incomp_if2
 
 abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
 
 show

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/5f29a3d1-ce02-4a6a-a3a3-d749a4c44c02)

Incomplete case statement:
---

1)incomp_case

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/04620f7f-8d07-4d48-af87-aa7565fa6a37)

iverilog incomp_case.v tb_incomp_case.v

./a.out

gtkwave tb_incomp_case.vcd

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/d128ad2c-a6d3-4faf-8ad9-543a8afff055)


yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog incomp_case.v
 
synth -top incomp_case
 
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
 
show

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/33119764-aed9-4f16-852a-f3382b63ad5e)


2)partial case:

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/4cf0773f-000d-400e-baf4-f7417afdc141)


yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog partial_case_assign.v
 
synth -top partial_case_assign
 
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
 
show

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/38c3fd11-5eee-4dca-8816-1a8086abc013)

3)Bad_case


iverilog bad_case.v tb_bad_case.v

./a.out

gtkwave tb_bad_case.vcd


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/0c068677-8b20-4bde-84ad-70707f84ad69)

yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog bad_case.v
 
synth -top bad_case

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
 
show

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/29a81dbd-a4e9-4576-9876-a10cf46106de)

Looping construction:
---

for and Generate for:
---
FOR
---

1)mux_generate

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/a4bcdcd2-c041-437b-90c0-f2b09735ddf6)

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/d94666be-1cb0-4b36-a9ef-3afe475a3f87)

iverilog mux_generate.v tb_mux_generate.v

./a.out

 gtkwave tb_mux_generate.vcd
 
 ![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/08fac435-6d49-486f-8ba0-451295cfe888)

2)demux

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/afc0b811-b52f-41c0-adac-8d25bb1b0397)

 iverilog demux_generate.v tb_demux_generate.v

./a.out

gtkwave tb_demux_generate.vcd

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/d427a447-7163-4a9e-869f-2948f3b83a3e)

Yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog demux_generate.v

synth -top demux_generate

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

write_verilog -noattr demux_generate_net.v

show

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/e920d8d2-a982-4683-a379-0fe32b10e2f7)

GLS:
---

 iverilog ../my_lib/verilog_model/primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v demux_generate_net.v tb_demux_generate.v

./a.out

gtkwave tb_demux_generate.vcd

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/c640fb90-6528-4eca-9bc6-48cb7645b233)

Generate for
---

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/fef5f5aa-0280-41a5-a2c4-aaa87fe949cc)

 iverilog rca.v fa.v tb_rca.v
 
 ./a.out

 gtkwave tb_rca.vcd
 
 ![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/c562d3c5-807d-4c5b-a38d-7b431bbc5b12)

Yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog rca.v fa.v

synth -top rca

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

write_verilog -noattr rcv_net.v

show fa

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/d0d6b652-b41b-458b-a1ff-f97b569aef41)


GLS:
---

iverilog ../my_lib/verilog_model/primitives.v ../my_lib/verilog_model/sky130_fd_sc_hd.v rcv_net.v tb_rca.v

 ./a.out
 
  gtkwave tb_rca.vcd

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/5b2d818d-a36d-4d9f-8eb3-a0ce3d472080)

Day:6
---

RTL simulation,synthesis and Gate leve simulation of 4-bit Ring Counter:
---
This project simulates the designed 4 bit ring counter. A ring counter is a digital sequential circuit that recirculates the same data throughout the circuit. It is one of the 

applications of shift registers.

A ring counter is a synchronous counter which transfers the same data throughout it. It is a typical application of shift register and can be designed using either D or JK flip-flops

(FFs). Here, a 4-bit ring counter is designed by a series of 4 D-FFs connected together in feedback manner. That means the output of the last FF is connected to the input of the first

FF. The clock signal is applied to all the FFs simultaneously.

Initially all the FFs are at RESET state. When the PRESET is applied, the input of the ring counter becomes 1. Now the output of the first FF (Q3) is 1 and other FF outputs (Q2, Q1 and 

Q0) will be low. Then for the next clock signal, Q2 becomes 1 and others outputs will be low. In this way, as the clock input changes, the outputs change and the data sequence rotates in

the ring counter.



State diagram is used to describe the behaviour of the digital sequential circuits. It shows the transitions of states from one state to the next as well as the output for a given input.

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/c3bffb56-f7dd-41dd-80eb-144a313ff0c6)

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/d112e3af-c7aa-419e-94f8-44621fa036ed)


Circuit:
---

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/54e3120a-99d2-47f4-b6e7-5f75724ed393)


Simulation:
--
iverilog ring.v tb_ring.v

./a.out
 
gtkwave dump.vcd
 
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/0d221b15-a332-4cbc-b8de-a75255c9e37e)
 


Synthesis:
---

yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog ring.v
 
synth -top ring_counter

dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
 
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
 
show

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/0578540a-3697-41ac-8c63-bf0d5a345b5c)


GLS:
---

 iverilog -DFUNCTIONAL -DUNIT_DELAY=#0 ../sky130RTLDesignAndSynthesisWorkshop/ring/iiitb_4bitrc/verilog_model/primitives.v ../sky130RTLDesignAndSynthesisWorkshop/ring/iiitb_4bitrc/verilog_model/sky130_fd_sc_hd.v ring_synth_net1.v tb_ringc.v
 
 ./a.out
 
 gtkwave dump.vcd

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/38da23cb-f9ef-4a9b-af47-2fbcd480ccdc)



Day:7(day 2 vsd-iat)
---
Basic STA:
----

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/9738bd74-3482-425e-8da8-7ac196df81b6)

Delay :
---

Delay is the function of input trasition and output load.

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/39b5adb8-6afd-4077-b545-54b892255af8)


Timing Arc :
---

Delay information from every input pin to every output pin which it can control.

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/7f776785-829c-4822-865e-50347927be20)

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/2cb98062-c5ff-494a-886a-a3b432e17315)

Timing Path
---

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/66cebb09-509a-4b3e-8fe9-400f52939fb5)


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/79720b10-dc49-4b1b-b12e-4100b1481b69)


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/d988d9c3-0b7e-4d0a-a45e-3053fceb87d5)


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/a40cc2fe-052a-43e9-8c83-d27eeb17e4f6)


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/9e856651-b670-4661-83b3-24f9b718eab7)


.LIB:
---

It contains * lib name * units * pvt conditions * delay information in the form of LUP table

std cell info like area , leakage power , pin info , funtionality of the output pin

timing sence of the pin (unateness and clk)

Exploring the .lib in DC Compiler:
----
csh

dc_shell

configure the lib in synapsys dc 

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/79cd293a-92a5-465b-9574-d752992f4162)

setup calculation with sampling point
---

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/645df29f-6081-49e5-83ca-bf7a9a7c94f9)

How to check the properties of .lib with respect to DC shell:
---

1)list lib

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/dd09ce25-b57b-4470-82d0-c0591322d3e6)

2)list the gates present in lib

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/5147ab06-e1fa-4e39-93c6-0eb96bb45f90)

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/90f8b8aa-49ac-4c4b-9edb-ad0f0dfa3f60)

3)display the pins and fuctionality

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/48652bea-fab4-4e07-b1b7-e0aa1986d1e8)

4)create list of cells

sh gvim my_script.tcl

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/6606fac0-4c9e-4791-86b4-2464f783b78c)

5)to know thw capacitance,area,clock

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/0c7828e7-52d3-46e2-aa4d-4d2692d9bdc0)


Day 8 (day 3 vsd-iat)
---

Advanced constraints:
---

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/9f7a2f94-aff7-4719-b16d-d29a9b68b49b)

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/290854a6-43c8-4379-abef-0aa29e89669f)

Clock jitter:
---
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/440e6daa-dedc-45e5-8223-a3a725102dfb)

Clock skew:
---

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/7b164f9b-5592-40a0-aec0-70fcb6f8958f)

Clock Modelling:

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/193d7f91-4129-42cc-89c2-68f0d00b05d8)

Summary

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/7e4a2530-049e-42f9-b919-17d54ef4c664)

How to constrain the Design:

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/128ad86a-ac52-4886-b910-2f4e2ba65de2)

Query the ports in the design:
----
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/a843e101-0d20-4475-857d-f100ac49abbc)

Query the clock 
---

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/f1a8e5b3-8857-42a5-b011-186f1daaee07)


Query the cell in the Design:
---

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/8bf186ee-dded-4922-a077-3525bafd2e47)


Creation of the clock
---

at port and pin

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/ee6edf30-3093-4aed-9c78-2695267772fe)


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/ce20cc1c-9b2e-4961-bf33-e8bbe44684f0)

Wave form creation

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/d36de97e-9892-4342-92b8-1d4db8cc3e9d)

I/O Constraints:
---

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/d06cb938-9f8c-4dde-b283-0d63e2c20543)

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/719d9c6e-9c1e-4022-a91b-2f1601091ae8)

Summary:
---

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/701bd6b9-9641-45b5-8e39-741677a8e0f0)

DC lab for constrain:
---

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/82cd7d02-ac57-4fb8-937e-a02e40b26378)


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/715a7ae6-39b8-4da2-b411-ab49a3821118)

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/9266ba0a-7c71-480c-874e-8ab4162dd07e)

DC query about pin
---

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/3c6d8b5b-425a-4b2e-b48d-d08a8caec88c)

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/566ab848-d307-4ef2-a652-f535c552aba3)


Clock creation in DC
---

get_ports *

current_design 

create_clock -name myclk -per 10 [get_ports clk]

get_clock *

report_clock *

remove_clock <name of the clock>

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/11781074-4085-4de0-8c4a-768e3c1b1f99)


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/58773580-1d55-4e94-8fd9-de195a15fb33)


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/804b2abb-9af1-4bc3-85ed-08c3d96ab0bc)


R2R Constarining:
---

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/bc4f7d09-ac2c-43b6-a17a-2827849d427c)


Constraining the Delays
-----
    
    
  ![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/b2a061a5-f0d0-4d58-8258-c63217674a50)

    
        create_clock -name myclk -per 10 [get_ports clk]
    
        set_clock_latency -source 1 [get_clocks myclk]
        
        set_clock_latency  2 [get_clocks myclk]
        
        set_clock_uncertainty -setup 0.5 [get_clocks myclk]
        
        set_clock_uncertainty -hold 0.2 [get_clocks myclk] 
        
        reamove_clock *
    
        report_timing
    
   ![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/d88b6b32-8d5a-436f-82b0-e62b77909784)
        
   ![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/503f0a89-3c41-4cc9-962b-2febd58f090b)
            
   ![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/96cafbf1-ebda-4681-a274-ee29fb105532)

   ![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/a46d739a-38cd-4f2e-8e31-a2697a33c6dd)
        
   ![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/b97f789a-0a8b-4328-8693-f41248621f6b)
Setup
    
    ![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/9fd77dcb-5db4-4c40-a929-8ce0bedb18d8)

    
   ![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/aaf7db32-f9e1-4187-856b-6856e1aae410)

    ![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/7a8dfd24-ff3c-48df-9e3c-d6202c35588a)

Hold
    
    
   ![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/17262de2-3699-453a-b786-28c2972c376e)

   ![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/560ada1a-29cc-4e68-bb64-515d29d7eb67)

    
IO delay
    
 ![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/50998f6a-3baa-46e1-80d1-4adf767618f4)
    
 ![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/67a7106f-b9b7-444a-b592-8689f6c8e3f3)


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/5b1f3010-28ee-42ee-b5ee-b07178e623ba)

set_input_delay -max <value: 5> -clock [get_clocks <name: MYCLK>] [get_ports <name: IN_A>];
    
set_input_delay -max <value: 5> -clock [get_clocks <name: MYCLK>] [get_ports <name: IN_B>];
    
set_input_delay -min <value: 1> -clock [get_clocks <name: MYCLK>] [get_ports <name: IN_A>];
    
set_input_delay -min <value: 1> -clock [get_clocks <name: MYCLK>] [get_ports <name: IN_B>];
    
set_input_transition -max <value: 0.3> [get_ports <name: IN_A>];
    
set_input_transition -max <value: 0.3> [get_ports <name: IN_B>];
    
set_input_transition -min <value: 0.1> [get_ports <name: IN_A>];
    
set_input_transition -min <value: 0.1> [get_ports <name: IN_B>];
    
report_timing -from <source pin name: IN_A> -trans -cap -nosplit > <name output file: a_trans>;
    
set_output_delay -max <value: 5> -clock [get_clocks <name: MYCLK>] [get_ports <name: OUT_Y>];
    
set_output_delay -min <value: 1> -clock [get_clocks <name: MYCLK>] [get_ports <name: OUT_Y>];
    
set_load -max <value: 0.4> [get_ports <name: OUT_Y>];
    
report_timing -to <destination pin name: OUT_Y> -trans -cap -nosplit > <name output file: out_load>;
    
report_port -verbose;
    

Generated Clock:
----

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/49b1be34-ac8a-457f-8487-a267702a3dec)

    
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/cb704428-b3ba-4f4f-a029-955df466ad4f)

    
Virtual clock , Max latency , rise and fall IO delays:
-----
    
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/8b946828-c947-4c8f-a4d5-5742c4b6810b)
    

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/c801fea5-925a-473f-b305-5463880ab116)



![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/6749b1cd-ea16-4525-a0de-94d706336ffd)

    
    I/O path constraining:
    -----
    
 ![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/36e1eebf-cb4d-45af-8b3d-a5bdae9b3d32)

    
 other way to define combi path
  ----
    
 ![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/3d5528a2-6e7d-479b-9c60-aa99e49898b9)

 reg2reg path having -ve flop and +ve flop
 -----
    
 ![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/b2af3da7-d4ce-4116-afc5-a21c97e0b441)

 Set_driving_cell
  -------
    
 ![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/644b613b-891d-45c9-9474-40a897384348)

    
 Finding the paths
  -----
    
 ![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/13992750-6764-4319-9eb8-a194cdcd8dbb)

    
 ![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/a571093a-cf30-4cea-9345-6417aec55191)

   
 ![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/11646d1f-fc64-4f7d-8469-4e742dae4cb8)

    
 Virtual Clock:
  -----  
    
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/bf2a5cb4-58f2-4887-bda3-144db3b0df67)


Constraining my Design:
----
 
.sdc
-----
    
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/301720a8-7a6c-41ea-a0f6-4ed9ad108d8c)



script_rc.tcl
-------
    
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/7afb8dcf-0132-4049-8fe2-e8e657d8f11b)



OpenSTA 
 ----
    
./sta script_rc.tcl
    
    
 Reports:
 -----
    
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/05fbee20-40a1-43e4-914b-efa429386f7f)
   

![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/e870d5f4-c68a-4ccf-abc4-47f86bdec7ba)


Circuit Design using sky130(ngspice):
------
    
Why we need circuit design and spice simulation beacause we are making timing claculation,cts other timing information comes from the LUP table that will be updated by 
    
circuit design and spice simulation (by tuning the w/l ration of pmos and nmos)
    
    
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/933d4370-8dea-4b61-8a01-c4df2908cf6a)


![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/cc5afca5-461e-4b6b-94db-e2c7934e4847)

    
    
![image](https://github.com/sangamanathpuncham/VSD_HDP/assets/132802184/7d54c32e-9da3-4996-89bb-b7c60752314a)

    
    
    
    
    
    

