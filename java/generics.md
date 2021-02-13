1. provides compile-time type checking and removes the risk of ClassCastException 
that was common while working with collection classes.

2. Generics enable types (classes and interfaces) to be parameters when defining 
classes, interfaces, and methods. 

3. Much like the more familiar formal parameters used in method declarations, 
type parameters provide a way for you to re-use the same code with different 
inputs. 

4. The difference is that the inputs to formal parameters are values, 

        add(int a, int b) : a= 5, b=6

while the inputs to type parameters are types.
  
        addItem<T>(T t) : t can be any type(object) can be reused for another object


#### Benefits of generics : 

1. Stronger type checks at compile time

      List<String> list = new ArrayList<String>(); 
      list.add("abc"); // allows only string

2. Elimination of casts, reading objects becomes easy no surprises

      List<String> list = new ArrayList<String>();
      list.add("hello");
      String s = list.get(0); // no need of casting (String) list.get(0);
   
      // Note : 
      List list = new ArrayList(); //takes any object
      list.add("one");
      list.add(true);
      
      //reading becomes difficult, you should know which value has at which index
      //casting is necessary
      String s = (String) list.get(0);
      Boolean b = (Boolean) list.get(1);
   
3. Enabling programmers to implement generic algorithms

    By using generics, programmers can implement generic algorithms 
    that work on collections of different types, can be customized, 
    and are type-safe and easier to read.      
        
        // Generic Box class, can take any object
        public class Box<T> {
            private T t;
            public void set(T t) {
                this.t = t;
            }
            public T get() {
                return t;
            }
        }


#### naming conventions

        E - Element (used extensively by the Java Collections Framework)
        K - Key
        N - Number
        T - Type
        V - Value
        S, U, V etc. - 2nd, 3rd, 4th types
      
#### Multiple Parameters 

        public interface Pair<K, V> {
            public K getKey();
            public V getValue();
        }

#### subclass in generics
  
    class Zoo<T extends Animal> {
        public T t; // T must be subclas of animal
    }

#### without generics there will be warning

        .. unsafe operations
        
#### variable declaration must match the type you pass to the actual object type.

        class Parent {
	
        }
        class Child {

        }
        // inside main, parent type child instance doesn't match
        List<Parent> myList = new ArrayList<Child>(); // error
        
        // works
        List<Parent> myList = new ArrayList<Parent>();
        List<Child> myList = new ArrayList<Child>();
        
#### bounded, wildcards  

        tobe updated : https://www.javaguides.net/
