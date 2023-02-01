+++
title = "Guide and Best Practices for GDB"
authors = ["Giao Vu Dinh"]
date = "2023-02-01"
description = "This page provides a refresher and best practices for GDB."
tags = [
    "intro-lab",
    "gdb",
]
+++

Note: This is not meant to be a comprehensive tutorial on how to use gdb, but rather a refresher on what you might encounter while helping 217 students debug and common commands you might have to use. 

## Part 1: How do I run gdb?

Step 1: Make sure you build your program with -g. 

Example: _$ gcc217 -g test.c definitions.c -o testprgm_

Step 2: Run gdb within emacs. 
Launch emacs: _$ emacs_
Call gdb with these keystrokes: _<esc> x gdb <enter>_
The editor should display a message like this: 
    
_Run gud-gdb (like this): gdb —fullname_ followed by the name of an executable. If the executable is not your desired program (in this case testprgm), delete it and type the name of your program. Then hit <enter>. 

After these steps, emacs should display the (gdb) prompt. 

Step 3: Run your program
Issue the run command: (gdb) run
If your program requires command line arguments, add them to the run declaration. gdb should run the program to completion unless there is a runtime error in the program. 


## Part 2: How do I debug with gdb?

**Setting Breakpoints**
  
You can set breakpoints within the program at the beginning of functions. This causes the program to pause whenever it hits the breakpoint, and you can manually control when to move to the next breakpoint.

You can set a breakpoint using the break command: 
    
_(gdb) break main - this sets a breakpoint at the beginning of main()._

You can tell gdb to continue execution past the breakpoint using the continue command:
    
_(gdb) continue_

You can stop the execution of the program while paused at a breakpoint using kill:
    
_(gdb) kill_

You can remove a breakpoint using the clear command:
    
_(gdb) clear main_

**Stepping Through the Program**

Note: Make sure you set at least one breakpoint so the program doesn’t immediately execute everything and terminate when you run it. 

You can execute the next line of your program using the next command: 
    
_(gdb) next_
Note: next always stays at the same function call level. If the next line of your program calls another function, next will simply execute that line and then move to the next line in the original function. 

You can execute the next line of your program, stepping into a called function, using the step command:
    
_(gdb) step_

**Looking at Variables**

Let’s say you’re looking at the function helloWorld(), which takes an integer argument a, and have set a breakpoint at the beginning of the function. You can use the print command to examine the value of the parameter passed to this call of the function:
    
_(gdb) print a_

You can also use the print function to examine the value of any variable in your current scope.

You can print the current address of a variable using the print command and &. This is particularly helpful for assignments that use pointers such as SymTable.
    
_(gdb) print &i - prints address of variable i_

**Looking at the Stack**

You can display a call stack trace using the where command. This is particularly helpful for debugging a segfault. 
    
_(gdb) where_

**Quitting**

You can quit gdb using the following commands:

_(gdb) quit
<ctrl-x> <ctrl-c>_


 ## Other Resources
If you would like a more detailed tutorial to reference, here is a link to the gdb tutorial provided by COS 217 (taken from Fall 22 semester): https://www.cs.princeton.edu/courses/archive/fall22/cos217/precepts/05multifilegdb/gdb.pdf 
