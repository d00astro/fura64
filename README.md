# fura64
Random stuff for the original 2016 Pine64 A65, with LCD. 
I've tried many times to make something useful with this thing but I alway struggle to finde the resources I need, so I decided to collect them here as I need them.
I never had much luck with the GPIOs on this thing, so I think I won't even bother with that. 

I might, however, turn this ino something more specific if I find a use case that works well for this device. 

## Armbian Version
The Pine64 A64(+) LCD does not seem to work with any Linux (pine?) kernels newer than 3.10 so I recommend using [`Armbian_5.90_Pine64_Ubuntu_xenial_default_3.10.107_desktop`](https://archive.armbian.com/pine64/archive/Armbian_5.90_Pine64_Ubuntu_xenial_default_3.10.107_desktop.7z )

## Getting the LCD and Touchscreen to work
1. Edit the file `/boot/armbianEnv.txt`, setting `pine64_lcd=on` instead of `off`.;
2. Edit the file `/etc/modules`, adding a line with `gt9xxf_ts` 

## Getting the LCD to maximum brightness
Run the script `max_lcd_brightness`, it can be set to run automaticall on startup by adding the `maxlcd.desktop` file to `~/.config/autostart`







