# ksh-scripts
A collection of Korn Shell scripts.

This is a collection of scripts that I have written professionally that offer instruction and insight into the use of Korn Shell as a programming language.  They are programs, fuctions, and routines written for Korn Shell 93 though many use the enhanced capabilities of the later versions of KSH.  Most of them will definitely not work with KSH88.  I typically use the most recent stable version of Korn Shell which, at this time is AJM 93u+ 2012-08-01.

They have been developed mostly under HP-UX though I also code on Linux.  Most of my work is in support of my role as an Oracle database administrator, and these scripts may relect that.  But, they employ methods that are easily generalizable.

Here are my coding standards:

- Use [[ ]] and (( )) instead of [  ] in conditionals.
- Use (( )) for all math operations.
- Never use 'let'.
- Use $( ) instead of "` `" for subshell calls.
- Always have a single exit point either at the bottom of a script or in an _exit routine.
- Only use Posix functions where explicitly necessary.
- Always use uppercase for variable names except for indexers.
- Prefer ${VAR} to $VAR.
- Always break up code into subroutines in long scripts.
- Feed subshells with here documents for small amounts of data.
- Don't code for portability unless it is a requirement for the project.
