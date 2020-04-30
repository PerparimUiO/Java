## Write a program that displays the dimensions of a letter­size (8.5 × 11 inch) sheet of paper in millimeters.There are 25.4 millimeters per inch. Use con stants and comments in your program. 

<details><summary>💾 Zgjidhje alternative </summary>
<p>
 
 ```java
 import java.util.Scanner;
public class P2_1 {
	public static void main(String[] args) {
		final double MILIMETERS_PER_INCH = 25.4;
		Scanner input = new Scanner(System.in);
		System.out.print("X: ");	
		double inch_dimensions_x = input.nextDouble();
		System.out.print("Y: ");
		double inch_dimensions_y = input.nextDouble();
		input.close();
		double milimeters_dimensions_x = inch_dimensions_x * MILIMETERS_PER_INCH;
		double milimeters_dimensions_y = inch_dimensions_y * MILIMETERS_PER_INCH;
		
		System.out.printf("Dimensions in milimeters: %.2f, %.2f", milimeters_dimensions_x, milimeters_dimensions_y);
	}
}

```
</p>
</details>

***

## Write a program that computes and displays the perimeter of a letter­size (8.5 × 11 inch) sheet of paper and the length of its diagonal.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P2_2 {
	public static void main(String[] args) {
		final double PAPER_WIDTH_INCHES = 8.5;
		final double PAPER_LENGTH_INCHES = 11.0;
		
		double perimeter = 2 * PAPER_LENGTH_INCHES + 2 * PAPER_WIDTH_INCHES;
		double diagonal = Math.sqrt(Math.pow(PAPER_WIDTH_INCHES, 2) + Math.pow(PAPER_LENGTH_INCHES, 2));
		System.out.printf("Perimeter: %.2f; Diagonal length: %.2f", perimeter, diagonal);
	}
}

```
</p>
</details>

***

## Write a program that reads a number and displays the square, cube, and fourth power. Use the  Math.pow method only for the fourth power.


<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P2_3 {
	public static void main(String[] args) {
		Scanner input = new Scanner(System.in);
		System.out.print("Number: ");
		double number = input.nextDouble();
		input.close();
		double square_number = number * number;
		double cube_number = square_number * number;
		double fourth_power_of_number = cube_number * number;
		
		System.out.printf("Square: %.2f, Cube: %.2f, Fourth power: %.2f", square_number, cube_number, fourth_power_of_number);
		
	}
}
```

</p>
</details>


***

## Write a program that prompts the user for two integers and then prints

 - `The sum`
 - `The difference`
 - `The product`
 - `The average`
 - `The distance (absolute value of the difference)`
 - `The maximum (the larger of the two)`
 - `The minimum (the smaller of the two)`
 
 💡 Hint: The max and min functions are declared in the Math class.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P2_4 {
	public static void main(String[] args) {
		Scanner input = new Scanner(System.in);
		System.out.print("Number a: ");
		double number_a = input.nextDouble();
		System.out.print("Number b: ");
		double number_b = input.nextDouble();
		input.close();
		double sum = number_a + number_b;
		double difference = number_a - number_b;
		double product = number_a * number_b;
		double average = (number_a + number_b) / 2;
		double distance = Math.abs(difference);
		double maximum = Math.max(number_a, number_b);
		double minimum = Math.min(number_a, number_b);
		System.out.printf("The sum: %.2f\n"
				+ 		  "The difference: %.2f\n"
				+         "The product: %.2f\n"
				+         "The average: %.2f\n"
				+         "The distance: %.2f\n"
				+         "The maximum: %.2f\n"
				+  		  "The minimum: %.2f", sum, difference, product, average, distance, maximum, minimum);
	}
}

```

</p>
</details>

***

## Enhance the output of P2_4.java so that the numbers are properly aligned.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P2_5 {
	public static void main(String[] args) {
		Scanner input = new Scanner(System.in);
		System.out.print("Number a: ");
		double number_a = input.nextDouble();
		System.out.print("Number b: ");
		double number_b = input.nextDouble();
		input.close();
		double sum = number_a + number_b;
		double difference = number_a - number_b;
		double product = number_a * number_b;
		double average = (number_a + number_b) / 2;
		double distance = Math.abs(difference);
		double maximum = Math.max(number_a, number_b);
		double minimum = Math.min(number_a, number_b);
		System.out.printf("The sum: %10.2f\n"
				+ 		  "The difference: %10.2f\n"
				+         "The product: %10.2f\n"
				+         "The average: %10.2f\n"
				+         "The distance: %10.2f\n"
				+         "The maximum: %10.2f\n"
				+  		  "The minimum: %10.2f", sum, difference, product, average, distance, maximum, minimum);
	}
}
```
</p>
</details>

***

## Write a program that prompts the user for a measurement in meters and then converts it to miles, feet, and inches.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P2_6 {
	public static void main(String[] args) {
		Scanner input = new Scanner(System.in);
		System.out.print("Measurement meters: ");
		double measurement_meters = input.nextDouble();
		input.close();
		double measurement_miles = measurement_meters * 0.000621371192;
		double measurement_feet = measurement_meters * 3.2808399;
		double measurement_inches = measurement_meters * 39.3700787;
		
		System.out.printf("Measurement miles: %.4f\n"
				+ 		  "Measurement feet: %.4f\n"
				+ 		  "Measurement inches: %.4f", 
		measurement_miles, measurement_feet, measurement_inches);
	}
}

```
</p>
</details>

***

## Write a program that prompts the user for a radius and then prints

- `The area and circumference of a circle with that radius`

- `The volume and surface area of a sphere with that radius`

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;

public class P2_7 {
	public static void main(String[] args) {
		Scanner input = new Scanner(System.in);
		System.out.print("Radius: ");
		double radius = input.nextDouble();
		input.close();
		System.out.println("Area of circle: " + (Math.PI * Math.pow(radius, 2)));
		System.out.println("Circumference of circle: " + (2 * Math.PI * radius));
		System.out.println("Volume of sphere: " + (4.0 / 3.0 * Math.PI * Math.pow(radius, 3)));
		System.out.println("Surface area of sphere: "+ (4.0 * Math.PI * Math.pow(radius, 2)));
	}
}

```

</p>
</details>

***

## Write a program that asks the user for the lengths of the sides of a rectangle. 
Then print:

- `The area and perimeter of the rectangle`

- `The length of the diagonal`

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P2_8 {
	public static void main(String[] args) {
		Scanner input = new Scanner(System.in);
		System.out.print("Side a: ");
		double side_a = input.nextDouble();
		System.out.print("Side b: ");
		double side_b = input.nextDouble();
		input.close();
		double area =  side_a * side_b;
		double perimeter = 	2 * (side_a + side_b);
		double diagonal = Math.sqrt(side_a * side_a + side_b * side_b);
		System.out.printf("Area: %.2f\nPerimeter: %.2f\nDiagonal length: %.2f", area, perimeter, diagonal);
	}
}

```
</p>
</details>

***

## Improve the program discussed in How To 2.1 to allow input of quarters in addition to bills

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P2_9 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        final int PENNIES_PER_DOLLAR = 100;
        final int PENNIES_PER_QUARTER = 25;
        System.out.print("Enter bill value (1 = $1 bill, 5 = $5 bill, etc.): ");
        int bill_value = input.nextInt();
        
        System.out.print("Enter quarter value (1 = $.25, 2 = $.50, etc.):");
        int quarter_value = input.nextInt();
        
        System.out.print("Enter item price in pennies: ");
        int item_price = input.nextInt();
        input.close();
        
        int amount_due = PENNIES_PER_DOLLAR * bill_value + PENNIES_PER_QUARTER * quarter_value - item_price;
        int dollar_coins = amount_due / PENNIES_PER_DOLLAR;
        amount_due = amount_due % PENNIES_PER_DOLLAR;
        int quarters = amount_due / PENNIES_PER_QUARTER;
        System.out.printf("Dollar coins: %d\n", dollar_coins);
        System.out.printf("Quarters: %d\n", quarters);
    }
}
```

</p>
</details>

***

## Write a program that helps a person decide whether to buy a hybrid car. 

Your pro gram’s inputs should be:

-`The cost of a new car`

-`The estimated miles driven per year`

-`The estimated gas price`

-`The efficiency in miles per gallon`

-`The estimated re-sale value after 5 years`

Compute the total cost of owning the car for five years. 
(For simplicity, we will not take the cost of financing into account.) 
Obtain realistic prices for a new and used hybrid and a comparable car from the Web.
Run your program twice, using today’s gas price and 15,000 miles per year.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P2_10 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Car cost: ");
        double car_cost = input.nextDouble();
        System.out.print("Miles driven: ");
        double miles_driven = input.nextDouble();
        System.out.print("Gas price: ");
        double gas_price = input.nextDouble();
        System.out.print("Fuel Efficiency: ");
        double fuel_efficiency = input.nextDouble();
        System.out.print("Re-sale value:  ");
        double resale_value = input.nextDouble();
        input.close();
        double cost_to_own = car_cost * (fuel_efficiency * miles_driven * gas_price);
        System.out.printf("Cost to own: %.2f", cost_to_own);
        System.out.println("Cost after re-sale: " + (car_cost - resale_value));
    }
}

```
</p>
</details>

***

## Write a program that asks the user to input

- `The number of gallons of gas in the tank`

- `The fuel efficiency in miles per gallon`

- `The price of gas per gallon`

Then print the cost per 100 miles and how far the car can go with the gas in the tank


<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P2_11 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Gas in tank: ");
        double gas_tank = input.nextDouble();
        System.out.print("Fuel efficiency: ");
        double fuel_efficiency = input.nextDouble();
        System.out.print("Price of gas: ");
        double gas_price = input.nextDouble();
        input.close();
        double cost_100_miles = 100 / fuel_efficiency * gas_price;
        System.out.printf("Cost per 100 miles: %.2f\n", cost_100_miles);
        double max_distance = fuel_efficiency * gas_tank;
        System.out.println("Maximum distance: " + max_distance);
    }
}
```

</p>
</details>

***

## File names and extensions. Write a program that prompts the user for the drive letter ( C ), the path ( \Windows\System ), the file name ( Readme ), and the extension ( txt ). Then print the complete file name  C:\Windows\System\Readme.txt . (If you use UNIX or a Macintosh, skip the drive name and use  / instead of \ to separate directories.)


<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P2_12 {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        System.out.print("Please enter the drive letter: ");
        String driveLetter = in.next();
        System.out.print("Please enter the path: ");
        String path = in.next();
        System.out.print("Please enter the filename: ");
        String filename = in.next();
        System.out.print("Please enter the extension: ");
        String extension = in.next();
        in.close();
        String completeFilename = driveLetter + ":" + path + "\\" + filename + "." + extension;
        System.out.println(completeFilename);
    }
}
```

</p>
</details>

***

## Write a program that reads a number between 1,000 and 999,999 from the user, where the user enters a comma in the input. Then print the number without a comma. Here is a sample dialog:

`Please enter an integer between 10,000 and 99,999: 23,456`
     23456
     
💡 Hint: Read the input as a string. Measure the length of the string. Suppose it contains n characters. Then extract substrings consisting of the first n - 4 characters and the last three characters


<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P2_13 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Number (between 1,000 - 999,999, including comma): ");
        String number = input.next();
        input.close();
        String prefix = number.substring(0, number.length() - 4);
        String postfix = number.substring(number.length() - 3);
        System.out.println(prefix + postfix);
    }
}
```
</p>
</details>

***

## Write a program that reads a number between 1,000 and 999,999 from the user and prints it with a comma separating the thousands.
Here is a sample dialog:

   `Please enter an integer between 1000 and 999999: 23456`
   
   23,456
   
<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P2_14 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Integer between 1 000 and 999 999: ");
        String number = input.next();
        input.close();
        String postfix = number.substring(number.length() - 3);
        String prefix = number.substring(0, number.length() - 3);
        System.out.println(prefix + "," + postfix);
    }
}
```

</p>
</details>
***
## Printing a grid Write a program that prints the grid of a tic-tac-toe game.

Of course, you could simply write seven statements of the form

**`System.out.println("+--+--+--+");`**

You should do it the smart way, though. Declare string variables to hold two kinds
of patterns: a comb-shaped pattern and the bottom line. Print the comb three times
and the bottom line once.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P2_15 {
    public static void main(String[] args) {
        String comb = "\n+--+--+--+\n|  |  |  |";
        String line = "+--+--+--+";
        System.out.println(comb + comb + comb);
        System.out.println(line);
    }
}

```
</p>
</details>

***

## Write a program that reads a five-digit positive integer and breaks it into a sequence of individual digits. 

`For example, the input 16384 is displayed as:`

**`1 6 3 8 4`**

You may assume that the input has no more than five digits and is not negative.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P2_16 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Five-digit number: ");
        int number = input.nextInt();
        input.close();
        int digit_a = number % 10; 
        number /= 10;
        int digit_b = number % 10;
        number /= 10;
        int digit_c = number % 10;
        number /= 10;
        int digit_d = number % 10;
        int digit_e = number /  10;
        System.out.printf("%d %d %d %d %d", digit_e, digit_d, digit_c, digit_b, digit_a);
    }
}
```

</p>
</details>

***

## Write a program that reads two times in military format (0900, 1730) and prints the number of hours and minutes between the two times. Here is a sample run. User input is in color.

 `Please enter the first time: 0900`
 
 `Please enter the second time: 1730`
 
8 hours 30 minutes
Extra credit if you can deal with the case where the first time is later than the second:

 `Please enter the first time: 1730`
 
 `Please enter the second time: 0900`
 
15 hours 30 minutes

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P2_17 {
    public static void main(String[] args) {
        final int MINUTES_IN_HOUR = 60;
        final int MINUTES_IN_DAY = 24 * 60;
        Scanner in = new Scanner(System.in);
        System.out.print("Please enter the first time: ");
        int firstTime = in.nextInt();
        int firstTimeInMinutes = firstTime / 100 * MINUTES_IN_HOUR + firstTime % 100;
        System.out.print("Please enter the second time: ");
        int secondTime = in.nextInt();
        in.close();
        int secondTimeInMinutes = secondTime / 100 * MINUTES_IN_HOUR + secondTime % 100;
        int minutes = secondTimeInMinutes - firstTimeInMinutes;
        minutes = (MINUTES_IN_DAY + minutes) % MINUTES_IN_DAY;
        int hours = minutes / 60;
        minutes %= 60;
        System.out.printf("%d hours %d minutes", hours, minutes);
    }
}

```
</p>
</details>
***

## Writing large letters. A large letter H can be produced like this:

It can be declared as a string literal like this:
final string LETTER_H = "*   *\n*   *\n*****\n*   *\n*   *\n";

(The \n escape sequence denotes a “newline” character that causes subsequent
characters to be printed on a new line.) Do the same for the letters E , L , and O . Then
write the message
H
E
L
L
O
in large letters.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P2_18 {
    public static void main(String[] args) {
        final String LETTER_H = "*   *\n*   *\n*****\n*   *\n*   *\n";
        final String LETTER_E = "*****\n* \n*****\n* \n*****\n";
        final String LETTER_L = "* \n* \n* \n* \n*****\n";
        final String LETTER_O = "*****\n*   *\n*   *\n*   *\n*****\n";
        System.out.println(LETTER_H);
        System.out.println(LETTER_E);
        System.out.println(LETTER_L);
        System.out.println(LETTER_L);
        System.out.println(LETTER_O);
    }
}

```

</p>
</details>
***
## Write a program that transforms numbers `1 ,  2 ,  3 , …,  12` into the corresponding month names `January ,  February ,March , …,  December` . Hint: Make a very long string  "January February March ..." , in which you add spaces such that each month name has the `same length`. Then use substring to extract the month you want.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P2_19 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Month number: ");
        int month = input.nextInt();
        input.close();
        String month_names = "January  February March    April    May      June     July     August   SeptemberOctober  November December ";
        String month_text = month_names.substring((month - 1) * 9, month * 9);
        System.out.println(month_text);
    }
}
```
</p>
</details>
***
## Easter Sunday is the first Sun­day after the first full moon of spring. To compute
the date, you can use this algorithm, invented by the mathe­matician Carl Friedrich
Gauss in 1800:

1. `Let y be the year (such as 1800 or 2001).`

2. `Divide y by 19 and call the remainder a . Ignore the quotient.`

3. `Divide y by 100 to get a quotient b and a remainder c .`

4. `Divide b by 4 to get a quotient d and a remainder e .`

5. `Divide 8 * b + 13 by 25 to get a quotient g . Ignore the remainder.`

6. `Divide 19 * a + b - d - g + 15 by 30 to get a remainder h . Ignore the quotient.`

7. `Divide c by 4 to get a quotient j and a remainder k .`

8. `Divide a + 11 * h by 319 to get a quotient m . Ignore the remainder.`

9. `Divide 2 * e + 2 * j - k - h + m + 32 by 7 to get a remainder r.Ignore the quotient.`

10. `Divide h - m + r + 90 by 25 to get a quotient n . Ignore the remainder.`

11. `Divide h - m + r + n + 19 by 32 to get a remainder p . Ignore the quotient.`

Then Easter falls on day p of month n . For example, if y is 2001 :
a = 6           h = 18              n = 4
b = 20, c = 1   j = 0, k = 1        p = 15
d = 5, e = 0    m = 0
g = 6           r = 6

Therefore, in 2001, Easter Sun­day fell on April 15. Write a program that prompts the
user for a year and prints out the month and day of Easter Sunday.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P2_21 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Current year: ");
        int y = input.nextInt();
        input.close();
        int a = y % 19;
        int b = y / 100; 
        int c = y % 100;
        int d = b / 4;
        int e = b % 4;
        int g = (8 * b + 13) / 25;
        int h = (19 * a + b - d - g + 15) % 30;
        int j = c / 4;
        int k = c % 4;
        int m = (a + 11 * h) / 319;
        int r = (2 * e + 2 * j - k - h + m + 32) % 7;
        int n = (h - m + r + 90) / 25;
        int p = (h - m + r + n + 19) % 32;
        System.out.println("Easter falls on " + p + "/" + n + "/" + y);
    }
}
```

</p>
</details>
***
## The following pseudocode describes how a bookstore computes the price of an order from the total price and the number of the books that were ordered.

`Read the total book price and the number of books.
  Compute the tax (7.5 percent of the total book price).
  Compute the shipping charge ($2 per book).
  The price of the order is the sum of the total book price, the tax, and the shipping charge.
  Print the price of the order.`
  
Translate this pseudocode into a Java program.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P2_22 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Book price: ");
        double book_price = input.nextDouble();
        System.out.print("Number of books: ");
        int books_number = input.nextInt();
        input.close();
        double tax = book_price * 7.5 / 100;
        final double SHIPPING_FEE = 2;
        double order_price = book_price * books_number + tax + SHIPPING_FEE;
        System.out.print("Order price: " + order_price);
    }
}
```
</p>
</details>
***
## The following pseudocode describes how to turn a string containing a ten-digit phone number (such as "4155551212" ) into a more readable string with parentheses and dashes, like this: "(415) 555-1212".

`Take the substring consisting of the first three characters and surround it with "(" and ") ". This is the area code.
Concatenate the area code, the substring consisting of the next three characters, a hyphen, and the substring consisting of the last four characters. This is the formatted number.`

Translate this pseudocode into a Java program that reads a telephone number into a
string variable, com­putes the formatted number, and prints it.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P2_23 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        String tel_number = input.next();
        input.close();
        String area_code = tel_number.substring(0, 4);
        String next_three = tel_number.substring(4, 7);
        String last_four = tel_number.substring(7, 10);
        System.out.printf("(%s) %s-%s", area_code, next_three, last_four);
    }
}
```
</p>
</details>
