

# Duplicated Code

## 同一个类的两个函数含有相同的表达式

```java
void printOwing(double amount) {
    printBanner();
    
    //print details
    System.out.println("name: "+ _name);
    System.out.println("amount: "+ amount);
}
```

通过提炼强化代码的清晰度，

 ```java
void printOwing(double amount) {
    printBanner();
}

void printDetails(double amount){
    System.out.println("name: "+ _name);
    System.out.println("amount: "+ amount);
}
 ```

## 两个互为兄弟的子类内含相同表达式

1. 对两个类都提炼函数
2. 对提炼出来的代码将它推入超类内,在子类中对它使用PULL Up Method



## 两个互为兄弟的子类内含表达式代码间类似，没有完全相同

1. 运用提炼函数将相似部分和差异部分割开，构成单独一个函数
2. 考虑使用塑造模板函数方法，运用Template Method设计模式，如下

<img src="../$%7Bimage%7D/image-20201203112810648.png" alt="image-20201203112810648" style="zoom: 80%;" />

[^图所在页]:P367



## 两个函数以不同的算法做相同的事

选择其中较清晰的一个，将其他函数的算法替换掉。

```java
 String foundPerson(String[] people) {
     for(int i = 0; i < people.length; i++) {
         if(people[i].equals("Don")) {
             return "Don";
         }
         if(people[i].equals("John")) {
             return "John";
         }
         if(people[i].equals("Kent")) {
             return "Kent";
         }
     }
     return "";
 }
```

替换上面算法实现，

```java
String foundPerson(String[] people) {
    List candidates = Arrays.asList(new String[]{"Don", "John", "Kent"});
    for(int i = 0; i < people.length; i++) {
        if(candidates.contains(people[i])) {
            return people[i];
        }
    }
    return "";
}
```



## 两个毫不相关的类出现Duplicated Code

1. 考虑对其中一个类进行提炼类（如下图），将重复代码提炼到一个独立类中，然后在另一个类内使用这个新类。

![image-20201203133407695](../$%7Bimage%7D/image-20201203133407695.png)

