# Replace Array with Object

你有一个数组，其中的元素各自代表不同的东西。**以对象替换数组，对于数组中的每个元素，以一个字段来表示**。

```java
String[] row = new String[3];
row[0] = "Liverpool";
row[1] = "15";
```

重构后，

```java
Performance row = new Performance();
row.setName("Liverpool");
row.setWins("15");
```

