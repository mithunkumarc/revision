#### looping maps

model class : Student

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

#### 1. looping map using studentMap.entryset()

        // inside main method
        Student s1 = new Student("kaj");
        Student s2 = new Student("saj");
        Student s3 = new Student("maj");
        Student s4 = new Student("vaj");
        Student s5 = new Student("paj");
        Map<Integer, Student> studentMap = new HashMap();
        studentMap.put(1, s1);
        studentMap.put(2, s2);
        studentMap.put(3, s3);
        studentMap.put(4, s4);
        studentMap.put(5, s5);
        Set<Map.Entry<Integer, Student>> entrySet = studentMap.entrySet();
        for(Map.Entry<Integer, Student> element : entrySet) {
          System.out.println(element.getKey() + ":" + element.getValue());
        }
        /* another simple way
        var entrySet = studentMap.entrySet();
        for(var element: entrySet) {
          System.out.println(element.getKey() +":"+ element.getValue());
        }
        */

#### 2. using iterator

                Student s1 = new Student("kaj");
		Student s2 = new Student("saj");
		Student s3 = new Student("maj");
		Student s4 = new Student("vaj");
		Student s5 = new Student("paj");
		Map<Integer, Student> studentMap = new HashMap();
		studentMap.put(1, s1);
		studentMap.put(2, s2);
		studentMap.put(3, s3);
		studentMap.put(4, s4);
		studentMap.put(5, s5);
		Iterator<Map.Entry<Integer, Student>> iterator = studentMap.entrySet().iterator();
		while(iterator.hasNext()) {
			Entry<Integer, Student> entry = iterator.next();
			System.out.println(entry.getKey() +":"+ entry.getValue());
		}


#### 3. looping map using forEach

        Student s1 = new Student("kaj");
        Student s2 = new Student("saj");
        Student s3 = new Student("maj");
        Student s4 = new Student("vaj");
        Student s5 = new Student("paj");
        Map<Integer, Student> studentMap = new HashMap();
        studentMap.put(1, s1);
        studentMap.put(2, s2);
        studentMap.put(3, s3);
        studentMap.put(4, s4);
        studentMap.put(5, s5);
        // forEach((key, value) -> ...)
        studentMap.forEach((number,student) -> System.out.println(number +":"+ student));

#### looping with stream method map

		Student s1 = new Student("kaj");
		Student s2 = new Student("saj");
		Student s3 = new Student("maj");
		Student s4 = new Student("vaj");
		Student s5 = new Student("paj");
		Map<Integer, Student> studentMap = new HashMap();
		studentMap.put(1, s1);
		studentMap.put(2, s2);
		studentMap.put(3, s3);
		studentMap.put(4, s4);
		studentMap.put(5, s5);
		// immutable, map cannot change state of reading object
		// you can create new object with new value and pass to next step
		// entrySet returns set, so map deals with set of entry objects
		studentMap.entrySet()
				  .stream() // map reads entry and create new Student with new value
				  .map(entry -> new Student(entry.getValue().getname().toUpperCase()))
				  .forEach(System.out::println);

#### hasmap vs hashtable

	HashTable : not supports null as key, methods are synchronized, threadsafe.
	HashMap : null can be used as key, methods aren't synchronized, not threadsafe.
	
	
	HashMap allows one null key and multiple null values whereas 
	Hashtable doesn’t allow any null key or value.

	HashMap is generally preferred over HashTable if thread synchronization is not needed

#### Why HashTable doesn’t allow null and HashMap does?

	To successfully store and retrieve objects from a HashTable, 
	the objects used as keys must implement the hashCode method and the equals method. 
	Since null is not an object, it can’t implement these methods. 
	HashMap is an advanced version and improvement on the Hashtable. 
	HashMap was created later.

#### how hashset works internally
