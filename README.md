linuxvmm
========

Based on http://www.cs.usfca.edu/~cruse/cs686s07/
Intended to be used with http://opensecuritytraining.info/AdvancedX86-VTX.html
which uses an ArchBang LiveCD image. The instructions for using the ArchBang arrangement
can be found [here](ArchBangLinuxVMM.txt)

```g++ -o mmake mmake.cpp```

```
./mmake linuxvmm
./mmake vmxmsrs
./mmake dram
```

```
sudo mknod /dev/vmm c 88 0
sudo mknod /dev/dram c 85 0
sudo chmod a+rw /dev/vmm
sudo chmod a+rw /dev/dram
```

```
sudo insmod linuxvmm.ko
sudo insmod dram.ko
```

```
g++ -o tryoutpc tryoutpc.cpp
g++ -o fileview fileview.cpp
```

```
sudo ./tryoutpc
sudo ./fileview /dev/dram
```

Observe value in EAX [15:0] ...