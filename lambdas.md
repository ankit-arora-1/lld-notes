# Lambdas

## Overview
Lets say I want to create a thread that prints "hello world". The most common way to do is to create a Printer class which implements the Runnable interface. We then provide the method body for the run method that is present in the Runnable method. 
This seems like a lot of work for achieving something simple. 
There is where Lambdas come into the picture. They help us write compact code. 

**Lambdas are anonymous implementation of a single abstract method interface**

If you look at the Runnable interface, it only provides one abstract method: "run". 
Such types of interfaces are called Single Abstract Method interfaces (SAM or Functional Interfaces). 
In Java, we can replace a functional interface with lambdas. 

Refer to this example on [lambda](https://github.com/ankit-arora-1/java-examples/blob/main/src/lambdas/Client.java)
We are passing a lambda expression to the thread constructor instead of defining our own class that implements Runnable. Lambdas are nothing but implementation of methods of SAM without the boilerplate code. 

Lambdas only work for SAM. If there are more than one abstract method in an interface, you can't use lambda expression for those. The reason being that there is no way for Java to know for which method are you trying to provide the implementation if there were more than one methods. 

Here is another example that uses [lambda](https://github.com/ankit-arora-1/java-examples/blob/main/src/lambdas/ComparatorExample.java) It uses comparator to demonstrate lambdas. 
The lambda expression can be further simplified by removing the data types from parameters (Java infers this automatically). We can even remove the curly braces from the method body if there is a single line as well as the "return" keyword (Java automatically returns the value if there are no curly braces present)

## Method reference
Check out this example on lambdas using callables: [Code](https://github.com/ankit-arora-1/java-examples/blob/main/src/lambdas/CallableExample.java)
In certain cases, we can replace lambdas with something called Method Reference where we just need to mention the name of the object (or class if we are working with static methods), followed by "::" and then the name of the method (notice we do not use brackets or pass the parameters. More discussion on this in further sections)

## Custom Function Interface. 
Check out this [example](https://github.com/ankit-arora-1/java-examples/tree/main/src/lambdas/customInterface) for creating our own function interface.
This is the closest Java comes to passing methods as objects. 

At the moment we are passing "MathOperation". But, we can avoid this and directly pass the lambda. Java has created some standard interfaces for us to use in such scenarios. 
One such interface is called "Function". It can be used when we have to pass one parameter and return one value. 
Similarly we have other such standard interfaces. 
Check out this [example](https://github.com/ankit-arora-1/java-examples/blob/main/src/lambdas/customInterface/Client.java) to see the use case of "BiFunctions".
