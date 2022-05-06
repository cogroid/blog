[![cogroid.com](https://github.com/cogroid/resources/raw/main/images/banner/cogroid-48.png)](https://cogroid.com)

# Build Guile 2.2 for Android

### Prerequisites

* 4GB RAM machine

* Ubuntu server 18.04 LTS 64 bits

### Prepare

* [Initial Server Setup with Ubuntu 18.04](https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-18-04)

```
sudo apt-get install build-essential

sudo apt install gcc-multilib

sudo apt install g++-multilib

sudo apt install flex

sudo apt install gdb

sudo apt install libiconv-hook-dev

sudo apt install libunistring-dev

export GUILE_DIR=/home/cogroid/wrk/d-guile

mkdir -p ${GUILE_DIR}/tmp

cd ${GUILE_DIR}/tmp

wget https://dl.google.com/android/repository/android-ndk-r18b-linux-x86_64.zip

unzip android-ndk-r18b-linux-x86_64.zip

sudo mkdir -p /home/cogroid/local

sudo cp -rf ./android-ndk-r18b /home/cogroid/local/

sudo apt install clang
```

### Build for Android

```
mkdir -p ${GUILE_DIR}/armv7

cd ${GUILE_DIR}/armv7

git clone https://github.com/cogroid/d-guile.git

cd d-guile/make/armv7

sudo apt update

make > configure.log&
```

```
sudo apt update

make update_makefile
```

```
sudo apt update

make build > build.log&
```

```
sudo apt update

make install
```

### Receive built files

```
Built files are at /home/cogroid/local/guile/armv7
```

---
[Head icons created by Freepik - Flaticon](https://www.flaticon.com/free-icons/head)
