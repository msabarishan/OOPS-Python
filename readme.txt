#OOPs-Object Oriented Programming System
#Python also supports OOPs.
#There are two major terminologies that should be known before entering OOPs concept, 1. Class 2.Object
#Class: Class contains the attributes (variables) and behaviour(methods-In the context of class, functions will be called as methods)
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

