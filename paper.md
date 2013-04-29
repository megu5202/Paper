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
Generic class types allow a class structure (usually a container class) to be built without specifying the member variable types. If someone were to write a `list` class without generic types, they would have to decide if it would be a list of Integers, a list of Doubles, or a list of some other type. In most cases, a class should have the capability to handle any data type or Object, and handle them all in a similar manner. Without generic types, there must be an implementation of `list` for every data type (a list of Integers, a list of Doubles, etc). Generic types allow you to create one class `list` to handle a generic type, which can specified when the `list` is actually used. Essentially, generic types allow for more concise code when implementing classes in Java.

Generic Types are usful in Java when a programmer wants to have a class that accepts different types. Without Generic Types, the programmer would have to manage a large code base, because each type would need it's own class. For example, a tuple class in Jave implemented without using Generics would have a different class for each combination type: 

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
This example shows only three different combinations, but to fully implement this basic class we would need to create a class representing every possible combination of classes. Suppose there were only 8 object types in Java; there would need to be 64 different tuple classes to accomadate every combination. (This number is actually much bigger since there are more than 8 types of objects in Java). The issues that arise from coding a simple class, like the one in our example, increase many times over for more complicated classes. Generic Types handle this issue by allowing the implementation of one class that can handle any object. Modifying the previous example with the benefit of Generic Types results in the following code:
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
In this implementation, `A` and `B` represent the types for `x` and `y`, respectively. This allows for the types of `x` and `y` in the tuple to be decided once the tuple is created. This allows for the use of the class in many different situations without having to create more classes. 

Initiation
----------
A Specification is initiated by a Member of the Java Community Process [2], and approved for development by the responsible Executive Committee. A group of experts is then formed to assist the Spec Lead with the development of the Specification [1]. The Java Specification Request (JSR) for Generic Types in Java was approved on May 17, 1999 [3].

The first draft of the Generic Types Specification calls for Sun Microsystems to include a provision in the Java Runtime Environment to add Generics to the language specification. The argument provided for the addition of generics to the Java programming language is that most of the code is already intrinsically generic but is prone to bugs and type errors because Java does not support generic types.

The proposal for Java generics was built upon two main principles, erasure and a type safety guarantee. Erasure ensures that at compile time the Java byte code has absolutly no generic informaton. This generic information should have been replaced by a parameratized type at compile time. Type safety gaurantee ensures that if code compiles without any warnings, that code is deamed "type safe". This means that a ClassCastException will not be thrown by generic code. [4]

The Java user community was pleased with the proposal of adding Generic Types to the Java programming language because they allow for more simple, concise code, and help prevent common bugs and type errors.

Draft Releases
--------------
The Expert Group develops the Specification through an iterative process, releasing drafts for public review and comments. A formal public review precedes a ballot held by the Executive Committee on whether the JSR should proceed to the Final Release stage. [1]

Changes to the Java Language Specification (JLS) were made in the grammar of the langauge to facilitate C++ style template syntax, but with more advanced features such as polymorphism and generic derivations [3]. Changes to the API were made in the Java Collections Framework (JCF) to include support for Java Generics, and to the Class class to allow for safer reflection. **what does this mean?**

Final Release
-------------

In the Final Release stage the Spec Lead submits the Specification to the Program Management Office for publication as the Proposed Final Draft. The Reference Implementation (RI) and Technology Compatibility Kit (TCK) must then be completed, and the RI pass the TCK. The Specification, RI, and TCK are then submitted to the Program Management Office, then to the Expert Committee for final approval [1]. The final release of JSR 14: Adding Generic types to Java, was released on September 30, 2004 [3].

The main benifits that came from adding generic types are type safety, less explicit casts, more declariative API's, and encouraged code resuse. Type safety guarantees that when code compiles without warnings, no implicit casts will throw an error. Less explicit casts need to be done because the programmer knows the type of the objects because they are not definined with the generic type. **More declaritive API's, what do they do?**. Finally code that uses generics is easier to reuse in many different applications, with less possibility of errors [4].

Although many good things came from the addition of generic types, the community found limitations in the way that Java generics were implemented. The first limitation was with formal type parameters, as shown in this example. **What is the following code doing, or what is it supposed to do, and what is it actually doing?**

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
public class example<T>{
    T obj = new T() ; 
}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This implementation is not allowed since all the information required to create T is erased at compile time. Another limitation here is that there is no hierarchy of parameterized types. If we have a class called `example` that inherits from object. **what is inheriting from object?** If we use a generic class parameterized with `example` then we can not add, remove, assign or anything with the same class parameterized to Object or vise versa. For example the following is not allowed.[4] **What is the following code doing?**

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
List<String> ls = new ArrayList<String>();
ls.add("one");
ls.add("two");
List<Object> lo = ls; //Illegal
lo.add(new Integer(3)); 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Another huge drawback is you can not parameterize a generic type with a primitive type. **What is the following code doing?**

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
List<int> ls = new ArrayList<ints>();
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This is not allowed. **is there a reason why it is not allowed?**

While there are limitations with the way that Java Generic Types were implemented, they are reasonable compared to the improvements they brought to the Java language. 

Maintenance
-----------
Once the Specification has passed through the Final Release stage, it and its RI and TCK are updated in response to ongoing requests for clarification, interpretation, enhancements, and revisions made by Members and commentators. The Expert Committee reviews proposed changes and indicates which can be carried out quickly and easily, and which must be made into a new JSR. [1]

Some unexpected benefits of Generic types resulted from erasure, one of the principles of creation **creation of what?**. These benefits include:

1. All code prior to the release of the JSR can remain unchanged because at runtime code that uses Generic Types in class implementation looks almost identical to code written without Generic Types, since there is no generic byte code.
2. When a parameterized version of class C is declared, the code of generic class C is not needed. **why?**
3. The volume of byte code does not increase as more parameterized types of the same generic class are created.

The release of Generic Types triggered the initiation of another request, for Reified Generics. This request aims to remove the erasure of generic information at runtime, so that Generic code would be easier to write. Since allowing the access of generic information at runtime would remove the backwards compatibility of Generics, the request also includes the option to make code reifiable only where specified. This request is not yet formal, or implemented in Java. [5]

References
----------
[1] The JSR process - http://jcp.org/aboutJava/communityprocess/final/jsr355/JCP-2.9-Final-clean.pdf

[2] Java Community Process - http://jcp.org/en/home/index

[3] JSR for Java Generic Types - http://jcp.org/en/jsr/detail?id=14

[4] Limitations - http://eyalsch.wordpress.com/tag/jsr-14/

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
