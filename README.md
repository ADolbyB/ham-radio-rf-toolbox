# Ham Radio RF Toolbox

This project started many years ago with an old Pentium III 500Mhz Panasonic CF-27 Laptop that I salvaged from FleaBay junk I procured on the cheap. I had it dual-booting MS-DOS 6.22 and Windows XP SP3.

As a new ham at the time, I was interested in having a way to flash my own surplus radios that my friends and I all had laying around. We had a bunch of old Mother /&#92;/&#92; Motorola VHF & UHF Genesis Handhelds, Jedi VHF & UHF Handhelds, MaxTracs, M1225s, and Analog Spectras.

We also had a bunch of old Kenwood Radios laying around: TK-730 mobile radios, TK-280/380 handhelds & TK-780/880 mobiles, TK-290/390 handhelds, TK-190 low band handhelds and TK-6110 low band mobiles.

Later on we acquired nicer radios like /&#92;/&#92; Astro & Astro25 stuff (XTS/XTLs), and Kenwood NX series stuff.

The old laptop worked great. Until it didn't. Which I expected. Which brings us here.

I (and a bunch of my friends) still have a bunch of radios laying around that work and we can't program them.

This project should solve that problem for awhile...

I have `3 Requirements` for this project to be considered a success:
1. Use only currently supported Operating Systems.
2. Execute Read/Write operations on real hardware without using a Virtual Machine or Emulators.
3. Use only currently supported hardware.

## Project Stages:

- Stage 1: Create Test dual-boot image using FreeDOS on partition 1, and Linux Mint 22.2 on partition 2.
     - I would have used Ubuntu 24.04, but the image is much larger.
     - Test cloning, compression, and restoring the partitions after some basic installs using the `install.sh` script.
     - This fulfills `Requirement 1`: Using only currently supported Operating Systems.

- Stage 2: Test with working prototype hardware
     - Here I will restore the image, manually add some software, and check read/write to multiple radios.
     - My prototype test setup is all spare parts: A Dell Latitude E6430 i5 with a port replicator with a real serial port.
     - This fulfills `Requirement 2`: Executing Read/Write operations on real hardware without using a Virtual Machine or Emulators, which cause unreliability due to serial passthroughs.

- Stage 3: Deploy on production model hardware
     - Find some cheap, new hardware such as this [Beelink MINI S12 Pro](https://www.amazon.com/Beelink-Computers-1000Mbps-Displays-Support/dp/B09J4D6TMG/)
     - Add a hardware DE9 Serial Port via one of the NVMe bays (there are 2).
     - This requires the following:
        - 1x [PCIe Riser](https://www.amazon.com/NGFF-Express-Riser-Speed-Cable/dp/B07KSZ62B8/) AND
        - 1x [PCIe to RS232 DB9 Card](https://www.amazon.com/StarTech-com-Interface-Standard-Retention-11050-PC-SERIAL-CARD/dp/B09YVMDCWM/)
     - I will pull the software from publicly available archives so we don't have to re-host the same software again (and side-step the proprietary software issues).
     - Why not a Raspberry Pi?
         - Short answer: Wrong processor architecture. This is what causes problems.
     - This fulfills `Requirement 3`: Using only currently supported hardware.

## Archives To Pull From:

- [Archive 1](https://pauhh.planet.ee/programmid/) - Mostly old MS-DOS software for `/\/\` and `Kenwood` 2way.
- [Archive 2](https://wiki.w9cr.net/index.php/EF_Johnson) - `EFJohnson` 2way Software for Windows.
- [Archive 3](https://wiki.w9cr.net/index.php/Astro_Saber/XTS3000) - `/\/\` Astro XTS3000 CPS for Windows.
- [Archive 4](https://wiki.w9cr.net/index.php/Astro_Firmware_Upgrades) - `/\/\` Astro XTS3000 Depot for Windows.
- [Archive 5](https://wiki.w9cr.net/index.php/Astro_Spectra) - `/\/\` Astro Spectra & AS Depot for Windows.
- [Archive 6](https://archive.org/download/astro25portablecpsr20.01.00) - `/\/\` Astro25 Portable Software.

### Other Useful Ham Tools [FW updates, etc.]:

- [`hugen79`](https://github.com/hugen79/) &quot;stock&quot; : [FW Version](https://github.com/hugen79/NanoVNA-H/releases)
- [`DiSlord`](https://github.com/DiSlord) &quot;enhanced&quot; : [FW Version](https://github.com/DiSlord/NanoVNA-D/releases)

- [tinySA Home](https://tinysa.org/wiki/pmwiki.php?n=Main.HomePage)
- [TinySA Version Comparison Table](https://www.tinysa.org/wiki/pmwiki.php?n=TinySA4.Comparison).
     - [FW Version](http://athome.kaashoek.com/tinySA/DFU/) for tinySA Basic.
     - [FW Version](http://athome.kaashoek.com/tinySA4/DFU/) for `tinysa4` : tinySA Ultra ZS405, Ultra+ ZS406 &amp; tinySA Ultra+ ZS407.

[//]: # ([tinySASaver]() by Erik)

#### Disclaimer:

Any software I link to here is located somewhere in the public domain. It is not my software, and in fact it has been there for YEARS. I DID NOT put it there. So if you have a problem, you may want to address those who put it there.