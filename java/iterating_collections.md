

package basics;

import java.util.ArrayList;
import java.util.Iterator;
import java.util.List;
import java.util.ListIterator;

class Student

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


using different iterating ways

1. enhanced for loop
2. iterator
3. list iteator
4. forEach (use stream if you want to apply intermediate operation)
5. split iterator

        public class TestIterate {

          public static void main(String[] args) {
            List<Student> myList = new ArrayList<Student>();
            myList.add(new Student("raj"));
            myList.add(new Student("taj"));
            myList.add(new Student("saj"));
            myList.add(new Student("baj"));
            myList.add(new Student("paj"));

            // enhanced for loop
            System.out.println("enhanced for loop");
            for(Student s : myList) {
              System.out.println(s);
            }

            // iterator 
            System.out.println("using iterator");
            Iterator<Student> studentIterator = myList.iterator();
            while(studentIterator.hasNext()) {
              System.out.println(studentIterator.next());
            }

            // list iterator
            System.out.println("using List iterator: only for lists, not for sets and maps");
            System.out.println("top to bottom reading");
            ListIterator<Student> listIterator = myList.listIterator();
            while(listIterator.hasNext()) {
              System.out.println(listIterator.next());
            }
            System.out.println("bottom to top reading");
            while(listIterator.hasPrevious()) {
              System.out.println(listIterator.previous());
            }

            // forEach
            System.out.println("using forEach");
            myList.forEach(s -> System.out.println(s));
            // myList.forEach(System.out::println);

            // list to stream and read from stream
            System.out.println("list to stream and do intermediate operations and print/collect");
            myList.stream().map(s -> s.setName(s.getname().toUpperCase())).forEach(System.out::println);
          }
        }


#### Split iterator

