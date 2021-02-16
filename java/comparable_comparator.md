Sorting can be in natural order or via a Comparable or many
Comparators.

Implement Comparable using compareTo(); provides only one sort
order.

Create many Comparators to sort a class many ways; implement
compare().

Use a lambda expression as a shorthand to create a Comparator.

To be sorted and searched, an array’s or List’s elements must be
comparable.

To be searched, an array or List must first be sorted.

#### comparable vs comparator

        both used to sort collections/array
        comparable : compare logic implemented by the class which implements comparable interface
        
                        Collections.sort(studentList); // student class implements comparable 
                        //stuck for one kind of sort, either name or age
                
        comparator : compare logic implemented by dedicated class which implements comparator, pass as argument to 
                        collections
                                                
                        Collections.sort(studentList, nameComparator); // class NameComparator implements comparator
                        //sort in many was depends on which comparator you send. eg: name comparator/age comparator/id etc


| Comparable           | Comparator  |
|:-------------:| :-----:|
| single sorting sequence(as implemented in original class) | multiple sorting sequences (eg: NameComparator, AgeComparator |
|  affects the original class     | doesn't affect the original class  |
|  provides compareTo() method   |  compare()  |
| java.lang | java.util |
| Collections.sort(studentList)  | Collections.sort(studentList, nameComparator) |




#### we can use comparable comparator for sorting list, for set/map they have treeset and treemap

        Collections.sort(studentList) // comparable 
        Collections.sort(studentList, nameComparator) // comparator 

#### comparator with list, logic passed from class which implements comparator interface
        
        class Student {
                private String name;
                public Student(String name) {
                        this.name = name;
                }
                @Override
                public String toString() {
                        return this.name;
                }
                // not a good idea. doing this for example, take helper method
                public Student setName(String name) {
                        this.name = name;
                        return this;
                }
                public String getname() {
                        return this.name;
                }

        }

        public class TestComparator {

                public static void main(String[] args) {
                        Student s1 = new Student("kaj");
                        Student s2 = new Student("saj");
                        Student s3 = new Student("maj");
                        Student s4 = new Student("vaj");
                        Student s5 = new Student("paj");
                        List<Student> studentList = new LinkedList();
                        studentList.add(s1);
                        studentList.add(s2);
                        studentList.add(s3);
                        studentList.add(s4);
                        studentList.add(s5);
                        // instead of anonymous class, lambda is being used here as comparator is functional interface
                        // instead of name compare, you can send age compare too. o1.age - o2.age
                        Collections.sort(studentList, (Student o1, Student o2) -> o1.getname().compareTo(o2.getname()));
                        for(Student s: studentList) {
                                System.out.println(s);
                        }
                }
        }


        // with anoymous class
        Collections.sort(studentList, new Comparator<Student>() {
                public int compare(Student s1, Student s2) {
                        return s1.getname().compareTo(s2.getname());
                };
        });


#### Comparable example, logic implemented in the original class


                class Student implements Comparable<Student> {
                        private String name;
                        public Student(String name) {
                                this.name = name;
                        }
                        @Override
                        public String toString() {
                                return this.name;
                        }
                        // not a good idea. doing this for example, take helper method
                        public Student setName(String name) {
                                this.name = name;
                                return this;
                        }
                        public String getname() {
                                return this.name;
                        }

                        @Override
                        public int compareTo(Student o) {
                                return this.name.compareTo(o.name);
                        }

                }

                public class HelloWorld {

                        public static void main(String[] args) {
                                Student s1 = new Student("kaj");
                                Student s2 = new Student("saj");
                                Student s3 = new Student("maj");
                                Student s4 = new Student("vaj");
                                Student s5 = new Student("paj");
                                List<Student> studentList = new LinkedList();
                                studentList.add(s1);
                                studentList.add(s2);
                                studentList.add(s3);
                                studentList.add(s4);
                                studentList.add(s5);
                                Collections.sort(studentList);
                                for(Student s: studentList) {
                                        System.out.println(s);
                                }
                        }
                }


#### TreeSet : custom sort : class should implement Comparable interface

        class Student implements Comparable<Student>{
          private String name;
          public Student(String name) {
            this.name = name;
          }
          @Override
          public String toString() {
            return this.name;
          }
          // not a good idea. doing this for example, take helper method
          public Student setName(String name) {
            this.name = name;
            return this;
          }
          public String getname() {
            return this.name;
          }

          @Override
          public int compareTo(Student o) {		
            return this.name.compareTo(o.name);
          }
        }

        public class TestSort {
          public static void main(String[] args) {
            Student s1 = new Student("kaj");
            Student s2 = new Student("saj");
            Student s3 = new Student("maj");
            Student s4 = new Student("vaj");
            Student s5 = new Student("paj");
            // treeset sort and add only primitive(with autoboxing) types
            // other objects need to implement comparable interface
            TreeSet<Student> ts = new TreeSet();
            ts.add(s1);
            ts.add(s2);
            ts.add(s3);
            ts.add(s4);
            ts.add(s5);
            for(Student s: ts) {
              System.out.println(s);
            }
          }
        }
