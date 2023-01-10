# <i class="fas fa-hand-sparkles fa-fw"></i> Lecture 2: Java Refresher with Hello World!

>Adapted from https://cse12x.github.io/java-tutorial/index.html

 This lecture will be a crash course in the syntax of the Java programming language. **This tutorial assumes that you already know how to program** and need a refresher in Java specifically. So for example, we won't completely explain programming concepts such as loops from scratch, but will teach you all of the details of the syntax for loops in Java.

## Other Resources
* [Learn X in Y minutes (where X=Java)](https://learnxinyminutes.com/docs/java/)

## Hello World!

As is tradition when learning a new programming language, you often see the simplest program you could write that prints "Hello World!" to the screen. We will start by just showing the syntax and then we will explain the components. Reminder, you can click on the other programming language to see how the same program would be written in those languages.


```java
// Contents of HelloWorld.java

public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```

That is a fair amount of text you have to write just to get the computer to say hello! One of the drawbacks of Java is it can be a bit verbose at times, but it something you get used to! Most of this code is what we might call "boiler plate" code, or code that you just have to write because the language requires it but doesn't really do anything important. We'll start by explaining the simplest part, the print statement, and then will explain the rest.

* `System.out.println("Hello World!");` is the actual line that causes the computer to print. In Java, we interact with the `System.out` object when we want to print text. `System.out.println` is a method that we are calling passing `"Hello World!"` as a parameter. Note that the Java statements such as a print statement end in a semicolon (`;`) to indicate the end of the line of Java.
* Everything outside of that line is generic starter code that most Java programs need.
    * **Class definition**
      ```java
      public class HelloWorld {
          ...
      }
      ```

      Every Java file needs to contain a `class` that you put code inside. We will talk more about classes in another chapter, so all you need to know know is you will need to write `public class X { ... }` (where `...` is the rest of your code) for each new Java file you write. Importantly, the name of the class has to match the name of the file. So we named the class `HelloWorld` because it is in a file called `HelloWorld.java`.
    * **Main method**
      ```java
      public static void main(String[] args) {
         ...
      }
      ```
      Any runnable program will need a main method with this exact definition. We will talk about the details of this text more in the section on Methods, so for now you will just need to memorize these components and write them down.

      ```{admonition} Tip
        It's okay to copy and paste this line from file to file as you learn it, but we recommend practicing writing it out so you can memorize the parts*.
      ```
    * In Java, we use curly brackets (`{` and `}`) to indicate how lines of code belong inside a structure. Every opening curly bracket (`{`) should have a corresponding closing curly bracket (`}`) to close the structure. Note that the class definition and the main method definition both open a curly bracket to put stuff inside, so we need two closing curly brackets to close each one.
    * In Java, we use `//` to write single-line comments.

So to recap the whole program, we have

```java
// Contents of HelloWorld.java

public class HelloWorld {                   // Class definition (matches file name)
  public static void main(String[] args) {  // Main method definition (always same)
    System.out.println("Hello World!");     // Actual code to print (needs ; at end)
  }                                         // Closing curly bracket for main method
}                                           // Closing curly bracket for class
```

# <i class="fas fa-book fa-fw"></i> Printing and Comments

## Printing

We already saw in the introduction our first "Hello World!" program that prints out to the console.

```java
// Contents of Printing.java

public class Printing {
    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```


In Java, we print by interacting with `System.out` which represents the output console (i.e., the screen). `println` is a method that stands for "print line". The `println` method prints a line of text based on the parameter you give it. You can print as many lines as you want by calling the method multiple times.

```java
public class Printing {
    public static void main(String[] args) {
        System.out.println("Hello World!");
        System.out.println("Hello Seattle!");
        System.out.println("Hello UW!");
    }
}
```

This will print the following output. Notice that each call to `println` corresponds to one line of output as `println` also prints a new-line character.

```text
Hello World!
Hello Seattle!
Hello UW!
```

### `print` vs. `println`

Sometimes, you want to have finer-grained control of how your printing is formatted, so Java provides an alternate method called `System.out.print`. `print` operates just like `println` but does **not** include a new-line at the end. So the same program as above but using `print` instead  of `println` would yield the following output.


```java
public class Printing {
    public static void main(String[] args) {
        System.out.print("Hello World!");
        System.out.print("Hello Seattle!");
        System.out.print("Hello UW!");
    }
}
```


```text
Hello World!Hello Seattle!Hello UW!
```

Notice that there are no spaces after each thing printed, since `print` doesn't include any trailing characters. If you would want the program to have spaces between calls of `print`, you must write the spaces yourself in the text you are printing.

```java
public class Printing {
    public static void main(String[] args) {
        System.out.print("Hello World! ");   // Note the space in the string!
        System.out.print("Hello Seattle! ");
        System.out.print("Hello UW!");
    }
}
```

### Mixing `print` and `println`

It is completely possible to mix-up your use of both `print` and `println` to format your output how you want! This will make more sense when we get to the chapter on looping or conditionals, but for example you could write a program like the following. Note that each call to `print` prints the text exactly while each call to `println` prints the text and then moves to the next line.

```java
public class Printing {
    public static void main(String[] args) {
        System.out.print("A");
        System.out.print("A");
        System.out.println("A");
        System.out.print("B");
        System.out.println("B");
        System.out.println("C");
    }
}
```


```text
AAA
BB
C
```

## Comments

Comments are useful to provide documentation and leave notes to yourself or other programmers who are working on your code with you. There are two main ways to write comments in Java (where `...` is some text):
* Single-line comments with `// ...`
* Multi-line comments with `/* ... */`

Here is an example program that uses comments

```java
public class Comments {
    public static void main(String[] args) {
        // This is a single-line comment
        System.out.println("First");
        /*
        This is
        a comment
        that spans multiple
        lines
        */
        System.out.println("Second");
    }
}
```

You write comments on any line of a program, even above a method or a method definition. It is very common to provide documentation for your class and your methods by leaving a comment above those methods. You normally don't need to comment your `main` method though.

```java
// This is a comment explaining what this class does
public class Example {
    // This is a comment explaining this method
    public static void main(String[] args) {
        // These comments are for you and your coworkers to explain complicated code
        System.out.println("Hello!");
    }
}
```

# <i class="fas fa-book fa-fw"></i> Variables, Types, Expressions

## Variables
Every variable and Java must be declared with a **type** to indicate which type of data will be stored in that variable. For example, the following program makes a variable called `x` and another variable called `y` and prints them out. Note that you have to specify when declaring the variable `x` that it will store an integer number (`int`).

```java
public class Variables {
    public static void main(String[] args) {
        int x = 4;
        int y = 6;
        System.out.println(x);
        System.out.println(y);
    }
}
```

```text
4
5
```

Note that you only have to specify the type of the variable when you first **declare** the variable. In other lines of code when you are using the variable, you just use the variable name (i.e., `System.out.println(x)`).

## Assignment
Variables in Java operate like most other languages such that you can update their values with an assignment statement. The following program makes a variable `x`, prints it out and then updates the value before printing it again. Note that as we said above, we don't need to specify the type in the assignment statement, only the initial declaration.

```java
public class Assignment {
    public static void main(String[] args) {
        int x = 4;
        System.out.println(x);
        x = 7;
        System.out.println(x);
    }
}
```

## Types
Since you have to be explicit in Java about types, it's important to know some of the fundamental data types that you can use in your programs. The following list shows the most common data types used in Java.

* `int` typed variables store integer numbers such as `5`.
* `double` typed variables store real numbers such a `4.5`.
* `boolean` typed variables store `true` or `false`.
* `char` typed variables store a single character such as `'a'`.
* `String` typed variables store a sequence of characters such as `"Hello"`

Note that `String` starts with a capital letter! This is because it is an "Object type" rather than a "primitive type". We won't cover this distinction in this section, but just note that `String`s can do more than simpler data types such as an `int` can. Also note that you surround a `char` value with single-quotes (`'`) and `String`s with double-quotes (`"`).

```java
public class Types {
    public static void main(String[] args) {
        int a = 5;
        double b = 4.5;
        boolean c = true;
        char d = 'a';
        String e = "Hello";
    }
}
```

Once a variable has a defined type, you cannot change the type of that variable. Java is also very strict when it comes to types. By saying `x` is of type `int`, you can only store integers in that variable. For example, the following code would cause a type error.

```java
public class Types {
    public static void main(String[] args) {
        int a = 5;
        a = 4.5;  // Error! Incompatible types
    }
}
```

## Expressions

Java provides operators to combine values in a particular way for computation. All of the usual operators such as addition (`+`), subtraction (`-`), multiplication (`*`) and division (`/`) are present.

```java
public class Expressions {
    public static void main(String[] args) {
        int x = 5;
        int y = 3;
        double z = 4.5;
        System.out.println(x + z - x / y);
    }
}
```

The output of this code is 8.5, which you may or may not have expected! One thing to note is that division between integers uses a special rule for **integer division**. When `x` is 5 and `y` is 3, `x / y` evaluates to 1 since 3 only goes into 5 one time evenly! You have to pay particular attention to when you are doing division to make sure if integer division is appropriate or not. If you do division involving a `double`, then "normal division" will be used.

Related to the concept of integer division is computing the remainder of a division operation. Java provides the **modulo operator** or **mod** to compute the remainder from integer division with the symbol `%`. Using the numbers from above, the expression `x % y` would equal 2 since the remainder of dividing 5 by 3 is 2.

Java has no operator for exponentiation (e.g., $3^2$). Instead, you have to use the `Math` module to do powers.

```java
public class Expressions {
    public static void main(String[] args) {
        int x = 3;
        int y = Math.pow(x, 2);
    }
}
```

## Casting

You are able to convert between types by **casting**. Casting is the process of converting one type to another. Note that there are special rules for what values can or can't be cast from one type to another that we will not discuss completely. The most important casting scenarios involve:

* Converting an `int` to a `double`
* Converting a `double` to an `int`

The following program shows the syntax to cast from these two types. For example, `(double) a` is an expression that interprets the value stored in `a` as a double. Note that it doesn't actually change the value stored in `a`, just returns the `double` version of whatever value is currently inside `a`.

```java
public class Casting {
    public static void main(String[] args) {
        int a = 5;
        double b = 3.5;
        double c = (double) a;
        int d = (int) b;
        System.out.println(c);  // Prints 5.0
        System.out.println(d);  // Prints 3
    }
}
```

Note that converting from `double` to `int` *loses precision* in that the things after the decimal are lost.

# <i class="fas fa-book fa-fw"></i> If/Else Statements

```{admonition} Info
In the following section, we will not include the class definition or main method to focus on the syntax at hand.
```

## Comparisons
Very commonly, we use `boolean`s when comparing two numbers. Java provides operators to compare two numbers with the following syntax.

```java
int x = 4;
int y = 5;
System.out.println(x == y);  // Equal
System.out.println(x != y);  // Not equal
System.out.println(x < y);   // Less than
System.out.println(x <= y);  // Less than or equal to
System.out.println(x > y);   // Greater than
System.out.println(x >= y);  // Greater than or equal to
```

## Boolean Operators

Booleans represent true or false values. You can combine boolean values using the logical operators:
* `a && b` for "and". This evaluates to true if and only if both `a` and `b` are true, otherwise it is false.
* `a || b` for "or". This evaluates to true if any of `a` or `b` are true. It is only false if both `a` and `b` are false.
* `!a` for "not". This "negates" the value such that is `false` if `a` was `true`, otherwise it is `true` if `a` was false.

The following code shows how to use these operators.

```java
boolean b1 = true;
boolean b2 = false;
boolean b3 = b1 && b2;
boolean b4 = b3 || !b2;
boolean b5 = b3 == b4;
```


* `b1` is `true`
* `b2` is `false`
* `b3` is `false` because `b1 && b2` evaluates to `false (at least one argument is `false`).
* `b4` is `true`. To evaluate `b3 || !b2` we first evaluate `!b2` to get `true`, and then `b3 || true` is `true`
* `b5` is `false` because `b3` is `false` and `b4` is `true`, which means they are not equal.

## Conditionals

Conditional statements or if/else statements in Java behave similarly to other languages. Important things to note about conditionals in Java are:

* `if` and `else if` statements require parentheses around their conditions.
* Java uses curly brackets (`{}`) to denote the opening and closing of an if/ese statement's body. Anything inside the curly brackets of a if/else statement only run if the condition for that block is met.
* Proper indentation is not a requirement of the Java language, but it is **strongly recommended** that you use proper indentation to show what lines of code belong inside/outside the body of an if statement.

```java
int n = 4;
if (n % 3 == 0) {
    System.out.println("Case 0");
} else if (n % 3 == 1 || n % 2 == 0) {
    System.out.println("Case 1");
} else {
    System.out.println("Case 2");
}
System.out.println("After if/else");
```

The output of this block is

```text
Case 1
After if/else
```

# <i class="fas fa-book fa-fw"></i> Loops

## While Loops

Just like most languages, Java has a notion of a `while` loop that runs multiple times while some condition is true. The syntax is similar to most other languages, with the normal Java requirements that we saw from if statements to have parentheses around the conditions and using curly brackets to indicate the start/stop of the loop body.

```java
int n = 1;
while (n < 100) {
    System.out.println(n);
    n = 2 * n;
}

System.out.println("After loop");
```

The semantics of the `while` loop are consistent across most languages: it repeatedly evaluates the condition and each time, if the condition is true, runs the body of the loop and stops once the condition is evaluated to false.

## For Loop
While the syntax for while loops is fairly consistent across languages, `for` loops generally have quite different syntax across languages. We will first show the syntax to print the numbers between 0 and 10 in Java, and then will explain all of parts of the syntax.

```java
for (int i = 0; i < 11; i = i + 1) {
    System.out.println(i);
}
```

The for loop in Java is fairly complex in that you have to specify a lot of things! The general format of the for loop in Java is the following:

```java
for (initialization; condition; update) {
    body;
}
```

So from the example above, the `for` loop runs the following steps (in order)
1. `initialization`: `int i = 0` this sets up a loop variable called `i` to start at 0
2. `condition`: `i < 11` this is the condition in which the for loop will continue to run. Think of this like the while loop condition.
3. `body`: `System.out.println(i)` is the body of the loop that will run once for each iteration of the loop.
4. `update`: `i = i + 1` is run to update the loop variable.
5. Repeat steps 2, 3, and 4 until the condition becomes false when we check step 3, in which case the loop stops.

### Short Update Syntax

It is quite tedious to write out `i = i + 1` every time you write a for loop, so Java provides two shorthand syntaxes to do the same thing. The following are essentially equivalent for almost all programming tasks.

* `i = i + 1;`
* `i += 1;`
* `i++;`

Similarly, there are operators for subtracting by 1 with

* `i = i - 1;`
* `i -= 1;`
* `i--;`

So this means we would write the loop above as:

```java
for (int i = 0; i < 11; i++) {
    System.out.println(i);
}
```

## Scope
An important notion in Java is the concept of a variable's **scope**. A variable is only defined in a certain part of the program, and we call this part of the program the variable's scope. In Java, scope is fairly simple in that a variable is only defined after its declaration until the next set of a closing curly bracket. The following code snippet demonstrates the concept of the variable `n` by showing where it is valid to reference it and where you can't. In the context of programming, we call trying to use a variable that is not defined in your current scope using something "out of scope".

```java
System.out.println(n);  // Out of scope: Not defined yet
for (int i = 0; i < 10; i++) {
    System.out.println(n); // Out of scope: Not defined yet
    int n = 2 * i;  // n is now defined and its scope is the for loop body
    System.out.println(n);  // n is in scope
}
System.out.println(n);  // Out of scope: No longer defined
```

Note how the variable `n` is only defined after its declaration but only until the body of the for loop continues. Outside of the loop, `n` can no longer be referenced since it is out of scope.

One variable to not in particular is the loop variable `i` in the example above. `i`'s scope is limited to the for loop body and the for loop "header" (the initialization, condition, and update). This means you can refer to `i` in any of those parts, but not outside the loop.

# <i class="fas fa-book fa-fw"></i> Strings

We have briefly mentioned the concept of a `String` in Java. A `String` is a sequence of characters, which we denote surrounded by double-quotes (e.g., `"Hello World!"`).

## String Concatenation

You can make variables of type `String` and you can even use `+` to combine `String`s together with **string concatenation**.

```java
String greeting = "Hello";
String location = "Seattle";
String result = greeting + " " + location + "!";
System.out.println(result);

// Output:
// Hello Seattle!
```

In Java, you can also concatenate `String`s with other data types, and they will be converted to `String`s!

```java
String s1 = "a";
String s2 = s1 + 4;
System.out.println(s2);  // a4
```

## String Methods

Earlier, we mentioned that `String` is a bit special compared to other data types, indicated by having an upper-case name compared to the primitive data types such as `int`. This is because `String` is an example of a special "object type" that carries more complex functionalities. For example, you can ask `String`s to perform more complicated operation by calling **method**s on them. The following code snippet shows many of the most common methods useful for `String`s. You can learn about more of the methods [here](https://docs.oracle.com/en/java/javase/11/docs/api/java.base/java/lang/String.html).

```java
String s1 = "Hello";

String s2 = s1.toUpperCase();  // "HELLO"
String s3 = s1.toLowerCase();  // "hello"

String s4 = s1.substring(1, 4);  // "ell"
String s5 = s1.substring(2);     // "llo"

char c = s1.charAt(1);    // 'e'
int i = s1.indexOf('l');  // 2
```

One thing to note, in particular, is that operations on `String`s **don't change the original `String`, but return a new one**. All of these method calls above are returning *new* `String`s and the original one is still stored in `s1`, unchanged.


# <i class="fas fa-book fa-fw"></i> Methods

Methods allow you to define reusable bundles of code that can help reduce redundancy and organize your code for readability. The concept of methods, or also called functions in other languages, are the same in Java but the syntax looks a little bit different.

Like before, we will start by showing the syntax and then will explain the components.

```java
public class Example {
    public static void main(String[] args) {
        System.out.println("The main method starts");
        String message = greetings(4, "Seattle");
        System.out.println(message);
        System.out.println("The main method ends");
    }

    public static String greetings(int times, String greetingTo) {
        System.out.println("Greetings starts");
        for (int i = 0; i < times; i++) {
            System.out.println("Hello " + greetingTo + "!");
        }
        System.out.println("Greetings ends");
        return "Greeted " + times + " times";
    }
}
```

This code has the output:

```text
The main method starts
Greetings starts
Hello Seattle!
Hello Seattle!
Hello Seattle!
Hello Seattle!
Greetings ends
Greeted 4 times
The main method ends
```

In general, the syntax for defining a method in Java is the following:

```java
public static ReturnType methodName(ParameterType1 parameterName1,
                                    ParameterType2 parameterType2, ...) {
    code;
    code;
    code;
    return value;
}
```

Note that we generally will define methods starting with `public static` as part of the Java syntax. Like with control structures such as while loops, we use curly brackets to indicate what lines of code belong inside the method.

The scoping rules that Java uses apply here. This means variables defined inside methods will only be available in that method. This is what we can use **return**s to return a single value from a method to the method that called it. If a method does not need to return a value it doesn't need to, but then the return type should be declared a special value `void` such as

```java
public static void method() {
```


Now that we have seen the general syntax, we can now see that the `main` method shown earlier is just that, a method. Java just requires this method
has this particular method name and parameter so it can call it to run the program.


To call a method in Java, you use parentheses after the method name and passing an parameters inside the parens.

```text
ReturnType variableName = methodName(value1, value2);
```

# <i class="fas fa-book fa-fw"></i> Files and I/O


Very commonly, we store data in files that we want to read from in our programs. For example, things like Google Docs are backed by some files somewhere on Google's computers.

For simplicity, we will only focus on *text files* which store only text data such as the file `poem.txt`.

```text
she sells
sea
shells by
the sea shore
```

## Reading From a File

To read from a file in Java, we use a `Scanner` object that controls how to read the file. A `Scanner` keeps track of where we are in the file and how to read the next parts bit by bit. The following code snippet shows how to to create a Scanner and read the file each "token" at a time. A *token* is a series of characters separated by whitespace. It is the same idea as the concept of a "word", but more general since there are many non-words that are stored in computer files such as numbers.

```java
public class FileReading {
    public static void main(String[] args) throws FileNotFoundException {
        Scanner fileInput = new Scanner(new File("poem.txt"));

        while (fileInput.hasNext()) {
            String token = fileInput.next();
            System.out.println(token);
        }
    }
}
```

This code yield the following output.

```text
she
sells
sea
shells
by
the
sea
shore
```

The `Scanner` object keeps track of which position we are in the file. The `hasNext()` method returns `true` if there are any remaining tokens, and the `next()` method will return the next token. In other words, this code is repeatedly asking for one token from the file at a time, until there are no more tokens.

To construct a `Scanner` we use the syntax to attach a `Scanner` to a particular file. Note that Java requires us to now change the `main` method declaration to include the statement `throws FileNotFoundException` because the file may not exist. You do not need to understand the `throws` keyword, outside you need to include this text when you are reading from files.

```java
Scanner fileInput = new Scanner(new File("poem.txt"));
```

## Line and Token Based Processing

Very commonly, we might need more granularity when it comes to how we want to read files. For example, consider the problem of counting the number of tokens that appear on each round. So for example, for our `poem.txt` above we might want to print out something like the following to count the number of words per line.

```text
1: 2
2: 1
3: 2
4: 3
```

The following code snippet shows how to do this in Java. Note that instead of calling the `next()` and `hasNext()` method, we are calling the `nextLine()` and `hasNextLine()`. These methods behave similarly, but instead of returning a single token returns the whole line of text. We then can actually use another `Scanner` made from this line to read just that line token by token! This is a common pattern for mixing line-based processing and token-based processing.

```java
public class FileReading {
    public static void main(String[] args) throws FileNotFoundException {
        Scanner fileInput = new Scanner(new File("poem.txt"));

        int lineNum = 1;
        // Loop over every line of the file
        while (fileInput.hasNextLine()) {
            String line = fileInput.nextLine();

            // Make a new Scanner attached to just this line of text
            Scanner lineInput = new Scanner(line);

            // Loop over every token in this line
            int tokenCount = 0;
            while (lineInput.hasNext()) {
                lineInput.next();
                tokenCount++;
            }

            System.out.println(lineNum + ": " + tokenCount);

            // Update the line number for the next iteration
            lineNum++;
        }
    }
}
```

The beauty of a `Scanner` is it hides all of the logic of figuring out what source of data it is attached to, how to fetch the next thing or tell if there is more data present. All we need to do as programmers is make a new `Scanner` instance and call the methods we want!

## User Input

Often, we also want to be able to interact with the user and ask them for input by having them type into the keyboard. It turns out that the `Scanner` was designed for this purpose to since user input is just another data source! We can make a new `Scanner` instance, but instead of attaching it to a file or a `String`, we can attach it to a special source for the user's keyboard called `System.in`. The following program asks the user for their name and age and prints a greeting. When we run this program, every time we call one of the `next` methods it will pause, and wait for the user to type in the requested info.

```java
public class UserInput {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.print("What is your name? ");
        String name = input.nextLine();

        System.out.print("What is your age? ");
        int age = input.nextInt();

        System.out.println("Welcome " + name + " (" + age + ")!");
    }
}
```

There are some things to note about this program:

* When constructing the `Scanner`, we say `new Scanner(System.in);` to attach it to the user's keyboard.
* We no longer need the `throws FileNotFoundException` in our `main` header since we are no longe reading from a file.
* To get the user's age, we called the method `nextInt()` instead of `next()`. It turns out that turning text data like the `String` `"16"` into a number is quite tricky. So instead, the `Scanner` provides other methods that do the conversion from text to the data type you are interested for you. Some of the methods that are most commonly used for interpreting a token of data include:
   * `next()` to get the next token as a `String`
   * `nextInt()` to get the next token as an `int`
   * `nextDouble()` to get the next token as a `double`
   * `nextBoolean()` to get the next token as a `boolean`
   * `nextLine()` get the whole line as a `String`
   * All of the equivalent `hasNextX()` methods such as `hasNext()` and `hasNextInt()`.

   # <i class="fas fa-book fa-fw"></i> Arrays

## Array Fundamentals

One of the most important capabilities in programming comes from the ability to process some *sequence of data*. For example we might write programs to process grades of students in a class, information about respondents to the US Census, or many other applications. Most programming languages provide a first introduction to processing sequences of data with the concept of *arrays*. An array is a *fixed-length* structure that stores multiple values of the same type.

In Java, the array syntax is mostly the same to how arrays are used in other languages. The largest difference is how you specify the type of an array. If you want an array storing integer values, the type is `int[]` (read as "int array"). The following code snippet makes an int array storing 5 elements, and uses assignment statements to fill in the array. One thing to note is that Java starts arrays with index 0. So an array of length 5 has valid indices `0, 1, 2, 3, 4`.

```java
int[] array = new int[5];
array[0] = 1;
array[1] = 14;
array[3] = array[1];
array[4] = 5;

System.out.println(array);
```

The syntax of assigning or getting a value inside an array is much like using a variable, but we add a `[x]` at the end to indicate we want to use index `x`. So on the left-hand of the `=` for assignment we are assigning *into* the variable at that index, and on the right side we are *getting* the value at that index.

By default, an array is initialized with the *zero-equivalent* of whatever type the array stores. So after creating the array in the example above, its contents start `[0, 0, 0, 0, 0]`.  By zero-equivalent, we mean there is a special value for each type that Java considers the most like 0 which will be the default contents for arrays of that type. So for a `boolean[]`, it defaults to `false` and for a `double[]` it defaults to `0.0`. You can also make arrays of object types such as `String[]` which defaults to a special value called `null`. Note that it is not expected that you understand the concept of `null` yet, so we do not explain what this special value means.

Two important notes about arrays in Java:
* Because Java requires you to declare types of variables ahead of time, it's not really possible to store an array of mixed types. You couldn't make an array of `boolean` or `int` types in the same array, since `int[]` only allows `int` and `boolean[]` only allows `boolean`.
* Arrays in Java are *fixed-length*. This means when you make an array, you have to specify how long it is in the line `new int[10]`. This is a limitation of arrays in that they are not dynamically sized. We will learn more complex data structures such as `ArrayList` later that dynamically resize based on what values you add.

## Looping over Arrays

Since arrays are designed to hold sequences of values, it is often useful to be able to process all of the values inside a loop rather than hard coding indices. In Java, an array knows how many elements are inside of it by accessing the `array.length` property. The loop is just using a for loop over all of the possible indices in the array. In our example above we said that for an array of length 5, the possible indices are `0, 1, 2, 3, 4` since the array indices start at 0. For a general array of length `array.length`, the possible indices are `0` (inclusive) to `array.length - 1` (inclusive). This is often equivalently written as `0` (inclusive) to `array.length` (exclusive), which is how the loop below is written.

```java
int[] array = new int[5];
// Code to fill array with some values

int sum = 0;
for (int i = 0; i < array.length; i++) {
    sum += array[i];
}
```

Array manipulations can be more complicated when it involves reading or accessing multiple indices at a time. Special care must be taken to make sure you never go **out of bounds** of an array. An `ArrayIndexOutOfBoundsException` occurs if you ever try to access an invalid index which is any index `< 0` or `>= array.length`.

The following code snippet shows how to write code that is careful about array indices in the task of trying to shift all the array elements to the left one index. So for example, if `array` stores the numbers `[1, 2, 3]`, then `shift(array)` should modify the array to store the numbers `[2, 3, 1]`. Note that since the loop is written to access both the values at index `i` and `i + 1`, we have to stop our loop one early so it doesn't cause an `ArrayOutOfBoundsException`. Also note the special case to handle the *empty array* case where the array length is 0!

```java
public static void shift(int[] numbers) {
    if (numbers.length > 0) {
        // Save the first number for later
        int firstNumber = numbers[0];

        // Shift every number forward one index
        for (int i = 0; i < numbers.length - 1; i++) {
            numbers[i] = numbers[i + 1];
        }

        // Store the old first number at the last spot
        numbers[numbers.length - 1] = firstNumber;
    }
}
```
