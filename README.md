# KVC-KVO
键值观察者和键值编码！
观察者模式(有时又被称为发布/订阅模式)是软件设计模式的⼀一种。 在此种模式中,⼀一个⺫⽬目标对象管理所有相依于它的观察者对象,并且在
它本⾝身的状态改变时主动发出通知。这通常透过呼叫各观察者所提供的 ⽅方法来实现。
                        KVC
  1、全称是Key-value coding,翻译成键值编码。它提供了⼀一种使⽤用字
    符串⽽而不是访问器⽅方法去访问⼀一个对象属性的机制。
  2、通过setValue: forKey: 的⽅方式对类的属性进⾏行赋值,key为 属性的名称,value为具体的赋值。
  3、通过- (id)valueForKey:(NSString *)key 访问对象的 属性
                        KVO
  A类中的某个属性值发⽣生变化,B类的对象做为A类对象的观察者,能 够观察到此变化,并进⾏行后续的处理。
1. 为调⽤用对象添加观察者
    - (void)addObserver:(NSObject *)observer forKeyPath:(NSString *)keyPath options:(NSKeyValueObservingOptions)options 
      context:(void *)context;
函数说明:
observer-观察者对象
  keyPath-对象的key,需要观察的属性 options-观察键值变化的⼏几种可选⽅方式 context-可以传NULL,如果⾮非NULL,
  则在观察者回调函数中会收到⼀一些数据
2.观察者收到消息后的处理函数
  - (void)observeValueForKeyPath:(NSString *)keyPath ofObject:
(id)object change:(NSDictionary *)change context:(void *)context;
函数说明: keyPath-对象的key,需要观察的属性 object-发送通知的对象 change-包含变化之前与变化之后属性值的字典 
context-被观察者对象传⼊入的context
