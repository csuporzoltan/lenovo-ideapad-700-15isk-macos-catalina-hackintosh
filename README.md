# MacOS 10.15.5 for Lenovo IdeaPad 700-15ISK (EFI Folder)
![image](http://www.kepfeltoltes.eu/images/2020/06/11/846Rajzt_bla_1.png)

## Configuration:
- Intel Core i7 - 6700HQ (Skylake) 2.6GHz base, 3.5GHz turbo, 0.8GHz minimum
- Intel HD 530 - 1500MB VRAM, can go up to 2048MB
- 16GB of 2400MHz DDR4
- Audio: ALC235
- WiFi: Intel (can be replaced with DW1560)
- RTL8111 Ethernet
- (for me) M.2 NVME 250GB SSD

## What is working:
- AirDrop, Continuity, Handoff
- Full QE/CI with Metal
- Audio all the time (using ALCDelay)
- Bluetooth devices (i'm using AirPods 2 + Magic Mouse 1)
- Full WiFi speed
- Full speed USB3.0
- Full CPU PM management (with HWP) can go down as 0.8GHz (3 hours of battery life for me)
- Disabled PROCHOT (under 30%, the laptop refuses to go below 0.8GHz unless you disable PROCHOT) both kernel and kext level
- Web camera (OOTB)
- FileVault 2 (basic functionality in BIOS, no mouse just keyboard)
- iMessage and FaceTime (you have to provide your own serial number!)
- HDMI (see What is not working section)
- HDMI audio
- Full combo jack (see Other programs section)

## What is not working:
- HDMI unplugging: For some reason, when you unplug the HDMI, the internal screen remains black. The solution is that put the laptop into sleep BEFORE plug in the cable. Sleep -> Wakeup -> Plug in HDMI, this way it works every unplug until reboot.
- Netflix on Safari (and DRM contents like Apple Music's Beats1 radio and Apple TV+)
- Apple Watch Unlock and Instant Hotspot is a little bit buggy, sometimes not working. This is a hardware issue, because the DW1560 is not a native card. If you do care about these, consider buying a Broadcom BCM94360NG instead of the DW1560. (if you do buy the broadcom one, dont forget to delete all the wifi related kexts!)
- Internal SDCard reader 
- OBVIOUSLY the Nvidia card (DONT forget to disable in bios, otherwise it's running all the time sucking power!!!)


## Other programs to use:
- freqVectorsEdit.sh (https://github.com/Piker-Alpha/freqVectorsEdit.sh) to change MacBookPro13,1's 1.2GHz low-mode to 0.8GHz
- VoltageShift (https://github.com/sicreative/VoltageShift) to undervolt the CPU by 0.15V 
- ALCPlugFix (https://www.tonymacx86.com/attachments/alcplugfix-zip.284678/) to fix the headphone combojack issue
- one-key-hidpi (https://github.com/xzhih/one-key-hidpi) to enable HiDPI
- Hackintool (https://www.tonymacx86.com/threads/release-hackintool-v3-x-x.254559/) to disable hibernate mode and sleepimage

## BIOS settings:
- Disable eGPU
- Disable Secure Boot (or sign Clover)

## Note:
- For some reason, in the setup and in the recovery stage of macOS, the ApplePS2SmartTouchpad kext is not loading. I haven't been able to find a reason for it, but you can use an USB mouse and keyboard for that time. After install, the kext is loading and working 100% of the time, so i'm not bothered. 

# Installation
Make an USB stick with MacOS then paste my EFI folder. Change the boardserial and serial number to your own. Enjoy! 
