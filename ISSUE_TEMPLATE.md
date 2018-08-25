Make sure you have provided the following information:

 - [X] link to your code branch cloned from rhboot/shim-review in the form user/repo@tag
 
drivelock/shim_review@drivelock-shim-arch-20180825
 - [X] completed README.md file with the necessary information
 
See drivelock/shim_review@drivelock-shim-arch-20180825
 - [X] shim.efi to be signed
 
See drivelock/shim_review@drivelock-shim-arch-20180825 (bootX64.efi)
 - [X] public portion of your certificate embedded in shim (the file passed to VENDOR_CERT_FILE)
 
See drivelock/uefiloader/blob/master/shimlib/shim_cert_DL.h
 - [X] any extra patches to shim via your own git tree or as files
 
See drivelock/uefiloader@drivelock-shim-arch-20180825
 - [X] any extra patches to grub via your own git tree or as files
 
None
 - [X] build logs
 
See drivelock/shim_review@drivelock-shim-arch-20180825 (build.log)

###### What organization or people are asking to have this signed:
DriveLock SE (https://www.drivelock.com)

###### Version of shim:
https://github.com/rhboot/shim/tree/0.8

###### Sysdev Submission ID:
14022676906032392
Microsoft asked us to get approval from the shim review board before proceeding

###### What product or service is this for:
DriveLock Full Disk Encryption

###### What's the justification that this really does need to be signed for the whole world to be able to boot it:
DriveLock Disk Protection is a full disk encryption product with pre-boot authentication used on thousands of computers. 
The loader is used to load and start our native UEFI based pre-boot authentication.
It's essential to be able to provide software that works with every machine that has Secure Boot enabled.

