---
layout: default
title: "CS304: Compilers"
course_description: "A detailed introduction to programming language translation, including the functions and general organization of compiler design and interpreters. Focuses on the study of syntax, semantics, ambiguities, procedures replication, iteration, and recursion in these languages."
next: ../Unit06
previous: ../Unit04
---
**Unit 5: Parsing and Syntax Analysis** <span id="5"></span> 
*The next step of the compilation process is parsing. * *This step also
has a foundation in formal languages and automata. * *Parsing takes
input from the Lexical Analysis step and builds a parse tree, which will
be used in future steps to develop the machine code.  In this unit, we
will define parsing and identify its uses.  We will also discuss two
parsing strategies, Top-Down Parsing and Bottom-Up Parsing, examining
what it means to approach parsing from each standpoint and taking a look
at an example of each.  By the end of the unit, you will understand
parsing techniques with regards to compilers, and be able to discuss
each of the two main approaches.*

**Unit 5 Time Advisory**  
This unit should take approximately 27 hours to complete.  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 5.1: 2 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 5.2: .5 hour  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 5.3: .5 hour  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 5.4: 1 hour  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 5.5: 15 hours  
<span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; "><span
id="cke_bm_525S" style="display: none; "> </span><span id="cke_bm_526S"
style="display: none; "> </span><span id="cke_bm_527S"
style="display: none; "> </span><span id="cke_bm_528S"
style="display: none; "> </span><span id="cke_bm_529S"
style="display: none; "> </span><span id="cke_bm_530S"
style="display: none; "> </span><span id="cke_bm_531S"
style="display: none; "> </span><span id="cke_bm_532S"
style="display: none; "> </span>☐    </span>Subunit 5.5.1: 6 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 5.5.2: 9 hours <span id="cke_bm_532E"
style="display: none; "> </span><span id="cke_bm_531E"
style="display: none; "> </span><span id="cke_bm_530E"
style="display: none; "> </span><span id="cke_bm_529E"
style="display: none; "> </span>

<span id="cke_bm_528E" style="display: none; "> </span><span
id="cke_bm_527E" style="display: none; "> </span><span id="cke_bm_526E"
style="display: none; "> </span><span id="cke_bm_525E"
style="display: none; "> </span>  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 5.6: 8 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 5.7: .1 hour  

**Unit5 Learning Outcomes**  
Upon successful completion of this unit, the student will be able to:  
  
-   <span dir="LTR">Explain parsing in the context of the compilation
    process.</span>
-   <span dir="LTR">Describe several approaches or strategies used for
    parsing.</span>
-   <span dir="LTR">Specify the functions of a parser in performing
    syntax analysis.</span>
-   <span dir="LTR">Describe the handling of ambiguities.</span>
-   <span dir="LTR">Summarize the design and construction of a
    scanner.</span>

**5.1 Parser Introduction and Overview** <span id="5.1"></span> 
-   **Reading: Torben Ægidius Mogensen’s Basics of Compiler Design:
    “Chapter 3: Syntax Analysis”**
    Link: Torben Ægidius Mogensen’s *Basics of Compiler Design*:
    “[Chapter 3: Syntax
    Analysis](http://www.diku.dk/hjemmesider/ansatte/torbenm/Basics/)”
    (PDF)  
        
     Instructions: Select the link and click “Get the book contents” to
    download a PDF version of the book.  Please read through section
    3.1.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Reading: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Notes Lecture 6 “Parsing”**
    Link: University of California, Berkeley: Paul Hilfinger’s CS164
    Programming and Compilers: Notes Lecture 6
    “[Parsing](http://inst.eecs.berkeley.edu/~cs164/sp11/lectures/)”
    (PDF)  
      
     Instructions: Select the PDF link for the Notes for Lecture 6 on
    parsing.  Again, this material overlaps some of the readings later
    in the class.  However, they add additional information and have a
    practical perspective.  
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**5.2 Requirements of a Parser** <span id="5.2"></span> 
-   **Reading: Wikipedia: “Parsing”**
    Link: Wikipedia:
    “[Parsing](https://resources.saylor.org/archived/wp-content/uploads/2012/01/CS304-5.2-PROGRAMMINGWIKI.pdf)”
    (PDF)  
        
     Instructions: Please read the following three paragraphs:
    “Programming languages,” “Overview of the process,” and “Types of
    Parsers.”  Requirements of a parser include: build internal
    representation of the input tokens (which come from the scanner);
    check that the input string of tokens is legal in the language of
    the compiler (i.e., that it can be derived from the start symbol);
    and determine the derivation steps for the input string of tokens. 
    In addition, the parser should be reliable, efficient (how efficient
    depends on the intended use), user friendly (i.e., provide clear,
    accurate messages), and supportable (assuming that the parser will
    be used for a long time).   
        
     Terms of Use: The article above is released under a [Creative
    Commons Attribution-Share-Alike License
    3.0](http://creativecommons.org/licenses/by-sa/3.0/) (HTML).  You
    can find the original Wikipedia version of this
    article [here](http://en.wikipedia.org/wiki/Parsing#Programming_languages) (HTML). 

**5.3 Functions of a Parser** <span id="5.3"></span> 
-   **Reading: Torben Ægidius Mogensen’s Basics of Compiler Design:
    “Chapter 3: Syntax Analysis”**
    Link: Torben Ægidius Mogensen’s *Basics of Compiler Design*:
    “[Chapter 3: Syntax
    Analysis](http://www.diku.dk/hjemmesider/ansatte/torbenm/Basics/)”
    (PDF)  
        
     Instructions: Select the link and click “Get the book contents” to
    download a PDF version of the book.  Please read subsections 3.4 –
    3.6.  The functions of a parser include: building an internal
    representation of the derivation tree and related parser
    information, and resolving ambiguities of the language pertaining to
    the input string of tokens.   
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Lecture 3: “Top Down Parsing”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Lecture
    3: “[Top-Down
    Parsing](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF)  
        
     Instructions: Select the PDF for Lecture 3 and read slide 4.  The
    first bullet is a requirement statement and the third bullet is a
    function statement.  An additional function is the output of
    meaningful and accurate messages, including error messages.   
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**5.4 Formal Language Considerations** <span id="5.4"></span> 
-   **Reading: Torben Ægidius Mogensen’s Basics of Compiler Design:
    “Chapter 3: Syntax Analysis”**
    Link: Torben Ægidius Mogensen’s *Basics of Compiler Design*:
    “[Chapter 3: Syntax
    Analysis](http://www.diku.dk/hjemmesider/ansatte/torbenm/Basics/)”
    (PDF)  
        
     Instructions: Note that this subsection is just a review of what
    has been covered in units 2 and 3.  Select the link and click “Get
    the book contents” to download a PDF version of the book.  Please
    read subsections 3.2 and 3.3.  The main idea is that context free
    languages are used to build efficient parsers, but are supplemented
    with special techniques to resolve ambiguities.   
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**5.5 Design of a Parser** <span id="5.5"></span> 
**5.5.1 Top-Down Parsers** <span id="5.5.1"></span> 
-   **Reading: Torben Ægidius Mogensen’s Basics of Compiler Design:
    “Chapter 3: Syntax Analysis”**
    Link: Torben Ægidius Mogensen’s *Basics of Compiler Design*:
    “[Chapter 3: Syntax
    Analysis](http://www.diku.dk/hjemmesider/ansatte/torbenm/Basics/)”
    (PDF)  
        
     Instructions: Select the link and click “Get the book contents” to
    download a PDF version of the book.  Please study 3.7 – 3.13, on
    pages 68 – 88.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Notes 9 and Lectures 3 and 4: “Top-Down Parsing”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Notes 9
    and Lectures 3 and 4: “[Top-Down
    Parsing](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF)  
        
     Instructions: Select the PDF for Notes 9 and Lectures 3 and 4 on
    Top-Down parsing.   
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Reading: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer
    Language Engineering: Lecture 4: “Top-Down Parsing”**
    Link: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer Language
    Engineering: Lecture 4: “[Top-Down
    Parsing](https://resources.saylor.org/archived/wp-content/uploads/2012/01/CS304-5.5.1-TOPDOWNPARSING.pdf)”
    (PDF)  
        
     Instructions: This material overlaps some of the previous
    readings.  However, it presents the material using examples.  Scan
    over the slides, studying those that you feel will benefit you.   
        
     Terms of Use: The article above is released under a [Creative
    Commons Attribution-Share-Alike License
    3.0](http://creativecommons.org/licenses/by-sa/3.0/) (HTML).  You
    can find the original version of this
    article [here](http://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-035-computer-language-engineering-spring-2010/lecture-notes/) (PDF).

-   **Reading: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Notes for Lecture 8 “Top-down
    parsers.”**
    Link: University of California, Berkeley: Paul Hilfinger’s CS164
    Programming and Compilers: Notes for Lecture 8 “[Top-down
    parsers](http://webcast.berkeley.edu/playlist#c,d,Computer_Science,03D59E2ECDDA66DF).”
    (PDF)  
      
     Instructions: Select the PDF links.  This material overlaps
    previous readings, but provides a practical view.  Look over the
    material and study the parts you feel will benefit you.  
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Web Media: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Video Lectures: “Lecture 7” and
    “Lecture 8”**
    Link: University of California, Berkeley: Paul Hilfinger’s CS164
    Programming and Compilers: Video Lectures: “[Lecture
    7](http://www.youtube.com/watch?v=ojNMHjOsZT8)” (YouTube) and
    “[Lecture 8](http://www.youtube.com/watch?v=uCKOAmbiHy8)”
    (YouTube)  
      
     Instructions: Please view both lectures.  
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**5.5.2 Bottom-Up Parsers** <span id="5.5.2"></span> 
-   **Reading: Torben Ægidius Mogensen’s Basics of Compiler Design:
    “Chapter 3: Syntax Analysis”**
    Link: Torben Ægidius Mogensen’s *Basics of Compiler Design*:
    “[Chapter 3: Syntax
    Analysis](http://www.diku.dk/hjemmesider/ansatte/torbenm/Basics/)”
    (PDF)  
        
     Instructions: Select the link and click “Get the book contents” to
    download a PDF version of the book.  Please study from 3.14 – 3.18,
    on pages 88 – 104.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Notes 10 and 11 and Lectures 4, 5, 6: “Bottom-Up Parsing”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Notes 10
    and 11 and Lectures 4, 5, 6: “[Bottom-Up
    Parsing](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF)  
        
     Instructions: Select the PDF for Notes 10 and 11, and Lectures 4, 5
    (1–263), 6 (1–47) on Bottom-Up parsing.   
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Reading: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer
    Language Engineering: Lecture 3: “Introduction to shift-reduce
    parsing”**
    Link: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer Language
    Engineering: Lecture 3: “[Introduction to shift-reduce
    parsing](https://resources.saylor.org/archived/wp-content/uploads/2012/01/CS304-5.5.2-SHIFTREDUCEPHASING.pdf)”
    (PDF)  
        
     Instructions: This material overlaps some of the previous
    readings.  However, it presents the material on bottom-up parsing
    using examples.  Scan slides 1–59, studying those that you feel will
    benefit you.   
        
     Terms of Use: The article above is released under a [Creative
    Commons Attribution-Share-Alike License
    3.0](http://creativecommons.org/licenses/by-sa/3.0/) (HTML).  You
    can find the original version of this
    article [here](http://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-035-computer-language-engineering-spring-2010/lecture-notes/) (HTML).  

-   **Reading: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Notes for Lectures 10 and 12
    “Parsing: Earley’s Algorithm” and “Bottom-up parsing”**
    Link: University of California, Berkeley: Paul Hilfinger’s CS164
    Programming and Compilers: Notes for Lectures 10 and 12 “[Parsing:
    Earley’s
    Algorithm](http://inst.eecs.berkeley.edu/~cs164/sp11/lectures/)”
    (PDF) and “[Bottom-up
    parsing](http://inst.eecs.berkeley.edu/~cs164/sp11/lectures/).”
    (PDF)  
      
     Instructions: Select the PDF links.  This material overlaps and
    reinforces previous readings, and, in addition, provides a practical
    view.  Look over the material and study that which you feel will
    benefit you.  
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpages above.

-   **Web Media: YouTube: University of California, Berkeley: Paul
    Hilfinger’s CS164 Programming and Compilers: Video Lectures:
    “Lecture 10,” “Lecture 11,” “Lecture 12,” “Lecture 13,” “Lecture
    14”**
    Link: YouTube: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Video Lectures: “[Lecture
    10](http://www.youtube.com/watch?v=Rr3cTLSXZ14),” (YouTube)
    “[Lecture 11](http://www.youtube.com/watch?v=a7eYcFXo1WA),”
    (YouTube) “[Lecture
    12](http://www.youtube.com/watch?v=JNroY8P-u2g),” (YouTube)
    “[Lecture 13](http://www.youtube.com/watch?v=nmA9y1QGIiI),”
    (YouTube) “[Lecture 14](http://www.youtube.com/watch?v=ySjyNTfBNzA)”
    (YouTube)  
      
     Instructions: View the entirety of the lectures above.  
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpages above.

**5.6 Construction of a Parser** <span id="5.6"></span> 
-   **Reading: Torben Ægidius Mogensen’s Basics of Compiler Design:
    “Chapter 3: Syntax Analysis”**
    Link: Torben Ægidius Mogensen’s *Basics of Compiler Design*:
    “[Chapter 3: Syntax
    Analysis](http://www.diku.dk/hjemmesider/ansatte/torbenm/Basics/)”
    (PDF)  
        
     Instructions: Select the link and click “Get the book contents” to
    download a PDF version of the book.  Please study from 3.15 to the
    end of Chapter 3.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Reading: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Notes for Lecture 12 “Bottom-up
    parsing.”**
    Link: University of California, Berkeley: Paul Hilfinger’s CS164
    Programming and Compilers: Notes for Lecture 12 “[Bottom-up
    parsing](http://inst.eecs.berkeley.edu/~cs164/sp11/lectures/).”
    (PDF)  
      
     Instructions: Select the PDF links.  Study slides 36 – 48.  Note
    slide 47, which summarizes in a diagram the various parsing
    algorithms.  
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Web Media: YouTube: University of California, Berkeley: Paul
    Hilfinger’s CS164 Programming and Compilers: Video Lectures:
    “Lecture 13,” and “Lecture 14”**
    Link: YouTube: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Video Lectures: “[Lecture
    13](http://www.youtube.com/watch?v=nmA9y1QGIiI),” (YouTube) and
    “[Lecture 14](http://www.youtube.com/watch?v=ySjyNTfBNzA)”
    (YouTube)  
      
     Instructions: Select the lecture 13 video and view from the
    26-minute mark to the end of the video lecture.  Also, view lecture
    14.   
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpages above.

-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Notes 12, 14, and 16 and Lectures 5, 6, and 7: “Bottom-Up Parsing”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Notes
    12, 14, and 16 and Lectures 5, 6, and 7: “[Bottom-Up
    Parsing](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF)  
        
     Instructions: Select the PDF for Notes 12, 14, and 16 and study
    them.  Select lectures 5 (264 to the end), 6 (48 to the end), and 7
    (91 to the end) and read the indicated slides.   
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Reading: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer
    Language Engineering: Lecture 3: “Introduction to shift-reduce
    parsing” and “Parse table formats” and Lecture 4: “Intermediate
    formats”**
    Link: MIT: S. Amarasinghe and M. Rinard’s 6.035 Computer Language
    Engineering: Lecture 3: “[Introduction to shift-reduce
    parsing](https://resources.saylor.org/archived/wp-content/uploads/2012/01/CS304-5.5.2-SHIFTREDUCEPHASING.pdf)”
    (PDF) and “[Parse table
    construction](https://resources.saylor.org/archived/wp-content/uploads/2012/01/CS304-5.6-PARSETABLECONSTRUCTION.pdf)”
    (PDF)  
        
     Instructions: This material overlaps, but also complements, some of
    the previous readings.  Scan over the slides, studying those that
    you feel will benefit you.  In particular, in the introduction to
    shift-reduce parsing, just look at slides 60 to the end.  
        
     Terms of Use: The article above is released under a [Creative
    Commons Attribution-Share-Alike License
    3.0](http://creativecommons.org/licenses/by-sa/3.0/) (HTML).  You
    can find the original version of this
    article [here](http://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-035-computer-language-engineering-spring-2010/lecture-notes/) (PDF). 

**5.7 Verification and Validation of a Parser** <span id="5.7"></span> 
*Note: The note in section 4.7 on Verification and Validation (V&V) of a
Scanner also applies to the V&V of a parser.  If a parser is constructed
using a parser generator, V&V depends on the V&V of the generator and
the correctness of the input to the generator.  Formal proof methods,
reviews, and testing can be used to verify the correctness of a parser
(i.e., that it produces the correct derivation for a legal program and
that it outputs correct error messages for incorrect syntax in the
program).  Formal proof methods alone are not practical for current
programming languages, but in conjunction with testing can be used to
verify the correctness of a parser.  Validation (i.e., satisfaction of
the requirements of a parser) requires testing and operational use. *

-   **Assessment: ePaperPress: Tom Niemann's “Tutorial on LEX and
    YACC”**
    Link: ePaperPress: Tom Niemann's “[Tutorial on LEX and
    YAC](http://epaperpress.com/lexandyacc/)” (PDF)  
        
     Instructions: Select the link above and choose the PDF format.  In
    this exercise, you will be introduced to LEX and YACC, which stand
    for Lexer (short for lexical analyzer) and Yet Another
    Compiler-Compiler.  They are generators, i.e. programs that generate
    other programs, in this case, a scanner and a parser.  Our focus in
    this Assessment will be on YACC.  Select the link for the PDF for
    Niemann's Tutorial above, and read the part of the tutorial on
    YACC.  This tutorial explains YACC and how YACC and LEX interface. 
    LEX and YACC are the original programs, and just as Flex is an open
    software version for LEX, Bison is an open software version for
    YACC.  
      
     **Exercise \#1: **Add a block diagram depicting YACC, C compiler,
    and the connections with their input and out files, and the
    connections to LEX.  
        
     **Exercise \#2: **In Assessment 3, we developed a scanner for
    recognizing the language L of Exercise \#1 of Assessment 1.  Here,
    instead of using LEX, we will use YACC.  YACC builds a context free
    syntax analyzer, i.e. a parser for the language we want to analyze;
    LEX builds a regular expression analyzer.  Because the former is
    more powerful than the latter, whatever LEX can do, YACC should be
    able to also do.  For this exercise, describe L by a grammar that
    can be input to YACC to create a parser for recognizing the strings
    of L.  
        
     **Exercise \#3 (Optional):** For this exercise, we will be build
    the parser for the language L, used in \#3 above, to check our
    solution to \#3.  We will use several software tools: a generator
    for scanners (lexical analyzers), a C compiler, and text editor for
    creating input files, and a parser generator.  We will use a scanner
    generator, called FLEX, based on the original LEX.  The particular
    version of Flex we will use is Win\_Flex, a FLEX scanner generator
    that runs on Windows.  There are several good compilers available, 
    cyngwin and gcc.  We will use gcc.  There are also several editors
    for creating input files; we will use Notepad++.  For the parser
    generator, we will use Bison, an open source parser generator based
    on the original YACC.  The version of Bison that we will use is
    Win\_Bison, a version that runs on Windows.  You may download the
    executables for
    [Win\_Flex](http://gnuwin32.sourceforge.net/packages/flex.htm) and
    [Win\_Bison](http://gnuwin32.sourceforge.net/packages/bison.htm).  
        
     You can check your answers with The Saylor Foundation’s “[Answer
    Key](https://resources.saylor.org/archived/wp-content/uploads/2012/06/CS304-Unit-5-Answer-Key-to-Assessment-4-FINAL.pdf)”
    (PDF). This assessment should take approximately 3 hours to complete
    (not including installation of Bison and the Gcc compiler).  
        
     Installation Guidance for installing Flex, Bison, and the gcc
    compiler were given at the end of the problem statement for
    Asseesment 3 Exercise \#4.  Additional guidance is included in the
    following problem statement.  
        
     a) Install Bison on your computer.  (FLEX should already be
    installed from Exercise \#3).  Installation of Bison may have been
    done when you installed FLEX.  If not, see the Installation guidance
    in the instructions for Assessment 3.  The installation of Bison
    includes documentation.  Good manuals can be found
    [here](http://gnuwin32.sourceforge.net/packages/flex.htm) for FLEX
    for Windows and
    [here](http://gnuwin32.sourceforge.net/packages/bison.htm) for Bison
    for Windows.  
      
     b) If you do not have a C compiler, install a C compiler on your
    computer.  Instructions for installing the gcc compiler can be found
    on [YouTube](http://www.youtube.com/watch?v=w2XLvEcSrgo).  
      
     c) Check your answer to Exercise 2 by using Bison and your C
    compiler to generate a simple parser for language L – strings of 0's
    and 1's, not including 00, and ending in 1.  Test the parser by
    running it on a collection of sample input strings that are in the
    language L.  Also, run it on some strings that are not in L.  
        
     Terms of Use: Please respect the copyright and terms of use on the
    webpages displayed above.


