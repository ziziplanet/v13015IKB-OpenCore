## OpenCore Hackintosh configuration for Lenovo v130-15IKB (81HN)

OpenCore configuration based on the configuration you can find at: https://github.com/Flex1911/macOS-V130-15IKB<br />
Thanks to the original author of this config!<br />

**This config is for personal use, and i'm just throwing this here for ease of access. While you can use this (serial isn't present), don't expect always up to date kexts or OpenCore itself, you should be experienced enough to mantain this config yourself overtime.<br />**

NVRAM reset seems to be fine on this particular model of laptop, however your mileage may vary depending on firmware version (my current firmware version is 8VCN26WW, NVRAM reset worked with no issues or weird bricks). If you have a different firmware version and you don't want to risk resetting NVRAM through OpenCore, update the firmware to clear it. If you don't want to see the Clear NVRAM option in the picker (perhaps out of fear of pressing it accidentally for safety reasons), disable AllowNvramReset in config.plist.<br />

OpenCore version is 0.7.7
This config has been tested with macOS 11 Big Sur and macOS Monterey 12.3

# Known issues
VoodooRMI (the driver for the touchpad gestures) hangs boot occasionally, so use the versions without it to install the os, then switch to the version with it.
Sleep works but sometimes after a while you get insta-wake both from sleep and when turning off the laptop. hold the power button or shut it down twice in a row with the power button when it turns back on to turn it off completely. this only happens sometimes so it's not a big deal for me.

# Changes compared to the original config:
- Updated OpenCore to 0.7.7, latest version at the time of writing (11/01/2022)<br />
- The AirportItlwm kext has been updated to the latest version, previous one was buggy and kept struggling to connect or having random disconnection issues, all of that has been fixed.<br />
- Set up the BootPicker GUI, as well as the startup chime! (Works on both speakers and headphones)<br />
- Fixed the various "no schema" errors that showed up due to MatchKernel entries which weren't used anymore. Those errors were harmless but now they don't show up anymore by having removed those entries.<br />

## Monterey
Monterey has been fixed, there are two configs with it. One for pre-install without bluetooth fixes or VoodooRMI (either for clean install or upgrade) and one for post-install with bluetooth fixes and VoodooRMI
