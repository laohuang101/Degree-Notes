# Tutorial Lab Questions and Answers

## Lab 1 – Introduction to Java Programming

### TASK 1:

**Question:** Create a source file containing a Java program. Perform the following steps to compile the program and run it.

1. Create a file named Welcome.java. You can use any editor that will save your file in text format.

```java
public class Welcome {
    /**
     * @param args the command line arguments
     */
    public static void main(String[] args) {
        System.out.println("Welcome to Java.");
    }
}
```

2. Compile the source file.
3. Run the bytecode.
4. Replace "Welcome to Java" with "My first program" in the program; save, compile, and run the program. You will see the message "My first program" displayed.

**Answer:**
```java
public class Welcome {
    public static void main(String[] args) {
        System.out.println("My first program");
    }
}
```

5. Replace main with Main, and recompile the source code. The compiler returns an error message because the Java program is case-sensitive.

**Answer:** Error occurs because Java is case-sensitive. The JVM looks for `main` (lowercase) as the entry point.

6. Change it back, and compile the program again.

7. If you use command-line:
   - Instead of the command javac Welcome.java, use javac welcome.java. What happens?
   - Instead of the command java Welcome, use java Welcome.class. What happens?

**Answers:**
- **Using `javac welcome.java` instead of `javac Welcome.java`:**
  - On case-sensitive systems (Linux/Unix), this will fail because the file is named `Welcome.java` (capital W).
  - On Windows, it might work due to case-insensitive file system.

- **Using `java Welcome.class` instead of `java Welcome`:**
  - Error occurs. The `java` command expects the class name (without `.class` extension), not the filename.

### TASK 2:

**Question:** Write the same program in Netbeans IDE or equivalent. Understand the Project File Structure (packages and Java files) and state the difference between the "Run Project" and "Run File".

**Answer:**

| Feature | Run Project | Run File |
|---------|-------------|----------|
| Scope | Runs the entire project (main class) | Runs only the selected file |
| Main Method | Must have a main method in the project | Must have a main method in the file |
| Use | Testing the complete application | Testing individual classes with main methods |

---

## Lab 2 – Primitive Data Types and Operations

**Question:** Use Scanner class for prompting the users for input.

### Instructor-led Demo:

**Question:** Write a program that reads a number in feet, converts it to meters, and displays the result. One foot is 0.305 meters.

**Answer:**
```java
import java.util.Scanner;

public class FeetToMeters {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Enter feet: ");
        double feet = input.nextDouble();
        double meters = feet * 0.305;
        System.out.println(feet + " feet is " + meters + " meters");
    }
}
```

### Exercise:

**Question 1:** Write a program that reads a Fahrenheit degree in double, then converts it to Celsius and displays the result on the console. The formula for the conversion is as follows: celsius = (Fahrenheit – 32) * 5 / 9

**Answer:**
```java
import java.util.Scanner;

public class FahrenheitToCelsius {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Enter Fahrenheit: ");
        double fahrenheit = input.nextDouble();
        double celsius = (fahrenheit - 32) * 5 / 9;
        System.out.println("Celsius: " + celsius);
    }
}
```

**Question 2:** Write a program that reads in the radius and length of a cylinder and computes volume using the following formulas:
- area = radius * radius * PI
- volume = area * length

**Answer:**
```java
import java.util.Scanner;

public class CylinderVolume {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Enter radius: ");
        double radius = input.nextDouble();
        System.out.print("Enter length: ");
        double length = input.nextDouble();
        double area = radius * radius * Math.PI;
        double volume = area * length;
        System.out.println("Area: " + area);
        System.out.println("Volume: " + volume);
    }
}
```

**Question 3:** Write a program that reads an integer between 0 and 1000 and adds all the digits in the integer. For example, if an integer is 943, the sum of all its digit is 16.

**Answer:**
```java
import java.util.Scanner;

public class SumDigits {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Enter integer (0-1000): ");
        int number = input.nextInt();
        int sum = 0;
        while (number > 0) {
            sum += number % 10;
            number /= 10;
        }
        System.out.println("Sum of digits: " + sum);
    }
}
```

**Question 4:** Write a program that converts an uppercase letter to a lowercase letter.

**Answer:**
```java
import java.util.Scanner;

public class UpperToLower {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Enter uppercase letter: ");
        char upper = input.next().charAt(0);
        char lower = (char)(upper + 32);
        System.out.println("Lowercase: " + lower);
    }
}
```

**Question 5:** Write a program that receives an ASCII code (an integer between 0 and 128) and displays its character. For example, if the user enters 97, the program displays character 'a'.

**Answer:**
```java
import java.util.Scanner;

public class AsciiToChar {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Enter ASCII code (0-128): ");
        int ascii = input.nextInt();
        char character = (char) ascii;
        System.out.println("Character: " + character);
    }
}
```

**Question 6:** Write a program that prompts the user to enter the month and year, and displays the number of days in the month. For example, January is 31 days, February is 28 days, March is 31 and etc.

**Answer:**
```java
import java.util.Scanner;

public class DaysInMonth {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Enter month (1-12): ");
        int month = input.nextInt();
        System.out.print("Enter year: ");
        int year = input.nextInt();
        int days;
        
        switch (month) {
            case 1: case 3: case 5: case 7: case 8: case 10: case 12:
                days = 31;
                break;
            case 4: case 6: case 9: case 11:
                days = 30;
                break;
            case 2:
                days = (year % 4 == 0 && year % 100 != 0) || (year % 400 == 0) ? 29 : 28;
                break;
            default:
                days = 0;
        }
        System.out.println("Number of days: " + days);
    }
}
```

**Question 7:** Write a program that prompts the user to enter assignment marks and displays the grade of the keyed in marks. The grading table is as follows:

| Marks | Grade | Description |
|-------|-------|-------------|
| 0-40 | F | Fail |
| 40-49 | F+ | Marginal Fail |
| 50-54 | D | Pass |
| 55-64 | C |  |
| 65-69 | B | Credit |
| 70-74 | B+ |  |
| 75-79 | A | Distinction |
| 80-100 | A+ |  |

**Answer:**
```java
import java.util.Scanner;

public class GradeCalculator {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Enter marks: ");
        int marks = input.nextInt();
        String grade;
        
        if (marks < 40) grade = "F - Fail";
        else if (marks < 50) grade = "F+ - Marginal Fail";
        else if (marks < 55) grade = "D - Pass";
        else if (marks < 65) grade = "C";
        else if (marks < 70) grade = "B - Credit";
        else if (marks < 75) grade = "B+";
        else if (marks < 80) grade = "A - Distinction";
        else if (marks <= 100) grade = "A+";
        else grade = "Invalid marks";
        
        System.out.println("Grade: " + grade);
    }
}
```

**Question 8:** Write a program that sum up all the values in double typed of an array. The array capacity is 100. You are required to use for-each construct (enhanced for).

**Answer:**
```java
import java.util.Scanner;

public class SumArray {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        double[] array = new double[100];
        System.out.println("Enter values (enter -1 to stop): ");
        int count = 0;
        
        for (int i = 0; i < array.length; i++) {
            double value = input.nextDouble();
            if (value == -1) break;
            array[i] = value;
            count++;
        }
        
        double sum = 0;
        for (double num : array) {
            sum += num;
        }
        System.out.println("Sum: " + sum);
    }
}
```

**Question 9:** Suppose that the tuition of a university is RM10000 this year and this tuition fee increases 5% every year. Write a program that uses a loop to compute the tuition in ten years.

**Answer:**
```java
public class TuitionCalculator {
    public static void main(String[] args) {
        double tuition = 10000;
        System.out.println("Year\tTuition");
        for (int year = 1; year <= 10; year++) {
            tuition *= 1.05;
            System.out.println(year + "\t" + String.format("%.2f", tuition));
        }
    }
}
```

**Question 10:** Use do-while construct, write a program that prompts the users to continue the program execution. "Yes" to continue the program and "No" to terminate the program.

**Answer:**
```java
import java.util.Scanner;

public class DoWhileMenu {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        String choice;
        do {
            System.out.println("Program running...");
            System.out.print("Continue? (Yes/No): ");
            choice = input.next();
        } while (choice.equalsIgnoreCase("Yes"));
        System.out.println("Program terminated.");
    }
}
```

**Question 11:** Write a program that reads in investment amount, annual interest rate, and number of years, and displays the future investment value using the following formula: futureInvestmentVal = investmentAmount x (1 + monthlyInterestRate) numberOfYears*12

**Answer:**
```java
import java.util.Scanner;

public class FutureInvestment {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Enter investment amount: ");
        double investmentAmount = input.nextDouble();
        System.out.print("Enter annual interest rate (%): ");
        double annualInterestRate = input.nextDouble();
        System.out.print("Enter number of years: ");
        int years = input.nextInt();
        
        double monthlyInterestRate = annualInterestRate / 1200;
        double futureValue = investmentAmount * Math.pow(1 + monthlyInterestRate, years * 12);
        
        System.out.printf("Future value: %.2f\n", futureValue);
    }
}
```

---

## Lab 3 – Objects and Classes

### Instructor-led Demo:

**Question:** Write a class named Account to model accounts. The UML diagram for the class is shown in Figure 4.0. Write a test program to test the Account class. In the client program, create an Account object with an account ID of 1222, a balance of 20000, and an annual interest rate of 4.5%. Use the withdraw method to withdraw $2500, use the deposit method to deposit $3000, and print the balance and the monthly interest.

**UML Diagram:**
```
Account
-id:int
-balance:double
-annualInterestRate:double
+Account()
+getId():int
+getBalance():double
+getAnnualInterestRate:double
+setId(id:int):void
+setBalance(bal:double):void
+setAnnualInterestRate(rate:double):void
+getMonthlyInterestRate():double
+withdraw(amount:double):void
+deposit(amount:double):void
```

**Answer:**
```java
public class Account {
    private int id;
    private double balance;
    private double annualInterestRate;
    
    public Account() {
        id = 0;
        balance = 0;
        annualInterestRate = 0;
    }
    
    public Account(int id, double balance, double annualInterestRate) {
        this.id = id;
        this.balance = balance;
        this.annualInterestRate = annualInterestRate;
    }
    
    public int getId() { return id; }
    public double getBalance() { return balance; }
    public double getAnnualInterestRate() { return annualInterestRate; }
    
    public void setId(int id) { this.id = id; }
    public void setBalance(double balance) { this.balance = balance; }
    public void setAnnualInterestRate(double annualInterestRate) { this.annualInterestRate = annualInterestRate; }
    
    public double getMonthlyInterestRate() {
        return annualInterestRate / 12;
    }
    
    public void withdraw(double amount) {
        balance -= amount;
    }
    
    public void deposit(double amount) {
        balance += amount;
    }
}
```

```java
public class TestAccount {
    public static void main(String[] args) {
        Account account = new Account(1222, 20000, 4.5);
        account.withdraw(2500);
        account.deposit(3000);
        System.out.println("Balance: " + account.getBalance());
        System.out.println("Monthly Interest Rate: " + account.getMonthlyInterestRate() + "%");
    }
}
```

### Exercise:

**Question 1:** Write a class named Rectangle to represent rectangles. The UML diagram for the class is shown in Figure 4.1 Suppose that all the rectangles are the same colour. Use a static variable for colour.

**UML Diagram:**
```
Rectangle
-width:double
-height:double
-color:String
+Rectangle()
+Rectangle(width:double, height:double, color:String)
+getWidth():double
+setWidth(width:double):void
+getHeight():double
+setHeight(height:double):void
+getColor:String
+setColor(color:String):void
+findArea():double
+findPerimeter():double
```

**Write a client program to test the class Rectangle. In the client program, create two Rectangle objects. Assign width 5 and height 50 each of the objects. Assign colour yellow. Display the properties of both objects and their areas.**

**Answer:**
```java
public class Rectangle {
    private double width;
    private double height;
    private static String color = "yellow";
    
    public Rectangle() {
        this(1, 1);
    }
    
    public Rectangle(double width, double height) {
        this.width = width;
        this.height = height;
    }
    
    public double getWidth() { return width; }
    public void setWidth(double width) { this.width = width; }
    public double getHeight() { return height; }
    public void setHeight(double height) { this.height = height; }
    public static String getColor() { return color; }
    public static void setColor(String color) { Rectangle.color = color; }
    
    public double findArea() {
        return width * height;
    }
    
    public double findPerimeter() {
        return 2 * (width + height);
    }
}
```

```java
public class TestRectangle {
    public static void main(String[] args) {
        Rectangle r1 = new Rectangle(5, 50);
        Rectangle r2 = new Rectangle(5, 50);
        Rectangle.setColor("yellow");
        
        System.out.println("Rectangle 1: Width=" + r1.getWidth() + ", Height=" + r1.getHeight() + 
                          ", Color=" + Rectangle.getColor() + ", Area=" + r1.findArea());
        System.out.println("Rectangle 2: Width=" + r2.getWidth() + ", Height=" + r2.getHeight() + 
                          ", Color=" + Rectangle.getColor() + ", Area=" + r2.findArea());
    }
}
```

**Question 2:** Write a class named Fan to model fans. The properties, as shown in Figure 4.2, are speed, on, radius, and color. You need to provide the accessor and mutator methods for the properties, and the toString method for returning a string consisting of all the values of all the properties in this class. Suppose the fan has three fixed speeds. Use constants 1, 2, and 3 to denote slow, medium, and fast speed.

**UML Diagram:**
```
Fan
-speed:int
-on:Boolean
-radius:double
-color:String
//constructor
//accessor methods
//toString method
```

**Write a client program to test the Fan class. In the client program, create a Fan object. Assign maximum speed, radius 10, color yellow, and turn it on. Display the object by invoking its toString object.**

**Answer:**
```java
public class Fan {
    public static final int SLOW = 1;
    public static final int MEDIUM = 2;
    public static final int FAST = 3;
    
    private int speed;
    private boolean on;
    private double radius;
    private String color;
    
    public Fan() {
        speed = SLOW;
        on = false;
        radius = 5;
        color = "blue";
    }
    
    public int getSpeed() { return speed; }
    public void setSpeed(int speed) { this.speed = speed; }
    public boolean isOn() { return on; }
    public void setOn(boolean on) { this.on = on; }
    public double getRadius() { return radius; }
    public void setRadius(double radius) { this.radius = radius; }
    public String getColor() { return color; }
    public void setColor(String color) { this.color = color; }
    
    public String toString() {
        if (on) {
            return "Fan is ON - Speed: " + speed + ", Radius: " + radius + ", Color: " + color;
        } else {
            return "Fan is OFF - Radius: " + radius + ", Color: " + color;
        }
    }
}
```

```java
public class TestFan {
    public static void main(String[] args) {
        Fan fan = new Fan();
        fan.setSpeed(Fan.FAST);
        fan.setRadius(10);
        fan.setColor("yellow");
        fan.setOn(true);
        System.out.println(fan.toString());
    }
}
```

**Question 3:** Java API has the GregorianCalendar class in the java.util package that can be used to obtain the year, month and day of a date. The no-arg constructor constructs an instance for the current date and the methods get(GregorianCalendar.YEAR), get(GregorianCalendar.MONTH), and get(GregorianCalendar.DAY) return the year, month and day. Write a program to test this class to display the current year, month and day.

**Answer:**
```java
import java.util.GregorianCalendar;

public class TestCalendar {
    public static void main(String[] args) {
        GregorianCalendar calendar = new GregorianCalendar();
        System.out.println("Year: " + calendar.get(GregorianCalendar.YEAR));
        System.out.println("Month: " + (calendar.get(GregorianCalendar.MONTH) + 1));
        System.out.println("Day: " + calendar.get(GregorianCalendar.DAY_OF_MONTH));
    }
}
```

**Question 4:** Write a class called Time. The Time class contains data fields hour, minute and second with their respective get methods. The no-arg constructor sets the hour, minute, and second for the current time in GMT. The current time can be obtained using System.currentTime(). Write a client program to test the Time class. In the client program, create a Time object and display hour, minute and second using the get methods.

**Answer:**
```java
public class Time {
    private int hour;
    private int minute;
    private int second;
    
    public Time() {
        long totalSeconds = System.currentTimeMillis() / 1000;
        this.second = (int)(totalSeconds % 60);
        long totalMinutes = totalSeconds / 60;
        this.minute = (int)(totalMinutes % 60);
        long totalHours = totalMinutes / 60;
        this.hour = (int)(totalHours % 24);
    }
    
    public int getHour() { return hour; }
    public int getMinute() { return minute; }
    public int getSecond() { return second; }
    
    public String toString() {
        return hour + ":" + minute + ":" + second;
    }
}
```

```java
public class TestTime {
    public static void main(String[] args) {
        Time time = new Time();
        System.out.println("Current time: " + time.toString());
        System.out.println("Hour: " + time.getHour());
        System.out.println("Minute: " + time.getMinute());
        System.out.println("Second: " + time.getSecond());
    }
}
```

**Question 5:** Using the Time class above, create an array storing Time object with its associated data (hour, minute, and second). Time object is created for every 5 seconds. Display the Time using toString method. The toString method returns hour:minute:second e.g., 1:30:30.

**Answer:**
```java
public class TestTimeArray {
    public static void main(String[] args) throws InterruptedException {
        Time[] times = new Time[3];
        for (int i = 0; i < times.length; i++) {
            times[i] = new Time();
            System.out.println("Time " + (i + 1) + ": " + times[i].toString());
            Thread.sleep(5000); // Wait 5 seconds
        }
    }
}
```

---

## Lab 4 – UML Modeling

**Question 1:** Given the following use case diagram. Explain the UML elements.

**Answer:**

| Element | Description | Symbol |
|---------|-------------|--------|
| Actor | External entity that interacts with the system (user, other system) | Stick figure |
| Use Case | Specific functionality or behavior of the system | Oval |
| System Boundary | Defines the scope of the system | Rectangle |
| Association | Relationship between actor and use case | Line |
| << include >> | Base use case always includes another use case | Dashed arrow with << include >> |
| << extend >> | Optional use case extends base use case under certain conditions | Dashed arrow with << extend >> |

**Question 2:** What is the main purpose of use case modeling?

**Answer:** Use case modeling is used to:
- **Capture functional requirements** from the user's perspective
- **Define system boundaries** and scope
- **Communicate with stakeholders** in a visual, understandable format
- **Identify actors** (users, external systems)
- **Document interactions** between actors and the system
- **Serve as basis** for test cases and system design

**Question 3:** Specify the situation for the following UML notations where it would be sensible to use these elements to structure your use case:
- << include >>
- << extend >>

**Answer:**

**<< include >>:**
- Use when a use case **always** requires another use case
- The included use case is a **mandatory** part of the base use case
- Example: "Process Payment" includes "Validate Credit Card"

**<< extend >>:**
- Use when a use case **optionally** adds behavior to another use case
- The extending use case runs only under **specific conditions**
- Example: "Print Receipt" extends "Process Payment" (only if customer wants receipt)

**Question 4:** Suppose you plan to develop application for an alarm clock. The clock shows the time of day. Using buttons, the users can set the hours and minutes fields individually and choose between 12 and 24 hour display. It is possible to set one or two alarms. When an alarm fires, it will sound some noise. The user can turn it off, or choose to "snooze". If the user does not respond at all, the alarm will turn off itself after 2 minutes. "Snoozing" means to turn off the sound, but the alarm will fire again after some minutes of delay. This "snoozing time" is pre-adjustable. Identify the top-level functional requirements for the clock, and model it with a use case diagram.

**Answer:**

**Top-level Functional Requirements:**
1. Display current time
2. Set time (hours and minutes)
3. Switch between 12-hour and 24-hour display
4. Set alarm (one or two alarms)
5. Turn off alarm
6. Snooze alarm
7. Adjust snooze time

**Use Case Diagram (Text Representation):**

```
┌─────────────────────────────────────┐
│           Alarm Clock System        │
├─────────────────────────────────────┤
│                                     │
│  ┌─────┐                            │
│  │User │                            │
│  └──┬──┘                            │
│     │                               │
│     ├─────────── Display Time       │
│     ├─────────── Set Time           │
│     ├─────────── Set Display Mode   │
│     ├─────────── Set Alarm          │
│     ├─────────── Turn Off Alarm     │
│     └─────────── Snooze Alarm       │
│                     │               │
│                     <<extend>>      │
│                     │               │
│              Adjust Snooze Time     │
│                                     │
└─────────────────────────────────────┘
```

---

## Lab 5 – Class Diagram

**Question 1:** Draw a class diagram which consists of all the classes in your system attributes and operations, relationships between the classes, multiplicity, and other model elements that you find appropriate.

**Scenario:** APComp consists of several departments. The departments are located in one or more offices. One office acts as a headquater. Each department has a manager who is recruited from the set of employees.

**Answer:**
```
┌─────────────────┐       ┌──────────────────┐
│   Department    │1..*   │      Office      │
├─────────────────┤◄──────┼──────────────────┤
│ - departmentId  │       │ - officeId       │
│ - name          │       │ - address        │
│ - location      │       │ - isHeadquarters │
├─────────────────┤       └──────────────────┘
│ + addEmployee() │
│ + getManager()  │
└────────┬────────┘
         │1
         │
         │1
┌────────▼────────┐
│    Employee     │
├─────────────────┤
│ - employeeId    │
│ - name          │
│ - salary        │
│ - hireDate      │
└─────────────────┘
```

**Question 2:** Consider the following Java code:

```java
import java.util.Vector;

public class Driver {
    private StringContainer b = null;

    public static void main(String[] args){
        Driver d = new Driver();
        d.run();
    }

    public void run() {
        b = new StringContainer();
        b.add("One");
        b.add("Two");
        b.remove("One");
    }
}

class StringContainer {
    private Vector v = null;

    public void add(String s) {
        init();
        v.add(s);
    }

    public boolean remove(String s) {
        init();
        return v.remove(s);
    }

    private void init() {
        if (v == null)
            v = new Vector();
    }
}
```

**Answer:**
```
┌─────────────────┐
│     Driver      │
├─────────────────┤
│ - b:StringContainer│
├─────────────────┤
│ + main()        │
│ + run()         │
└────────┬────────┘
         │1
         │
         │1
┌────────▼─────────────────┐
│    StringContainer       │
├──────────────────────────┤
│ - v:Vector               │
├──────────────────────────┤
│ + add(String)            │
│ + remove(String):boolean │
│ - init()                 │
└──────────────────────────┘
```

**Question 3:** To be a collector you have to have one or more collections. Each collection must have 2 or more items. Each collection belongs to one collector. A collection is made up of items owned. A particular item may be in more than one collection.

**Answer:**
```
┌─────────────────┐       ┌──────────────────┐
│    Collector    │1..*   │   Collection     │
├─────────────────┤◄──────┼──────────────────┤
│ - collectorId   │       │ - collectionId   │
│ - name          │       │ - name           │
├─────────────────┤       └────────┬─────────┘
│ + addCollection()│                │2..*
└─────────────────┘                │
                                   │
                                   │
                          ┌────────▼─────────┐
                          │      Item        │
                          ├──────────────────┤
                          │ - itemId         │
                          │ - description    │
                          └──────────────────┘
```

**Question 4:** Consider the following scenario:

You, as an Information Technology manager of AsiaMax Airline Company, are required to develop a new Flight Ticket Booking System (FTBS). The new computerised system can support the work of the flight ticket booking activities to the administration clerk and report generation to the manager. In booking flight tickets, the customers can walk in to the counter to book the tickets.

The administrative clerk is able to register, update and search customer's details when the registration is required for ticket booking. In this registration, customers are required to provide name, identity or passport number, date of birth, address, contact number and email address. The system will generate unique customer ID automatically and this customer information will be stored in database.

Following the registration, customers can proceed to book the tickets by providing the place to go, the date of departure and return, number of tickets (adult or kids), type of seat (business or economy), and passenger information. The attended clerk will search the desired tickets with the flight schedule. In this search process, a list of available flight schedule will be displayed for customer selection. The selected schedule and customer information will be placed to the customer booking file. This file contains customer information and booking details. The customer will then do final confirmation regarding the reservation with the total payment required inclusive of tax. Once the confirmation is made, customers are required to make payment of their reservation. A receipt will be generated when the payment is recorded.

The manager is able to read reports of monthly sales, detail customers, peak season ticket sales. The administrative clerk and manager have the authority access to report generation feature. The system is required to record the generated report date and time, person who generates that report and report title.

All the end users are required to login to the system in order to use the functions.

**TASK 1:** Analyse the above scenario and construct a use case diagram that depicts the functional requirements for the AsiaMax Airline Company.

**Answer:**

**Actors:** Admin Clerk, Manager, Customer

**Use Cases:**
- Login
- Register Customer
- Update Customer
- Search Customer
- Book Flight Ticket
- Search Flight Schedule
- Make Payment
- Generate Receipt
- Generate Monthly Sales Report
- Generate Customer Detail Report
- Generate Peak Season Sales Report

```
┌─────────────────────────────────────────────────────────┐
│              Flight Ticket Booking System                │
├─────────────────────────────────────────────────────────┤
│                                                         │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐    │
│  │Admin Clerk  │  │   Manager   │  │  Customer   │    │
│  └──────┬──────┘  └──────┬──────┘  └──────┬──────┘    │
│         │                │                │            │
│         │◄───────────────┴────────────────┤            │
│         │                                │            │
│         ├───────────── Login ────────────┤            │
│         │                                │            │
│         ├───────── Register Customer ────┤            │
│         ├───────── Update Customer ──────┤            │
│         ├───────── Search Customer ──────┤            │
│         │                                │            │
│         ├───────── Book Flight Ticket ───┤            │
│         │         │                      │            │
│         │         <<include>>            │            │
│         │         │                      │            │
│         │    Search Flight Schedule ─────┤            │
│         │         │                      │            │
│         │         <<include>>            │            │
│         │         │                      │            │
│         │      Make Payment ─────────────┤            │
│         │         │                      │            │
│         │         <<extend>>             │            │
│         │         │                      │            │
│         │    Generate Receipt ────────────┤            │
│         │                                │            │
│         ├───────── Monthly Sales Report ──┤            │
│         ├───────── Customer Detail Report─┤            │
│         ├───────── Peak Season Sales Report────────────┤            │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

**TASK 2:** Create a class diagram for FTBS of AsiaMax Airline Company. Look for opportunities to use the generalisation and composition and/or aggregation symbols. The class diagram should include main attributes and some methods for the major classes only. You may make any relevant assumptions about the business rules to support your answer.

**Answer:**
```
┌──────────────────┐
│      User        │
├──────────────────┤
│ - userId         │
│ - username       │
│ - password       │
├──────────────────┤
│ + login()        │
│ + logout()       │
└────────┬─────────┘
         │
         │◄──────┐
         │       │
         │   ┌───┴────────┐
         │   │            │
┌────────▼───┐ ┌────────▼────────┐
│   Clerk    │ │    Manager      │
├────────────┤ ├─────────────────┤
│ - clerkId  │ │ - managerId     │
├────────────┤ ├─────────────────┤
│ + register()│ │ + generateReport()│
│ + update()  │ └─────────────────┘
│ + search()  │
│ + bookTicket()│
│ + processPayment()│
└─────┬──────┘
      │1
      │
      │1..*
┌─────▼──────────┐
│   Customer     │
├────────────────┤
│ - customerId   │
│ - name         │
│ - passportNo   │
│ - dateOfBirth  │
│ - address      │
│ - contactNo    │
│ - email        │
├────────────────┤
│ + getDetails() │
└────┬───────────┘
     │1
     │
     │1..*
┌────▼──────────────┐
│    Booking        │
├───────────────────┤
│ - bookingId       │
│ - bookingDate     │
│ - totalAmount     │
│ - paymentStatus   │
├───────────────────┤
│ + confirm()       │
│ + cancel()        │
└────┬──────────────┘
     │1
     │
     │1..*
┌────▼──────────────┐
│   Ticket          │
├───────────────────┤
│ - ticketId        │
│ - type            │
│ - seatType        │
├───────────────────┤
│ + getDetails()    │
└────┬──────────────┘
     │
     │
     │1
┌────▼──────────────┐
│ FlightSchedule    │
├───────────────────┤
│ - scheduleId      │
│ - origin          │
│ - destination     │
│ - departureDate   │
│ - returnDate      │
│ - availableSeats  │
├───────────────────┤
│ + checkAvailability()│
└───────────────────┘

┌──────────────────┐
│    Report        │
├──────────────────┤
│ - reportId       │
│ - title          │
│ - generatedDate  │
│ - generatedBy    │
├──────────────────┤
│ + print()        │
└──────────────────┘
```

---

## Lab 6 – Inheritance and Polymorphism

### Instructor-led Demo:

**Question:** The Account class is to model a bank account. An account has the properties account number, balance, and annual interest rate, and methods to deposit and withdrawal. Create two subclasses for checking and saving accounts. A checking account has an overdraft limit, but a savings account cannot go overdrawn. Test your program.

**Answer:**
```java
public class Account {
    protected String accountNumber;
    protected double balance;
    protected double annualInterestRate;
    
    public Account(String accountNumber, double balance, double annualInterestRate) {
        this.accountNumber = accountNumber;
        this.balance = balance;
        this.annualInterestRate = annualInterestRate;
    }
    
    public void deposit(double amount) {
        balance += amount;
    }
    
    public void withdraw(double amount) {
        balance -= amount;
    }
    
    public double getBalance() {
        return balance;
    }
}
```

```java
public class CheckingAccount extends Account {
    private double overdraftLimit;
    
    public CheckingAccount(String accountNumber, double balance, double annualInterestRate, double overdraftLimit) {
        super(accountNumber, balance, annualInterestRate);
        this.overdraftLimit = overdraftLimit;
    }
    
    @Override
    public void withdraw(double amount) {
        if (balance - amount >= -overdraftLimit) {
            balance -= amount;
        } else {
            System.out.println("Exceeds overdraft limit");
        }
    }
}
```

```java
public class SavingsAccount extends Account {
    public SavingsAccount(String accountNumber, double balance, double annualInterestRate) {
        super(accountNumber, balance, annualInterestRate);
    }
    
    @Override
    public void withdraw(double amount) {
        if (balance >= amount) {
            balance -= amount;
        } else {
            System.out.println("Insufficient funds - no overdraft allowed");
        }
    }
}
```

```java
public class TestAccounts {
    public static void main(String[] args) {
        CheckingAccount checking = new CheckingAccount("C001", 1000, 0.01, 500);
        SavingsAccount savings = new SavingsAccount("S001", 2000, 0.02);
        
        checking.withdraw(1200); // Should work (within overdraft)
        savings.withdraw(2500);  // Should fail
        System.out.println("Checking balance: " + checking.getBalance());
        System.out.println("Savings balance: " + savings.getBalance());
    }
}
```

### Exercise:

**Question 1:** Implement a class named Person and two subclasses of Person named Student and Employee. Make Faculty and Staff subclasses of Employee. A person has a name, address, phone number, and email address. A student has a status (freshman, sophomore, junior, or senior). Define the status as a constant (Hint: Use Enum). An employee has an office, salary, and date-hired. Define a class named MyDate that contains the fields year, month, and day. A faculty member has office hours and a rank. A staff member has a title, override the toString method in each class to display the class name and the person's name.

Furthermore from Q1, make FullTime and PartTime subclasses of Staff. Full time staff has a fixed salary whereas part time staff has a salary depending on worked hour. Implement this requirement that demonstrate the earning for both staff.

Test your program. Demonstrate the result to the instructor.

**Answer:**
```java
public class Person {
    protected String name;
    protected String address;
    protected String phone;
    protected String email;
    
    public Person(String name, String address, String phone, String email) {
        this.name = name;
        this.address = address;
        this.phone = phone;
        this.email = email;
    }
    
    @Override
    public String toString() {
        return "Person: " + name;
    }
}
```

```java
public enum StudentStatus {
    FRESHMAN, SOPHOMORE, JUNIOR, SENIOR
}

public class Student extends Person {
    private StudentStatus status;
    
    public Student(String name, String address, String phone, String email, StudentStatus status) {
        super(name, address, phone, email);
        this.status = status;
    }
    
    @Override
    public String toString() {
        return "Student: " + name + " (Status: " + status + ")";
    }
}
```

```java
public class MyDate {
    private int year;
    private int month;
    private int day;
    
    public MyDate(int year, int month, int day) {
        this.year = year;
        this.month = month;
        this.day = day;
    }
    
    @Override
    public String toString() {
        return year + "-" + month + "-" + day;
    }
}
```

```java
public class Employee extends Person {
    private String office;
    private double salary;
    private MyDate dateHired;
    
    public Employee(String name, String address, String phone, String email, String office, double salary, MyDate dateHired) {
        super(name, address, phone, email);
        this.office = office;
        this.salary = salary;
        this.dateHired = dateHired;
    }
    
    @Override
    public String toString() {
        return "Employee: " + name;
    }
}
```

```java
public class Faculty extends Employee {
    private String officeHours;
    private String rank;
    
    public Faculty(String name, String address, String phone, String email, String office, double salary, MyDate dateHired, String officeHours, String rank) {
        super(name, address, phone, email, office, salary, dateHired);
        this.officeHours = officeHours;
        this.rank = rank;
    }
    
    @Override
    public String toString() {
        return "Faculty: " + name;
    }
}
```

```java
public class Staff extends Employee {
    private String title;
    
    public Staff(String name, String address, String phone, String email, String office, double salary, MyDate dateHired, String title) {
        super(name, address, phone, email, office, salary, dateHired);
        this.title = title;
    }
    
    @Override
    public String toString() {
        return "Staff: " + name;
    }
}
```

```java
public class FullTimeStaff extends Staff {
    private double fixedSalary;
    
    public FullTimeStaff(String name, String address, String phone, String email, String office, MyDate dateHired, String title, double fixedSalary) {
        super(name, address, phone, email, office, fixedSalary, dateHired, title);
        this.fixedSalary = fixedSalary;
    }
    
    public double getEarnings() {
        return fixedSalary;
    }
    
    @Override
    public String toString() {
        return "FullTime Staff: " + name + " - Earnings: RM" + getEarnings();
    }
}
```

```java
public class PartTimeStaff extends Staff {
    private double hourlyRate;
    private int hoursWorked;
    
    public PartTimeStaff(String name, String address, String phone, String email, String office, MyDate dateHired, String title, double hourlyRate, int hoursWorked) {
        super(name, address, phone, email, office, hourlyRate * hoursWorked, dateHired, title);
        this.hourlyRate = hourlyRate;
        this.hoursWorked = hoursWorked;
    }
    
    public double getEarnings() {
        return hourlyRate * hoursWorked;
    }
    
    @Override
    public String toString() {
        return "PartTime Staff: " + name + " - Earnings: RM" + getEarnings();
    }
}
```

```java
public class TestPersonHierarchy {
    public static void main(String[] args) {
        MyDate date = new MyDate(2020, 1, 15);
        
        Student student = new Student("Alice", "123 Street", "555-1234", "alice@email.com", StudentStatus.JUNIOR);
        FullTimeStaff fullTime = new FullTimeStaff("Bob", "456 Ave", "555-5678", "bob@email.com", "Office A", date, "Manager", 5000);
        PartTimeStaff partTime = new PartTimeStaff("Charlie", "789 Rd", "555-9012", "charlie@email.com", "Office B", date, "Assistant", 20, 80);
        
        System.out.println(student);
        System.out.println(fullTime);
        System.out.println(partTime);
    }
}
```

**Question 2:** Enabling GeometricObject comparable, Circle and Cylinder are subclasses of GeometricObject. Modify the GeometricObject class to implement the Comparable interface, define the max method in the GeometricObject class. Write a test program that uses the max method to find the larger of two circles and the larger of two cylinders.

**Answer:**
```java
public class GeometricObject implements Comparable<GeometricObject> {
    protected String color;
    protected boolean filled;
    
    public GeometricObject() {
        this("white", false);
    }
    
    public GeometricObject(String color, boolean filled) {
        this.color = color;
        this.filled = filled;
    }
    
    public static GeometricObject max(GeometricObject o1, GeometricObject o2) {
        if (o1.compareTo(o2) > 0)
            return o1;
        else
            return o2;
    }
    
    @Override
    public int compareTo(GeometricObject o) {
        return 0; // To be overridden by subclasses
    }
}
```

```java
public class Circle extends GeometricObject {
    private double radius;
    
    public Circle(double radius) {
        this.radius = radius;
    }
    
    public double getArea() {
        return Math.PI * radius * radius;
    }
    
    @Override
    public int compareTo(GeometricObject o) {
        if (this.getArea() > ((Circle) o).getArea())
            return 1;
        else if (this.getArea() < ((Circle) o).getArea())
            return -1;
        else
            return 0;
    }
}
```

```java
public class Cylinder extends Circle {
    private double height;
    
    public Cylinder(double radius, double height) {
        super(radius);
        this.height = height;
    }
    
    public double getVolume() {
        return getArea() * height;
    }
    
    @Override
    public int compareTo(GeometricObject o) {
        if (this.getVolume() > ((Cylinder) o).getVolume())
            return 1;
        else if (this.getVolume() < ((Cylinder) o).getVolume())
            return -1;
        else
            return 0;
    }
}
```

```java
public class TestComparable {
    public static void main(String[] args) {
        Circle c1 = new Circle(5);
        Circle c2 = new Circle(3);
        System.out.println("Larger circle: " + (GeometricObject.max(c1, c2).getArea()));
        
        Cylinder cyl1 = new Cylinder(3, 5);
        Cylinder cyl2 = new Cylinder(2, 8);
        System.out.println("Larger cylinder: " + (GeometricObject.max(cyl1, cyl2).getVolume()));
    }
}
```

**Question 3:** Create a class named ComparableCylinder that extends Cylinder and implements Comparable. Implement the compareTo method to compare the cylinders on the basic of volume. Write a test class to find the larger of two instances of ComparableCylinder objects.

**Answer:**
```java
public class ComparableCylinder extends Cylinder implements Comparable<ComparableCylinder> {
    public ComparableCylinder(double radius, double height) {
        super(radius, height);
    }
    
    @Override
    public int compareTo(ComparableCylinder o) {
        if (this.getVolume() > o.getVolume())
            return 1;
        else if (this.getVolume() < o.getVolume())
            return -1;
        else
            return 0;
    }
}
```

```java
public class TestComparableCylinder {
    public static void main(String[] args) {
        ComparableCylinder c1 = new ComparableCylinder(3, 5);
        ComparableCylinder c2 = new ComparableCylinder(2, 8);
        
        if (c1.compareTo(c2) > 0)
            System.out.println("Cylinder 1 is larger");
        else if (c1.compareTo(c2) < 0)
            System.out.println("Cylinder 2 is larger");
        else
            System.out.println("Cylinders are equal");
    }
}
```

**Question 4:** Create an interface named Colorable having an abstract method named howtoColor method. Every class of a colorable object must implement the Colorable interface. Create a class named Square that extends GeometricObject and implements Colorable. Implement howToColor to display a message on how to color the square.

**Answer:**
```java
public interface Colorable {
    void howToColor();
}
```

```java
public class Square extends GeometricObject implements Colorable {
    private double side;
    
    public Square(double side) {
        this.side = side;
    }
    
    public double getArea() {
        return side * side;
    }
    
    @Override
    public void howToColor() {
        System.out.println("Color all four sides of the square");
    }
}
```

```java
public class TestColorable {
    public static void main(String[] args) {
        GeometricObject[] objects = {new Square(5), new Circle(3)};
        
        for (GeometricObject obj : objects) {
            if (obj instanceof Colorable) {
                ((Colorable) obj).howToColor();
            }
        }
    }
}
```

---

## Lab 7 – Abstract Class and Interfaces

### Instructor-led Demo:

**Question:** Write a program that handles employees' salaries and workloads. There are part time and full time employee and they are payable with salaries. The salary for full time employee will be paid as monthly basis and part time employee will be based on hourly worked. There is a kind of employee (Assistant) which is not payable. All employees are required to work a certain number of hours depending on the type of employee. Part time work not more than 6 hour a week, full time work 40 hours a week and assistant work only 2 hours a week.

**Answer:**
```java
public abstract class Employee {
    protected String name;
    protected int hoursWorked;
    
    public Employee(String name, int hoursWorked) {
        this.name = name;
        this.hoursWorked = hoursWorked;
    }
    
    public abstract double calculateSalary();
    
    public abstract boolean validateHours();
}
```

```java
public class FullTimeEmployee extends Employee {
    private double monthlySalary;
    
    public FullTimeEmployee(String name, double monthlySalary) {
        super(name, 40);
        this.monthlySalary = monthlySalary;
    }
    
    @Override
    public double calculateSalary() {
        return monthlySalary;
    }
    
    @Override
    public boolean validateHours() {
        return hoursWorked == 40;
    }
}
```

```java
public class PartTimeEmployee extends Employee {
    private double hourlyRate;
    
    public PartTimeEmployee(String name, int hoursWorked, double hourlyRate) {
        super(name, hoursWorked);
        this.hourlyRate = hourlyRate;
    }
    
    @Override
    public double calculateSalary() {
        return hoursWorked * hourlyRate;
    }
    
    @Override
    public boolean validateHours() {
        return hoursWorked <= 6;
    }
}
```

```java
public class Assistant extends Employee {
    public Assistant(String name) {
        super(name, 2);
    }
    
    @Override
    public double calculateSalary() {
        return 0; // Not payable
    }
    
    @Override
    public boolean validateHours() {
        return hoursWorked == 2;
    }
}
```

```java
public class TestEmployees {
    public static void main(String[] args) {
        Employee fullTime = new FullTimeEmployee("Alice", 5000);
        Employee partTime = new PartTimeEmployee("Bob", 5, 15);
        Employee assistant = new Assistant("Charlie");
        
        System.out.println("Alice's salary: RM" + fullTime.calculateSalary());
        System.out.println("Bob's salary: RM" + partTime.calculateSalary());
        System.out.println("Charlie's salary: RM" + assistant.calculateSalary());
    }
}
```

### Exercise:

**Question 1:** Consider the UML diagram. Write a program that demonstrate Movable interface and MovablePoint and MovableCircle classes. State any assumption for your program.

**Answer:**
```java
public interface Movable {
    void moveUp();
    void moveDown();
    void moveLeft();
    void moveRight();
}
```

```java
public class MovablePoint implements Movable {
    private int x;
    private int y;
    private int xSpeed;
    private int ySpeed;
    
    public MovablePoint(int x, int y, int xSpeed, int ySpeed) {
        this.x = x;
        this.y = y;
        this.xSpeed = xSpeed;
        this.ySpeed = ySpeed;
    }
    
    @Override
    public void moveUp() { y -= ySpeed; }
    
    @Override
    public void moveDown() { y += ySpeed; }
    
    @Override
    public void moveLeft() { x -= xSpeed; }
    
    @Override
    public void moveRight() { x += xSpeed; }
    
    @Override
    public String toString() {
        return "(" + x + ", " + y + ")";
    }
}
```

```java
public class MovableCircle implements Movable {
    private MovablePoint center;
    private int radius;
    
    public MovableCircle(int x, int y, int xSpeed, int ySpeed, int radius) {
        this.center = new MovablePoint(x, y, xSpeed, ySpeed);
        this.radius = radius;
    }
    
    @Override
    public void moveUp() { center.moveUp(); }
    
    @Override
    public void moveDown() { center.moveDown(); }
    
    @Override
    public void moveLeft() { center.moveLeft(); }
    
    @Override
    public void moveRight() { center.moveRight(); }
    
    @Override
    public String toString() {
        return "Circle[radius=" + radius + ", center=" + center + "]";
    }
}
```

```java
public class TestMovable {
    public static void main(String[] args) {
        MovablePoint point = new MovablePoint(0, 0, 2, 2);
        System.out.println(point);
        point.moveUp();
        point.moveRight();
        System.out.println(point);
        
        MovableCircle circle = new MovableCircle(0, 0, 1, 1, 5);
        System.out.println(circle);
        circle.moveDown();
        circle.moveLeft();
        System.out.println(circle);
    }
}
```

**Question 2:** Modify the Lab 6-Q2 (Exercise), according to the UML diagram below. Write a test program called TestResizableCircle to test the method defined in ResizeableCircle.

**Answer:**
```java
public interface Resizable {
    int resize(int percent);
}
```

```java
public class ResizableCircle extends Circle implements Resizable {
    public ResizableCircle(double radius) {
        super(radius);
    }
    
    @Override
    public int resize(int percent) {
        radius = radius * (100 + percent) / 100;
        return percent;
    }
}
```

```java
public class TestResizableCircle {
    public static void main(String[] args) {
        ResizableCircle circle = new ResizableCircle(10);
        System.out.println("Original radius: " + circle.radius);
        circle.resize(50); // Increase by 50%
        System.out.println("New radius: " + circle.radius);
    }
}
```

---

## Lab 8 – Java GUI Development

### Instructor-led Demo:

**Question:** Write a program that creates a JFrame for system login. The form/UI has username and password textfields, and a login button. Display a message box when the button is clicked. Note that the login authentication or authorisation can be hardcoded in this demo.

**Answer:**
```java
import javax.swing.*;
import java.awt.event.*;

public class LoginForm extends JFrame {
    private JTextField usernameField;
    private JPasswordField passwordField;
    private JButton loginButton;
    
    public LoginForm() {
        setTitle("Login System");
        setSize(300, 200);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(null);
        
        JLabel userLabel = new JLabel("Username:");
        userLabel.setBounds(20, 20, 80, 25);
        add(userLabel);
        
        usernameField = new JTextField();
        usernameField.setBounds(100, 20, 150, 25);
        add(usernameField);
        
        JLabel passLabel = new JLabel("Password:");
        passLabel.setBounds(20, 50, 80, 25);
        add(passLabel);
        
        passwordField = new JPasswordField();
        passwordField.setBounds(100, 50, 150, 25);
        add(passwordField);
        
        loginButton = new JButton("Login");
        loginButton.setBounds(100, 90, 80, 25);
        add(loginButton);
        
        loginButton.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                String username = usernameField.getText();
                String password = new String(passwordField.getPassword());
                
                // Hardcoded authentication
                if (username.equals("admin") && password.equals("1234")) {
                    JOptionPane.showMessageDialog(null, "Login Successful!");
                } else {
                    JOptionPane.showMessageDialog(null, "Invalid Credentials!");
                }
            }
        });
    }
    
    public static void main(String[] args) {
        LoginForm form = new LoginForm();
        form.setVisible(true);
    }
}
```

### Exercise:

**Question 1:** Write a program that adds a group of radio buttons to select background colours. The available colours are red, yellow, white, gray, and green.

**Answer:**
```java
import javax.swing.*;
import java.awt.*;

public class ColorSelector extends JFrame {
    public ColorSelector() {
        setTitle("Color Selector");
        setSize(300, 150);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new FlowLayout());
        
        JRadioButton red = new JRadioButton("Red");
        JRadioButton yellow = new JRadioButton("Yellow");
        JRadioButton white = new JRadioButton("White", true);
        JRadioButton gray = new JRadioButton("Gray");
        JRadioButton green = new JRadioButton("Green");
        
        ButtonGroup group = new ButtonGroup();
        group.add(red);
        group.add(yellow);
        group.add(white);
        group.add(gray);
        group.add(green);
        
        red.addActionListener(e -> getContentPane().setBackground(Color.RED));
        yellow.addActionListener(e -> getContentPane().setBackground(Color.YELLOW));
        white.addActionListener(e -> getContentPane().setBackground(Color.WHITE));
        gray.addActionListener(e -> getContentPane().setBackground(Color.GRAY));
        green.addActionListener(e -> getContentPane().setBackground(Color.GREEN));
        
        add(red);
        add(yellow);
        add(white);
        add(gray);
        add(green);
    }
    
    public static void main(String[] args) {
        ColorSelector frame = new ColorSelector();
        frame.setVisible(true);
    }
}
```

**Question 2:** Write a program that creates a simple calculator performs add, subtract, multiply and divide operations.

**Answer:**
```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class Calculator extends JFrame {
    private JTextField num1Field, num2Field, resultField;
    private JButton addBtn, subBtn, mulBtn, divBtn;
    
    public Calculator() {
        setTitle("Simple Calculator");
        setSize(300, 250);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new GridLayout(5, 2, 5, 5));
        
        add(new JLabel("Number 1:"));
        num1Field = new JTextField();
        add(num1Field);
        
        add(new JLabel("Number 2:"));
        num2Field = new JTextField();
        add(num2Field);
        
        add(new JLabel("Result:"));
        resultField = new JTextField();
        resultField.setEditable(false);
        add(resultField);
        
        addBtn = new JButton("+");
        subBtn = new JButton("-");
        mulBtn = new JButton("*");
        divBtn = new JButton("/");
        
        add(addBtn);
        add(subBtn);
        add(mulBtn);
        add(divBtn);
        
        addBtn.addActionListener(e -> calculate('+'));
        subBtn.addActionListener(e -> calculate('-'));
        mulBtn.addActionListener(e -> calculate('*'));
        divBtn.addActionListener(e -> calculate('/'));
    }
    
    private void calculate(char op) {
        try {
            double num1 = Double.parseDouble(num1Field.getText());
            double num2 = Double.parseDouble(num2Field.getText());
            double result = 0;
            
            switch (op) {
                case '+': result = num1 + num2; break;
                case '-': result = num1 - num2; break;
                case '*': result = num1 * num2; break;
                case '/': 
                    if (num2 != 0) result = num1 / num2;
                    else { resultField.setText("Error: Div by 0"); return; }
                    break;
            }
            resultField.setText(String.valueOf(result));
        } catch (NumberFormatException e) {
            resultField.setText("Invalid Input");
        }
    }
    
    public static void main(String[] args) {
        Calculator calc = new Calculator();
        calc.setVisible(true);
    }
}
```

**Question 3:** Write a program that converts miles and kilometres. If you enter a value in the Mile text field and press that Enter key, the corresponding kilometre is displayed in the Kilometer text field.

**Answer:**
```java
import javax.swing.*;
import java.awt.event.*;

public class MilesToKm extends JFrame {
    private JTextField mileField, kmField;
    
    public MilesToKm() {
        setTitle("Miles to Kilometers");
        setSize(300, 150);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(null);
        
        JLabel mileLabel = new JLabel("Miles:");
        mileLabel.setBounds(20, 20, 80, 25);
        add(mileLabel);
        
        mileField = new JTextField();
        mileField.setBounds(100, 20, 150, 25);
        add(mileField);
        
        JLabel kmLabel = new JLabel("Kilometers:");
        kmLabel.setBounds(20, 50, 80, 25);
        add(kmLabel);
        
        kmField = new JTextField();
        kmField.setBounds(100, 50, 150, 25);
        kmField.setEditable(false);
        add(kmField);
        
        mileField.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                try {
                    double miles = Double.parseDouble(mileField.getText());
                    double km = miles * 1.60934;
                    kmField.setText(String.format("%.2f", km));
                } catch (NumberFormatException ex) {
                    kmField.setText("Invalid Input");
                }
            }
        });
    }
    
    public static void main(String[] args) {
        MilesToKm converter = new MilesToKm();
        converter.setVisible(true);
    }
}
```

**Question 4:** Write a program that calculates the future value of an investment at a given interest rate for a specified number of years. The formula for the calculation is as follows: futureValue = investmentAmount * (1 + montlyInterestRate)years*12

Use text fields for interest rate, investment amount, and years. Display the future amount in a text field when the user clicks the Calculator button.

**Answer:**
```java
import javax.swing.*;
import java.awt.event.*;

public class FutureValueCalculator extends JFrame {
    private JTextField investmentField, rateField, yearsField, resultField;
    private JButton calculateButton;
    
    public FutureValueCalculator() {
        setTitle("Future Investment Value");
        setSize(350, 250);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(null);
        
        addLabelAndField("Investment Amount:", 20, investmentField = new JTextField());
        addLabelAndField("Annual Interest Rate (%):", 60, rateField = new JTextField());
        addLabelAndField("Number of Years:", 100, yearsField = new JTextField());
        
        addLabelAndField("Future Value:", 140, resultField = new JTextField());
        resultField.setEditable(false);
        
        calculateButton = new JButton("Calculate");
        calculateButton.setBounds(120, 180, 100, 25);
        add(calculateButton);
        
        calculateButton.addActionListener(e -> calculateFutureValue());
    }
    
    private void addLabelAndField(String text, int y, JTextField field) {
        JLabel label = new JLabel(text);
        label.setBounds(20, y, 180, 25);
        add(label);
        field.setBounds(200, y, 120, 25);
        add(field);
    }
    
    private void calculateFutureValue() {
        try {
            double investment = Double.parseDouble(investmentField.getText());
            double annualRate = Double.parseDouble(rateField.getText()) / 100;
            int years = Integer.parseInt(yearsField.getText());
            
            double monthlyRate = annualRate / 12;
            double futureValue = investment * Math.pow(1 + monthlyRate, years * 12);
            
            resultField.setText(String.format("%.2f", futureValue));
        } catch (NumberFormatException e) {
            resultField.setText("Invalid Input");
        }
    }
    
    public static void main(String[] args) {
        FutureValueCalculator calculator = new FutureValueCalculator();
        calculator.setVisible(true);
    }
}
```

**Question 5:** Create a JFrame form that display the following JComponent objects (JLabel, JTextField, JButton, and JTable). Handle the events for Add, Edit and Delete buttons. The Add button inserting each JTextField's value to a row of JTable. The Edit button modifying the record in the JTable. The Delete button removing the record of JTable.

**Answer:**
```java
import javax.swing.*;
import javax.swing.table.DefaultTableModel;
import java.awt.*;

public class TableApp extends JFrame {
    private JTable table;
    private DefaultTableModel model;
    private JTextField nameField, ageField, salaryField;
    private JButton addButton, editButton, deleteButton;
    
    public TableApp() {
        setTitle("Table Application");
        setSize(500, 400);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new BorderLayout());
        
        // Input Panel
        JPanel inputPanel = new JPanel(new GridLayout(3, 2, 5, 5));
        inputPanel.add(new JLabel("Name:"));
        nameField = new JTextField();
        inputPanel.add(nameField);
        inputPanel.add(new JLabel("Age:"));
        ageField = new JTextField();
        inputPanel.add(ageField);
        inputPanel.add(new JLabel("Salary:"));
        salaryField = new JTextField();
        inputPanel.add(salaryField);
        
        // Button Panel
        JPanel buttonPanel = new JPanel();
        addButton = new JButton("Add");
        editButton = new JButton("Edit");
        deleteButton = new JButton("Delete");
        buttonPanel.add(addButton);
        buttonPanel.add(editButton);
        buttonPanel.add(deleteButton);
        
        // Table
        model = new DefaultTableModel(new Object[]{"Name", "Age", "Salary"}, 0);
        table = new JTable(model);
        JScrollPane scrollPane = new JScrollPane(table);
        
        // Layout
        JPanel northPanel = new JPanel(new BorderLayout());
        northPanel.add(inputPanel, BorderLayout.CENTER);
        northPanel.add(buttonPanel, BorderLayout.SOUTH);
        
        add(northPanel, BorderLayout.NORTH);
        add(scrollPane, BorderLayout.CENTER);
        
        // Event Handlers
        addButton.addActionListener(e -> addRecord());
        editButton.addActionListener(e -> editRecord());
        deleteButton.addActionListener(e -> deleteRecord());
    }
    
    private void addRecord() {
        String name = nameField.getText();
        int age = Integer.parseInt(ageField.getText());
        double salary = Double.parseDouble(salaryField.getText());
        
        model.addRow(new Object[]{name, age, salary});
        clearFields();
    }
    
    private void editRecord() {
        int row = table.getSelectedRow();
        if (row >= 0) {
            model.setValueAt(nameField.getText(), row, 0);
            model.setValueAt(Integer.parseInt(ageField.getText()), row, 1);
            model.setValueAt(Double.parseDouble(salaryField.getText()), row, 2);
            clearFields();
        } else {
            JOptionPane.showMessageDialog(this, "Select a row to edit");
        }
    }
    
    private void deleteRecord() {
        int row = table.getSelectedRow();
        if (row >= 0) {
            model.removeRow(row);
        } else {
            JOptionPane.showMessageDialog(this, "Select a row to delete");
        }
    }
    
    private void clearFields() {
        nameField.setText("");
        ageField.setText("");
        salaryField.setText("");
    }
    
    public static void main(String[] args) {
        TableApp app = new TableApp();
        app.setVisible(true);
    }
}
```

---

## Lab 9 – File Input/Output & Exception Handling

### Instructor-led Demo:

**Question:** Handle Exception: Write a program that meets the following requirements: Create an array with one hundred randomly chosen integers. Cause an exception, ArrayIndexOutOfBoundsException, display the message "Out Of Bound". You can display all the array elements using looping.

**Answer:**
```java
import java.util.Random;

public class ArrayExceptionDemo {
    public static void main(String[] args) {
        int[] array = new int[100];
        Random random = new Random();
        
        for (int i = 0; i < array.length; i++) {
            array[i] = random.nextInt(1000);
        }
        
        try {
            // Cause exception
            for (int i = 0; i <= array.length; i++) {
                System.out.println("Element " + i + ": " + array[i]);
            }
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Out Of Bound: " + e.getMessage());
        }
    }
}
```

**Question:** File Input/Output: Given an array of integers, write a program that writes these integers into the file. Prompt the users to read the integers from the same file.

**Answer:**
```java
import java.io.*;
import java.util.Scanner;

public class FileIODemo {
    public static void main(String[] args) {
        int[] numbers = {10, 20, 30, 40, 50};
        
        // Write to file
        try (PrintWriter writer = new PrintWriter("numbers.txt")) {
            for (int num : numbers) {
                writer.println(num);
            }
        } catch (IOException e) {
            System.out.println("Error writing to file");
        }
        
        // Read from file
        try (Scanner scanner = new Scanner(new File("numbers.txt"))) {
            System.out.println("Reading from file:");
            while (scanner.hasNextInt()) {
                System.out.println(scanner.nextInt());
            }
        } catch (IOException e) {
            System.out.println("Error reading from file");
        }
    }
}
```

### Exercise:

**Question 1:** Write a program that counts the number of characters including words and lines in a file. The program prompts the user for inputting the filename. Note that the IOException to be handled. Sample output as follows: 
Please enter the filename: narrative.txt
File Sample.txt has
1732 characters,
204 words and 70 lines.

**Answer:**
```java
import java.io.*;
import java.util.Scanner;

public class FileStats {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Please enter the filename: ");
        String filename = scanner.nextLine();
        
        int characters = 0;
        int words = 0;
        int lines = 0;
        
        try (BufferedReader reader = new BufferedReader(new FileReader(filename))) {
            String line;
            while ((line = reader.readLine()) != null) {
                lines++;
                characters += line.length() + 1; // +1 for newline
                if (!line.trim().isEmpty()) {
                    words += line.trim().split("\\s+").length;
                }
            }
        } catch (IOException e) {
            System.out.println("Error reading file: " + e.getMessage());
        }
        
        System.out.println("File " + filename + " has");
        System.out.println(characters + " characters,");
        System.out.println(words + " words and " + lines + " lines.");
    }
}
```

**Question 2:** Suppose that a text file scores.txt contains an unspecified number of scores. Write a program that reads the scores from the file and displays their total and average. Scores are separately by blanks. Hint: Read the scores one line at a time until all the lines are read. For each line, use StringTokenizer or Scanner to extract the scores and convert them into double values using the Double.parseDouble method.

**Answer:**
```java
import java.io.*;
import java.util.*;

public class ScoreCalculator {
    public static void main(String[] args) {
        try (Scanner scanner = new Scanner(new File("scores.txt"))) {
            double total = 0;
            int count = 0;
            
            while (scanner.hasNext()) {
                double score = scanner.nextDouble();
                total += score;
                count++;
            }
            
            double average = count > 0 ? total / count : 0;
            
            System.out.println("Total: " + total);
            System.out.println("Average: " + average);
        } catch (IOException e) {
            System.out.println("Error reading file");
        }
    }
}
```

**Question 3:** Write a program to create a file named ints.txt if it does not exist. Write one hundred integers created randomly into the file using text I/O. Integers are separated by spaces in the file. Using StringTokenizer or Scanner to read the data back from the file and display the sorted data.

**Answer:**
```java
import java.io.*;
import java.util.*;
import java.util.stream.*;

public class RandomIntegers {
    public static void main(String[] args) {
        Random random = new Random();
        
        // Write 100 random integers
        try (PrintWriter writer = new PrintWriter("ints.txt")) {
            for (int i = 0; i < 100; i++) {
                writer.print(random.nextInt(1000) + " ");
            }
        } catch (IOException e) {
            System.out.println("Error writing to file");
        }
        
        // Read and sort
        try (Scanner scanner = new Scanner(new File("ints.txt"))) {
            List<Integer> numbers = new ArrayList<>();
            while (scanner.hasNextInt()) {
                numbers.add(scanner.nextInt());
            }
            Collections.sort(numbers);
            System.out.println("Sorted numbers: " + numbers);
        } catch (IOException e) {
            System.out.println("Error reading from file");
        }
    }
}
```

**Question 4:** Given the Loan class below. Modify the Loan class to throw IllegalArgumentException if the loan amount, interest rate or number of years is less than or equal to zero.

**Answer:**
```java
package loan;

import java.util.Date;

public class Loan {
    private double annualInterestRate;
    private int numberOfYears;
    private double loanAmount;
    private java.util.Date loanDate;
    
    public Loan() {
        this(2.5, 1, 1000);
    }
    
    public Loan(double annualInterestRate, int numberOfYears, double loanAmount) {
        if (annualInterestRate <= 0) {
            throw new IllegalArgumentException("Interest rate must be positive");
        }
        if (numberOfYears <= 0) {
            throw new IllegalArgumentException("Number of years must be positive");
        }
        if (loanAmount <= 0) {
            throw new IllegalArgumentException("Loan amount must be positive");
        }
        
        this.annualInterestRate = annualInterestRate;
        this.numberOfYears = numberOfYears;
        this.loanAmount = loanAmount;
        this.loanDate = new java.util.Date();
    }
    
    public double getAnnualInterestRate() { return annualInterestRate; }
    public void setAnnualInterestRate(double annualInterestRate) {
        if (annualInterestRate <= 0)
            throw new IllegalArgumentException("Interest rate must be positive");
        this.annualInterestRate = annualInterestRate;
    }
    
    public int getNumberOfYears() { return numberOfYears; }
    public void setNumberOfYears(int numberOfYears) {
        if (numberOfYears <= 0)
            throw new IllegalArgumentException("Number of years must be positive");
        this.numberOfYears = numberOfYears;
    }
    
    public double getLoanAmount() { return loanAmount; }
    public void setLoanAmount(double loanAmount) {
        if (loanAmount <= 0)
            throw new IllegalArgumentException("Loan amount must be positive");
        this.loanAmount = loanAmount;
    }
    
    public java.util.Date getLoanDate() { return loanDate; }
    
    public double monthlyPayment() {
        double monthlyRate = annualInterestRate / 1200;
        return loanAmount * monthlyRate / (1 - Math.pow(1 + monthlyRate, -numberOfYears * 12));
    }
    
    public double totalPayment() {
        return monthlyPayment() * numberOfYears * 12;
    }
}
```

---

## Lab 10 – Object Input/Output

### Exercise:

**Question 1:** Write a program to create a file named binaryint.dat if it does not exist. If it exists, append new data to it. Write one hundred integers created randomly into the file using binary I/O.

**Answer:**
```java
import java.io.*;
import java.util.Random;

public class WriteBinaryInt {
    public static void main(String[] args) {
        Random random = new Random();
        
        try (DataOutputStream output = new DataOutputStream(new FileOutputStream("binaryint.dat", true))) {
            for (int i = 0; i < 100; i++) {
                output.writeInt(random.nextInt(1000));
            }
        } catch (IOException e) {
            System.out.println("Error writing to file");
        }
    }
}
```

**Question 2:** Suppose a binary data file created in Q1 (binaryint.dat). Write a program to find the total of integers.

**Answer:**
```java
import java.io.*;

public class ReadBinaryInt {
    public static void main(String[] args) {
        try (DataInputStream input = new DataInputStream(new FileInputStream("binaryint.dat"))) {
            long sum = 0;
            while (input.available() >= 4) {
                sum += input.readInt();
            }
            System.out.println("Sum of integers: " + sum);
        } catch (IOException e) {
            System.out.println("Error reading from file");
        }
    }
}
```

**Question 3:** Write a program that stores an array of five int values 1, 2, 3, 4, and 5, a Date object for current time, and the double value 5.5 into the file named objfile.dat.

**Answer:**
```java
import java.io.*;
import java.util.Date;

public class WriteMixedObjects {
    public static void main(String[] args) {
        int[] ints = {1, 2, 3, 4, 5};
        Date date = new Date();
        double value = 5.5;
        
        try (ObjectOutputStream output = new ObjectOutputStream(new FileOutputStream("objfile.dat"))) {
            output.writeObject(ints);
            output.writeObject(date);
            output.writeDouble(value);
        } catch (IOException e) {
            System.out.println("Error writing to file");
        }
    }
}
```

**Question 4:** Given a Loan.java class. Rewrite the Loan class to implement Serializable. Write a program that creates five Loan objects and stores them in a file named loanobj.dat.

**Answer:**
```java
package loan;

import java.io.Serializable;
import java.util.Date;

public class Loan implements Serializable {
    private static final long serialVersionUID = 1L;
    private double annualInterestRate;
    private int numberOfYears;
    private double loanAmount;
    private transient Date loanDate; // transient won't be serialized
    
    public Loan(double annualInterestRate, int numberOfYears, double loanAmount) {
        this.annualInterestRate = annualInterestRate;
        this.numberOfYears = numberOfYears;
        this.loanAmount = loanAmount;
        this.loanDate = new Date();
    }
    
    // Getters and setters...
    public double getAnnualInterestRate() { return annualInterestRate; }
    public int getNumberOfYears() { return numberOfYears; }
    public double getLoanAmount() { return loanAmount; }
    public Date getLoanDate() { return loanDate; }
}
```

```java
import java.io.*;
import loan.Loan;

public class StoreLoanObjects {
    public static void main(String[] args) {
        Loan[] loans = {
            new Loan(3.5, 5, 100000),
            new Loan(4.0, 10, 200000),
            new Loan(2.5, 3, 50000),
            new Loan(5.0, 15, 300000),
            new Loan(3.0, 7, 150000)
        };
        
        try (ObjectOutputStream output = new ObjectOutputStream(new FileOutputStream("loanobj.dat"))) {
            output.writeObject(loans);
        } catch (IOException e) {
            System.out.println("Error writing to file");
        }
    }
}
```

---

## Lab 11 – Coursework Discussion

**Discussion:**

**Object oriented concepts:**
- **Object/Class** – Java class for business domain and object instantiation
- **Inheritance** – general class to specific class
- **Encapsulation** – Data or operation hiding ie., private keyword and get/set methods
- **Abstraction** – abstract class and abstract methods to be implemented by the subclasses.
- **Polymorphism** – overriding and overloading methods

**UML diagram:**
- **Use case diagram** – actors, user-case, system boundary, association <<include>> or <<extend>>
- **Class diagram** demonstrating the object oriented concepts – Logical class (single responsibility principle) according to business domain, class relationships (association, generalisation, aggreggation or composition, realisation, dependency), data properties and operations in the class. Note: class diagram is developed in line with application design in relation to software implementation.

### 1. Object/Class

**Question:** What is a class and what is an object?

**Answer:**
- **Class**: Blueprint or template for creating objects with similar properties and behaviors
- **Object**: Instance of a class with specific values for its attributes
- **Business Domain Example**: `Customer` class in banking system, `Product` class in e-commerce

```java
// Class definition
public class Customer {
    private String customerId;
    private String name;
    private String email;
    
    // Constructor
    public Customer(String customerId, String name, String email) {
        this.customerId = customerId;
        this.name = name;
        this.email = email;
    }
}

// Object instantiation
Customer customer1 = new Customer("C001", "John Doe", "john@email.com");
```

### 2. Inheritance

**Question:** What is inheritance and how is it implemented in Java?

**Answer:**
- **Concept**: Creating new classes from existing classes, inheriting attributes and methods
- **Purpose**: Code reuse, establishing "is-a" relationship
- **Example**: `Vehicle` (general) → `Car`, `Truck`, `Motorcycle` (specific)

```java
// Base class
public class Employee {
    protected String name;
    protected double salary;
    
    public Employee(String name, double salary) {
        this.name = name;
        this.salary = salary;
    }
}

// Subclass
public class Manager extends Employee {
    private double bonus;
    
    public Manager(String name, double salary, double bonus) {
        super(name, salary);
        this.bonus = bonus;
    }
    
    public double getTotalSalary() {
        return salary + bonus;
    }
}
```

### 3. Encapsulation

**Question:** What is encapsulation and why is it important?

**Answer:**
- **Concept**: Hiding internal state and requiring interaction through methods
- **Purpose**: Data protection, maintainability, flexibility
- **Implementation**: Private fields, public getters/setters

```java
public class BankAccount {
    private double balance; // Hidden state
    
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        }
    }
    
    public void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
        }
    }
    
    public double getBalance() {
        return balance;
    }
}
```

### 4. Abstraction

**Question:** What is abstraction and how is it implemented in Java?

**Answer:**
- **Concept**: Hiding complex implementation details and showing only necessary features
- **Purpose**: Simplify code, focus on what an object does rather than how
- **Implementation**: Abstract classes, interfaces

```java
public abstract class Shape {
    protected String color;
    
    public abstract double calculateArea(); // Abstract method
    
    public void display() {
        System.out.println("This is a shape");
    }
}

public class Circle extends Shape {
    private double radius;
    
    public Circle(double radius) {
        this.radius = radius;
    }
    
    @Override
    public double calculateArea() {
        return Math.PI * radius * radius;
    }
}
```

### 5. Polymorphism

**Question:** What is polymorphism and what are the two types?

**Answer:**
- **Concept**: Same method name, different behaviors based on object type
- **Types**: 
  - **Overloading**: Same method name, different parameters (compile-time)
  - **Overriding**: Subclass provides specific implementation (runtime)

```java
// Overloading
public class Calculator {
    public int add(int a, int b) { return a + b; }
    public double add(double a, double b) { return a + b; }
}

// Overriding
public class Animal {
    public void makeSound() {
        System.out.println("Some sound");
    }
}

public class Dog extends Animal {
    @Override
    public void makeSound() {
        System.out.println("Woof!");
    }
}
```

### UML Diagram Elements

#### Use Case Diagram Components

| Element | Symbol | Description |
|---------|--------|-------------|
| Actor | Stick figure | External entity interacting with system |
| Use Case | Oval | Specific functionality or goal |
| System Boundary | Rectangle | Defines system scope |
| Association | Line | Relationship between actor and use case |
| <<include>> | Dashed arrow | Mandatory inclusion of use case |
| <<extend>> | Dashed arrow | Optional extension under conditions |

#### Class Diagram Components

**Relationships:**

1. **Association**: Basic relationship between classes
   - `Customer` has a `Address`

2. **Generalization (Inheritance)**: "is-a" relationship
   - `Student` is a `Person`

3. **Aggregation**: "has-a" relationship, weak ownership
   - `Department` has `Employee`s (employees can exist independently)

4. **Composition**: "has-a" relationship, strong ownership
   - `Order` has `OrderItem`s (items cannot exist without order)

5. **Realization**: Implements interface
   - `Circle` implements `Shape` interface

6. **Dependency**: Uses another class
   - `OrderProcessor` uses `PaymentGateway`

**Class Diagram Example:**

```
┌─────────────────┐
│    Person       │
├─────────────────┤
│ - name: String  │
│ - email: String │
├─────────────────┤
│ + getName()     │
│ + setEmail()    │
└────────┬────────┘
         │
         │◄───┐
         │    │
    ┌────┴────┐
    │         │
┌───▼──────┐ ┌▼──────────────┐
│  Student │ │    Employee    │
├──────────┤ ├───────────────┤
│ - status │ │ - salary      │
│ - gpa    │ │ - hireDate    │
├──────────┤ ├───────────────┤
│+ study() │ │ + work()      │
└──────────┘ └───────────────┘
```

**Design Principles:**
- **Single Responsibility Principle**: Each class has one reason to change
- **Business Domain Alignment**: Classes should reflect real-world entities
- **Logical Separation**: Separate concerns into appropriate classes

---

*End of Tutorial Lab Questions and Answers*
