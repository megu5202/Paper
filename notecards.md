1- Title

2- What is a Generic Type
Generic types implement a class where the type of the member variables is defined when the object is created.

3- What does this mean?
Lets say we want a tuple class. First we want a tuple of two Integers (5, 3), in this case we would write a tuple class that handles Integers.

4- Integer Tuple class code
Here we have a tuple class that handles Integers. It declares two integers, then has a constructor function.

5- Integer Double class
Lets say that now we want a tuple of two Doubles, we have to write a new Tuple class that handles doubles...

6- Integer Double class code
This tuple class handles Doubles, it declares two doubles, then has a constructor funtion.

7- Generics
Instead of creating yet another tuple class to handle characters, we want a generic class. 
This generic class would allow us to decide the types when we use the tuple.

8- Generic Tuple
Generics allowa us to create this class and then allow us to set A, and B when we create the objects.
This code declares two object of type A and B and then provides a simple constructor.

9- Using Generic Tuple
Instead of using the different tuples we declare the type of the tuple when we are actually using it.

10- Proposal
Sun Microsystems realized the possible benefits of Generic Types and created JSR 14: Adding Generics to the Java Programming Language
They wanted to create a class that allowed for... type safety guaruntee, and erasure


11- Final Release
