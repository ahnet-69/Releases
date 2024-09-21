# Bootloader Locking Guide for Xperia 1/5 II


> [!Warning]
> DO NOT ATTEMPT BOOTLOADER RE-LOCKING ON CARRIER MODELS UNLOCKED USING QUNLOCKTOOL!
> INCLUDING A002SO,SOG02,SOG01,SO-52A,SO-51A
> YOU WILL NOT BE ABLE TO UNLOCK AGAIN!
> **YOU HAVE BEEN WARNED!**

NOTE: YOUR DATA WILL BE WIPED IMMIDIATELY UPON LOCKING. **KEEP THAT IN MIND**

## Requirements
- A phone runinng latest AOSPA build
- PC with platform tools setup
- Brian
- possibly bomb?

## Method
- Sideload the latest build through AOSPA recovery. ( NO NEED FOR CLEAN FLASH ).
- Make sure your phone is plugged in to your PC and restart your phone. Once the screen goes black hold volume up ( NOT POWER BUTTON ). It will vibrate once and boot into fastboot [ LED TURNS BLUE ]
- Install fastboot drivers using respective GUIDE on rom's XDA.
- Run the following command:
```sh
fastboot erase avb_custom_key
```
- Then Download the avb_custom.img from the release on github of the rom build  you are using and flash it with the below command:
```sh
fastboot flash avb_custom_key avb_custom_key.img
```
- After the flash is done follow step 2 to reboot back to fastboot [ BLUE LED MODE ].
- run the following command:
```sh
fastboot oem lock
```
- Reboot your phone.
- You will see that phone shows a screen displaying that a custom OS was loaded. You can happily ignore it
- After it is done wiping the phone it will boot into your ROM. enjoy!

Note: You can unlock your phone again by getting unlock code from sony website and unlocking using fastboot.

Incase your device says its curropt retry the guide otherwise contact us over at our telegram channels. Thankyou!

[**[Ahnet Build Support](https://t.me/ahnetsdiscussion)**]

[**[XperiaChat](https://t.me/SonyXperiaChat)**]
