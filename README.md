# Android
工作学习总结

1、利用xml实现点击切换图片效果ImageView
  <ImageView android:background="@drawable/***.xml" *android:clickable="true"(点击效果这个必须添加，否则点击事件不生效) />
  在drawable下新建xml文件,右键drawable→New→Drawable Resource File
  xml文件配置如下：
  <?xml version="1.0" encoding="utf-8"?>
  <selector xmlns:android="http://schemas.android.com/apk/res/android">
    <!-- 定义按钮按下时的图片 -->
    <item android:state_pressed="true" android:drawable = "@drawable/filemanage_public_new_focus"/>
    <!-- 定义按钮默认的图片 -->
    <item android:drawable = "@drawable/filemanage_public_new" />
  </selector>
  
2、设置TextView隐藏
  xml: android:visibility="gone"(隐藏且不保留空间) 还要与之关联Java show_time.setVisibility(View.GONE);

3、Android Studio误删文件的话怎么恢复
  右键主文件夹→选择local history→show history→找到你想恢复的点击左上角resevert

4、TextClock时间控件必须成对使用，例：<TextClock></TextClock> 
  每秒刷新可参考 https://blog.csdn.net/qq_36771930/article/details/107381884?utm_medium=distribute.pc_relevant.none-task-blog-OPENSEARCH-4.control&depth_1-utm_source=distribute.pc_relevant.none-task-blog-OPENSEARCH-4.control
  手机为12小时制的使用以下两句强行将格式转为24小时制 android:format12Hour="HH:mm"  android:format24Hour="HH:mm"

5、Button按钮背景颜色为默认蓝紫色且设置颜色无效，修改themes.xml下的parent="Theme.MaterialComponents.DayNight.DarkActionBar"改为parent="Theme.MaterialComponents.DayNight.DarkActionBar.Bridge"

6、使用layout_columnWeight必须所有行都设置此属性，否则空间会回到（0,0）

7、图片资源存储不当的话，会引起应用运行直接停止

8、Plugin Error: Plugin "Android WiFi ADB" is incompatible (supported only in IntelliJ IDEA). 解决方法：在 C:\Users\Administrator\AppData\Roaming\Google\AndroidStudio4.1\plugins 下找到对应插件删除即可

9、解决AS使用切换到其他窗口再切换回来光标位置跑到本行最前边的情况：File → Setting → Editor → Virtual Space(After the end of line√)

10、*悬浮窗权限问题 ①首先确定是否在AndroidManifest添加权限<uses-permission android:name="android.permission.SYSTEM_ALERT_WINDOW" /> ②build.gradle(Module):targetSdkVersion改为22

11、Android Studio4.1.2 ButterKnife插件使用问题plugins下载Android-ButterKnife-Injections.jar，用户\AppData\Roaming\Google\AndroidStudio4.1\plugins下面的ButterKnife移到你AS安装路径下如：D:\Android\androidstudio\plugins

12、*查看反编译文件的数值可对应R文件进行查找

13、AS报错：Attempt to invoke virtual method 'void android.widget.ImageView.setImageResource(int)' on a null object reference

出现此种错误一般由两个原因组成：①控件ID没对应例如

View view = LayoutInflater.from((Context) SpotlightActivity.this.getApplication()).inflate(R.layout.activity_background_popup, null);
                
                iv_black = (ImageView) view.findViewById(R.id.iv_black);
                iv_red = (ImageView) view.findViewById(R.id.iv_red);
                iv_blue = (ImageView) view.findViewById(R.id.iv_blue);
                iv_custom = (ImageView) view.findViewById(R.id.iv_custom);
               
               此处可能由于忘记写view而导致报错
               
               ②View view = LayoutInflater.from((Context) SpotlightActivity.this.getApplication()).inflate(R.layout.activity_background_popup, null);
              
               可能加载的布局界面不对，而导致没找到ID报错
               

14、图片资源放在drawable-hdpi下能保持图片尺寸不变

15、android studio 打包报错：Generate Signed APK: Errors while building APK. You can find the errors in the 'Messages' view.
找到app文件下的build.gradle文件，之后在该文件中的android加入如下代码即可：

android {
......
lintOptions {
    checkReleaseBuilds false
    abortOnError false
    }
｝
