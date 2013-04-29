Authors: Nicolas Broeking, Melissa Guba, Josh Rahm
<br>Emails: nicolas.broeking@colorado.edu, melissa.guba@colorado.edu, joshua.rahm@colorado.edu
<br>Date: April 16, 2013


Java - Generic Types
====================

Introduction
------------

Programming languages are always evolving to better suit the needs of modern programmers. Changes in successful programming languages are generally broken up into change proposals. In the case of Java, these change proposals are called Java Specification Requests (JSR). In this paper, we will focus on the proposal to add Generic Types to Java. 


Generic Types
-------------
Generic Class Types are a way for the programmer to build a class structure, usually a container class, and not specify the types of the member variables. A common example of this is if we were to wright a list class. Well you can ask What do you want? A list of Integers, a list of Doubles, or a list of pretty much any Object. For most cases it shouldn't matter what kind of list it is because a list should behave the same way, however if your language doesn't support generic types you have to create a class for each type. So you have to create a list of Integers, and a list of Doubles, even if you don't use both. However, generic types allow you to just create a list of whatever and you can fill in the whatever when you acctually use the list. So instead of creating a huge code base for all kinds of lists you can create just one generic class of a list. 
<br>Generic Types are usful in Java when a programmer wants to have a class that accepts different types. Without Generic Types, the programmer would have to manage a large code base, because each type would need it's own class. For example, a tuple class in Jave implemented without using Generics would have a different class for each combination type: 
<br>
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
This example shows only three different combinations, but to fully implement this basic class we would need to create a class representing every possible combination of classes. If we assume there are only 8 classes in java, which there isn't, but if there were only 8 we would need 64 different tuple classes to accomadate every combination. The issues that arise from coding a simple class, like the one in our example, increase many times over for more complicated classes. Generic Types handle this issue by allowing the implementation of one class that can handle any object. Modifying the previous example with the benefit of Generics results in the following:
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

**summary of first draft of Generic Type specification...**

The first draft of the Generic Types Specification calls for Sun Microsystems to include a provision in the Java Runtime Environment to add Generics to the language specification. The argument provided for the addition of generics to he Java programming language is that most of the code is already intrinsically generic but because Java does not support generic types, the code is prone to bugs and type errors.

The proposal of java generics was built upon two main principles, Erasure and type safety gaurentee. Erasure gives that at compile time the java byte code has absolutly no generic informaton at all. All of the generic information is removed and replaced by the parameratized type at compile time. The type safety gaurentee, gaurentees if the code compiles without any warnings then the code is deamed "type safe". This means that the ClassCastException will not be thrown by the generic code. [4]

**examples of community reactions to the proposal...**

The community overall was very pleased with adding generics to the java programming language because generic types in java were in high demand.

Draft Releases
--------------
The Expert Group develops the Specification through an iterative process, releasing drafts for public review and comments. A formal public review precedes a ballot held by the Executive Committee on whether the JSR should proceed to the Final Release stage. [1]

**how the proposal was changed...**

<br>**(need info here)**


Final Release
-------------

In the Final Release stage the Spec Lead submits the Specification to the Program Management Office for publication as the Proposed Final Draft. The Reference Implementation (RI) and Technology Compatibility Kit (TCK) must then be completed, and the RI pass the TCK. The Specification, RI, and TCK are then submitted to the Program Management Office, then to the Expert Committee for final approval. [1] 

Changes to the Java Language Specification (JLS) include changes in the grammar of the langauge to facilitate C++-style template syntax, but with more advanced features such as polymorphism and generic derivations.[3]

Changes to API include changes in the Java Collections Framework (JCF) to include support for Java Generics, and to the Class class to allow for safer reflection.

**When was it released?***

The Final release of JSR 14: Adding generic types to java was released on September 30, 2004 [3]

The three main benifits that came out of adding generic types is Type Safety, Less explicit casts, More declariative API's, and encourages code reuse. Type Safety added the gaurentee that if the code compiles without warnings then no implicit casts will throw an error. Less explicit casts need to be done because the programmer knows the type of the objects because they are not definined with the generic type. Finally with the addition of generic types there is a greater ability to reuse code which will lead to fewer bugs. [4]

Although many good things came out of adding generic types the community found limitations with the way java generics was done. The first limitation was with formal type parameters.

~~~~~~java
public class nicsClass <T>
{
    T obj = new T() ; 
}
~~~~~~

This is not allowed because T has no code for creating T because all that information is erased at compile time. The next limitation is that there is no hierarchy of paramaterized types. If we have a class called nicsClass that enherits from object. If we use a generic class parameterized with nicsClass then we can not add, remove, assign or anything with the same class parameterized to Object or vise versa. For example the following is not allowed.[4]

~~~~~~~java
List<String> ls = new ArrayList<String>();
ls.add("one");
ls.add("two");
List<Object> lo = ls; //Illegal
lo.add(new Integer(3)); 
~~~~~~~~~~

Another huge drawback is you can not paramaterize a generic type with a primitive type.

~~~~~~~~java

List<int> ls = new ArrayList<ints>();

~~~~~~~~

This is not allowed.

While there are other limitations with the way java generics were implemented. They are a very small amount compared to the improvements that they brought to the java language. 

Maintenance
-----------
Once the Specification has passed through the Final Release stage, it and its RI and TCK are updated in response to ongoing requests for clarification, interpretation, enhancements, and revisions made by Members and commentators. The Expert Committee reviews proposed changes and indicates which can be carried out quickly and easily, and which must be made into a new JSR. [1]

**unexpected benefits of Generic Types...**

Three unexpected benefits of Generic types were brought because of one of the principles of creation, erasure. The benefits being:

1. All code prior the the release of the jsr can remain unchanged because at runtime there is no generic byte code.
2. When we declair a parameterized version of class C we don't need the code of generic class C.
3. The volume of the byte code does not increase as we create more parameterized types of the same generic class.


**examples of new JSR's that have resulted from the Generic Types JSR...**

The only request that came from this one is a in the works request called reilified generics. This request aims to remove the premis erasure and not erase the generic information. However this is not a formal request yet and the request is a work in progress. [5]

References
----------
**(Put links here with a note about what info was gotten from it, so fancy citations can be added later)**

[1] The JSR process - http://jcp.org/aboutJava/communityprocess/final/jsr355/JCP-2.9-Final-clean.pdf

[2] Java Community Process - http://jcp.org/en/home/index

[3] JSR for java generics - http://jcp.org/en/jsr/detail?id=14

[4] Limitations - http://eyalsch.wordpress.com/tag/jsr-14/

[5] other JSR - http://tech.puredanger.com/java7#reified

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
