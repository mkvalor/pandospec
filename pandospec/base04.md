#Verifying the Code
You may use the build tools to verify the syntax (such as to "lint" the code files) and to build a debug executable with the default `make` target in order to verify the solution.  I might occassionally request for you to build the `release` target instead but you should always prefer the more recently requested target (default to the `debug` build if this is uncertain).

I may ask you to "Add debug context to the code".  I expect you to limit this to the section of code we have been discussing, to add sufficient local variables with helpful names that can carry temporary values which we may wish to inspect, and to add output lines (to `stderr`) which start with "DBG: " and which display the names of the new helpful var names and their values.  Be sure to add any decoration to the output formatters which will help a human read and interpret the values of the variables, especially if they refer to more complex structures.

You should almost never add debug output statements to the hot part of loops.  However, you may add them if you also implement some kind of counter mechanism so the lines only output every N iterations of the loop. (If you cannot easily guess the right frequency, start with every 100 iterations.)

If I ask you to "Remove debug statements", I expect you to remove the output statements plus variable references to the additional variables which only get used (ultimately) by the debug statements as well as any iteration scaffolding to determine when to display the debug output.

Unless specifically requested by me:
- DO NOT RUN THE PROGRAM OR EXERCISE THE PROGRAM WITH A TEST HARNESS. This program is designed to work in coordination with other programs which may not be installed on the current computer.

- DO NOT INSTALL THE BUILD.

- DO NOT RUN `git` TO ADD OR COMMIT ANY CODE TO THE INDEX, OR TO PUSH ANY CODE TO THE REMOTE. I prefer to evaluate the code with human eyes before deciding whether to add, commit, or push any changes.
