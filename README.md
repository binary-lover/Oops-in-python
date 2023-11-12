<h1 align = "center"> Oops-in-python </h1>
    
* **object-oriented Programming** (OOPs) is a programming paradigm that uses objects and classes in programming. It aims to implement real-world entities like inheritance, polymorphisms, encapsulation, etc.
    - The main concept of OOPs is to bind the data and the functions that work on that together as a single unit so that no other part of the code can access this data.
*  **OOPs Concepts in Python**
   - Class
   - Objects
   - Polymorphism
   - Encapsulation
   - Inheritance
   - Data Abstraction

    ![](https://media.geeksforgeeks.org/wp-content/uploads/20230818181616/Types-of-OOPS-2.gif)

* **The Python self**
    - Class methods must have an extra first parameter in the method definition. We do not give a value for this parameter when we call the method, Python provides it
    - If we have a method that takes no arguments, then we still have to have one argument.
    - This is similar to this pointer in C++ and this reference in Java.

      ```
      # Creating Class
      class Student:
          # Creating A sonstructor
          def __init__(self,name,cls,roll_no):
              self.name = name
              self.cls = cls
              self.roll_no = roll_no
          # Creating a funtion that print information of the person
          def info(self):
              print(f"Student's name is {self.name}, who studies in class {self.cls} and roll no {self.roll_no}")
      
      # Creating an object
      a = Student("lucky","BSC H CS",1351)
      
      # Creating another object
      b = Student("Aman","BSC H Maths", 3432)
      
      # Calling info() from class
      a.info()
      b.info()
      
      # Chainging the name of Student a
      a.name = "mohit"
      a.info()

      ```
    - Another Example:

      ```
      class Dog:

    	# class attribute
    	attr1 = "mammal"
    
    	# Instance attribute
    	def __init__(self, name):
    		self.name = name
    		
    	def speak(self):
    		print("My name is {}".format(self.name))
    
      # Driver code
      # Object instantiation
      Rodger = Dog("Rodger")
      Tommy = Dog("Tommy")
      
      # Accessing class methods
      Rodger.speak()
      Tommy.speak()

      ```

* **Python Class**
    - A class is a collection of objects. A class contains the blueprints or the prototype from which the objects are being created. It is a logical entity that contains some attributes and methods.

      ```
      #Python3 program to
      #demonstrate defining
      #a class
 
      class Dog:
          pass
      ```
* **Python Object**
    - The object is an entity that has a state and behavior associated with it. It may be any real-world object like a mouse, keyboard, chair, table, pen, etc

      ```
      obj = Dog()
      ```

* **Encapsulation :** -  It describes the idea of wrapping data and the methods that work on data within one unit. This puts restrictions on accessing variables and methods directly and can prevent the accidental modification of data.
  
  ![](https://www.boardinfinity.com/blog/content/images/2022/12/Your-paragraph-text--77-.jpg)
  
    - **Protected Members :** -  members of the class that cannot be accessed outside the class but can be accessed from within the class and its subclasses. To accomplish this in Python,it can be done by prefixing the name of the member by a single underscore “_”.
      
      ```
        # Python program to 
        # demonstrate protected members 
          
        # Creating a base class 
        class Base: 
            def __init__(self): 
          
                # Protected member 
                self._a = 2
          
        # Creating a derived class 
        class Derived(Base): 
            def __init__(self): 
          
                # Calling constructor of 
                # Base class 
                Base.__init__(self) 
                print("Calling protected member of base class: ",  
                      self._a) 
          
                # Modify the protected variable: 
                self._a = 3
                print("Calling modified protected member outside class: ", 
                      self._a) 
          
          
        obj1 = Derived() 
          
        obj2 = Base() 
          
        # Calling protected member 
        # Can be accessed but should not be done due to convention 
        print("Accessing protected member of obj1: ", obj1._a) 
          
        # Accessing the protected variable outside 
        print("Accessing protected member of obj2: ", obj2._a) 
      ```
  - **Private Members :** - Private members are similar to protected members, the difference is that the class members declared private should neither be accessed outside the class nor by any base class. To define a private member prefix the member name with double underscore “__”.
        ```
        # Python program to 
        # demonstrate private members 
          
        # Creating a Base class 
          
          
        class Base: 
            def __init__(self): 
                self.a = "GeeksforGeeks"
                self.__c = "GeeksforGeeks"
          
        # Creating a derived class 
        class Derived(Base): 
            def __init__(self): 
          
                # Calling constructor of 
                # Base class 
                Base.__init__(self) 
                print("Calling private member of base class: ") 
                print(self.__c) 
          
          
        # Driver code 
        obj1 = Base() 
        print(obj1.a) 
          
        # Uncommenting print(obj1.c) will 
        # raise an AttributeError 
          
        # Uncommenting obj2 = Derived() will 
        # also raise an AttributeError as 
        # private member of base class 
        # is called inside derived class 
        ```
  
* **Python Inheritance :** - Inheritance is the capability of one class to derive or inherit the properties from another class. The class that derives properties is called the derived class or child class and the class from which the properties are being derived is called the base class or parent class.
  - The benefits of inheritance are:
      - t represents real-world relationships well.
      - It provides the reusability of a code. We don’t have to write the same code again and again. Also, it allows us to add more features to a class without modifying it.
      - It is transitive in nature, which means that if class B inherits from another class A, then all the subclasses of B would automatically inherit from class A.
  - Types of Inheritence are:
      - **Single Inheritence :**
          - Single-level inheritance enables a derived class to inherit characteristics from a single-parent class.
    - **Multilevel Inheritance:** Multi-level inheritance enables a derived class to inherit properties from an immediate parent class which in turn inherits properties from his parent class. 
    - **Hierarchical Inheritance:** Hierarchical-level inheritance enables more than one derived class to inherit properties from a parent class.
    - **Multiple Inheritance:** Multiple-level inheritance enables one derived class to inherit properties from more than one base class.

* **Inheritence In Python :** - two classes i.e. Person (parent class) and Employee (Child Class). The Employee class inherits from the Person class. We can use the methods of the person class through the employee class as seen in the display function in the above code. A child class can also modify the behavior of the parent class as seen through the details() method.
  
    - Here we are with an example:
      
      ```
        class Parentcls:
        def __init__(self,name,place):
            self.name = name
            self.place = place
            
        def info(self):
            print(f"parent name is {self.name}, lives in {self.place}")
        
        class Child(Parentcls):
            def showhobby(self):
                print(f"{self.name}'s hobby is palying football")
            # def __init__(self, name, place):
            #     super().__init__(name, place)
            
        p1 = Child("lucky","delhi")
        p1.info()
        p1.showhobby()
      ```

    - Another Example:
      
      ```
      # Python code to demonstrate how parent constructors
      # are called.
      
      # parent class
      class Person(object):
      
      	# __init__ is known as the constructor
      	def __init__(self, name, idnumber):
      		self.name = name
      		self.idnumber = idnumber
      
      	def display(self):
      		print(self.name)
      		print(self.idnumber)
      		
      	def details(self):
      		print("My name is {}".format(self.name))
      		print("IdNumber: {}".format(self.idnumber))
      	
      # child class
      class Employee(Person):
      	def __init__(self, name, idnumber, salary, post):
      		self.salary = salary
      		self.post = post
      
      		# invoking the __init__ of the parent class
      		Person.__init__(self, name, idnumber)
      		
      	def details(self):
      		print("My name is {}".format(self.name))
      		print("IdNumber: {}".format(self.idnumber))
      		print("Post: {}".format(self.post))
      
      
      # creation of an object variable or an instance
      a = Employee('Rahul', 886012, 200000, "Intern")
      
      # calling a function of the class Person using
      # its instance
      a.display()
      a.details()
      ```

  <em>these Notes are derived from GFG</em>
        
