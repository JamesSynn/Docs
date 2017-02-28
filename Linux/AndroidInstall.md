


# Android Install 

on Fedora
OpenCV Setting

## Environment

### Reference

Fedora 22 64bit
jdk-8u51-linux-x64
OpenCV-3.1.0-android-sdk
Android Studio 2.1

Openssl 1.0.0

### Latest

Fedora 25 64bit
jdk-8u121-linux-x64
OpenCV-3.2.0-android-sdk
Android Studio 2.3

Openssl 1.0.2


준비중...
curl -L https://raw.githubusercontent.com/jamessynn/androidinstall


## OpenCV Setting

- New Project

- import Module

- ~/opencv/sdk/java

- build.gradle(module:opencv) version change

- gradle synce

- Project > Open Module Settings > Depedencies > add > Module > OK

- Project > New > Folder > JNI Folder > Change Folder

- src/main/jniLibs/ > Finish

- cd ~/opecv-android-sdk/sdk/native/libs

- copy armeabi-v7a, x86-64

- app > paste > ~/app/src/jniLibs > OK > OK

- delete except -v7a/-java3.so, x86-64/-java3.so

- Main Activity.java > 

	private static final String TAG = "MainActivity";
	
	Static{
		if(!OpenCVLoader.initDebug()){
			Log.d(TAG, "OpenCV not Loaded");
		}else{
			Log.d(TAG, "OpenCV Loaded");			
		}
	}

- gradle.properties > android.useDeprecatedNdk = true

- run
