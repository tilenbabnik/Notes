# Output

## Println
Prints out to the console and makes a new line at the end.

```java
System.out.println("Hello, World!");
```

## Print
Prints out to the console but doesn't make a new line at the end.

```java
System.out.print("Hello, ");
System.out.print("World!");
```

## Printf
We can use printf to format the output. To start specifying the format use % sign. In the second part of printf statement give variables for each placeholder.

### Flags
Flags are used to specify additional formatting options.

* -
* +
* ,
* 0

### Width
Specifies how many characters can be used to output the number.

```java
int number = 20;
System.out.printf("%5d", number); // Will print "   20"
```

### Precision
To specify how precise you want to output double to console start with a dot then specify precision with number.

```java
double pi = 3.141592;
System.out.printf("%.3f", pi);
```

### Conversion Character
Comes at the end and specifies the command or a placeholder.

* d => whole numbers (int)
* f => decimal numbers (double, float)
* e => decimal numbers in exponential form
* s => text (string)
* n => new line