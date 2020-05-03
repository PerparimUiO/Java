#### We want to add a button to the tally counter in Section 8.2 that allows an operator to undo an accidental button click. Provide a method

    public void undo()
    
that simulates such a button. As an added precaution, make sure that the operator cannot click the undo button more often than the count button.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P8_01 {
    private int value;

    public int getValue() {
        return value;
    }

    public void count() {
        value = value + 1;
    }

    public void reset() {
        value = 0;
    }

    public void undo() {
        value -= 1;
    }
}

```

</p>
</details>

#### Simulate a tally counter that can be used to admit a limited number of people. First, the limit is set with a call
    public void setLimit(int maximum)
If the count button was clicked more often than the limit, simulate an alarm by printing out a message “Limit exceeded”.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P8_02 {
    private int value;
    private int maximum;

    public int getValue() {
        return value;
    }

    public void count() {
        if (value + 1 > maximum) {
            System.out.println("Limit exceeded");
        } else {
            value = value + 1;
        }
    }

    public void reset() {
        value = 0;
    }

    public void undo() {
        value -= 1;
    }

    public void setLimit(int maximum) {
        this.maximum = maximum;
    }
}

```

</p>
</details>

####  Reimplement the Menu class so that it stores all menu items in one long string.
    Hint: Keep a separate counter for the number of options. When a new option is added, append the option count, the option, and a newline character.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P8_03 {
    private String options;
    private int optionsCount = 0;
    
    public P8_03() {
        this.options = "";
    }
    
    public void addOption(String option) {
        this.optionsCount += 1;
        this.options += String.format("%s%d)%s\n", this.options, this.optionsCount, option);
    }
    
    public void getOptions() {
        System.out.println(options);
    }
    
    public void getInput() {
        Scanner console = new Scanner(System.in);
        int choice;
        do {
            System.out.print("Choice: ");
            choice = console.nextInt();
        } while (choice < 1 || choice > optionsCount);
        console.close();
    }
}

```

</p>
</details>

#### Implement a class Address . An address has a house number, a street, an optional apartment number,  a city, a state, and a postal code. Supply two constructors: one with an apartment number and one without. Supply a print method that prints the address with the street on one line and the city,  state, and zip code on the next line. Supply a method public boolean comesBefore(Address other)  that tests whether this address comes before another when the addresses are compared by postal code.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P8_04 {
    private int houseNumber;
    private String street;
    private int apartmentNumber;
    private String city;
    private int postalCode;

    public P8_04(int houseNumber, String street, int apartmentNumber, String city, int postalCode) {
        this.houseNumber = houseNumber;
        this.street = street;
        this.apartmentNumber = apartmentNumber;
        this.city = city;
        this.postalCode = postalCode;
    }

    public P8_04(int houseNumber, String street, String city, int postalCode) {
        this.houseNumber = houseNumber;
        this.street = street;
        this.city = city;
        this.postalCode = postalCode;
    }

    public void print() {
        System.out.println(String.format("%s, %s\n%s, %s, %d", street, 
                (apartmentNumber != 0)? apartmentNumber : houseNumber, city, postalCode));
    }
    
    public boolean comesBefore(P8_04 other) {
        return this.postalCode > other.postalCode;
    }
}

```

</p>
</details>

#### Implement a class SodaCan with methods getSurfaceArea() and 
    getVolume() 
In the constructor, supply the height and radius of the can.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P8_05 {
    private double height;
    private double radius;

    public P8_05(double height, double radius) {
        this.height = height;
        this.radius = radius;
    }

    public double getSurface() {
        return 2 * Math.PI * this.radius * this.radius + 2 * Math.PI * this.radius * this.height;
    }

    public double getVolume() {
        return Math.PI * this.radius * this.radius * 2 * this.height;
    }
}

```

</p>
</details>

#### Implement a class Car with the following properties. A car has a certain fuel efficiency (measured in miles/gallon) and a certain amount of fuel in the gas tank.  The efficiency is specified in the constructor, and the initial fuel level is 0. Supply a method drive that simulates driving the car for a certain distance,reducing the fuel level in the gas tank, and methods getGas- Level ,  to return the current fuel level, and addGas , to tank up. Sample usage:
    Car myHybrid = new Car(50); // 50 miles per gallon
    myHybrid.addGas(20); // Tank 20 gallons
    myHybrid.drive(100); // Drive 100 miles
    System.out.println(myHybrid.getGasLevel()); // Print fuel remaining

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P8_06 {
    private final int INITIAL_FUEL = 0;
    private double fuel;
    private double fuelEfficiency;
    
    public P8_06(double fuelEfficiency) {
        this.fuelEfficiency = fuelEfficiency;
        this.fuel = this.INITIAL_FUEL;
    }
    
    public void addGas(double amount) {
        this.fuel += amount;
    }
    
    public void drive(double distance) {
        this.fuel -= distance * this.fuelEfficiency;
    }
    
    public void printFuel() {
        System.out.println(this.fuel);
    }
}

```

</p>
</details>

#### Implement a class Student . For the purpose of this exercise, a student has a name and a total quiz score. Supply an appropriate constructor and methods:
      getName() ,
      addQuiz(int score) , 
      getTotalScore() , 
      and getAverageScore() . 
To compute the latter, you also need to store the number of quizzes that the student took.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P8_07 {
    private String name;
    private double totalScore;
    private int scoreCount;
    
    public P8_07(String name) {
        this.name = name;
    }
    
    public String getName() {
        return this.name;
    }
    
    public void addQuiz(double score) {
        this.totalScore += score;
        this.scoreCount += 1;
    }
    
    public double getTotalScore() {
        return this.totalScore;
    }
    
    public double getAverageScore() {
        return this.totalScore / this.scoreCount;
    }
}

```

</p>
</details>

#### Modify the Student class of Exercise P8.7 to compute grade point averages. Methods are needed to add a grade and get the current GPA. Specify grades as elements of a class Grade . Supply a constructor that constructs a grade from a string, such as "B+" . You will also need a method that translates grades into their numeric values (for example, "B+" becomes 3.3).

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P8_08 {
    private String name;
    private double totalScore;
    private int scoreCount;
    
    public P8_08(String name) {
        this.name = name;
    }
    
    public String getName() {
        return this.name;
    }
    
    public void addQuiz(double score) {
        this.totalScore += score;
        this.scoreCount += 1;
    }
    
    public void addQuiz(Grade grade) {
        this.totalScore += grade.getScore();
        this.scoreCount += 1;
    }
    
    public double getTotalScore() {
        return this.totalScore;
    }
    
    public double getAverageScore() {
        return this.totalScore / this.scoreCount;
    }
}

```

</p>
</details>

#### Declare a class ComboLock that works like the combination lock in a gym locker, as shown here. The lock is constructed with a combination—three numbers between 0 and 39. The reset method resets the dial so that it points to 0. The turnLeft and turnRight methods turn the dial by a given number of ticks to the left or right. The open method attempts to open the lock. The lock opens if the user first turned it right to the first number in the combina- tion, then left to the second, and then right to the third.
    public class ComboLock
    {
       . . .
       public ComboLock(int secret1, int secret2, int secret3) { . . . }
       public void reset() { . . . }
       public void turnLeft(int ticks) { . . . }
       public void turnRight(int ticks) { . . . }
       public boolean open() { . . . }
    }

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P8_09 {
    private int secret1;
    private int secret2;
    private int secret3;
    private int dial;

    public P8_09(int secret1, int secret2, int secret3) {
        this.secret1 = secret1;
        this.secret2 = secret2;
        this.secret3 = secret3;
    }

    public void reset() {
        this.dial = 0;
    }

    public void turnLeft(int ticks) {
        this.scroll(-ticks);
        if (this.secret1 == -1) {
            if (this.shouldUnlock(secret2) == true) {
                System.out.println("Secret 2 unlocked");
            }
        }
    }

    public void turnRight(int ticks) {
        this.scroll(ticks);
        if (this.shouldUnlock(secret1) == true) {
            System.out.println("Secret 1 unlocked");
            if (this.shouldUnlock(secret2) == true) {
                if (this.shouldUnlock(secret3) == true) {
                    System.out.println("Combo lock unlocked");
                }
            }
        }
    }

    public void scroll(int ticks) {
        if (this.dial + ticks > 39) {
            if (ticks >= 39) {
                this.dial += ticks - 39;
            } else if (this.dial >= 39) {
            }
        } else if (this.dial + ticks < 0) {
            this.dial += 40 + ticks;
            this.dial += ticks - 40;
        } else {
            this.dial += ticks;
        }
    }

    public boolean shouldUnlock(int secret) {
        if (this.dial == secret) {
            secret = -1;
            return true;
        } else {
            return false;
        }
    }
}

```

</p>
</details>

#### Implement a VotingMachine class that can be used for a simple election. Have methods to clear the machine state, to vote for a Democrat, to vote for a Republican, and to get the tallies for both parties.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P8_10 {
    private int democratsVotes;
    private int republicanVotes;

    public void clear() {
        this.democratsVotes = 0;
        this.republicanVotes = 0;
    }

    public void voteDemocrats() {
        this.democratsVotes += 1;
    }

    public void voteRepublicans() {
        this.republicanVotes += 1;
    }

    public void showVotes() {
        System.out.println("Democrats:" + this.democratsVotes);
        System.out.println("Republicans: " + this.republicanVotes);
    }
}

```

</p>
</details>

#### Provide a class for authoring a simple letter. In the constructor, supply the names of the sender and the recipient:
    public Letter(String from, String to)
Supply a method

    public void addLine(String line)
to add a line of text to the body of the letter. Supply a method

    public String getText()
that returns the entire text of the letter. The text has the form:

    Dear recipient name :
    blank line
    first line of the body
    second line of the body
    . . .
    last line of the body
    blank line
    Sincerely,
    blank line
    sender name
Also supply a main method that prints this letter.

    Dear John:
    I am sorry we must part.
    I wish you all the best.
    Sincerely,
    Mary
Construct an object of the Letter class and call addLine twice.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P8_11 {
    private String sender;
    private String recipient;
    private StringBuilder content;
    private String header;
    private String footer;

    public P8_11(String from, String to) {
        this.sender = from;
        this.recipient = to;
        this.header = String.format("Dear %s:\n", sender);
        this.footer = String.format("Sincerely,\n%s", recipient);
        this.content = new StringBuilder();
    }

    public void addLine(String line) {
        this.content.append(String.format("%s\n", line));
    }

    public String getText() {
        String output = this.header + this.content.toString() + this.footer;
        return output;
    }
}

```

</p>
</details>

#### Write a class Bug that models a bug moving along a horizontal line. The bug moves either to the right or left. Initially, the bug moves to the right, but it can turn to change its direction. In each move, its position changes by one unit in the current direction. Provide a constructor
    public Bug(int initialPosition)
    and methods
    •    public void turn()
    •    public void move()
    •    public int getPosition()
Sample usage:

    Bug bugsy = new Bug(10);
    bugsy.move(); // Now the position is 11
    bugsy.turn();
    bugsy.move(); // Now the position is 10
Your main method should construct a bug, make it move and turn a few times, and print the actual and expected positions. 

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P8_12 {
    private int position;
    private boolean moveRight;

    public P8_12(int initialPosition) {
        this.position = initialPosition;
        this.moveRight = true;
    }

    public void turn() {
        this.moveRight = false;
    }

    public void move() {
        if (moveRight) {
            this.position += 1;
        } else {
            this.position -= 1;
        }
    }

    public int getPosition() {
        return this.position;
    }
}

```

</p>
</details>

#### Implement a class Moth that models a moth flying in a straight line. The moth has a position, the distance from a fixed origin. When the moth moves toward a point of light, its new position is halfway between its old position and the position of the light source. Supply a constructor
    public Moth(double initialPosition)
and methods

    •    public void moveToLight(double lightPosition)
    •    public void getPosition()
Your main method should construct a moth, move it toward a couple of light sources, and check that the moth’s position is as expected.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P8_13 {
    private double position;

    public P8_13(double initialPosition) {
        this.position = initialPosition;
    }
    
    public double getPosition() {
        return this.position;
    }
    
    public void moveToLight(double lightPosition) {
        this.position = (this.position + lightPosition) / 2;
    }
}

```

</p>
</details>

#### Reimplement the CashRegister class so that it keeps track of the price of each added  item in an ArrayList<Double>.  Remove the itemCount and totalPrice instance variables.Reimplement the clear , addItem , getTotal , and getCount methods. Add a method  displayAll that displays the prices of all items in the current sale.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.ArrayList;

public class P8_16 {
    private ArrayList<Double> items;

    public P8_16() {
        this.items = new ArrayList<Double>();
    }

    public void clear() {
        this.items.clear();
    }

    public void addItem(double itemPrice) {
        this.items.add(itemPrice);
    }

    public double getTotal() {
        double total = 0;
        for (double itemPrice : this.items) {
            total += itemPrice;
        }
        return total;
    }

    public double getCount() {
        return items.size();
    }

    public void displayAll() {
        for (double itemPrice : this.items) {
            System.out.println(itemPrice);
        }
    }
}

```

</p>
</details>

####  Reimplement the CashRegister class so that it keeps track of the total price as an integer:  the total cents of the price. For example, instead of storing 17.29, store the integer 1729.  Such an implementation is commonly used because it avoids the accumulation of roundoff errors.  Do not change the public interface of the class.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.ArrayList;
public class P8_17 {
    private ArrayList<Double> items;
    private int totalCents;

    public P8_17() {
        this.items = new ArrayList<Double>();
    }

    public void clear() {
        this.items.clear();
    }

    public void addItem(double itemPrice) {
        this.items.add(itemPrice * 100);
    }

    public double getTotal() {
        return totalCents / 100;
    }

    public double getCount() {
        return items.size();
    }

    public void displayAll() {
        for (double itemPrice : this.items) {
            System.out.println(itemPrice);
        }
    }
}

```

</p>
</details>

#### After closing time, the store manager would like to know how much business was transacted during the day. Modify the CashRegister class to enable this functionality. Supply methods getSalesTotal and getSalesCount to get the total amount of all sales and the number of sales. Supply a method resetSales that resets any counters and totals so that the next day’s sales start from zero.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.ArrayList;
public class P8_18 {
    private ArrayList<Double> items;
    private int totalCents;

    public P8_18() {
        this.items = new ArrayList<Double>();
    }

    public void clear() {
        this.items.clear();
    }

    public void addItem(double itemPrice) {
        this.items.add(itemPrice * 100);
    }

    public double getTotal() {
        return totalCents / 100;
    }

    public double getCount() {
        return items.size();
    }

    public void displayAll() {
        for (double itemPrice : this.items) {
            System.out.println(itemPrice);
        }
    }    
}
```

</p>
</details>

