##  Introduce Explaining Variable(引入解释性变量)

程序存在一个复杂的表达式，将该复杂的表达式（或其中一部分）的结果放进一个临时变量，以此变量名称来解释表达式用途。

```java
if((platform.toUpperCase().indexOf("MAC")> -1 )&&
   (browser.toUpperCase().indexOf("ie") > -1)&&
   wasInitialized() && resize > 0) {
    //do something
}
```

通过引入解释性变量进行重构，

```java
final boolean isMacOs = platform.toUpperCase().indexOf("MAC")> -1;
final boolean isIEBrowser = browser.toUpperCase().indexOf("ie") > -1;
final boolean wasInitialized = resize > 0;

if(isMacOs && isIEBrowser && wasInitialized() && wasInitialized) {
    //do something
}
```

