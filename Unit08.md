---
layout: default
title: "CS304: Compilers"
course_description: "A detailed introduction to programming language translation, including the functions and general organization of compiler design and interpreters. Focuses on the study of syntax, semantics, ambiguities, procedures replication, iteration, and recursion in these languages."
next: ../Unit09
previous: ../Unit07
---
**Unit 8: Code Generation** <span id="8"></span> 
*This unit is closely related to Unit 7, where the emphasis was on
representation of data structures needed for run-time.  While there will
be some overlap, the emphasis in this unit is on instruction-level
intermediate code generation and from intermediate code to target
code.*  
  
 *The* *lastphase* *(or next to the last phase if there is a code
optimization phase)* *of the compilation process is code generation,
where the output from the previous steps is finally translated into
machine code, ready to execute on the target platform.  In this unit, we
will start with a discussion of code generation in general before moving
on to a more detailed description of the code generation process.  This
will include an in-depth discussion of three main areas: Instruction
Selection, Instruction Scheduling, and Register Allocation.  By the end
of this unit, you will have a firm understanding of the code generation
process.*

**Unit 8 Time Advisory**  
This unit should take approximately 16 hours to complete.  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 8.1: 3 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 8.2: 4 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 8.3: 3 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 8.4: 6 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 8.5: .1 hour

**Unit8 Learning Outcomes**  
Upon successful completion of this unit, the student will be able to:  
  
-   <span dir="LTR">Explain the use of an intermediate language.</span>
-   <span dir="LTR">Identify the difficult aspects of code
    generation.</span>
-   <span dir="LTR">Give examples of translation from simple source
    statements to intermediate code.</span>
-   <span dir="LTR">Give examples of translation from intermediate
    language statements to assembler or machine code.</span>

**8.1 Introduction to Intermediate Code Generation** <span
id="8.1"></span> 
-   **Reading: Torben Ægidius Mogensen’s Basics of Compiler Design:
    “Chapter 7: “Intermediate-Code Generation”**
    Link: Torben Ægidius Mogensen’s *Basics of Compiler Design*:
    “[Chapter 7: Intermediate-Code
    Generation](http://www.diku.dk/hjemmesider/ansatte/torbenm/Basics/)”
    (PDF)  
        
     Instructions: Select the link and click “Get the book contents” to
    download a PDF version of the book.  Please read Chapter 7.  Read
    the entire chapter, which discusses generation to a relatively
    low-level intermediate language.  Section 7.9 overlaps some of the
    previous readings.  This reading also applies to 8.1.1.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**8.1.1 Requirements and Overview** <span id="8.1.1"></span> 
*Note: The reading of 8.1 applies to this subunit. * *Requirements of
intermediate-code generation are included in sections 7.1 and 7.2.  *

**8.1.2 Examples of Abstract Syntax Tree to Intermediate-Code
Generation** <span id="8.1.2"></span> 
-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Handout 23: “Intermediate Representation”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Handout
    23: “[Intermediate
    Representation](http://www.keithschwarz.com/cs143/WWW/sum2011/)”
    (PDF)  
        
     Instructions: Select the PDF for Handout 23.  Intermediate
    representation of a source program may be part of the front end, may
    be part of the back end, depending on the design of the compiler and
    its intended use, or may be simply called the “middle part” of the
    compiler between the front end and back end.  Handout 23 covers IR
    in the context of code generation.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above

**8.2 Detailed Example: Three Address Code (TAC)** <span
id="8.2"></span> 
**8.2.1 TAC Language and Generation from an AST** <span
id="8.2.1"></span> 
-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Handout 24: “TAC Examples” and Lecture 13 “TAC”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Handout
    24: “[TAC Examples](http://www.keithschwarz.com/cs143/WWW/sum2011/)”
    (PDF) and Lecture 13
    “[TAC](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF)  
        
     Instructions: Select the PDF for Handout 24.  TAC is a generic
    assembly language.  Read Handout 24.  Slides 1 through 149 give
    examples of TAC statements, function calls and encoding of
    objects.   
      
     Note: This reading also applies to 8.2.2.  Slides 150 to 173 give
    examples of generation of TAC from an AST (abstract syntax tree). 
    Select the link for the video, skim it and, if it is helpful to you,
    watch it.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpages above.

**8.2.2 Generation of TAC** <span id="8.2.2"></span> 
*Note: The reading of 8.2.1 applies to this subunit.  The lecture slides
150 through 173 describe the generation of TAC.*

**8.3 Additional Intermediate Language Generation Examples** <span
id="8.3"></span> 
-   **Reading: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Notes for Lecture 31: “Code
    Generation”**
    Link: University of California, Berkeley: Paul Hilfinger’s CS164
    Programming and Compilers: Notes for Lecture 31: “[Code
    Generation](http://inst.eecs.berkeley.edu/~cs164/sp11/lectures/)”
    (PDF)  
      
     Instructions: Select the PDF link for the notes for Lecture 31 on
    Code Generation.  These discuss generation of intermediate code for
    a stack machine, stack machine with accumulator, and for a TAC
    machine.   
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Web Media: YouTube: University of California, Berkeley: Paul
    Hilfinger’s CS164 Programming and Compilers: Video Lecture: “Lecture
    31”**
    Link: YouTube: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Video Lecture: “[Lecture
    31](http://www.youtube.com/watch?v=39bKp57zd30)” (YouTube)  
      
     Instructions: The video lecture 31 is optional, and is listed as an
    aid if you have any questions on the notes.  
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**8.4 Generation of Machine Code** <span id="8.4"></span> 
**8.4.1 Introduction: Intermediate Code to Machine Code** <span
id="8.4.1"></span> 
-   **Reading: Torben Ægidius Mogensen’s Basics of Compiler Design:
    “Chapter 8: Intermediate-Code Generation”**
    Link: Torben Ægidius Mogensen’s *Basics of Compiler Design*:
    “[Chapter 8: Machine-Code
    Generation](http://www.diku.dk/hjemmesider/ansatte/torbenm/Basics/)”
    (PDF)  
        
     Instructions: Select the link and click “Get the book contents” to
    download a PDF version of the book.  Please read Chapter 8.  It
    describes the translation from a low-level intermediate language to
    machine code.  This translation addresses the handling of
    restrictions on the machine language; for example, a finite number
    of registers is a restriction of a target machine and its machine
    language.  The intermediate language assumes an unlimited number of
    registers, i.e., virtual register machine.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**8.4.2 Details: Intermediate Code to Machine Code** <span
id="8.4.2"></span> 
-   **Reading: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Notes for Lecture 34: “Registers,
    Functions, Parameters”**
    Link: University of California, Berkeley: Paul Hilfinger’s CS164
    Programming and Compilers: Notes for Lecture 34: “[Registers,
    Functions,
    Parameters](http://inst.eecs.berkeley.edu/~cs164/sp11/lectures/)”
    (PDF)  
      
     Instructions: Select the PDF link for the notes for Lecture 34 on
    Code Generation. Read these excellent notes on generation of machine
    code from intermediate code.  
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above. 

-   **Reading: Torben Ægidius Mogensen’s Basics of Compiler Design:
    “Chapter 9: “Register Allocation” and “Chapter 10: Function Calls”**
    Link: Torben Ægidius Mogensen’s *Basics of Compiler Design*:
    “[Chapter 9: Register
    Allocation](http://www.diku.dk/hjemmesider/ansatte/torbenm/Basics/)”
    (PDF) and “[Chapter 10: Function
    Calls](http://www.diku.dk/hjemmesider/ansatte/torbenm/Basics/)”
    (PDF)  
        
     Instructions: Select the link and click “Get the book contents” to
    download a PDF version of the book.  Please look over Chapters 9 and
    10.  Chapter 9 overlaps the above reading, and is a supplementary
    discussion of the problem of mapping a large number of variables
    used in an intermediate language translation into a smaller number
    of registers, plus memory locations available on the target
    machine.  Chapter 10 covers function calls using a stack, activation
    records, and frame pointers.  Look over these chapters and read the
    parts that will add to your understanding of register allocation and
    function calls.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpages above. 

-   **Web Media: YouTube: University of California, Berkeley: Paul
    Hilfinger’s CS164 Programming and Compilers: Video Lectures:
    “Lecture 32,” “Lecture 33,” “Lecture 34”**
    Link: YouTube: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Video Lectures: “[Lecture
    32](http://www.youtube.com/watch?v=F7o5ttm0578),” (YouTube)
    “[Lecture 33](http://www.youtube.com/watch?v=LT0flmovt0w),”
    (YouTube) “[Lecture 34](http://www.youtube.com/watch?v=2gBDWXneO98)”
    (YouTube)  
      
     Instructions: Please watch the videos above.  
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpages above.

-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Lectures 17 and 18: “Register Allocation” and “Garbage Collection”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Lectures
    17 and 18: “[Register
    Allocation](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF)
    and “[Garbage
    Collection](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF)  
        
     Instructions: Select the PDF for Lectures 17 and 18.  These are
    very well-done formal presentations and give a lot of detail. 
    Register allocation, linear scan and Chaitin’s algorithm are
    explained.  Regarding garbage collection, reference counting,
    mark-and-sweep, and stop-and-copy are explained.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpages above. 

**8.5 Verification and Validation of Code Generation** <span
id="8.5"></span> 
*Note: As with previous parts of a compiler and previous steps of the
compilation process, we are interested in the verification (i.e., does
the code generator work correctly) and the validation (i.e., does the
code generator satisfy the requirements as part of the compiler).  The
same kinds of techniques used for the previous parts of a compiler
apply, as well, to the code generator. *  
  
 *If our code generator produces intermediate code and we have a known
“correct” generator from* *intermediate code to machine code, then our
V&V efforts can focus on the translation to intermediate code.* 
*Moreover, if we have a known “correct” compiler from another source
language that is similar to our source language and satisfies similar
requirements, we could write a simple translator between them and show
that the simple translator is correct.  Again, if we want to verify
intermediate code to assembler code, and we have a known “correct”
generator from the same intermediate language to another assembler
language, we could write a simple translator between the assembler
languages and then verify that translator. *  
  
 *The use of an intermediate language has another benefit: it can make
the use of formal proofs of correctness easier than their use on AST to
target language generation. Lastly, measurements of process time and
memory usage will be needed to validate time and space requirements.  *

-   **Assessment: University of Copenhagen: Torben Ægidius Mogensen’s
    Basics of Compiler Design: “Chapter 7: Intermediate Code
    Generation”**
    Link: University of Copenhagen: Torben Ægidius Mogensen’s *Basics of
    Compiler Design:* “[Chapter 7: Intermediate-Code
    Generation](http://www.diku.dk/hjemmesider/ansatte/torbenm/Basics/)”
    (PDF)  
      
     Instructions: Please click on the link above, and then select “Get
    the book contents” to download a PDF version of the book.  Complete
    the following:  
      
     Exercise \#1: Do Exercise 7.1 in Mogensen’s “Chapter 7
    Intermediate-Code Generation” on page 173.  
      
     Exercise \#2:  Do Exercise 8.2 in Mogensen’s “Chapter 8
    Machine-Code Generation” on page 189.  
      
     These exercises will give you some practice with code generation
    and are based on Chapter 7, which covers intermediate code
    generation, and Chapter 8, which covers machine code generation. 
    Intermediate code can be high level, i.e. close to the input
    language, or low level, i.e. close to the target machine language,
    and, hence, though Exercise \#2 jumps to Chapter 8, the process of
    syntax directed translation is the same.  These exercises illustrate
    the process for syntax directed translation to intermediate code or
    machine code.  You can check your answers with the Saylor
    Foundation’s “[Answer
    Key](http://www.saylor.org/site/wp-content/uploads/2012/06/CS304-Unit-8-Answer-Key-to-Assessment-6-FINAL.pdf)”
    (PDF).  
        
     This assessment should take you approximately 3 hours to
    complete.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.


