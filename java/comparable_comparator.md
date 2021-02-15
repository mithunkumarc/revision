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
