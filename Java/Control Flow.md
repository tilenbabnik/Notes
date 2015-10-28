# Control Flow

## If statement
To check if value is true use if statement.

```java
boolean isAlive = true;
if (isAlive) {
	System.out.println("He is alive!");
}
```

To specify what to do when if statement doesn't pass use else statement.

```java
boolean isAlive = true;
if (isAlive) {
	System.out.println("He is alive!");
} else {
	System.out.println("He is dead!");
}
```

## Switch statement
To check for multiple values that are not booleans use switch statement.

```java
String food = "Pizza";

switch (food) {
	case "Hamburger":
		System.out.println("You must be american!");
		break;
	case "Pizza":
		System.out.println("From Italy!");
		break;
	default:
		System.out.println("Don't know what this is!");
}
```