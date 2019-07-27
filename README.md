#### __Download source:__

```
$ mkdir ~/mydroid
$ cd ~/mydroid
$ repo init -u https://github.com/odroid-n2/android_manifest.git -b pie
$ repo sync --no-tags --no-clone-bundle
```

#### __Set up Linaro toolchains path:__

```
$ export PATH=$PATH:/PATH/TO/mydroid/vendor/linaro/gcc-linaro-6.3.1-2017.05-x86_64_aarch64-linux-gnu/bin
$ export PATH=$PATH:/PATH/TO/mydroid/vendor/linaro/gcc-linaro-aarch64-none-elf-4.9-2014.09_linux/bin
$ export PATH=$PATH:/PATH/TO/mydroid/vendor/linaro/gcc-linaro-arm-none-eabi-4.8-2014.04_linux/bin
```
+ Replace */PATH/TO/* with your current correct path.

#### __Set up ccache:__

```
$ export USE_CCACHE=1
$ export CCACHE_DIR=/path/to/ccache_cache/.ccache
$ prebuilts/misc/linux-x86/ccache/ccache -M 50G
```

#### __Select the target device:__

```
$ source build/envsetup.sh
$ lunch odroidn2-[userdebug|user|eng]
```

#### __Compile Android image:__

```
$ make -jxx selfinstall
```
+ Replace *xx* with number of cores of your CPU.

#### __For support refer to:__
+ https://forum.odroid.com/viewtopic.php?f=178&t=35463
