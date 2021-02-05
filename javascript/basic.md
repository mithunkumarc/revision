#### script tag : 

      recommeded , place at the bottom of body

#### external file : 

      import in html
      <script src="myScript1.js"></script>

#### Display output : 

      document.getElementById("demo").innerHTML = 5 + 6;
      Writing into the HTML output using document.write(). // deletes existing html  	
      Writing into an alert box, using window.alert().
      Writing into the browser console, using console.log().	


#### window object : 

      window object is the global scope object, that means that variables, properties, 
      and methods by default belong to the window object. 
      This also means that specifying the window keyword is optional

#### identifiers : 

      In JavaScript, the first character must be a letter, or an underscore (_), or a dollar sign ($).

      Subsequent characters may be letters, digits, underscores, or dollar signs.

      Hyphens are not allowed in JavaScript. They are reserved for subtractions.

      A letter (A-Z or a-z)
      A dollar sign ($)
      Or an underscore (_)


#### variables

      var let const
      use let/const, var has redelaring problems


      A variable declared without a value will have the value undefined.

        var x = 10;
        // Here x is 10
        {
          var x = 2;
          // Here x is 2
        }
        // Here x is 2


#### Hoisting : 

        Variables defined with var are hoisted to the top and can be initialized at any time

          carName = "Volvo";
          alert(carName);
          var carName;

####  const : 

        const variable cannot be reinitialized
        const variable cannot point to other value/object
        state of object can be changed



####  only in case of var 

        If you re-declare a JavaScript variable, it will not lose its value.


#### string concat 

        left to right : "5" + 2 + 3: 523
        2 + 3 + "5": 55
	
	
####  underscore with variable : 

        Using the underscore is not very common in JavaScript, 
        but a convention among professional programmers is to use it 
        as an alias for "private (hidden)" variables.

#### datatypes 

        number
        boolean
        string
        function
        object 
        symbol
        undefined 
        null : typeof null : object 
        null == undefined : true, null === undefined : false

#### function

        parameters
        arugments
        call
        return

#### self call function : immediately called function

        (function name(){ console.log("hello world");})()

#### creating object :

        1. functional constructor , using new operator
        2. object literal : {}

#### accessing property

        objectName.propertyName
        or
        objectName["propertyName"]

#### this keyword : 

        In a method, this refers to the owner object.
          var person = {
            firstName: "John",
            lastName : "Doe",
            id       : 5566,
            fullName : function() {
            return this.firstName + " " + this.lastName;
            }
          };
          
        Alone, this refers to the global object.
          var x = this;

        In a function, this refers to the global object.
          function myFunction() {
            return this;
          }
          
        In a function, in strict mode, this is undefined.
          "use strict";
          function myFunction() {
            return this;
          }
          
        In an event, this refers to the element that received the event.
          <button onclick="this.style.display='none'">
            Click to Remove Me!
          </button>
        Methods like call(), and apply() can refer this to any object.


####  don't create primitive type objects, use literals


        Do Not Declare Strings, Numbers, and Booleans as Objects!
        When a JavaScript variable is declared with the keyword "new", the variable is created as an object:
        Don't create strings as objects. It slows down execution speed.
        The new keyword complicates the code. This can produce some unexpected results:

        var x = new String();        // Declares x as a String object
        var y = new Number();        // Declares y as a Number object
        var z = new Boolean();       // Declares z as a Boolean object

#### Events 

        HTML events are "things" that happen to HTML elements.



#### comparing using == and ===

        == : compares only values
        === : compares values with types (strict compare)

#### string methods 

        substring(start, end)
        substr(start, length)

#### type coercion, parse

        Boolean(1);     //number to boolean
        true

        String(123);    //number to string
        "123"

        Number('345') + 4     //string to number
        349

        with prefix +, type will be number
            typeof +"1"
            "number"
	
#### array : 

        var cars = new Array("Saab", "Volvo", "BMW");

        use this : var cars = ["Saab", "Volvo", "BMW"];

#### difference between object and array 

        arrays use numbered indexes.  
        objects use named indexes.


#### array methods 

        [].join(" * ");
        The pop() method removes the last element from an array:
        The push() method adds a new element to an array (at the end):
        The push() method returns the new array length:
        The shift() method removes the first array element and "shifts" all other elements to a lower index.
        delete fruits[0];  Using delete may leave undefined holes in the array. Use pop() or shift() instead.
        arr.splice(start[, deleteCount[, item1[, item2[, ...]]]])
          fruits.splice(2, 2, "Lemon", "Kiwi");
        merging :  myGirls.concat(myBoys); 
        The slice() method slices out a piece of an array into a new array.
          arr.slice([start[, end]])
        The slice() method creates a new array. It does not remove any elements from the source array.
        arr.sort([compareFunction])

#### loops

        for...in : reads index, use array reference to read value
        for...of : directly reads values from array 


#### math random dates

        tobe updated

#### json : parse, stringify

        tobe updated

##### ES5 Features

          "use strict"
          String.trim()
          Array.isArray()
          Array.forEach()
          Array.map()
          Array.filter()
          Array.reduce()
          Array.reduceRight()
          Array.every()
          Array.some()
          Array.indexOf()
          Array.lastIndexOf()
          JSON.parse()
          JSON.stringify()
          Date.now()
          Property Getters and Setters
          New Object Property Methods

#### ES6

          The let keyword
          The const keyword
          JavaScript Arrow Functions: map filter reduce
          JavaScript For/of
          JavaScript Classes
          JavaScript Promises : async : await : resove,reject,catch
          JavaScript Symbol : const: can be used as property of object 
          Default Parameters: default values to function params
          Function Rest Parameter: remaining params considered as array 
          Array.find(): 
          Array.findIndex()
          New Number Properties
          New Number Methods
          New Global Methods
          JavaScript Modules

#### 2016

        JavaScript Exponentiation (**)
        JavaScript Exponentiation assignment (**=)
        JavaScript Array.prototype.includes


#### 2017

        JavaScript String padding
        JavaScript Object.entries
        JavaScript Object.values
        JavaScript async functions
        JavaScript shared memory

#### 2018

        > Asynchronous Iteration
          for await () {}


        > Promise Finally  
        let myPromise = new Promise();
        myPromise.then();
        myPromise.catch();
        myPromise.finally();

      > Object Rest Properties

        let { x, y, ...z } = { x: 1, y: 2, a: 3, b: 4 };
        x; // 1
        y; // 2
        z; // { a: 3, b: 4 }

        >New RegExp Features


####  object constructors 

        function Person(first, last, age, eye) {
          this.firstName = first;
          this.lastName = last;
          this.age = age;
          this.eyeColor = eye;
        }
        var myFather = new Person("John", "Doe", 50, "blue");

        It is considered good practice to name constructor functions with an upper-case first letter.

        In JavaScript, the thing called this is the object that "owns" the code.

        The value of this, when used in an object, is the object itself.


#### prototype : 

        All JavaScript objects inherit properties and methods from a prototype.

        The JavaScript prototype property also allows you to add new methods to objects constructors:

          Person.prototype.nationality = "English";


####  ES5 object methods 

        // Adding or changing an object property
        Object.defineProperty(object, property, descriptor)

        // Adding or changing many object properties
        Object.defineProperties(object, descriptors)

        // Accessing Properties
        Object.getOwnPropertyDescriptor(object, property)

        // Returns all properties as an array
        Object.getOwnPropertyNames(object)

        // Returns enumerable properties as an array
        Object.keys(object)

        // Accessing the prototype
        Object.getPrototypeOf(object)

        // Prevents adding properties to an object
        Object.preventExtensions(object)
        // Returns true if properties can be added to an object
        Object.isExtensible(object)

        // Prevents changes of object properties (not values)
        Object.seal(object)
        // Returns true if object is sealed
        Object.isSealed(object)

        // Prevents any changes to an object
        Object.freeze(object)
        // Returns true if object is frozen
        Object.isFrozen(object)


####  __proto__ link between our object and its prototype 

        or proto points to prototype 
        __proto__ is internal property of an object, pointing to its prototype.


#### call vs apply

        theFunction.apply(valueForThis, arrayOfArgs)
        theFunction.call(valueForThis, arg1, arg2, ...)

#### closure : 

        internal state , not allowed to manipulate from outside
        read only

#### A transpiler : eg : babel

        is a special piece of software that can parse (“read and understand”) 
        modern code, and rewrite it using older syntax constructs, 
        so that the result would be the same.

        eg : nullish coalescing operator
        // before running the transpiler
        height = height ?? 100;

        // after running the transpiler
        height = (height !== undefined && height !== null) ? height : 100;


#### A polyfill 

        is a piece of code (usually JavaScript on the Web) used to provide 
        modern functionality on older browsers that do not natively support it.

#### polyfill vs transpiler

        A polyfill will try to emulate certain APIs, so can use them as if they were already implemented.

        A transpiler on the other hand will transform your code and 
        replace the respective code section by other code, 
        which can already be executed.

#### compiling vs transpiling

        Transpilation = translate + compilation.


        Compiling: code from a high level language is get 
        converted to machine level language.

        Transpiling: code from a high level language gets 
        converted to another high level language.

        The typescript compiler compiles typescript code into JavaScript.

        A good example of transpiler is the Typescript transpiler, which converts Typescript code to JavaScript. 
        Babel transpiler can also be used for ES6 JS code to ES5 JS code.

#### webpack : 

        a dependency analyzer and module bundler.
        When webpack processes dependencies, it must turn everything 
        into javascript because webpack works on top of javascript. 
        As a result, it uses different loaders to translate different 
        types of resources/code into javascript. When we need ES6 or ES7 features, 
        we use babel-loader to accomplish this.

#### Symbol : 

        constants, no two symbols are same 
        used as property of object
        cannot be read using for...in 
        we can access only if we know
        hidden from other scripts(others js files)
        its like internal purpose

#### object entries

        Object.entries(obj).forEach(([key, value]) => console.log(`${key}: ${value}`)); 

#### map vs weakmap

        var k1 = {a: 1};
        var k2 = {b: 2};

        var map = new Map();
        var wm = new WeakMap();

        map.set(k1, 'k1');
        wm.set(k2, 'k2');

        k1 = null;
        map.forEach(function (val, key) {
            console.log(key, val); // k1 {a: 1}
        });

        k2 = null;
        wm.get(k2); // undefined


#### generators

      tobe updated

#### modules, export and import

      > default export

      > dynamic import (may be similar to lazy loading)

#### mixim  :similar to interface in java, no instance fields/only methods

          // mixin
          let sayHiMixin = {
            sayHi() {
            alert(`Hello ${this.name}`);
            },
            sayBye() {
            alert(`Bye ${this.name}`);
            }
          };

          // usage:
          class User {
            constructor(name) {
            this.name = name;
            }
          }

        // copy the methods
          Object.assign(User.prototype, sayHiMixin);
          // sayHi Bye available to User

          * no point in creating instance of mixin, as no instance fields
	
#### use await for expression which is giving promise object 

        let result = await (expression should return promise);
        let finalResult = await result.getAnotherPromise();

#### ajax vs fetch

      > ajax : callback
      > fetch : promises : 

        The major difference is that Fetch works with promises, not callbacks. 
        JavaScript developers have been moving away from callbacks after the 
        introduction of promises.

#### fetch handle error

        function handleErrors(response) {
            if (!response.ok) {
                throw Error(response.statusText);
            }
            return response;
        }


          fetch("http://httpstat.us/500")
              .then(handleErrors)
              .then(function(response) {
                  console.log("ok");
              }).catch(function(error) {
                  console.log(error);
              });

##### fetch post request

            // data to be sent to the POST request
            let _data = {
              title: "foo",
              body: "bar", 
              userId:1
            }

            fetch('https://jsonplaceholder.typicode.com/posts', {
              method: "POST",
              body: JSON.stringify(_data),
              headers: {"Content-type": "application/json; charset=UTF-8"}
            })
            .then(response => response.json()) 
            .then(json => console.log(json));
            .catch(err => console.log(err));

