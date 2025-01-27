need ubuntu 16.04 linux version to  run this code..dont install higher version above ubuntu 16.04  ..once installtion done use below commands to install neccesary packages for ns3

1. sudo apt-get update
2.sudo apt-get install build-essential gcc g++ python git mercurial unzip cmake libpcap-dev libxerces-c-dev libpcre3-dev flex bison pkg-config autoconf libtool libboost-dev libboost-iostreams-dev qt4-dev-tools gnuplot-x11 libboost-all-dev libboost-signals-dev libboost-filesystem-dev

after above packages installation over ..use below steps to install our coding package

1.copy the P2P-aodv-dsr-gossip-consens-projectcode.tar.gz file which i send to u inside home directory and extract that.
2.it will extract as ns-allinone-3.25
3.open the terminal and goto cd ns-allinone-3.25 and then give these command 


CXXFLAGS="-std=c++11 -Wno-unused-parameter" ./build.py


it will install the ns3 package..after installtion successful ..follow below steps

4.input script for each protocols kept inside 
ns-3.25/scratch/input-cons.cc -->for consensalgorithm
ns-3.25/scratch/input-aodv.cc -->for aodv protocol
ns-3.25/scratch/input-dsr.cc -->for dsr 
ns-3.25/scratch/input-gossip.cc -->for gossip protocol
 
5.type cd ns-3.25 and then type ./waf --run scratch/input-cons
same way for other protocols
./waf --run scratch/input-aodv
./waf --run scratch/input-dsr
./waf --run scratch/input-gossip
 
it will create outputs output-cons.xml for cons input file ..same way for other input files like output-aodv.xml,output-dsr.xml and output-gossip.xml..
and print the pdr,delay,loss and average throughput in Mbps in end of terminal print ...

6.to compile animation use ./NetAnim 

then it will open the window ..go top left corner --to open button and click it and select output-*.xml from ns-3.25
and then click play button ..it will start animation

(note:if it not works copy NetAnim exe (looks like square cutting symbol) file from ns-allinone-3.25/netanim-3.108  folder and paste inside ns-3.25 after that follow above step) 



7.coding file is in folder
ns-3.25/src/gossip/model/gossip-routing-protocol.cc -->main coding for leader selection,byzatine attack creation and minimum energy based routing 
ns-3.25/src/gossip/model/gossip-routing-protocol.h-->declaration part of fucntions and variables 

ns-3.25/src/aodv/model/aodv-routing-protocol.cc -->coding for byzatine attack creation
ns-3.25/src/aodv/model/aodv-routing-protocol.h-->declaration part of byzatine fucntions and variables 

ns-3.25/src/dsr/model/dsr-routing.cc -->coding for byzatine attack creation
ns-3.25/src/dsr/model/dsr-routing.h-->declaration part of byzatine fucntions and variables 
ns-3.25/src/consalg/model/consalg.cc -->coding for consens algorithm 
ns-3.25/src/consalg/model/consalg.h-->declaration part of consalg fucntions and variables 

8.graph we plotted by varying number of nodes, and byzantine faults  ..we vary the number of nodes as we want and take the values which printed in end of terminal and put those values in .dat files and dispalyed as graph using gnuplot files and commands ..same way for byzantine faults ..  
we vary the input  inside input-aodv.cc as follows

size (50),//change nodes here
  enableBYZANTINE (true),//enebling or disable ddos
  num_Byzantine_faults(16),//number of byzatine faults

same way for input-dsr.cc file ..

for input-gossip.cc file we add to enable/disable gossip routing as addtional and it will given as follows

 size (50),
 enableBYZANTINE (true),
 enableGosssipRouting (true),
 num_Byzantine_faults(5),

9.graph files we kept as .dat files which is named as follows

ns-3.25/delay_p2p.dat
ns-3.25/delay_p2pfault.dat
ns-3.25/loss_p2p.dat
ns-3.25/loss_p2pfault.dat
ns-3.25/pdr_p2p.dat
ns-3.25/pdr_p2pfault.dat
ns-3.25/throughput_p2p.dat
ns-3.25/throughput_p2pfault.dat

these .dat files linked to .gnuplot files and those files are

ns-3.25/delay.gnuplot
ns-3.25/delayfault.gnuplot
ns-3.25/loss.gnuplot
ns-3.25/lossfault.gnuplot
ns-3.25/pdr.gnuplot
ns-3.25/pdrfault.gnuplot
ns-3.25/Throughput.gnuplot
ns-3.25/Throughputfault.gnuplot

10.to run gnuplot file use command 
gnuplot filename.gnuplot 
or to run all gnuplot files in single command
use
gnuplot *.gnuplot
it will genearate graph screens in .png format inside ns-3.25

