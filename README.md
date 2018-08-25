This repo is for review of requests for signing shim.  To create a request for review:

+ clone this repo
+ edit the template below
+ add the shim.efi to be signed
+ add build logs
+ commit all of that
+ tag it with a tag of the form "myorg-shim-arch-YYYYMMDD"
+ push that to github
+ file an issue at https://github.com/rhboot/shim-review/issues with a link to your tag

-------------------------------------------------------------------------------
What organization or people are asking to have this signed:
-------------------------------------------------------------------------------
DriveLock SE (https://www.drivelock.com)

-------------------------------------------------------------------------------
What product or service is this for:
-------------------------------------------------------------------------------
DriveLock Disk Protection (a full disk encryption with pre-boot authentication)

-------------------------------------------------------------------------------
What's the justification that this really does need to be signed for the whole world to be able to boot it:
-------------------------------------------------------------------------------
DriveLock Disk Protection is a full disk encryption product with pre-boot authentication used on thousands of computers. 
The loader is used to load and start our native UEFI based pre-boot authentication.
It's essential to be able to provide software that works with every machine that has Secure Boot enabled.

-------------------------------------------------------------------------------
Who is the primary contact for security updates, etc.
-------------------------------------------------------------------------------
- Name: Udo Riedel
- Position: CTO
- Email address: udo.riedel@drivelock.com
- PGP key, signed by the other security contacts, and preferably also with signatures that are reasonably well known in the linux community:
PGP key in file: UdoRiedel.asc
Signature (signed by Thomas Reichert - secondary contact) in file: UdoRiedel.asc.sig
Signature (signed by Stefani Seibold [stefani-at-seibold.net]) in file: UdoRiedel.StefaniSeibold.sig


-------------------------------------------------------------------------------
Who is the secondary contact for security updates, etc.
-------------------------------------------------------------------------------
- Name: Thomas Reichert
- Position: VP Product Management Encryption
- Email address: thomas.reichert@drivelock.com
- PGP key, signed by the other security contacts, and preferably also with signatures that are reasonably well known in the linux community:
PGP key in file: ThomasReichert.asc
Signature (signed by Udo Riedel - primary contact) in file: ThomasReichert.asc.sig
Signature (signed by Stefani Seibold [stefani-at-seibold.net]) in file: ThomasReichert.StefaniSeibold.sig

-------------------------------------------------------------------------------
What upstream shim tag is this starting from:
-------------------------------------------------------------------------------
https://github.com/rhboot/shim/tree/0.8

-------------------------------------------------------------------------------
URL for a repo that contains the exact code which was built to get this binary:
-------------------------------------------------------------------------------
https://github.com/drivelock/uefiloader

-------------------------------------------------------------------------------
What patches are being applied and why:
-------------------------------------------------------------------------------
* We build with UDK instead of GnuEfi (as our whole project uses UDK)
* We removed the code copied from UDK
* We removed unused code

-------------------------------------------------------------------------------
What OS and toolchain must we use to reproduce this build?  Include where to find it, etc.  We're going to try to reproduce your build as close as possible to verify that it's really a build of the source tree you tell us it is, so these need to be fairly thorough. At the very least include the specific versions of gcc, binutils, and gnu-efi which were used, and where to find those binaries.
-------------------------------------------------------------------------------
See https://github.com/drivelock/uefiloader/blob/master/Readme.txt

-------------------------------------------------------------------------------
Which files in this repo are the logs for your build?   This should include logs for creating the buildroots, applying patches, doing the build, creating the archives, etc.
-------------------------------------------------------------------------------
https://github.com/drivelock/uefiloader/blob/master/bin/build.log

-------------------------------------------------------------------------------
Add any additional information you think we may need to validate this shim
-------------------------------------------------------------------------------
After pre-boot authentication Windows is booted (so Windows bootloader is used).
We are able to boot Windows 7, 8, 10 (all versions supported by Microsoft).

