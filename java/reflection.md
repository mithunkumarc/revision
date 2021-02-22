1. Java Reflection is a process of examining or modifying the run time behavior of a class at run time.
2. The java.lang.Class class provides many methods that can be used to get metadata, examine and change the run time behavior of a class.
3. The java.lang and java.lang.reflect packages provide classes for java reflection.

#### inspect

        fields, its modifiers
        methods, its modifiers
        parent class
        implemented interfaces
        constructors

#### The Reflection API is mainly used in:

1. IDE (Integrated Development Environment) e.g. Eclipse, MyEclipse, NetBeans etc.
2. Debugger
3. Test Tools etc.

#### api

1. Java Reflection makes it possible to inspect classes, interfaces, fields and methods at runtime, without knowing the names of the classes, methods etc. at compile time.
2. It is also possible to instantiate new objects, invoke methods and get/set field values using reflection.

> The name reflection is used to describe code which is able to inspect other code in the same system (or itself) at runtime.


#### useful api

##### can inspect object of unknown type

      License unknownRefVariable = new License();	
   	  unknownRefVariable.getClass().getMethods();	// 


##### methods declared in class
   	 
     Method[] methods = License.class.getMethods();
   	 for(var m : methods) {
   		 System.out.println(m);
   	 }
   	 
##### getpackage name
   	 
     System.out.println(License.class.getPackage());
   	 
     
##### instance variables of class

   	 Field[] fields = License.class.getDeclaredFields();
   	 for(var field : fields) {
   		 System.out.println(field);
   	 }
   	 
##### interfaces implmented by a class

   	 var interfaces = License.class.getInterfaces();
   	 for(var i : interfaces) {
   		 System.out.println(i);
   	 }
     
##### read all constructors

       var cons = a.getClass().getConstructors();
       for(var constructor : cons) {
         System.out.println(constructor);
       }
   	 
##### get superclass

         var classObj = a.getClass().getSuperclass();
         System.out.println(classObj);

##### modifiers of method can be individually checked

        System.out.println(Modifier.isStatic(method.getModifiers())); // true or false
        System.out.println(Modifier.isPublic(method.getModifiers())); // true of false
        // isAbstract, isProtected, isPrivate, isSynchronised, isFinal
        
        // example modifiers
        //final
        //abstract
        //private
        //protected

     
#### example

        import java.lang.reflect.Field;
        import java.lang.reflect.Method;

        interface renewable{

        }

        class License implements renewable{
            private int licenseNumber;

            public void register(int number) {
             System.out.println(number + " : registration");
            }

            public void renew(int number) {
             System.out.println("Renew license :  " + number);
            }

            public int getLicenseNumber() {
             return licenseNumber;
            }

            public void setLicenseNumber(int licenseNumber) {
             this.licenseNumber = licenseNumber;
            }

        }
        public class TestReflection {
            public static void main(String[] args) {

              // License l = new License();	
              // if you don't know the type of variable "l"
             // l.getClass().getMethods();	// can inspect object of unknown type

             // methods declared in class
             Method[] methods = License.class.getMethods();
             for(var m : methods) {
               System.out.println(m);
             }

             // getpackage number
             System.out.println(License.class.getPackage());

             // instance variables of class
             Field[] fields = License.class.getDeclaredFields();
             for(var field : fields) {
               System.out.println(field);
             }

             //interfaces
             var interfaces = License.class.getInterfaces();
             for(var i : interfaces) {
               System.out.println(i);
             }   	    	 
            }
        }
