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
    





