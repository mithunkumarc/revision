#### wrapper class

#### collections can hold objects but not primitives. 

        collections supports only objects.
        primitive datatypes are not objects.
        so collections doesn't support primitive datatypes like int, float, boolean, char.
        solution was to use wrapper classes instead of primitive types.
        Add wrapper class object to collection

#### boxing : prior to java 5

        Prior to Java 5, a common use for the so-called wrapper classes (e.g., Integer, Float,
        Boolean, and so on) was to provide a way to get primitives into and out of
        collections. 
        
        creating instance of primitive value using wrapper class is called boxing.
        
        Integer object = new Integer(1);
        Integer anotherObject = Integer.valueOf(1);// recommended


#### Autoboxing : after java 5

        Prior to Java 5, you had to “wrap” a primitive manually before
        you could put it into a collection. Starting with Java 5, primitives still have to
        be wrapped, but autoboxing takes care of it for you.
