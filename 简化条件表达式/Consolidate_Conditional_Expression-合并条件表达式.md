# Consolidate Conditional Expression

有时程序中有一串条件检查，检查条件各不相同，最终行为却一致。这种情况应该采用“||”和“&&”将它们合并为一个条件表达式。

```java
double disabilityAmount() {
    if(_seniority < 0) return 0;
    if(_monthsDisabled > 12)return 0;
    if(_isPartTime) return 0;
    //compute the disability amount
}
```

重构后，

```java
double disabilityAmount() {
    if(isNotEligableForDisability()) return 0;
    //compute the dis ability mount
}
```

如果这些检查是彼此独立，的确不能视为同一次检查，那么就不要使用本项重构。因为在这种情况下，你的代码已经清楚表达出自己的意义。

