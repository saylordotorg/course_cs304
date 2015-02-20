---
layout: default
title: "CS304: Compilers"
course_description: "A detailed introduction to programming language translation, including the functions and general organization of compiler design and interpreters. Focuses on the study of syntax, semantics, ambiguities, procedures replication, iteration, and recursion in these languages."
next: ../Unit03
previous: ../Unit01
---
**Unit 2: Formal Languages and Formal Grammar** <span id="2"></span> 
*Formal languages and formal grammars are the theoretical foundation for
computer languages and the compilation process.  Formal languages are
defined by their grammars, which specify the syntax of the languages.*

**Unit 2 Time Advisory**  
This unit should take approximately 6 hoursto complete.  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 2.1: 1hour  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 2.2: 1 hour  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 2.3: 2 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 2.4: 2 hours

**Unit2 Learning Outcomes**  
Upon successful completion of this unit, the student will be able to:  
  
-   <span dir="LTR">De</span>fine a formal language.
-   <span dir="LTR">Give examples of a formal language.</span>
-   <span dir="LTR">Define a formal grammar and explain its
    purpose.</span>
-   <span dir="LTR">Define syntax and semantics of a formal
    language.</span>

**2.1 Motivation for Formal Languages** <span id="2.1"></span> 
-   **Reading: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer
    Language Engineering: Lecture 2: “Specifying languages with regular
    expressions and context-free grammars”**
    Link: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer Language
    Engineering: Lecture 2: “[Specifying languages with regular
    expressions and context-free
    grammars](http://www.saylor.org/site/wp-content/uploads/2012/01/CS304-2.1-MIT.pdf)”
    (PDF)  
        
     Instructions: Study slides 2 – 8, and slides 38 – 41.  Regular and
    context-free languages are introduced.  Also, read slides 68 – 70.  
        
     Terms of Use: The resource above is released under an
    [Attribution-NonCommercial-ShareAlike License 3.0 Unported (CC
    BY-NC-SA
    3.0)](http://creativecommons.org/licenses/by-nc-sa/3.0/) (HTML).  It
    is attributed to MIT and the original resource can be found
    [here](http://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-035-computer-language-engineering-spring-2010/lecture-notes/) (PDF). 

-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Handout 08: “Formal Grammars”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Handout
    08: “[Formal
    Grammars](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF)  
        
     Instructions: Select the Handout on Formal Grammars and read pages
    10 – 11, which give some history of FORTRAN and ALGOL.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**2.2 Formal Grammars** <span id="2.2"></span> 
-   **Reading: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer
    Language Engineering: Lecture 3: “Introduction to shift-reduce
    parsing”**
    Link: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer Language
    Engineering: Lecture 3: “[Introduction to shift-reduce
    parsing](http://www.saylor.org/site/wp-content/uploads/2012/01/CS304-2.2-MIT.pdf)”
    (PDF)  
        
     Instructions: Please study slides 41–67.  
        
     Terms of Use: The resource above is released under an
    [Attribution-NonCommercial-ShareAlike License 3.0 Unported (CC
    BY-NC-SA
    3.0)](http://creativecommons.org/licenses/by-nc-sa/3.0/) (HTML).  It
    is attributed to MIT and the original resource can be found
    [here](http://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-035-computer-language-engineering-spring-2010/lecture-notes/) (PDF). 

-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Handout 03: “Lexical Analysis”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Handout
    03: “[Lexical
    Analysis](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF)  
        
     Instructions: Select the Handout on Formal Grammars and read pages
    1 – 10.  Formal languages are defined by formal grammars.  Regular
    and context-free grammars are applied in scanning and parsing of
    programming languages.  Formal grammars define the syntax of a
    formal language.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**2.3 Syntax of Formal Languages** <span id="2.3"></span> 
-   **Reading: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Notes for Lecture 6: “Parsing”**
    Link: University of California, Berkeley: Paul Hilfinger’s CS164
    Programming and Compilers: Notes for Lecture 6:
    “[Parsing](http://inst.eecs.berkeley.edu/~cs164/sp11/lectures/)”
    (PDF)  
      
     Instructions: Select the link for Lecture 6 and study the slides.  
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.  

**2.4 Semantics of Formal Languages** <span id="2.4"></span> 
-   **Reading: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Notes for Lecture 16 “Static
    Semantics Overview”**
    Link: University of California, Berkeley: Paul Hilfinger’s CS164
    Programming and Compilers: Notes for Lecture 16 “[Static Semantics
    Overview](http://inst.eecs.berkeley.edu/~cs164/sp11/lectures/)”
    (PDF)  
      
     Instructions: Select the PDF link for lecture notes 16 and study
    slides 1 – 7.  Note that these notes are associated with lecture
    17.   
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Web Media: YouTube: University of California, Berkeley: Paul
    Hilfinger’s CS164 Programming and Compilers: Video Lecture: “Lecture
    17”**
    Link: YouTube: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Video Lecture: “[Lecture
    17](http://www.youtube.com/watch?v=ZT9mCu10iyA)" (YouTube)  
      
     Instructions: Listen to a portion of the video lecture 16 at
    location 12:12 (12 minutes and 12 seconds into the lecture) to
    15:00, where Professor Hilfinger talks about semantics.  
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Assessment: MIT: S. Amarasinghe and M. Rinard, 6.035 Computer
    Language Engineering: “Practice Quiz 1”**
    Link: MIT: S. Amarasinghe and M. Rinard, 6.035 Computer
    Language Engineering:
    “[Practice Quiz 1](http://www.saylor.org/site/wp-content/uploads/2012/02/CS304-QUIZ.pdf)”
    (PDF)  
        
     Instructions: Select the PDF and complete exercises 1, 2, and 6. 
    In exercise 1, just do the regular expression part of this exercise,
    which will give you practice in writing regular expressions for a
    regular language and in forming an FSA (finite state
    automaton—assessment 2) to recognize the language.  The exercise
    takes the following steps:  
        
           regular language → regular expression  
        
     For exercise 2: Again we are given a regular language and asked to
    derive a regular expression that defines the language.  L =
    {0<sup>i</sup> 1<sup>j</sup> | i is even and j is odd}.  Then,
    complete exercise 6 as listed.  
        
     The reference's solutions are given at the end of the PDF. 
    Additional exercise and solution information is available in The
    Saylor Foundation’s “[Answer Key to CS304 Assessment
    1](http://www.saylor.org/site/wp-content/uploads/2012/06/CS304-Unit-2-Answer-Key-to-Assessment-1-FINAL.pdf).”
    (PDF)


