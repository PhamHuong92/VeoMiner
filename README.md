# VeoMiner
Amoveo mining with OpenCL for NVidia and AMD GPU. Many GPU for single miner process. Low CPU needed for many GPU.

This miner is free-to-use with developer fee is 2%. Miner mines for 72 seconds of each hour for developer.

## Windows

### NVidia Run Dependencies
* Install Visual Studio 2015
* Install Cuda 9.1 (includes OpenCL)

### AMD Run Dependencies
* Install [AMD OpenCL](https://support.amd.com/en-us/kb-articles/Pages/OpenCL2-Driver.aspx)

### Releases

   [Windows Release Zip](https://github.com/PhamHuong92/VeoMiner/releases)


### Run

Example:
```
veominer.exe BEhisEvznTU6uM+PrmOk62mGfYxe2rJwMTcbUQk1v9alYGS6PKYSczo4297GP401V9DF20YRzaGUYguK3lapWE4= 0,1,2,3 192 128 SEED 65536 0
```

Template:
```
veominer.exe <Address> <DeviceIds> <BlockSize> <NumBlocks> <RandomSeed> <SuffixMax> <PlatformId> <PoolUrl>
```
* DeviceIds is optional an defaults to ALL. Use list for not ALL: 0,1,2,3,4,5,6,7
* BlockSize is optional and defaults to 64.
* NumBlocks is optional and defaults to 96.
* RandomSeed is optional. Set this if you want multiple miners using the same address to avoid nonce collisions.
* SuffixMax optional and defaults to 65536.
* PlatformId optional and defaults to 0.
* PoolUrl is optional and defaults to http://amoveopool2.com/work


## Linux

### Install dependencies

```
sudo apt-get install libcpprest-dev libncurses5-dev libssl-dev unixodbc-dev g++ git
```

### NVidia Install CUDA9.1 (includes OpenCL)

```
wget http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/cuda-repo-ubuntu1604_9.1.85-1_amd64.deb
sudo apt-key adv —fetch-keys http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/7fa2af80.pub
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
wget https://github.com/PhamHuong92/VeoMiner/releases/download/1.2/veominer_Ubuntu16_1.2.tar.gz
tar -xzvf veominer_Ubuntu16_1.2.tar.gz
```

### Run

Example:
```
./veominer BEhisEvznTU6uM+PrmOk62mGfYxe2rJwMTcbUQk1v9alYGS6PKYSczo4297GP401V9DF20YRzaGUYguK3lapWE4= 0,1,2,3 192 128 SEED 65536 0
```
