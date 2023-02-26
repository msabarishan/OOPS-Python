#OOPs-Object Oriented Programming System
#Python also supports OOPs.
#There are two major terminologies that should be known before entering OOPs concept, 1. Class 2.Object
#Class: A Class is like an object constructor, or a "blueprint" for creating objects.
        Class contains the attributes (variables) and behaviour(methods-In the context of class, functions will be called as methods)
      There are two different types of class. 1. In-built Class 2. User Defined / Extrinsic Class
      1. Inbuilt Class:
                      These class are already available as in-built function in Python. Eg: int,str
                      
                      Codes for Verifying:
                      
                      a=5
                      print(type(a))
                      
                      output: <class 'int'>
                      Explanantion: Here object a is assigned with int class
     2.User Defined Class:
                      These class are defined and executed through coding in Python. Eg: Refer below codes
                      
                      Codes for Verifying:
                      
                      class student:
                      def dept(self):
                          self.dept='Science'
                          return  self.dept
                          
                      stud1=student()
                      stud1_dept=stud1.dept()
                      print(stud1_dept)
                      print(type(stud1))
                      
                      output: Science
                              <class '__main__.student'>
                      Explanantion: Here a new class student is formed and object stud1 is assigned to the student class.
                      
#Object: Object is an instance of a class.Everying in python is almost an object. Objects are already mentioned in the above examples.

#Different ways of calling class,

      Codes:
      
      class student:
          def dept(self):
              self.dept='Science'
              return  self.dept
          
      stud1=student()
      stud2=student()
      # Method1 (Mostly used)
      stud1_dept=stud1.dept()
      # Method2 
      stud2_dept=student.dept(stud2)
      
      print(stud1_dept)
      print(stud2_dept)
      
      Output:
      
      Science
      Science
      
#__init__ method in Python:
      This method is automatically executed when a class is called.
      
      Codes:
      
      #_inint_method

      class computer:
          
          def __init__(self,core,ram):
              self.core=core
              self.ram=ram
          def spec(self):
              print(self.core,self.ram)
      
      comp1=computer('i5','10GB')
      comp2=computer('i7','16GB')
      
      comp1.spec()
      comp2.spec()
      
      Output:
      i5 10GB
      i7 16GB
      
#Constructer:
   It determines how much memory needs to allocated for an object and this memory depends on the number of variables. "stud1=student()"    is called constructed. Whenever this code is executed the __init__ method is called allocating memory based on number of variables.      These are stored in heap memory.
   
# Self:
    The object itself is passed as self along with the mentioned arguments.
    
    Eg:
    
    Codes:
      # Constructor, self and compare

      class computer:
          
          def __init__(self,core,ram):
              self.core=core
              self.ram=ram
              
          def comp(self,other):
              if(self.ram == other.ram):
                  return True
              else:
                  return False
          
      comp1=computer('i5','10GB')
      comp2=computer('i7','10GB')
      
      
      if (comp1.comp(comp2)):
          print("Both have same Ram")
      else:
          print("Both have different Ram")
          
     Explanation:
     When comp1=computer('i5','10GB') is executed the memory for two variables core and ram is allocated. For comparison comp1 is passed      as self and comp2 is passed as other argument.
 
 # Types of variable:
      1. Instance Variable
      2. Static/Class Variable
      
      Eg:
      
      Codes:
      
      #Typed of variable
     # instance variable
     
     class computer:
         
         brand='Acer'
         
         def __init__(self,core,ram):
             self.core=core
             self.ram=ram
             
         
     comp1=computer('i5','10GB')
     comp2=computer('i7','16GB')
     
     # Modifying instance Variable
     comp2.ram="32GB"
     #Modifying class/ static variable
     computer.brand='Lenovo'
     
     print(comp1.brand,comp1.core,comp1.ram)
     print(comp2.brand,comp2.core,comp2.ram)
     
     Explanantion:
     
     In the above example brand is class variable, core and ram are instance variable.
     
#Types of Methods:

     1. Instance Method
     2. Class Method
     3. Static Method
     
     1. Instance Method: Types: 1.Accessor 2.Mutator
     
     Eg:
        #types of methods
        #instance method
        
        class student:
            def __init__(self,s):
                self.score=s
            def average(self,other):
                return ((self.score+other.score)/2)      
                
        student1=student(100)
        student2=student(80)
        
        print(student1.average(student2))
        
        1. Accessor Method:
        
             class student:
                 def __init__(self,s):
                     self.score=s
                 def average(self,other):
                     return ((self.score+other.score)/2)
                 
                 #get_score is accessor method
                 def get_score(self):
                     return self.score
                 #get_score is mutator method
                 def set_score(self,value):
                     self.score=value
                     
             student1=student(100)
             student2=student(80)
             
             print(student2.get_score())
             
       2. Mutator Method:
       
             class student:
                 def __init__(self,s):
                     self.score=s
                 def average(self,other):
                     return ((self.score+other.score)/2)
                 
                 #get_score is accessor method
                 def get_score(self):
                     return self.score
                 #get_score is mutator method
                 def set_score(self,value):
                     self.score=value
                     
             student1=student(100)
             student2=student(80)
             
             student2.set_score(120)
             
             print(student1.average(student2))
             
    # 2. Class Method:
    
         Eg:
         
         Codes:
         
         class student:
             college ="GCT"
             def __init__(self,s):
                 self.score=s
             def average(self,other):
                 return ((self.score+other.score)/2)
             
             #get_score is accessor method
             def get_score(self):
                 return self.score
             #get_score is mutator method
             def set_score(self,value):
                 self.score=value
             
             # @ Decorator
             @classmethod
             def get_clg(cls):
                 return cls.college
             
                 
         student1=student(100)
         student2=student(80)
         
         student2.set_score(120)
         
         print(student.college)
         
         Explanation: Use decorator for defining class method. This method is used especially to call class variables.
    
    #3. Static Method:
        This method is used when there is no requirement for calling static or instance variable.
        
      Eg:
       Codes:
                   
       class student:
           college ="GCT"
           def __init__(self,s):
               self.score=s
           def average(self,other):
               return ((self.score+other.score)/2)
           
           #get_score is accessor method
           def get_score(self):
               return self.score
           #get_score is mutator method
           def set_score(self,value):
               self.score=value
               
           # @ Decorator
           @staticmethod   
           def clg_loc():
               print("GCT is located at Coimbatore, Tamilnadu")
           
               
       student1=student(100)
       student2=student(80)
       
       student2.set_score(120)
       
       student.clg_loc()
       
#Inner Class:
       A class is nested inside a class. This can be used only if the nested class not used anywhere else.
       
       Eg: Codes
       
         class computer:
             
             def __init__(self):
                 self.core='i5'
                 self.ram='8GB'
                 self.make=self.make()
                 
             class make:
                 def __init__(self):
                     self.brand="Acer"
                     self.make="India"
             
         comp1=computer()
         comp2=computer()
         
         print(comp1.make.brand,comp1.core)
         
         
#Inheritance:

Two Major Terms: 1. Super-Class (Parent Class) 2. Sub-Class (Child Class).
Sub-class can in-herit the features of superclass but vice-versa is not possible.

Three types: 1. Single Level 2.Mutli-level 3.Multiple
    1. Single Level In-heritance: One class is passes to the next class. In below example Class A is super class and Class B is sub-class. Class B inherit the feature of Class A.

    Codes:
       class classA:
           
           def __init__(self):
               print("this is class A")
               
           def feature1(self):
               print("this is feature 1")
               
           def feature2(self):
               print("this is feature 2")
       
               
       class classB(classA):
               
           def feature3(self):
               print("this is feature 3")
               
           def feature4(self):
               print("this is feature 4")
               
       b=classB()
       
       b.feature1()
       
   2.Multilevel Inheritance: The  immediate super class of child class is also a child class of another super class. In below example: Class C inherit the features of class A and class B also class B inherit the feature of class A
   
     Codes:
       
       class classA:
           
           def __init__(self):
               print("this is class A")
               
           def feature1(self):
               print("this is feature 1")
               
           def feature2(self):
               print("this is feature 2")
       
               
       class classB(classA):
               
           def feature3(self):
               print("this is feature 3")
               
           def feature4(self):
               print("this is feature 4")
               
       class classC(classB):
               
           def feature5(self):
               print("this is feature 5")
               
               
       c=classC()
       
       c.feature1()
       
   3.Multiple Inheritance: A sub-class having more than one immediate super class. In the below example, class C is inherit the features of class A and class B, also      Class B and Class C are independent.
   
     Eg:
     
     Codes:
     #multiple inheritance

     class classA:
         
         def __init__(self):
             print("this is class A")
             
         def feature1(self):
             print("this is feature 1")
             
         def feature2(self):
             print("this is feature 2")
     
             
     class classB():
             
         def feature3(self):
             print("this is feature 3")
             
         def feature4(self):
             print("this is feature 4")
             
     class classC(classA,classB):
         
         def __init__(self):
             print("this is class C")
             
         def feature5(self):
             print("this is feature 5")
             
             
     c=classC()
     
     c.feature1()
     c.feature3()
    
# Constructor Inheritance & Method Resolution Order (MRO):
  Priority:
  1. Multilevel or Single level inheritance: First priority is given to sub-class. If there is no constructor in sub-class, then constructor of super class is
     inherited by subclass. Incase there are multiple level of inheritance, the priority goes from immediate successor to farthest successor
     
  2. Multiple inheritance: First priority is given to sub-class. If there is no constructor in sub-class, then constructor of super class is
     inherited by subclass. If there are more than one super class, the priority goes from left to right (MRO).
     
  Codes:
  
  The level of priority can be understood  with the help of below codes,
  
        class classA:
          # This is constructor of A
          def __init__(self):
              print("this is class A")
              
          def feature1(self):
              print("this is feature 1")
              
          def feature2(self):
              print("this is feature 2")
              
        class classB(classA):
            # This is constructor of B
            def __init__(self):
                print("this is class B")
                
            def feature3(self):
                pass
                
            def feature4(self):
                pass
                
        class classC(classA):  
            def feature5(self):
                pass
                
        class classD(classB):  
            def feature6(self):
                pass
            
        class classF():  
            
            def __init__(self):
                print("this is class F")
                
            def feature7(self):
                pass
                
        class classE(classA,classF):
            def feature7(self):
                pass
        # class C does not have constructor        
        c=classC()
        # class B does  have constructor 
        b=classB()
        # class D does not have constructor and its immediate successor is class B 
        d=classD()
        # class E does not have constructor and left most constructor is class A
        e=classE()
        
  super(): This is used for inheriting the constructor of multiple super class. It can be also used to pass the methods of superclass (which is not inherited due to              similar name)
  
  Codes:
  1.Multilevel inheritance:
  
    class classA:
        # This is constructor of A
        def __init__(self):
            print("this is class A")
            
        def feature1(self):
            print("this is feature 1")
            
        def feature2(self):
            print("this is feature 2")
    
            
    class classB(classA):
        # This is constructor of B
        def __init__(self):
            super().__init__()
            print("this is class B")
            
    
            pass
    b=classB()
   
 2.Multiple Inheritance:
   Codes:
      # constructor inheritance-super().__init__ : Multilevel
      class classA:
          # This is constructor of A
          def __init__(self):
              print("this is class A")
          
      class classF():  
          
          def __init__(self):
              print("this is class F")
              
          def feature1(self):
              print("This is class F feature1")
              
      class classE(classA,classF):
          def __init__(self):
              super().__init__()
              print("this is class E")
          
          def feature1(self):
              print("This is class E feature1")
              
          def feat(self):
              super().feature1()
      
      e=classE()
      e.feat()
      
      
 #Polymorphism: The concept of Polymorphism denotes to object taking multiple  form. 
 1. Duck Typing 2. Operator Overloading 3. Method Overloading 4.
 
     1. Duck Typing:
        
       IDE: Generally Integrated Development Environments (IDEs) are coding tools that make writing, debugging, and testing your code easier (eg VS code, Pycharm). In             context of OOPs, Integrated development environments (IDE) are applications that facilitates the development of other applications.
             
    #Polymorphism -Duck Typing
    Eg: Codes:
    
    class vscode:
        def execute(self):
            print("Compiled Successfully")
            
    class test:
        def result(self,ide):
            ide.execute()
        
    vscode_ide=vscode()
    test1=test()
    test1.result(vscode_ide)
    
    Explanantion: Here execute is a method of class vscode. There is no inheritance between class test and class vscode. Still the method execute is called through                     class test by passing the execute method as ide.
    
    #Polymorphism -Operator Overloading : This involves redefining the function of operators (lik '+,'-') in a class.
    Eg: Codes:
    
      class cars:
    
          def __init__(self,cost,tax):
              self.cost=cost
              self.tax=tax
          def __add__(self,other):
              cost=self.cost+other.cost
              tax=self.tax+other.tax
              total=cars(cost,tax)
              return total
          
      car1=cars(10000,1800)
      car2=cars(20000,4000)
      
      total=car1+car2
      
      print(total.tax)
    
 
        
  
   




             





