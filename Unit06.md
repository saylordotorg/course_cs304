**Unit 6: Syntax Directed Translation and Semantic Analysis** <span
id="6"></span> 
*Semantic Analysis takes input from the parsing process and prepares the
code for the code-generation step.  In this unit, we will discuss this
process in detail, learning about* *scope and* *type-checking,* *type
expression, type equations, and type inference.  *

**Unit 6 Time Advisory**  
This unit should take approximately 32 hours to complete.  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 6.1: 2 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 6.2: 4 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 6.3: 26 hours

<span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; "><span
id="cke_bm_525S" style="display: none; "> </span>☐    </span>Subunit
6.3.1: 4 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 6.3.2: 1 hour  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 6.3.3: 4 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 6.3.4: 17 hours <span id="cke_bm_525E"
style="display: none; "> </span>

<span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 6.3.4.1: 6 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 6.3.4.2: 5 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 6.3.4.3: 2 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 6.3.4.4: 2 hours

<span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 6.4: .1 hour

**Unit6 Learning Outcomes**  
Upon successful completion of this unit, the student will be able to:  
  
-   <span dir="LTR">Explain semantic analysis in the context of the
    compilation process.</span>
-   <span dir="LTR">Describe scope checking and type checking.</span>
-   <span dir="LTR">Specify the functions of semantic analysis.</span>
-   <span dir="LTR">Solve type equations and make inferences in a type
    calculus.</span>

**6.1 Syntax-Directed Translation and Attribute Grammars** <span
id="6.1"></span> 
-   **Reading: Torben Ægidius Mogensen’s Basics of Compiler Design:
    “Chapter 5: Interpretation”**
    Link: Torben Ægidius Mogensen’s *Basics of Compiler Design*:
    “[Chapter 5:
    Interpretation](http://www.diku.dk/hjemmesider/ansatte/torbenm/Basics/)”
    (PDF)  
        
     Instructions: Select the link and click “Get the book contents” to
    download a PDF version of the book.  Please look over Chapter 5 on
    interpretation, where execution of a program takes place as the
    derivation is produced.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Handout 16 “Syntax-directed translation”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Handout
    16 “[Syntax-directed
    translation](http://www.keithschwarz.com/cs143/WWW/sum2011/)”
    (PDF)  
        
     Instructions: Please study the definitions and examples. 
    Syntax-directed translation and attribute grammars are techniques
    for using the parser to drive the translation directly.  Attributes
    are properties of grammar symbols, and the attributes take on
    values.  Rules associated with each grammar production specify how
    to compute the value of the attributes.   
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**6.2 Intermediate Representation** <span id="6.2"></span> 
-   **Reading: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer
    Language Engineering: Lecture 5: “Intermediate formats”**
    Link: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer Language
    Engineering: Lecture 5: “[Intermediate
    formats](https://resources.saylor.org/archived/wp-content/uploads/2012/01/CS304-6.2-INTERMEDIATEFORMATS.pdf)”
    (PDF)  
        
     Instructions: Please study the slides on intermediate
    representations.  Data, as well as computations and flow of control,
    have intermediate representations.  This reading also applies to
    subsections 6.2.1 and 6.2.2 below.  
        
     Terms of Use: The article above is released under a [Creative
    Commons Attribution-Share-Alike License
    3.0](http://creativecommons.org/licenses/by-sa/3.0/) (HTML).  You
    can find the original version of this
    article [here](http://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-035-computer-language-engineering-spring-2010/lecture-notes/) (PDF).

**6.2.1 Representation of Program Data—Symbol Tables** <span
id="6.2.1"></span> 
-   **Reading: Torben Ægidius Mogensen’s Basics of Compiler Design:
    “Chapter 4: Scopes and Symbol Tables”**
    Link: Torben Ægidius Mogensen’s *Basics of Compiler Design*:
    “[Chapter 4: Scopes and Symbol
    Tables](http://www.diku.dk/hjemmesider/ansatte/torbenm/Basics/)”
    (PDF)  
        
     Instructions: Select the link and click “Get the book contents” to
    download a PDF version of the book.  Please read Chapter 4 on scope
    of names and symbol tables.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**6.2.2 Representation of Program Computation** <span
id="6.2.2"></span> 
*Note: The reading of section 6.2, slides 68 to the end, cover this
subsection topic.  *

**6.3 Functions of Semantic Analysis** <span id="6.3"></span> 
*Note: Semantic analysis includes checking the scope of names in a
program and checking for type errors.*

**6.3.1 Scope Checking of Names in a Program** <span id="6.3.1"></span> 
-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Handout 18 “Semantic analysis”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Handout
    18 “[Semantic
    analysis](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF)  
        
     Instructions: Select the PDF for Handout 18 and read this overview
    of semantic analysis.  See slide 10 for the functions of semantic
    analysis.   
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Lecture 8: “Semantic Analysis”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Lecture
    8: “[Semantic
    Analysis](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF)  
        
     Instructions: Select the PDF for Lecture 8 and study slides 5 –
    103.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**6.3.2 Scope Checking with Inheritance** <span id="6.3.2"></span> 
-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Lecture 8: “Semantic Analysis”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Lecture
    8: “[Semantic
    Analysis](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF)  
        
     Instructions: Select the PDF for Lecture 8 and study slides 104 –
    137 on scope checking for object-oriented languages.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above

**6.3.3 Static vs. Dynamic Scope Checking** <span id="6.3.3"></span> 
-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Lecture 8: “Semantic Analysis”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Lecture
    8: “[Semantic
    Analysis](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF)  
        
     Instructions: Select the PDF for Lecture 8 and study slides 138 to
    the end, on scope checking at run-time.  Static scope checking
    occurs at compile-time; dynamic scope checking occurs at run-time. 
    The scope checking in 6.3.1 and 6.3.2 above is static scope
    checking.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Reading: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Notes for Lecture 16 “Static
    Semantics Overview”**
    Link: University of California, Berkeley: Paul Hilfinger’s CS164
    Programming and Compilers: Notes for Lecture 16 “[Static Semantics
    Overview](http://inst.eecs.berkeley.edu/~cs164/sp11/lectures/lecture16.pdf)”
    (PDF)  
      
     Instructions: Select the PDF link.  These slides overlap the
    readings above, but the 10 slides give a nice review of the
    material.  
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**6.3.4 Type Checking** <span id="6.3.4"></span> 
*Note: Type checking is one of the static (i.e., compile-time) checks of
semantic analysis.  Others are flow-of-control and uniqueness checks. 
Checking is done when the intermediate representation is being
created.  *

-   **Reading: University of Copenhagen: Torben Ægidius Mogensen’s
    Basics of Compiler Design: “Chapter 6: Type Checking”**
    Link: University of Copenhagen: Torben Ægidius Mogensen’s *Basics of
    Compiler Design*: “[Chapter 6: Type
    Checking](http://www.diku.dk/hjemmesider/ansatte/torbenm/Basics/)”
    (PDF)  
        
     Instructions: Select the link and click “Get the book contents” to
    download a PDF version of the book.  Please read Chapter 6 (pages
    133 – 143), which presents an overview of type checking, nicely
    organized: symbol table environment, type checking for expressions,
    functions, and then, for programs.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**6.3.4.1 Type Expressions, Type Equivalence, Type Inference, and What
to Check** <span id="6.3.4.1"></span> 
-   **Reading: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer
    Language Engineering: Lecture 6: “Semantic Analysis”**
    Link: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer Language
    Engineering: Lecture 6: “[Semantic
    Analysis](https://resources.saylor.org/archived/wp-content/uploads/2012/01/CS304-6.3.4.1-SEMANTICANALYSIS.pdf)”
    (PDF)  
        
     Instructions: Please study the slides on type systems and what to
    check for when building intermediate representations for various
    language constructs.  
        
     Terms of Use: The article above is released under a [Creative
    Commons Attribution-Share-Alike License
    3.0](http://creativecommons.org/licenses/by-sa/3.0/) (HTML).  You
    can find the original version of this
    article [here](http://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-035-computer-language-engineering-spring-2010/lecture-notes/) (PDF).

-   **Reading: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Notes for Lecture 17 “Types”**
    Link: University of California, Berkeley: Paul Hilfinger’s CS164
    Programming and Compilers: Notes for Lecture 17
    “[Types](http://inst.eecs.berkeley.edu/~cs164/sp11/lectures/lecture17.pdf)”
    (PDF)  
      
     Instructions: Select the PDF link.  There is overlap between this
    reading and the above readings.  Look over slides 2 through 14 and
    use them as a review or supplement to the above readings.  Slides 15
    through 31 give examples of type inference for the languages Prolog,
    Java, and Python.   
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Web Media: YouTube: University of California, Berkeley: Paul
    Hilfinger’s CS164 Programming and Compilers: Video Lectures:
    “Lecture 18,” “Lecture 19,” “Lecture 20,” and “Lecture 21”**
    Link: YouTube: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Video Lectures: “[Lecture
    18](http://www.youtube.com/watch?v=X76TacJv7NI),” “[Lecture
    19](http://www.youtube.com/watch?v=aJ28vfymr4I&feature=relmfu),”
    “[Lecture
    20](http://www.youtube.com/watch?v=kYw-RVfb88M&feature=relmfu),” and
    “[Lecture
    21](http://www.youtube.com/watch?v=GjvSaphlRk4&feature=relmfu)”
    (YouTube)  
      
     Instructions: Video lectures 18 to 21 correspond to these notes and
    are optional.  They may be helpful in understanding some of the
    notes.  
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpages above.

**6.3.4.2 Type Systems as Proof Systems—Type Checking as Proofs** <span
id="6.3.4.2"></span> 
-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Lecture 9: “Type Checking”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Lecture
    9: “[Type Checking](http://www.keithschwarz.com/cs143/WWW/sum2011/)”
    (PDF)  
        
     Instructions: Select the PDF for Lecture 9 and study the very
    interesting presentation on type checking by proofs.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Reading: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Notes for Lecture 22 “Type
    Inference and Unification”**
    Link: University of California, Berkeley: Paul Hilfinger’s CS164
    Programming and Compilers: Notes for Lecture 22 “[Type Inference and
    Unification](http://inst.eecs.berkeley.edu/~cs164/sp11/lectures/lecture22.pdf)”
    (PDF)  
      
     Instructions: Select the PDF link.  Look at slides 1 through 8. 
    The slides are somewhat formal and present a “type calculus.”  Use
    these slides to add to your understanding of types.  
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Web Media: YouTube: University of California, Berkeley: Paul
    Hilfinger’s CS164 Programming and Compilers: Video Lecture: “Lecture
    22”**
    Link: YouTube: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Video Lecture: “[Lecture
    22](http://www.youtube.com/watch?v=tXsYMws4u5o)” (YouTube)  
      
     Instructions: Video lecture 22 corresponds to these notes and is
    optional.  If it adds to the notes and helps you, view it.  
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**6.3.4.3 Applications of Type Proofs** <span id="6.3.4.3"></span> 
-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Lecture 10: “Type Checking II”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Lecture
    10: “[Type Checking
    II](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF)  
        
     Instructions: Select the PDF for Lecture 10 and study the
    application of the type proof system (introduced above) to the
    detection of type errors.   
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**6.3.4.4 Type Equations, Unification and Binding of Type Expressions**
<span id="6.3.4.4"></span> 
-   **Reading: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Notes for Lecture 22 “Type
    Inference and Unification”**
    Link: University of California, Berkeley: Paul Hilfinger’s CS164
    Programming and Compilers: Notes for Lecture 22 “[Type Inference and
    Unification](http://inst.eecs.berkeley.edu/~cs164/sp11/lectures/lecture22.pdf)”
    (PDF)  
      
     Instructions: Select the PDF link.  Look at slides 8 through 19. 
    The slides supplement the readings above with type examples.  A
    binding is a substitution of a type expression for a type
    variable.   
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**6.4 Verification and Validation of Semantic Analysis** <span
id="6.4"></span> 
*Note: The note in section 5.7 on Verification and Validation (V&V) of a
Parser also applies to the V&V of semantic analysis.  By verification,
we mean that the semantic analyzer performs a correct analysis relative
to the programming language definition.  Formal proof methods using a
type calculus, reviews, and testing can be used to verify the
correctness of the semantic analysis.  Verification includes showing
that the analyzer performs the required analysis, adheres to the
programming language definition, and outputs correct error messages.*
* “Valid”* *means that the semantic analysis satisfies its end
requirements in the overall compilation process.  Requirements include
processing time and memory space targets, maintainability, and
reliability.*

-   **Assessment: University of Copenhagen: Torben Ægidius Mogensen’s
    Basics of Compiler Design: “Chapter 6: Type Checking”**
    Link: University of Copenhagen: Torben Ægidius Mogensen’s *Basics of
    Compiler Design:* “[Chapter 6: Type
    Checking](http://www.diku.dk/hjemmesider/ansatte/torbenm/Basics/)”
    (PDF)  
        
     Instructions: Please click on the link above, and select “Get the
    Book Contents” to download the PDF file of Mogensen’s “Chapter 6:
    Type Checking.”  Complete the following:  
        
     Exercise \#1: Do Exercise 6.1 in Mogensen’s “Chapter 6 Type
    Checking” on page 143.  
     Exercise \#2: Do Exercise 6.2 and 6.3 in Mogensen’s “Chapter 6 Type
    Checking” on pages 143 and 144.  
        
     These exercises will give you some practice with semantic analysis
    and are based on Chapter 6, which covers type checking.  Then,
    please check your answers against the solutions in the Saylor
    Foundation’s “[Answer Key to Assessment
    5.”](https://resources.saylor.org/archived/wp-content/uploads/2012/06/CS304-Unit-6-Answer-Key-to-Assessment-5-FINAL.pdf)
    (PDF)  
        
     This assessment should take you approximately 3 hours to
    complete.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.


