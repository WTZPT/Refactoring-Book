# Introduce Assertion

某一段代码需要对程序状态做出某种假设。 常常会有这样一段代码：只有当某条件为真时，该代码才能正常执行。如平方根计算只对正值才能进行，又如某个对象可能假设其字段至少有一个不等于null。

 这种假设通常并没有在代码中明确表现出来，必须阅读整个算法才能看出。有时通过注释写出这样的假设，现在可以考虑使用断言来明确这些假设。

```java
double getExpenseLimit() {
    return (_expenseLimit != NULL_EXPENSE)?
        _expenseLimit :
    	_primaryProject.getMemberExpenseLImit();
}
```

以断言明确表现这种假设进行重构，

```java
double getExpenseLimit() {
    Assert.isTrue(_expenseLimit != NULL_EXPENSE || _primaryProject != null)
    return (_expenseLimit != NULL_EXPENSE)?
        _expenseLimit :
    	_primaryProject.getMemberExpenseLImit();
}
```



>  断言是一个条件表达式，应该总是为真。如果它失败，表示程序员犯了错误。因此断言的失败应该导致一个非受控异常。断言绝对不能被系统的其他部分使用。实际上，程序最后的成品往往将断言统统删除。

注意，不要滥用断言。请不要使用它来检查“你认为应该为真”的条件，请使用它来检查“一定必须为真”的条件。**滥用断言可能会造成难以维护的重复逻辑。**

应该常常问自己，如果断言所指示的约束条件不能满足，代码是否仍能正常运行？如果可以，就把断言拿掉。

