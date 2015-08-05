android_local_normandy
======================

Local Manifest for Cyanogenmod Lollipop 5.1.1 on Nokia X (normandy)

Getting Started
---------------

To get started with Android, you'll need to get
familiar with [Git and Repo](http://source.android.com/download/using-repo).

Make a build directory:

	mkdir Android (or whatever name you choose, which will be refered to as Android throughout)
	cd Android
	mkdir .repo/local_manifests

To initialize your local repository using the CM12.1 manifest, use commands like these:

    repo init -u git://github.com/CyanogenMod/android.git -b cm-12.1

    curl -L -o .repo/local_manifests/normandylp.xml -O -L https://raw.github.com/NormandyLP/local_manifests/master/normandylp.xml
 
    	( or Download: https://github.com/NormandyLP/local_manifests/blob/master/normandylp.xml
		and place it in ~/Android/.repo/local_manifest.xml

Then to sync up:

    repo sync

You will need to apply some pathces to fix build erros and other bugs:

    cd Android/device/nokia/normandy/patch
    ./apply.sh

To build issue commands like these:

    cd Android
    . build/envsetup.sh && lunch cm_normandy-userdebug
    brunch normandy
