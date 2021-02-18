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


1. call parent constructor
2. prent class refvar
3. parent class method
4. 
