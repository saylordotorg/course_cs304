Course Syllabus for "CS304: Compilers"
--------------------------------------

Because we have compiler programs, software developers often take the
process of compilation for granted.  However, as a software developer,
you should cultivate a solid understanding of how compilers work in
order to develop the strongest code possible and fully understand its
underlying language.  In addition, the compilation process comprises
techniques that are applicable to the development of many software
applications.  As such, this course will introduce you to the
compilation process, present foundational topics on formal languages and
outline each of the essential compiler steps: scanning, parsing,
translation and semantic analysis, code generation, and optimization. 
By the end of the class, you will have a strong understanding of what it
means to compile a program, what happens in the process of translating a
higher-level language into a lower-level language, and the applicability
of the steps of the compilation process to other applications.

### Learning Outcomes

Upon successful completion of this course, the student will be able
to:  
  

-   <span dir="LTR">Describe the compilation process and explain the
    function of the components that comprise the structure of a
    compiler.</span>
-   <span dir="LTR">Apply concepts of formal languages and finite-state
    machines to the translation of computer languages.</span>
-   <span dir="LTR">Identify the compiler techniques, methods, and tools
    that are applicable to other software applications.</span>
-   <span dir="LTR">Describe the challenges and state-of-the-practice of
    compiler theory and practice.</span>

### Course Requirements

In order to take this course, you must:  
  
 <span dir="LTR"><span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 24px; text-align: left; -webkit-text-size-adjust: none; ">√
   </span>Have access to a computer.</span>  
  
 <span dir="LTR"><span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 24px; text-align: left; -webkit-text-size-adjust: none; ">√
   </span>Have continuous broadband Internet access.</span>  
  
 <span dir="LTR"><span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 24px; text-align: left; -webkit-text-size-adjust: none; ">√
   </span>Have the ability/permission to install plug-ins or software
(e.g., Adobe Reader or Flash).</span>  
  
 <span dir="LTR"><span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 24px; text-align: left; -webkit-text-size-adjust: none; ">√
   </span>Have the ability to download and save files and documents to a
computer.</span>  
  
 <span dir="LTR"><span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 24px; text-align: left; -webkit-text-size-adjust: none; ">√
   </span>Have the ability to open Microsoft files and documents (.doc,
.ppt, .xls, etc.).</span>  
  
 <span dir="LTR"><span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 24px; text-align: left; -webkit-text-size-adjust: none; ">√
   </span>Have competency in the English language.</span>  

<span dir="LTR"><span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 24px; text-align: left; -webkit-text-size-adjust: none; ">√   
</span></span>Have read the [Saylor Student
Handbook.](http://www.saylor.org/site/wp-content/uploads/2012/05/Saylor-StudentHandbook.pdf)

<span dir="LTR"><span
style="color: rgb(85, 85, 85); font-family: 'Myriad Pro', 'Gill Sans', 'Gill Sans MT', Calibri, sans-serif; font-size: 16px; line-height: 24px; text-align: left; -webkit-text-size-adjust: none; ">√
   </span>Have a basic mastery of the material in </span>CS101, CS102,
CS201, CS202, and CS303.

### Course Information

Welcome to CS304.  Below, please find some general information on the
course and its requirements.

**Course Designer: **JM Perry

**Primary Resources:**

*Note: The MIT, Stanford, and Berkeley resources overlap.  However, they
reinforce each other, have differences in presentation, examples, and
topic emphasis, and provide the opportunity to review the material. 
Moreover, they offer a choice of perspective and style, which some
students may find appealing.  There are several ways to use these
resources.  All students should use the Mogensen text.  Of the MIT,
Stanford, and Berkeley resources, a student may 1) choose the one whose
style is most appealing and stick with it, occasionally using the others
where they are beneficial, 2) use all three resources totally, or 3) for
each topic/subunit select the resource you find most helpful.  Lastly,
the Berkeley resource includes video lectures, which can be useful for
explaining certain points of a topic.  *

-   <span dir="LTR">Open courseware from MIT: </span>[6.035 Computer
    Language
    Engineering](http://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-035-computer-language-engineering-spring-2010/index.htm)
-   <span dir="LTR">Open courseware from Stanford University:
    </span>[CS143 Compilers](http://www.stanford.edu/class/cs143/)
-   <span dir="LTR">Open courseware from Berkeley: CS164 Programming
    Languages and Compilers </span>[Video
    Lectures](http://webcast.berkeley.edu/playlist#c,d,Computer_Science,03D59E2ECDDA66DF) and
    [Lecture
    Notes](http://inst.eecs.berkeley.edu/~cs164/sp11/lectures/).
-   <span dir="LTR">Torben Ægidius Mogensen’s</span> textbook, [Basics
    of Compiler
    Design](http://www.diku.dk/hjemmesider/ansatte/torbenm/Basics/basics_lulu2.pdf)
-   <span dir="LTR">Wikipedia </span>

**Requirements for Completion:** Passing grade on quizzes and the final
exam; achieve the objectives of each unit and the goals of the course;
ability to apply the concepts taught in the course.

**Time Requirements:** This course should take approximately
**146 hours** to complete.

**Tips/Suggestions:** As you study the topics in the course, keep in
mind the application of compiler techniques and tools to the development
of other types of software.


**Table of Contents:** You can find the course's units at the links below.

- [Unit 1](https://legacy.saylor.org/cs304/Unit01/)
- [Unit 2](https://legacy.saylor.org/cs304/Unit02/)
- [Unit 3](https://legacy.saylor.org/cs304/Unit03/)
- [Unit 4](https://legacy.saylor.org/cs304/Unit04/)
- [Unit 5](https://legacy.saylor.org/cs304/Unit05/)
- [Unit 6](https://legacy.saylor.org/cs304/Unit06/)
- [Unit 7](https://legacy.saylor.org/cs304/Unit07/)
- [Unit 8](https://legacy.saylor.org/cs304/Unit08/)
- [Unit 9](https://legacy.saylor.org/cs304/Unit09/)
- [Unit 10](https://legacy.saylor.org/cs304/Unit10/)
- [Unit 11](https://legacy.saylor.org/cs304/Unit11/)
- [Final Exam](http://saylordotorg.github.io/LegacyExams/CS/CS304/CS304-FinalExam.html), [Answers](http://saylordotorg.github.io/LegacyExams/CS/CS304/CS304-FinalExam-Answers.html)
