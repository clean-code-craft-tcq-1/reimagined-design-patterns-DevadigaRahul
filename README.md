# reimagined-design-patterns

Give a summary description of Four design patterns that you choose from the following design patterns: **Adapter,  Builder, Composite, Decorator, Observer, Interpreter, State, Mediator, Memento, Prototype, Proxy**. In your summaries say:

- what kind of problem(s) you can solve with that pattern and when you use it, maybe with a short example
- how the pattern works, what the basic idea of the pattern is
- what the main advantage and what the the main disadvantage is of using this pattern
- Write a short summary for each of the four patterns, about half a page for each pattern (rather less than more). 

> Do not add diagrams, and do not try to give a complete description of the patterns as found in the books. Rather think of how you would explain the essential ideas of these patterns in a few sentences to a colleague while drinking coffee.

1. Adapter:it is a structural design pattern

    a. what kind of problem(s) you can solve with that pattern and when you use it, maybe with a short example
   - it allows objects with incompatible interfaces to collaborate. 
   - by converting the interface of one class into an interface expected by the clients. 
   - Socket wrenches provide an example of the Adapter. 
     - A socket attaches to a ratchet, 
     - provided that the size of the drive is the same. 
     - Typical drive sizes in the United States are 1/2" and 1/4". 
     - Obviously, a 1/2" drive ratchet will not fit into a 1/4" drive socket unless an adapter is used. 
     - A 1/2" to 1/4" adapter has a 1/2" female connection to fit on the 1/2" drive ratchet, and a 1/4" male connection to fit in the 1/4" drive socket.
    
    b. how the pattern works, what the basic idea of the pattern is
   - Identify the players: 
     - the component(s) that want to be accommodated (i.e. the client), and the component that needs to adapt (i.e. the adaptee).
   - Identify the interface that the client requires.
   - Design a "wrapper" class that can "impedance match" the adaptee to the client.
   - The adapter/wrapper class "has a" instance of the adaptee class.
   - The adapter/wrapper class "maps" the client interface to the adaptee interface.
   - The client uses (is coupled to) the new interface
    
    c. what the main advantage and what the the main disadvantage is of using this pattern  

   - Single Responsibility Principle. 
     - You can separate the interface or data conversion code from the primary business logic of the program.
   - Open/Closed Principle. 
     - You can introduce new types of adapters into the program without breaking the existing client code, as long as they work with the adapters through the client interface.
   - The overall complexity of the code increases because you need to introduce a set of new interfaces and classes. Sometimes it’s simpler just to change the service class so that it matches the rest 

2. Builder:it is a Creational design patterns

    a. what kind of problem(s) you can solve with that pattern and when you use it, maybe with a short example
   - it lets you construct complex objects step by step. 
   - The pattern allows you to produce different types and representations of an object using the same construction code.
   - This pattern is used by fast food restaurants to construct children's meals. 
     - Children's meals typically consist of a main item, a side item, a drink, and a toy (e.g., a hamburger, fries, Coke, and toy dinosaur). 
     - Note that there can be variation in the content of the children's meal, but the construction process is the same. 
     - Whether a customer orders a hamburger, cheeseburger, or chicken, the process is the same. 
     - The employee at the counter directs the crew to assemble a main item, side item, and toy. 
     - These items are then placed in a bag. 
     - The drink is placed in a cup and remains outside of the bag. 
     - This same process is used at competing restaurants.
    
    b. how the pattern works, what the basic idea of the pattern is
   - Decide if a common input and many possible representations (or outputs) is the problem at hand.
   - Encapsulate the parsing of the common input in a Reader class.
   - Design a standard protocol for creating all possible output representations. Capture the steps of this protocol in a Builder interface.
   - Define a Builder derived class for each target representation.
   - The client creates a Reader object and a Builder object, and registers the latter with the former.
   - The client asks the Reader to "construct".
   - The client asks the Builder to return the result.

    c. what the main advantage and what the the main disadvantage is of using this pattern  
   -  You can construct objects step-by-step, defer construction steps or run steps recursively.
   - You can reuse the same construction code when building various representations of products.
   - Single Responsibility Principle. 
     - You can isolate complex construction code from the business logic of the product.
   - The overall complexity of the code increases since the pattern requires creating multiple new classes.

3. Composite :it is a structural design pattern 

    a. what kind of problem(s) you can solve with that pattern and when you use it, maybe with a short example
   - it lets you compose objects into tree structures and then work with these structures as if they were individual objects. 
   - the example :Armies of most countries are structured as hierarchies. 
     - An army consists of several divisions; a division is a set of brigades, and a brigade consists of platoons, which can be broken down into squads. 
     - Finally, a squad is a small group of real soldiers. 
     - Orders are given at the top of the hierarchy and passed down onto each level until every soldier knows what needs to be done.
    
    b. how the pattern works, what the basic idea of the pattern is
   - Ensure that your problem is about representing "whole-part" hierarchical relationships.
   - Consider the heuristic, "Containers that contain containees, each of which could be a container." 
     - For example, "Assemblies that contain components, each of which could be an assembly.
     - " Divide your domain concepts into container classes, and containee classes.
   - Create a "lowest common denominator" interface that makes your containers and containees interchangeable. 
   - It should specify the behavior that needs to be exercised uniformly across all containee and container objects.
   - All container and containee classes declare an "is a" relationship to the interface.
   - All container classes declare a one-to-many "has a" relationship to the interface.
   - Container classes leverage polymorphism to delegate to their containee objects.
   - Child management methods [e.g. addChild(), removeChild()] should normally be defined in the Composite class. 
   - Unfortunately, the desire to treat Leaf and Composite objects uniformly may require that these methods be promoted to the abstract Component class. 
   - See the Gang of Four for a discussion of these "safety" versus "transparency" trade-offs.

    C. what the main advantage and what the the main disadvantage is of using this pattern  
   -  You can work with complex tree structures more conveniently: 
     - use polymorphism and recursion to your advantage.
   -  Open/Closed Principle. 
     - You can introduce new element types into the app without breaking the existing code, which now works with the object tree.
   -  It might be difficult to provide a common interface for classes whose functionality differs too much. 
     - In certain scenarios, you’d need to overgeneralize the component interface, making it harder to comprehend.

4. Decorator: it is also known as a Wrapper, a structural design pattern 

    a. what kind of problem(s) you can solve with that pattern and when you use it, maybe with a short example
   - it lets you attach new behaviors to objects by placing these objects inside special wrapper objects that contain the behaviors.
   - Wearing clothes is an example of using decorators. 
     - When you’re cold, you wrap yourself in a sweater. If you’re still cold with a sweater, you can wear a jacket on top. 
     - If it’s raining, you can put on a raincoat. 
     - All of these garments “extend” your basic behavior but aren’t part of you, and you can easily take off any piece of clothing whenever you don’t need it.
    
    b. how the pattern works, what the basic idea of the pattern is
   - Make sure your business domain can be represented as a primary component with multiple optional layers over it.
   - Figure out what methods are common to both the primary component and the optional layers. 
     - Create a component interface and declare those methods there.
   - Create a concrete component class and define the base behavior in it.
   - Create a base decorator class. It should have a field for storing a reference to a wrapped object. 
     - The field should be declared with the component interface type to allow linking to concrete components as well as decorators. 
     - The base decorator must delegate all work to the wrapped object.
   - Make sure all classes implement the component interface.
   - Create concrete decorators by extending them from the base decorator. 
     - A concrete decorator must execute its behavior before or after the call to the parent method (which always delegates to the wrapped object).
   -  The client code must be responsible for creating decorators and composing them in the way the client needs.

    C. what the main advantage and what the the main disadvantage is of using this pattern  
   -  You can extend an object’s behavior without making a new subclass.
   -  You can add or remove responsibilities from an object at runtime.
   -  You can combine several behaviors by wrapping an object into multiple decorators.
   -  Single Responsibility Principle. 
     - You can divide a monolithic class that implements many possible variants of behavior into several smaller classes.
   -  It’s hard to remove a specific wrapper from the wrappers stack.
   -  It’s hard to implement a decorator in such a way that its behavior doesn’t depend on the order in the decorators stack.
   -  The initial configuration code of layers might look pretty ugly.

