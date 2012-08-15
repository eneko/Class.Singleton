Class.Singleton
==================

Class.Singleton defines and instantiates a singleton class.

![Screenshot](http://github.com/eneko/Class.Singleton/raw/master/screenshot.jpg)

How to use
----------

Class.Singleton objects can be defines as any Mootools class, taking advantage of the nice syntax and benefits of Mootools classes.

	var MySingleton = new Class.Singleton({
		initialize: function(){
			// code here
		},
		method1: function(){
			// code here
		},
		method2: function(){
			// code here
		}
	});

To obtain the singleton object, use getInstance:

	var foo = MySingleton.getInstance().method1();

Alternatively, the instance can be assigned to the global variable instead
of the class:

	var MySingleton = new Class.Singleton({
		// ...
	}).getInstance();

	var foo = MySingleton.method1();


Inheritance
-----------

Singletons also work when building complex classes using inheritance, mixins, etc.

	var BaseClass = new Class({
		initialize: function() {
			// Initialization code here
			console.log('BaseClass initialized.');
		},
		method1: function() {
			// some code
		}
	});

	var MySingleton = new Class.Singleton({
		Extends: BaseClass,
		initialize: function() {
			this.parent();
			console.log('MySingleton initialized.');
		},
		method1: function() {
			this.parent();
			// more code
		}
	});

Note that singletons created with Class.Singleton are automatically instantiated and initialized.