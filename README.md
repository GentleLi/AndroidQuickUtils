## QuickUtils


<!--
<div style="float: left"><img src="http://cesarferreira.com/wp-content/uploads/2012/07/dribbble.png"  
style="width:200px" /></div>  
-->
<div style="float: left"><img src="https://dl.dropbox.com/u/86831/cesarferreira/nexus_header2.jpg" /></div>  
This repository offers a set of random useful classes to deal with repetitive tasks in the Android Framework.
Intended to help you getting your Android applications off the ground quickly, by offering ready-to-use components and utility classes that wrap a lot of the boilerplate that's involved when writing Android apps.


## Changelog

### 0.2 <sub><sup>`2012/08/02`</sup></sub>
- Checks if the app has connectivity to the Internet
- `getCurrentTime()` is now divided into `getCurrentTimeInSeconds()` and `getCurrentTimeInMilliseconds()`
- public static long getCurrentTimeInSeconds()
- `sleep` method now accepts milliseconds instead of seconds
- `log` now has a warning method
- Updated SDK version to 4.0.3
- Added `math` category
- Get a random number between a given range
- Check if a number is odd

### 0.1 <sub><sup>`2012/07/10`</sup></sub>
- Added `log` category
- Added error log method
- Added information log method
- Added verbose log method
- Added debug log method
- Added `sdcard` category
- Added isSDCardAvailable method
- Added isSDCardWritable method
- Added `misc` category
- Added vibrate method
- Added sleep method
- Added toast method with custom lenght time
- Added get current time in miliseconds method



-----




## Usage
Really simple usage, you just need to specify the category and the method you want to use.

```java
QuickUtils.__category__.__method__
```
-------------------

## LOG <sub><sup>`category`</sup></sub>

With this methods you don't need to set the TAG variable in every class of your project and you can disable the logs everywhere without deleting/commenting the log lines by setting the debug mode to PRODUCTION (explained in the previous section).

```java
QuickUtils.log.__method__
```


### Error Log 

```java
QuickUtils.log.e("error description");
```

### Verbose Log 

```java
QuickUtils.log.v("verbose description");
```

### Information Log 

```java
QuickUtils.log.i("information description");
```

### Warning Log 

```java
QuickUtils.log.w("warning description");
```

### Debug Log 

```java
QuickUtils.log.d("debug description");
```

### Debug Log `throwable`

```java
QuickUtils.log.d("debug description", Throwable t);
```

------------

## MISC <sub><sup>`category`</sup></sub>

With this methods you don't need to set....

```java
QuickUtils.misc.__method__
```


### Checks if the app has connectivity to the Internet `boolean`
True if has connection to the Internet and false if it doesn't.

```java
QuickUtils.misc.hasInternetConnection(Context context);
```


### Get the current time in milliseconds `long`

```java
QuickUtils.misc.getCurrentTimeInMiliseconds();
```

### Get the current time in seconds `long`

```java
QuickUtils.misc.getCurrentTimeInSeconds();
```

### Sleep `void`
Causes the thread which sent this message to sleep for the given interval of time (given in milliseconds). The precision is not guaranteed - the Thread may sleep more or less than requested.


```java
QuickUtils.misc.sleep(durationInMilliseconds);
```

### Toast method with short duration `void`

```java
QuickUtils.misc.toast(context, "This is a short toast");
```

### Toast with non specified duration `void`
Either `Toast.LENGTH_SHORT` or `Toast.LENGTH_LONG`

```java
QuickUtils.misc.toast(context, "This is a short toast", Toast.LENGTH_LONG);
```
------------

## MATH <sub><sup>`category`</sup></sub>

Math Utils.

```java
QuickUtils.math.__method__
```

### Returns a random number between MIN inclusive and MAX exclusive. `int`
A random int between MIN inclusive and MAX exclusive.

```java
QuickUtils.sdcard.getRandomNumber(int min, int max);
```

### Check if a number is Odd. `boolean`
True if the num is odd and false if it's even

```java
QuickUtils.sdcard.isOdd(int num);
```



------------

## SDCARD <sub><sup>`category`</sup></sub>

SDCard Utils.

```java
QuickUtils.sdcard.__method__
```

### Check if the SD Card is Available `boolean`
True if the sd card is available and false if it is not

```java
QuickUtils.sdcard.isSDCardAvailable();
```

### Check if the SD Card is Writable `boolean`
True if the sd card is writable and false if it is not

```java
QuickUtils.sdcard.isSDCardWritable();
```

## Example


```java
@Override
 public void onCreate(Bundle savedInstanceState) {
		super.onCreate(savedInstanceState);
		setContentView(R.layout.activity_main);

		// SET ENVIRONMENT
		QuickUtils.setDebugMode(QuickUtils.DEVELOPER_MODE); // can be omited

		try {
			QuickUtils.log.w("This is dangerous code");

			// do DANGEROUS STUFF
			// ...
			// ...

			QuickUtils.misc.toast(this,
					"The result of your dangerous calculations is: " + number);

		} catch (Exception exception) {
			QuickUtils.log.d("Exception thrown", exception);
		}

		// Check if you can write on your sdcard
		if (QuickUtils.sdcard.isSDCardAvailable()
				&& QuickUtils.sdcard.isSDCardWritable()) {

			// you can write safely on your sdcard
			// ...
			// ...
		}

	}
```

## Downloads
All the versions can be found [here](https://github.com/cesarferreira/AndroidQuickUtils/tags)


## Instalation
As simple as going to your project's properties and include the `QuickUtils.jar` library or add the QuickUtils project as a library as shown below.

 ![](https://dl.dropbox.com/u/86831/cesarferreira/goanswer.png)


## Setting up the environment
Set the default TAG for logcat debug purposes

```java
QuickUtils.setTAG("DESIRED_TAG");
```


### Debug mode

To enable the log outputs (This is the default behavior of the library so you don't need to set this up).

```java
QuickUtils.setDebugMode(QuickUtils.DEVELOPER_MODE);
```

When the application is ready to go and you want to disable the log outputs.

```java
QuickUtils.setDebugMode(QuickUtils.PRODUCTION_MODE);
```

AndroidManifest.xml
-------------------

If you intend to use the vibration util don't forget to add the vibration permission, if you haven't already, in your `<manifest>`:

```xml
<uses-permission android:name="android.permission.VIBRATE" />   
```

If you intend to use the `hasConnectivity` method don't forget to add the network state access permission, if you haven't already, in your `<manifest>`:

```xml
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```


Import
------
```java
import com.cesar.android;
```


## Contributing

Want to contribute? Great! 

1. Fork it.
2. Create a branch (`git checkout -b my_branch`)
3. Commit your changes (`git commit -am "Added changes"`)
4. Push to the branch (`git push origin my_branch`)
5. Create an [Issue](https://github.com/cesarferreira/AndroidQuickUtils/issues) with a link to your branch
6. Enjoy a refreshing Diet Coke and wait


## License
Apache License, Version 2.0 (http://www.apache.org/licenses/LICENSE-2.0.html)

## Authors
 * César Ferreira (cesar.manuel.ferreira@gmail.com)
