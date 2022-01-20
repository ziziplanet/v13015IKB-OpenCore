## OpenCore Hackintosh configuration for Lenovo v130-15IKB (81HN)

OpenCore configuration based on the configuration you can find at: https://github.com/Flex1911/macOS-V130-15IKB (last time i tried to make my own config it didn't work, so i'm basing everything off this existing one that DOES boot)<br />
Obviously a big THANK YOU to the original author with of this config, without it i wouldn't be able to run macOS on this laptop.<br />

**I would NOT recommend you using a prebuilt configuration for your computer IF you do not have any hackintosh knowledge, that would make maintaining your config harder in case something breaks with future macOS versions, so learn how it all works first (at least the basics)!<br />
This config is mostly for personal use. While you can use this (serial isn't present), expect lazy workarounds and not always up to date kexts or OpenCore itself. If you read the first warning and still decided to continue, it means you should be experienced enough to mantain this config yourself overtime, i will only really update it when i need to for my personal needs.<br />**

NVRAM reset seems to be fine on this particular model of laptop, however your mileage may vary depending on firmware version (my current firmware version is 8VCN26WW, NVRAM reset worked with no issues or weird bricks). If you have a different firmware version and you don't want to reset NVRAM through OpenCore, update the firmware to clear it. If you don't want to see the Clear NVRAM option in the picker (perhaps out of fear of pressing it accidentally for safety reasons), disable AllowNvramReset in config.plist.<br />

OpenCore version is 0.7.7, maybe i will roll out some updated stuff here and there, otherwise you can update it yourself following: https://dortania.github.io/OpenCore-Post-Install/universal/update.html\<br />
This config has been tested with macOS 11 Big Sur 11.6.2 (20G314) and the operating system works fine.<br />
**UPDATE:** This config has been now tested with macOS 12 Monterey 12.1 (21C52). Please take a look at the Monterey section for more info.
**UPDATE 2:** You can get touchpad gestures working just fine by adding the VoodooRMI kext (https://github.com/VoodooSMBus/VoodooRMI).

# Changes compared to the original config:
- Updated OpenCore to 0.7.7, latest version at the time of writing (11/01/2022)<br />
- The AirportItlwm kext has been updated to the latest version, previous one was buggy and kept struggling to connect or having random disconnection issues, all of that has been fixed.<br />
- Set up the BootPicker GUI, as well as the startup chime! (Works on both speakers and headphones)<br />
- Fixed the various "no schema" errors that showed up due to MatchKernel entries which weren't used anymore. Those errors were harmless but now they don't show up anymore by having removed those entries.<br />
- Kexts haven't been updated (for Big Sur this still works fine, but for Monterey you need some kext updates. Please check the Monterey section.)<br />

My laptop's specs are pretty much identical to the config i based this on, so go check that (make sure your specs are identical as well, or stuff might just... not work ya know, however countrary to what the readme says, intel wifi *does* work in the original as well, it was added by the author but the readme.md stayed unchanged.<br />
I would like to note however that this particular model of laptop seems to come with an HDD sometimes. While macOS in an HDD will work, i recommend anything earlier than Big Sur, or you'll not have a great experience. An SSD for Big Sur and above IS recommended.<br />

## Monterey
So, for Monterey to not kernel panic during boot, you need to update a bunch of kexts. Mainly:
- Lilu (https://github.com/acidanthera/Lilu/releases)
- WhateverGreen (https://github.com/acidanthera/WhateverGreen/releases)
- AppleALC (https://github.com/acidanthera/AppleALC/releases)
- AirportItwlm (you need to put the Monterey version of this kext in, https://github.com/OpenIntelWireless/itlwm/releases)<br />
However it is recommended to just update them all while you're at it.
After this, you're met with a decision, or macOS will hang at boot:
- Fix Bluetooth (https://dortania.github.io/OpenCore-Install-Guide/extras/monterey.html)
- Delete the Bluetooth kexts from the kext folder (IntelBluetoothFirmware.kext and IntelBluetoothInjector.kext) which **will break bluetooth functionality**, but if you don't care about bluetooth that's fine.

Well that's about it, have fun with macOS!
