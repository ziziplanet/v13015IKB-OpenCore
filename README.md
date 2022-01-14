OpenCore Hackintosh configuration for Lenovo v130-15IKB (81HN)

**/!\I would NOT recommend you using a prebuilt configuration for your computer IF you do not have any hackintosh knowledge, that would make maintaining your config harder in case something breaks with future macOS versions, so learn how it all works first (at least the basics)!<br />**

**/!\ This config is mostly for personal use. While you can use this (serial isn't present), expect lazy workarounds and not always up to date kexts or OpenCore itself. If you read the first warning and still decided to continue, it means you should be experienced enough to mantain this config yourself overtime, i will only really update it when i need to for my personal needs.**

**/!\ NVRAM reset seems to be fine on this particular model of laptop, however your mileage may vary depending on firmware version. Only reset NVRAM if you really need to, and if you want to be 100% on the safe side update the firmware to clear it. If you don't want to see the Clear NVRAM option (perhaps out of fear of pressing it accidentally for safety reasons), disable AllowNvramReset in config.plist.<br />**

OpenCore configuration based on the configuration you can find at: https://github.com/Flex1911/macOS-V130-15IKB (last time i tried to make my own config it didn't work, so i'm basing everything off this existing one that DOES boot)<br />
OpenCore version is 0.7.7, when i update my config i'll also update it here, otherwise you can update it yourself following: https://dortania.github.io/OpenCore-Post-Install/universal/update.html\<br />
This config has been tested with macOS 11 Big Sur 11.6.2 (20G314) and the operating system works fine.<br />

Here's the changes compared to the above config this one is based on:<br />
Updated OpenCore to 0.7.7, latest version at the time of writing (11/01/2022)<br />
The AirportItlwm kext has been updated to the latest version, previous one was buggy and kept struggling to connect or having random disconnection issues, all of that has been fixed.<br />
Set up the BootPicker GUI, as well as the startup chime! (Works on both speakers and headphones)<br />
Fixed the various "no schema" errors that showed up due to MatchKernel entries which weren't used anymore. Those errors were harmless but annoying, those have been fixed by removing those entries.<br />
Kexts haven't been updated (yet, mostly because Big Sur works fine, but when i upgrade to Monterey this will probably have all kexts updated for Monterey to work)<br />

My laptop's specs are pretty much identical to the config i based this on, so go check that (make sure your specs are identical as well, or stuff might just... not work ya know, however countrary to what the readme says, intel wifi *does* work in the original as well.<br />
I would like to note however that this particular model of laptop seems to come with an HDD sometimes. While macOS in an HDD will work, i recommend anything earlier than Big Sur, or you'll not have a great experience. An SSD for Big Sur and above IS recommended.<br />

~~I have not tested this config with Monterey, not sure if it boots. If it doesn't it's probably an easy fix.<br />~~
**UPDATE:** I have now tested this configuration with Monterey, it kernel panics in the current state mainly because of outdated kexts. After updating the kexts, you are left with two options: try to fix bluetooth or just kill it off by deleting the kexts, otherwise Monterey will hang at boot. More info here: https://dortania.github.io/OpenCore-Install-Guide/extras/monterey.html

Well that's about it, have fun with macOS!
