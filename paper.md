Authors: Nicolas Broeking, Melissa Guba, Josh Rahm
<br>Emails: nicolas.broeking@colorado.edu, melissa.guba@colorado.edu, joshua.rahm@colorado.edu
<br>Date: April 16, 2013


Java - Generic Types
====================

Introduction
------------

Programming languages are always evolving to better suit the needs of modern programmers. Changes in successful programming languages are generally broken up into change proposals. In the case of Java, these change proposals are called Java Specification Requests (JSR) and there is a development and approval process that each must go through. In this paper, we will focus on the proposal to add Generic Types to Java. 


Generic Types
-------------
Generic class types allow a class structure (usually a container class) to be built without specifying the member variable types. This applies to Objects, but not primitive types. If someone were to write a `tuple` class without generic types, they would have to decide if it would be a tuple of Integers, a tuple of Doubles, a tuple of some other type, or a combination thereof. In most cases, a class should have the capability to handle any Object, and handle them all in a similar manner. Without generic types, there must be an implementation of `tuple` for every Object (a list of Integers, a tuple of Doubles, etc). Generic types allow you to create one class `tuple` to handle a generic type, which can specified when the `tuple` is actually used. The following code show the implementation of a class `tuple` in Java, without using Generics: 

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
class tuple1
{
	private Integer x;
	private Integer y;

	tuple1()
	{
		x = 0;
		y = 0;
	}

	public void setx(Integer a)
	{
		x = a;
 	}

	public void sety(Integer a)
	{
		y = a;
	}

	public Integer getx()
	{
		return x;
	}

	public Integer gety()
	{
		return y;
	}
}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
class tuple2
{
	private Integer x;
	private Double y;
	
	tuple2()
	{
		x = 0;
		y = 0.0;
	}
	
	public void setx(Integer a)
	{
		x = a;
 	}

	public void sety(Double a)
	{
		y = a;
	}
	
	public Integer getx()
	{
		return x;
	}

	public Double gety()
	{
		return y;
	}
}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
class tuple3
{
	private Double x;
	private Double y;
	
	tuple3()
	{
		x = 0.0;
		y = 0.0;
	}
	
	public void setx(Double a)
	{
		x = a;
 	}

	public void sety(Double a)
	{
		y = a;
	}
	
	public Double getx()
	{
		return x;
	}

	public Double gety()
	{
		return y;
	}
}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
This example shows only three different combinations, but to fully implement this basic class we would need to create a class representing every possible combination of classes. Suppose there were only 8 object types in Java; there would need to be 64 different tuple classes to accommodate every combination. (This number is actually much bigger since there are more than 8 types of objects in Java). The issues that arise from coding a simple class, like the one in our example, increase many times over for more complicated classes. Generic Types handle this issue by allowing the implementation of one class that can handle any object. Modifying the previous example with the benefit of Generic Types results in the following code:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
class tuple1<A, B>
{
	private A x;
	private B y;

	tuple1()
	{
		x = 0;
		y = 0;
	}

	public void setx(A a)
	{
		x = a;
 	}

	public void sety( B a)
	{
		y = a;
	}

	public A getx()
	{
		return x;
	}

	public B gety()
	{
		return y;
	}
}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
In this implementation, `A` and `B` represent the types for `x` and `y`, respectively. This allows for the object types of `x` and `y` in the tuple to be decided once the tuple is created. The class can now be used in many different situations without having to create more classes. Essentially, Generic types allow for more concise code when implementing classes in Java.

Initiation
----------
A Specification is initiated by a Member of the Java Community Process [2], and approved for development by the responsible Executive Committee. A group of experts is then formed to assist the Spec Lead with the development of the Specification [1]. The Java Specification Request (JSR) for Generic Types in Java was approved on May 17, 1999 [3].

The first draft of the Generic Types Specification calls for Sun Microsystems to include a provision in the Java Runtime Environment to add Generics to the language specification. The argument provided for the addition of generics to the Java programming language is that most of the code is already intrinsically generic but is prone to bugs and type errors because Java does not support generic types.

The proposal for Java generics was built upon two main principles, erasure and a type safety guarantee. Erasure ensures that at compile time the Java byte code has absolutly no generic informaton. This generic information should have been replaced by a parameratized type at compile time. Type safety gaurantee ensures that if code compiles without any warnings, that code is deamed "type safe". This means that a ClassCastException will not be thrown by generic code. [4]

The Java user community was pleased with the proposal of adding Generic Types to the Java programming language because they allow for more simple, concise code, and help prevent common bugs and type errors.

Draft Releases
--------------
The Expert Group develops the Specification through an iterative process, releasing drafts for public review and comments. A formal public review precedes a ballot held by the Executive Committee on whether the JSR should proceed to the Final Release stage. [1]

Changes to the Java Language Specification (JLS) were made in the grammar of the langauge to facilitate C++ style template syntax, but with more advanced features such as polymorphism and generic derivations [3]. Changes to the API were made in the Java Collections Framework (JCF) to include support for Java Generics, and to the Class class to allow for safer reflection. Safer reflection is another implementation type safety, allowing less error-prone code.

Final Release
-------------

In the Final Release stage the Spec Lead submits the Specification to the Program Management Office for publication as the Proposed Final Draft. The Reference Implementation (RI) and Technology Compatibility Kit (TCK) must then be completed, and the RI pass the TCK. The Specification, RI, and TCK are then submitted to the Program Management Office, then to the Expert Committee for final approval [1]. The final release of JSR 14: Adding Generic types to Java, was released on September 30, 2004 [3].

The main benifits that came from adding generic types are type safety, less explicit casts, and encouraged code resuse. Type safety guarantees that when code compiles without warnings, no implicit casts will throw an error. Less explicit casts need to be done because the programmer knows the type of the objects because they are not definined with the generic type. Finally code that uses generics is easier to reuse in many different applications, with less possibility of errors [4].

Although many good things came from the addition of generic types, the community found limitations in the way that Java generics were implemented. The first limitation was with formal type parameters, as shown in this example. The following code is supposed to declare a new object `example` of type T at construction time.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
public class example<T>{
    T thing = new T(); 
}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This implementation is not allowed within Generics because the type T is not declared as a valid Object anywhere. Code that would correctly declare a new object `example` with type T using Generics:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
public class example<T>{
	public T x;
	public example(T a){
		x = a;
	}
}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Another example of a limitation is Given a class called `Animal` that inherits from Object, and another class `Lion` that inherits from Object, it would be logical to allow `Lion` to also inhereit `Animal` (since lions are a subset of animals). The fourth line of the following code is incorrect:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
List<Lion> lion_list = new ArrayList<Lion>();
lion_list.add("simba");
lion_list.add("nala");

List<Animal> animal_list = lion_list; 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The fourth line will cause errors because Generics do not allow such a hierarchy of parameterized types [4]. A more common problem with Generics is that you cannot parameterize a generic type with a primitive type (int, char, etc).

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
List<int> list = new ArrayList<int>();
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

To modify the above code so that it would work, the wrapper `Integer` would have to be used. The wrapper implements the primitive type `int`.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
List<Integer> list = new ArrayList<Integer>();
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

While there are many limitations with the way that Java Generic Types were implemented, they are considered reasonable compared to the improvements they brought to the Java language. 

Maintenance
-----------
Once the Specification has passed through the Final Release stage, it and its RI and TCK are updated in response to ongoing requests for clarification, interpretation, enhancements, and revisions made by Members and commentators. The Expert Committee reviews proposed changes and indicates which can be carried out quickly and easily, and which must be made into a new JSR [1].

There were multiple unexpected benefits of Generic types resulting mainly from erasure. First, all code prior to the release of the JSR was able to remain unchanged because at runtime, code that uses Generic Types in class implementations looks almost identical to code written without Generic Types, since there is no generic byte code. Another benefit is that the volume of byte code does not increase as more parameterized types of the same generic class are created (unlike C++ templates). Finally, when a parameterized version of class `example` is declared, the code of generic class `example` is not needed, again reducing byte code [4].

The release of Generic Types triggered the initiation of another request, for Reified Generics. This request aims to remove the erasure of generic information at runtime, so that Generic code would be easier to write. Since allowing the access of generic information at runtime would remove the backwards compatibility of Generics, the request also includes the option to make code reifiable only where specified. This request is not yet formal, or implemented in Java. [5]

References
----------
[1] The JSR process - http://jcp.org/aboutJava/communityprocess/final/jsr355/JCP-2.9-Final-clean.pdf

[2] Java Community Process - http://jcp.org/en/home/index

[3] Java Generic Types JSR - http://jcp.org/en/jsr/detail?id=14

[4] Limitations and Benefits - http://eyalsch.wordpress.com/tag/jsr-14/

[5] Reified Generics JSR - http://tech.puredanger.com/java7#reified

NOTES
----- 
###Definitions:
Reference Implementation (RI): The prototype or "proof of concept" implementation of a
Specification.

Specification Lead (Spec Lead): The Expert responsible for leading the effort to develop
or make significant revisions to a Specification and for completing the associated
Reference Implementation and Technology Compatibility Kit. A Spec Lead (or the Spec
Lead's host company or organization) must be a Java Community Process Member.

Technology Compatibility Kit (TCK): The suite of tests, tools, and documentation that
allows an organization to determine if its implementation is compliant with the
Specification.
