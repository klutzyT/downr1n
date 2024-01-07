# downr1n
Downr1n enables tethered downgrades of checkm8 iOS devices to iOS 15, 14 and 13.

In my opinion, using [dualra1n](https://github.com/dualra1n/dualra1n) is a better option than downgrading if you have the necessary storage (if you dont theres also a --downgrade option in dualra1n). if you activate the localboot path it would be so much better, believe me XD.

# Usage
1: Download an IPSW file with the version you want to downgrade to and place it in the ipsw/ directory.

2: Execute the script (run it as root on Linux, dont run it as root on Mac OS).

Example: ./downr1n.sh --downgrade 14.3

The various command-line options are as follows:

      --downgrade        : Downgrade your device to iOS 15-13.0 tethered.

      --dfuhelper        : A helper tool to help anyone who is struggling to get into DFU mode manually.

      --jailbreak        : Jailbreak with dualra1n loader. Usage: `./downr1n.sh --jailbreak 14.8`.

      --taurine          : Jailbreak with taurine. Usage: `./downr1n.sh --jailbreak 14.3 --taurine`.

      --boot             : Boot the device.

      --keyServer        : Use this option to downgrade when the key server is not working at that moment. this only works on Mac OS. use ex: --downgrade 14.8 --keyServer 

      --dont-restore     : Avoids using futurerestore, this can be used to only create boot files. Example: `--downgrade 14.3 --dont-restore`.

      --fixBoot          : Boots the device using fsboot.

      --debug            : Debug the script.

---

# Dependencies
- please execute this command: python3 -m pip install pyimg4[compression] fastapi aiohttp ujson wikitextparser uvicorn.
- A disabled passcode on A10 and A11 devices.
- unzip, python3, libimobiledevice-utils, libusbmuxd-tools, xz-utils.
- An .iPSW file containing iOS 15, 14, 13.
- A device running macOS or a Linux distro (Live CDs are supported just ensure you have enough storage). It is recommended to use macOS, as it is likely more stable and faster. (**Windows subsystem for Linux is NOT supported**) 

# Issues Putting Device in PwnDFU Mode

- Theres is a DFU mode exists where the device's screen is black. However, when downgrading the device, it will exit and go back to recovery. To put the device into PwnDFU mode, you need to put it into real DFU mode by pressing poweroff+(volume down or home button). if you dont know how just use the --dfuhelper command. Once in PwnDFU mode, execute ./binaries/$(username)/gaster pwn to succeed. If the device is not in DFU mode, it will just loop.

# importants things

- downgrading from ios 16 to 14/13 or another version, you will have to bypass the setup somehow. **We will not provide a tutorial for this just look it up yourself**.

- on ios 13 the touch id doesn't work so the home button on iphone 7/7 plus will not work unfortunately.

- you can't downgrade to iOS 14.2 and lower on a11 (aka: iPhone 8/8 Plus and iPhone X) devices. Use 14.3+ on these devices

# Warnings
- I am **NOT** responsible for any data loss. The user of this program accepts responsibility should something happen to their device.
 **If your device is stuck in recovery, please run one of the following:**
   - futurerestore --exit-recovery
   - irecovery -n

# fixing some problems

- please execute wikiproxy.py manually if it gives error with the server key. for ex: sudo python3 wikiproxy.py

- if the error still occurres even after running the command above, and if you are getting this error after running future restore add this arg to your command (--keyServer) for example ./downr1n.sh --downgrade 14.5 --keyServer.

- remember if you use the next command or activate localboot it is better that you first downgrade and when you finish, then you can use --jailbreak to jailbreak the device and it will ask you to activate the localboot path.The reason why you should do this is because the localboot needs to be executed after --jailbreak

# Need Help?
- Join my discord server: [Dualra1nServer](https://discord.gg/Gjs2P7FBuk)

# How to Jailbreak?
- Jailbreak with dualra1n-loader: ./downr1n --jailbreak (YourVer = 14.3). Note: this does not actually jailbreak the device. When I say "jailbreak," I'm referring to the process of installing Sileo and bootstrapping the device. Dualra1n-loader only installs Sileo and bootstraps with the kernel patch.

- Jailbreak with Taurine: ./downr1n --jailbreak (YourVer = 14.3) --taurine. Note: this is not recommended.

# This project was created with love by Edwin :)

# Credits

- thanks to [uckermark](https://github.com/Uckermark/) for the amazing dualra1n-loader

- thanks to [sasa](https://github.com/sasa8810) for the code of download futurerestore ;|

- thanks to [KlutzyT](https://github.com/klutzyT) for improvements

<details><summary>Other credits for tools and codes used in downr1n</summary>

- [wikiproxy.py](https://github.com/afastaudir8/wikiproxy).

- [futurerestore](https://github.com/futurerestore/futurerestore) without futurerestore it couldn't be downgraded.  

- [palera1nLegacy](https://github.com/palera1n/palera1n/tree/legacy) some code based on palera1n legacy.

- [exploit](https://github.com/exploit3dguy/) for asrpatcher

- [iSuns9](https://github.com/iSuns9/restored_external64patcher) thank you for restored_external64patcher

- [Nathan](https://github.com/verygenericname) for the ramdisk
    
- [m1sta](https://github.com/m1stadev) for [pyimg4](https://github.com/m1stadev/PyIMG4)

- [tihmstar](https://github.com/tihmstar) for [pzb](https://github.com/tihmstar/partialZipBrowser)/original [iBoot64Patcher](https://github.com/tihmstar/iBoot64Patcher)/original [liboffsetfinder64](https://github.com/tihmstar/liboffsetfinder64)/[img4tool](https://github.com/tihmstar/img4tool)

- [xerub](https://github.com/xerub) for [img4lib](https://github.com/xerub/img4lib) and [restored_external](https://github.com/xerub/sshrd) in the ramdisk

- [libimobiledevice](https://github.com/libimobiledevice) for several tools used in this project (irecovery, ideviceenterrecovery etc), and [nikias](https://github.com/nikias) for keeping it up to date

- [Ralp0045](https://github.com/Ralph0045/Kernel64Patcher) amazing dtree_patcher and kernel64patcher ;)

- [mineek](https://github.com/mineek/sunst0rm) because the original idea.

</p>
</details>
