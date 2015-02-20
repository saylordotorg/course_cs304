---
layout: default
title: "CS304: Compilers"
course_description: "A detailed introduction to programming language translation, including the functions and general organization of compiler design and interpreters. Focuses on the study of syntax, semantics, ambiguities, procedures replication, iteration, and recursion in these languages."
next: ../Unit11
previous: ../Unit09
---
**Unit 10: Compiler Verification and Validation** <span id="10"></span> 
*The verification and validation (V&V) of a compiler consists of the V&V
of its parts: scanner or lexical analyzer, syntax analyzer, semantic
analyzer, Intermediate Code Generator, Intermediate Code Optimizer, Code
Generator, and Code Optimizer.* *See the V&V notes for each of these. 
V&V is based on a careful plan, a well-defined compiler process
(including version control or more extensive configuration control, and
efficient and effective documentation), peer reviews, measurements,
(including defect analysis), component tests, formal proofs, and
integration tests.  It can utilize known correct tools, such as parser
generators, code generation templates, and other compilers and compiler
parts.  In addition, a formal certification of the compiler can be done
by an independent organization. *  
  
 *Remember that verification pertains to correctness, which means
satisfaction of specifications; and validation pertains to user needs,
which means satisfaction of user operational requirements.  Verification
addresses, for example, correctness of results of scanning, semantic
analysis, code generation, and code optimization.  Validation includes
meeting operational, functional, performance, and physical requirements
for processing time and memory space, and also, the
“ilities”—reliability, availability, maintainability, and usability. *  
  
 *V&V depends on the complications of the source and target programming
languages, the intended use of the compiler, number of front ends to
back ends, available tools, run-time environments and machine
architecture, and the system that it will interface with. *  
  
 *Finally, certification of a compiler—i.e., compliance to a
standard—may be necessary for safety or security of critical
programs.  *

**Unit 10 Time Advisory**  
This unit should take approximately 1 hour to complete.

**Unit10 Learning Outcomes**  
Upon successful completion of this unit, the student will be able to:  
  
-   <span dir="LTR">Describe verification and validation of a
    compiler.  </span>

-   **Reading: Wikipedia: “ANSI C”**
    Link: Wikipedia: “[ANSI
    C](http://www.saylor.org/site/wp-content/uploads/2012/01/CS304-10-ANSIC.pdf)”
    (PDF)  
        
     Instructions: Select the link and read about certification of ANSI
    C compilers.  
        
     Terms of Use: Thearticle above is released under a [Creative
    Commons Attribution-Share-Alike License
    3.0](http://creativecommons.org/licenses/by-sa/3.0/) (HTML).  You
    can find the original Wikipedia version of this
    article [here](http://en.wikipedia.org/wiki/ANSI_C) (HTML).

-   **Assessment: The Saylor Foundation’s “Assessment 8”**
    Link: The Saylor Foundation’s “[Assessment
    8](http://www.saylor.org/site/wp-content/uploads/2012/06/CS304-Unit-10-Assessmet-8.pdf)”
    (PDF)  
      
     Instructions: Please review subunits 4.7, 5.7, 6.4, 8.5, and 9.6 of
    this course.  They discuss verification and validation of lexical
    analyzers, parsers, semantic analyzers, code generators, and code
    optimizers, respectively.  In this unit (Unit 10) and in these
    exercises, we combine the ideas of those sections and look at an
    integrated approach to the verification and validation of the
    compiler as a whole.  
        
     Exercise \#1: Outline an approach for verifying software that
    translates from one programming language to another.  
        
     Exercise \#2: Outline an approach for validating software that
    translates from one programming language to another.  
        
     This assessmentshould take you approximately 1 hour and 30 minutes
    to complete.  
        
     You can check your answers with the Saylor Foundation’s “[Answer
    Key](http://www.saylor.org/site/wp-content/uploads/2012/06/CS304-Unit-10-Answer-Key-to-Assessment-8-FINAL.pdf)”
    (PDF)


