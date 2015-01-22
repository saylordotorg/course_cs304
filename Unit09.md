**Unit 9: Code Optimization** <span id="9"></span> 
*Simply compiling and executing a program is not enough to get the most
out of your code.  It is the optimization process that allows your code
to run as effectively* *and efficientlyas possible.  In this unit, we
will first take a look at optimization, learning what it is and why we
are interested in it.  Next, we will review different optimization
categories, including Peephole, Local, Loop, Language Dependent, and
Machine Dependent.  We will conclude with a discussion of different
optimization techniques.  By the end of this unit, you will have a basic
understanding of a wide range of optimization techniques and how they
improve the effectiveness of your program.*

**Unit 9 Time Advisory**  
This unit should take approximately 22 hours to complete.  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 9.1: 1 hour  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 9.2: 2 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 9.3: 4 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 9.4: 8 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 9.5: 6 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 9.6: 1 hour

**Unit9 Learning Outcomes**  
Upon successful completion of this unit, the student will be able to:  
  
-   <span dir="LTR">Define </span>*optimization*.
-   <span dir="LTR">Describe approaches and give examples of local
    optimizations.</span>
-   <span dir="LTR">Describe approaches and give examples of global
    optimizations.</span>
-   <span dir="LTR">Describe approaches and give examples of code
    optimizations.</span>

**9.1 The What and Why of Code Optimizations** <span id="9.1"></span> 
-   **Reading: Torben Ægidius Mogensen’s Basics of Compiler Design:
    “Chapter 11: Analysis and Optimisation”**
    Link: Torben Ægidius Mogensen’s *Basics of Compiler Design*:
    “[Chapter 11: Analysis and
    Optimisation](http://www.diku.dk/hjemmesider/ansatte/torbenm/Basics/)”
    (PDF)  
        
     Instructions: Select the link and click “Get the book contents” to
    download a PDF version of the book.  Please read Chapter 11.  Read
    the introductory section, up to 11.1.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**9.2 Fundamentals of Code Optimization** <span id="9.2"></span> 
-   **Reading: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Notes for Lecture 36: “Local
    Optimization”**
    Link: University of California, Berkeley: Paul Hilfinger’s CS164
    Programming and Compilers: Notes for Lecture 36: “[Local
    Optimization](http://inst.eecs.berkeley.edu/~cs164/sp11/lectures/)”
    (PDF)  
      
     Instructions: Select the PDF link for the notes for Lecture 36,
    slides 1 through 8.  This reading also applies to subsections 9.2.1
    through 9.2.4.   
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Reading: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer
    Language Engineering: Lecture 9: “Introduction to Program Analysis
    and Optimization”**
    Link: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer Language
    Engineering: Lecture 9: “[Introduction to Program Analysis and
    Optimization](http://www.saylor.org/site/wp-content/uploads/2012/01/CS304-9.2-INTRODUCTIONPROGRAM.pdf)”
    (PDF)  
        
     Instructions: Please read the slides, which introduce the topics of
    this unit.  
        
     Terms of Use: The resource above is released under an
    [Attribution-NonCommercial-ShareAlike License 3.0 Unported (CC
    BY-NC-SA
    3.0)](http://creativecommons.org/licenses/by-nc-sa/3.0/) (HTML).  It
    is attributed to MIT and the original resource can be found
    [here](http://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-035-computer-language-engineering-spring-2010/lecture-notes/) (PDF). 

**9.2.1 Basic Blocks and CFG (Control Flow Graph)** <span
id="9.2.1"></span> 
*Note: The reading for 9.2 applies to this subsection.*

**9.2.2 Types of Optimizations** <span id="9.2.2"></span> 
*Note: The reading for 9.2 applies to this subsection.*

**9.3 Local Intermediate Code Optimizations: Definitions and Examples**
<span id="9.3"></span> 
*Note: The link for 9.2 applies to this subsection.  Read slides 9
through 24.  Slide 27 lists some challenges.  Slides 25 and 26 apply to
subsection 9.5 below on Code Optimization.  Peephole optimization is a
technique for improving assembly code.*

-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Handout 26: “Code Optimization” and Lecture 14: “IR Optimization”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Handout
    26: “[Code
    Optimization](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF)
    and Lecture 14: “[IR
    Optimization](http://www.keithschwarz.com/cs143/WWW/sum2011/)”
    (PDF)  
        
     Instructions: Select the PDF for Handout 26.  Read pages 1 through
    10.  This material overlaps with the previous reading, but it is a
    nice narrative summary of local optimizations.  Select the PDF for
    the lecture and read it.  The lecture is an excellent unified formal
    treatment of the topic  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpages above.

**9.4 Global Intermediate Code Optimizations: Definitions and Examples**
<span id="9.4"></span> 
-   **Reading: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Notes for Lecture 37: “Global
    Optimization”**
    Link: University of California, Berkeley: Paul Hilfinger’s CS164
    Programming and Compilers: Notes for Lecture 37: “[Global
    Optimization](http://inst.eecs.berkeley.edu/~cs164/sp11/lectures/)”
    (PDF)  
      
     Instructions: Select the PDF link for the notes for Lecture 37. 
    Read the slides.  Global optimization uses forward analysis (e.g.,
    constant propagation), which moves information forward, and backward
    analysis (e.g., liveness), which moves information backward.  Note
    slide 5, which states that dynamic properties of a program are
    undecidable.  
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Handout 26: “Code Optimization” and Lectures 15 and 16: “Global
    Optimization” and “Global Optimization II”**
    Stanford University: Keith Schwarz’s CS143 Compilers: Handout 26:
    “[Code
    Optimization](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF)
    and Lectures 15 and 16: “[Global
    Optimization](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF)
    and “[Global Optimization
    II](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF)  
        
     Instructions: Select the PDF for Handout 26.  Read pages 10 through
    16.  This material overlaps the previous reading, but it is a nice
    narrative summary of global optimizations.  In addition, it includes
    machine optimizations.  Note the last section, “Optimization Soup,”
    which mentions the limitations of optimization.  Select the PDF for
    the lectures and read them.  The lectures cover the material in more
    detail and present it in a unified formal way using semilattices.   
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpages above.

-   **Reading: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer
    Language Engineering: Lectures 10, 11 and 12: “Introduction to
    dataflow analysis” and “Foundations of dataflow analysis”**
    Link: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer Language
    Engineering: Lectures 10, 11 and 12: “[Introduction to dataflow
    analysis](http://www.saylor.org/site/wp-content/uploads/2012/01/CS304-9.4-INTRODUCTIONDATAFLOW.pdf)”
    (PDF) and “[Foundations of dataflow
    analysis](http://www.saylor.org/site/wp-content/uploads/2012/01/CS304-9.4-FOUNDATIONSDATAFLOW.pdf)”
    (PDF)  
        
     Instructions: Please scan over the slides.  They repeat some of the
    material from above readings.  However, they are an excellent
    review, and go into detail on the formalism that underlies global
    optimizations.   
        
     Terms of Use: The resources above are released under an
    [Attribution-NonCommercial-ShareAlike License 3.0 Unported (CC
    BY-NC-SA
    3.0)](http://creativecommons.org/licenses/by-nc-sa/3.0/) (HTML). 
    They are attributed to MIT and the original resources can be found
    [here](http://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-035-computer-language-engineering-spring-2010/lecture-notes/) (PDF).

**9.5 Code Optimization** <span id="9.5"></span> 
*Note: Slides 25 and 26 of the reading for 9.3, on peephole
optimization, apply to this section.  *

-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Lecture 19: “Code Optimization”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Lecture
    19: “[Code
    Optimization](http://www.keithschwarz.com/cs143/WWW/sum2011/)”
    (PDF)  
        
     Instructions: Select the PDF for Lecture 19, slides 1 through 225. 
    This chapter discusses optimizations that depend on the machine. 
    Read about pipelining, data dependency, instruction scheduling,
    locality optimization, loop reordering, structure peeling, and
    optimizations for parallelism.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Reading: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer
    Language Engineering: Lectures 13, 14, 15, 16, 17: “Introduction to
    code optimization: instruction scheduling,” “Loop optimization:
    instruction scheduling,” “More loop optimizations,” “Register
    allocation,” “Parallelization”**
    Link: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer Language
    Engineering: Lectures 13, 14, 15, 16, 17: “[Introduction to code
    optimization: instruction
    scheduling](http://www.saylor.org/site/wp-content/uploads/2012/01/CS304-9.5-INTRODUCTIONCODEOPTIMIZATION.pdf),”
    (PDF) “[Loop optimization: instruction
    scheduling](http://www.saylor.org/site/wp-content/uploads/2012/01/CS304-9.5-LOOPOPTIMIZATION.pdf),”
    (PDF) “[More loop
    optimizations](http://www.saylor.org/site/wp-content/uploads/2012/01/CS304-9.5-MORELOOPOPTIMIZATION.pdf),”
    (PDF) “[Register
    allocation](http://www.saylor.org/site/wp-content/uploads/2012/01/CS304-9.5-REGISTERALLOCATION.pdf),”
    (PDF)
    “[Parallelization](http://www.saylor.org/site/wp-content/uploads/2012/01/CS304-9.5-PARALLELIZATION.pdf)”
    (PDF)  
        
     Instructions: Please scan over the slides.  If you find a part that
    is helpful and adds to your knowledge of optimizations, read it. 
    These slides repeat some of the material from above readings. 
    However, they are an excellent review, concise and clear, and
    reinforce key points.  They also provide additional examples.   
        
     Terms of Use: The resources above are released under an
    [Attribution-NonCommercial-ShareAlike License 3.0 Unported (CC
    BY-NC-SA
    3.0)](http://creativecommons.org/licenses/by-nc-sa/3.0/) (HTML). 
    They are attributed to MIT and the original resources can be found
    [here](http://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-035-computer-language-engineering-spring-2010/lecture-notes/) (PDF).

-   **Reading: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer
    Language Engineering: Lectures 18: “Memory optimization”**
    Link: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer Language
    Engineering: Lectures 18: “[Memory
    optimization](http://www.saylor.org/site/wp-content/uploads/2012/01/CS304-9.5-MEMORYOPTIMIZATION.pdf)”
    (PDF)  
        
     Instructions: Please read the slides on memory optimization. 
    Recall that optimization includes memory as well as speed.  
        
     Terms of Use: The resource above is released under an
    [Attribution-NonCommercial-ShareAlike License 3.0 Unported (CC
    BY-NC-SA
    3.0)](http://creativecommons.org/licenses/by-nc-sa/3.0/) (HTML).  It
    is attributed to MIT and the original resource can be found
    [here](http://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-035-computer-language-engineering-spring-2010/lecture-notes/) (PDF).

**9.6 Verification and Validation of Code Optimization** <span
id="9.6"></span> 
-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Handout 26: “Code Optimization” and Lecture 14: “IR Optimization”**
    Link: Link: Stanford University: Keith Schwarz’s Handout 26: “[Code
    Optimization](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF)
    and Lecture 14: “[IR
    Optimization](http://www.keithschwarz.com/cs143/WWW/sum2011/)”
    (PDF)  
        
     Instructions: Select the PDF for Lecture 14.  Read slides 18
    through 20 and slides 24 through 32.  These slides essentially state
    that an optimization must not change the behavior of the generated
    code.  This includes introducing errors and changing the semantics. 
    The V&V (verification and validation) techniques mentioned for the
    other parts of a compiler also apply to optimization.  In addition,
    these slides suggest that the formalisms for optimization—e.g.,
    soundness—are directly applicable.   
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpages above.

-   **Assessment: University of Copenhagen: Torben Ægidius Mogensen’s
    Basics of Compiler Design: “Chapter 11: Analysis and Optimization”**
    Link: University of Copenhagen: Torben Ægidius Mogensen’s *Basics of
    Compiler Design:* “[Chapter 11: Analysis and
    Optimization](http://www.diku.dk/hjemmesider/ansatte/torbenm/Basics/)”
    (PDF)  
        
     Instructions: Please click on the link above, and select “Get the
    book contents” to download a PDF version of the book.  Complete the
    following:  
        
     Exercise \#1: Do Exercise 11.1 parts a) and b) in Mogensen’s
    “Chapter 11 Analysis and Optimization” on page 254.  
        
     This exercise will give you some practice with code optimization
    and is based on Chapter 11, which covers analysis and optimization. 
    The exercise uses common subexpression elimination as an example of
    optimization.  You can check your answers with the Saylor
    Foundation’s “[Answer
    Key](http://www.saylor.org/site/wp-content/uploads/2012/06/CS304-Unit-9-Answer-Key-to-Assessment-7-FINAL.pdf)”
    (PDF).  
        
     This assessment should take you approximately 3 hours to
    complete.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.


