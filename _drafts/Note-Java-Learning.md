---
layout: post
title: "Java"
published: false
---

"Write once run anywhere" (WORA) that is Java tagline or concept to create an application machine/OS agnostic. The idea is you only write code once for all machine/os environment wether it's desktop, mobile or any devices with only one condition that is the machine should have Java Virtual Machine (JVM) running. 

Java is an Object Oriented Programming (OOP) Language. With this approach, (almost) everything in Java is an object while it still have some primitives, Java make some significant difference from procedural languages. In Java all procedure (method) should live in a class. Variables or procedure outside class is prohibited. What about global variable? well, global variable is an EVIL dinosaur! stop using it or rather wrap all of it in a public class.

Java is case sensitive and strict typing meaning that all variables must have specific type. There is instance variables, class variables and local variables.

Instance variable is variable that the value can be different in one and another of the instances of the class (objects). In contrary, class variables is variable that the value is always the same on every instance of the class (objects). 

Local variables is variables that live under the methods of the class. Instance varialbes got iniated and can be used instanly after you declared it. But local variables needs to be explicitely iniated. You'll have compiler error wher using a local variables that haven't be iniated.

Method arguments act like local variables so it needs to be assigned and that is why Java will throw an error if you try to call a method with different number or type of parameters. If a method have 3 arguments then it should be passed EXACTLY 3 parameters with the same order and types. Java always pass everything as a (copy) value to method arguments.

at least one main method: public static void main(String[] args);

Unique:
- boolean can ONLY have either true of false.
- filename = class name (exactly)
- compile .java to .class with javac run .class with java
