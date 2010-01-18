Class.Singleton
==================

Class.Singleton defines and instantiates a singleton class.

How to use
----------

Class.Singleton objects can be defines as any Mootools class, taking advantage of the nice syntax and benefits of Mootools classes.

var MySingleton = new Class.Singleton({

	initialize: function(){
	},

	method1: function(){
	},

	method2: function(){
		
	}

});


Inheritance
-----------

Singletons also work when building complex classes using inheritance, mixins, etc.

var BaseClass = new Class({
	initialize: function() {
		// Initialization code here
		console.log('BaseClass initialized...');
	},
	method1: function() {
		// some code
	}
});

var MySingleton = new Class.Singleton({
	Extends: BaseClass,
	initialize: function() {
		this.parent();
		console.log('MySingleton);
	},
	method1: function() {
		this.parent();
		// more code
	}
});
