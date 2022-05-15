[![cogroid.com](https://github.com/cogroid/resources/raw/main/images/banner/cogroid-48.png)](https://cogroid.com)

# Build libatomic_ops 7.6.2 for Android

### Prerequisites

* 4GB RAM machine

* Ubuntu server 18.04 LTS 64 bits

### Prepare

* [Initial Server Setup with Ubuntu 18.04](https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-18-04)

```
sudo apt-get install build-essential

sudo apt install gcc-multilib

sudo apt install g++-multilib

export AO_DIR=/home/cogroid/wrk/d-libatomic_ops

mkdir -p ${AO_DIR}/tmp

cd ${AO_DIR}/tmp

wget https://dl.google.com/android/repository/android-ndk-r18b-linux-x86_64.zip

unzip android-ndk-r18b-linux-x86_64.zip

sudo mkdir -p /home/cogroid/local

sudo cp -rf ./android-ndk-r18b /home/cogroid/local/

sudo apt install clang
```

### Build for Android

Set APP_PKG to package name of your android app.

```
export APP_PKG=com.cogroid.atomspace.tester
```

```
mkdir -p ${AO_DIR}/armv7

cd ${AO_DIR}/armv7

git clone https://github.com/cogroid/d-libatomic_ops.git

cd d-libatomic_ops/make/armv7

sudo apt update

make > build.log&
```

```
sudo apt update

make install
```

### Receive built files

```
Built files are at /home/cogroid/local/libatomic_ops/armv7
```

---
[Head icons created by Freepik - Flaticon](https://www.flaticon.com/free-icons/head)
