
#### Encapsulatoin : 

binding data and function together and also controls visibility/accessiblity of data through access specifiers

        Encapsulation in java is a process of wrapping code and data together into a single unit.
        We can create a fully encapsulated class in java by making all the data members of the class private. 
        Now we can use setter and getter methods to set and get the data in it.
        The Java Bean class is the example of fully encapsulated class.
        
        if our class has only setter method : allowed write only. 
        if our class has only getter method : allowed read only.


#### example of Encapsulation

        Fields are private so that value cannot be changed from outside class
        setter methods will validate before value is set
        getter methods will apply logic like conversion/any required format on field and returns value.

      class Product {
        // fields are private, not accessible directly
        private int id;
        private String name;
        private double cost;

        // default constructor

        // setter getters for instance variables
        public int getId() {
          return id;
        }
        public void setId(int id) {
          // validate here
          this.id = id;
        }
        public String getName() {
          return name;
        }
        public void setName(String name) {
          this.name = name;
        }
        public double getCost() {
          return cost;
        }
        public void setCost(double cost) {
          this.cost = cost;
        }	
      }
