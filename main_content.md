## Basic Syntax
```cpp
#include <iostream> // This includes the input/output library
using namespace std; // This line tells the compiler to use the standard namespace

int main() {
    int num1 = 5; // First number
    int num2 = 3; // Second number
    int sum = num1 + num2; // Add the numbers together
    cout << "The sum is: " << sum << endl; // Print the result
    return 0; // Tells the computer the program ran successfully
}
```
Let's break down this line:
`
std::cout << "The sum is: " << sum << std::endl;
`
- `std::cout` - This is the C++ way of referring to the "standard output stream," which is typically your screen. Think of cout as "character output," a way to send text and numbers from your program to the screen.

- `<<` operator - This operator is used with std::cout to "insert" data into the output stream. It's like saying, "take what's on my right and send it to the output." You can chain multiple << operators together to output different things in sequence.

- `"The sum is: "` - This is a string of text (a sequence of characters) that will be displayed exactly as it is. In this case, it provides a simple message to the user about what the number following it represents.

- `sum` - This is a variable that stores the result of adding two numbers (num1 and num2). When used with std::cout, the actual value stored in sum is displayed. So, if num1 was 5 and num2 was 3, sum would be 8, and that's the number shown on the screen.

- `std::endl` - This part represents the "end line" in the output stream, which moves the cursor to the next line of the console or terminal. It's like hitting 
"Enter" after typing a line, ensuring that anything printed next appears on a new line. It also flushes the output buffer, which means it makes sure that all output is immediately displayed on the screen.

## if-else statement
```cpp
#include <iostream>
using namespace std;

int main() {
    int number = -5; // Let's say we have a number

    if (number > 0) {
        cout << "The number is positive." << endl;
    } else {
        cout << "The number is negative." << endl;
    }

    return 0;
}
```
In this example, the if statement checks whether number is greater than 0. If true, it prints that the number is positive. If not (else), it prints that the number is negative.

```cpp
if (condition1) {
    // Code to execute if condition1 is true
} else if (condition2) {
    // Code to execute if condition1 is false but condition2 is true
} else if (condition3) {
    // Code to execute if both condition1 and condition2 are false but condition3 is true
} else {
    // Code to execute if none of the above conditions are true
}
```
 In C++, else if statements are used when you have multiple conditions to check sequentially. After an initial if statement, you can use one or more else if blocks to test other conditions. If none of the conditions are met, an optional else block can be executed as the default case.

## Loops
```cpp
#include <iostream>
using namespace std;

int main() {
    for (int i = 0; i < 5; i++) {
        cout << "This is a loop iteration." << endl;
    }

    return 0;
}
```
Here, the for loop starts with i at 0 and repeats the print statement until i is equal to 4 (for a total of 5 times). Each time through the loop, i is increased by 1 (i++).

```cpp
for (initialization; condition; increment/decrement) {
    // Block of code to be executed
}
```
The while loop repeats a block of code as long as a specified condition is true. It's useful when the number of iterations is not known before the loop starts.

```cpp
while (condition) {
    // Block of code to be executed
}
```

```cpp
int i = 0;
while (i < 5) {
    cout << i << " ";
    i++;
}
```
The do-while loop is similar to the while loop, but it tests the condition after executing the loop's body. This means the loop's body will always be executed at least once.

```cpp
do {
    // Block of code to be executed
} while (condition);
```
```cpp
int i = 0;
do {
    cout << i << " ";
    i++;
} while (i < 5);
```
- Use a for loop when the number of iterations is known.
- Use a while loop when the number of iterations is not known, and you want to repeat based on a condition being true.
- Use a do-while loop when the block of code needs to run at least once, but then may repeat based on a condition.



## functions
```cpp
#include <iostream>
using namespace std;

// Function declaration
int addNumbers(int a, int b) {
    return a + b; // Return the sum of a and b
}

int main() {
    int result = addNumbers(5, 3); // Call the function with 5 and 3 as arguments
    cout << "The result is: " << result << endl; // Print the result

    return 0;
}
```
In this example, addNumbers is a function that takes two integers as input and returns their sum. We then call this function in main, store the result in result, and print it

```cpp
#include <iostream>
using namespace std;

// Function declaration
void greet() {
    cout << "Hello, welcome to C++ functions!" << endl;
}

int main() {
    greet(); // Function call
    return 0;
}
```

In this example, greet is a function that does not take any parameters and does not return any value (void return type). It simply prints a greeting message when called.

```cpp
void greet(string name) {
    cout << "Hello, " << name << "! Welcome to C++ functions!" << endl;
}
//To call this function, you would pass the name as an argument:
greet("Alice");

```


## Basic input and output

```cpp
int age;
cout << "Enter your age: ";
cin >> age; // Takes input from the user and stores it in the age variable
```
- Output: As seen before, cout is used for output.
- Input: To get input from the user, we use cin followed by the >> operator and the variable name.

```cpp
#include <iostream>
#include <string> // Include the string library to use the string type

using namespace std;

int main() {
    string name; // Declare a string variable to store the user's name

    cout << "Enter your name: ";
    getline(cin, name); // Use getline to read a line of text into the name variable

    cout << "Hello, " + name + "! Welcome to C++ programming." << endl;

    return 0;
}
```

```cpp
#include <iostream>
#include <string> // Include the string library

using namespace std;

int main() {
    string firstName; // Variable to store the first name
    string lastName;  // Variable to store the last name

    cout << "Enter your first name: ";
    getline(cin, firstName); // Reads the first name

    // Ignore any characters left in the input buffer, up to and including the first newline
    cin.ignore(numeric_limits<streamsize>::max(), '\n');

    cout << "Enter your last name: ";
    getline(cin, lastName); // Reads the last name

    cout << "Hello, " << firstName << " " << lastName << "!" << endl;

    return 0;
}\
```

In this example, cin.ignore(numeric_limits<streamsize>::max(), '\n') is used to clear the input buffer, ensuring that any leftover characters, especially the newline character from the first input, do not interfere with the second getline() call. numeric_limits<streamsize>::max() specifies the maximum number of characters to ignore, and '\n' specifies that it should stop ignoring if it encounters a newline character.

## Comments in C++

```cpp
// This is a single-line comment

/*
This is a multi-line comment
that spans multiple lines.
*/
```

## Arrays

```cpp
#include <iostream>
using namespace std;

int main() {
    int myArray[5]; // Declares an array of 5 integers
    return 0;
}
```
You can initialize an array at the time of declaration:
```cpp
int myArray[5] = {1, 2, 3, 4, 5}; // Initialization
```
You access each element of the array using its index. Array indices start from 0.
```cpp
cout << myArray[0]; // Accesses the first element
```
To go through each element of the array, you can use a loop:
```cpp
for(int i = 0; i < 5; i++) {
    cout << myArray[i] << " ";
}
```

## Struct

A struct (or structure) is a way to group variables of different types under a single name.
```cpp
struct Person {
    string name;
    int age;
};

Person person1;
person1.name = "Alice";
person1.age = 30;
```
Structs are particularly useful for grouping data together when you start working with more complex programs that require a way to manage different types of data as a single unit.

- Efficiency: Arrays provide a way to store and access a sequence of data efficiently, especially when you know the size of the collection in advance.
- Organization: Structs help in organizing data into meaningful groups, making your code more readable and manageable.

```cpp
#include <iostream>
#include <string>
using namespace std;

// Step 1: Define the Struct
struct Person {
    string name;
    int age;
};

int main() {
    // Step 2: Declare an Array of Structs
    Person people[3]; // Array to hold 3 persons

    // Step 3: Initialize the Array
    // Manually initializing each element of the array
    people[0] = {"Alice", 30};
    people[1] = {"Bob", 25};
    people[2] = {"Charlie", 35};

    // Step 4: Iterate Through the Array
    for(int i = 0; i < 3; i++) {
        // Accessing and printing each person's name and age
        cout << people[i].name << " is " << people[i].age << " years old." << endl;
    }

    return 0;
}
```

In this code:

- A struct named Person is defined with name and age as its fields.
- An array named people of type Person is declared to hold 3 Person structs.
- The array is initialized with 3 Person objects, each representing a person with a name and age.
- A loop iterates through the people array, accessing and printing the name and age of each Person.

