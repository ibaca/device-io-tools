## 1. Install java 8
http://www.webupd8.org/2014/03/how-to-install-oracle-java-8-in-debian.html

## 2. Install toolchain (cross-compiler raspberry pi)
http://jeremy-nicola.info/portfolio-item/cross-compilation-distributed-compilation-for-the-raspberry-pi/

You can skip raspberrypi-tools compilation, just...
```
$ cd <workdir>
$ git clone https://github.com/raspberrypi/tools.git --depth=1
$ ln -s /<workdir>/tools/arm-bcm2708/gcc-linaro-arm-linux-gnueabihf-raspbian/bin/arm-linux-gnueabihf-gcc /<workdir>/tools/bin/gcc
```
Set device-io env PI_TOOLS=/<workdir>/tools

## 3. Compile device IO
https://wiki.openjdk.java.net/display/dio/Getting+Started

```
$ make
```

## 4. Install 
```
$ scp <workdir>/device-io/build/jar/dio.jar pi@<IP>:/home/pi/ejdk1.8.0/lib
$ scp <workdir>/device-io/build/so/libdio.so pi@<IP>:/usr/lib
```
