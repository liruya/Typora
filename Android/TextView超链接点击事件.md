# TextView超链接点击事件

1. 布局文件设置

   ```xml
   android:autoLink="web | email | phone | map | none | all"
   android:textColorLink="#FFFFFFFF"
   ```

   可设置为web email phone map none all, 点击后跳转到对应的外部默认应用界面

2. 代码设置文字中部分可点击

   ```java
   textView.setText(getClickableSpan("clickText"));
   textView.setMovementMethod(LinkMovementMethod.getInstance());
   ```

   ```java
   private SpannableString getClickableSpan(final String text) {
       SpannableString spanStr = new SpannableString(text);
       //设置下划线文字
       spanStr.setSpan(new UnderlineSpan(), 0, text.length(), Spanned.SPAN_EXCLUSIVE_EXCLUSIVE);
       //设置文字的单击事件
       spanStr.setSpan(new ClickableSpan() {
           @Override
           public void onClick(View widget) {
               startWebActivity(text);
           }
       }, 0, text.length(), Spanned.SPAN_EXCLUSIVE_EXCLUSIVE);
       //设置文字的前景色
       spanStr.setSpan(new ForegroundColorSpan(Color.WHITE), 0, text.length(), Spanned.SPAN_EXCLUSIVE_EXCLUSIVE);
       return spanStr;
   }
   ```

   

