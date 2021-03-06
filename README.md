Alert Dialog ![API](https://img.shields.io/badge/API-15%2B-brightgreen.svg?style=flat) [![Known Vulnerabilities](https://snyk.io/test/github/TutorialsAndroid/KAlertDialog/badge.svg?targetFile=library%2Fbuild.gradle)](https://snyk.io/test/github/TutorialsAndroid/KAlertDialog?targetFile=library%2Fbuild.gradle) [![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-KAlertDiaog-blue.svg?style=flat)](https://android-arsenal.com/details/1/7588)
===================
AlertDialog for Android, a beautiful and material alert dialog to use in your android app.

**Library available at JitPack.io**

[![](https://jitpack.io/v/TutorialsAndroid/KAlertDialog.svg)](https://jitpack.io/#TutorialsAndroid/KAlertDialog)

## Important

**Note this library was made in the making for `Kinda` app this library was copied from `sweet-alert-dialog` repository on github we made this library because we want to use own library on `Kinda` app.So this library is in development we will monthly
update this library with some changes.**

## ScreenShot
![](https://github.com/TutorialsAndroid/KAlertDialog/blob/master/art/device-2019-03-23-132617.png)

## Setup
The simplest way to use AlertDialog is to add the library as dependency to your build.

## Gradle

Add it in your root build.gradle at the end of repositories:

	allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}

Step 2. Add the dependency

	dependencies {
	        implementation 'com.github.TutorialsAndroid:KAlertDialog:v4.1'
	}

## Usage

**Show material progress**

    KAlertDialog pDialog = new KAlertDialog(this, KAlertDialog.PROGRESS_TYPE);
    pDialog.getProgressHelper().setBarColor(Color.parseColor("#A5DC86"));
    pDialog.setTitleText("Loading");
    pDialog.setCancelable(false);
    pDialog.show();


You can customize progress bar dynamically with materialish-progress methods via **KAlertDialog.getProgressHelper()**:
- resetCount()
- isSpinning()
- spin()
- stopSpinning()
- getProgress()
- setProgress(float progress)
- setInstantProgress(float progress)
- getCircleRadius()
- setCircleRadius(int circleRadius)
- getBarWidth()
- setBarWidth(int barWidth)
- getBarColor()
- setBarColor(int barColor)
- getRimWidth()
- setRimWidth(int rimWidth)
- getRimColor()
- setRimColor(int rimColor)
- getSpinSpeed()
- setSpinSpeed(float spinSpeed)

A basic message：

    new KAlertDialog(this)
        .setTitleText("Here's a message!")
        .show();

A title with a text under：

    new KAlertDialog(this)
        .setTitleText("Here's a message!")
        .setContentText("It's pretty, isn't it?")
        .show();

A error message：

    new KAlertDialog(this, KAlertDialog.ERROR_TYPE)
        .setTitleText("Oops...")
        .setContentText("Something went wrong!")
        .show();

A warning message：

    new KAlertDialog(this, KAlertDialog.WARNING_TYPE)
        .setTitleText("Are you sure?")
        .setContentText("Won't be able to recover this file!")
        .setConfirmText("Yes,delete it!")
        .show();

A success message：

    new KAlertDialog(this, KAlertDialog.SUCCESS_TYPE)
        .setTitleText("Good job!")
        .setContentText("You clicked the button!")
        .show();

A message with a custom icon：

    new KAlertDialog(this, KAlertDialog.CUSTOM_IMAGE_TYPE)
        .setTitleText("Sweet!")
        .setContentText("Here's a custom image.")
        .setCustomImage(R.drawable.custom_img)
        .show();

Bind the listener to confirm button：

    new KAlertDialog(this, KAlertDialog.WARNING_TYPE)
        .setTitleText("Are you sure?")
        .setContentText("Won't be able to recover this file!")
        .setConfirmText("Yes,delete it!")
        .setConfirmClickListener(new KAlertDialog.OnSweetClickListener() {
            @Override
            public void onClick(KAlertDialog sDialog) {
                sDialog.dismissWithAnimation();
            }
        })
        .show();

Show the cancel button and bind listener to it：

    new KAlertDialog(this, KAlertDialog.WARNING_TYPE)
        .setTitleText("Are you sure?")
        .setContentText("Won't be able to recover this file!")
        .setCancelText("No,cancel plx!")
        .setConfirmText("Yes,delete it!")
        .showCancelButton(true)
        .setCancelClickListener(new KAlertDialog.OnSweetClickListener() {
            @Override
            public void onClick(KAlertDialog sDialog) {
                sDialog.cancel();
            }
        })
        .show();

**Change** the dialog style upon confirming：

    new KAlertDialog(this, KAlertDialog.WARNING_TYPE)
        .setTitleText("Are you sure?")
        .setContentText("Won't be able to recover this file!")
        .setConfirmText("Yes,delete it!")
        .setConfirmClickListener(new KAlertDialog.OnSweetClickListener() {
            @Override
            public void onClick(KAlertDialog sDialog) {
                sDialog
                    .setTitleText("Deleted!")
                    .setContentText("Your imaginary file has been deleted!")
                    .setConfirmText("OK")
                    .setConfirmClickListener(null)
                    .changeAlertType(KAlertDialog.SUCCESS_TYPE);
            }
        })
        .show();
        
 ## License

* [Apache Version 2.0](http://www.apache.org/licenses/LICENSE-2.0.html)

```
Copyright 2019 KAlertDialog

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

 http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
       
