Java Generics
=============

**Java Generics**

By: Nic Broeking, Melissa Guba, Joshua Rahm

What is a generic type?
=======================

A Generic Type is a generic class or interface that is parameterized over types.


What does this mean?
====================

Example: implementation of a tuple class

Tuple of Integers:

(5, 3)

Tuple Class for Integers
=====================

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
public class Tuple1{
	public Integer x;
	public Integer y;

	public Tuple1(Integer a, Integer b){
		x = a;
		y = b;
	}
}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Tuple of Double
===============

Tuple of Doubles:

(5.0, 3.5)


Tuple Class for Doubles
====================

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
public class Tuple2{
	public Double x;
	public Double y;

	public Tuple2(Double a, Double b){
		x = a;
		y = b;
	}
}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Generics
========

Tuple of Characters:

("a", "b")


A Generic Tuple
===============

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
public class Tuple<A, B>{
	public A x;
	public B y;

	public Tuple1(A a, B b){
		x = a;
		y = b;
	}
}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Using a Generic Tuple
=====================

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
tuple<Integer, Integer> Tuple1 = new tuple <Integer, Integer>();
tuple<Double, Integer> Tuple2 = new tuple <Double, Integer>();
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Proposal
========

* Type Safety Guaruntee
* Erasure


Positive Community Response
===========================
**Type Safety**

ClassCastException


Positive Community Response
===========================
**Less explicit casts**

ADD CODE THAT EXPLAINS SLIDE 12


Positive Community Response
===========================

**Encourages Code Reusue**

Instead of having create new classes for each type of object.

Instead you can create one genericed class.

It is more efficient and creates a smaller code base.

If you make a change it is universal.

Negative Community Response
===========================

**Formal Type Parameters**

~~~~~~~~~~~~~~~java
public class example<T>
{
	private T x;
	public example()
	{
		x = new T();
	}
}

~~~~~~~~~~~~~~~~

Negative Community Response
===========================

**Hiearchy of parameterized types**

~~~~~~~~~~~~~~~~~~~java

List<Dog> ls = new ArrayList<Dog>();

ls.add("Dalmation");
ls.add("Lab");

List<Animals> lo = ls; // Throws ERROR

~~~~~~~~~~~~~~~~~~~

Negative Community Respose
==========================

**No Primatives**

~~~~~~~~~~java

List<int> ls = new ArrayList<int>();

~~~~~~~~~~

Adds a layer of inefficency

If you want a list of plain ints you cant have it.

Final Release
=============

Changed java language spec to add c++ style template syntax.

Modified reflextions api to take advatage of generics.

Slide 18
========

Slide 19
========

Conclution
==========





