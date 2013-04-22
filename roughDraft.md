Written By: Nicolas Broeking, Josh Rahm, Melissa Guba <br>
Emails: nicolas.broeking@colorado.edu, "Need Other Emails" <br>
Written On: April 16, 2013 <br>

Java Generics
=============

In may 1999 the JSR to add Generic Types to the java programming language was approved May 17, 1999. Once the Java Specification Request is approved the community notifiys the Spec Lead to form the expert group and to create the community draft. The community draft is a document dedicated to do something that I have no idea. "Need the rest of the process"

Generic Types in java fixed the problem that if programmers wanted to have a class that accepted different types they had to manage a large code base because they had to write the code seperatly for each class. For example: If we were writing a tuple class in java we would have to maintain a different class for each combination type such as: <br>
~~~java
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
~~~java
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
This is just an example of two different combinations but for just this basic class we would need every combination and if we just worried about the 8 primitive types we would have to manage 64 different classes. "Check math" For much more complicated classes this would become even more of a nightmere. So in order to solve this the JSR suggestest generic types so instead of having to manage 64+ classes we would only need to make one generic class that looked like:

~~~java
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

This allows this class to be able to keep any tuple of type(x) = A and type(y) = B. So instead of keeping track of 64 classes. We just need to keep track of 1. The people at sun microsystems relized the need for this change and so they submitted the JSR. After going through the process "Still need to know the process" the vote passed unanimisly and java officially added generic types to the programming language on September 30, 2004. 
