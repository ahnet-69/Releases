# Passing Strong Integrity On Custom Roms
Custom roms have various methods to spoof stuff to play services which allow us to pass device integrity out of the box. Unfortunately this interferes with [TrickyStore](https://github.com/5ec1cff/TrickyStore) and we do not pass strong. _(VERY SIMPLIFIED EXPLANATION)_

## Requirements
- Root (KSU/APATCH/MAGISK)
- Working keybox (unrevoked)
- Rom supporting props to disable pihooks (AOSPA supports it)
- brian
- bomb?

## Steps
- Be on the latest Rom build released.
- Flash The latest [TrickyStore](https://github.com/5ec1cff/TrickyStore) Module in your root manager.
- Flash The latest [Play Integrity Fix](https://github.com/chiteroman/PlayIntegrityFix) Module in your root manager.
- Remember to put your working keybox at /data/adb/tricky_store. (No need to modify target.txt for broken tee. Latest version auto detects)
- Set the following props

```sh
setprop persist.sys.pihooks.disable.gms_props true
```
```sh
setprop persist.sys.pihooks.disable.gms_key_attestation_block true
```
- After a reboot you should be passing strong.

### NOTE
- Remember to add your apps in /data/adb/tricky_store/target.txt if they still detect root
- Additionally some apps check for weird dirs such as TWRP or manager apps like KernelSU or apatch ( Keep that in mind )
