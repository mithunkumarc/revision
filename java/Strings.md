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


#### methods
        charAt()
        int compareTo​(String anotherString) : Compares two strings lexicographically.
                
        String	concat​(String str) : Concatenates the specified string to the end of this string.
        
        boolean	contains​(CharSequence s) : 
        Returns true if and only if this string contains the specified sequence of char values.
        
        boolean	contentEquals​(CharSequence cs)	: Compares this string to the specified CharSequence.
        boolean	contentEquals​(StringBuffer sb)	: Compares this string to the specified StringBuffer.
        boolean	endsWith​(String suffix) : Tests if this string ends with the specified suffix.
        boolean	equals​(Object anObject) : Compares this string to the specified object.
        
        boolean	equalsIgnoreCase​(String anotherString) : 
        Compares this String to another String, ignoring case considerations.
        
        static String	format​(String format, Object... args)	: 
        Returns a formatted string using the specified format string and arguments.
        
        int	hashCode()	: Returns a hash code for this string.
        
        int	indexOf​(int ch) : 
        Returns the index within this string of the first occurrence of the specified character.
        
        boolean	isBlank() : Returns true if the string is empty or contains only white space codepoints, otherwise false.
        boolean	isEmpty() : Returns true if, and only if, length() is 0.
        
        static String	join​(CharSequence delimiter, CharSequence... elements)	
        Returns a new String composed of copies of the CharSequence elements joined together with a copy of 
        the specified delimiter.


        int	lastIndexOf​(int ch)	
        Returns the index within this string of the last occurrence of the specified character.

        int	length()	
        Returns the length of this string.

        Stream<String>	lines()	
        Returns a stream of lines extracted from this string, separated by line terminators.

        boolean	matches​(String regex)	
        Tells whether or not this string matches the given regular expression.

        String	repeat​(int count)	
        Returns a string whose value is the concatenation of this string repeated count times.

        String	replace​(char oldChar, char newChar)	
        Returns a string resulting from replacing all occurrences of oldChar in this string with newChar.

        String[]	split​(String regex)	
        Splits this string around matches of the given regular expression.

        String[]	split​(String regex, int limit)	
        Splits this string around matches of the given regular expression.

        boolean	startsWith​(String prefix)	
        Tests if this string starts with the specified prefix.

        boolean	startsWith​(String prefix, int toffset)	
        Tests if the substring of this string beginning at the specified index starts with the specified prefix.

        String	strip()	
        Returns a string whose value is this string, with all leading and trailing white space removed.

        String	stripLeading()	
        Returns a string whose value is this string, with all leading white space removed.

        String	stripTrailing()	
        Returns a string whose value is this string, with all trailing white space removed.

        String	substring​(int beginIndex)	
        Returns a string that is a substring of this string.

        String	substring​(int beginIndex, int endIndex)	
        Returns a string that is a substring of this string.

        char[]	toCharArray()	
        Converts this string to a new character array.

        String	toLowerCase()	
        Converts all of the characters in this String to lower case using the rules of the default locale.


        String	toString()	
        This object (which is already a string!)

        String	toUpperCase()	
        Converts all of the characters in this String to upper case using the rules of the default locale.


        String	trim() : remove extra space


#### new methods in java 9/11/new versions

        tobe updated

#### String format function

        tobe updated

#### How to implement immutable class

        tobe updated

#### comparing strings

        .equals : compare content
        .compareTo : compare lexicographically : dictionary order, -1 , 0(equal) , 1

#### blank final variable

        tobe updated


