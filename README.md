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
