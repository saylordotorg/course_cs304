---
layout: default
title: "CS304: Compilers"
course_description: "A detailed introduction to programming language translation, including the functions and general organization of compiler design and interpreters. Focuses on the study of syntax, semantics, ambiguities, procedures replication, iteration, and recursion in these languages."
next: ../Unit05
previous: ../Unit03
---
**Unit 4: Scanning and Lexical Analysis** <span id="4"></span> 
*Lexical analysis is performed by a scanner, one of the front-end
components of a compiler.  The foundation for lexical analysis is
provided by regular grammars and finite state automata.  This unit
studies scanners and lexical analysis in terms of development process
products: requirements, functions, design, construction, and test.  The
verification of a scanner is done through testing.  Validation is based
on the programming language specifications, and operation of the scanner
as a component of the compiler or application system that uses it.*

**Unit 4 Time Advisory**  
This unit should take approximately 11 hours to complete.  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 4.1: 1 hour  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 4.2: 2 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 4.3: 2 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 4.4: 2 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 4.5: 2 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 4.6: 2 hours  
  
 <span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 21px; text-align: left; -webkit-text-size-adjust: none; ">☐
   </span>Subunit 4.7: .1 hour

**Unit4 Learning Outcomes**  
Upon successful completion of this unit, the student will be able to:  
  
-   <span dir="LTR">Explain scanning and lexical analysis in the context
    of the compilation process.</span>
-   <span dir="LTR">Define </span>*token* and *lexeme*.
-   <span dir="LTR">Specify the functions of a scanner in performing
    lexical analysis.</span>
-   <span dir="LTR">Describe the handling of blanks, keywords, and
    comments.</span>
-   <span dir="LTR">Summarize the design and construction of a
    scanner.</span>

**4.1 Lexical Analysis Introduction and Overview** <span
id="4.1"></span> 
-   **Web Media: YouTube: University of California, Berkeley: Paul
    Hilfinger’s CS164 Programming and Compilers: Video: “Lecture 2”**
    Link: YouTube: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Video: “[Lecture
    2](http://www.youtube.com/watch?feature=player_embedded&v=F908k-sUtQk)”
    (YouTube)  
      
     Instructions: Please watch from the 4-minute mark to the 30-minute
    mark, and from the 37-minute mark to the end.  This video gives you
    a glimpse into lexical analysis, which will be studied in more depth
    in the remaining sections of this unit.  
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpages above.

**4.2 Requirements for a Scanner** <span id="4.2"></span> 
-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Handout 3 and Lecture 1: “Lexical Analysis”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Handout
    3 and Lecture 1: “[Lexical
    Analysis](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF)  
        
     Instructions: Select the PDF for Handout 3 and read the Basics on
    pages 1–2.  Also, study the lecture, slides 1 – 12.  This reading
    also applies to section 4.3.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**4.3 Functions of a Scanner** <span id="4.3"></span> 
*Note: The reading in 4.2 also applies to this subunit.  Pages 1 and 2
of the notes includescanner functions.  Also, study lecture slides 13 –
46.*

**4.4 Review of Regular Expressions, FSAs, and Regular Languages** <span
id="4.4"></span> 
-   **Reading: Torben Ægidius Mogensen’s Basics of Compiler Design:
    “Chapter 2: Lexical Analysis”**
    Link: Torben Ægidius Mogensen’s *Basics of Compiler Design*:
    “[Chapter 2: Lexical
    Analysis](http://www.diku.dk/hjemmesider/ansatte/torbenm/Basics/)”
    (PDF)  
        
     Instructions: Select the link and click “Get the book contents” to
    download a PDF version of the book.  Please look over Chapter 2 on
    Lexical Analysis.  If you are comfortable with this material just
    review it.  If you feel you are somewhat uncomfortable with this
    material, read or study it to become comfortable with it; it is the
    foundation for much of our work on compilers.  This reading applies
    to subsections 4.4.1 – 4.4.4.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**4.4.1 Regular Expressions to NFAs** <span id="4.4.1"></span> 
*Note: The reading of 4.4 applies to this subsection.  A regular
expression has associated non-deterministic finite automata (NFA) that
accept it. *

**4.4.2 NFAs to DFAs** <span id="4.4.2"></span> 
*Note: The reading of 4.4 applies to this subsection.  An NFA can be
converted to a DFA, which is a finite automaton where the state
transition is determined by the input symbol and the current state. *

**4.4.3 Space and Speed Optimization of DFAs** <span id="4.4.3"></span> 
*Note: The reading of 4.4 applies to this subsection.  The recognition
of a regular expression in a regular language can be done in several
ways: by operating on the expression directly, using an NFA, or using a
DFA.  Also, an automaton can be transformed to an equivalent having
fewer states.  The size (that is, the number of states) and the speed of
the automaton determine the most efficient way to recognize a regular
expression.  Note in section 2.7 of the reading the time estimates for
processing an expression by a DFA and by an NFA.*

**4.4.4 Power of Regular Languages** <span id="4.4.4"></span> 
*Note: The reading of 4.4 applies to this subsection also.  Regular
languages include many languages and can be used for many applications,
including scanners.  Further, given regular languages, their union,
concatenation, repetition, set difference, and intersection are also
regular languages—we say that regular languages are closed under these
operations.  Regular languages can be expressed, equivalently, using
regular expressions, NFAs, or DFAs.  A key limiting characteristic of
regular languages is seen from DFAs.  A DFA is a finite automaton, and,
thus, can remember only a finite number of symbols.  Hence, a DFA cannot
recognize a string of the type a<sup>n</sup> b c<sup>n</sup>, for any n
(because for any n it will require an infinite number of states to
remember the number of a’s).  Most computer languages are not regular
and we will need to use a larger formal language class to parse them.*

**4.5 Design of a Scanner** <span id="4.5"></span> 
-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Handout 3 and Lecture 1: “Lexical Analysis”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Handout
    3 and Lecture 1: “[Lexical
    Analysis](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF)  
        
     Instructions: Select the PDF for Handout 3 and read from page 3 to
    the end, including Scanner Implementation 1 and 2, and the FORTRAN I
    Case Study.  Also, study the lecture, slides 46–216.   
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**4.6 Construction of a Scanner** <span id="4.6"></span> 
-   **Reading: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Notes for Lecture 2 “Lexical
    Analysis, Regular Expressions”**
    Link: University of California, Berkeley: Paul Hilfinger’s CS164
    Programming and Compilers: Notes for Lecture 2 “[Lexical Analysis,
    Regular
    Expressions](http://inst.eecs.berkeley.edu/~cs164/sp11/lectures/)”
    (PDF)  
      
     Instructions: Select the PDF link for lecture notes \#2, Lexical
    Analysis and Regular Expressions.  Study all of its slides.  
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Web Media: YouTube: University of California, Berkeley: Paul
    Hilfinger’s CS164 Programming and Compilers: Video Lecture: “Lecture
    2”**
    Link: YouTube: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Video Lecture: “[Lecture
    2](http://www.youtube.com/watch?v=F908k-sUtQk&feature=relmfu)”
    (YouTube)  
      
     Instructions: Select the video link and watch Lecture 2.  
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Handout 4 and Lecture 2: “Introduction to FLEX”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Handout
    4 and Lecture 2: “[Introduction to
    FLEX](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF)  
        
     Instructions: Select the PDF for Handout 4 and study the notes. 
    Also, select the PDF for Lecture 2 and study the Introduction to
    FLEX slides.  FLEX is a scanner generator.  It produces a scanner,
    given a description of the patterns to be identified and actions to
    take for each token.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Reading: Torben Ægidius Mogensen’s Basics of Compiler Design:
    “Chapter 2: Lexical Analysis”**
    Link: Torben Ægidius Mogensen’s *Basics of Compiler Design*:
    “[Chapter 2: Lexical
    Analysis](http://www.diku.dk/hjemmesider/ansatte/torbenm/Basics/)”
    (PDF)  
        
     Instructions: Select the link and click “Get the book contents” to
    download a PDF version of the book.  Please read section 2.9.1. 
    Scanners are usually not written anew, but are generated by tools
    called scanner (or parser) generators.   
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

-   **Reading: Stanford University: Keith Schwarz’s CS143 Compilers:
    Handout 4 “FLEX in a Nutshell” and Lecture 2: “Introduction to
    FLEX”**
    Link: Stanford University: Keith Schwarz’s CS143 Compilers: Handout
    4 “[FLEX in a
    Nutshell](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF) and
    Lecture 2: “[Introduction to
    FLEX](http://www.keithschwarz.com/cs143/WWW/sum2011/)” (PDF)  
        
     Instructions: Select the PDF for Handout 4 and also Lecture 2 and
    read about FLEX.  
        
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpages above.

-   **Reading: University of California, Berkeley: Paul Hilfinger’s
    CS164 Programming and Compilers: Readings Lecture 2 “Flex Manual”**
    Link: University of California, Berkeley: Paul Hilfinger’s CS164
    Programming and Compilers: Readings Lecture 2 “[Flex
    Manual](http://inst.eecs.berkeley.edu/~cs164/sp11/lectures/)”
    (PDF)  
      
     Instructions: Select the PDF link for the reading for the “Flex
    Manual,” which contains details on the Flex scanner generator.  
      
     Terms of Use: Please respect the copyright and terms of use
    displayed on the webpage above.

**4.7 Verification and Validation of a Scanner** <span id="4.7"></span> 
*Note: Scanners for production compilers or software systems must be
verified (by proof, demonstration, review, or test, that shows that the
requirements, design, and performance specifications are met) and
validated (also by proof, demonstration, review, or test that shows that
the scanner satisfies the needs of its users and its role in a larger
containing system—either compiler or system application).  The amount of
effort expended in verifying and validating a scanner is dependent on
the purpose and intended use of the scanner.  For both verification and
validation, the description of the input language must be shown to be
correct.  If the scanner is generated, then the quality of the scanner
depends on the reliability and effectiveness of the generator.  *

-   **Assessment: ePaperPress: Tom Niemann's Tutorial on LEX and YACC**
    Link: ePaperPress: Tom Niemann's [Tutorial on Lex and
    Yacc](http://epaperpress.com/lexandyacc/) (PDF)  
        
     Instructions: Click on the link above to access the ePaperPress
    website.  Then, click on the hyperlink for the PDF format.  In this
    exercise, you will be introduced to LEX and YACC, which stand for
    Lexer (short for lexical analyzer) and Yet Another
    Compiler-Compiler.  They are generators, i.e. programs that generate
    other programs, in this case, a scanner and a parser.  Our focus in
    this Unit 4 Assessment will be on LEX, actually, FLEX – which stands
    for Fast Lexer.  Read the entire PDF tutorial on LEX; it provides a
    concise description of LEX and YACC.  Then, please follow these
    instructions for each exercise:  
                  
     **Exercise \#1: **Draw a high level block diagram depicting LEX and
    a C compiler, together with the input and output files for each of
    them.  
        
     **Exercise \#2: **Give the LEX input file for replacing 00 with the
    text 'error' in the language L of Exercise \#1 from Assessment 1.   
        
     **Exercise \#3 (optional): **For this exercise, we will be using
    several software tools: a generator for scanners (lexical
    analyzers), a C compiler, and text editor for creating input files. 
    We will use a scanner generator, called FLEX for creating scanners. 
    FLEX is based on the earlier, original LEX.  There are several good
    compilers available, cyngwin and gcc.  We will use gcc.  There are,
    also, several editors for creating input files; we'll use
    Notepad++.   
        
     a) Install FLEX on your computer.  Installation guidance is given
    below.  
     b) If you do not have a C compiler, install a C compiler on your
    computer.  Instructions for installing the gcc compiler can be found
    on YouTube linked
    [here](http://www.youtube.com/watch?v=w2XLvEcSrgo).  
     c) Check your answer to Exercise 2 by using FLEX and your C
    compiler to create a scanner; test the scanner by running it on a
    collection of sample input strings that are in the language of
    Exercise \#1 from Assessment 1.  Also, run it on some strings that
    are not in the language of Exercise \#1.  
        
     You can check your answers with The Saylor Foundation’s “[Answer
    Key](http://www.saylor.org/site/wp-content/uploads/2012/03/CS304-Unit-4-Answer-Key-to-Assignment-3-FINAL.pdf)”
    (PDF). This assessment should take approximately 3 hours to complete
    (not including installation of Flex and the Gcc compiler).  
        
     **Installation Notes for FLEX, Bison, and the Gcc (Gnu Compiler
    Collection) Compiler**  
        
     These notes give suggestions on the installation of FLEX, Bison
    (open source software for the original Lex and Yacc), and the gcc
    compiler.  
        
     To download and install FLEX (used for Exercise \#2 and Exercise
    \#3, and Bison used for Exercise \#3):  
      
     1) Use your search engine to find a free software version of Flex
    and Bison to download; for example, type in 'free software
    foundation fast lexical analyzer' or 'free software foundation
    software for Yacc;’ look over the results and select a copy of FLEX
    and Bison to investigate.  Be careful to avoid risky sites.  
     Look for a specific version of FLEX, for example, search for 'FLEX
    for Windows.'  
      
     OR  
        
     2) Go to the location [here](http://www.gnu.org/software/flex/) for
    Flex, [here](http://gnuwin32.sourceforge.net/packages/flex.htm) for
    a Windows version for Flex, and
    [here](http://gnuwin32.sourceforge.net/packages/bison.htm) for
    Bison.  
        
     3) After selecting a 'reliable' site, such as gnu.org, look for a
    version of FLEX for your operating system and follow the
    instructions for downloading and installing it, including
    documentation.  This should also give you Bison.  After downloading
    FLEX, if Bison is not included, repeat the steps 1), 2), 3) for
    Bison.   
        
     4) For a C compiler, you may already have one installed on your
    machine.  If not use your search engine to search for “cyngwin C
    compiler” or “gcc C compiler” and look for a free software version
    that you can download.  Be caution of risky web sites.  For the gcc
    compiler, for example, search for “codeblocks.org gcc compiler”.  
    Some of the results may refer to mingcc (minimal gcc compiler),
    which will work.  Installation of a compiler can be involved and the
    use of an installer is recommended.  A good tutorial on the
    installation of the gcc compiler can be viewed on
    [YouTube](http://www.youtube.com/watch?v=w2XLvEcSrgo).  
        
     Make sure that the version of FLEX or LEX, and Yacc and Bison, you
    obtain are compatible.  
      
     You can check your answers with The Saylor Foundation’s “[Answer
    Key](http://www.saylor.org/site/wp-content/uploads/2012/06/CS304-Unit-4-Answer-Key-to-Assessment-3-FINAL.pdf)”
    (PDF)  
        
     Terms of Use: Please respect the copyright and terms of use on the
    webpages displayed above.


