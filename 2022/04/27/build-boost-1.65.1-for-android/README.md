[![cogroid.com](https://github.com/cogroid/resources/raw/main/images/banner/cogroid-48.png)](https://cogroid.com)

# Build Boost 1.65.1 for Android

### Prerequisites

* 4GB RAM machine

* Ubuntu server 18.04 LTS 64 bits

### Prepare

* [Initial Server Setup with Ubuntu 18.04](https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-18-04)

```
sudo apt-get install build-essential

sudo apt install gcc-multilib

sudo apt install g++-multilib

export BOOST_DIR=/home/cogroid/wrk/d-boost

mkdir -p ${BOOST_DIR}/tmp

cd ${BOOST_DIR}/tmp

wget https://dl.google.com/android/repository/android-ndk-r18b-linux-x86_64.zip

unzip android-ndk-r18b-linux-x86_64.zip

sudo mkdir -p /home/cogroid/local

sudo cp -rf ./android-ndk-r18b /home/cogroid/local/

sudo apt install clang
```

### Build for Android

```
mkdir -p ${BOOST_DIR}/armv7

cd ${BOOST_DIR}/armv7

git clone https://github.com/cogroid/d-boost.git

cd d-boost/make/armv7

make > build.log&
```

### Receive built files

```
Built files are at ${BOOST_DIR}/armv7/d-boost/build/armv7/install/libs/armeabi-v7a

```

---
[Head icons created by Freepik - Flaticon](https://www.flaticon.com/free-icons/head)
