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
Changed java language spec to add c++ style template syntax.
Modified reflections api to take advatage of generics.

12- Positive Community Response
Type safety means that if the code compiles without warnings, you are gaurteneed that your code will not throw a casting error, unless you explicitly try and cast an object.

13- Positive Community Response
Generic types are all implicit casts. Implicit casts are casts which are safe and assumed by the compiler. With the addition of Generic types there are less explicit casts since object do not have to cast to a specific type to use container type classes.

14- Positive Community Response
Instead of having create new classes for each type of object.
Instead you can create one generic class.
It is more efficient and creates a smaller code base.
If you make a change it is universal.

15- Negative Community Response
Formal Type Parameters - you cannot use "new" because erasure makes it so that the class does not know anything about T at compile time.

16- Negative Community Response
hierarchy of parameterized types - it would be handle if you could make generic type object inherit one another when approporiate, but you cannot

17- Negative Community Response
no primitive types - Adds a layer of inefficency because if you want a list of plain "int"s you cant have it.

18- The JSR Process
While learning about the specific Generics JSR we learned about the Specification process
the process is good because it allows for multiple stages of revision and modification from both experts of the Java language and regular users.

19- Conclusion


20- Sources
The resources were generally easy to find and interpret for information.