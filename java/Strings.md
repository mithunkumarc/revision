#### Strings : 

        sequence of characters
        String class is special and doesn’t need to be instantiated with new.
                String s1 = "hello";//double quotes, first way
                String s2 = new String("hello"); // second way
                
#### concatenation : use operator "+"

        If both operands are numeric, + means numeric addition.
        2. If either operand is a String, + means concatenation.
        3. The expression is evaluated left to right. eg : 1 + 2 + "c " : output 3c

#### Strings are immutable : read string pool concept

        once string is created , value cannot be changed.
        String class is final
        fiels/instance variables private
        no setter method, allow constructor initailization at the time of creating object
        
#### string pool : 

        Java realizes that many strings repeat in the program and solves this issue by reusing common ones. 
        The string pool, also known as the intern pool, is a location in the Java virtual machine (JVM)
        that collects all these strings.

        The string pool contains literal values that appear in your program 
        When you use 
                String s = "Hello"; 
                String s2= "Hello";
                you get the same copy for both s and s2. 

        However, when you do 
                String s = new String("Hello"); 
                String s2 = new String("Hello") 
                you have different copies for s and s2 in the heap.

#### why strings are immutable 

        strings are reused in same application, 
        if strings are mutable, changing at one place will affect other places too.

#### strings can be read character by character using index, 0 based index

#### methods

#### new methods in java 9/11/new versions



#### equals vs ==

        equals : compares content
        == used between any two reference variables, true if both pointing to same object else false;

#### compare string

        String s1 = "hello";
        String s2 = "hello";
        s1 == s2; //true , s1 and s2 both pointing to same copy in string pool
        
        String s1 = new String("hello");
        String s2 = new String("hello");
        s1 == s2; //false, s1 and s2 pointing to different copy in heap

#### Mutable Strings : String buffer and String builder

        // code same for StringBuffer
        StringBuilder sb = new StringBuilder("start");
        sb.append("+middle"); // sb = "start+middle"
        StringBuilder same = sb.append("+end"); // "start+middle+end"

        * NOte :  StringBuffer does the same thing but more slowly because it is thread safe.
        * Thread safe : methods are syncronized



String format function
immutable class
blank final variable



