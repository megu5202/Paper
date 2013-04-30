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



Final Release
=============
SOMETHING


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
**Encouraged Code Reusue**

ADD CODE THAT IS AN EXAMPLE OF REUSABLE CODE


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
List<Dog> dog_list = new ArrayList<Dog>();

dog_list.add("Dalmation");
dog_list.add("Lab");

List<Animals> animal_list = dog_list; // ERROR
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Negative Community Respose
==========================
**No Primitives**

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
List<int> list = new ArrayList<int>();
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


The JSR Process
===============

Initiation - introduction of problem/idea for improvement
Draft Releases - implementation of specfication is discussed and modifications are made
Final Release - when the specification is introduced into Java
Maintenance - later changes and consequences of the specification


Conclusion
==========

Short note about generics
What we learned about specification process

Resources
=========
The JSR process - http://jcp.org/aboutJava/communityprocess/final/jsr355/JCP-2.9-Final-clean.pdf
Java Community Process - http://jcp.org/en/home/index
Java Generic Types JSR - http://jcp.org/en/jsr/detail?id=14
Limitations and Benefits - http://eyalsch.wordpress.com/tag/jsr-14/
Reified Generics JSR - http://tech.puredanger.com/java7#reified





