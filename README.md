# AndroidStuff
A collection of my Android device knowledge


## Devices
* [LG H830](https://github.com/crossan007/AndroidStuff/blob/master/H830.md) (T-Mobile Variant of LG G5)
* LG D580 (AT&T Variant of LG G3)

# Partitions

## EFS
  IMEI and SIM Unlock can be stored on a phone's EFS partitions located here:
  *  /dev/block/bootdevice/by-name/modemst1
  *  /dev/block/bootdevice/by-name/modemst2
  *  /dev/block/bootdevice/by-name/fsg
  
  Quick backup script:
```
adb shell
dd if=/dev/block/bootdevice/by-name/modemst1 of=/sdcard/modemst1-original.img
dd if=/dev/block/bootdevice/by-name/modemst2 of=/sdcard/modemst2-original.img
dd if=/dev/block/bootdevice/by-name/fsg of=/sdcard/fsg-original.img
exit
adb pull /sdcard/modemst1-original.img
adb pull /sdcard/modemst2-original.img
adb pull /sdcard/fsg-original.img

```

