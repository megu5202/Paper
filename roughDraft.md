Written By: Nicolas Broeking, Josh Rahm, Melissa Guba <br>
Emails: nicolas.broeking@colorado.edu, "Need Other Emails" <br>
Written On: April 16, 2013 <br>

Java Generics
=============

In may 1999 the JSR to add Generic Types to the java programming language was approved May 17, 1999. Once the Java Specification Request is approved the community notifiys the Spec Lead to form the expert group and to create the community draft. The community draft is a document dedicated to do something that I have no idea. "Need the rest of the process"

Generic Types in java fixed the problem that if programmers wanted to have a class that accepted different types they had to manage a large code base because they had to write the code seperatly for each class. For example: If we were writing a tuple class in java we would have to maintain a different class for each combination type such as: <br>
~~~Java
Class tuple1
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
