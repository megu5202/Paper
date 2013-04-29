Java Generics
=============

**Java Generics**

By: Nic Broeking, Melissa Guba, Joshua Rahm

What is a generic type?
=======================

A generic type by definition is a generic class or interface that is parameterized over types.

In other words it is a class where you define the type of the member variables when you create the object.

What does this mean?
====================

Lets say we want a tuple class.

But at first we want a tuple of two Integers: ( 5, 3 )

We would write a tuple class of Integers. 

A Integer tuple Class
=====================

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
class tuple1
{
	public Integer x;
	public Integer y;

	tuple1(Integer a, Integer b)
	{
		x = a;
		y = b;
	}
}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Tuple of Double
===============

But after a while we relize we also need a tuple of Doubles and we want to return ( 5.0, 3.5)

So we have to write a whole new class of Tuples that allow for Doubles. 

A Double tuple Class
====================

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
class tuple2
{
	public Double x;
	public Double y;

	tuple1(Double a, Double b)
	{
		x = a;
		y = b;
	}
}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

But then we decide we need a tuple of different Objects. So more tuple classes!!!

Generics
========

Instead of creating more tuple classes we want a generic class. 

This generic class would allow us to decide the types when we use the tuple.

A Generic Tuple
===============

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
class tuple<A, B>
{
	public A x;
	public B y;

	tuple1(A a, B b)
	{
		x = a;
		y = b;
	}
}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This allows us to create this class and then allow us to set A, and B when we create the objects.

Using a Generic Tuple
=====================

Instead of using the different tuples we declaire the type of the tuple

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
tuple<Integer, Integer> myTuple = new tuple<Integer, Integer>();

tuple< Double, Integer > myTuple2 = new tuple < Double, Integer>();
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Proposal
========

Sun Microsystems relized the problem here and created JSR 14: Adding Generics to the Java Programming Language

They wanted to create a class that allowed for:
* the ability to create a class without declairing the types
* the ability to create container classes that could hold any type

Final Release
=============

Changed java language spec to add c++ style template syntax.

Expanded the java collections api to include genericized types.

Modified reflextions api to take advatage of generics. 

Positive Community Responce
===========================

### Things people like
1. Adds type safety
2. Cleans up code
3. Encourages code reuse.

Negative Community Responce
===========================

### Things people don't like
1. Code Obfuscatation : List<<CellTable< ActionButton< String, Integer>, ? extends DateFormat<String>>
2. Do not work with primative types
3. Types are not enforced at runtime

Slide 14
========

Slide 15
========

Slide 16
========

Slide 17
========

Slide 18
========

Slide 19
========

Slide 20
========



