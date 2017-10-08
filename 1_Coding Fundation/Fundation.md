### JAVA Question
[2017/10/3 下午1:53:46] Koteswari Krishna: what is the difference b/w overloading and overriding
[2017/10/3 下午1:54:03] Koteswari Krishna: what are the data types do you know?
[2017/10/3 下午1:54:26] Koteswari Krishna: Explain about different types of variables?
[2017/10/3 下午1:55:23] Koteswari Krishna: what is type casting
[2017/10/3 下午1:56:01] Koteswari Krishna: what are the control statements do you ?
[2017/10/3 下午1:56:20] Koteswari Krishna: what is String Concatnation?
[2017/10/3 下午1:57:08] Koteswari Krishna: what are access modifiers
[2017/10/3 下午1:57:23] Koteswari Krishna: can we overload statice method in java?
[2017/10/3 下午1:58:10] Koteswari Krishna: can we override static method in java?
[2017/10/3 下午1:58:21] Koteswari Krishna: can we override private method in java?
[2017/10/3 下午1:58:47] Koteswari Krishna: what are the diffrences between abstarct class and interface?
[2017/10/3 下午1:59:39] Koteswari Krishna: what is abstraction?
[2017/10/3 下午2:00:04] Koteswari Krishna: what is coupling?
[2017/10/3 下午2:00:17] Koteswari Krishna: what is data hiding?
[2017/10/3 下午2:00:53] Koteswari Krishna: what is IS-A relationship and HAS-A relationship?
[2017/10/3 下午2:01:21] Koteswari Krishna: what is the difference b/w composition and aggrigation?
[2017/10/5 下午1:55:45] Koteswari Krishna: what is exception handling and what are the types of exceptions?
[2017/10/5 下午1:56:37] Koteswari Krishna: what are the Object class methods do you know?
[2017/10/5 下午1:57:57] Koteswari Krishna: 11
[2017/10/5 下午1:58:00] Koteswari Krishna: methods
[2017/10/5 下午1:58:03] Koteswari Krishna: are there
[2017/10/5 下午1:58:32] Koteswari Krishna: what is cloning?what are the types clonings?
[2017/10/5 下午1:59:15] Koteswari Krishna: what is autoboxing and unboxing?
[2017/10/5 下午1:59:40] Koteswari Krishna: what is SCP?
[2017/10/5 下午2:00:03] Koteswari Krishna: what is String,StringBuffer and StringBuilder
[2017/10/5 下午2:00:59] Koteswari Krishna: what is String,StringBuffer and StringBuilder
[2017/10/5 下午2:01:07] Koteswari Krishna: what is the use of toString()?
[2017/10/5 下午2:01:16] Koteswari Krishna: what is constructor
[2017/10/5 下午2:01:29] Koteswari Krishna: what are the differences between .equals() and (==) operator?
[2017/10/5 下午2:02:13] Koteswari Krishna: what is garbage collection
[2017/10/5 下午2:02:47] Koteswari Krishna: what are the diffrences between throw and throws?
[2017/10/5 下午2:03:00] Koteswari Krishna: what is the difference between final,finally and finalize()?
[2017/10/5 下午2:03:34] Koteswari Krishna: Can finally block be used without catch?
[2017/10/5 下午2:03:46] Koteswari Krishna: What is exception propagation ?
[2017/10/5 下午2:04:19] Koteswari Krishna: What is the meaning of immutable in terms of String?..
[2017/10/5 下午2:04:58] Koteswari Krishna: Why string objects are immutable in java?
[2017/10/5 下午2:05:24] Koteswari Krishna: How many objects will be created in the following code?String s1="Antra";String s2="Antra";String s3="Antra"?

### Stream - **Java**
 In Java, the Scanner class is widely used to read input, but each language has its own mechanism for handling IO (input and output). 

The syntax for reading from stdin using the Scanner class is as follows:
```java
Scanner scan = new Scanner(System.in);
```
This creates a new Scanner object that reads from the System.in stream and can be accessed using the variable name . To read in information from stdin, you just need to apply Scanner's methods to your scanner object. Here are two basic examples:

```java
scan.next(); // returns the next token of input
scan.hasNext(); // returns true if there is another token of input (false otherwise)
scan.nextLine() // returns the next LINE of input
scan.nextInt();
scan.nextDouble();
scan.hasNextLine(); // returns true if there is another line of iput
```
Check out the comprehensive list of Scanner methods to learn more. 

When you are finished reading from an input stream, you should close it to avoid a resource leak. The following line of code closes the Scanner object referenced by our  variable:
```java
scan.close();
```
Let's say we want to assign a value received from stdin to some String that we'll name , and then print it. We can accomplish this with the following code:
```java
Scanner scan = new Scanner(System.in); // open scanner
String s = scan.next(); // read the next token and save it to 's'
scan.close(); // close scanner
System.out.println(s); // print 's' to System.out, followed by a new line
```
If the input token is Hi!, the above code will print Hi!. 

You can also print text in quotes using System.out.println, or combine quoted text with a variable 
```java
System.out.println("Input received: " + s);
```
