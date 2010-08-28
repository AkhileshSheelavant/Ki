    Ki Framework
    
    -- A Statechart Framework for Sproutcore

#Overview

Ki is a statechart framework that supports:

  * State Hierarchy - nesting of states
  * State Orthogonality - state independence (concurrency)
  * State Clustering - grouping states together within a state 
  * Asynchronous State Transitioning - allow for asynchronous actions during a state transition process
  * Module Design - building states independently that can then be connected and reused within a statechart
  
The framework's design was closely based on David Harel's original paper ["Statecharts: A Visual Formalism For Complex Systems"](http://www.wisdom.weizmann.ac.il/~harel/papers/Statecharts.pdf).

#Why Use Statecharts?

In most applications that react to external and internal asynchronous events, some form of states are used to 
help manage when an action can respond to those incoming events. Usually these states are represented as kinds of
variables within objects or module whose value is checked to determine if a constraint has been met.
The problem with states that are built as such are the following:

  * The actions that rely on the state variables are spread throughout the system and not 
    centralized with a single entity, such as the state or states they use
  * States represented as simple variables are difficult to test as independent entities
  * States that are independent of or dependent on other states are not represented explicitly, but, 
    rather, buried within statements of code
  * Transitioning between states is often not done in a centralized and consistent manner
  * Modularizing and being able to reuse state logic is often error prone and not done in a consistent manner
  
Ki resolves these issues and thereby helps make your state logic more maintainable, testable, and easier to manage. 

#Some Background on Statecharts

David Harel originally developed the idea of statecharts back in the early 80s while working on a complex application for the 
Israel Aircraft Industries. Given the complexity of the system and the number of events the system had
to react to, Harel attempted to make use of traditional state transition diagrams to explicitly design how the 
system's states would react to events and transition to other states. However, trying to use a tradition approach to 
representing finite states during the design process led to a few problems. 

First, a small change to the system would often represent a large change to the state transition diagram, and, ultimately, 
would lead to exponential growth. This made the state transition diagrams difficult if not
impossible to maintain and manage. Next, there was no method of being able to abstract away details. No abstraction 
meant there was no method of being able to zoom in and out of the state transition diagrams. State transition diagrams were 
also not well suited to depict how a group of states were dependent on a common state or states or how states were independent 
(orthogonal) of one another. Finally, given that state transition diagrams were drawn on paper, there was no way to economically represent 
states and state transitions in order to conserve space.   

Through various experimentation while working on the application, Harel and a team of others worked on new approaches 
to address the problems with traditional state transition diagrams. This eventually led to a new way of depicting, managing,
and maintaining an application's state architecture: Statecharts.  

Statechart diagrams are able to address the shortcomings of traditional state transition diagrams. They allowed states to be grouped
together and placed with a parent state. Grouping of states into a common parent state also allowed for abstraction. 
In addition, grouping states into a common parent state meant that the number of state transitions could be reduced.
States that were independent of each other could be depicted in statecharts with minimal effort. 

This new approach of depicting states meant that diagrams could now be properly managed for complex systems and would not
grow or change exponentially in size based on small changes to the system. Another benefit of statecharts was its 
formal and precise way of describing states, but also allowing for relative ease of analyzing the diagrams by people who 
were not experts of statecharts.           
    
    
  