# ksh-scripts
<b>A collection of Korn Shell scripts.</b>

This is a collection of scripts that I have written professionally that offer instruction and insight into the use of Korn Shell as a programming language.  They are programs, fuctions, and routines written for Korn Shell 93 though many use the enhanced capabilities of the later versions of KSH.  Most of them will definitely not work with KSH88.  I typically use the most recent stable version of Korn Shell which is, at this time, AJM 93u+ 2012-08-01.

They have been developed mostly under HP-UX though I also code on Linux.  Most of my work is in support of my role as an Oracle database administrator, and these scripts will tend reflect that.  But, they employ methods that are easily generalizable.

<b>Folders</b>

Folders contain the following:

- Functions - Scripts that are intended to be used as callable subroutines through the function path variable FPATH.  This folder contains scripts that are callable by scripts or from the command-line.  Each script has a file name that matches the function name within the script.  There is one function per script.
- Tutorials - Small programs and routines that demonstrate some capability of Korn Shell or describe solutions that I have found for various programming challenges I have faced.

<b>Coding Standards and Style</b>

Here are my coding standards:

- Use one space per level indentation.
- Use [[ ]] and (( )) instead of [  ] in conditionals.
- Use (( )) for all math operations instead of 'let'.
- Use $( ) instead of backticks for subshell calls.
- Always have a single exit point either at the bottom of a script or in an _exit routine.
- For large programs, always exit with a return code.
- Only use Posix functions where explicitly necessary.
- Always use uppercase for variable names except for indexers.
- Prefer ${VAR} to $VAR.
- Always break up code into subroutines in long scripts.
- Feed subshells with here documents for small amounts of data.
- Tab-indent here documents.
- Use 'print' and NOT 'echo'.
- Use 'getopts' to process program and function arguments.
- Use 'getopts' to create man pages for scripts.
- Don't code for portability unless it is a requirement for the project.

Note:  This just explains my rules of coding and should not be construed as advocacy for a particular style.  This is just how I do things, and I try to be fairly consistent in so doing.  These preferences are driven by what I consider to be good programming methodology as well as implementing the best practices of the language in its most recent incarnation.

<b>So, why NOT code for portability?</b>

Several years ago, the software our organization maintains underwent a major recoding from a COBOL-based system to Java-based with an Oracle database backend&mdash;actually numerous Oracle databases.  The developers, who were consultants with the Oracle Corporation, insisted on design decisions that emphasized portability even though that was never a requirement of the system they were building.  To this day, we are hamstrung by many of those misguided decisions.  A great many flaws in our system can be traced back to that decision, but the design is now a lump of granite that cannot be affordably altered.  The presumed need for portability is still nowhere on the horizon, and those programmers are long gone.  But, we are stuck with those inane design choices that seriously impact the performance of the system and make it much more difficult to do simple things like patching the Oracle software.  We were left with a very fragile design.

This experience taught me a lesson.  DO NOT DESIGN TO REQUIREMENTS THAT DO NOT EXIST!  This is not to say that portability is never a desirable goal, but it needs to be an explicitly-stated requirement of the system.  Requirements-based design is crucial to the success of any system.  In our case, design decisions based on a non-requirement has damaged the system's ability to satisfy basic, explicitly-stated requirements.  We never needed, for example, the software to be backend agnostic, but the Oracle employees that wrote the new system imagined it as a possible future requirement and, consequently, put the software's business logic entirely within the mid-tier Java code.  In so doing, they duplicated functionality in Java that could be handled automatically and more effienctly WITHOUT CODE by the Oracle database itself&mdash;and it would have been a lot less buggy.

As a UNIX System Administrator and an Oracle Database Administrator, I endeavor to employ the full power of the languages and software that I use.  Coding for portability requires compromises that often leave the best features of a language out of play. Now, if that is a requirement, then so be it.  But, if it is NOT a requirement, then there is no need to act as if it was.  There is no degree of portability imaginable for our system that would, for example, require us to NOT develop with the full potential of Korn Shell in its very latest capabilities.  Korn Shell is, itself, portable to virtually any UNIX flavor and version.  Windows database servers are not even on the table in our case, but the latest version of Korn Shell has even been ported to that by AST's UWIN project.  There will never be a requirment for our KSH code to be translated into BASH or, God forbid, PowerShell.  When we finally do transition to Linux in the not-to-distant future, Korn Shell will be there.

In this repository, I am going to demonstrate the most powerful features of Korn Shell including Object Oriented script design, and I am not going to bother with how they might have to be recoded for other shells.  If you are stuck with another shell&mdash;or even an older version of Korn Shell&mdash;then this repository might not be for you.  But, it you want to delve into the true power of Korn Shell, then stick around.

<b>The Korn Shell Repository</b>

The Korn Shell source code can be obtained from the following GitHub repository:

https://github.com/att/ast

This was created by Lefteris Koutsofios following the takedown of the official AT&T Software Technology (AST) website by the company due to "security concerns".  There are no binaries, but the entire <i>ast-open</i> suite is provided and can be downloaded and built following the instructions provided.  Korn Shell is a component of the suite.  My practice is to perform a 'bin/package make' of the suite and then copy the results for my platform (in arch/\<architecture\> under PACKAGEROOT) to /opt/ast.
