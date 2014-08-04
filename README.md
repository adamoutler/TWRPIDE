
Overview
---------------
This project provides TWRP with an IDE.

Requires
Netbeans 8: https://netbeans.org/downloads/
AOSP Source Tree



Getting Started
---------------
First configure your build environment as you usually would, eg: 
     repo init -u git://github.com/adamoutler/android.git  -b android-4.4;repo sync;
     cd vendor;git clone https://github.com/DonkeyCoyote/proprietary_vendor_asus.git;cd proprietary_vendor_asus/;cp -R ./* ../asus/;cd ../../
     chmod +x ./build/envsetup.sh;source ./build/envsetup.sh shoot && lunch omni_grouper-eng;make -j5 recoveryimage


once you've built the image you are ready to clone the ide
    cd bootable
    git clone https://github.com/adamoutler/TWRPIDE.git


Project Config
---------------
You will need more memory that the default provided by netbeans.  Open /usr/local/netbeans-8.0/etc/netbeans.conf in your favorit editor, locate "netbeans\_default\_options" and replace the entire line of arguments with the one below 

    "-J-client -J-Xss64m -J-Xms512m -J-Xmx6g -J-Dapple.laf.useScreenMenuBar=true -J-Dapple.awt.graphics.UseQuartz=true -J-Dsun.java2d.noddraw=true -J-Dsun.java2d.dpiaware=true -J-Dsun.zip.disableMemoryMapping=true -J-XX:+UseConcMarkSweepGC -J-XX:+UseParNewGC -J-Dnetbeans.exception.report.min.level=99999"

Open Netbeans and then open the cloned project in bootable/IDE/TeamWinRecovery

If you find netbeans gives you popup errors, it is likely because of an invalid symlink and the reported file can be deleted. 

Thanks to Helicopter88 for putting together [this Manifest](https://raw.githubusercontent.com/helicopter88/recovery_manifest/android-4.4/README.md)

