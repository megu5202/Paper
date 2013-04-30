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

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~Java
public class Tuple1
{
	public Integer x;
	public Integer y;

	public Tuple1(Integer a, Integer b)
	{
		x = a;
		y = b;
	}
}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Tuple of Double
===============

But after a while we realize we also need a tuple of Doubles and we want to return ( 5.0, 3.5)

So we have to write a whole new class of Tuples that allow for Doubles. 

A Double tuple Class
====================

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~Java
public class Tuple2
{
	public Double x;
	public Double y;

	public Tuple2(Double a, Double b)
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

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~Java
public class Tuple<A, B>
{
	public A x;
	public B y;

	public Tuple1(A a, B b)
	{
		x = a;
		y = b;
	}
}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This allows us to create this class and then allow us to set A, and B when we create the objects.

Using a Generic Tuple
=====================

Instead of using the different tuples we declare the type of the tuple

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~Java
Tuple<Integer, Integer> myTuple = new Tuple<Integer, Integer>();

Tuple< Double, Integer > myTuple2 = new Tuple < Double, Integer>();
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Proposal
========

Sun Microsystems realized the problem here and created JSR 14: Adding Generics to the Java Programming Language

They wanted to create a class that allowed for:
* the ability to create a class without declaring the types
* the ability to create container classes that could hold any type

Final Release
=============

Changed Java language spec to add C++ style template syntax.

Expanded the Java collections API to include genericized types.

Modified Reflections API to take advantage of generics. 


Positive Community Response
===========================

**Type Safety**

If the code compiles without warnings you are guaranteed that you will not throw a casting error. Unless you explicitly try and cast an object.

Positive Community Response
===========================

**Less explicit casts**

Generic types are all implicit casts

With the addition of Generic types there are less explicit casts because you don't have to cast to a specific type to use contaner type classes.

Positive Community Response
===========================

**Encourages Code Reusue**

Instead of having create new classes for each type of object.

Instead you can create one genericized class.

It is more efficient and creates a smaller code base.

If you make a change it is universal.

Negative Community Response
===========================

**Formal Type Parameters**

~~~~~~~~~~~~~~~Java
public class Example<T>
{
	private T x;
	public Example()
	{
		x = new T();
	}
}

~~~~~~~~~~~~~~~~

Negative Community Response
===========================

**Hiearchy of parameterized types**

~~~~~~~~~~~~~~~~~~~Java

List<Dog> ls = new ArrayList<Dog>();

ls.add( new Dog("Dalmatian") );
ls.add( new Dog("Lab") );

List<Animals> lo = ls; // Throws ERROR

~~~~~~~~~~~~~~~~~~~

Negative Community Response
==========================

**No Primatives**

~~~~~~~~~~Java

List<int> ls = new ArrayList<int>();

~~~~~~~~~~

Adds a layer of inefficiency

If you want a list of plain ints you cant have it.

Slide 18
========

Slide 19
========

Conclusion
==========





