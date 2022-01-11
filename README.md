# v13015IKB-OpenCore
OpenCore Hackintosh configuration for Lenovo v130-15IKB (81HN)

/!\ I would NOT recommend you using a prebuilt configuration for your computer IF you do not have any hackintosh knowledge, that would make maintaining your config harder in case something breaks with future macOS versions, so learn how it all works first (at least the basics)!<br />

OpenCore configuration based on the configuration you can find at: https://github.com/Flex1911/macOS-V130-15IKB (last time i tried to make my own config it didn't work, so i'm basing everything off this existing one that DOES boot)<br />
OpenCore version is 0.7.7, when i update my config i'll also update it here, otherwise you can update it yourself following: https://dortania.github.io/OpenCore-Post-Install/universal/update.html\
This config has been tested with macOS 11 Big Sur 11.6.2 (20G314) and the operating system works fine.<br />

Here's the changes compared to the above config this one is based on:<br />
Updated OpenCore to 0.7.7, latest version at the time of writing (11/01/2022)<br />
The AirportItlwm kext has been updated to the latest version, previous one was buggy and kept struggling to connect or having random disconnection issues, all of that has been fixed.<br />
Set up the BootPicker GUI, as well as the startup chime! (Works on both speakers and headphones)<br />
Fixed the various "no schema" errors that showed up due to MatchKernel entries which weren't used anymore. Those errors were harmless but annoying, those have been fixed by removing those entries.<br />

My laptop's specs are pretty much identical to the config i based this on, however countrary to what the readme says, intel wifi *does* work in the original as well.<br />
I would like to note however that this laptop seems to come with an HDD sometimes. While macOS in an HDD will work, i recommend anything earlier than Big Sur, or you'll not have a great experience. An SSD for Big Sur and above IS recommended.<br />

I have not tested this config with Monterey, not sure if it boots. If it doesn't it's probably an easy fix.<br />
Well that's about it, have fun with macOS!
