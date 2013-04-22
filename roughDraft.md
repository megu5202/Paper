Written By: Nicolas Broeking, Josh Rahm, Melissa Guba <br>
Emails: nicolas.broeking@colorado.edu, "Need Other Emails" <br>
Written On: April 16, 2013 <br>

Java Generics
=============

<!--- Are you sure this is the correct information? Generics were not introduced into Java until version 1.5, which was released in 2004, a solid 2 releases after 1999 -->

In may 1999 a JSR document requested to add Generic Types to the Java programming language was approved May 17, 1999. Once the Java Specification Request is approved the community
notifies the Spec Lead to form the expert group and to create the community draft. The community draft is a document dedicated to do something that I have no idea. "Need the rest of the process"

Generic Types in Java fixed the problem that if programmers wanted to have a class that accepted different types they had to manage a large code base because they had to
write the code separately for each class. For example: If we were writing a tuple class in Java we would have to maintain a different class for each combination type such as: <br>

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
This is just an example of two different combinations but for just this basic class we would need every combination and if we just worried about the 8 primitive
types we would have to manage 64 different classes. "Check math" For much more complicated classes this would become even more of a nightmare. So in order to
solve this the JSR suggested generic types so instead of having to manage 64+ classes we would only need to make one generic class that looked like:

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

This allows this class to be able to keep any tuple of type(x) = A and type(y) = B. So instead of keeping track of 64 classes. We just need to keep track of 1.
The people at Sun Microsystems realized the need for this change and so they submitted the JSR. After going through the process "Still need to know the process" the
vote passed unanimously and Java officially added generic types to the programming language on September 30, 2004. 

Who Was Against It?
===================

At the introduction of generics there was a heated backlash among the community. The developers needed to find a way to create a generic interface that allowed for backwards
compatibility with the plethora of existing Java code while at the same time avoiding the C++ template debacle. Generics was the answer.

However, the Java community did not completely accept generics. Arguments against included that the introduction of generics compromised the elegance of language because of the
extra syntax required to use them. Some animosity stemmed from the potential abuse of generics in Java similar to the extensive use of templates in C++, however a major
difference being that Java does not allow default parameters or typedefs, which would make generics even more verbose.

In addition to the extra verbosity, another main complaint of generics is that the type information is lost at compile time. The issue is that when there is no runtime
enforcement of these types.

Arguments For?
==============

The arguments for adding generics to Java are obvious. Generics allow for reasonable flexibility under the type safety.
