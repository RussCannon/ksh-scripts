# ksh-scripts
<b>A collection of Korn Shell scripts.</b>

This is a collection of scripts that I have written professionally that offer instruction and insight into the use of Korn Shell as a programming language.  They are programs, fuctions, and routines written for Korn Shell 93 though many use the enhanced capabilities of the later versions of KSH.  Most of them will definitely not work with KSH88.  I typically use the most recent stable version of Korn Shell which is, at this time, AJM 93u+ 2012-08-01.

They have been developed mostly under HP-UX though I also code on Linux.  Most of my work is in support of my role as an Oracle database administrator, and these scripts will tend reflect that.  But, they employ methods that are easily generalizable.

<b>Folders</b>

Folders contain the following:

- Functions - Scripts that are intended to be used as callable subroutines through the function path variable FPATH.  This folder contains scripts that are callable by scripts or from the command-line.  Each script has a file name that matches the function name within the script.  There is one function per script.

<b>Coding Standards and Style</b>

Here are my coding standards:

- Use one space per level indentation.
- Use [[ ]] and (( )) instead of [  ] in conditionals.
- Use (( )) for all math operations.
- Never use 'let'.
- Use $( ) instead of backticks for subshell calls.
- Always have a single exit point either at the bottom of a script or in an _exit routine.
- Only use Posix functions where explicitly necessary.
- Always use uppercase for variable names except for indexers.
- Prefer ${VAR} to $VAR.
- Always break up code into subroutines in long scripts.
- Feed subshells with here documents for small amounts of data.
- Tab indent here documents.
- Use 'print' and NOT 'echo'.
- Design function scripts to contain one function each with the same file name as the function.
- Don't code for portability unless it is a requirement for the project.

Note:  This just explains my rules of coding and should not be construed as advocacy for a particular style.  This is just how I do things, and I try to be fairly consistent in so doing.  These preferences are driven by what I consider to be good programming methodology as well as implementing the best practices of the language in its most recent incarnation.

<b>Korn Shell Repository</b>

The Korn Shell source code can be obtained from the following GitHub repository:

https://github.com/att/ast

This was created by Lefteris Koutsofios following the takedown of the official AT&T Software Technology (AST) website by the company due to "security concerns".  There are no binaries, but the entire <i>ast-open</i> suite is provided and can be downloaded and built following the instructions provided.  Korn Shell is a component of the suite.  My practice is to perform a 'bin/package make' of the suite and then copy the results for my platform (in arch/\<architecture\> under PACKAGEROOT) to /opt/ast.  The shebangs in my scripts reflect this practice.
