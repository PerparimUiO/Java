
#### P9.1 Add a class NumericQuestion to the question hierarchy of Section 9.1. If the response and the expected answer differ by no more than 0.01, then accept the response as correct.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class NumericQuestion extends Question {
    private double answer;

    public void setAnswer(double correctResponse) {
        answer = correctResponse;
    }

    public boolean checkAnswer(String response) {
        double responseDouble = Double.parseDouble(response);
        return Math.abs(responseDouble - answer) <= 0.01;
    }
}
```

</p>
</details>

####  P9.2  Add a class FillInQuestion to the question hierarchy of Section 9.1. Such a question is  constructed with a string that contains the answer, surrounded by _ _ , for exam­ple,  "The inventor of Java was _James Gosling_" . The question should be displayed as  The inventor of Java was _____

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;

public class FillInQuestion extends Question {
    public void setText(String questionText) {
        Scanner parser = new Scanner(questionText);
        parser.useDelimiter("_");
        String question = parser.next();
        String answer = parser.next();
        question += "_____" + parser.next();
        parser.close();

        super.setText(question);
        super.setAnswer(answer);
    }
}

```

</p>
</details>

#### /*Modify the checkAnswer method of the Question class so that it does not take into
account different spaces or upper/lowercase characters. For example, the response
"JAMES gosling" should match an answer of "James Gosling" .*/

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P9_03 {
    public class Question {
        private String text;
        private String answer;

        public Question() {
            text = "";
            answer = "";
        }

        public void setText(String questionText) {
            text = questionText;
        }

        public void setAnswer(String correctResponse) {
            answer = correctResponse;
        }

        public boolean checkAnswer(String response) {
            return response.toLowerCase().equals(answer.toLowerCase());
        }

        public void display() {
            System.out.println(text);
        }
    }
}

```

</p>
</details>

#### P9.4    Add a class AnyCorrectChoiceQuestion to the question hierarchy of Section 9.1 that allows multiple correct choices. The respondent should provide any one of the correct choices. The answer string should contain all of the correct choices, separated by spaces. Provide instructions in the question text.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class AnyCorrectChoiceQuestion extends ChoiceQuestion {
    private String allAnswers;

    public AnyCorrectChoiceQuestion() {
        super();
    }

    public void setAnswer(String correctResponse) {
        allAnswers = correctResponse + " " + allAnswers;
    }

    public boolean checkAnswer(String response) {
        return allAnswers.contains(response);
    }
    
    public void display() {
        super.display();
    }
}

```

</p>
</details>

#### Add a class MultiChoiceQuestion to the question hierarchy of Section 9.1 that allows  multiple correct choices. The respondent should provide all correct choices, separated by spaces. Provide instructions in the question text.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.ArrayList;
import java.util.Scanner;

public class MultiChoiceQuestion extends ChoiceQuestion {
    private ArrayList<String> allAnswers;

    public MultiChoiceQuestion() {
        super();
        this.allAnswers = new ArrayList<String>();
    }

    public void setAnswer(String correctResponse) {
        this.allAnswers.add(correctResponse);
    }

    public boolean checkAnswer(String response) {
        Scanner parser = new Scanner(response);
        ArrayList<String> correctAnswersSeen = new ArrayList<String>();
        int totalAnswers = 0;
        while (parser.hasNext()) {
            String answer = parser.next();
            if (this.allAnswers.contains(answer) && !correctAnswersSeen.contains(answer)) {
                correctAnswersSeen.add(answer);
            }
            totalAnswers += 1;
        parser.close();
        }
        return correctAnswersSeen.size() == this.allAnswers.size() && totalAnswers == allAnswers.size();
    }
    
    public void display() {
        super.display();
        System.out.println("Note: there are several correct answers. List all of them separated by spaces");
    }
}

```

</p>
</details>

#### P9.8    Implement a superclass Person . Make two classes, Student and Instructor , that inherit from Person . A person has a name and a year of birth. A student has a major, and an instructor has a salary. Write the class declarations, the constructors, and the methods toString for all classes. Supply a test program that tests these classes and methods.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class Person {
    private String name;
    private int birthYear;

    public Person(String name, int birthYear) {
        this.name = name;
        this.birthYear = birthYear;
    }

    public String getName() {
        return this.name;
    }

    public int getBirthYear() {
        return this.birthYear;
    }
}

```

</p>
</details>

#### P9.8    Implement a superclass Person . Make two classes, Student and Instructor,that inherit from Person . A person has a name and a year of birth. A student has a major, and an instructor has a salary. Write the class declarations, the constructors, and the methods toString for all classes. Supply a test program that tests these classes and methods.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class Student extends Person {
    private String major;

    public Student(String name, int birthYear, String major) {
        super(name, birthYear);
        this.major = major;
    }

    public String getMajor() {
        return this.major;
    }
}

public class Instructor extends Person {
    private double salary;

    public Instructor(String name, int birthYear, double salary) {
        super(name, birthYear);
        this.salary = salary;
    }

    public double getSalary() {
        return this.salary;
    }
}


```

</p>
</details>

#### Make a class Employee with a name and salary. Make a class Manager inherit from Employee . Add an instance variable, named department , of type String . Supply a method toString that prints the manager’s name, department, and salary. Make a class Executive inherit from Manager . Supply appropriate toString methods for all classes. Supply a test program that tests these classes and methods.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class Employee {
    private String name;
    private double salary;
    
    public Employee(String name, double salary) {
        this.name = name;
        this.salary = salary;
    }
    
    public String getName() {
        return this.name;
    }
    
    public double getSalary() {
        return this.salary;
    }
}

```

</p>
</details>

#### Make a class Employee with a name and salary. Make a class Manager inherit from Employee . Add an instance variable, named department , of type String . Supply a method toString that prints the manager’s name, department, and salary. Make a class Executive inherit from Manager . Supply appropriate toString methods for all classes. Supply a test program that tests these classes and methods.
<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class Manager extends Employee {
    private String department;
    
    public Manager(String name, double salary, String department) {
        super(name, salary);
        this.department = department;
    }
    
    public String getDepartment() {
        return this.department;
    }
}

```

</p>
</details>

#### 
    P9.10 The Rectangle class of the standard Java library does not supply a method to com­
    pute the area or the perimeter of a rectangle. Provide a subclass BetterRectangle of the
    Rectangle class that has getPerimeter and getArea methods. Do not add any instance
    variables. In the constructor, call the setLocation and setSize methods of the Rectangle
    class. Provide a program that tests the methods that you supplied.

    P9.11    Repeat Exercise P9.10, but in the BetterRectangle constructor, invoke the superclass
    constructor.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.awt.Rectangle;
public class BetterRectangle extends Rectangle {
    public BetterRectangle(int x, int y, int width, int height) {
        super(x, y, width, height);
    }
    
    /*public BetterRectangle(int x, int y, int width, int height) {
        super.setLocation(x, y);
        super.setSize(width, height);
    }*/
    public double getPerimeter() {
        return super.getHeight() * 2 + super.getWidth() * 2;
    }
    
    public double getArea() {
        return super.getHeight() * super.getWidth();
    }
}
```

</p>
</details>

####  P9.12    A labeled point has x- and y-coordinates and a string label. Provide a class Labeled­Point with a constructor LabeledPoint(int x, int y, String label) and a toString method that displays x, y and label

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class LabeledPoint {
    private int x;
    private int y;
    private String label;

    public LabeledPoint(int x, int y, String label) {
        this.x = x;
        this.y = y;
        this.label = label;
    }

    public String toString() {
        return String.format("%s [x=%d, y=%d, label=%s]", getClass().getName(), this.x, this.y, this.label);
    }
}

```

</p>
</details>

#### P9.15    A person has a name and a birth year. Use the average method in Section 9.6 to process a collection of Person objects.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class PersonsAverage {
    public static double average(Person[] objects) {
        double sum = 0;
        for (Person person : objects) {
            sum += person.getBirthYear();
        }
        return sum / objects.length;
    }
}

```

</p>
</details>

#### Declare an interface Filter as follows:
     public interface Filter
     {
     boolean accept(Object x);
     }
 Write a method
 
     public static ArrayList<Object> collectAll(ArrayList<Object> objects, Filter f)
  
that returns all objects in the objects array that are accepted by the given filter.Provide a class ShortWordFilter whose filter method accepts all strings of length < 5.  Then write a program that reads all words from System.in , puts them into an `ArrayList<Object>`, calls collectAll , and prints a list of the short words.*/

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.ArrayList;
public class ShortWordFilter implements Filter {
    public boolean accept(Object x) {
        return x.toString().length() < 5;
    }

    public static ArrayList<Object> collectAll(ArrayList<Object> objects, Filter f) {
        ArrayList<Object> collected = new ArrayList<Object>();
        for (Object object : collected) {
            if (f.accept(object)) {
                collected.add(object);
            }
        }
        return collected;
    }
}

```

</p>
</details>


#### Business P9.21   Implement a superclass Appointment and subclasses Onetime , Daily , and Monthly.  An appointment has a description (for example, “see the dentist”) and a date.   Write a method`occursOn(int year, int month, int day)`that checks whether the appointment occurs on  that date. For example, for a monthly appointment, you must check whether the day of the month   matches. Then fill an array of Appointment objects with a mixture of appointments.  Have the user enter a date and print out all appointments that occur on that date.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.text.DateFormat;
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;

public class Appointment {
    private String description;
    private Date date;

    public Appointment(String description, int year, int month, int day) throws ParseException {
        this.description = description;
        DateFormat dateFormatter = new SimpleDateFormat(String.format("yyyy-MM-dd"));
        this.date = dateFormatter.parse(String.format("%d-%d-%d", year, month, day));
    }

    public boolean occursOn(int year, int month, int day) throws ParseException {
        DateFormat dateFormatter = new SimpleDateFormat(String.format("yyyy-MM-dd"));
        Date checkedDate = dateFormatter.parse(String.format("%d-%d-%d", year, month, day));
        return checkedDate.equals(this.date);
    }

    public void print() {
        System.out.println(String.format("Appointment: %s\nDate: %s", this.description, this.date.toString()));
    }
    
    public Date getDate() {
        return this.date;
    }
}

// Onetime Class

import java.text.ParseException;

public class Onetime extends Appointment {
    public Onetime(String description, int year, int month, int day) throws ParseException {
        super(description, year, month, day);
    }
}

// Daily Class
import java.text.ParseException;

public class Daily extends Appointment {
    public Daily(String description, int year, int month, int day) throws ParseException {
        super(description, year, month, day);
    }
}

// Monthly Class
import java.text.ParseException;

public class Monthly extends Appointment {
    public Monthly(String description, int year, int month, int day) throws ParseException {
        super(description, year, month, day);
    }
}

```

</p>
</details>

#### 

     P9.18   The System.out.printf method has predefined formats for printing integers, floating-
     point numbers, and other data types. But it is also extensible. If you use the S for­mat,
     you can print any class that implements the Formattable interface. That interface has a
     single method:
     void formatTo(Formatter formatter, int flags, int width, int precision)
     In this exercise, you should make the BankAccount class implement the Formattable
     interface. Ignore the flags and precision and simply format the bank balance, using
     the given width. In order to achieve this task, you need to get an Appendable reference
     like this:
     Appendable a = formatter.out();
     Appendable is another interface with a method
     void append(CharSequence sequence)
     CharSequence is yet another interface that is implemented by (among others) the String
     class. Construct a string by first converting the bank balance into a string and then
     padding it with spaces so that it has the desired width. Pass that string to the append
     method.

     ••• P9.19    Enhance the formatTo method of Exercise P9.18 by taking into account the precision.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.io.IOException;
import java.util.Formattable;
import java.util.Formatter;
import java.util.Scanner;


public class BankAccount implements Formattable {
    private double balance;

    public BankAccount(double balance) {
        this.balance = balance;
    }

    public BankAccount() {
        this(0);
    }

    public void deposit(double amount) {
        if (amount > 0) {
            this.balance += amount;
        } else {
            throw new IllegalArgumentException("Deposit amount should be positive and greater than 0.");
        }
    }

    public void withdraw(double amount) {
        if (amount > 0 && this.balance - amount >= 0) {
            this.balance -= amount;
        } else if (amount < 0) {
            throw new IllegalArgumentException("Withdraw amount should be positive and greater than 0.");
        } else {
            System.out.println("Error: Withdraw amount exceeds available funds.");
        }
    }

    @Override
    public void formatTo(Formatter formatter, int flags, int width, int precision) {
        Appendable a = formatter.out();
        // round appropriately based on precision
        double rounded = Math.round(balance * Math.pow(10, precision)) / Math.pow(10, precision);
        String balanceString = Double.toString(rounded);
        // add trailing 0s if necessary
        Scanner getDecimal = new Scanner(balanceString);
        getDecimal.useDelimiter("\\.");
        String digitsPart = getDecimal.next();
        String decimalPart = getDecimal.next();
        getDecimal.close();
        if (precision == 0) {
            // remove any decimal part if the precision is 0
            balanceString = digitsPart;
        } else {
            // add remaining extra zeros
            int extraZeros = decimalPart.length();
            while (extraZeros < precision) {
                balanceString = balanceString + "0";
                extraZeros++;
            }
        }
        while (width > balanceString.length()) {
            balanceString = " " + balanceString;
        }
        try {
            a.append(balanceString);
        } catch (IOException e) {
            System.out.println("Error!");
        }
    }

}

```

</p>
</details>
