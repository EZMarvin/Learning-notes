### JAVA Question
* what is the difference b/w overloading and overriding
* what are the data types do you know?
* Explain about different types of variables?
* what is type casting
* what are the control statements do you ?
* what is String Concatnation?
* what are access modifiers
* can we overload statice method in java?
* can we override static method in java?
* can we override private method in java?
* what are the diffrences between abstarct class and interface?
* what is abstraction?
* what is coupling?
* what is data hiding?
* what is IS-A relationship and HAS-A relationship?
* what is the difference b/w composition and aggrigation?
* what is exception handling and what are the types of exceptions?
* what are the Object class methods do you know?
* what is cloning?what are the types clonings?
* what is autoboxing and unboxing?
* what is SCP?
* what is String,StringBuffer and StringBuilder
* what is String,StringBuffer and StringBuilder
* what is the use of toString()?
* what is constructor
* what are the differences between .equals() and (==) operator?
* what is garbage collection
* what are the diffrences between throw and throws?
* what is the difference between final,finally and finalize()?
* Can finally block be used without catch?
* What is exception propagation ?
* What is the meaning of immutable in terms of String?..
* Why string objects are immutable in java?
* How many objects will be created in the following code?String s1="Antra";String s2="Antra";String s3="Antra"?

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
### Random 
* Math.random() 产生[0.0-1.0) 带正号的double值
* Util.Random 
```java
Random random1 = new Random(); // 创建随机数生成器 seed num 默认是当前时间的毫秒数
Random random2 = new Random(10); // 用Seed number创建生成器
Random random3 = new Random(10);

int num1 = random1.nextInt(20); // 生成 [0, 10) 范围内随机数
int num2 = random2.nextInt(10); // 相同seed 生成随机数序列相同
int num3 = random3.nextInt(10);
random1.nextBoolean();
random1.nextBytes();
random1.nextDouble();
random1.nextFloat();
```
