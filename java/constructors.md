#### constructor 

      member of class, used to initialize properties of object
      provides oppertunity to initialize state of an object at the time of creating it.
      
#### initializing state of object using dot operator

            class Student {
              String name;
              int age;
            }

            Student s1 = new Student();
            s1.name = "raj";
            s1.age = 12;

#### initializing state of object using setter method


            class Student {
              String name;
              int age;
            }
            
            Student s1 = new Student();
            s1.setName("raj");
            s1.setAge(12);

#### initializing state of object using constructor : better than dot operator and setter method

            class Student {
              String name;
              int age;
              public Student(String name, int age) {
                this.name = name;
                this.age = age;
              }
            }

            public class HelloWorld {
              public static void main(String[] args) {
                Student s1 = new Student("raj",12);
              }
            }


#### instance variable and local variable to have same name, so differiate between the use "this" keyword

              // if you skip this keyword, Student object state will not get initialized
              // value goes to local variable
              public Student(String name, int age) {
                this.name = name;
                this.age = age;
              }


#### Default constructor
  
      By default java compiler provides empty constructor if user fail to provide one.
      Default constructor assign default values to instance variables.


        class Student {
          String name;
          int age;
          // we have not provided any constructor here
        }

        // below default constructor will be added in above class
        public Student(String name, int age) {
            this.name = "null"; // string default value is null
            this.age = 0; // int default vlaue is zero
          }

#### overloaded constructor 

##### uses of overloaded constructor : 1. reuse 

##### uses of overloaded constructor : 2. not all objects have all information
      

#### constructor chaining

#### access modifiers

#### return statement

#### this super

#### new operator
