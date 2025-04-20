## Procedure Activation


## Give runtime storage managemenr for calls and return statements

In compiler design, **runtime storage management** is a crucial part of implementing procedure or function calls and handling return statements. The compiler, along with the runtime system, must organize memory effectively to store data such as parameters, return addresses, local variables, and intermediate values. This is primarily achieved through a **runtime memory layout**, which includes areas like the **code segment**, **data segment**, **heap**, and most importantly, the **stack**.

For managing function calls and returns, the **stack segment** plays a central role. When a function is called, a new block of memory known as an **activation record** or **stack frame** is created and pushed onto the stack. This record stores critical information required for the function to execute and eventually return. It typically contains the return address (so control can go back after the function ends), parameters passed to the function, space for local variables, and administrative data like the dynamic link (pointing to the caller's frame) and access link (used in languages with nested procedures for referencing non-local variables).

The **stack pointer (SP)** keeps track of the top of the stack, while the **frame pointer (FP)** helps reference fixed locations within the current activation record. These pointers are adjusted as the function executes and cleaned up when the function returns. If the function is recursive, each call generates a new activation record with its own state, allowing multiple independent calls to coexist.

On encountering a **return statement**, the runtime system performs cleanup: it may move the return value into a designated register or memory location, reset the stack and frame pointers, and then use the saved return address to transfer control back to the caller. The stack frame is then popped, effectively deallocating the function’s runtime storage.

In addition to the stack, the **heap segment** is used for dynamic memory allocation, such as allocating memory during execution using constructs like `new` or `malloc`. While heap memory is managed manually or by garbage collectors (in high-level languages), stack memory is automatically managed by the call and return mechanisms.

Thus, runtime storage management for calls and returns ensures correct handling of procedure execution contexts, supports recursion, enables scope-based memory allocation, and contributes to overall program correctness and efficiency. It is a foundational part of the compiler's backend and runtime system design.

## Calculate IN and OUT of flow graph


```cardlink
url: https://www.youtube.com/watch?v=sMoFyTGRtWI
title: "How to Compute Data Flow In and Out Equations from the given Graph"
description: "It is the entire description of how you can calculate In and Out values from the given Graph by generating Gen and Kill values and by the Iterations"
host: www.youtube.com
favicon: https://www.youtube.com/s/desktop/c722ba88/img/logos/favicon_32x32.png
image: https://i.ytimg.com/vi/sMoFyTGRtWI/hqdefault.jpg
```

```cardlink
url: https://www.youtube.com/watch?v=QOTaceVUsmQ
title: "LP IN OUT Calculation"
description: "Compiler Design  Numerical"
host: www.youtube.com
favicon: https://www.youtube.com/s/desktop/c722ba88/img/logos/favicon_32x32.png
image: https://i.ytimg.com/vi/QOTaceVUsmQ/maxresdefault.jpg
```

## Non-Imperative Langaugaes
**Non-imperative programming languages**, also known as **declarative languages**, focus on **what** the program should accomplish rather than **how** to accomplish it. Unlike imperative languages, which rely on a sequence of statements that change the program’s state, non-imperative languages emphasize **expressing logic and relationships** without explicitly stating control flow. One of the key characteristics of non-imperative languages is the absence of **explicit loops and conditional statements**; instead, computations are described through **expressions, rules, or logical assertions**. These languages are often **side-effect free**, meaning functions or expressions do not alter any state or variables outside their scope, leading to more predictable and maintainable code.

Another major feature is **referential transparency**, where the value of an expression depends only on its inputs and not on any hidden state or mutable data. This allows for easier reasoning, debugging, and optimizations such as memoization. Non-imperative languages also support **higher-level abstraction**, enabling developers to write concise and readable code. There are different types of non-imperative languages including **functional languages** (e.g., Haskell, Lisp), where computation is treated as the evaluation of mathematical functions, and **logic programming languages** (e.g., Prolog), where problems are solved by specifying rules and facts, and the system infers solutions through automated reasoning.

Additionally, many non-imperative languages support **lazy evaluation**, where expressions are not evaluated until their results are required, leading to potential performance benefits. These languages are also **well-suited for parallel and concurrent programming**, as their stateless nature avoids many issues related to shared memory and synchronization. Overall, non-imperative languages offer a powerful alternative to imperative styles, promoting a more abstract, mathematical, and often more elegant approach to problem-solving.

## Code improving transformations
**Code improving transformations** are a set of techniques used during the optimization phase of a compiler to enhance the performance and efficiency of the compiled code without changing its functionality. These transformations operate on the intermediate representation (IR) of the code and aim to make the generated machine code run faster, use less memory, and consume fewer resources. The goal is to produce high-quality object code that performs better on the target hardware architecture. Code improving transformations are vital in modern compilers, especially for performance-critical applications such as operating systems, real-time systems, mobile apps, and embedded systems.

One of the most basic but widely used transformations is **constant folding**. In this technique, constant expressions in the code are evaluated at compile time instead of at runtime. For example, an expression like `4 + 6` would be replaced with `10` during compilation. This reduces the number of operations that need to be performed during program execution, thereby saving CPU time. Another related optimization is **constant propagation**, where the values of known constants are substituted throughout the program to simplify expressions and potentially expose other opportunities for optimization.

Another significant transformation is **dead code elimination**, which removes instructions or blocks of code that have no effect on the program output. Examples of dead code include variables that are assigned values but never used, or conditional branches that are never taken. Removing such unnecessary code not only reduces the size of the executable but also improves execution speed by avoiding superfluous computations. Similarly, **common subexpression elimination (CSE)** identifies duplicate expressions computed multiple times and replaces them with a single computation stored in a temporary variable. This prevents redundant calculations and improves efficiency.

**Loop optimizations** are among the most powerful code improving transformations because loops are frequently executed and thus have a big impact on performance. **Loop unrolling** is a technique where the loop body is replicated multiple times to reduce the number of iterations and the overhead of loop control statements. For instance, a loop that runs 10 times could be unrolled to execute two iterations per loop, effectively reducing loop control operations by half. Another useful technique is **loop invariant code motion**, where computations that yield the same result on every iteration are moved outside the loop, ensuring they are only computed once rather than repeatedly.

**Strength reduction** is another effective transformation where expensive operations such as multiplication and division are replaced with cheaper alternatives like addition and bit shifting. For example, multiplication by a power of 2 can be replaced with a left shift operation, which is much faster. Similarly, **function inlining** replaces a function call with the actual body of the function, eliminating the overhead of the call and allowing further optimizations within the inlined code. However, excessive inlining can increase code size, so it must be applied carefully.

In conclusion, code improving transformations play a crucial role in making compiled programs more efficient and effective. These techniques are foundational to compiler design and directly impact the performance and responsiveness of software applications. By applying transformations like constant folding, dead code elimination, loop optimization, strength reduction, and function inlining, compilers can produce high-quality machine code that runs faster and more efficiently. These improvements are particularly important in systems with limited resources and where performance is critical, making code optimization an essential aspect of software development.