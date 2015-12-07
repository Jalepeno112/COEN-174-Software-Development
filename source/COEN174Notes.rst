COEN 174: Software Development
================================
Fundemental theory of software development: everything can be solved by adding a level of indirection.


Chapter 2: Systems vs Programs
----------------------------------

**2015-09-23**

* How is a system different from a program?

Complexity of the Actual Code
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Systems typically have more depth and breadth than a single program

    - *breadth*: refers to the number and variety of components 
        - more major functionality
            - example: browse web-pages and read e-mail and edit web-pages all in the same place
        - more features within each function
            - example: spam filtering within mail reader, spelling correction
        - more interface features
            - example: fetch mail from a different place, export mail
        - more users
            - not just number of users, but skill level also varies (novice versus experts)
    - *depth*: refers to the complexity and relationship among components
        - more layers of abstraction
        - more linkages between layers
        - more libraries and frameworks being used

Technical Concerns
~~~~~~~~~~~~~~~~~~~~
    - which platform(s) will be used?
    - which language(s) will be used?
    - is a DB required?
    - is it networked?
    - is a configuraton management system required?

Non-engineering aspects
~~~~~~~~~~~~~~~~~~~~~~~~
    - more people and resources to coordinate
    - people with different skills
    - need to impose a team structure

Chapter 6
------------------

Main Points:
    - What are requirements?
    - What are the steps in requirements engineering?
    - What are informal and formal methods of gathering describing and evaluating requirements?

What Are Requirements
~~~~~~~~~~~~~~~~~~~~~
They are statements that describe what the system should/must do.
They *do not* describe how the software is to be constructed.

Top reason for project failure:
    Poorly defined requirements

Top reason for porject success:
    Clearly defined requirements

If some requirements are *missing*, they are *incomplete*.
If they are *conflicting*, then the are *ambiguous*.

Requirements Engineering:
    The process of determining requirements

Requirements engineering involves:
    * talk to the customer about what they want
    * end up with a formal document that the customer can sign off on
    * How to get from point a to point b
        - using a **process**

Requirements Process
^^^^^^^^^^^^^^^^^^^^^^^
A **process** is a framework used to guide system development

It includes:
    - tasks to be performed
    - sequencing of tasks
    - inputs and outputs
    - pre-conditions and post conditions

Example:
    - requirements -> design -> implementation -> testing
    - although in real life, the model is usually not this linear

The requirements process more explicitly is:
    - Elicitation: talk to the customer
        * Talk to the customer about what they want
        * Focus on the *what* not the *how*
        * Focus on high level requriements:
            - deal wtith business concerns
            - communication skills important
            - justification (how will software save money)
            - scope of the project
            - constraints: schedule/cost
            - user characteristics (who will be using the system)
    - Analysis: tabulated/sort/prioritize (i.e. analyze) the data from elicitation
    - Definition, Prototyping, Review
        * Definition: write it up informally
        * Prototyping: build a prototype/mock up to get feedback
        * Review: check it over
    - Specification
    - Agreement

High-level reqs:
    deal with business issues

Low-level reqs:
    more technical than high level reqs

Why do we Need Requriements
^^^^^^^^^^^^^^^^^^^^^^^^^^^^
For acceptance testing, you need requirements so that you know can know if you are delivering the right product
Limit scope crrep.
Planning for training and support.
Scheduling the project.

Competing requirements:
    * Individual functionality versus contrains (reliability, security, performance)
    * Systems with other interfaces (interoperability) versus data and formats
    * Business flow versus user interfaces

Different systems = Different Requirements
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Different systems will generally have different requirements.  Two backup systems could have different requirements and come out as two very different systems.
    * Physical Environment: 
        -where will system run?  one location? several?
    * Interfaces:
        - where is the input coming from?
        - where is the outpt going?
    * Users
        - Who will use the system?  different types? different types?
    * Functionality
        - what will it do?  Contraints on time or space?
    * Documentation
        - what kind? how detailed?
    * Data
        - format? persistent? accuracy?
    * Resources
        - what equipment and personnel are necessary?
    * Security
        - Must access be controlled?  data backed up?
    * Quality Assurance
        - Will the system detect errors?  Mean time to failure?

Requirements Analysis    
^^^^^^^^^^^^^^^^^^^^^^^^^
Organizing and prioritizing the data gathered during the elicitation

.. note::
    Important to ask if the customer is involved in this process

We will find that we are missing some information and other information is condradictory.

Make assumptions (based on experience), document them and then validate them through prototyping

Prioritizing requirements
###########################
Set levels of requirements:
    - absolutetly necessary/critical
    - highly desirable/recommended
    - possible/suggested

Analytical Hierarchy Process (AHP)
###################################
More rigerous approach to prioritizing.
The key idea is that you compare compoenents or requirements pairwise.

    R1  R2  R3
R1  1   3   5  
R2  1/3 1   1/2
R3  1/5 2   1

R1 is 3 times as important as R2, and 5 times as important as R3.

normalize each column (divide each element by the sum so that the sum of each column is 1)

    R1      R2      R3
R1  .65     .5      .77 |   1.92
R2  .22     .17     .08 |   .047
R3  .13     .33     .15 |   .061

Sum each row and then divide each sum by the sum of sums.  Gives you a percentage that each requirement that each has.
R1 is the most important, R3 is the second most important, R2 is the least.

Another example:
    3 requirements (R1, R2, R3)
    R1 is 4x as impoartant as R2 and 2x as imporant as R3
    R3 is 2x as important as R2

        R1  R2  R3
    R1  1   4   2       | R1 is 4R2 and 2R3
    R2  1/4 1   1/2     | R2 is 1/4R2 and 1/2R3
    R3  1/2 2   1       | R3 is 1/2R1 and 2R2

    *normalize, sum each row and then divide the sum of each row by the sum of the sums of each row*
        R1  R2  R3
    R1  4/7 4/7 4/7     | 4/7
    R2  1/7 1/7 1/7     | 1/7
    R3  2/7 2/7 1/7     | 2/7
        -----------------------
        1   1   1       | 1

Requirements Definition, Prototyping, Reviews
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
The customer is involved in all of these steps.

Definition:
    involves writing up the reqs

If we need clarification we can prototype.

Prototypes are common for user interfaces:
    low-fidelity: paper/cards
    high-fidelity: mockup in browser/Visual Basic

Results go through review.

Requirement Specification
^^^^^^^^^^^^^^^^^^^^^^^^^^
Customer is **not** involved in this phase, but thye will sign off on this at the end.

In some orgs:
    - requirements doc:     written for customer
    - requirements spec:    written for engineers/technical teams

.. note::
    Some specification languages are even executable

Requirements Agreement
^^^^^^^^^^^^^^^^^^^^^^
Customer is involved.

This signals that the requirements phase is over.

Analysis models
~~~~~~~~~~~~~~~~
Formal model is used to write-up the results of analysis

Structure analysis:
    Developed in 1960s.

Unified Modeling Language (UML):
    Developed in 1990s.  

How do structured analysis and OO analysis differ?
    Structured analysis considers data and operations seperately; whereas, OO analysis considers them together.

Scenario-based models
^^^^^^^^^^^^^^^^^^^^^^
User satisfaction is key to success of a system.
Therefore models involving the user are usually constructed first.

use-case:
    describes how a user interacts with the system to accomplish some goal or perform something.

The diagram itself is not enough.  We also need narriative:
    - preconditions
    - postconditions
    - actor(s)
    - goal
    - name
    - expectations
    - steps in a  typical sequence

.. note::
    These should only be done in the scope of the system

Example:
    - name:             login
    - precondition:     none
    - postcondition:    user authenticated
    - goal:             authenticate user
    - steps:            1) enter username, 2) enter password, 3)information is submitted, 4) user taken to landing screen
    - exceptions:       username/password incorrect (user will be prompted again)
    - 
Activity Diagrams
^^^^^^^^^^^^^^^^^
Shows the dynamic behavior of the system (or part of the system).  Looks much like a flowchart but also has notation for concurrency

.. image::
    :src: ActivityDigramCake

Swimlane Diagrams
^^^^^^^^^^^^^^^^^^
Activity diagrams but with responsibilities assigned

Place each part of the activity digram in a column and then assign each column to a person.

Database Models
^^^^^^^^^^^^^^^^
Identify data and their relationships.  A *data object* is simply composite information.

Ex:
    object = person
        attribute = first name, last name

Data Flow Diagram (DFD)
########################
Models how data is transformed as it flows through the system.
Can be decomposed heirarchically.

.. image::
    :src: DataFlowDiagram.png

Entity Relationship Diagrams (ERD)
###################################
entities are just objects.

Cardinality:
    Displaying the difference between 1 object and many objects (| for 1, > for many)

Modality:
    Display the difference between optional and mandatory objects (O for optional, | mandatory)

Ex:
    Course |---- [instance of] ------ <class

    There are multiple classes for one course.

Ex: Senior Design

    Student >|---- [member] -----|| team >|---- [advises] ----|<advisor

    Every student is a member of a team, and teams are made up of multiple students. Teams must have students, and all students (limited scope to senior design students) must have a team
    A team can have multiple advisors, and advisors can have multiple teams.   Each team must have an advisor, and each advisor must have a team.

Behavior Based Models
########################
ERD: Describes objets and their relationships.

DFD: Describes how data is transfomred.

Neither of these describes the behavior of the data. State Transition Diagrams (STDs) and Sequence Diagrams (UML) explain the behavior.

Example of STD: copier
    Reading comds.

.. image::
    :src: STD_SeniorDesign.png

Chapter 7
------------
Main Points:
    - High level vs low level design
    - Architectural Styles
    - UML class diagrams

What is Design?
~~~~~~~~~~~~~~~~~
Design is the *how*.

Design is the process of taking a problem and coming up with a solution.

.. note::
    Engineering = putting science into practice paying attention to efficiency, economy and safety.

Design is the process of taking a problem and coming up with a solution that meets established and proessional practices

Levels of Design
~~~~~~~~~~~~~~~~~
Architectural design: high level design describing the major componenets

Detailed design: low level design describing modules, classes,etc.

In theory, each design decision, should related to one module and or one requirement.
In practice, this does not happen, so we will use traceability tables.

Ex:
    Req     | D1    |   D2  |   D3  |   D4  |      
    R1      | X
    R2      |       |   X
    R3      |           X       X   |   
    R4      |           X               X

Shows which desicions meet what requirements.

Software Architectures
~~~~~~~~~~~~~~~~~~~~~~~
Describes how the software is put together or structured.  High-level view of the system.  May not show all components or connections for simplicity.

Architectural Styles
^^^^^^^^^^^^^^^^^^^^^
Each style conjures up mentally a picture of what the structure of the system is.  

Three Cs of arch-styles:
    - componenets:  things that do the work
    - connectors:  things that transport between coponenets
    - constraints:  limits on the number and or type of connectors or components to acheive the style

.. note::
    The good and the bad is for each architecture is tied to the constraint

Data Centric Architectures
############################
Repository: client is active, data store is passive
Blackboard: clients are passive, data share active

Components: clients and data store
Connectors: read/write functions from clients to data store
Constraints: Clients don't talk to eachother (clients are independent)

good: Easy for clients to come and go
bad: Single point of failure

Data Flow Architecture
#######################
Pipes and filters

Ex: UNIX shell
    $ grep pattern file | greap pattern | sort | less

Components: filters
Connectors: Pipes
Constraints: Filters are independent.

good:   reusability and flexibility; support concurrency
bad:    need translator filters for filters that do not speak same language; not good for incremental updates

.. note::
    This style takes a transformational view/approach to data.  Everything that comes in is modified, translated, and passed down the pipeline.

Layered Architecture
########################
Each layer provides a service to the layer above. Lower layers are closer to the machine. Higher layers provide more abstraction.

Components:     layers
Connectors:     calls between layers
Contraints:     Only communicate with the layer directly below you

good:   natural supports abstraction; great reusability
bad:    overhead reduces performance.  Switching between layers hurts performance

Call and Return Architectures
#################################
Each node makes a call to another node, which then returns some value

components:     functions
connectors:     function calls
constraints:    stack based

Object Oriented Architectures
##############################
Components:     objects/ methods
Connectors:     messages
Constraint:     Objects are responsbile for maintaining the integrity of its representation through encapsulation.

good:   easy to abstract which increases reusability
bad:    inheritance means that there is a long train of code that you have to maintain, objects must know the identity of another object in order to communicate (high/tight-coupling) with it

Object Oriented terminology:
    - object:       an instance of a class
    - class:        datatype that provides both attributes and operations on those operations
    - objects communicate by sending messages
    - messages:     consists of the name of the operation to invoke (i.e. the method), the destination object and any parameters.  Messages invoke methods
    - inheritance:  ability of a subclass to reuse or have access to all attributes and operations of its parent(s).
    - under the idea of subclassing, classes fall into a hierarchical relationships.
        * anything that is true for a parent is true for its children (but not the other way around)
    - A subclass may:
        * keep existing behavior
        * add behavior
        * override behavior
    - A subclass may **not**:
        * remove behavior

Event Based Architecture
##########################
Components:     whatever you like (objects, functions, layers)
Connectors:     whatever you had before and events
    *Whatever you had before* is called explicit invocations
    *Events* are implicit invocations

When a change occurs to a component, it announces an event (broadcasts).  
Components that are listning for (registered for) an event have their event handler invoked.

Constraint:     the announcer does not know who receives the event or in what order multiple components receive it

Example:
    Twitter, web-frameworks / browsers, windowing system

good:   a component does not have to know the identity of another compontent in order to communicate with it (low/loose-coupling)
bad:    unpredictable, hard to debug asynchronous code

Example of Chosing an Architecture
###################################
Problem:
    Given a system w/ 2 componenets:
        V: represents a set of vertices
        E: represents a set of edges

    Requirements:
        When an edge is added to E, its vertices must be added to V.
        When a vertex is deleted from V, the incident edges are deleted from E

    Relationship is named G (for graph).

    In the future, we might need to modify G to G'.
    Also we might add a new component C that keeps track of the number of vertices in V.

The point:  most real-world applications are hybrids of multiple systems.

Class Based Modeling
^^^^^^^^^^^^^^^^^^^^^^^^
UML has a class diagram.

Design Concepts
~~~~~~~~~~~~~~~~~~
Key terms:
    - modularity
    - abstraction
    - refinement

Modularity
^^^^^^^^^^^^
modularity:
    * dividing a system into independent components that can be independently managed/thought about
    * we do this because a single monolithic system is too difficult to understand

Example:
    consider two problems, P1 and P2.  Let C represent the complexity of each problem:
        C(P1+P2) > C(P1) + C(P2)

    The complexity of P1 and P2 together is greater than the sum of the complexity of P1 and P2 independently.
    It is easier to think about problems in smaller components.

Too many modules however leads to too much linkage between modules.  Too few modules leads to too much complexity within each module

Abstraction
^^^^^^^^^^^
Abstraction:
    The hiding of details to facilitate understanding.

Different types of abstractions:
    - procedural:
        follow the recipe.  You feed it the input, it spits output and you don't care how it works
    - data:
        you don't know what the data looks like underneath
    - control:
        you don't know how control is done or who's in charge (event-based model)

Refinement
^^^^^^^^^^^
Refinement:
    A method of design that uses a top down strategy that successfully reveals levels of detail.
    Also called *elaboration*

Example:
    Debugging a program.  Start at the top level and dig down until you locate the problem.
    Layered architectures work off this principle.

Abstraction and refinement are complementary

Chapter 8
---------------
Main points:
    - Coupling and Cohesion
    - Traditional metrics
    - Object-Oriented Metrics

Cohesion
~~~~~~~~~
Cohesion:
    Is the degreee of relatedness within a module, unit or component

A cohesive module should do one thing and do it well.  It helps us to understand and maintain software.
All relevant code is in one location and there is no extraneous code.

Different Types of Cohesion
^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Coincidental Cohesion:
    Two tasks (or ideas or pieces of functionality) are in the same module for no good or apparent reason

Logical Cohesion:
    Two tasks that related logically (do the same think like conersion or output) are in the same module

Temporal Cohesion:
    Two tassks that occur near one another in time are in the same module

Procedural Cohesion:
    Occurs when two tasks that are evaluated in the same order in the same module

Communication Cohesion
    Two tasks that rely on the same data structure are in the same module

Items are ordered from *low* to *high* cohesiveness

Coupling
~~~~~~~~~~
Coupling:
    The degree or level of interconnectivity (or interdependence) among modules

Less/Lower/Looser coupling also helps software maintenance. 
Changes are less likely to ripple through the system.

.. note::
    You want high cohesion and low coupling.

Different Types of Coupling
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Data Coupling:
    Simple Argument list of atomic values

.. note::
    Atomic types are integers, references, pointers

Stamp Coupling:
    Portions of data structures are pass as arguments

Control Coupling:
    Pass a control flag as an argument

External Coupling:
    Ties to input, output, and other external devices

Common Coupling:
    Access to a common global data structure

Content Couplin:
    One module just goes in and violates access control to access data in another module

Items are ordered from loose to tight.

Metrics
~~~~~~~~~~~~~
Metrics:
    Quantify quality

We want our software to have certain qualities.  Whether explicitly specified or not (maintainable, usable, reusable, flexible, adaptable, etc.).
All of these qualities of software are hard to measure.

To be useful a metric should be:
    - simple to compute
    - simple to understand
    - intuitive

Early metrics tend to be more low-level and code oriented; whereas, more recent metrics are more high level and design oriented.

Traditional Metrics
^^^^^^^^^^^^^^^^^^^^^^^

Lines of Code
##############
Rationale: 
    more lines of code means more complexity or functionality

It's simple to compute and intuitive.

Problems:
    - More lines does not necessarily lead to more complexity
    - What actually defines a *line* of code
    - This system made sense in Assembly, where each line is a different statement.

Halstead's Complexity Metric
#################################
Rationale:
    More operators and operands = more complex

n1 = # of operators (unique)
n2 = # of unique operands

N1 = total # of operators
N2= total # of operands

EX:
    main()
    {
        int a, b, c, avg;
        scanf("%d %d %d", &a, &b, &c);
        avg = (a + b + c) / 3;
        printf("avg = %d", avg);
    } 
    The unique operators are: main, (), {}, int, scanf, &, =, +, /, printf
    The unique operands are: a, b, c, avg, "%d %d %d", 3, "avg = %d"

Properties:
    - n = n1 + n2 = program vocabulary
    - N = N1 + N2 = program length
    - V = N*log(n) = Program Volumne

Halstead's complexity metric measures the textual/lexical complexity not the structural complexity.

McCabe's Cyclomatic Complexity
################################
Rationale:
    Complexity is more related to structure of a program than to its text.  The more complicated control-flow, the more complex the program

Relies on the use of Flow Graphs.

Quantities:
    N = number of nodes
    E = number of edges
    Complexity = E - N + 2

    If P = # of  desicion nodes, then complexity = P + 1

Problem with McCabe's is that it doesn't take into account the fact that text also changes the complexity of a module

Henry Kafura Information Flow
#################################
Rationale: the connections between modules that result in complexity.  Measures the inter-module flow

Quantities:
    Fan_in = number of incoming connections
    Fan_out = number of outgoing connections

    Complexity_module = (Fan_in * Fan_out)^2
    Complexity_total = sum of Complexity_modules


Object Oriented Metrics
^^^^^^^^^^^^^^^^^^^^^^^^^
Object oriented metrics typically differ from traditonal metrics.  Rather than just focusing on complexity, they often try and measure characteristics such as abstraction, and reuse.

We will discuss one set of metrics - Chidamber and Kember (CK)

Weighted Methods Per Class (WMC)
#################################
Use your favorite traditional completixy metric, apply it to each method in a class and add them up.
The higher the number, the more complex the class is (and therefore harder to understand, modify, ... )

Depth of Inheritance Tree (DIT)
################################
Length of the longest path in the inheritance tree (from root to a leaf)

High number: more reuse (good), more complexity (bad)
Low number: less reuse (bad), less complexity (good)

The deeper a class in the hierarchy, the greater the number of methods it will probably inherit which makes it harder to predict its behavior.

Deeper trees involve greater design complexity since more classes and methods are involved.

Deeper classes in the tree have a greater potential for reusing inherited methods.

Number of Children (NOC)
##########################
Number of subclasses of a parent class.

Higher number:  greater reuse (good), dilution abstraction (bad)

Lack of Cohesion Methods (LCOM)
#####################################
Consider a class with methods m1, m2, ..., mn and instance variables i1, i2, ..., ik

P = set of all method pairs that have non-common INSTANCE variables
Q = Set of all method pairs that have common INSTANCE variables

LCOM = |P| - |Q| if |P| > |Q| else 0

EX:
    M1 = {a,b,c ,s}     //method M1 uses instance variables a,b,c,s
    M2 = {d,b,z}
    M3 = {f,h,n}

    Consider each pair
    (M1,M2) -> Q
    (M1,M3) -> P
    (M2,M3) -> P

    LCOM = |P| - |Q| = 2 - 1 = 1

Trying to measure the cohesion of modules.
High LCOM means low cohesion and low LCOM means high cohesion.

Chapter 10
--------------
Main Points:
    - What is the point of testing?
    - How can we "test" the system?
    - What are validation and verification?
    - Code Coverage for testing?

Quality
~~~~~~~~~
Clearly, we want our software to be high quality.  Quality assurance refers to activities to measure and improve quality.
Quality control rferes to activities to verify the quantity.  

Quality:
    Can be defined as conformance to specification and serving a purpose.

The former part of that definition refers to the verification and the latter refers to validation

V Process Model
~~~~~~~~~~~~~~~~
Requirements                             [validation]       acceptance testing
    High Level (architectural design)    [verification]    System testing
        Low Level (program level design) [verification]   unit testing
            implementation                  

Move from requirements down to implementation, then back up to the testing.  
Things towards the top are more abstract, and things towards the bottom are more concrete.

*Verification* answers the question "did we build the product right?"

*Validation* answers the question "did we build the right product?"

Lack Of Quality
~~~~~~~~~~~~~~~~
Quality is lacking due to errors.

Fault/defect:
    a condition that may cause a failure

Failure:
    Inability of a system to conform to specifications

.. note::
    A fault does not have to be in code.  Faults can also exist in requirements and design documents

The later an erorr is found, the more expensive it is to fix

Finding Errors
~~~~~~~~~~~~~~~
We can find faults in many ways.  **Testing** is one way.

Testing:
    involves running the program with the purpose of *finding errors*.
    It is the most common, easiest, and "cheapest" way
    It is also the only *dynamic* way (i.e. running the program)

There are also many *static* ways to find errors, but these are typically harder and more "expensive."

We can do inspections, reviews, or even use formal methods to prove the code correct.  We can also do a static analysis of the code.

Testing
~~~~~~~~~~
Testing can only show the *presence* of defects, not their absence.

In other words, testing cannot be used to prove a program correct because exhaustive testing is simply not possible.

Example:
    Program to find roots of quadratic ax^2+bx+c.
    We have three inputs, a,b and c.
    Let's assume each input is a 32 bit quanity.  Also assume that we can do one test in 1 ns.
    We would need 2.5 trillion years to test all possible inputs

Another definition of testing:
    To provide a general assessment of quality.  The better the test cases, the better the assessment

Who Does the Testing?
^^^^^^^^^^^^^^^^^^^^^^^
Programmers do *unit testing*.
Testers do *system and integration testing*
Users do *alpha* (in house) and *beta* (not in house) testing

What is Tested?
^^^^^^^^^^^^^^^
Unit testing:
    Test an individual unit

.. note::
    A *unit* is a handful of functions or classes that ideally exhibit high cohesion

Integration/System testing:
    All componenets to test a complete system

When to Stop Testing?
^^^^^^^^^^^^^^^^^^^^^^
Never.  Slightly more practical answer - when all bugs are found. In actuality, when you executed all the test cases.

Fault Seeding
^^^^^^^^^^^^^^^^^
Purposely placing a few errors in the code and then giving it to a test team.

The idea is that:
    >>> (#of seeded faults found / total # of seeded faults) = (#of unseeded faults found) / (Total # of non-seeded faults)

Assumption:
    Distribution across code / functionality of seeded faults matches closely that of actual faults.

Predicting the actual number of faults:
    - Metrics to infer which modules are more complex and therefore more prone to errors
    - Intuition or experience
    - Historical knoweledge of the code (including that of off the shelf code)

Types of Testing
^^^^^^^^^^^^^^^^^^^

Acceptance Testing
###################
Done before official acceptance by the customer (before official release of software).
Black box testing.

Conformance Testing
#####################
Meeting standards requirements.
Black box testing.

Configuration Testing
#######################
Testing across different platforms.
Black box testing.

Performance Testing
####################
Testing non-functional requirements.
Black box testing.

Stress Testing
################
Testing for gradual degradation under the increasing workload
Black box testing.

Genearting Test Cases
^^^^^^^^^^^^^^^^^^^^^
From *intuition*: 
    no guidance, just experience

From *specification*:
     black box testing

From *code*:
  white box testing

From *existing cases*: 
    regression testing

From *history*:
    Looks where errors ahve occurred in the past

Black Box Testing
^^^^^^^^^^^^^^^^^^^^^
Testing done without knoweldge of the implementation.  Testing done at the level of the specification.

Key idea:   generate a minimal number of test cases by considering which test cases are equivalent

.. note::
    Equivalent test cases are bad.  We want to identify them and remove them.

Equivalence Class Partitioning
###############################
Motiviation:    eliminate redundant test cases
Reason:         Save time and computing effort
Idea:           Input is divided into several classes. A representative of each class is used for testing.

Example: Application That makes Recommendations based on age
    Inputs      Test Input
    0-12        7
    13-19       17
    20-35       27
    36-120      47
    <0          -5
    >120        130

    Pick a representative value from each class of input.  Testing 7 is just as good as testing 8, so we don't need to test everything from 0-12.
    
    .. note::
        We classify valid and invalid inputs

Boundary Value Analysis
########################
Goal:       Improve ECP by selecting the most appropriate test inputs
Rationale:  In reality, if we look at historical data, many errors ocur when checking the end points of a range
Idea:       pick as test cases - the boundary, boundary + 1, boundary - 1

Example: Application That makes Recommendations based on age
    Inputs      Test Input  Using BVA
    0-12        7           -1,0,1, 11,12,13
    13-19       17          12,13,14,18,19,20
    20-35       27          19,20,21,34,35,36
    36-120      47          35,36,37,119,120,121
    <0          -5          -1,0
    >120        130         120,121

    #you can then remove the invalid (repeated) arguments in each test stream
    Inputs      Test Input  Using BVA
    0-12        7           -1,0,1, 11,12
    13-19       17          13,14,18,19
    20-35       27          20,21,34,35
    36-120      47          36,37,119,120
    <0          -5          -1
    >120        130         121    

Example: Application requires a username of only (lower case) letters and at most eight characters.
    What are some good test cases using ECP and BVA?
    First consider the length of the string
        inputs  ECP     BVA
        1-8     3       1,2,7,8
        < 1     0       0
        > 8     10      9

    Test strings of length 0,1,2,7,8,9 with valid characters in order to isolate the difference between failing from too many characters and failing from invalid characters.

    Now we can consider the content.
        Inputs          BVA
        a-z (97-122)    97,98,121,122
        <a              96
        >z              123

Whitebox Testing
^^^^^^^^^^^^^^^^^^
Testing done with knoweledge of the code, so let's use it

Code Coverage
##############
We want good code coverage from our test suite. The better the code coveage the more test cases required, but it betters our perception of quality.

Logical Paths
###############
Ideally we want all possible paths thru the code to be executed. For programs with loop, the number of paths is infinite.  We can deal with this problemby limiting loops to at most one iteration per loop.
For each binary decision, there are 2 possible paths.  In the worst case a program with N desicions has 2^N possible paths

Linearly Independence Paths
############################
Not all paths are linearly independent , in that some are combnations of other paths.

The number of linearly independent paths is the same as the cylomatic complexity.
    E - N + 2 = 6 - 5 + 2 = 3
    P + 1 = 2 + 1 = 3
    #Regions = 3

Branch Coverage
#################
Also called decision coverage or edge coverage.

Ensure that each branch will be taken and not taken if we look across all tests

Statement Coverage
######################
Also known as node coverage

Ensure that each statement will be executed at least once

Function Coverage
#####################
Ensures that each function is executed at least once

One test case for a single-function flowgraph

Other Ways of Finding Errors
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Inspections and Reviews are two other ways of finding errors

Review
    simply any process that uses humans to examine a software artifact for the purpose of finding errors

Inspection
    just a more detailed review

Walk through
    An explanation of the artifact

Finding errors is cheaper using testing, but fixing them is expensive.  Testing works only on code, but reviews work on any artifact.  Testing catches errors 'late' whereas inspections and reviews catch errors 'early'

Formal Methods
    Prove the program correct.  usually only practical for small portions of the code

Static Analysis Tools
    Examine the source code looking for errors.
    Results must be examined by hand.

    Ex:
        Lint, gcc -wall

IEEE Code of Ethics for Software Engineers
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
1. PUBLIC - Software engineers shall act consistently with the public interest.

2. CLIENT AND EMPLOYER - Software engineers shall act in a manner that is in the best interests of their client and employer consistent with the public interest.

3. PRODUCT - Software engineers shall ensure that their products and related modifications meet the highest professional standards possible.

4. JUDGMENT - Software engineers shall maintain integrity and independence in their professional judgment.

5. MANAGEMENT - Software engineering managers and leaders shall subscribe to and promote an ethical approach to the management of software development and maintenance.

6. PROFESSION - Software engineers shall advance the integrity and reputation of the profession consistent with the public interest.

7. COLLEAGUES - Software engineers shall be fair to and supportive of their colleagues.

8. SELF - Software engineers shall participate in lifelong learning regarding the practice of their profession and shall promote an ethical approach to the practice of the profession.


In summary, software engineers are expected to act in a manner that benefits the public good (or at least doesn't put it in harm's way).  This means that software enginners must produce safe and reliable code that doesn't put human life at risk and encourage other software engineers to do the same.

Chapter 11
---------------

What is Configuration Management
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Management of software artifacts (docuemnts, code, test cases).  Coordination of change control. Performing (or at least faciliting) system builds.

Examples:
    - Git
    - NPM
    - Brewer (ruby)
    - Jenkins

Chapter 12: Support and Maintenance
-----------------------------------
You have finally released the product, now the real work - we must support.

Support
~~~~~~~~~~~
Non defect support and defect support.
Techincal teams handle defect support; whereas non-technical teams handle non-defect support.

Non-defect support
^^^^^^^^^^^^^^^^^^^
 - General Help (instructions)
 - Usage Questions
 - Additional feature requests

Defect support
^^^^^^^^^^^^^^^^^^^
 - Bug fixes
 - Workarounds
 - Recovery from failure

Maintenance
~~~~~~~~~~~~~~
The final, never ending phase of software development.  Accounts  for 80% of all efforts and cost spent

Types of Maintenance
^^^^^^^^^^^^^^^^^^^^^^^

Corrective:
    fixing errors in requirements, design or implementation (20% of all maintenance)

Adaptive:
    accommodating new platforms (25% of all maintenance)

Perfective:
    enhancements / adding new features (50% of all maintenance)

Preventative:
    Improving software quality for the next round of maintenance (5% of all maintenance)

Perfective Maintenance
########################
Majority of maintenance cost.  40% of all efforts and cost spent are on perfective maintenance.

A major way to reduce software costs is to reduce perfective maintenance. To do this we can: 
    - Practice good design by implementing high cohesion and low coupling.  
    - Use evolutionary process models. 
    - do preventive maintenance 

Preventive Maintenance
#######################
Software needs preventive maintenance because while software doesn't break down (bits don't deteriorate) the world around the software changes.

Business needs change, technology changes, society changes.

The application of today's methodologies to yesterday's systems to support tomorrow's requirements.

Other Maintenance Terms
#########################

Reverse Engineering
    Extracting design from the code

Re-engineering
    Is reverse engineering followed by forward engineering

Chapter 4: Software Process Models
------------------------------------------
Main points:
    - What is a software process model
    - Why process models are important
    - No one software process model is best

What is a Software Process Model
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Software Process Model:
    It's a structure or framework for the development of a software product

It defines several things:
    - Set of tasks to be performed
    - Inputs and Outputs of each task
    - Preconditions and post condition of each task
    - Sequence of flow
    - Who does each task

Simple Process Model
^^^^^^^^^^^^^^^^^^^^^^
Even the simplest pieces of software employ a process model: code-compile-test

.. note::
    Not the technical term for this process model

Problem Statement ---> write code ---> compile ---> test ---> "product" 

In the event of an error, go back to write code.

This model ignores:
    - Design
    - Requirements
    - Maintenance
    - Formal testing

Why are Process Models Important
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
As software gets more complex, so does development. If we don't have a process in place then failures become more likely because of complexity.

Different Process Models
~~~~~~~~~~~~~~~~~~~~~~~~~~~
This sections contains descriptions of several different process models.   You should know how to compare and contrast the different models.

Waterfall Model
^^^^^^^^^^^^^^^^^^
One of the earliest models and it is based on the traditional engineering model.

Requirements --> Design --> Implementation --> Testing --> Release

Requirements: creates requirements document / specification
Design: creates design document (solution)
Implementation: create the system (code)
Testing: produces tested code ready for release

In order to start, you need a business need (a why).

Advantages: 
    - Simple
    - Familiarity.  It is applicable to more than just software engineering
    - It has great process visibility (the ability to measure how close to completion) due to its document-driven, linear nature

Disadvantages:
    - Doesn't accommodate changes 
    - Customer never sees product until release so they have no opportunity to voice opinion about it.
    - Assumes that requirements are clear, complete, and immutable

Use for:
    - Small projects
    - Clear and well-defined requirements
    - Examples:
        * Control systems
        * Embedded system

Variation #1
################
Requirements -->    Design -->  Implementation -->  Testing -->     Release
             -->    Test Plan -->   Low Level testing -->

Do testing all along the design and implementation phases.

V Process Model
^^^^^^^^^^^^^^^^^^^
Req Engr                    acceptance testing
    System Design        system testing
        Program Design  unit testing
                Implementation

Req Engr --- acceptance testing -> validation

System design -- system testing -> verification

Program design --- unit testing -> verification

.. note::
    Has all of the same advantages and disadvantages as the Waterfall model

Incremental Model
^^^^^^^^^^^^^^^^^^^^^
Modification of the waterfall model.  Key idea is decomposing the large system into several smaller systems.  Key question is how to integrate the smaller ones.

There are 2 approaches:
    - Continuous Integration
    - Multiple Releases

Continuous Integration
#######################
Decompose the system into several components.  Each component represents a piece of major functionality.  All components are worked on simultaneously. As each componenet is finished, it is dropped into an integration bucket.

    Req1    Req2    ...     ReqX
    Des     Des             Des
    Impl    Impl            Impl
    Test    Test            Test
    -----------------------------
    |   Integration bucket      | -------> System Testing -------> 
    -----------------------------

Each requirement is done as a mini-waterfall model.

Multiple Releases
##################
First release contains core functionality.  Subsequent releases build upon the core (and previous releases).

Req  ->   Des  ->   Impl  ->  Test  ->  Package+Release
            Req  ->   Des  ->   Impl  ->  Test  ->  Package+Release
                Req  ->   Des  ->   Impl  ->  Test  ->  Package+Release
                                 Req  ->   Des  ->   Impl  ->  Test  ->  Package+Release

Evaluation of Incremental Model
###############################
Advantages:
    - Encourages low coupling (better at accomendating change)
    - Allows different groups to develop in parallel
    - Encourages careful documentation of abstractions
    - Works when people or other recoursces are ntot immediately available

Disadvatages:
    - Coordination of overlapping releases is difficult
    - Idea of decomposition can be difficult
    - Poorer process visibility

Spiral Model
^^^^^^^^^^^^^
An evolutionary model that factors in the risks of future development.
A *risk* involves a cost benfit analysis.  Risks are things like - how much will it cost, what is the benefit, what will break, how long will it take, etc...

Evaluation of the Spiral Model
################################
Explicitly takes into account that the product will need to change over the course of its development.  To do this, the spiral model relies on extensive, frequent customer communication, especially when compared to other models.

This model assumes that the customer is frequently available for discussion.

It also relies on accurate risk analysis.  You also have poor process visibility.  You have no idea how far along the project is.

Rational Unified Process (RUP)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Idea: unline the waterfall model, which views req, design, implementation, test as phases, RUP views them as activities

All of the activities happen in parallel.  Each activity happens at different amounts at different periods of times.  For example, requirements gathering happens a lot more at the beginning, but it never actually ends; whereas implementation happens very little at the beginning, but ramps up later.

Because of the parallel structure, you have more process visibility.  However, with lots of overlapping activities, you have more intra and inter team communication.
Acknowledges  need for verifying efficacy of requirements and design by implementing and testing.


Problems with Traditional Processes
------------------------------------

Many traditional models were created decades ago at a time when big projects and companies were the norm (e.g. areospace).
Development times were >5 years.
Times have changed and smaller companies and projects prevail.
Also, today technology changes quite rapidly.

Traditional models cannot cope with changing requirements.
They have a hidden assumption thatthe requirements are well understood.
Traditional models rely on extra development effort to make up for lost time - the mythical man month

Traditional models have a lot of waste or duplication of effort (e.g. lots of documents are prouced but never looked at and is quickly out of date)

Team Structures
--------------------

Traditional process Models
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Three styles:
    Controlled Centralized:
        - Well defined leader who makes all decisions with no discussion.
        - Maintains conistency, unified vision, and less time wasted
    Democractic Decentralized:
        - No leader at all
        - Discussions take place as group
        - Consensus is needed before moving forward
        - Allows for diversity of opinions, which generates new ideas and novel solutions
        - Not a good model under time pressure
    Controlled Decentralized:
        - Desicions take place as group
        - But there is one person responsible for limiting discussion
        - The goal is to still allow diversity of opinions to facilitate creation of novel solutions while also making sure that deadlines are met

Agile Development
----------------------

What is agile devlopment?  Why do we need agile development?  What is extreme programming?

Agile Processes
~~~~~~~~~~~~~~~~
Agile Process:
    a family of software development methodologies that have some common characteristics:
        - short process and iterations
            * divide work into small pieces then release software to customer as often as possible
        - incremental design
            * dont do a complete design upfront since it is going to change.  Delay design decisions as long as possible
        - user involvement
            * Don't produce formal, immutable docs at start, instead ask users for constant feedback
        - Minimal documentation
            * Source code considered documentation
        - Informal communications
            * Maintain constant communication, but it's informal
        - Change
            * Assume everything will change

An Example Agile Process: Extreme Programming (XP)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

What is XP?
^^^^^^^^^^^^^^^
A Model for small teams facing the pressure of changing requirements

Takeaways
^^^^^^^^^^^^^
Places a lot of emphasis on business value.  To achieve this, it relies on frequent custom communication.  
Balances cost demoand with programming effort.

Key Characteristics of XP
^^^^^^^^^^^^^^^^^^^^^^^^^^
**Short releases**:             every 2-4 weeks
**Simple Design**:              You don't spend a lot of time up front on a complicated design.  
**Test driven development**:    write the unit test before you write the code (unbaised test cases)
**Pairwise Programming**:       two programmers on one keyboard.  Catch mistakes
**Collective Ownership**:       anyone can change anything at any time
**Continuing Integration**:     Always have a working copy
**On site customer**:           Customer is a team member
**Coding Standards**:           consistent naming conventions, etc.
**Documentless**:               No tradional documentation is produced instead the code and test suites are considered documentation

Analysis of XP
^^^^^^^^^^^^^^^^^^
**Pairwise programming**:   Are we wasting personnel or gaining quality (verification)
**Customer Communication**: Are we wasting everyone's time or gaining quaility (validation)
**Documentless**:           Saving time or lost without a road map? 


Bad Software Development Stories
-----------------------------------

Therac-25
~~~~~~~~~~~
Radiation therapy machine.  Due to a concurrent programming error, it sometimes gave patients doses of radition thousands of times greater than it was supposed to which resulted in death and serious injury.  

Previous designs had hardware interlocks for safety to make sure that all mechanical insturments were in the correct place before radition treament started.  However, the Therac-25 removed these hadrware interlocks and replaced them with software interlocks that were prone to failure due to a race condition.  

The software engineers had reused code from a previous model and had assumed that the previous code had been thoroughly tested and was safe.  They also did not have their code formally reviewed.  The Therac-25 correctly displayed an error when the interlock failed, but user manual did not explain what the errors meant and so operators proceeded anyway.  The entire system was also not tested in full until it was assemlbed at  the hospital.

Air Inter Flight 148
~~~~~~~~~~~~~~~~~~~~~~~
Air Inter Flight 148 was a Airbus A320 that deperted Lyon, France and crashed into the mountains while coming in for landing.  

The pilots had no warning of pending impact because the aircraft was not equipped with a ground promixity warning system.  Further, the user interface for the airbuses autopilot was poorly designed.  When the pilots went ot input their decent angle, they didn't realize that the auto-pilot was in vertical speed mode instead of flight angle mode.  The value they entered, meant to be in degrees actually translated to feet and the plane then descended too quickly and into the mountains.

98 people were on board and only a handful survived the crash.

Ariane-5
~~~~~~~~~~~~~~
Ariane-5 was supposed to be the next big rocket for space missions and help increase the reputation of the European Space Agnecy.

Instead, the Ariane-5 rocket crashed on its maiden voyage due to a software failure.   The Ariane-5 reused code from the Ariane-4, but the Ariane-5 was built differently, and the software wasn't able to support this change.  

The crash was caused by a 64 bit floting point number that was casted to a 16 signed integer.  This 16-bit integer overflowed and caused a hardware failure which then caused the rest of the rocket's system to fail and resulted in the destruction of the flight.

The rocket had not been thoroughly tested, and later flight simulators accurately predicted the failure of the launch.  This failure greatly hurt the Euorpean Space Agency's reputation.  Ariane-5 rockets were not trusted until 10 years after this failure.

MIM-104 Patriot
~~~~~~~~~~~~~~~~~~~
The MIM-104 Patriot is a counter-missle system developed by the US military.  In 1991, an Iraq SCUD missle struct a US bunker in Dhahran that had a Patriot system installed and resulted in the death of 28 US soldiers.  

The investigation revelead that the Patriot system's failure to shoot down the incoming missle was due to a software error in how the system handleded timestamps.  If the Patriot system was left on for too long, the internal clock began to drift.  The one at Dhahran had been on for 100 hours and the clock had drifted by 1/3 of a second.  This caused the sytem to track the incoming SCUD incorrectly.

Mars Climate Orbiter
~~~~~~~~~~~~~~~~~~~~~~
The Mars Climate Orbiter was sent out to Mars to study teh climate of the planet.  Unforutnately, the small probe crashed into Mars due to a software error.

The error was due to the fact that part of the software had been designed to work in feet, but other parts were working with meters.  When data was passed between these two parts, it resulted in erroneous calculations that casued the probe to miscalcuate its landing.  The problem had been noted and discovered, but no action had been taken.





Final Review
---------------
Monday December 7th, 2015 @ 1:30pm

30% is pre-midterm
70% is post-midterm

Two part exam:
    - First part is questions 1-10 with a maximum of 90 minutes.  It covers:
        * requirements, design, testing, maintenance, metrics
    - Second part is questions 11-16.  Remainder of time.  It covers:
        * Ethics, stories, process models, Team structures


Requirements:
    - AHP
    - Entity relationship
    - UML diagram

Design:
    - high level vs low level design
    - software architectures

Metrics:
    - Coupling and cohesion
    - standard metrics
    - OO metrics

Testing:
    - point of testing
    - types/ phases of testing (blackbox vs whitebox; unit, integration, system, acceptance; regression, compliance, stress)
    - validation:   pertains to requirements
    - verification: pertains to checking the code

Maintenance:
    - types of maintenance
    - cost of each time of maintenance

Ethics:
    - IEEE code of ethics

Stories:
    - All on online

Process Models:
    - Tradtional models:
        * waterfall
        * incremental
        * spiral
        * RUP

Team Structures:
    - Democratic
    - Centralized
    - CSPAN
    - XP




