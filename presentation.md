Java Generics ** 1
=============

**Java Generics**

By: Nic Broeking, Melissa Guba, Joshua Rahm

What is a generic type? ** 2
=======================

A Generic Type is a generic class or interface that is parameterized over types.


What does this mean? ** 3
====================

Example: implementation of a tuple class

Tuple of Integers:

(5, 3)

Tuple Class for Integers ** 4
=====================

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
public class Tuple{
	public Integer x;
	public Integer y;

	public IntegerTuple(Integer a, Integer b){
		x = a;
		y = b;
	}
}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Tuple of Double ** 5
===============

Tuple of Doubles:

(5.0, 3.5)


Tuple Class for Doubles ** 6
====================

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
public class DoubleTuple{
	public Double x;
	public Double y;

	public DoubleTuple(Double a, Double b){
		x = a;
		y = b;
	}
}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Generics ** 7 
========

Tuple of Characters:

("a", "b")


A Generic Tuple ** 8
===============

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
public class Tuple<A, B>{
	public A x;
	public B y;

	public Tuple(A a, B b){
		x = a;
		y = b;
	}
}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Using a Generic Tuple ** 9
=====================

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
Tuple<Integer, Integer> tuple1 = new Tuple <Integer, Integer>();
Tuple<Tomato, SuspenspensionBridge> tuple2 = new Tuple<Tomato, SuspenspensionBridge>();
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Proposal ** 10
========

* Type Safety Guaruntee
* Erasure

Erasure
=============
Type parameters are completely
removed by the compiler, and formal
type parameters are replaced by their
bound.

Type Safety Guarantee
===========================
**Type Safety**

ClassCastException

Type Safety Guarantee
---------------------
"If your entire application compiles without warnings,
then it is type-safe."


Positive Community Response
===========================
**Less explicit casts**

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
ArrayList<Integer> array = new ArrayList<Integer>();
array.add(5);
Integer x = array.get(0);

vs

ArrayList array = new ArrayList();
array.add(5);
Integer x = (Integer) array.get(0);

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Positive Community Response
===========================
**Encouraged Code Reusue**


~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
public class Tuple<A, B>{
	public A x;
	public B y;

	public Tuple1(A a, B b){
		x = a;
		y = b;
	}
}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Negative Community Response
===========================
**Formal Type Parameters**

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
public class Example<T>{
	private T x;
	public Example(){
		x = new T();
	}
}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Negative Community Response
===========================
**Hierarchy of parameterized types**

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
List<Dog> doglist = new ArrayList<Dog>();

doglist.add( new Dog("Dalmation") );
doglist.add( new Dog("Lab") );

List<Animals> animallist = doglist; // COMPILE PUKE
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Negative Community Response
==========================
**No Primitives**

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
List<int> list = new ArrayList<int>(); // invalid
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


The JSR Process
===============

Initiation - introduction of problem/idea for improvement

Draft Releases - implementation of specification is discussed and modifications are made

Final Release - when the specification is introduced into Java

Maintenance - later changes and consequences of the specification


Conclusion
==========

Generics revolutionized the Java Programming Language.

They brought a much needed feature to a great language!

Resources
=========
The JSR process - http://jcp.org/aboutJava/communityprocess/final/jsr355/JCP-2.9-Final-clean.pdf

Java Community Process - http://jcp.org/en/home/index

Java Generic Types JSR - http://jcp.org/en/jsr/detail?id=14

Limitations and Benefits - http://eyalsch.wordpress.com/tag/jsr-14/

Reified Generics JSR - http://tech.puredanger.com/java7#reified





