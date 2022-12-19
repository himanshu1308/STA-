# Static Timing Analysis(STA)
## Basic Terminology
#### Timing path 
Timing path is defined as the path between start point and end point.
#### Start point
All input ports or clock pins of a sequential element are considered as valid start point.
#### End Point
All output port or D pin of sequential element is considered as End point.

![time](https://user-images.githubusercontent.com/44607144/193751168-768f4dfc-0220-4e88-8b9b-7b7d73953f75.png)

* Timing path 1 : Input port to D pin of Lauch Flop.
* Timing path 2 : Clock port of capture flop to Output port
* Timing path 3 : Clock port of lauch flop to D pin of Capture flop
* Timing path 4 : Input port to Output port

#### Arrival Time :
The time required by a signal tp start at start point and reach the end point is called arrival time. It is calculated at the end point.

![image](https://user-images.githubusercontent.com/44607144/193751673-2a2eb193-c6fb-42be-b626-e3b04e196e91.png)
#### Required Time :
Expected time for signal to arrive.

![image](https://user-images.githubusercontent.com/44607144/193751862-f9cffe25-eeb3-4a07-a6a6-c22e51175a42.png)

#### Slack 
It is difference between Arrival time and required arrival time,
```
Slack= AT - RAT
```
* Max Slack (Setup Timing, Setup Slack, Setup Analysis) : The difference between expected maximum require time and actual arrival time.

* Min Slack (Hold Timing, Hold Slack, Hold Analysis) : The difference between actual arrival time and expected minimum require time.

#### Types of analysis 
![image](https://user-images.githubusercontent.com/44607144/193752506-eb19cacb-266d-477c-8ddc-41d03482c5dc.png)


## OpenTimer
OpenTimer is a new static timing analysis (STA) tool to help IC designers quickly verify the circuit timing. It is developed completely from the ground up using C++17 to efficiently support parallel and incremental timing.
Key features are:
* Industry standard format (.lib, .v, .spef, .sdc) support
* Graph- and path-based timing analysis
* Parallel incremental timing for fast timing closure
* Award-winning tools and golden timers in CAD Contests

### Installation guide
Type the following commands to intstall OpenTimer in your machine :
```
$ git clone https://github.com/OpenTimer/OpenTimer.git
$ cd OpenTimer
$ mkdir build
$ cd build
$ cmake ../
$ apt install cmake --classic (If it shows that cmake is not installed already)
$ make 
```
After successful build, you can find binaries and libraries in the folders ```bin and lib```, respectively.
#### Run Test
After successful build we are now ready to make test, to do so just type
```
$ make test
```
After all the test are passed, we are ready to go with OpenTimer.
To run opentimer:
```
$ cd OpenTimer 
$ ./bin/ot-shell
```
The image shown below will open after launching opentimer:


![image](https://user-images.githubusercontent.com/44607144/190922947-e2d46a74-44cc-438e-b17a-d31c0d4e1be2.png)

## Timing analysis of My design
I have performed the whole RTL to GDSII flow for my design, you can check the link for reference https://github.com/himanshu1308/iiitb_pwm.git 

type the following commands after opening terminal:
```
$ cd OpenLane 
$ sudo make mount
$ sta 
```
After this the OpenTimer tool will open, then type the following commands one by one:
```
read_liberty -max sky130_fd_sc_hd__fast.lib
read_liberty -min sky130_fd_sc_hd__slow.lib
read_verilog iiitb_pwm_gen.v
link_design iiitb_pwm_gen
read_sdc iiitb_pwm_gen.sdc
read_spef iiitb_pwm_gen.nom.spef
set_propagated_clock [all_clocks]
report_checks
```
![1](https://user-images.githubusercontent.com/44607144/193761227-53f9ac44-1e4b-48cf-b2e8-4cf734442685.png)

After writing these commands the OpenTimer tool will output results which have start Point, End Point and type of analysis. The results will look like the image shown below:

![2](https://user-images.githubusercontent.com/44607144/193761265-ad00b398-8110-4a42-8625-97a54f44996d.png)
At last line it is showing slack =







#Contributors 
* Himanshu Kumar Rai
* Kunal Ghosh

# Acknowledgments
* Kunal Ghosh, Director, VSD Corp. Pvt. Ltd.
* Dr. Tsung-Wei Huang and Dr. Martin Wong (The University of Illinois at Urbana-Champaign, IL, USA)


# Contact Information
* Himanshu Kumar Rai, Research Scholar, International Institute of Information Technology, Bangalore himanshukumar.rai@iiitb.ac.in 
* Kunal Ghosh, Director, VSD Corp. Pvt. Ltd. kunalghosh@gmail.com


