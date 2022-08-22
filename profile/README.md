# AOSP Mainline

AOSPM is a collaborative project to run upstream Linux and AOSP on "form factor" devices, traditionally phones.
Whilst the majority of upstream AOSP testing is done with dev boards like the Thundercomm RB3 (db845c), these can often
be prohibitive for hobbyist developers, and lack useful features like modem/GPS, haptics, batteries, etc... Phones with
the same SDM845 SoC are easily obtainable and with some soldering to expose UART can become just as effective dev devices.

## Supported phones

 * Xiaomi PocoPhone F1
 * OnePlus 6 (6T TBD)
 * SHIFTPHONES SHIFT6mq
 * FairPhone 4
 * yours...?
 
The kernel is regularly seeing support for more phones, postmarketOS host an [an excellent wiki which includes many of these devices](https://wiki.postmarketos.org/wiki/Devices).
You can see also browse by SOC, e.g. [the Snapdragon 845 page](https://wiki.postmarketos.org/wiki/Qualcomm_Snapdragon_845_(SDM845)), contributions are always welcome!

If your device isn't yet supported but has an SDM845 or similar SoC, bringing up AOSPM should be relative straightforward!

TBD: porting guide? In the meantime, the wiki has some useful resources: https://github.com/aospm/android_device_generic_sdm845/wiki

## The repos

* https://github.com/aospm/android_device_generic_sdm845
  * Primary device repo, contains all necessary abstractions to support SDM845 and similar devices with mostly shared definitions
* https://github.com/aospm/qrild
  * Work in progress Radio HAL, currently a big mess, used with associated "rild" feature branch in d/g/s
* https://github.com/aospm/external_vibrator-ff
  * Generic vibrator HAL using forcefeedback API, try it on your devboard by attaching a game controller with rumble!
* https://github.com/aospm/android-lights-hal
  * New lights HAL, written by SoMainline, supports generic backlights and LEDs
 

## Current development

 * AIDL Lights HAL
 * SMB2 (pmi8998) charger / fuel gauge drivers - currently using default health HAL, could add new features
 * Improve audio support / headphone switching - active kernel regressions
 * Radio HAL / RIL - https://github.com/aospm/qrild

## Next up

 * Investigate ways to reduce code carried on top of AOSP, integrate better with upstream HALs
 * Venus video transcoding
 * Calls?
