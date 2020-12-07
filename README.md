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
