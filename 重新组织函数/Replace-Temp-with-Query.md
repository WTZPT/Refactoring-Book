## Replace Temp with Query （以查询取代临时变量）

程序存在以一个临时变量保存某一个表达式的运算结果，将这个表达式提炼到一个独立函数中，将这个临时变量的所有引用点替换为对新函数的调用。此后，新函数就可以被其他函数调用。

```JAVA
void method1(double quantity, double itemPrice) {
    double basePrice = quantity * itemPrice;
    ...
}

void method2(double quantity, double itemPrice) {
    double basePrice = quantity * itemPrice;
    ...
}

void method3(double quantity, double itemPrice) {
    double basePrice = quantity * itemPrice;
    ...
}
```

重构后，

```java
void method1(double quantity, double itemPrice) {
    final double basePrice = calculateBasePrice(quantity, itemPrice);
    ...
}

void method2(double quantity, double itemPrice) {
    final double basePrice = calculateBasePrice(quantity, itemPrice);
    ...
}

void method3(double quantity, double itemPrice) {
    final double basePrice = calculateBasePrice(quantity, itemPrice);
    ...
}

private double calculateBasePrice(double quantity, double itemPrice) {
    return quantity * itemPrice;
}
```

