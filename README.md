# Appium
Appium-selenium 3.0 API for Mobile Automation Testing

![appium](https://user-images.githubusercontent.com/24494133/42090141-d006b1c2-7bbd-11e8-9647-b751c9f7c986.png)

### LATEST VERSION
Android 13 - tiramisu August 15, 2022 </br>
Android 12 -Snow cone 11 -October 4, 2021 </br>
Android 11- red velvet cake September 8, 2020 </br>
Android 10 10 - quince tart sept 3 2019  api level29 </br>
Android 9 pie  august 6 2018 </br>

appium java client 8.2.0 - Aug 30, 2022 </br>
selenium-4.4.0 </br>
appium gui desktop-1.22 </br>
Xcode -14 </br>
latest version of iOS - iOS 15.5 </br>
latest mac Version macOS 13: Ventura  – June 6, 2022  </br>
latest mac Version macOS 12: Monterey (Star) – October 25, 2021 (Latest: 12.4) </br>

.ipa -ios file extension </br>
# crash logs
settings-privacy-analytics and improvements-analyticsdata- filenam.ips
# ADB Commands
1)adb devices

2)adb shell

dumpsys window windows | grep -E 'CurrentFocus'

3)adb tcpip 5555

4)adb connect 192.168.0.101
(*ip of wifi of mobile) 

5)adb logcat>/Eclipse/logcat.txt 

6)adb logcat --buffer=crash </br>
7)adb logcat AndroidRuntime:E *:S </br>
8)adb install -r TheAppName.apk

--------------------------------------------

emulator -avd kitkat



--------------------------------------------



adb install "D:\software\testing software\MOBILE TESTING\APKS\HTML5testWebView.apk"

chrome://inspect/#devices

# AndroidStudio emulator
![avd settings](https://user-images.githubusercontent.com/24494133/42304144-68bd9b46-8042-11e8-99a6-5cd42b342882.PNG)
# Appium Architecture
![appiumarchitecture](https://user-images.githubusercontent.com/24494133/43879019-8efea5be-9bbf-11e8-9264-dcef7e7fab1e.png)

### Locators
-ios predicate string </br>
-ios class chain </br>
```
let elem = app.cells.matchingPredicate(NSPredicate(format: "label CONTAINS 'Olivia'"))
elem.click();
HashMap<String, String> scrollObject = new HashMap<String, String>();
scrollObject.put("predicateString", "label == 'ADD TO CART'");

driver.findElement(MobileBy.iOSClassChain(selector));

```
AccessibilityId- content-desc </br>
AndroidUIAutomator -text </br>
driver.findElementByAndroidUIAutomator("new UiSelector().text(\"i accept adds\")").click() </br>
ClassName -class </br>
CssSelector </br>
Id- ResourceId  </br>
LinkText </br>
Name -text</br>
PartialLinkText </br>
TagName </br>
XPath- driver.findElementByXPath("//ClassName[@content-desc='content-desc']").click() </br>
 driver.findElementByXPath("//ClassName[@index='1']").click()
```
public void iOSScrollToElement() {
		  RemoteWebElement element = (RemoteWebElement)driver.findElement(By.name("test-ADD TO CART"));
		  String elementID = element.getId();
		  HashMap<String, String> scrollObject = new HashMap<String, String>();
		  scrollObject.put("element", elementID);
//		  scrollObject.put("direction", "down");
//		  scrollObject.put("predicateString", "label == 'ADD TO CART'");
//		  scrollObject.put("name", "test-ADD TO CART");
		  scrollObject.put("toVisible", "sdfnjksdnfkld");
		  driver.executeScript("mobile:scroll", scrollObject);
	  }
``` 
### Android ScrollAnd Swipe
``` 
   public static void androidScroll1() {
		Dimension dim = driver.manage().window().getSize();
		int x = dim.getWidth() / 2;
		int startY = (int) (dim.getHeight() * 0.2);
		int endY = (int) (dim.getHeight() * 0.8);
		//downward scroll
		TouchAction t = new TouchAction(driver);
		t.press(PointOption.point(x, startY)).moveTo(PointOption.point(x, endY)).release().perform();
}
-----------------------------------------------------------
public static void scrollUsingText(String visibleText) {
		((FindsByAndroidUIAutomator<MobileElement>) driver).findElementByAndroidUIAutomator(
				"new UiScrollable(new UiSelector().scrollable(true).instance(0)).scrollIntoView(new UiSelector().textContains(\""
						+ visibleText + "\").instance(0))");
	}

	}
```
Switch apps
```
 driver.startActivity(new Activity(settingsAppPackageName, settingsAppActivityName));
```
