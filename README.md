This repositories fork from [sigar](https://github.com/hyperic/sigar).

In this repo I merged most of sigar's PRs and currently use it only for myself.

# Doc

Visit the SIGAR Wiki for documentation, bugs, support, etc.:
https://sourceforge.net/projects/sigar/files/docs/

# Build

Environment：cmake/gcc/vs2015 + Perl 5.8 + JDK 1.8 + Ant 1.9.7.1

1) Install cmake and Perl5 and add it's executables to PATH. Make sure you use Strawberry perl and not the perl present in unix scripts we use.
   
   - [perl](https://www.perl.org/)
   - [strawberryperl](https://strawberryperl.com/)
2) Set ANT build environment : ANT_HOME and add ANT_HOME/bin to PATH.
   
   - [ant](https://ant.apache.org/)

Windows command prompt environment **(Choose one)** :

1) Open the Visual Studio command prompt from the start menu.**(Recommend)**
2) Manually set up the compilation environment
   
   Make sure to build in a new cmd environment if previously different architecture build was executed in the current cmd to reset the environment variable to default.
   
   **(Different vs versions have different file paths and file name)**

- Win32 : "C:\Program Files (x86)\Microsoft Visual Studio 9.0\VC\bin\vcvars32.bat"
  
  > Uncomment the commented statements in sigar_get_pointer() and sigar_set_pointer() @ sigar-1.6.4\bindings\java\src\jni\javasigar.c for Win32 build.
- Win64 : "C:\Program Files (x86)\Microsoft Visual Studio 9.0\VC\bin\amd64\vcvarsamd64.bat"

Go to sigar-1.6\bindings\java and run :

1. ant clean
2. ant

the final: sigar-amd64-winnt.dll will be in sigar-1.6.4\bindings\java\sigar-bin\lib

