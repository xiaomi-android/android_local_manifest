
Local manifest addon for building AOSP Jellybean 4.3 for Xiaomi MI2

Getting Started
---------------

Make a build directory:

	mkdir android (or whatever name you choose)
	cd android (or the name  you chose)
	
Initialize your local repository:

    repo init -u https://android.googlesource.com/platform/manifest -b android-4.3_r3.1
    curl --create-dirs -L -o .repo/local_manifests/manifest_xiaomi_aries.xml -O -L https://raw.github.com/xiaomi-android/android_local_manifest/android-4.3/manifest_xiaomi_aries.xml

Sync:

    repo sync

Setup the build environment:

    . build/envsetup.sh

Select a device to build using "lunch" like this: lunch full_<device>-userdebug

    lunch full_aries-userdebug

And start the build (-j# is set the # of virtual cores you have in your build box.  examples: -j8, -j32, etc):

    make -j8 otapackage

Look for the flashable .zip in: out/target/product/<device>

