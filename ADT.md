<h1>ABSTRACT DATA TYPES</h1>

<h4>What is an ADT</h4>

*A type in which
	*What the operations of the type are is public
		*That is, public to the client

	*How the type is implemented is private
		*That is, private to the client

*Abstract = irrelevant details are ignored
*The ADT is abstract because how the ADT is implemented is ignored


<h4>ADTs and Program Design</h4>

*ADTs are an important part of bottom up program desgin
*In practice, programs are built using a combination of top down and bottom up approaches:

	*Top down:
		*Decompose problem into subproblems, then decompose subproblems. Repeat until subproblems are simple
		*Structure charts are a common design tool

*Bottom up
	*Design a set of tools and use them to build a solution the problem
	 *The tools are the values and operations of ADTs

*Designing ADTs is an essential part of bottom up design


<h4>ADT Mechanisms in Modern Languages</h4>
Modern languages provide a mechanism for defining ADTs
The mechanism must give a client access to public details and restrict access to private details

Mechanisms in common languages
Ada: package
client sees interface in public part of specification
client can't see implementation in body and private part of specification

Java: class
client can see class name and non-private members
client can't see private members

C++: class
client can see class name and members that follow non-private access specifier
client can't see members that follow private access specifier

C: no ADT implementation mechanism

Others (eg python, perl, ruby, modula 2) use some variant of modules
modules are roughly similar to packages
modules are typically implemented with one file
module is a generic term for a package-like mechanism

Note: A java package does not provide for ADTs. It provides for namespace control by allowing use of the same class name in different contexts (eg java.ship.Deck and java.game.Deck)

ADT: Values and Operations

When we define an ADT, the two items that we define are
The values in the type (ie fields in a record or class)
the set of operations (ie routines/methods) that can be used on values of that type.

It's useful to categorize the operations of an ADT

ADT Operations Categories

Declare a variable of the type
(ie using a type defined in the package)

Allocate a variable of the type
May be done by a declaration
Or may require a special operation (eg new or constructor-like call

Operations on values (ie procedures and functions that have values of the type as parameters):
Query a property of the value or the status of a value or a component of a value
Modify a value (ie through an in/out parameter)
Combining two or more values and return a new value (of the same or different type)
Comparing two or more values
Convert a value to a string
Input/output of values

Iterate through subcomponents (collections only)
Example: Java Iterators
      Tree t = new Tree();
      // Add some elements here
      Iterator i = t.getIterator();
      while i.hasNext()
          S.o.p(i.next())
      

Why are Iterators Important

Code to iterate through collection is independent of the data structure

Iterator can maintain the state of its data structure traversal
Example: recursive routine to print a tree
Recursive routine is easy: traversal and printing are in same routine
Iterator version is harder: traversal and printing are separated.
The iterator must remember the current node and determine the next node!

More Examples of Itereators

As another example, here are Ruby's iterators:
the .each method is normally defined for an ADT
        t = Tree.new
        # Add some elements here

        t.each do |e|
            print e
        end

        for e in t   # Syntactic suger version
            print e
        end
      
One more example: Sather's iterators are very elegant (elts! is defined for most ADTs):
        t: Tree = new Tree();
        -- Add some elements here

        loop
            put(t.elts!)  -- loops understand elts!
        end loop
      

Why We Use ADT's.

ADTs have several benefits:
Simplicity: Client programmer does not have to be concerned with details that underlie the implementation of the ADT (eg keeping track of the front and back of a queue)
High level operations: Design solutions in terms of the problem (ie think in terms of stacks, not arrays and array indices)

Abstractions on top of abstractions (eg stacks of words)

Reliability: user cannot corrupt ADT values

Reliability: encourage reuse of well-tested ADT's

Flexibility for client programmer: can choose from among several implementations of an ADT
Example: array stack for efficient time and space
Or linked stack for flexibility

Independence: separating specification and implementation allow client and ADT to be programmed simultaneously

Independence: ADT programmer can change implementations of ADT without forcing client to change

ADT Design Principle

Parnas Principle: A general for creating ADTs
Maximize Cohesion:
Every ADT has a single, well-defined purpose

Minimize Coupling:
Design classes so that changing one does not break the other.
Minimize reliance of one class on another

Invented by David Parnas