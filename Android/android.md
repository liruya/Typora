Android

矢量图
<build.gradle>
defaultConfig {
        ......
        vectorDrawables.useSupportLibrary = true
}
<Activity>
static {
        AppCompatDelegate.setCompatVectorFromResourcesEnabled( true );
}

平台版本					API 级别		VERSION_CODE					备注
Android 7.0					24			N	
Android 6.0					23			M	
Android 5.1					22			LOLLIPOP_MR1	
Android 5.0					21			LOLLIPOP
Android 4.4W				20			KITKAT_WATCH					仅限Wearables
Android 4.4					19			KITKAT	
Android 4.3					18			JELLY_BEAN_MR2	
Android 4.2、4.2.2			17			JELLY_BEAN_MR1	
Android 4.1、4.1.1			16			JELLY_BEAN	
Android 4.0.3、4.0.4			15			ICE_CREAM_SANDWICH_MR1	
Android 4.0、4.0.1、4.0.2		14			ICE_CREAM_SANDWICH
Android 3.2					13			HONEYCOMB_MR2	
Android 3.1.x				12			HONEYCOMB_MR1	
Android 3.0.x				11			HONEYCOMB	
Android 2.3.4
Android 2.3.3				10			GINGERBREAD_MR1	
Android 2.3.2
Android 2.3.1
Android 2.3					9			GINGERBREAD
Android 2.2.x				8			FROYO	
Android 2.1.x				7			ECLAIR_MR1	
Android 2.0.1				6			ECLAIR_0_1
Android 2.0					5			ECLAIR
Android 1.6					4			DONUT	
Android 1.5					3			CUPCAKE	
Android 1.1					2			BASE_1_1	
Android 1.0					1			BASE	


APP字体不随系统字体变化，在BaseActivity中重写getResources方法
  

```java
@Override
public void onConfigurationChanged ( Configuration newConfig )
{
    super.onConfigurationChanged( newConfig );
}

@Override
public Resources getResources() {
    Resources res = super.getResources();
    if (res != null) {
        Configuration config = res.getConfiguration();
        if (config != null && config.fontScale != 1) {
            config.fontScale = 1;
        }
    }
    return res;
}
```

Android 8/9 wifiInfo.getSSID 返回 <unkown ssid>
需要 <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION"/>
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>

fragment点击穿透 在layout跟节点设置clickable=true

android 添加assets
src/main/下添加assets文件夹
多语言时 在string文件中定义路径
file:///android_asset/path/filename

ldpi:1dp=0.75px mdpi:1dp=1px hdpi:1dp=1.5px xhdpi:1dp=2px xxhdpi:1dp=3px xxxhdpi:1dp=4px

