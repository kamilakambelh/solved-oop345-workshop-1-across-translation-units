Download Link: https://assignmentchef.com/product/solved-oop345-workshop-1-across-translation-units
<br>
In this workshop, you implement aspects of linkage, storage duration, namespaces, guards, and operating system interfaces.

## Learning Outcomes

Upon successful completion of this workshop, you will have demonstrated the abilities to:– declare a local variable that remains in memory for the lifetime of the program– guard a class definition from repetition– access a variable defined in a different translation unit– receive program arguments from the command line– upgrade code to accept and manage a user-defined string of any length

## *In-Lab*

This workshop consists of three modules:– `w1` (partially supplied)– `process` (supplied)– `String`

Enclose all your source code within the `sdds` namespace and include the necessary guards in each header file.

### `w1` Module (partially supplied)

Finish the implementation of the `main` function, by completing the parts marked with `TODO`:

– write the prototype of the `main` function to receive a set of standard command line arguments– echoes the set of arguments to standard output in the following format:“`1: first argument2: second argument3: third argument4: …“`

**Do not modify this module in any other place!**

### `process` Module

The process module is supplied and you do not need to change its header or implementation files. The implementation file defines a single function named `process()` that receives the address of an unmodifiable C-style null terminated string, constructs a `String` object from the C-style string and inserts that object into standard output followed by a newline.

### `String` Module

Your `String` module defines a class named `String` that holds a C-style null-terminated string of up to 3 characters *excluding the null byte terminator*. The class includes the following member and helper functions:

– a one-argument constructor that receives the address of an unmodifiable C-style null-terminated string and copies the string at that address into an instance variable. Check for receipt of the null address and store an empty string in that case.

– a query named `display()` that receives a reference to an `std::ostream` object and inserts the string stored in the instance variable.

– a **free helper** insertion operator that inserts the saved string into the left operand.  This operator should count how many times it has been called (by incrementing a counter), and prints this value to the screen as shown below.  **Do not use global variables to store the counter!**“`COUNTER: STRING“`

Do not use the `string` class of the standard library in this workshop.  Use only `cstring` functions where necessary.

In the namespace `sdds`, this module should contain a *global variable* named `g_maxSize` of type `unsigned int` (an integer that has non-negative values). Initialize it with `3`. Declare the variable in the header and define it in the implementation file.

### Sample Output

When the program is started with the command:“`w1.exe Welcome to C++!“`the output should look like:“`Command Line:1: w1.exe2: Welcome3: to4: C++!

——————Global variable:——————Old Value: 3New Value: 4——————

——————Processing:——————1: Wel2: to3: C++——————“`

### Submission (30%)

To test and demonstrate execution of your program use the same data as shown in the output example above.

Upload your source code to your `matrix` account. Compile and run your code using the latest version of the `g++` compiler (available at `/usr/local/gcc/9.1.0/bin/g++`) and make sure that everything works properly.

Then, run the following command from your account (replace `profname.proflastname` with your professor’s Seneca userid):“`~profname.proflastname/submit 345XXX_w1_lab“`and follow the instructions. Replace XXX with the section letter(s) specified by your instructor.

**:warning:Important:** Please note that a successful submission does not guarantee full credit for this workshop. If the professor is not satisfied with your implementation, your professor may ask you to resubmit. Resubmissions will attract a penalty.

## *At-Home*

For this part of the workshop, upgrade your `String` class to manage a C-style null-terminated string of any length.  When a new instance is created, the custom constructor should accept at most `g_maxSize` characters (excluding the null terminator).  No other modules need to be changed.

### Sample Output

When the program is started with the command:“`w1.exe Welcome to C++!“`the output should look like:“`Command Line:1: w1.exe2: Welcome3: to4: C++!

——————Global variable:——————Old Value: 3New Value: 4——————

——————First processing:——————1: Welc2: to3: C++!——————

——————Second processing:——————4: Welco5: to6: C++!——————

WelcomeWelcomeSchool of Software Design and Data Science7: Welcome8: Welcome9: Welcome“`