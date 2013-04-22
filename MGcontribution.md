Written By: Nicolas Broeking, Josh Rahm, Melissa Guba <br>
Emails: nicolas.broeking@colorado.edu, melissa.guba@colorado.edu <br>
Written On: April 16, 2013 <br>


HEY NIC - I split the paper up into sections, and said what each section should have in it (based on the rubric and stuff on piazza), gave my best go at formatting, and took the information you wrote in roughDraft.md and used it where it made sense in here, and made it look nicer. Since I didn't want to just delete all your stuff and I still have no idea how GitHub pull requests work, I figured you could just copy and paste this over to the roughDraft if you like how everything looks and sounds. I also made notes and stuff bold for now so they are a little easier to pick out.
thats all for now,
melissa


Java - Generic Types
====================

Introduction
------------

Programming languages are always evolving to better suit the needs of modern programmers. Changes in successful programming languages are generally broken up into change proposals. In the case of Java, these change proposals are called Java Specification Requests (JSR). In this paper, we will focus on the proposal to add Generic Types to Java. 


Generic Types
-------------
**Generic Types are...**
**(need info here)**

They are used for... (**anything else to add to this?**)
Generic Types are usful in Java when a programmer wants to have a class that accepts different types. Without Generic Types, the programmer would have to manage a large code base, because each type would need it's own class. For example, a tuple class in Jave implemented without using Generics would have a different class for each combination type: <br>
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
class tuple1{
	private int x;
	private int y;

	tuple1(){
		x = 0;
		y = 0;
	}

	public void setx(int a){
		x = a;
 	}

	public void sety(int a){
		y = a;
	}

	public int getx(){
		return x;
	}

	public int gety(){
		return y;
	}
}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~<br>
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
class tuple2{
	private int x;
	private double y;
	
	tuple2(){
		x = 0;
		y = 0.0;
	}
	
	public void setx(int a){
		x = a;
 	}

	public void sety(double a){
		y = a;
	}
	
	public int getx(){
		return x;
	}

	public double gety(){
		return y;
	}
}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~<br>
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
class tuple3{
	private double x;
	private double y;
	
	tuple3(){
		x = 0.0;
		y = 0.0;
	}
	
	public void setx(double a){
		x = a;
 	}

	public void sety(double a){
		y = a;
	}
	
	public double getx(){
		return x;
	}

	public double gety(){
		return y;
	}
}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~<br>
This example shows only three different combinations, but to fully implement this basic class we would need every combination of at least the 8 primitive types (**list the types**), resulting in 64 different combinations, thus 64 separate classes to code and manage (**check math**). The issues that arise from coding a simple class, like the one in our example, increase many times over for more complicated classes. Generic Types handle this issue by allowing the implementation of one class that can handle any type, and all 64 (**check math**) combinations. Modifying the previous example with the benefit of Generics results in the following: <br>
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~java
class tuple1<A, B>{
	private A x;
	private B y;

	tuple1(){
		x = 0;
		y = 0;
	}

	public void setx(A a){
		x = a;
 	}

	public void sety( B a){
		y = a;
	}

	public A getx(){
		return x;
	}

	public B gety(){
		return y;
	}
}
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~<br>
In this implementation, `A` and `B` represent the types for `x` and `y`, respectively. This allows for the types of `x` and `y` in the tuple to be decided once the tuple is created. Consequently, there can be separate people developing the implementation of the tuple, and using a tuple in their own code, and they do not have to worry about who is changing what as long as they both are aware there are two variables (`x` and `y`, in our example) and that those variables have some type `A` and `B`.



Initiation
----------
A Specification is initiated by a Member of the Java Community Process [2], and approved for development by the responsible Executvie Committee. A group of experts is then formed to assist the Spec Lead with the development of the Specification [1]. The Java Specification Request (JSR) for Generic Types in Java was approved on May 17, 1999 [source?].

**summary of first draft of Generic Type specification...**
**(need info here)

**examples of community reactions...**
**(need info here)**


Draft Releases
--------------
The Expert Group develops the Specification through an iterative process, releasing drafts for public review and comments. A formal public review precedes a ballot held by the Executive Committee on whether the JSR should proced to the Final Release stage. [1]

**how the proposal was changed...**
**(need info here)**


Final Release
-------------
In the Final Release stage the Spec Lead submits the Specification to the Program Management Office for publication as the Proposed Final Draft. The Reference Implementation (RI) and Technology Compatibility Kit (TCK) must then be completed, and the RI pass the TCK. The Specification, RI, and TCK are then submitted to the Program Management Office, then to the Expert Committee for final approval. [1] 

**when the final proposal was accepted...September 30, 2004 [source?]**

**what the final accepted form of the proposal was...**
**(need info here)**


Maintenance
-----------
Once the Specification has passed through the Final Release stage, it and its RI and TCK are updated in response to ongoing requests for clarification, interpretation, enhancements, and revisions made by Members and commentators. The Expert Committee reviews proposed cahnges and indicates which can be carried out quickly and easily, and which must be made into a new JSR. [1]

**unexpected benefits of Generic Types...**
**(need info here)**

**examples of requests for clarification, interpretation, or enhancements to Generic Types...**
**(need info here)**

**examples of new JSR's that have resulted from the Generic Types JSR...**
**(need info here)**



References
----------
**(Put links here with a note about what info was gotten from it, so fancy citations can be added later)**

[1] The JSR process - http://jcp.org/aboutJava/communityprocess/final/jsr355/JCP-2.9-Final-clean.pdf
[2] Java Community Process - http://jcp.org/en/home/index


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