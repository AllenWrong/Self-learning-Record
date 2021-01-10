#### <a href="https://github.com/AllenWrong/Self-learning-Record/blob/master/student-dist.tar.gz">Project Assignment</a>

## Error

**1.spim error**
```
  % coolc hello_world.cl 
  % spim hello_world.s
  /usr/class/cs143/cool/bin/spim: line 82: 
  /usr/class/cs143/cool/bin/../bin/.i686/spim: No such file or directory
```

The student_dist.tar.gz is missing the lib/.i686 directory. I solved this by copying the files from the VirtualBox image, but it still failed. I found that my 64-bit Linux (Ubuntu 17.10), did not have the 32-bit libc installed, so I fixed that with:

do the following action:
`sudo apt-get install libc6-i386`


## Syllabus

This online class will be available as soon as the course begins, but is organized around a weekly cycle.

If you follow the structure of the course, working through one section each week, you will receive a quiz every week.  It's advisable to complete the quiz within two weeks of beginning a section.  You will have the option to take each quiz multiple times and only your highest score will be used. There will be no quizzes the first week, the week of the midterm, or the week of the final.

The midterm and final will contain problems at a similar level of difficulty to that in the quizzes, but the exams will be longer. There will also be no retries on exams (you can take an exam only once).  

The compiler project consists of four programming assignments. This part of the course is optional; you can take the class without doing the project. In fact, if you start the project and later decide not to turn in all of the project assignments we will simply consider you to be taking the non-project version of the course. Students who complete the project will have that noted on their Statement of Accomplishment at the end of the course.

The first two project assignments are easier than the last two, so you may end up taking more time with the later assignments.  Each part of the project can be written independently of the other parts and for each assignment we will give you the reference implementation's other components to use for testing. Thus, even if one of the parts of your compiler does not work correctly you can still do the next assignment using the reference compiler's components.

The project can be done either in C++ or Java. If you really, really want to, you can in fact write the project in any language you like, but you will have to reimplement some basic functionality that we provide in C++ and Java. You will also need to ensure you adhere to the (undocumented) interfaces between the compiler passes. We don't recommend this option, but people have asked and if you are an experienced programmer who doesn't mind figuring things out on your own it is at least plausible that you could do this and enjoy it.

The weight for the various assignments in the course will be: 20% electronic quizzes, 15% midterm, 25% final, 40% programming assignments.

Finally, this course is self-paced. The self-paced course has exactly the same materials and you will learn the same things. The differences are that there is not necessarily going to be a cohort of other students to interact with; and there is no instructional staff support.

Below is a table with a recommended "schedule" to follow.  There are no deadlines, but we suggest completing a programming assignment no later than two weeks after you start it. 

Key: PA = Programming Assignment

<table border="0" cellpadding="2" cellspacing="0" width="100%">
<tbody>
<tr><th align="left" bgcolor="#333399" valign="top" width="10%"><span style="color: #000000; font-family: Arial;" color="white" face="Arial"><b>Week</b></span></th><th align="left" bgcolor="#333399" valign="top" width="25%"><span style="color: #000000; font-family: Arial;" color="white" face="Arial">Videos</span></th><th align="left" bgcolor="#333399" valign="top" width="15%"><span style="color: #000000; font-family: Arial;" color="white" face="Arial">Quiz / Exam</span></th><th align="left" bgcolor="#333399" valign="top" width="15%"><span style="color: #000000; font-family: Arial;" color="white" face="Arial">PA assigned</span></th><th align="left" bgcolor="#333399" valign="top" width="15%"><span style="color: #000000; font-family: Arial;" color="white" face="Arial">PA due</span></th></tr>
<tr>
<td>1</td>
<td>Course Overview<br>Cool: The Course Project</td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<td>2</td>
<td>Lexical Analysis<br>Finite Automata</td>
<td>Quiz #1</td>
<td>PA1</td>
<td></td>
</tr>
<tr>
<td>3</td>
<td>Parsing<br>Top-Down Parsing</td>
<td>Quiz #2</td>
<td></td>
<td></td>
</tr>
<tr>
<td>4</td>
<td>Bottom-Up Parsing I<br>Bottom-Up Parsing II</td>
<td>Quiz #3</td>
<td>PA2</td>
<td>PA1</td>
</tr>
<tr>
<td>5</td>
<td>Semantic Analysis and Type Checking</td>
<td>Midterm</td>
<td></td>
<td></td>
</tr>
<tr>
<td>6</td>
<td>Cool Type Checking<br>Runtime Organization</td>
<td>Quiz #4</td>
<td>PA3</td>
<td>PA2</td>
</tr>
<tr>
<td>7</td>
<td>Code Generation<br>Operational Semantics</td>
<td>Quiz #5</td>
<td></td>
<td></td>
</tr>
<tr>
<td>8</td>
<td>Local Optimization<br>Global Optimization</td>
<td>Quiz #6</td>
<td></td>
<td></td>
</tr>
<tr>
<td>9</td>
<td>Register Allocation<br>Garbage Collection</td>
<td></td>
<td>PA4</td>
<td>PA3</td>
</tr>
<tr>
<td>10</td>
<td>Java</td>
<td>Final Exam</td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

****

## Getting Started with the VM

If you wish to write a compiler for the course, you will need an
environment in which to do so. Due to the complexity of getting all the
needed tools installed correctly, we provide a pre-configured Linux
system via VirtualBox VM.

VirtualBox allows you to install the VM on your own computer. Instructions on setting up VirtualBox are available here.

Once the VM is set up, you can compile the example programs. Once the assignments become available, you will be able to work on these inside the VM as well.

To play around with the example cool programs, make a directory and copy over one or more examples from the /usr/class/cs143/examples directory. These examples are the same as the ones posted on the website. The coolc command will run the reference compiler to generate the assembly output (.s) file, which you can run using the spim simulator. For example, to compile and run "hello_world.cl", run in a terminal (where $ represents the prompt):

$ mkdir examples<br/>
$ cd examples<br/>
$ cp /usr/class/cs143/examples/hello_world.cl .<br/>
$ coolc hello_world.cl<br/>
$ spim hello_world.s<br/>
SPIM Version 6.5 of January 4, 2003<br/>
Copyright 1990-2003 by James R. Larus (larus@cs.wisc.edu).<br/>
All Rights Reserved.<br/>
See the file README for a full copyright notice.<br/>
Loaded: /usr/class/cs143/cool/lib/trap.handler<br/>
Hello, World.<br/>
COOL program successfully executed<br/>
Stats -- #instructions : 152<br/>
         #reads : 27  #writes 22  #branches 28  #other 75<br/>

****

## Other Project Resources
A list of other resources that you might find helpful:

- **C++ and UNIX:**<br/>
  - Thomas Anderson's Quick Introduction to C++ may be useful if you know C but are not familiar with all of the C++ subset we use in the programming projects.
  - A more thorough guide to using the version of Gnu C++ installed on our Linux machines is here.
Quick guide to <a href="http://cslibrary.stanford.edu/107">UNIX development tools</a> (one of the many useful documents available in Nick Parlante's ever-growing <a href="http://cslibrary.stanford.edu">CS library</a>)

- **Help with the gdb debugger:**<br/>
  - GNU's online <a href="http://sourceware.org/gdb/current/onlinedocs/gdb/">gdb users guide</a>
  - Printable quick reference: gdbref.ps
  - A GDB article that Julie Zelenski wrote a few years ago for a programming journal: <a target="[object Object]" href="http://web.stanford.edu/class/cs107/gdb_coredump1.pdf">GDB breakpoint tricks</a>

- **References on lex & yacc:**<br/>
Lex is the original lexical scanner developed by Lesk and Schmidt; Paxson's improved version is flex. Similarly, yacc is Johnson and Sethi's original parser; bison is the GNU-equivalent written by Corbett and Stallman. Both are designed to be upward-compatible with the original while adding extensions and improvements.
  - Original documentation by the authors of the tools themselves. These papers are quite readable and serve as an excellent introduction for familiarizing yourself with the tools.
    - <a href="http://dinosaur.compilertools.net/lex/index.html">Lesk and Schmidt on lex</a>
    - <a href="http://dinosaur.compilertools.net/#yacc">Johnson on yacc</a>
  - Man pages are available from command line, e.g., man lex. We've also put up browsable versions of the Solaris man pages for <a href="http://www.stanford.edu/class/archive/cs/cs143/cs143.1112/materials/other/manlex.html">lex</a>, <a href="http://www.stanford.edu/class/archive/cs/cs143/cs143.1112/materials/other/manflex.html">flex</a>, <a href="http://www.stanford.edu/class/archive/cs/cs143/cs143.1112/materials/other/manyacc.html">yacc</a>, and <a href="http://www.stanford.edu/class/archive/cs/cs143/cs143.1112/materials/other/manbison.html">bison</a>.
  - GNU's online documentation (full manuals, long, but very complete)
    - <a href="http://flex.sourceforge.net/manual/">flex</a>
    - <a target="[object Object]" href="http://www.gnu.org/software/bison/manual/bison.html">bison</a>
  - The <a href="http://www.combo.org/lex_yacc_page/">lex &amp; yacc page</a> page from Combo.org.
  - An <a href="http://www2.linuxjournal.com/lj-issues/issue51/2227.html">article</a> from the Linux Journal singing the praises of lex & yacc.
  
- **References on JLex and Java_cup:**<br/>
  - Manual for <a href="http://www.cs.princeton.edu/~appel/modern/java/JLex/current/manual.html">JLex</a>, <a href="http://www2.cs.tum.edu/projects/cup/manual.html">Java CUP</a>.
  - <a href="http://www.cs.princeton.edu/~appel/modern/java/JLex/">JLex</a>.
  - <a href="http://www.stanford.edu/class/archive/cs/cs143/cs143.1112/javadoc/java_cup/">Java CUP</a>.
  - <a href="http://www.stanford.edu/class/archive/cs/cs143/cs143.1112/javadoc/cool_ast/">Cool Trees</a> (Start with class TreeNode).

- **References on MIPS & SPIM:**<br/>
A PDF version of the <a href="http://www.stanford.edu/class/archive/cs/cs143/cs143.1112/materials/other/SPIM_Manual.pdf">SPIM Manual</a> (appendix from Hennessy & Patterson's architecture book)
The <a href="http://www.cs.wisc.edu/~larus/spim.html">SPIM home page</a> (downloadable versions, more docs).

Just for fun:

- A list of <a href="Http://www.netfunny.com/rhf/jokes/91q3/cerrors.html">funny error messages</a> from the old MPW C compiler.
- A translator for <a href="http://www.csse.monash.edu.au/~damian/papers/HTML/Perligata.html">Latin to Perl</a> (and you thought there was no practical use for what you learned in 143!)

****

## Installing Directly on Linux
**NOTE: We highly recommend using the VirtualBox VM.**

However, there was enough demand that we are providing these instructions for people who want to run directly on their own installation of Linux. These instructions were tested with Ubuntu 11.10, but should work on similar (Debian-based) systems, and can be adapted for other distros.

Steps:

- Install packages (If you only intend to use the C++ version, you don't need the jdk). For Ubuntu:<br/>
`sudo apt-get install flex bison build-essential csh openjdk-6-jdk libxaw7-dev`

- Make the /usr/class directory:<br/>
`sudo mkdir /usr/class`

- Make the directory owned by you:<br/>
`sudo chown $USER /usr/class`

- Go to /usr/class and download the tarball:<br/>
`cd /usr/class`
`wget https://s3-us-west-1.amazonaws.com/prod-edx/Compilers/Misc/student-dist.tar.gz`
- Untar:<br/>
`tar -xf student-dist.tar.gz`

If you want things exactly like the VM:

- Add a symlink to your home directory:<br/>
`ln -s /usr/class/cs143/cool ~/cool`

- Add the bin directory to your $PATH environment variable. If you are using bash, add to your .profile (or .bash_profile, etc. depending on your configuration; note that in Ubuntu have to log out and back in for this to take effect):<br/>
`PATH=/usr/class/cs143/cool/bin:$PATH`

****

## Readings
No textbook is required for the class, but if you would like to do some additional reading this page lists the relevant material from three popular texts:

- Compilers: Principles, Techniques, and Tools (CPTT, aka "The Dragon Book")
2nd edition
Aho, Lam, Sethi, and Ullman

- Engineering a Compiler (EC)
2nd edition
Cooper and Torczon

- Modern Compiler Implementation (MCI)
Appel, with Palsberg
Note: there are versions of this book tailored to C and Java, as well as ML.

#### Lexical Analysis and Finite Automata

- CPTT: Sections 3.1, 3.3, 3.4, 3.6, 3.7, 3.8
- EC: Chapter 2 through Section 2.5.1 except for 2.4.4
- MCI: Chapter 2

#### Parsing
- CPTT: Sections 4.1-4.6, 4.8.1, 4.8.2
- EC: Sections 3.1-3.5
- MCI: Chapter 3

#### Semantic Analysis and Types
- CPTT: Sections 5.1-5.3 6.3, 6.5
- EC: Sections 4.1-4.4
- MCI: Chapters 4 and 5

#### Runtime Systems and Code Generation
- CPTT: Sections 6.2, 7.1-7.4, 8.1-8.3, 8.6
- EC: Chapter 5, Sections 7.1-7.2
- MCI: Chapters 6, 7, and 14

#### Optimization
- CPTT: Sections 8.5, 8.7, 9.1-9.4
- EC: Sections 8.1-8.4, 8.6, 9.1-9.3
- MCI: Chapter 10

#### Advanced Topics: Register Allocation, Garbage Collection
- CPTT: Sections 7.5-7.6, Section 8.8
- EC: Sections 13.1-13.2, 13.4,
- MCI: Chapters 11 and 13
