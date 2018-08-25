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

###### What product or service is this for:
DriveLock Disk Protection (a full disk encryption with pre-boot authentication)

###### What is the origin and full version number of your shim?
https://github.com/rhboot/shim/tree/0.8

###### What's the justification that this really does need to be signed for the whole world to be able to boot it:
DriveLock Disk Protection is a full disk encryption product with pre-boot authentication used on thousands of computers. 
The loader is used to load and start our native UEFI based pre-boot authentication.
It's essential to be able to provide software that works with every machine that has Secure Boot enabled.

###### How do you manage and protect the keys used in your SHIM?
Only public keys are in the SHIM as it verifies signatures of loaded components.

###### Do you use EV certificates as embedded certificates in the SHIM?
Yes

###### What is the origin and full version number of your bootloader (GRUB or other)?
Windows is booted (so no Linux bootloader is used)

###### If your SHIM launchers any other components, please provide further details on what is launched
SHIM launches Pre-boot authentication components (native EFI application and EFI drivers for smart card and keyboard)

###### How do the launched components prevent execution of unauthenticated code?
SHIM verifies digital signatures of launched components and can only launch components signed with the embedded certificate.

###### Does your SHIM load any loaders that support loading unsigned kernels (e.g. GRUB)?
No

###### What kernel are you using? Which patches does it includes to enforce Secure Boot?
Windows 7, 8, 10

###### What changes were made since your SHIM was last signed?
Previous version was signed by Microsoft. We changed the certificate used due to change of the company name.

###### What is the hash of your final SHIM binary?
dfa7a11aedca5bc092241aa6d9f5d83dda2097da86f2ed7140e4c8a910f7d7e8 (SHA256)
