*明日科技（www.mingrisoft.com） 用户名：bbgavin

9.1/2、普通对话框 ① AlertDialog ② setIcon() setTitle() setMessage() setButton() ③ 调用show()方法

  列表对话框 ① AlertDialog.Buileder ② setIcon() setTitle() setItems(）| setSingleChoiceItems | setMultiChoiceItems setPositiveButton ③ 调用Builder对象的.create().show()方法
  
9.3、 使用Notification显示通知的步骤： ① 获取系统的NotificationManager服务（getSystemService()方法） ② 创建Notification对象 ③ 为Notification对象设置属性 ④ 发送Notification通知（NotificationManager类的notify()方法）
