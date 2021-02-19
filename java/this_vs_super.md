* this/super must appear at the first line of constructor
* only either this or super keyword must appear in the first line inside constructor


#### this

1. differentiate between local variable and instance variable
      
      public Student(String name) {
          this.name = name;
      }
      
2. constructor chaining

       class Student {
          String name;
          String address;
          public Student(String name, String address) {
            this.name = name;
            this.address = address;
          }
          public Student(String name) {
            this(name, "default address");
          }
        }
        
3. send current object as parameter to method
   
         class Student {
          String name;
          public Student(String name) {
            this.name = name;
          }
          public void enroll() {
            this.selectSubject(this); // sending current object as this
          }
          public void selectSubject(Student s) {
            System.out.println("select subject : "+ s.name);
          }
        }

        public class HelloWorld {
          public static void main(String[] args) {
            Student s = new Student("vin");
            s.enroll();
          }
        }
 
4. send current object as parameter to constructor
      
            class College {
              public College(Student s) {
                System.out.println(s.name + " enrolled");
              }
            }

            class Student {
              String name;
              College college;
              public Student(String name) {
                this.name = name;
              }
              public void enroll() {
                this.college = new College(this); // send current object as parameter to constructor
              }
            }

            public class HelloWorld {
              public static void main(String[] args) {
                Student s = new Student("vin");
                s.enroll();
              }
            }

#### super


1. call parent constructor :super(..args) will  call matching parent class constructor

            class Animal {
                  public Animal() {
                        System.out.println("animal constructor");
                  }
            }

            class Dog extends Animal {
                  //default constructor will be added by compiler
                  //default constructor call parent class constructor by default
                  //to call parent class constructor, super keyword is used
                  //super() will be used at the first line insdie constrcutor
                  //super() will call parent class constructor
            }
            public class HelloWorld {
                  public static void main(String[] args) {
                        Dog d = new Dog();
                  }
            }
            
another example : 
      
            class Animal {
                  String name;
                  public Animal(String name) {
                        this.name = name;
                  }
            }

            class Dog extends Animal {
                  public Dog(String name) {
                        super(name); // passing to parent for initialization and inherit the same value
                  }
            }
            public class HelloWorld {
                  public static void main(String[] args) {
                        Dog d = new Dog("tommy");
                        System.out.println(d.name); // tommy
                  }
            }

2. parent class refvar

3. parent class method
 
