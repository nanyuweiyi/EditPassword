# SeparatedEditText
密码输入框。有实心，空心以及下划线形式。可控制明文密文显示。

## screenshot

<img src='https://github.com/WGwangguan/SeparatedEditText/blob/master/screenshot/shixin.gif' height='600'/>

<img src='https://github.com/WGwangguan/SeparatedEditText/blob/master/screenshot/kongxin.gif' height='600'/>

<img src='https://github.com/WGwangguan/SeparatedEditText/blob/master/screenshot/kongxin.gif' height='600'/>

## 如何安装

- 配置根目录的build.gradle 
```java
allprojects {
	repositories {
		...
		maven { url "https://jitpack.io" }
	}
}
```

- 配置app module的build.gradle 
```java
dependencies {
    implementation 'com.github.WGwangguan:SeparatedEditText:v1.0'
}
```

## 如何使用

1. 布局文件

在布局文件中添加SeparatedEditText并设置相关自定义属性
```
// 实心输入框
    <com.kenny.separatededittext.SeparatedEditText
        android:id="@+id/edit_solid"
        android:layout_width="match_parent"
        android:layout_height="50dp"
        android:inputType="number"
        app:blockColor="@color/colorPrimary"
        app:blockSpacing="2dp"
        app:corner="10dp"
        app:maxLength="9"
        app:cursorWidth="3dp"
        app:cursorDuration="1000"
        app:cursorColor="@android:color/holo_green_light"
        app:separateType="@integer/type_solid"
        app:textColor="@color/colorAccent" />
    
// 下划线输入框
<com.kenny.separatededittext.SeparatedEditText
        android:id="@+id/edit_underline"
        android:layout_width="match_parent"
        android:layout_height="50dp"
        android:layout_marginTop="20dp"
        android:inputType="number"
        app:blockSpacing="10dp"
        app:borderColor="@color/lightGrey"
        app:separateType="@integer/type_underline"
        app:textColor="@color/colorAccent" />

//空心输入框
<com.kenny.separatededittext.SeparatedEditText
        android:id="@+id/edit_hollow"
        android:layout_width="match_parent"
        android:layout_height="50dp"
        android:layout_marginTop="20dp"
        android:inputType="number"
        app:borderColor="@color/lightGrey"
        app:corner="10dp"
        app:cursorColor="@android:color/holo_orange_light"
        app:cursorWidth="3dp"
        app:maxLength="4"
        app:separateType="@integer/type_hollow"
        app:textColor="@color/colorAccent" />
        
```

注：需给控件设置相应宽高。

2. Java代码

可以通过代码设置所有相关的自定义属性
```
public void handleContent(View v) {
        solid.setPassword(!showContent);
        hollow.setPassword(!showContent);
        underline.setPassword(!showContent);
        showContent = !showContent;
    }

public void handleCursor(View v) {
        solid.setShowCursor(!showCursor);
        hollow.setShowCursor(!showCursor);
        underline.setShowCursor(!showCursor);
        showCursor = !showCursor;
    }
    
```

## 可配置属性

#### SeparatedEditText

属性名 | 属性说明
:---:|:---:
password | 设置是否是密码样式，true 则显示小圆点
showCursor | 设置是否显示游标
separateType | 设置显示样式：type_hollow、type_solid、type_underline
maxLength | 设置显示框框个数
corner | 设置圆角 dp
borderColor | 设置边框颜色，type_hollow、type_underline适用
borderWidth | 设置边框粗细 dp
blockColor | 设置框框实心部分颜色，type_solid适用
blockSpacing | 设置框框间隙，type_solid、type_underline适用
textColor | 设置文本绘制颜色
cursorColor | 设置游标显示颜色
cursorWidth | 设置进游标宽度
cursorDuration | 设置游标闪烁时长 毫秒


