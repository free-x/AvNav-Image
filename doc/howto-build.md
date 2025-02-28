# Howto Build

## Preparation

- First read the documentation of [pi-gen](https://github.com/RPi-Distro/pi-gen/blob/master/README.md) carefully
- Install required tools

## Clone 

Clone necessary repos 
- Either Bookworm ARMHF
```console
git clone https://github.com/RPi-Distro/pi-gen.git
```

- or Bookworm ARM64
```console
git clone https://github.com/RPi-Distro/pi-gen.git -b arm64
```

- Clone stages for AvNav

```console
git clone https://github.com/free-x/stage-avnav.git
git clone https://github.com/free-x/stage-sk.git
git clone https://github.com/free-x/stage-mcs.git
```

## Link stages 

```console
cd pi-gen
ln -s ../stage* .
```

## Configuration

Build your config. For example

```
RELEASE='bookworm'
IMG_NAME='avnav-bookworm-armhf'
TARGET_HOSTNAME=avnav
KEYBOARD_KEYMAP=de
KEYBOARD_LAYOUT=German
TIMEZONE_DEFAULT=Europe/Berlin
STAGE_LIST="stage0 stage1 stage2 stage-sk stage-mcs stage-avnav"
ENABLE_SSH=1
WPA_COUNTRY=DE
FIRST_USER_PASS='raspberry'
DISABLE_FIRST_BOOT_USER_RENAME=1
USE_QCOW2=0
AVNAV_DAILY=1
export AVNAV_DAILY
```

## Build

```console
sudo ./build.sh -c <your_config>
```

Take a large cup of coffee





 

