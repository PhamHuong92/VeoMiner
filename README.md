# VeoMiner
Amoveo mining with OpenCL for NVidia and AMD GPU on Windows or Ubuntu. This miner is free-to-use with developer fee minimum 1%, default 2%.

## FAQ
* My AMD rigs lock up or crash. Why?
  - Most AMD GPU need to set SyncKernel argument true. Set SyncKernel like this: sk=1
* Which arguments control hash rates?
  - BlockSize: d=?
  - NumBlocks: n=?
  - AutoLocal: a=0 or a=1
  - KernelVersion: kv=3 Was a previous veominer faster for you? Try kv=2 or kv=1
* Why was an older version of veominer was faster?
  - Kernel optimizations are not faster for every GPU. If an older veominer was faster for your GPU rig, set kv=2 or kv=1

## Windows

### NVidia Run Dependencies
* Install Visual Studio 2015
* Install Cuda 9.1 (includes OpenCL)

### AMD Run Dependencies
* Install [AMD OpenCL](https://support.amd.com/en-us/kb-articles/Pages/OpenCL2-Driver.aspx)

### Releases

   [Windows Release Zip](https://github.com/PhamHuong92/VeoMiner/releases)


### Run

Example 2.0 and up:
```
veominer.exe BEhisEvznTU6uM+PrmOk62mGfYxe2rJwMTcbUQk1v9alYGS6PKYSczo4297GP401V9DF20YRzaGUYguK3lapWE4= b=128 n=128 p=0 d=all
```

Template 2.0 and up:
```
veominer.exe <MinerAddress>.<OptionalWorkerId> <Option>=<OptionValue>
```
* DeviceIds: Default is ALL, d=0,1,2,3,4 or d=all
* BlockSize: Default is 64. b=64
* NumBlocks: Default is 100. n=100
* SuffixMax: Default is 65536. s=65536
* PlatformId: Default is 0. p=0
* AutoLocal: Default is false. a=false or a=true
* PoolUrl: Default is http://amoveopool2.com/work   u=http://amoveopool2.com/work
* KernelVersion: Default is 3. Available 1, 2, or 3. kv=3
* DevFeePercent: Default is 2. Available 1 and up. df=2
* RandomSeed: Deafult is Computer Name + Current Time. r=RaNdOmStRiNg

Example 1.5 and below:
```
veominer.exe BEhisEvznTU6uM+PrmOk62mGfYxe2rJwMTcbUQk1v9alYGS6PKYSczo4297GP401V9DF20YRzaGUYguK3lapWE4= 0,1,2,3 192 128 SEED 65536 0
```

Template 1.5 and below:
```
veominer.exe <Address> <DeviceIds> <BlockSize> <NumBlocks> <RandomSeed> <SuffixMax> <PlatformId> <AutoLocal> <PoolUrl> <SyncKernel>
```
* DeviceIds is optional an defaults to ALL. Use list for not ALL: 0,1,2,3,4,5,6,7
* BlockSize is optional and defaults to 64.
* NumBlocks is optional and defaults to 96.
* RandomSeed is optional. Set this if you want multiple miners using the same address to avoid nonce collisions.
* SuffixMax optional and defaults to 65536.
* PlatformId optional and defaults to 0.
* AutoLocal optional and defaults to false. Try set true. Some faster. Some slower.
* PoolUrl is optional and defaults to http://amoveopool2.com/work
* SyncKernel is optional. Default is false. Make multiple GPU kernel run synchronous. Most time bad.

## Linux

### Install dependencies

```
sudo apt-get install libcpprest-dev libncurses5-dev libssl-dev unixodbc-dev g++ git
```

### NVidia Install CUDA9.1 (includes OpenCL)

```
wget http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/cuda-repo-ubuntu1604_9.1.85-1_amd64.deb
sudo apt-key adv --fetch-keys http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/7fa2af80.pub
sudo dpkg -i cuda-repo-ubuntu1604_9.1.85-1_amd64.deb
sudo apt update
sudo apt install cuda -y
```

### AMD Install OpenCL
```
sudo apt-get install libclc-amdgcn mesa-opencl-icd
```

### Install release

```
- Ubuntu16
wget https://github.com/PhamHuong92/VeoMiner/releases/download/2.0/veominer_Ubuntu16_2.0.tar.gz
tar -xzvf veominer_Ubuntu16_2.0.tar.gz

- Ubuntu17
wget https://github.com/PhamHuong92/VeoMiner/releases/download/2.0/veominer_Ubuntu17_2.0.tar.gz
tar -xzvf veominer_Ubuntu17_2.0.tar.gz
```

### Run

Example:
```
./veominer BEhisEvznTU6uM+PrmOk62mGfYxe2rJwMTcbUQk1v9alYGS6PKYSczo4297GP401V9DF20YRzaGUYguK3lapWE4= b=128 n=128 p=0 d=all
```
