
# รัน flutter แล้วเจอ #import error <Flutter/Flutter.h>
 ![Image of Yaktocat](images/03.jpg)
 ปกติผมกดรันเลยครับ เวลากด save  ui จะอัพเดตทันที แต่มีํธีนี้ผมใช่ได้ไม่ได้ครับ ผมรันไม่ผ่าน ไม่รู้ว่าเกิดจากสาเหตุอะไร เลยมาถามหารู้ว่าจะแก้ปัญหานี้ยังไง
<details>
  <summary>กดรันแล้วผลลัพธิ์ที่ออกมา</summary>



```
Launching lib/main.dart on iPhone in debug mode...
Automatically signing iOS for device deployment using specified development team in Xcode project: MJN9RHXR9J
Running pod install...
Running Xcode build...
Xcode build done.                                            8.0s
Failed to build iOS app
Error output from Xcode build:
↳
    ** BUILD FAILED **


Xcode's output:
↳
    In file included from /usr/local/Caskroom/flutter/1.22.4/flutter/.pub-cache/hosted/pub.dartlang.org/sqflite-1.3.2+1/ios/Classes/SqfliteOperation.m:9:
    In file included from /usr/local/Caskroom/flutter/1.22.4/flutter/.pub-cache/hosted/pub.dartlang.org/sqflite-1.3.2+1/ios/Classes/SqfliteOperation.h:7:
    /usr/local/Caskroom/flutter/1.22.4/flutter/.pub-cache/hosted/pub.dartlang.org/sqflite-1.3.2+1/ios/Classes/SqflitePlugin.h:2:9: fatal error: 'Flutter/Flutter.h' file not found
    #import <Flutter/Flutter.h>
            ^~~~~~~~~~~~~~~~~~~
    1 error generated.
    note: Using new build system
    note: Building targets in parallel
    note: Planning build
    note: Constructing build description
    warning: The iOS deployment target 'IPHONEOS_DEPLOYMENT_TARGET' is set to 8.0, but the range of supported deployment target versions is 9.0 to 14.3.99. (in target 'FMDB' from project 'Pods')
    warning: The iOS deployment target 'IPHONEOS_DEPLOYMENT_TARGET' is set to 8.0, but the range of supported deployment target versions is 9.0 to 14.3.99. (in target 'Flutter' from project 'Pods')

Could not build the precompiled application for the device.

It appears that your application still contains the default signing identifier.
Try replacing 'com.example' with your signing id in Xcode:
  open ios/Runner.xcworkspace

Error launching application on iPhone.

```


</details>

## วิธีที่ทำให้ผมทำงานต่อไปได้
 <details>
  <summary>อีกวิธีนึงที่ทำให้รันได้</summary>

1. เปิด `terminal` บนโปรเจคขึ้นมา
2. ใช้คำสั่ง `flutter run` 
   
วิธีนี้จะช่วยให้ผมทำงานต่อไปได้ แต่จะไม่สะดวก ตอนที่เราอยากจะเห็นผลงานเวลาโค๊ดเสร็จแล้ว 
จะต้องมากด `r` เพื่อ รีเฟรชหน้า หรือ `R` เพื่อรีตาร์ท ผมชอบเขียนแต่ละส่วนเสร็จแล้ว กด `save`จะเห็นผลทันที แต่แบบนี้ กด `save`แล้วมาใช้คำสั่ง `r`อีก มันไม่สะดวกครับผม
```
cpe@thvsdis-MacBook-Pro relationship_app % flutter run
Launching lib/main.dart on iPhone in debug mode...
Automatically signing iOS for device deployment using specified development team in Xcode project: MJN9RHXR9J
Running pod install...                                           2,030ms
Running Xcode build...                                                  
 └─Compiling, linking and signing...                        11.2s
Xcode build done.                                           38.3s
Installing and launching...                                        28.2s
Syncing files to device iPhone...                                  321ms

Flutter run key commands.
r Hot reload. 🔥🔥🔥
R Hot restart.
h Repeat this help message.
d Detach (terminate "flutter run" but leave application running).
c Clear the screen
q Quit (terminate the application on the device).
An Observatory debugger and profiler on iPhone is available at: http://127.0.0.1:53542/XwP3UdFrfeU=/

Running with unsound null safety
For more information see https://dart.dev/null-safety/unsound-null-safety


```
</details>
<details>
<summary>วิธีที่ผมลองแก้ไขปัญหานี้</summary>
ก่อนที่ผมจะเริ่มโพสต์นี้ ผมหาวิธีมาบ้างแล้วในแต่ละที่ที่ผมลองทำตาม

[วิธีแรก](https://stackoverflow.com/questions/64973346/error-flutter-flutter-h-file-not-found-when-flutter-run-on-ios-mobile) ผมได้ลองทำตามแล้ว ของเมนท์แรก 
```
1.cd ios
2.pod install
3.cd ..
4.flutter run
```
ได้ผลลัพธิ์ออกมาเหมือนเดิมครับ

แต่.....
ล่าสุดในตอนที่ผมเขียนอยู่ ผมได้ลอง เมนท์ที่สองดูครับ
```
1.Remove ios/Flutter/Flutter.podspec: rm ios/Flutter/Flutter.podspec
2.flutter clean
3.Run your app again.
```
ผลลัพธิ์คือ รันได้แล้วครับผม
</details>
