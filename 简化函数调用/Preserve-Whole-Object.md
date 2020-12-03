## Preserve Whole Object(保持对象完整)

从某个对象中取出若干值，将它们作为某一次函数调用时的参数，可以考虑传递整个对象。

```java
int low = daysTempRange().getLow();
int high = daysTempRange().getHigh();
withinPlan = plan.withinRange(low,high);
```

重构后，

```java
withinPlan = plan.withinRange(daysTempRange());
```

该重构方法需要注意，当你传递的是数值，被调用函数就只依赖于这些数值，而不依赖它们所属的对象。**当你传递的是整个对象，被调用函数所在的对象就需要依赖参数对象**，如果这会使你的依赖结构恶化，那么就不该使用该方法进行重构。





作者观点：

> 如果被调用函数只需要参数对象的其中一项数值，那么只传递那个数值会更好。我并不认同这种观点，因为传递一项数值和传递一个对象，至少在代码清晰度上是等价的（当然对于按值传递的参数来说，性能上可能有所差异）。更重要的考量应该放在对象之间的依赖关系上。

