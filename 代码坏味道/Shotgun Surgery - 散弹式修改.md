## Shotgun Surgery



Shotgun Surgery是指每遇到某种变化时都必须在许多不同的类内做出许多小修改。如果需要修改的代码散步四处，会造成很难找到它们。

在这种情况下应该使用[Move Method(142)](..\在对象之间搬移特性\Move_Method-搬移函数.md)和[Move File(146)](..\在对象之间搬移特性\Move_Field-搬移字段.md)把所有需要修改的代码放进同一个类。如果眼下没有合适的类可以安置这些代码，就创建一个。通过运用[Inline Class(154)](..\在对象之间搬移特性\Inline_Class-将类内联化.md)把一系列相关行为放进同一个类。这可能会造成少量的Divergent Change，但可以更加轻易处理它。

