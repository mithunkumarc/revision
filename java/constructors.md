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

#### parameterized constructor

      constructor which accepts arguments is called parameterized construcotor
      
      eg:
      // name age are parameters
      public Student(String name, int age) {
		this.name = name;
		this.age = age;
	}

#### when default constructor not provided by compiler

      when user provides a parameterized constructor, compiler wont provide default constructor

#### overloaded constructor : some time object knows only few state info while creating

	class Student {
		String name;
		int age;
		String address;
		// only name
		public Student(String name) {
			this.name = name;
		}
		// only name and age
		public Student(String name, int age) {
			this.name = name;
			this.age = age;
		}
		// all info: name age and address
		public Student(String name, int age, String address) {
			this.name = name;
			this.age = age;
			this.address = address;
		}
	}

	public class HelloWorld {
		public static void main(String[] args) {
			Student s1 = new Student("raj");
			Student s2 = new Student("saj",12);
			Student s3 = new Student("laj",12,"raybag");
		}
	}


##### uses of overloaded constructor : 1. reuse 

	class Student {
		String name;
		int age;
		String address;
		public Student(String name) {
			this.name = name;
		}
		public Student(String name, int age) {
			this(name);// reusing constructor with only name
			this.age = age;
		}
		public Student(String name, int age, String address) {
			this(name,age); // reusing constructor with name and age
			this.address = address;
		}
	}
	
	public class HelloWorld {
		public static void main(String[] args) {
			Student s1 = new Student("raj");
			Student s2 = new Student("saj",12);
			Student s3 = new Student("laj",12,"raybag");
		}
	}

##### uses of overloaded constructor : 2. not all objects have all information
      
		// only name
		public Student(String name) {
			this.name = name;
		}
		// only name and age
		public Student(String name, int age) {
			this.name = name;
			this.age = age;
		}
		// all info: name age and address
		public Student(String name, int age, String address) {
			this.name = name;
			this.age = age;
			this.address = address;
		}

#### constructor chaining: one constructor can call another constructor of same class or parent class

		// this keyword is used to call another constructor of same class
		public Student(String name) {
			this.name = name;
		}
		public Student(String name, int age) {
			this(name);// calling constructor with only string 
			this.age = age;
		}
		public Student(String name, int age, String address) {
			this(name,age); // calling constructor with string and int
			this.address = address;
		}
		
		super keyword is used to call parent class constructor

		class Student {
			String name;
			int age;
			String address;
			public Student(String name, int age) {
				this.name = name;
				this.age = age;
			}
		}
		class CollegeStudent extends Student{
			public CollegeStudent(String name, int age) {
				super(name,age); // calling parent class constructor
			}
		}
		public class HelloWorld {
			public static void main(String[] args) {
				Student s = new Student("saj",12);
				System.out.println(s.name);
				System.out.println(s.age);
			}
		}

#### order of constructor calling in inheritance

	always parent class constructor called first
	
	class Animal {
		public Animal() {
			System.out.println("animal constructo");
		}
	}
	class Dog extends Animal {
		public Dog() {
			// parent constructor called here using super keyword: super();
			System.out.println("dog constructor");
		}
	}
	public class HelloWorld {
		public static void main(String[] args) {
			Animal a = new Dog();
		}
	}
	// output : 
	animal constructor
	dog constructor
	
	parent class state initialized first and then inherit same in child class.

	class Student {
		String name;
		int age;
		String address;
		public Student(String name, int age) {
			this.name = name;
			this.age = age;
		}
	}
	class CollegeStudent extends Student{
		public CollegeStudent(String name, int age) {
			super(name,age); // calling parent class constructor
		}
	}

	public class HelloWorld {
		public static void main(String[] args) {
			Student s = new Student("saj",12);
			System.out.println(s.name); // sai
			System.out.println(s.age); // 12
		}
	}


#### always parent class constructor fired first

	when we create instance, always parent class constructor called first
	so that parent fields initialzed first and gets inherited to child class.

#### access modifiers

1. pubic constructor

	instantiated anywhere
	
2. protected constructor
	
	can be instantiated only inside the package
	outside the package when subclass is instantiated, parent constructor gets called.
	eg:
		package pak1;
		class Laptop{
			protected Laptop() {}
		}
		
		package pak2;
		class HPlaptop extends Laptop{
			Laptop l = new HPlaptop();// calls parent laptop constructor
		}
	
3. construcotor with default access modifier
	
4. private constructor : 
	instantiated only within class

#### return statement

#### this super

#### new operator
