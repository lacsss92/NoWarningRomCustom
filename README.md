# NoWarningRomCustom
Delete Warning messages on boot with custom ROM on S10e

/!\ Need to be root (Magisk for example) & usb debugging ON

--------------

#Get the file

$ adb shell
adb> $ su
adb> # dd if=/dev/block/platform/13d60000.ufs/by-name/up_param of=/sdcard/Download/up_param.bin #extract the u_param
adb> # exit
adb> $ exit
$ adb pull /sdcard/Download/up_param.bin /home/debian/Bureau/ #send u_param file from smartphone to your vm
$ adb pull /sdcard/Documents/up_param.bin /home/debian/Bureau/ #backup to prevent any problem

--------------

change file extension from .bin to .tar
Open the tar file with archive manager
delete the two problematics files : svb_orange.jpg & booting_warning.jpg
Change back from .tar to .bin file

--------------

#Send back the file

$ adb push /home/debian/Bureau/up_param.bin /sdcard/up_param.bin
$ adb shell
adb> $ su
adb> # dd if=/sdcard/up_param.bin of=/dev/block/platform/13d60000.ufs/by-name/up_param

Reboot the phone
