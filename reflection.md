Stack Mechanics

When I ran the recursive factorial function, I could clearly see the stack growing because each call printed "Entering factorial(n)" before making another recursive call. For example, factorial(5) called factorial(4), then factorial(3), and so on until the base case was reached. Once the base case returned a value, the messages showed the functions returning one by one, which demonstrated the stack shrinking as function calls were removed. The Fibonacci function showed a similar pattern, but it generated many more function calls because each call created two additional recursive calls. The depth-tracking output made it easier to visualize how recursion adds stack frames.

When I tested the stack overflow demonstration, the program continuously printed function calls and never reached a stopping point because there was no base case. Eventually, the program crashed due to stack overflow. This demonstrated what happens when recursive functions continue adding stack frames without ever returning.

Each time a function is called, a new stack frame is created. The stack frame stores the function's parameters, local variables, and the return address that tells the program where to continue execution after the function finishes. As more functions are called, additional stack frames are pushed onto the stack. When functions return, those stack frames are removed in reverse order. This assignment helped me understand that recursion works by repeatedly adding and removing stack frames.


Recursion Costs

For the same input value, Fibonacci used more stack space than factorial. The factorial function only makes one recursive call at each level, so the number of active stack frames grows in a predictable linear way. Fibonacci is different because most calls generate two more recursive calls. This creates a much larger recursive call tree and significantly increases the amount of work performed.

Python limits recursion depth to prevent programs from causing stack overflows. Without this limit, a recursive function with a missing or incorrect base case could continue creating stack frames until the program crashes. My stack overflow demonstration showed exactly why this protection is useful. By enforcing a recursion limit, Python reduces the risk of exhausting system memory and terminating unexpectedly.


Function Pointers and Callbacks

Function pointers enable callbacks by allowing a function to be passed as a parameter to another function. Instead of hardcoding a specific function call, a program can decide which function to execute at runtime. In the process_array example, the same function was able to apply different operations to an array depending on which callback was provided. This makes code more reusable and flexible.

One real-world example of callbacks is a graphical user interface. When a user clicks a button, the program executes a callback function associated with that button. The same event system can handle many different actions without changing the underlying code.

Systems programmers often use callbacks because they provide flexibility and modularity. Although function pointers can be harder to read than direct function calls, they allow programs to respond dynamically to events and support more generic, reusable designs.