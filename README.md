# Solid principles

## S.O.L.I.D is the acronym for five principles of java. They are:

### S: Single responsibility principle
### O: Open-closed principle
### L: Liskov substitution principle
### I: Interface segregation principle
### D: Dependency inversion principle

![sdfg](https://user-images.githubusercontent.com/54953508/123519113-23aa4a80-d6cb-11eb-8906-2063b91b3ba5.png)


# Single-responsibility principle
## “ A class should have one, and only one, reason to change”
#### According to single-responsibility principle a class that you write should have one and only one reason to change. This simply means, a class should be created with only one aim. This however does not imply you should write only one method in your class rather, all the properties of your class should point to a single goal.


# Open-closed principle
## “Classes should be open for extension, but closed for modifications.”

### Imagine, in your application, you have already written a class Person as shown below
![a](https://user-images.githubusercontent.com/54953508/123518535-1d669f00-d6c8-11eb-9bc1-4d31b9d59eff.png)
### Now after some months your code grows incrementally and for some use case you are dealing with some data relating to engineers. So now if you go and add some more properties to the person class say yearsOfExperience and domain, so that you can reuse the person class itself for engineers too, then you are violating open-closed principle. Instead, in such a scenario write a new class called engineer and extend the person class.

![b](https://user-images.githubusercontent.com/54953508/123518602-6caccf80-d6c8-11eb-8830-40002386af40.png)

# Liskov Substitution Principle
## “Derived classes should be able to substitute their base classes without the behavior of your code changing.”
### Liskov Substitution Principle — is one of the SOLID principles defined by Barbara Liskov. This principle is based on the parent-child relationship. It says objects of child classes should be capable to replace their super class objects. That requires the objects of your subclasses to behave in the same way as the objects of your superclass.
### A popular real life example to explain LSP is the bulb analogy. In this example in the family of bulbs, considering the old filament bulb to be a parent of all bulb types and a CFL bulb is a child of the same family inherited from it.
### When one replaces a failed filament bulb with a CFL, in other words in programming terms substitutes the old with the new, it must provide light that is provided by the old bulb, in other words works without affecting correctness or functionality (provides a constant light in the house). In the preceding example the substitution worked perfectly since there is no modification in functionality.
### But if one replaces it with a decoration bulb then we can imagine correctness or functionality (provides a constant light in the house)of the parent is not served here and LSP is violated.

# Interface segregation principle
## “Client should never be forced to depend on an interface they do not use.”
### The Interface Segregation Principle (ISP) states that a client should not be exposed to methods it doesn’t need. Declaring methods in an interface that the client doesn’t need pollutes the interface and leads to a “bulky” or “fat” interface.
### Imagine we have an interface called Employee, which would have methods such as doCoding, recruit, processPayment, clean, trainNewComers, etc. Now, If we were to create a Developer class, we are forced to implement all these methods even though a developer class has nothing to do with jobs like recruiting , cleaning etc. This interface violates the Interface segregation principle.
### To solve these problems let us refractor our code as per Interface segregation principle. We can refactor our code to have separate interfaces for developer, recruiter, accountant, janitor, trainer etc. each with only appropriate methods.
### Developer - doCoding()
### Recruiter - recruit()
### Accountant - processPayment()
### Janitor - clean()
### Now your code has become cleaner.
### By violating the ISP, we face the following problems in our code:
### Client developers are confused by the methods they don’t need.
### Maintenance becomes harder because of side effects: a change in an interface forces us to change classes that don’t implement the interface.
### So next time when you code make sure you don’t violate ISP by adding methods to existing interfaces that the clients don’t need.

# Dependency inversion Principle (DIP)
## “This principle states that the high-level module must not depend on the low-level module, but they should depend on abstractions”.
### Robert C. Martin’s definition of the Dependency Inversion Principle consists of two parts:
### High-level modules should not depend on low-level modules. Both should depend on abstractions.
### Abstractions should not depend on details. Details should depend on abstractions.
### Let’s take the classical example of a copy module which reads characters from the keyboard and writes them to the output device.
### In a bad design the high level class uses directly and depends heavily on the low level classes. In such a case if we want to change the design to direct the ### output to a new Output device we have to make changes in the Copy method.

## Consider the code snippet below
![c](https://user-images.githubusercontent.com/54953508/123518770-52272600-d6c9-11eb-915e-905c0a96ebc3.jpeg)

### The high-level module copy method now depends on the low-level device.
### Here the copy method reads character from the keyboard and then decides where this character needs to go. If it’s a printer, it writes to the printer. Otherwise, it writes to the device. Now if we want to change the design to direct the output to a new Output device we have to make changes in the Copy method. (Let’s assume that it is a very complex, with a lot of logic and really hard to test).
### Let’s look at an alternate implementation:

![d](https://user-images.githubusercontent.com/54953508/123518802-708d2180-d6c9-11eb-8b9b-a9c587f7e3c3.jpeg)

### Here we have two separate interfaces, one to provide the read() and the other to define the write() methods.
### The responsibility of the copy() method is quite clear here: It reads from the Reader interface and writes whatever it gets to the Writer interface. Copy method now focuses only on the actual operation, and it does so by identifying everything else as its dependencies.
## Wrapping Up
### S.O.L.I.D principles helps you to keep Code smells away and will make your codebase maintainable and expandable. So friends be solid on S.O.L.I.D principles. Thank you for making it to the end !



