# Static Timing Analysis(STA)
## Basic Terminology
### Timing path 
Timing path is defined as the path between start point and end point.
### Start point
All input ports or clock pins of a sequential element are considered as valid start point.
### End Point
All output port or D pin of sequential element is considered as End point.

![time](https://user-images.githubusercontent.com/44607144/193751168-768f4dfc-0220-4e88-8b9b-7b7d73953f75.png)

* Timing path 1 : Input port to D pin of Lauch Flop.
* Timing path 2 : Clock port of capture flop to Output port
* Timing path 3 : Clock port of lauch flop to D pin of Capture flop
* Timing path 4 : Input port to Output port














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

#Contributors 
* Himanshu Kumar Rai
* Kunal Ghosh

# Acknowledgments
* Kunal Ghosh, Director, VSD Corp. Pvt. Ltd.
* Dr. Tsung-Wei Huang and Dr. Martin Wong (The University of Illinois at Urbana-Champaign, IL, USA)


# Contact Information
* Himanshu Kumar Rai, Research Scholar, International Institute of Information Technology, Bangalore himanshukumar.rai@iiitb.ac.in 
* Kunal Ghosh, Director, VSD Corp. Pvt. Ltd. kunalghosh@gmail.com


