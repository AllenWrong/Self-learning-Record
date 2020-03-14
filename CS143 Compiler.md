## Other Project Resources
A list of other resources that you might find helpful:

- **C++ and UNIX:**<br/>
  - Thomas Anderson's Quick Introduction to C++ may be useful if you know C but are not familiar with all of the C++ subset we use in the programming projects.
  - A more thorough guide to using the version of Gnu C++ installed on our Linux machines is here.
Quick guide to UNIX development tools (one of the many useful documents available in Nick Parlante's ever-growing CS library)

- **Help with the gdb debugger:**
  - GNU's online gdb users guide
  - Printable quick reference: gdbref.ps
  - A GDB article that Julie Zelenski wrote a few years ago for a programming journal: GDB breakpoint tricks

- **References on lex & yacc:**
Lex is the original lexical scanner developed by Lesk and Schmidt; Paxson's improved version is flex. Similarly, yacc is Johnson and Sethi's original parser; bison is the GNU-equivalent written by Corbett and Stallman. Both are designed to be upward-compatible with the original while adding extensions and improvements.
 - Original documentation by the authors of the tools themselves. These papers are quite readable and serve as an excellent introduction for familiarizing yourself with the tools.
  - Lesk and Schmidt on lex
  - Johnson on yacc
Man pages are available from command line, e.g., man lex. We've also put up browsable versions of the Solaris man pages for lex, flex, yacc, and bison.
GNU's online documentation (full manuals, long, but very complete)
flex
bison
The lex & yacc page from Combo.org.
An article from the Linux Journal singing the praises of lex & yacc.
References on JLex and Java_cup:
Manual for JLex, Java CUP.
JLex.
Java CUP.
Cool Trees (Start with class TreeNode).
References on MIPS & SPIM:
A PDF version of the SPIM Manual (appendix from Hennessy & Patterson's architecture book)
The SPIM home page (downloadable versions, more docs).

Just for fun:

- A list of funny error messages from the old MPW C compiler.
- A translator for Latin to Perl (and you thought there was no practical use for what you learned in 143!)

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

### Lexical Analysis and Finite Automata

- CPTT: Sections 3.1, 3.3, 3.4, 3.6, 3.7, 3.8
- EC: Chapter 2 through Section 2.5.1 except for 2.4.4
- MCI: Chapter 2

### Parsing
- CPTT: Sections 4.1-4.6, 4.8.1, 4.8.2
- EC: Sections 3.1-3.5
- MCI: Chapter 3

### Semantic Analysis and Types
- CPTT: Sections 5.1-5.3 6.3, 6.5
- EC: Sections 4.1-4.4
- MCI: Chapters 4 and 5

### Runtime Systems and Code Generation
- CPTT: Sections 6.2, 7.1-7.4, 8.1-8.3, 8.6
- EC: Chapter 5, Sections 7.1-7.2
- MCI: Chapters 6, 7, and 14

### Optimization
- CPTT: Sections 8.5, 8.7, 9.1-9.4
- EC: Sections 8.1-8.4, 8.6, 9.1-9.3
- MCI: Chapter 10

### Advanced Topics: Register Allocation, Garbage Collection
- CPTT: Sections 7.5-7.6, Section 8.8
- EC: Sections 13.1-13.2, 13.4,
- MCI: Chapters 11 and 13
