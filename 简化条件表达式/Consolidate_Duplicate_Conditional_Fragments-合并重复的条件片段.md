# Consolidate Duplicate Conditional Fragments 

在条件表达式的每个分支上有着相同的一段代码，可以将这段重复代码搬移到条件表达式之外

```java
if(isSpecialDeal()) {
    total = price * 0.95;
    send();
} else {
    total = price * 0.95;
    send();
}
```

重构后，代码能够更清楚地表明哪些东西随条件变化而变化，哪些东西保持不变。

```java
if(isSpecialDeal()) {
    total = price * 0.95;
} else {
    total = price * 0.95;
}
send();
```

