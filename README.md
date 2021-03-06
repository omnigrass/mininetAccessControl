# mininetAccessControl

## Setup
http://www.brianlinkletter.com/set-up-mininet/

## Topology
![topology](resources/Topology.jpg)

## Topology of authTopo.py
![Topology](resources/authTopo.png)

## Setup
###-> in virtual machine
$ sudo dhclient eth1
$ ifconfig eth1

###-> in Terminal
`$ ssh -Y mininet@192.168.56.101`
or
`$ ssh -X mininet@192.168.56.101'

*user: mininet | pw: mininet

## Run authTopo.py
1. Clone this repo in your virtual machine 
2. cd into `mininetAccessControl`
3. Make authTopo executable by running `$ sudo chmod 777 authTopo.py`
4. run `$ sudo ./authTopo.py`
5. open another terminal (preferrably use tmux)
6. Launch controller by running `ryu-manager controller.py`
7. 

## Use Pox
1. install pox <br>
```$ git clone http://github.com/noxrepo/pox```

2. make sure no other controller is running <br>
```$ sudo killall controller```

3. paste `poxController.py` and `allowedMacs.txt` to `/home/mininet/pox/pox/misc/`

3. run pox testController <br>
```$ cd pox
$./pox.py log.level --DEBUG misc.poxController```

This runs a custom topology with a Server on host 4
##Useful tools
####Mininet GUI
http://www.brianlinkletter.com/how-to-use-miniedit-mininets-graphical-user-interface/


##Troubleshooting
For Error:
`Exception: Error creating interface pair (s1-eth1,s2-eth1): RTNETLINK answers: File exists` <br>
run <br>
`$ sudo mn -c`

##Controller used
[Ryu](https://osrg.github.io/ryu/) <br>
[Ryu Starter pack](http://sdnhub.org/releases/sdn-starter-kit-ryu/)
