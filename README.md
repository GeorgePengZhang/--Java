## 概述

**模式**是特定环境下人们解决某类重复出现问题的一套成功或有效的解决方案。

**软件模式**是将模式的一般概念应用于软件开发领域，即软件开发的总体指导思想或参照样板。软件模式并非仅限于设计模式，还包括架构模式、分析模式和过程模式等。

**设计模式**是一套被反复使用、多数人知晓的、经过分类编目的、代码设计经验的总结，使用设计模式是为了可重用代码、让代码更容易被他人理解并且保证代码可靠性。

## 七大设计原则

### 1、单一职责原则（Single Responsibility Principle）

**定义：**一个类只负责一个功能领域中的相应职责，或者就一个类而言，应该只有一个引起它变化的原因。

一个类不能太"累"！在软件系统中，一个类(大到模块，小到方法)承担的职责越多，它被复用的可能性就越小，而且一个类承担的职责过多，就相当于将这些职责耦合在一起，当其中一个职责变化时，可能会影响其他职责的运作，因此要将这些职责进行分离，将不同的职责封装在不同的类中，即将不同的变化原因封装在不同的类中，如果多个职责总是同时发生改变则可将它们封装在同一个类中。

### 2、开闭原则（Open-Closed Principle）

**定义：**软件实体(类、模块、函数等等)应该是可以扩展的，但是不可修改。

任何软件都需要面临一个很重要的问题，即它们的需求会随时间的推移而发生变化。当软件系统需要面对新的需求时，我们应该尽量保证系统的设计框架是稳定的。如果一个软件设计符合开闭原则，那么可以非常方便地对系统进行扩展，而且在扩展时无须修改现有代码，使得系统在拥有适应性和灵活性的同时具备较好的稳定性和延续性。随着软件规模越来越大，软件寿命越来越长，软件维护成本越来越高，设计满足开闭原则的软件系统也变得越来越重要。


### 3、里氏代换原则（Liskov Substitution Principle）

**定义：**所有引用基类（父类）的地方必须能透明地使用其子类的对象。

一个软件实体如果使用的是一个父类的话，那么一定适用于其子类，而且它察觉不出父类对象和子类对象的区别。也就是说，在软件里面，把父类都替换成它的子类，程序行为没有变化。

里氏代换原则是面向对象设计的基本原则之一。 里氏代换原则中说，任何基类可以出现的地方，子类一定可以出现。LSP 是继承复用的基石，只有当派生类可以替换掉基类，且软件单位的功能不受到影响时，基类才能真正被复用，而派生类也能够在基类的基础上增加新的行为。里氏代换原则是对开闭原则的补充。实现开闭原则的关键步骤就是抽象化，而基类与子类的继承关系就是抽象化的具体实现，所以里氏代换原则是对实现抽象化的具体步骤的规范。

在软件中将一个基类对象替换成它的子类对象，程序将不会产生任何错误和异常，反过来则不成立，如果一个软件实体使用的是一个子类对象的话，那么它不一定能够使用基类对象。例如：我喜欢动物，那我一定喜欢狗，因为狗是动物的子类；但是我喜欢狗，不能据此断定我喜欢动物，因为我并不喜欢老鼠，虽然它也是动物。


### 4、依赖倒转原则（Dependence Inversion Principle）

**定义：**抽象不应该依赖于细节，细节应该依赖于抽象。换而言之，要针对接口编程，而不是针对实现编程。

我们在程序代码中传递参数时或在关联关系中，尽量引用层次高的抽象层类，即使用接口和抽象类进行变量类型声明、参数类型声明、方法返回类型声明，以及数据类型的转换等，而不要用具体类来做这些事情。为了确保该原则的应用，一个具体类应当只实现接口或抽象类中声明过的方法，而不要给出多余的方法，否则将无法调用到在子类中增
加的新方法。

### 5、接口隔离原则（Interface Segregation Principle）

**定义：**使用多个专门的接口，而不使用单一的总接口。即客户端不应该依赖那些它不需要的接口。

它还有另外一个意思是：降低类之间的耦合度。由此可见，其实设计模式就是从大型软件架构出发、便于升级和维护的软件设计思想，它强调降低依赖，降低耦合。

当一个接口太大时，我们需要将它分割成一些更细小的接口，使用该接口的客户端仅需知道与之相关的方法即可。每一个接口应该承担一种相对独立的角色，不干不该干的事，该干的事都要干。

### 6、合成复用原则（Composite Reuse Principle）

**定义：**尽量使用对象组合，而不是继承来达到复用的目的。

在一个新的对象里通过关联关系（包括组合关系和聚合关系）来使用一些已有的对象，使之成为新对象的一部分；新对象通过委派调用已有对象的方法达到复用功能的目的。简言之：复用时要尽量使用组合/聚合关系（关联关系），少用继承。

### 7、迪米特法则，又称最少知道原则（Law of Demeter Principle）

**定义：**一个软件实体应当尽可能少地与其他实体发生相互作用。

如果两个类不必彼此直接通信，那么这两个类就不应当发生直接的相互作用。如果其中一个类需要调用另一个类的某一个方法的话，可以通过第三方转发这个调用。

最少知道原则是指：一个实体应当尽量少地与其他实体之间发生相互作用，使得系统功能模块相对独立。

如果一个系统符合迪米特法则，那么当其中某一个模块发生修改时，就会尽量少地影响其他模块，扩展会相对容易，这是对软件实体之间通信的限制，迪米特法则要求限制软件实体之间通信的宽度和深度。迪米特法则可降低系统的耦合度，使类与类之间保持松散的耦合关系。

## 24种设计模式，可以分为三大类

### 创建型模式(Creational Patterns)

这些设计模式提供了一种在创建对象的同时隐藏创建逻辑的方式，而不是使用 new 运算符直接实例化对象。这使得程序在判断针对某个给定实例需要创建哪些对象时更加灵活。

- [简单工厂模式(Simple Factory Pattern)](https://github.com/GeorgePengZhang/DesignPattern-Java/blob/master/%E5%88%9B%E5%BB%BA%E5%9E%8B%E6%A8%A1%E5%BC%8F/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%E4%B9%8B%E7%AE%80%E5%8D%95%E5%B7%A5%E5%8E%82%E6%A8%A1%E5%BC%8F.md)

- [工厂方法模式(Factory Method Pattern)](https://github.com/GeorgePengZhang/DesignPattern-Java/blob/master/%E5%88%9B%E5%BB%BA%E5%9E%8B%E6%A8%A1%E5%BC%8F/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%E4%B9%8B%E5%B7%A5%E5%8E%82%E6%96%B9%E6%B3%95%E6%A8%A1%E5%BC%8F.md)

- [抽象工厂模式(Abstract Factory Pattern)](https://github.com/GeorgePengZhang/DesignPattern-Java/blob/master/%E5%88%9B%E5%BB%BA%E5%9E%8B%E6%A8%A1%E5%BC%8F/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%E4%B9%8B%E6%8A%BD%E8%B1%A1%E5%B7%A5%E5%8E%82%E6%A8%A1%E5%BC%8F.md)

- [单例模式(Singleton Pattern)](https://github.com/GeorgePengZhang/DesignPattern-Java/blob/master/%E5%88%9B%E5%BB%BA%E5%9E%8B%E6%A8%A1%E5%BC%8F/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%E4%B9%8B%E5%8D%95%E4%BE%8B%E6%A8%A1%E5%BC%8F.md)

- [原型模式(Prototype Pattern)](https://github.com/GeorgePengZhang/DesignPattern-Java/blob/master/%E5%88%9B%E5%BB%BA%E5%9E%8B%E6%A8%A1%E5%BC%8F/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%E4%B9%8B%E5%8E%9F%E5%9E%8B%E6%A8%A1%E5%BC%8F.md)

- [建造者模式(Builder Pattern)](https://github.com/GeorgePengZhang/DesignPattern-Java/blob/master/%E5%88%9B%E5%BB%BA%E5%9E%8B%E6%A8%A1%E5%BC%8F/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%E4%B9%8B%E5%BB%BA%E9%80%A0%E8%80%85%E6%A8%A1%E5%BC%8F.md)


### 结构型模式(Structural Patterns)

这些设计模式关注类和对象的组合。继承的概念被用来组合接口和定义组合对象获得新功能的方式。

- [适配器模式(Adapter Pattern)](https://github.com/GeorgePengZhang/DesignPattern-Java/blob/master/%E7%BB%93%E6%9E%84%E5%9E%8B%E6%A8%A1%E5%BC%8F/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%E4%B9%8B%E9%80%82%E9%85%8D%E5%99%A8%E6%A8%A1%E5%BC%8F.md)

- [桥接模式(Bridge Pattern)](https://github.com/GeorgePengZhang/DesignPattern-Java/blob/master/%E7%BB%93%E6%9E%84%E5%9E%8B%E6%A8%A1%E5%BC%8F/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%E4%B9%8B%E6%A1%A5%E6%8E%A5%E6%A8%A1%E5%BC%8F.md)

- [组合模式（Composite Pattern）](https://github.com/GeorgePengZhang/DesignPattern-Java/blob/master/%E7%BB%93%E6%9E%84%E5%9E%8B%E6%A8%A1%E5%BC%8F/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%E4%B9%8B%E7%BB%84%E5%90%88%E6%A8%A1%E5%BC%8F.md)

- [装饰器模式（Decorator Pattern）](https://github.com/GeorgePengZhang/DesignPattern-Java/blob/master/%E7%BB%93%E6%9E%84%E5%9E%8B%E6%A8%A1%E5%BC%8F/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%E4%B9%8B%E8%A3%85%E9%A5%B0%E6%A8%A1%E5%BC%8F.md)

- [外观模式（Facade Pattern）](https://github.com/GeorgePengZhang/DesignPattern-Java/blob/master/%E7%BB%93%E6%9E%84%E5%9E%8B%E6%A8%A1%E5%BC%8F/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%E4%B9%8B%E5%A4%96%E8%A7%82%E6%A8%A1%E5%BC%8F.md)

- [享元模式（Flyweight Pattern）](https://github.com/GeorgePengZhang/DesignPattern-Java/blob/master/%E7%BB%93%E6%9E%84%E5%9E%8B%E6%A8%A1%E5%BC%8F/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%E4%B9%8B%E4%BA%AB%E5%85%83%E6%A8%A1%E5%BC%8F.md)

- [代理模式（Proxy Pattern）](https://github.com/GeorgePengZhang/DesignPattern-Java/blob/master/%E7%BB%93%E6%9E%84%E5%9E%8B%E6%A8%A1%E5%BC%8F/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%E4%B9%8B%E4%BB%A3%E7%90%86%E6%A8%A1%E5%BC%8F.md)



### 行为型模式(Behavioral Patterns)

这些设计模式特别关注对象之间的通信。

- [责任链模式（Chain of Responsibility Pattern）](https://github.com/GeorgePengZhang/DesignPattern-Java/blob/master/%E8%A1%8C%E4%B8%BA%E5%9E%8B%E6%A8%A1%E5%BC%8F/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%E4%B9%8B%E8%81%8C%E8%B4%A3%E9%93%BE%E6%A8%A1%E5%BC%8F.md)

- [命令模式（Command Pattern）](https://github.com/GeorgePengZhang/DesignPattern-Java/blob/master/%E8%A1%8C%E4%B8%BA%E5%9E%8B%E6%A8%A1%E5%BC%8F/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%E4%B9%8B%E5%91%BD%E4%BB%A4%E6%A8%A1%E5%BC%8F.md)

- [解释器模式（Interpreter Pattern）](https://github.com/GeorgePengZhang/DesignPattern-Java/blob/master/%E8%A1%8C%E4%B8%BA%E5%9E%8B%E6%A8%A1%E5%BC%8F/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%E4%B9%8B%E8%A7%A3%E9%87%8A%E5%99%A8%E6%A8%A1%E5%BC%8F.md)

- [迭代器模式（Iterator Pattern）](https://github.com/GeorgePengZhang/DesignPattern-Java/blob/master/%E8%A1%8C%E4%B8%BA%E5%9E%8B%E6%A8%A1%E5%BC%8F/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%E4%B9%8B%E8%BF%AD%E4%BB%A3%E5%99%A8%E6%A8%A1%E5%BC%8F.md)

- [中介者模式（Mediator Pattern）](https://github.com/GeorgePengZhang/DesignPattern-Java/blob/master/%E8%A1%8C%E4%B8%BA%E5%9E%8B%E6%A8%A1%E5%BC%8F/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%E4%B9%8B%E4%B8%AD%E4%BB%8B%E8%80%85%E6%A8%A1%E5%BC%8F.md)

- [备忘录模式（Memento Pattern）](https://github.com/GeorgePengZhang/DesignPattern-Java/blob/master/%E8%A1%8C%E4%B8%BA%E5%9E%8B%E6%A8%A1%E5%BC%8F/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%E4%B9%8B%E5%A4%87%E5%BF%98%E5%BD%95%E6%A8%A1%E5%BC%8F.md)

- [观察者模式（Observer Pattern）](https://github.com/GeorgePengZhang/DesignPattern-Java/blob/master/%E8%A1%8C%E4%B8%BA%E5%9E%8B%E6%A8%A1%E5%BC%8F/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%E4%B9%8B%E8%A7%82%E5%AF%9F%E8%80%85%E6%A8%A1%E5%BC%8F.md)

- [状态模式（State Pattern）](https://github.com/GeorgePengZhang/DesignPattern-Java/blob/master/%E8%A1%8C%E4%B8%BA%E5%9E%8B%E6%A8%A1%E5%BC%8F/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%E4%B9%8B%E7%8A%B6%E6%80%81%E6%A8%A1%E5%BC%8F.md)

- [策略模式（Strategy Pattern）](https://github.com/GeorgePengZhang/DesignPattern-Java/blob/master/%E8%A1%8C%E4%B8%BA%E5%9E%8B%E6%A8%A1%E5%BC%8F/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%E4%B9%8B%E7%AD%96%E7%95%A5%E6%A8%A1%E5%BC%8F.md)

- [模板方法模式（Template Method Pattern）](https://github.com/GeorgePengZhang/DesignPattern-Java/blob/master/%E8%A1%8C%E4%B8%BA%E5%9E%8B%E6%A8%A1%E5%BC%8F/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%E4%B9%8B%E6%A8%A1%E6%9D%BF%E6%96%B9%E6%B3%95%E6%A8%A1%E5%BC%8F.md)

- [访问者模式（Visitor Pattern）](https://github.com/GeorgePengZhang/DesignPattern-Java/blob/master/%E8%A1%8C%E4%B8%BA%E5%9E%8B%E6%A8%A1%E5%BC%8F/%E8%AE%BE%E8%AE%A1%E6%A8%A1%E5%BC%8F%E4%B9%8B%E8%AE%BF%E9%97%AE%E8%80%85%E6%A8%A1%E5%BC%8F.md)








