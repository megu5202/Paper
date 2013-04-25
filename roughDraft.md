Written By: Nicolas Broeking, Josh Rahm, Melissa Guba <br>
Emails: nicolas.broeking@colorado.edu, joshua.rahm@colorado.edu, "Need Other Emails" <br>
Written On: April 16, 2013 <br>

Java Generics
=============

<!--- Are you sure this is the correct information? Generics were not introduced into Java until version 1.5, which was released in 2004, a solid 2 releases after 1999 -->

Once the Java Specification Request is approved the community. notifies the Spec Lead to form the expert group and to create the community draft. The community draft is a document dedicated to do something that I have no idea. "Need the rest of the process"

Generic Types in Java fixed the problem that if programmers wanted to have a class that accepted different types they had to manage a large code base because they had to write the code separately for each class. For example: If we were writing a tuple class in Java we would have to maintain a different class for each combination type such as: <br>

~~~Java
class tuple1
{
	private int x;
	private int y;
	tuple1()
	{
		x = 0;
		y = 0;
	}
	public void setx(int a)
 	{
		x = a;
 	}
	public void sety( int a)
	{
		y = a;
	}
	public int getx()
	{
		return x;
	}
	public int gety()
	{
		return y;
	}
}
~~~
<br>
~~~Java
class tuple2
{
	private int x;
	private char y;
	tuple1()
	{
		x = 0;
		y = 0;
	}
	public void setx(int a)
 	{
		x = a;
 	}
	public void sety( char a)
	{
		y = a;
	}
	public int getx()
	{
		return x;
	}
	public char gety()
	{
		return y;
	}
}
~~~
<br>
This is just an example of two different combinations but for just this basic class we would need every combination and if we just worried about the 8 primitive types we would have to manage 64 different classes. "Check math" For much more complicated classes this would become even more of a nightmare. So in order to solve this the JSR suggested generic types so instead of having to manage 64+ classes we would only need to make one generic class that looked like:

~~~Java
class tuple1<A,B>
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
~~~

This allows this class to be able to keep any tuple of type(x) = A and type(y) = B. So instead of keeping track of 64 classes. We just need to keep track of 1. The people at Sun Microsystems realized the need for this change and so they submitted the JSR. After going through the process "Still need to know the process" the vote passed unanimously and Java officially added generic types to the programming language on September 30, 2004. 



Who Was Against It?
-------------------

At the introduction **(which introduction? when Generics were accepted and incorporated into Java or when the first JSR was released?)** of generics there was a heated backlash among the community. The developers needed to find a way to create a generic interface that allowed backwards compatibility with the plethora of existing Java code, and avoid the C++ template debacle. **(why was there a C++ debacle? instead of saying just "there was one" say what it was)**. Generics was the answer.

However, the Java community did not completely accept generics. Arguments against included that the introduction of generics compromised the elegance of language because of the extra syntax required to use them. Some animosity stemmed from the potential abuse of generics in Java similar to the extensive use of templates in C++, however a major difference being that Java does not allow default parameters or typedefs, which would make generics even more verbose.

In addition to the extra verbosity, another main complaint of generics is that the type information is lost at compile time. The issue is that when there is no runtime enforcement of these types, there can be issues with runtime binding if, for example, a binary file was hot swapped with a different type, there would be no way to check it during runtime, and this could cause some unexplainable errors.

Another main complaint stemming from the use of generics is that they were never well defined since it is impossible to use primitive data types with them. Since Java may not use primitives with their types, there is an extra overhead introduced with the autoboxing of types and frequent copying from stack to heap and increased garbage collection requirement.

Arguments For
-------------

The arguments for adding generics to Java are obvious. Generics allow for reasonable flexibility under the type safety that Java provides. With generics, Lists and other collections don't have to store a general object, they can store a specific type of object which, in turn allows for Java to leverage it's compile time type checking to ensure that the correct class types is being casted.

Community Reactions:
-------------------
Negative:
- "generics compromise the elegance of the language"
- "potential abuse of generics like the extensive use of templates in C++", why is this bad?
- "type information lost at compile time" example? 
- "generics were never well defined" becuase you cannot use them with primitive data types.

Positive:
- "allow reasonable flexibility under type safety" how?



Initiation
----------
A Specification is initiated by a Member of the Java Community Process [2], and approved for development by the responsible Executvie Committee. A group of experts is then formed to assist the Spec Lead with the development of the Specification [1]. The Java Specification Request (JSR) for Generic Types in Java was approved on May 17, 1999 ***(source?)***.

**summary of first draft of Generic Type specification...**
<br>**(need info here)**

**examples of community reactions...**
<br>**(need info here)**


Draft Releases
--------------
The Expert Group develops the Specification through an iterative process, releasing drafts for public review and comments. A formal public review precedes a ballot held by the Executive Committee on whether the JSR should proced to the Final Release stage. [1]

**how the proposal was changed...**
<br>**(need info here)**


Final Release
-------------
In the Final Release stage the Spec Lead submits the Specification to the Program Management Office for publication as the Proposed Final Draft. The Reference Implementation (RI) and Technology Compatibility Kit (TCK) must then be completed, and the RI pass the TCK. The Specification, RI, and TCK are then submitted to the Program Management Office, then to the Expert Committee for final approval. [1] 

**when the final proposal was accepted...September 30, 2004 (source?)**

**what the final accepted form of the proposal was...**
<br>**(need info here)**


Maintenance
-----------
Once the Specification has passed through the Final Release stage, it and its RI and TCK are updated in response to ongoing requests for clarification, interpretation, enhancements, and revisions made by Members and commentators. The Expert Committee reviews proposed cahnges and indicates which can be carried out quickly and easily, and which must be made into a new JSR. [1]

**unexpected benefits of Generic Types...**
<br>**(need info here)**

**examples of requests for clarification, interpretation, or enhancements to Generic Types...**
<br>**(need info here)**

**examples of new JSR's that have resulted from the Generic Types JSR...**
<br>**(need info here)**



References
----------
**(Put links here with a note about what info was gotten from it, so fancy citations can be added later)**

[1] The JSR process - http://jcp.org/aboutJava/communityprocess/final/jsr355/JCP-2.9-Final-clean.pdf
<br>[2] Java Community Process - http://jcp.org/en/home/index


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
