**Unit 7: Runtime Environment** <span id="7"></span> 
*Runtime* *environment considerations include organization* *of the
compiled program, storage,* *building blocks of a compiled program, and*
*different runtime configurations. * *This unit has some overlap with
Unit 8.  The emphasis in this unit is on representation of needed data
structures and techniques for objects and inheritance.  The emphasis of
Unit 8 is on instruction generation.  *

**Unit 7 Time Advisory**  
This unit should take approximately 14 hours to complete.  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 7.1: 8 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 7.2: 2 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 7.3: 4 hours 

**Unit7 Learning Outcomes**  
Upon successful completion of this unit, the student will be able to:  
  
-   <span dir="LTR">Describe the role of intermediate representation and
    runtime environments in the compilation process.</span>
-   <span dir="LTR">Explain the encoding of data structures in runtime
    memory.</span>
-   <span dir="LTR">Explain the encoding of procedures, functions, and
    parameters at runtime.</span>
-   <span dir="LTR">Explain how objects, inheritance, and exceptions are
    encoded at runtime.</span>

**7.1 Overview of Runtime Environments** <span id="7.1"></span> 
-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Handout 22: “Runtime Environments”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Handout
    22: “[Runtime
    Environments](http://www.keithschwarz.com/cs143/WWW/sum2011/)”
    (PDF)  
        
     Instructions: Select the PDF for Handout 22.  Read the handout,
    which discusses data representations and their organization in
    memory for a program.  This reading also applies to subunits 7.1.3
    through 7.1.5 below.  After semantic analysis, intermediate
    representations are encoded.  This is the last step of the
    “front-end” of the compilation process.  The relationship of front
    ends to back ends can be many-to-one or one-to-many.  In the former
    case, a single back end is used for several languages, each handled
    by its own front end.  In the latter case, one front end handles the
    input, source language, and the back end is used for several target
    machines, each having its own back end.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**7.1.1 Functions and Requirements of Intermediate Representation (IR)**
<span id="7.1.1"></span> 
-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Lecture 11: “Runtime Environments”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Lecture
    11: “[Runtime
    Environments](http://www.keithschwarz.com/cs143/WWW/sum2011/)”
    (PDF)  
        
     Instructions: Select the PDF for Lecture 11.  Read the functions of
    IR generation on slides 6 and 7.  Some requirements for IR
    generation are on slide 8.   
      
     Note: This reading applies to 7.1.2.  Slides 9 through 18 present a
    generic design for IR generation.  Note: This reading also applies
    to 7.1.3.   
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**7.1.2 Design of the IR Step** <span id="7.1.2"></span> 
*Note: The reading of 7.1.1 applies to this subunit.*

**7.1.3 Data Structure Encoding in Memory** <span id="7.1.3"></span> 
*Note: The reading of 7.1 applies to this subunit.  Encoding of
primitive types and arrays are discussed.  From the 7.1.1 reading, see
slides 19 through 37 for additional coverage. *

**7.1.4 Scope and Extent of Variables** <span id="7.1.4"></span> 
*Note: The reading of 7.1 applies to this subunit.  Scope of a variable
is the lexical area of a program in which the variable can be used. 
Extent, or lifetime, is the period of time that a variable exists.  *

**7.1.5 Runtime Stack and Parameter Passing** <span id="7.1.5"></span> 
*Note: In addition to the following reading, the reading of 7.1 applies
to this subunit.*

-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Lecture 11: “Runtime Environments”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Lecture
    11: “[Runtime
    Environments](http://www.keithschwarz.com/cs143/WWW/sum2011/)”
    (PDF)  
        
     Instructions: Select the PDF for Lecture 11.  See slides 38 through
    118 for a discussion of the stack, activation trees, closure and
    coroutines, and parameter passing.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above. 

-   **Reading: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Notes for Lecture 25 “Run-time
    Organization”**
    Link: University of California, Berkeley: Paul Hilfinger’s CS164
    Programming and Compilers: Notes for Lecture 25 “[Run-time
    Organization](http://inst.eecs.berkeley.edu/~cs164/sp11/lectures/)”
    (PDF)  
      
     Instructions: Select the PDF link for the notes for Lecture 25. 
    This reading continues the topic of 7.1, with some differences.  In
    this presentation, IR is treated as part of code generation, and it
    has a lot of detail on the run-time encoding for procedures and
    functions.  
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Web Media: YouTube: University of California, Berkeley: Paul
    Hilfinger’s CS164 Programming and Compilers: Video Lectures:
    “Lecture 25,” “Lecture 26,” “Lecture 27”**
    Link: YouTube: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Video Lectures: “[Lecture
    25](http://www.youtube.com/watch?v=Tuip6xANn_4),” (YouTube)
    “[Lecture 26](http://www.youtube.com/watch?v=x22P9w_O_RI),”
    (YouTube) “[Lecture 27](http://www.youtube.com/watch?v=_U0Y3ZsDUcI)”
    (YouTube)  
      
     Instructions: Please view the lectures above.   
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpages above.

**7.2 More Complicated Representations: Objects and Inheritance** <span
id="7.2"></span> 
-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Lecture 12: “Runtime Environments II”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Lecture
    12: “[Runtime Environments
    II](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF)  
        
     Instructions: Select the PDF for Lecture 12.  Read the lecture
    slides.  Encoding of objects, inheritance, and dynamic type checking
    are described, including difficulties and solutions.   
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**7.3 Encoding of Exceptions and OOP (Object-Oriented Programs)** <span
id="7.3"></span> 
-   **Reading: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Notes for Lecture 28 “Exceptions,
    OOP”**
    Link: University of California, Berkeley: Paul Hilfinger’s CS164
    Programming and Compilers: Notes for Lecture 28 “[Exceptions,
    OOP](http://inst.eecs.berkeley.edu/~cs164/sp11/lectures/)” (PDF)  
      
     Instructions: Select the PDF link for the notes for Lecture 28. 
    This reading continues the topic of 7.2.   
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Web Media: YouTube: University of California, Berkeley: Paul
    Hilfinger’s CS164 Programming and Compilers: Video Lectures:
    “Lecture 28,” “Lecture 29,” “Lecture 30”**
    Link: YouTube: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Video Lectures: “[Lecture
    28](http://www.youtube.com/watch?v=NG-WEI9oA34),” (YouTube)
    “[Lecture 29](http://www.youtube.com/watch?v=Jp7SxSZNasI),”
    (YouTube) “[Lecture 30](http://www.youtube.com/watch?v=fao6nyVmraw)”
    (YouTube)  
      
     Instructions: Select the link for the three video lectures.  Scan
    over these and listen to the parts that will benefit you.  They
    correspond to the Notes for Lecture 28.   
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpages above.


