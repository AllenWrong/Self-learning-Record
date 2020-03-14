## Installing Directly on Linux
**NOTE: We highly recommend using the VirtualBox VM.**

However, there was enough demand that we are providing these instructions for people who want to run directly on their own installation of Linux. These instructions were tested with Ubuntu 11.10, but should work on similar (Debian-based) systems, and can be adapted for other distros.

Steps:

- Install packages (If you only intend to use the C++ version, you don't need the jdk). For Ubuntu:
sudo apt-get install flex bison build-essential csh openjdk-6-jdk libxaw7-dev

- Make the /usr/class directory:
sudo mkdir /usr/class
- Make the directory owned by you:
sudo chown $USER /usr/class
- Go to /usr/class and download the tarball:
cd /usr/class
wget https://s3-us-west-1.amazonaws.com/prod-edx/Compilers/Misc/student-dist.tar.gz
- Untar:
tar -xf student-dist.tar.gz

If you want things exactly like the VM:

- Add a symlink to your home directory:
ln -s /usr/class/cs143/cool ~/cool
- Add the bin directory to your $PATH environment variable. If you are using bash, add to your .profile (or .bash_profile, etc. depending on your configuration; note that in Ubuntu have to log out and back in for this to take effect):

PATH=/usr/class/cs143/cool/bin:$PATH

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
