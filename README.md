# Design-Patterns
# 设计模式的练习

## 迭代器 Iterator
		
	/** 
	 * 	为什么要引入迭代器（Iterator）呢？
	 *	这里只使用了Iterator的hasNext和next方法
	 *	也就是说 不依赖于BookShelf的实现
	 *	所以不管BookShelf怎么改变，只要BookShelf的iterator()方法有效
	 *	即使不对while循环进行修改，代码也能正常运行
	 *	帮助我们编写【可复用】的代码
	 *
	 * 	将遍历功能置于Aggregate角色外是Iterator模式的一个特征
	 * 	根据这个特征可以针对一个ConcreteAggregate角色编写多个ConcreteIterator角色
	 *
	 * 	//遍历方法可以多种多样
	 * 	//不需要deleteIterator 
	 */
	
## 适配器 Adapter
		
	/**
	* 使用现有的类时，可以使用适配模式来把这些现有的类当做【组件】使用
	* 当出现bug时我们可以很明确的知道bug不是由现有的类产生的
	* 可以不改变现有代码的前提下适配新的接口（API）
	* 可以解决新旧版本兼容性问题
	*/	 
		 
## 模板方法 TemplateMethod	 
		 
	/**
	* 模板方法模式的优点是可以在抽象父类中编写算法
	* 要求父类子类之间的协作与一致性
	* 处理的流程被定义在父类中，而具体的处理则交给了子类
	*/ 
	 	
## 工厂方法 FactoryMethod	
	 	
	/**
	* 工厂模式把框架(framework包)和具体加工(idcard包) 分离开来 进行【解耦】
	* 框架(framework包)不依赖 具体加工(idcard包)
	* 不用new关键字来生成实例，而是调用专用方法进行生成，防止父类和其他具体类耦合
	* 
	* 注意：使用模板方法模式和工厂方法模式需要理解框架，所以必须要向维护这些类的开发人员正确的传达设计意图
	*
	*
	* 多种生成实例的方法:
	* 	1.定义为抽象方法:像现在一样在Factory类中直接定义，这样子类就必须实现。
	* 		protected abstract Product createProduct(String name);
	* 	2.为其实现默认处理，这样的话如果子类没有实现该方法，将进行默认处理
	* 		public Product createProduct(String name){
	* 			return new Product(name);		
	* 		}
	* 	3.在其中抛出异常，这样子类没有实现的话可以告知程序员(异常类需编写)
	* 		public Product createProduct(String name){
	* 			throw new FactoryMethodRuntimeException();	
	* 		}
	*/
	 	
## 单例 Singleton
		 
	/**
	*	private static Singleton singleton=new Singleton();
	* 	//必须为private 防止不小心使用new关键字创建  
	*	//并且不能先为null 否则会有线程安全问题
	*
	*	//获取唯一实例的方法通常命名为:getInstance
	*/ 	
	 	
## 原型 Prototype
		 
	/**
	*	以下情况我们无法根据类来生成实例，而要根据实例来生成实例
	*	1.对象总类繁多，无法将他们整合到一个类时
	*	2.难以根据类生成实例时
	*	3.想解耦框架与生成的实例时
	*
	*	在Porduct和Manager类中的代码完全没有出现其他类，意味着我们可以独立修改这两个类，不受其他类影响
	*	这是很重要的，因为一旦在类中使用到了别的类名，就意味着该类与其他类紧密地耦合在一起
	*	
	*	作为【组件复用】：一旦在代码中出现要使用类的名字，就无法与类分离开来，也就是无法实现复用
	*	此处说的“作为组件复用”中不包含替换源代码，以JAVA来说，重要的是当手边只有.class文件时，该类能否复用
	*	即【即使没有.java文件也能复用该类】
	*
	*	//实现Clonable接口的类的实例可以调用clone方法进行复制
	*	//clone方法的返回值是复制出新的实例
	*	//没有实现Clonable接口的类调用clone方法会在运行时抛出异常（CloneNotSupportedException）
	*
	*	//clone方法定义在java.lang.Object中，因此所有类都继承了clone方法
	*	//Clonable接口只是【标记接口】，没有实现任何方法
	*	
	*	//clone方法进行的是【浅复制】
	*	//只是：将被复制的实例的字段值直接复制到新的实例中
	*	//例如：当字段中保存的是数组时，使用clone方法进行复制只会复制该数组的引用
	*	//无法满足需求时：重写clone方法，并使用super.clone()来调用父类的clone方法
	*	//注意：clone只是复制，并不会调用被复制实例的构造函数，对于需要初始化的类需要自己实现clone方法，并在内部进行初始化操作
	*	
	*/ 	
	 	
## 构建 Builder	
	 	
	 	
	 	
	 	
	 	
	 	
	 	
	 	
	 	
	 	
	 	
	 	
	 	
	 	
	 	
	 	
