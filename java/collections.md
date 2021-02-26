                Iterable (i)  
                       - Collection(i)
                              - List(i) 
                              - Queue(i) 
                              - Set(i)

                List(i) 
                       - ArrayList(c)
                       - LinkedList(c also Deque(i)) , 
                       -  Vector(c)
                                - Stack

                Queue(i) 
                        - Deque(i)
                               - ArrayDeque(c)
                               - LinkedList(c)
                        - Priority Queue(c)

                                       
                Set(i) - 
                        SortedSet(i)
                                - TreeSet(c)

                        HashSet(c), 
                        LinkedHashSet(c)

#### Collection class/interface

        collection api Represents the data structure in which objects are stored

        Collection java.util interface from which Set and List extend
        Collections A class that holds static collection utility methods

#### Map : 

                Map(i) 
                        - SortedMap(i)
                                - NavigableMap(i)
                                        - TreeMap(c)
                        - HashTable(c)
                        - HashMap(c)
                                - LinkedHashMap
        
#### List : 

      Ordered, 
      duplicates allowed, 
      index based


#### Set  :
        
        May or may not be ordered (hashset not ordered, linkedhashset ordered)
        may be sorted(treeset) 
        duplicates not allowed

#### Map : 

        May be oredered : LinkedHashMap
        may not be ordered : HashMap
        sorted ; TreeMap 
        duplicate keys are not allowed.

#### Queue

        Queues of things to process Ordered by FIFO or by priority

#### ordered vs sorted

        ordered : same as the user add element 
        sorted : number : ascending descending, string : alphabetical

#### collection classes


        ArrayList Fast iteration and fast random access.

        Vector It’s like a slower ArrayList, but it has synchronized methods.

        LinkedList Good for adding elements to the ends, i.e., stacks and
        queues.

        HashSet Fast access, assures no duplicates, provides no ordering.

        LinkedHashSet No duplicates, iterates by insertion order.

        TreeSet No duplicates, iterates in sorted order.

        HashMap Fastest updates (key/values); allows one null key, many
        null values.

        Hashtable Like a slower HashMap (as with Vector, due to its
        synchronized methods). No null values or null keys allowed.

        LinkedHashMap Faster iterations; iterates by insertion order or last
        accessed; allows one null key, many null values.

        TreeMap A sorted map. sorts primitive types. use comparable for sorting user defined objects.

        PriorityQueue A to-do list ordered by the elements’ priority.

        ArrayDeque Like an ArrayList only better performance; ordered
        only by index. Good for stacks and queues.


#### ArrayList vs LinkedList

        ArrayList : single block of memory, fast read, delete/create slow.
        LinkedList : linked memory, fast delete/create, and slow read.

#### HashSet vs LinkedHashSet vs TreeSet

        HashSet : when order is not cared. 
        LinkedHashSet : Order is important. 
        TreeSet : sorted order


#### ConcurrentSkipListSet vs treeset

        both implements Sorted Set interface
        Both are sorted by natural order or according to the comparator provided.
        ConcurrentSkipListSet is thread safe, TreeSet is not thread safe.
        
        
#### sortedset vs navigable set (interfaces)

      The Java NavigableSet interface, java.util.NavigableSet, is a subtype of the Java SortedSet interface. 
      Therefore the NavigableSet behaves like a SortedSet, 
      but with an additional set of navigation methods available in addition to the sorting mechanisms of the SortedSet

      // navigable set methods
      headSet : returns all elements which are less than passed element, headSet(5); returns all elements < 5
      tailSet : returns all elements which are higher than passed element, tailset(5) ; returns > 5
      higher : retuns element which is greater than or equal to passed element : eg higher(5); returns >= 5
      lower : retuns element which is less than or equal to passed element : eg lower(5); returns <= 5
      pollFirst : remove first element
      pollLast : remove last element


#### BlockingQueue : interface
  
        block accessing thread if queue is full and thread try to add new one
        bock accessing thread if queue is empty and thread try to read

        A blocking queue indicates that the queue blocks the accessing thread if it is full 
        (when the queue is bounded : initial size is mentioned) 
        or becomes empty. If the queue is full, then adding a new element will block the accessing thread 
        unless there is space available for the new element. 
        Similarly, if the queue is empty, then accessing an element blocks the calling thread:


####  ConcurrentLinkedQueue 

        It is an unbounded, thread-safe, and non-blocking queue.
        
        Unlike a LinkedBlockingQueue, a ConcurrentLinkedQueue is a non-blocking queue. 
        Thus, it does not block a thread once the queue is empty. Instead, it returns null. 
        Since its unbounded, it'll throw a java.lang.OutOfMemoryError if there's no extra memory to add new elements.

#### BlockingQueue vs ConcurrenLinkedQueue

        Both implements the Queue Interface
        They both use linked nodes to store their elements
        Both are suitable for concurrent access scenarios

        while accessing BlockingQueue has compiletime exceptions
        but ConcurrentLinkedQueue gives 
          null: when thread try to read empty list
          OutOfMemoryError: when thread try to add new element whent queue is full


#### concurrent exception : 

        when reading/iterating arraylist for examaple, you cannot modify , if you try to modify you get this exception
        for this use collection from java.util.concurrent



#### thread safe list : java.util.concurrent.CopyOnWriteArrayList<E>
  
        A thread-safe variant of ArrayList in which all mutative operations (add, set, and so on) are implemented 
        by making a fresh copy of the underlying array.

#### thread safe set : java.util.concurrent.CopyOnWriteArraySet<E>

        
#### thread safe map : java.util.concurrent.ConcurrentHashMap



#### tobe covered

            wrapper class
            autoboxing
            java 11 autoboxing
            unboxing
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
