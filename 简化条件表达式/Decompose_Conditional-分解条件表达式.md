# Decompose Conditional

在程序之中，复杂的条件逻辑是最常导致复杂度上升的地点之一。

可以将条件语句分解为多个独立函数，根据每个小块代码的用途，为分解而得的新函数命名，并将原函数中对应的代码改为调用新建函数，从而更清楚地表达自己的意图,提高代码可读性。

```java
if(date.before(SUMMER_START) || date.after(SUMMER_END)) {
    charge = quantity * _winterRate * _winterServiceCharge;
} else {
    charge = quantity * _summerRate;
}
```

重构后，

```java
if(notSummer(date)) {
    charge = winterCharge(quantity);
}else {
    charge = summerCharge(quantity);
}
```











