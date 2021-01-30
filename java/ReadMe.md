        java 8 new apis 

java 9 Modules Introduction

[introduction](https://beginnersbook.com/2018/09/java-9-modules/)

        Core Java

####  Procedure Oriented Language vs Object Oriented Language

                prog divided to function : objects
                no access specifiers encapsulation : exist
                func is imp : data is imp
                no polymor overloading/rriding : exist
                
#### Features

        Simple
        Object Oriented
        Platform Independent : code written for JVM : JVM  platform dependent
        Secure : enables to develop virus-free, tamper-free systems. 
        Architecture-neutral
                compiler generates an architecture-neutral object file format, which makes 
                the compiled code executable on many processors, 
                with the presence of Java runtime system.
        Portable
                Being architecture-neutral and having no implementation dependent aspects 
                of the specification makes Java portable. 
        Robust
                Java makes an effort to eliminate error-prone situations by emphasizing 
                mainly on compile time error checking and runtime checking.

        Multithreaded
                With Java's multithreaded feature it is possible to write programs 
                that can perform many tasks simultaneously. 

        Interpreted
                Java byte code is translated on the fly to native machine 
                instructions and is not stored anywhere. 

        High Performance
                With the use of Just-In-Time compilers, 
                Java enables high performance.
        Distributed
                Java is designed for the distributed environment of 
                the internet.

        Dynamic
                Java programs can carry an extensive amount of 
                run-time information that can be used to verify and 
                resolve accesses to objects at run-time.

#### java secure: 

        programs run inside a virtual machine called sandbox.
        explicit pointer : point to address location
        Byte-code verifier checks the code fragments for illegal code that can violate access right to object.
        It provides java.security package implements explicit security.
        It provides library level safety.
        Run-time security check takes place when we load new code.

#### classloaders : 

        Java ClassLoader is an abstract class. It belongs to a java.lang package. 
        It loads classes from different resources. 
        Java ClassLoader is used to load the classes at run time. 
        In other words, JVM performs the linking process at runtime. 
        Classes are loaded into the JVM according to need
        
#### ClassLoader is based on three principles: Delegation, Visibility, and Uniqueness.

        Delegation principle: It forwards the request for class loading to parent class loader. 
        It only loads the class if the parent does not find or load the class.
        Visibility principle: It allows child class loader to see all the classes loaded by parent ClassLoader. 
        But the parent class loader cannot see classes loaded by the child class loader.
        Uniqueness principle: It allows to load a class once. It is achieved by delegation principle. 
        It ensures that child ClassLoader doesn't reload the class, which is already loaded by the parent.
        
#### Types of classloaders :    
        
        Bootstrap Class Loader: It loads standard JDK class files from rt.jar and other core classes. 
        Extensions Class Loader: It delegates class loading request to its parent. 
        If the loading of a class is unsuccessful, it loads classes from jre/lib/ext directory or any other 
        directory as java.ext.dirs. classes in JAR files in lib/ext directory of JRE, and in the system-wide, 
        platform-specific extension directory (/usr/jdk/packages/lib/ext)
        System Class Loader: It loads application specific classes from the CLASSPATH environment variable.

#### main method

        syntax, access specifieres, overrided/overloaded?
        why manin method is static

#### how System.out.println() works

#### singlenton implementation

#### final finally finalize(java 11)


        Hello world program : Creating java class and executing in command prompt

#### data types
        
        char byte short int long float double boolean : primitive
        string array arraylist : builtin
        Person class: user defined
                
        
#### arrays
        
        fixed size, fixed type, reading fast, deleting elements create holes
        int[] a = new int[10];
        int[] b = {};
        
### varargs : varname...datatype

        public static void main(args...String) {
                //args  : multiple arguments can be received
        }
        

#### Looping statements and Control statements

        if, if else, else if
        enhanced for loop
        switch : supports char int string, (check latest java version)
        
#### Identifiers : names of variable/fields/methods/class/interface names
        
        _ and $ only special sympbols allowed
        digits not allowed in the beginning
        any length
        _ cannot be used as var name (check latest java version)


#### class

        blueprint of an object, 
        defines what object can have as state and how it should behave as methods
        public and default access modifiers only allowed
        protected and private not allowed.
        static applied to inner class
        final can be applied to call to stop inheritance
        static variables are also called class variables
        static methods are also called class methods
        each file can have any number of class but only one public class
        //check: public to class file same as filename? main method?
        
        
#### object

        An object is a runtime instance of a class in memory.
        has state and behaviour
        object can be made up of group of objects
        object can be state of another object. so access modifiers can be applied.
        staic final can also be applied on variable pointing to object
        
#### instance methods
        
        methods behaviour/return value depends on state
        or methods operate on state and can change state value
        eg: horn() of class Car

#### instance variables

        state of object
        eg : name of person class
        instance variables can be final
        instance variables can point to object(you can say static object)
        
#### Ways to initialize instance variables

        1. constructors
        2. setter methods
        3. using reference variable(depends on access specifier)
        4. directly instialize inside class.
        

#### local variable, instance variable, static variable

#### how to create (global)constants 


        Association : one to one, one to many, many to many
        Association : composition and aggregation
        return statement, break and continue statement

#### import statement
     
        any number of import statement allowed
        import all classes : import java.util.*;
        specific import : import java.util.ArrayList;
        speicific import recommended. import what u need.

#### static import : 

        we can access the static members of a class directly without class name or any object
        eg : 
        import static java.lang.Math.*; 
        inside main method : System.out.println(sqrt(4)); 

#### class found in multiple packages

        eg : Date found in util and sql
        When the class is found in multiple packages, Java gives you the compiler error:
                import java.util.*;
                import java.sql.*; // DOES NOT COMPILE
        The type Date is ambiguous
        solution : 
                import java.util.Date;
                import java.sql.*;

        if you want to use both : 
                java.util.Date date;
                java.sql.Date sqlDate;
                
        packages and declaring package
        access specifiers
        Rules for source files
        Object Oriented Language Brief
        sending parameter values to method,[ var...args ]
        inheritance and encapsulation
        overloading methods
        abstract classes

#### Constructor
        
        member of class
        name of constructor must be same as class name
        fired when object(new operator) is created
        constructor can have empty return statement.(no return value)
        purpose: initialize instance variable at the time of object being created
        constructor implicity returns object which has been created(memory allocated pointer/address)
        allocated memory for object
        can be declared as public, protected, private and default
        multiple constructors are allowed        
        constructors can be overloaded(constructors with differenct number of params or order) 
        constructors cannot be overrided as they dont inherit to subclass
        static final cannot be applied to constructors

#### Default constructor

        if we dont provide any constructor, default constructor is provided
        default constructor assign default value to instance varialbles

#### constructor chaining : reuse for initialization of instance varialbles

        one constructor can call another constructor in the same class using this keyword
        child class constructor can call parent class constructor using super keyword
        

        Default
        Overloaded
        chaining
        Access modifiers
        Polymorphism
        Property hiding
        overriding
        this and super, difference between local and instance variables
        TypeCasting
        instanceof
        Enum datatype
        final keyword
        static keyword
        Variable
        method
        Inheritance
        Can be overrided? No they ll be replaced in subclass
        setters and getters methods
        print() and main()
        Interfaces, sam, marker, tagged interface
        Default,static,private methods
        reflection
        string class, immutable, equals vs ==
        String buffer and String builder
        String format function
        object class and its methods
        pass by reference pass by value : ex1 : primitive, ex2 : object : swap
        Wrapper classes
        generics
        Collection hierarchy and generics - forEach loop
        Lists : include split iterator
          Immutable : List.of
        Set
        Override hashcode and equals for hashset
        Comparable for treeset
        Immutable : Set of
        comparable and comparator
        map
          Immutable : Map of
        Exception, types, custom exception, throw throws, try with resources, rethrow
        Autocloseable interface
        io and scanner : try resource : java 8
        Multi threading
        Anonymous classes and functional interfaces
        JVM Architecture
        lambdas and streams
        Filter
        Map
        Reduce
        Foreach
        Streams
        Takewhile
        Dropwhile
        Parallel
        Sequential
        Skip
        Limit
        etc...
        Creating a Dictionary program using collection
        Singleton pattern
        Java 8 . 
          Default private methods in interface
          Functional interfaces
          Lambdas and streams
          Double colon operator
          optionals
        Java 9
          Modules
        Java 10
          Type inference : side effects
        Java 11
          Sting isblank, lines(), 



        J2EE

        1.java database connection : jdbc with crud operations.

        2.MVC design pattern 

        3.Difference between DAO , DTO and service classes

        4.Servlets

        5.http request and http response

        6.http session

        7.servlet config and servlet context

        8.Jsp

        9.servlet - jsp - jdbc integration


        Hibernate

        1.Architecture

        2.crud operations

        3.one to one mapping

        4.one to many mapping 

        Spring 

        1.Architecture

        2.Maven pom file

        3.Dependency injection 

        4.spring mvc

        5.spring and hibernate integration 

        6.project on spring with hibernate
        
        BiConsumer
        BiFunction
        BinaryOperator
        BiPredicate
        BooleanSupplier
        Consumer
        DoubleBinaryOperator
        DoubleConsumer
        DoubleFunction
        DoublePredicate
        DoubleSupplier
        DoubleToIntFunction
        DoubleToLongFunction
        DoubleUnaryOperator
        Function
        IntBinaryOperator
        IntConsumer
        IntFunction
        IntPredicate
        IntSupplier
        IntToDoubleFunction
        IntToLongFunction
        IntUnaryOperator
        LongBinaryOperator
        LongConsumer
        LongFunction
        LongPredicate
        LongSupplier
        LongToDoubleFunction
        LongToIntFunction
        LongUnaryOperator
        ObjDoubleConsumer
        ObjIntConsumer
        ObjLongConsumer
        Predicate
        Supplier
        ToDoubleBiFunction
        ToDoubleFunction
        ToIntBiFunction
        ToIntFunction
        ToLongBiFunction
        ToLongFunction
        UnaryOperator
        https://www.tutorialspoint.com/java8/java8_streams.htm
        https://howtodoinjava.com/java8/java-streams-by-examples/
        https://stackify.com/streams-guide-java-8/
        https://www.geeksforgeeks.org/stream-generate-method-java/
        https://www.geeksforgeeks.org/stream-ofnullablet-method-in-java-with-examples/
        
#### read 

        https://github.com/wesleyegberto/java-new-features

