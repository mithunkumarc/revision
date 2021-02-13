#### wrapper class

        byte	Byte
        short	Short
        int	Integer
        long	Long
        float	Float
        double	Double
        boolean	Boolean
        char	Character
        
        
#### compraing wrapper class objects 

        Integer i1 = 1000; // autoboxing : Intger.valueOf(1000);
        Integer i2 = 1000; // autoboxing : Intger.valueOf(1000);
        
        i1 == i2;// false : as i1 and i2 points to two differenct instances
        i1.equals(i2);// true : as content is same : 1000

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
        you could put it into a collection. 
        
        Integer i = new Integer(5);
        List<Integer> mylist = new ArrayList<Integer>();
        mylist(i);
        
        Starting with Java 5, primitives still have to
        be wrapped, but autoboxing takes care of it for you.
        
        List<Integer> mylist = new ArrayList<Integer>();
        mylist(5); // translated to : mylist(new Integer(5)); or mylist(Integer.valueOf(5));
        
        
        // another example for autoboxing
        Integer val = 2; // autoboxing
        // above code translated to : Integer val = Integer.valueof(2);
        
        
