**Unit 1: Introduction to Compilers** <span id="1"></span> 
*The compilation process is one of the stepsin executing a program. 
Understanding how compilerswork and what goes on “behind the scenes”
will help you get better at developing software.  This unit will first
provide you with an introduction to the compiler, its history, compiler
structure and design, and the types of compilers.  By the end of this
unit, you will be able to describe the steps of the  compilation
process.*

**Unit 1 Time Advisory**  
This unit should take approximately 8hours to complete.  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 1.1: 1hour  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 1.2: 2hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 1.3: 1 hour  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 1.4: 4 hours

**Unit1 Learning Outcomes**  
Upon successful completion of this unit, the student will be able to:  
  
-   <span dir="LTR">Describe the </span>role and applications of
    compilers.
-   <span dir="LTR">Define compiler, interpreter, and translator, and
    recount the early history of compilers.</span>
-   <span dir="LTR">Explain the process for development of a compiler in
    the context of a systems process.</span>
-   <span dir="LTR">Explain the structure of compilers and the
    corresponding steps in the compilation process.</span>

**1.1 System View of Compilers** <span id="1.1"></span> 
*Note: A compiler is a complex software system, and, as such, has a
system life cycle that starts with a need, transitions to design and
construction/implementation, undergoes testing, transitions to use in
its intended environment, undergoes maintenance over its life, and ends
with “disposal” and archival storage.  The activities, various work
products, and documentation that comprise the processes used during the
system’s life must be carefully planned.  The part of the system life
cycle that deals with the design and construction of the compiler is
called the development life cycle.  This course focuses on the
development life cycle, but the overall system life cycle must be kept
in mind.*   
  
 *The term “compiler process” is related to, but different from the
system (life cycle) process.  The “compiler process” refers to the
processing that a compiler does when it performs its function of
translation of a source program to a target program.  It also refers to
the approach taken to design a compiler.  Design, in fact, is one
activity in the system (life cycle) process.*

**1.2 Overview of Compilers** <span id="1.2"></span> 
**1.2.1 Compiler Definitions, Terminology, and Anatomy of a Compiler**
<span id="1.2.1"></span> 
-   **Reading: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer
    Language Engineering: Lecture 1: “Introduction”**
    Link: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer Language
    Engineering: Lecture 1:
    “[Introduction](https://resources.saylor.org/wwwresources/archived/site/wp-content/uploads/2012/01/CS304-MIT1.1.pdf)”
    (PDF)  
        
     Instructions: For a definition of a compiler and some terminology,
    study slides 13–26.  For an anatomy of a compiler see slides 27–47. 
    For examples of optimization see slides 48–76.  These slides have
    good examples of compiler output for a given input and a lot of
    examples of optimizations.  A compiler translates a high-level
    language to a low-level language.  
        
     Terms of Use:  The resource above is released under an
    [Attribution-NonCommercial-ShareAlike License 3.0 Unported (CC
    BY-NC-SA
    3.0)](http://creativecommons.org/licenses/by-nc-sa/3.0/) (HTML).  It
    is attributed to MIT and the original resource can be found
    [here](http://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-035-computer-language-engineering-spring-2010/lecture-notes/) (PDF). 

-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Lecture 00: “Introduction to Compilers”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Lecture
    00: “[Introduction to
    Compilers](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF)  
        
     Instructions: For a slightly different overview of compilers,
    select the first link in the lecture column on the far right labeled
    00: Introduction to Compilers.  Please study slides 8–47.  These
    slides make an analogy between compilation and the
    equivalence-preserving transformations of an electrical circuit.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Reading: Wikipedia’s “Compilers”**
    Link: Wikipedia’s
    “[Compilers](https://resources.saylor.org/wwwresources/archived/site/wp-content/uploads/2012/01/CS304-1.2.1-COMPILERSWIKI.pdf)”
    (PDF)  
        
     Instructions: Read the short paragraph on Related Techniques, which
    defines related terms: language translator, assembler, disassembler,
    and decompiler.  
        
     Terms of Use: The article above is released under a [Creative
    Commons Attribution-Share-Alike License
    3.0](http://creativecommons.org/licenses/by-sa/3.0/) (HTML).  You
    can find the original Wikipedia version of this
    article [here](http://en.wikipedia.org/wiki/Compilers#Related_techniques) (HTML). 

**1.2.2 History** <span id="1.2.2"></span> 
-   **Reading: Wikipedia’s “Compiler History”**
    Link: Wikipedia’s “[Compiler
    History](https://resources.saylor.org/wwwresources/archived/site/wp-content/uploads/2012/01/CS304-1.2.2-COMPILERSHISTORYWIKI.pdf)”
    (PDF)  
        
     Instructions: Please read the interesting history of the early
    compilers and computer pioneers, such as Grace Hopper, who worked on
    the first COBOL compiler.  
        
     Terms of Use: The article above is released under a [Creative
    Commons Attribution-Share-Alike License
    3.0](http://creativecommons.org/licenses/by-sa/3.0/) (HTML).  You
    can find the original Wikipedia version of this
    article [here](http://en.wikipedia.org/wiki/Compiler#History) (HTML). 

**1.2.2.1 Translation** <span id="1.2.2.1"></span> 
-   **Reading: Torben Ægidius Mogensen’s Basics of Compiler Design:
    “Chapter 1: Introduction”**
    Link: Torben Ægidius Mogensen’s *Basics of Compiler Design*:
    “[Chapter 1:
    Introduction](http://www.diku.dk/hjemmesider/ansatte/torbenm/Basics/)”
    (PDF)  
        
     Instructions: Select the link and click “Get the book contents” to
    download a PDF version of the book.  Please read sections 1.1, 1.2,
    and 1.3. Note that “compile” means to translate from a high-level
    language, used by humans, to a low-level language used by a
    computer.  A high-level language uses concepts, objects, and tasks
    performed by a human, whereas a low-level or machine language uses
    concepts, objects, and tasks performed by machines.  This reading
    also applies to the subsections 1.2.2.1.1 – 1.2.2.1.3, 1.2.2.2, and
    to section 1.3 of this course.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**1.2.2.1.1 Translate Source Language to Target Language** <span
id="1.2.2.1.1"></span> 
*Note: The reading for this subsection is covered by the reading for
1.2.2.1 above.  The input language to a compiler, typically a
programming language, is called the source language.  The output
language of a compiler is called the target language or object code,
typically an assembly language or machine language. *

**1.2.2.1.2 Object Code and Executables** <span id="1.2.2.1.2"></span> 
*Note: The reading for this subsection is covered by the reading for
1.2.2.1.*

**1.2.2.1.3 Platform Independent Compilers** <span
id="1.2.2.1.3"></span> 
*Note: The reading for this subsection is covered by the reading for
1.2.2.1 above.  In the textbook reading, the author describes seven
phases of a compiler.  The middle phase is called Intermediate Code
Generation.  The intermediate code is independent of a particular target
machine.  One of the back-end phases is called Machine Code Generation,
which translates the machine-independent code to machine-dependent code
for a particular computer.*

**1.2.2.2 Comparison between Compiler and Interpreter** <span
id="1.2.2.2"></span> 
*Note: The reading for subsection 1.2.2.1 above covers this
subsection.  *

**1.2.3 Other Applications** <span id="1.2.3"></span> 
-   **Reading: Torben Ægidius Mogensen’s Basics of Compiler Design:
    “Chapter 1: Introduction”**
    Link: Torben Ægidius Mogensen’s *Basics of Compiler Design*:
    “[Chapter 1:
    Introduction](http://www.diku.dk/hjemmesider/ansatte/torbenm/Basics/)”
    (PDF)  
        
     Instructions: Select the link and click “Get the book contents” to
    download a PDF version of the book.  Please read section 1.4, which
    gives reasons for studying compilers.  In the discussion, the author
    suggests other applications for compiler techniques and tools.  He
    specifically mentions domain-specific languages.  Other applications
    derive from techniques and methods used in compilers.  For example,
    if the input to a software system can be described using a formal
    grammar, then lexical- and syntax-phase techniques may be the most
    effective and efficient to use for inputting, verifying, and
    representing the data for processing.  Front-end techniques can also
    be applied via software tools to the enforcement of development and
    programming standards and procedures.  Knowledge of compiler
    techniques and methods helps in the design of new programming
    languages, new hardware architectures, generation of software
    applications, and the design of software tools.   
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**1.2.4 Hardware Compilation** <span id="1.2.4"></span> 
-   **Reading: Wikipedia: “Compilers”**
    Link: Wikipedia:
    “[Compilers](https://resources.saylor.org/wwwresources/archived/site/wp-content/uploads/2012/01/CS304-1.2.4-COMPILERSHARDWAREWIKI.pdf)”
    (PDF)  
        
     Instructions: Please read the short paragraph on Hardware
    Compilation.  Note that hardware compilation refers to the
    translation of a software program to a hardware representation.  
        
     Terms of Use: The article above is released under a [Creative
    Commons Attribution-Share-Alike License
    3.0](http://creativecommons.org/licenses/by-sa/3.0/) (HTML).  You
    can find the original Wikipedia version of this
    article [here](http://en.wikipedia.org/wiki/Compilers#Hardware_compilation) (HTML). 

**1.3 Systems Process for Development of a Compiler** <span
id="1.3"></span> 
**1.3.1 Need for Compilers** <span id="1.3.1"></span> 
*Note: The reading in section 1.2.2.1 above applies to this section. 
The need for compilers arises from the need for high-level languages,
which are more relevant for problem solving and software development by
humans.  Moreover, high-level languages are machine independent.  *

**1.3.2 Development Life Cycle Process for a Compiler** <span
id="1.3.2"></span> 
*Note: Since development of a compiler is a relatively complex
system-development effort, typically having many users and developers,
and will be maintained over a life of many years, a formal process
should be used for its development.  The development process should
extend from requirements through verification and validation, and should
include reviews, tests, analysis and measures, quality assurance,
configuration control, and key documentation.  The development process
is a part of the overall system life cycle process, which additionally,
includes deployment, maintenance, disposal and archival storage.  The
compiler development process should consist of procedures for writing
and documenting the needs and requirements, the architecture and design,
construction, integration, and verificaton and validation of the
compiler.  Documentation should also include the formal foundationsand
techniques used, tradeoffs made, alternatives evaluated, and the chosen
alternative for design or implementation.  Full coverage of all of these
indetail is beyond the scope of this course.  As we proceed through this
course, however, we include high-level needs, requirements, functions,
performance considerations, and verification and validation issues for a
compiler and its parts.*

**1.4 Compiler Design Overview** <span id="1.4"></span> 
**1.4.1 One-Pass vs. Multi-Pass** <span id="1.4.1"></span> 
-   **Reading: Wikipedia: “One-pass versus multi-pass compilers”**
    Link: Wikipedia: “[One-pass versus multi-pass
    compilers](https://resources.saylor.org/wwwresources/archived/site/wp-content/uploads/2012/01/CS304-1.4.1.-ONEPASSWIKI.pdf)”
    (PDF)  
        
     Instructions: Please read the paragraph on one-pass and multi-pass
    compilers.  This distinction was more relevant in the early days of
    computing, when computer memory was limited and processing time was
    much slower compared to current computers.  This reading applies to
    all the subsections of 1.4.1.   
        
     Terms of Use: The article above is released under a [Creative
    Commons Attribution-Share-Alike License
    3.0](http://creativecommons.org/licenses/by-sa/3.0/) (HTML).  You
    can find the original Wikipedia version of this
    article [here](http://en.wikipedia.org/wiki/Compiler#One-pass_versus_multi-pass_compilers) (HTML). 

**1.4.1.1 One-Pass** <span id="1.4.1.1"></span> 
*Note: A “pass” refers to reading and processing the input, i.e., source
or source representation.  The reading for 1.4.1 gives the rationale for
a one-pass design—namely, a one-pass compiler is simpler to implement. 
However, more sophisticated processing, such as optimizations, may
require multiple passes over the source representation.  *

**1.4.1.2 Multi-Pass** <span id="1.4.1.2"></span> 
*Note: The reading for 1.4.1 above includes information on a multi-pass
design.  The compiler is composed of components, which perform the steps
of the compilation process.  Some of the components may make a separate
pass over the source representation—thus, the name of multi-pass. 
Multi-pass compilers are used for translating more complex languages
(for example, high-level language to high-level language), and for
performing more complete optimizations.  Moreover, multi-pass compilers
are easier to verify and validate, because testing and proof of
correctness can be accomplished for the smaller components.  Multi-pass
compilers are also used for translation to an assembler or machine
language for a theoretical machine, and for translation to an
intermediate representation such as bytecode.  Bytecode, or pcode
(portable code), is a compact encoding that uses a one-byte instruction,
and parameters for data or addresses, to represent the results of syntax
and semantic analysis.  The bytecode or pcode is independent of a
particular machine.  It is executed by a virtual machine residing on the
target machine. *

**1.4.2 Structure of a Compiler** <span id="1.4.2"></span> 
-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Handout 01: “CS143 Course Overview”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Handout
    01: “[CS143 Course
    Overview](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF)  
        
     Instructions: Select the link and read the CS143 Course Overview
    handout (not the lecture).  You have studied the lecture
    “Introduction to Compilers” as part of section 1.2.1 above.  The
    handout gives an overview of the structure of a compiler with a good
    explanation.  This handout also applies to subsections 1.4.2.1 and
    1.4.2.2 below.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**1.4.2.1 Front End** <span id="1.4.2.1"></span> 
*Note: The Course Overview handout, referenced in section 1.4.2 above,
pages 2–5, to the end of Intermediate Code Generation, describes the
front-end process, or analysis stage, of the compilation process.  The
intermediate code used as an example is TAC, three-address code.  The
front end, or analysis, consists of lexical analysis, syntax analysis or
parsing, semantic analysis, and intermediate code generation.  Lexical
analysis may be preceded by preprocessing, depending on the language and
the development environment.*

**1.4.2.2 Back End** <span id="1.4.2.2"></span> 
*Note: The Course Overview handout, referenced in section 1.4.2 above,
also applies to this subsection.  Read the handout pages 5–7, up to
Historical Perspective.  These pages explain the back-end, or synthesis
state, of the compilation process, which includes intermediate code
optimization, object code generation, and object code optimization.  The
symbol table and error-handling topics apply to both the front end and
to the back end.  The section on one-pass versus multi-pass complements
the previous explanation, in sections 1.4.1.1 and 1.4.1.2, of the number
of “passes” that a compiler uses.*

**1.4.2.3 Some More History** <span id="1.4.2.3"></span> 
*Note: The Course Overview handout has a very good section on history,
which helps us understand why the structure of a compiler is as
described in previous sections.  Read the Historical Perspective
section, which shows the important influence of programming languages on
the development of compilers. *


