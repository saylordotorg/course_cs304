---
layout: default
title: "CS304: Compilers"
course_description: "A detailed introduction to programming language translation, including the functions and general organization of compiler design and interpreters. Focuses on the study of syntax, semantics, ambiguities, procedures replication, iteration, and recursion in these languages."
next: ../Unit04
previous: ../Unit02
---
**Unit 3: Finite State Machines** <span id="3"></span> 
*Finite state machines (FSM), also called finite state automata (FSA),
are conceptual models for recognizing, parsing, and generating strings
in a formal language.  An FSM can be used to recognize (i.e., determine)
whether a string adheres to the syntax of a language.  Moreover, an FSM
can be used to build a syntax tree, which shows the derivation (i.e.,
how the string was constructed) of the string.  This unit introduces (or
reviews) FSMs, which are covered in detail in other courses (for
example, CS202: Discrete Structures).*

**Unit 3 Time Advisory**  
This unit should take approximately 6 hours to complete.  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 3.1: 2 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 3.2: 2 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 3.3: 2 hours

**Unit3 Learning Outcomes**  
Upon successful completion of this unit, the student will be able to:  
  
-   <span dir="LTR">De</span>fine the types of finite state machines
    (FSMs) used in the compilation process.
-   <span dir="LTR">Identify the type of language and grammar recognized
    by each type of FSM.</span>
-   <span dir="LTR">Explain the use of FSA in the compilation
    process.</span>

**3.1 Definitions** <span id="3.1"></span> 
-   **Reading: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer
    Language Engineering: Lecture 2: “Specifying languages with regular
    expressions and context-free grammars**
    Link: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer Language
    Engineering: Lecture 2: “[Specifying languages with regular
    expressions and context-free
    grammars](https://resources.saylor.org/wwwresources/archived/site/wp-content/uploads/2012/01/CS304-2.1-MIT.pdf)”
    (PDF)  
        
     Instructions: Study slides 9 – 33.  These slides describe and give
    examples of regular languages/regular expressions and their
    corresponding finite state machine.  
        
     Terms of Use: The resource above is released under
    an [Attribution-NonCommercial-ShareAlike License 3.0 Unported (CC
    BY-NC-SA
    3.0)](http://creativecommons.org/licenses/by-nc-sa/3.0/) (HTML).  It
    is attributed to MIT and the original resource can be
    found [here](http://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-035-computer-language-engineering-spring-2010/lecture-notes/) (PDF).

-   **Reading: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Notes for Lecture 2 “Lexical
    Analysis, Regular Expressions” and Notes for Lecture 3 “FSA”**
    Link: University of California, Berkeley: Paul Hilfinger’s CS164
    Programming and Compilers: Notes for Lecture 2 “[Lexical Analysis,
    Regular
    Expressions](http://inst.eecs.berkeley.edu/~cs164/sp11/lectures/)”
    (PDF) and Notes for Lecture 3
    “[FSA](http://webcast.berkeley.edu/playlist#c,d,Computer_Science,03D59E2ECDDA66DF)”
    (PDF)  
      
     Instructions: Select the PDF link for lecture notes 2 and study all
    the slides.  Then, select the PDF link for lecture notes 3 and study
    slides 1 – 5.   
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpages above.

**3.2 Some Results and Examples of FSAs** <span id="3.2"></span> 
-   **Reading: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer
    Language Engineering: Lecture 2: “Specifying languages with regular
    expressions and context-free grammars”**
    Link: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer Language
    Engineering: Lecture 2: “[Specifying languages with regular
    expressions and context-free
    grammars](https://resources.saylor.org/wwwresources/archived/site/wp-content/uploads/2012/01/CS304-2.1-MIT.pdf)”
    (PDF)  
        
     Instructions: Study slides 34 – 76.  These slides give results and
    examples of conversion from a non-deterministic finite state
    automaton (NFA) to a deterministic finite state automaton (DFA);
    regular expressions or strings; context free grammars and pushdown
    automata (PDA); and context sensitive grammars and Turing machines. 
    They, also, introduce parsing and abstract syntax trees.  
        
     Terms of Use: The resource above is released under
    an [Attribution-NonCommercial-ShareAlike License 3.0 Unported (CC
    BY-NC-SA
    3.0)](http://creativecommons.org/licenses/by-nc-sa/3.0/) (HTML).  It
    is attributed to MIT and the original resource can be
    found [here](http://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-035-computer-language-engineering-spring-2010/lecture-notes/) (PDF).

-   **Reading: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Notes for Lecture 3 “FSA”**
    Link: University of California, Berkeley: Paul Hilfinger’s CS164
    Programming and Compilers: Notes for Lecture 3
    “[FSA](http://inst.eecs.berkeley.edu/~cs164/sp11/lectures/)” (PDF)  
      
     Instructions: Select the PDF link for lecture notes 3 and study
    slides 6 and 7.   
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**3.3 Some Applications of FSA** <span id="3.3"></span> 
-   **Reading: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Notes for Lecture 3 “FSA”**
    Link: University of California, Berkeley: Paul Hilfinger’s CS164
    Programming and Compilers: Notes for Lecture 3
    “[FSA](http://inst.eecs.berkeley.edu/~cs164/sp11/lectures/)” (PDF)  
      
     Instructions: Select the PDF link for lecture notes 3 and study
    slides 8 to the end.  These notes repeat some of the material from
    section 3.2 and provide additional practice in applying FSAs.    
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpages above.

-   **Assessment: MIT: S. Amarasinghe and M. Rinard, 6.035 Computer
    Language Engineering: “Practice Quiz 1”**
    Link: MIT: S. Amarasinghe and M. Rinard, 6.035 Computer
    Language Engineering: “[Practice Quiz
    1](https://resources.saylor.org/wwwresources/archived/site/wp-content/uploads/2012/02/CS304-QUIZ.pdf)”
    (PDF)  
        
     Instructions: Select the PDF for Practice Quiz 1.  In this
    assessment, we will extend and do exercises 1, 2.  In addition, you
    will need to complete exercise 3.   For exercise 1: Do the FSA part
    of this exercise.  This exercise gives you practice in forming an
    FSA (finite state automaton) to recognize a language.  The exercise
    takes the following steps:  
        
                 regular language → regular expression → FSA that
    recognizes the given language  
        
     For exercise 2, give the FSA for the regular expression of this
    exercise.   Then, complete exercise 3 as listed.  
        
     The reference's solutions are given at the end of the PDF.  For the
    exercises on FSAs, you should use paper and pencil to draw the FSA
    as it is formed.  Additional exercise and solution information is
    available in The Saylor Foundation’s “[Answer Key to CS304
    Assessment2](https://resources.saylor.org/wwwresources/archived/site/wp-content/uploads/2012/08/CS304-Unit-3-Answer-Key-to-Assessment-2-FINAL.pdf).”(PDF)  


