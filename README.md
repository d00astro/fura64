# fura64
Random stuff for the original 2016 Pine64 A65, with LCD. 
I've tried many times to make something useful with this thing but I alway struggle to finde the resources I need, so I decided to collect them here as I need them.
I never had much luck with the GPIOs on this thing, so I think I won't even bother with that. 

![A64 Board](pine64.png)


I might, however, turn this ino something more specific if I find a use case that works well for this device. 

## Armbian Version
The Pine64 A64(+) LCD does not seem to work with any Linux (pine?) kernels newer than 3.10 so I recommend using [`Armbian_5.90_Pine64_Ubuntu_xenial_default_3.10.107_desktop`](https://archive.armbian.com/pine64/archive/Armbian_5.90_Pine64_Ubuntu_xenial_default_3.10.107_desktop.7z )

## Getting the LCD and Touchscreen to work
1. Edit the file `/boot/armbianEnv.txt`, setting `pine64_lcd=on` instead of `off`.;
2. Edit the file `/etc/modules`, adding a line with `gt9xxf_ts` 

## Getting the LCD to maximum brightness
Run the script `max_lcd_brightness`, it can be set to run automaticall on startup by adding the `maxlcd.desktop` file to `~/.config/autostart`

## Python 3.8
Somewhere, eg in `~/Downloads/` , and as root (or using `sudo`, depending on debian flavor) run the following to install Python 3.8
```
apt install libffi-dev libbz2-dev liblzma-dev libsqlite3-dev libncurses5-dev libgdbm-dev zlib1g-dev libreadline-dev libssl-dev tk-dev build-essential libncursesw5-dev libc6-dev openssl git;
wget https://www.python.org/ftp/python/3.8.0/Python-3.8.0.tar.xz
tar xf Python-3.8.0.tar.xz
cd cpython-3.8*
./configure --prefix=$HOME/.local --enable-optimizations --disable-profiling
make -j -l 4
make altinstall
cd ..
rm -r Python-3.8.0
rm Python-3.8.0.tar.xz
```

Then add to `~/.bashrc`:
```
export PATH=$HOME/.local/bin/:$PATH
```






