# EventBus-notes
[EventBus ProGuard](http://greenrobot.org/eventbus/documentation/proguard/)

```
-keepattributes *Annotation*
-keepclassmembers class * {
    @org.greenrobot.eventbus.Subscribe <methods>;
}
-keep enum org.greenrobot.eventbus.ThreadMode { *; }
 
# Only required if you use AsyncExecutor
-keepclassmembers class * extends org.greenrobot.eventbus.util.ThrowableFailureEvent {
    <init>(java.lang.Throwable);
}
```
除了上面的还有自己定义的各种 event 事件的实体类也需要排除混淆
```
-keep class 包名.youreventbean.**{*;}
```
