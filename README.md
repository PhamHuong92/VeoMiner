# VeoMiner
Amoveo mining with OpenCL for NVidia and AMD GPU on Windows or Ubuntu. This miner is free-to-use with developer fee minimum 1%, default 2%.

## FAQ
* My AMD rigs are slow for multiple GPU. Why?
  - Set sk=2 for AMD GPU
* How do I set alternate pools?
  - u=http://amoveopool2.com/work u=http://veopool.pw:8085/work u=http://159.65.120.84:8085
  - Pool fail over does not work with stratum connection yet

## Windows

### NVidia Run Dependencies
* Install Cuda (includes OpenCL)

### AMD Run Dependencies
* Install [AMD OpenCL](https://support.amd.com/en-us/kb-articles/Pages/OpenCL2-Driver.aspx)

### Releases

   [Windows Release Zip](https://github.com/PhamHuong92/VeoMiner/releases)


### Run

Example:
```
veominer.exe BOOLfeOfNfSAeLparTsIgIygGp3jxVWwJdeU5tGKKCoaBd8brgaye7WL/2PP+mLUGGYc8G+KLGUeyvApghtydQo= p=0 d=all u=stratum+tcp://stratum.amoveopool.com:8822
```

Template:
```
veominer.exe <MinerAddress>.<OptionalWorkerId> <Option>=<OptionValue>
```
* DeviceIds: Default is ALL, d=0,1,2,3,4 or d=all
* PlatformId: Default is 0. p=0
* Difficulty: Stratum connection only. Default is pool set. diff=9900
* PoolUrl: Default is stratum+tcp://stratum.amoveopool.com:8822 u=stratum+tcp://stratum.amoveopool.com:8822
* Set GetWork Alternate Pools with many u= Example: u=http://amoveopool2.com/work u=http://veopool.pw:8085/work u=http://159.65.120.84:8085  Pool fail over not work with Stratum yet
* SyncKernel: Default sk=0. Set sk=2 for AMD GPU
* FailAttemptsSwitch: Switch Pool after fa= fail attempt. Default fa=3
* ResumePrimarySeconds: Resume primary pool after rp= seconds. Default rp=600
* DevFeePercent: Default is 2. Available 1 and up. df=2
* ParallelBuffers: Only for sk=2, set pb=X parallel buffers. Default pb=2
* RandomSeed: Deafult is Computer Name + Current Time. r=RaNdOmStRiNg

## Linux

### Install dependencies

```
sudo apt-get install libcpprest-dev libncurses5-dev libssl-dev unixodbc-dev g++ git libcurl4-gnutls-dev libjansson-dev
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
wget https://github.com/PhamHuong92/VeoMiner/releases/download/2.8/veominer_Ubuntu16_2.8.tar.gz
tar -xzvf veominer_Ubuntu16_2.8.tar.gz

- Ubuntu17
wget https://github.com/PhamHuong92/VeoMiner/releases/download/2.7/veominer_Ubuntu17_2.7.tar.gz
tar -xzvf veominer_Ubuntu17_2.7.tar.gz

- Ubuntu18
wget https://github.com/PhamHuong92/VeoMiner/releases/download/2.8/veominer_Ubuntu18_2.8.tar.gz
tar -xzvf veominer_Ubuntu18_2.8.tar.gz
```

### Run

Example:
```
./veominer BOOLfeOfNfSAeLparTsIgIygGp3jxVWwJdeU5tGKKCoaBd8brgaye7WL/2PP+mLUGGYc8G+KLGUeyvApghtydQo= p=0 d=all
```

## API
* GET http://localhost:11363/hashrate
  - {"0":4503457400,"1":4503457308,"2":4503457108,"3":4503457008,"4":4503457008,"5":4503457008}
* GET http://localhost:11363/shares
  - {"accepted":111,"rejected":1}

