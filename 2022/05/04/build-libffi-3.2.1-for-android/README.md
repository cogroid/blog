[![cogroid.com](https://github.com/cogroid/resources/raw/main/images/banner/cogroid-48.png)](https://cogroid.com)

# Build libffi 3.2.1 for Android

### Prerequisites

* 4GB RAM machine

* Ubuntu server 18.04 LTS 64 bits

### Prepare

* [Initial Server Setup with Ubuntu 18.04](https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-18-04)

```
sudo apt-get install build-essential

sudo apt install gcc-multilib

sudo apt install g++-multilib

export FFI_DIR=/home/cogroid/wrk/d-libffi

mkdir -p ${FFI_DIR}/tmp

cd ${FFI_DIR}/tmp

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
mkdir -p ${FFI_DIR}/armv7

cd ${FFI_DIR}/armv7

git clone https://github.com/cogroid/d-libffi.git

cd d-libffi/make/armv7

sudo apt update

make > configure.log&
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
Built files are at /home/cogroid/local/libffi/armv7
```

---
[Head icons created by Freepik - Flaticon](https://www.flaticon.com/free-icons/head)
