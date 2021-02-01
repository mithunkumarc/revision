
1. Inheritance
    1. what is inheritance. example
    2. types of inheritance
    3. top most class in Java
    4. Object class and its methods
    5.  

#### Method overriding : 

    overriding implmention in child class

#### variables hiding 
    
    overriding child instance variable value

        class Animal {
            String name = "abc";
            public void eat(){}
        }
        class Dog extends Animal {
            String name = "def";
            public void eat(){}
        }

        problem case : 
        Animal a = new Dog();
        System.out.println(a.name); // prints "abc"
        a.eat(); // dog eat
        
        method called are always overridden(on which object called)(polymorphism)
        instance variables values are parent class
