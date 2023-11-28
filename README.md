# mining-versus-coin-on-Orange-Pi
Instruction to mining versus coin on Orange Pi

I have tested on [[Orange Pi 3 LTS]][1] and [Orange Pi 4 LTS][2], it works and give you 1.5MH/s - 1.7MH/s each OPi.

I ran them on Ubuntu Focal from the manufacturer, so please install the OS first.

Then you need to install some files to run it, the file `libssl1.1_1.1.1f-1ubuntu2_arm64.deb` included in this github in case that you cannot download from ubuntu.com, download to your OPi and execute
```shell
sudo dpkg -i libssl1.1_1.1.1f-1ubuntu2_arm64.deb
```


## Orange Pi 4 LTS
```shell
wget http://ports.ubuntu.com/pool/main/o/openssl/libssl1.1_1.1.1f-1ubuntu2_arm64.deb
sudo dpkg -i libssl1.1_1.1.1f-1ubuntu2_arm64.deb
```

## Orange PI 3 LTS
```shell
sudo apt-get install libomp5 -y
wget http://ports.ubuntu.com/pool/main/o/openssl/libssl1.1_1.1.1f-1ubuntu2_arm64.deb
sudo dpkg -i libssl1.1_1.1.1f-1ubuntu2_arm64.deb
```
## Mining instruction
Then download the CCMiner-ARM-optimized from here https://github.com/Oink70/CCminer-ARM-optimized/releases/

Both Orange Pi 3 LTS and Orange Pi 4 LTS using A53 so download the default miner
```shell
wget https://github.com/Oink70/CCminer-ARM-optimized/releases/download/v3.8.3-4/ccminer-3.8.3-4_ARM && sudo chmod +x ccminer-3.8.3-4_ARM
```

Start mining in screen by this command
```shell
screen -S versus -dm ./ccminer-3.8.3-4_ARM -a verus -o stratum+tcp://sg.vipor.net:5040 -u RKJ24LAUcLr5ANzJ5Gpu2RQKoqocznfTg4.OPi3LTS-2 -t 3
```

In case your OS does not have screen, install it `sudo apt install screen`

The number after `-t ` is the core you use, I suggest to use 3 cores of 4 cores of the OPi you have, running 4/4 cores will burn your board

The address after `-u ` is your versus address

This is the example for vipor pool, choose your pool you are familiar with.

Happy mining with Orange Pi!

Donate me some VERUS to `RKJ24LAUcLr5ANzJ5Gpu2RQKoqocznfTg4`

[1]: https://orangepi.vn/shop/orange-pi-3-phien-ban-lts-chip-allwinnner-h6-2gb-ram "Orange Pi 3 LTS"
[2]: https://orangepi.vn/shop/orange-pi-4-lts-ram-4gb-non-emmc "Orange Pi 4 LTS"
