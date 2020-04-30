## Write a program that reads an integer and prints if it's positive or negative.
💡

<details><summary>💾 Zgjidhje alternative </summary>
<p>
  
```java
import java.util.Scanner;
public class P3_01 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Number: ");
        int number = input.nextInt();
        input.close();
        System.out.println((number > 0)?  "Positive":
                           (number == 0)? "Zero":
                                          "Negative");
    }
}

```

</p>
</details>

## Write a program that reads a floating point number and prints `zero` if the number is zero. Otherwise, print `positive` or `negative`. Add `small` if the absolute value   of the number is less than 1, or `large` if it exceeds 1,000,000. Note: my solutions aim to test my knowledge of the ternary operator. You can always solve the problem with a normal if/else if/else statement

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P3_02 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Number: ");
        double number = input.nextDouble();
        input.close();
        System.out.print((number > 0)? 
                             (number < 1)? "Positive small":
                             (number > 1000000)? "Positive large":
                             "Positive":
                         (number < 0)? 
                             (number < 1)? "Negative small":    
                             (number > 1000000)? "Negative large":
                             "Negative":
                         "Zero");
    }
}
```

</p>
</details>

## Write a program that reads an integer and prints how many digits the number has, by checking whether the number is ≥ 10, ≥ 100, and so on. (Assume that all integers are less than ten billion.) If the number is negative, first multiply it by –1.

<details><summary>💾 Zgjidhje alternative </summary>
<p>
  
```java
import java.util.Scanner;
public class P3_03 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        long number = input.nextInt();
        input.close();
        int num_digits = 1;
        if (number < 0) number *= -1;
        if (number >= 10 && number < 100)
        {
            num_digits = 2;
        }
        else if (number >= 100 && number < 1000) 
        {
            num_digits = 3;
        }
        else if (number >= 1000 && number < 10000)
        {
            num_digits = 4;
        }
        else if (number >= 10000 && number< 100000)
        {
            num_digits = 5;            
        }
        else if (number >= 100000 && number < 1000000)
        {
            num_digits = 6;            
        }
        else if (number >= 1000000 && number < 10000000)
        {
            num_digits = 7;
        }
        else if (number >= 10000000 && number < 100000000)
        {
            num_digits = 8;            
        }
        else if (number >= 100000000 && number < 1000000000)
        {
            num_digits = 9;
        }
        else if (number >= 1000000000 && number < 1000000000)
        {
            num_digits = 10;
        }
        else
        {
            System.out.println("Number greater than 10 billion.");
        }
        System.out.printf("Num digits: %d", num_digits);
    }
}

```

</p>
</details>


## Write a program that reads three different numbers and prints if they're "all the same", "all different" or "neither".

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P3_04 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        double n1 = input.nextDouble();
        double n2 = input.nextDouble();
        double n3 = input.nextDouble();
        input.close();
        
        if ((n1 == n2) && (n2 == n3))
        {
            System.out.println("All the same");
        }
        else if ((n1 != n2) && (n1 != n3))
        {
            System.out.println("All different");
        }
        else
        {
            System.out.println("Neither");
        }
    }
}
```

</p>
</details>

## Write a program that reads three numbers and prints “increasing” if they are  in increasing order, “decreasing” if they are in decreasing order, and “neither”  otherwise. Here, “increasing” means “strictly increasing”, with each value larger  than its predecessor. The sequence 3 4 4 would not be considered increasing.

<details><summary>💾 Zgjidhje alternative </summary>
<p>
  
```java
import java.util.Scanner;
public class P3_05 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        double n1 = input.nextDouble();
        double n2 = input.nextDouble();
        double n3 = input.nextDouble();
        input.close();
        System.out.println((n1 > n2 == true) && (n2 > n3 == true)? "Decreasing":
                           (n1 < n2 == true) && (n2 < n3 == true)? "Increasing":
                                                                   "Neither");
    }
}
```

</p>
</details>

## Repeat Exercise P3.5, but before reading the numbers, ask the user whether increasing/decreasing should be “strict” or “lenient”. In lenient mode, the sequence 3 4 4 is increasing and the sequence 4 4 4 is both increasing and decreasing

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;


public class P3_06 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Strict or lenient? ");
        String mode = input.next().toLowerCase();
        double n1 = input.nextDouble();
        double n2 = input.nextDouble();
        double n3 = input.nextDouble();
        input.close();
        if (mode.equals("strict"))
        {
            if ((n1 < n2) && (n2 < n3))
            {
                System.out.println("Increasing");
            }
            else if ((n1 > n2) && (n2 > n3))
            {
                System.out.println("Decreasing");
            }
            else
            {
                System.out.println("Neither");
            }
        }
        else if (mode.equals("lenient"))
        {
            if (((n1 <= n2) && (n2 < n3)) || ((n1 < n2 ) && (n2 <= n3)))
            {
                System.out.println("Increasing");
            }
            else if ((n1 >= n2) && (n2 > n3) || ((n1 > n2) && (n2 >= n3)))
            {
                System.out.println("Decreasing");
            }
            else if ((n1 == n2) && (n2 == n3))
            {
                System.out.println("Increasing and decreasing");
            }
            else
            {
                System.out.println("Neither");
            }
        }
    }
}
```

</p>
</details>

## Write a program that reads in three integers and prints “in order” if they are sorted in  ascending or descending order, or “not in order” otherwise. For example,

     1 2 5 in order
     
     1 5 2 not in order
     
     5 2 1 in order
     
     1 2 2 in order

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P3_07 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        double n1 = input.nextDouble();
        double n2 = input.nextDouble();
        double n3 = input.nextDouble();
        if ((n1 <= n2  && n2 < n3) || (n1 < n2 && n2 <= n3) || (n1 > n2 && n2 >= n3) || (n1 >= n2 && n2 > n3))
        {
            System.out.println("In order");
        }
        else
        {
            System.out.println("Not in order");
        }
        input.close();
    }
}
```

</p>
</details>

## Write a program that reads four integers and prints “two pairs” if the input consists of two matching pairs (in some order) and “not two pairs” otherwise. For example,

  1 2 2 1   two pairs
  
  1 2 2 3   not two pairs
  
  2 2 2 2   two pairs  

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P3_08 {
  public static void main(String[] args) {
    Scanner input = new Scanner(System.in);
    double n1 = input.nextDouble();
    double n2 = input.nextDouble();
    double n3 = input.nextDouble();
    double n4 = input.nextDouble();
    if (n1 == n2 || n1 == n3 || n1 == n4 || n2 == n3 || n2 == n4 || n3 == n4) {
      System.out.println("Two pairs");
    } else {
      System.out.println("Not two pairs");
    }
    input.close();
  }
}
```

</p>
</details>

## Write a program that reads a temperature value and the letter C for Celsius or F for  Fahrenheit. Print whether water is liquid, solid, or gaseous at the given temperature at sea level.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P3_09 {
  public static void main(String[] args) {
    Scanner input = new Scanner(System.in);
    System.out.print("Temperature type: ");
    String temp_type = input.next();
    System.out.print("Temperature value: ");
    double temp_value = input.nextDouble();
    input.close();
    if (temp_type.equals("C")) {
      if (temp_value >= 0 && temp_value <= 100) {
        System.out.println("Water is liquid.");
      } else if (temp_value > 100) {
        System.out.println("Water is gaseous.");
      } else {
        System.out.println("Water is solid.");
      }
    } else if (temp_type.equals("F")) {
      if (temp_value >= 32 && temp_value < 132) {
        System.out.println("Water is liquid.");
      } else if (temp_value >= 132) {
        System.out.println("Water is gaseous.");
      } else {
        System.out.println("Water is solid.");
      }
    }
  }
}
```

</p>
</details>

## The boiling point of water drops by about one degree Celsius for every 300 meters (or 1,000 feet) of altitude. Improve the program of Exercise P3.9 to allow the user to supply the altitude in meters or feet.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P3_10 {
	public static void main(String[] args) {
		final int FREEZE_CELSIUS = 0;
		final int FREEZE_FAHRENHEIT = 32;
		double boil_celsius = 100;
		double boil_fahrenheit = 212;

		Scanner input = new Scanner(System.in);
		System.out.print("Temperature type (C/F): ");
		String temp_type = input.next();
		System.out.print("Temperature value: ");
		double temp_value = input.nextDouble();
		System.out.print("Altitude type (M/F): ");
		String alt_type = input.next();
		System.out.print("Altitude value: ");
		double alt_value = input.nextDouble();
		input.close();

		if (temp_type.equals("C")) {
			if (alt_type.equals("M")) {
				boil_celsius -= alt_value / 300;
			} else {
				boil_celsius -= alt_value / 1000;
			}

			if (temp_value <= FREEZE_CELSIUS) {
				System.out.println("Solid");
			} else if (temp_value >= boil_celsius) {
				System.out.println("Gas");
			} else {
				System.out.println("Liquid");
			}
		} else {
			if (alt_type.equals("M")) {
				boil_fahrenheit -= alt_value / 300;
			}
			else {
				boil_fahrenheit -= alt_value / 1000;
			}
			if (temp_value <= FREEZE_FAHRENHEIT) {
				System.out.println("Solid");
			} else if (temp_value >= boil_fahrenheit) {
				System.out.println("Gas");
			} else {
				System.out.println("Solid");
			}
		}
	}
}
```

</p>
</details>

## Add error handling to Exercise P3.10. If the user provides an invalid unit for the altitude, print an error message and end the program.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P3_11 {
	public static void main(String[] args) {
		final int FREEZE_CELSIUS = 0;
		final int FREEZE_FAHRENHEIT = 32;
		double boil_celsius = 100;
		double boil_fahrenheit = 212;

		Scanner input = new Scanner(System.in);
		System.out.print("Temperature type (C/F): ");
		String temp_type = input.next();
		System.out.print("Temperature value: ");
		double temp_value = input.nextDouble();
		System.out.print("Altitude type (M/F): ");
		String alt_type = input.next();
		System.out.print("Altitude value: ");
		double alt_value = input.nextDouble();
		input.close();

		if (temp_type.equals("C")) {
			if (alt_type.equals("M")) {
				boil_celsius -= alt_value / 300;
			} else if (alt_type.equals("F")) {
				boil_celsius -= alt_value / 1000;
			} else {
				System.out.println("Invalid unit for altitude.");
				return;
			}
			if (temp_value <= FREEZE_CELSIUS) {
				System.out.println("Solid");
			} else if (temp_value >= boil_celsius) {
				System.out.println("Gas");
			} else {
				System.out.println("Liquid");
			}
		} else if (temp_type.equals("F")) {
			if (alt_type.equals("M")) {
				boil_fahrenheit -= alt_value / 300;
			} else if (alt_type.equals("F")) {
				boil_fahrenheit -= alt_value / 1000;
			} else {
				System.out.println("Invalid unit for altitude.");
				return;
			}
			if (temp_value <= FREEZE_FAHRENHEIT) {
				System.out.println("Solid");
			} else if (temp_value >= boil_fahrenheit) {
				System.out.println("Gas");
			} else {
				System.out.println("Solid");
			}
		} else {
			System.out.println("Invalid temperature unit.");
			return;
		}
	}
}
```

</p>
</details>

## Write a program 
that translates a letter grade into a number grade. Letter grades are  A, B, C, D, and F, possibly followed by + or –. Their numeric values are 4, 3, 2, 1, and  0. There is no F+ or F–. A + increases the numeric value by 0.3, a – decreases it by 0.3.
 However, an A+ has value 4.0.
 
     `Enter a letter grade: B-`
     
     `The numeric value is 2.7.`

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P3_12 {
	public static void main(String[] args) {
		Scanner input = new Scanner(System.in);
		final double A_GRADE = 4.0;
		final double B_GRADE = 3.0;
		final double C_GRADE = 2.0;
		final double D_GRADE = 1.0;
		final double F_GRADE = 0.0;
		final double PLUS_MINUS_ADJUSTMENT = 0.3;
		System.out.print("Letter grade: ");
		String grade = input.next();
		input.close();
		double numeric_grade = F_GRADE;
		if (grade.charAt(0) == 'A') {
			numeric_grade = A_GRADE;
		} else if (grade.charAt(0) == 'B') {
			numeric_grade = B_GRADE;
		} else if (grade.charAt(0) == 'C') {
			numeric_grade = C_GRADE;
		} else if (grade.charAt(0) == 'D') {
			numeric_grade = D_GRADE;
		} else if (grade.charAt(0) == 'F') {
		} else {
			System.out.println("Invalid letter grade.");
			return;
		}

		if (grade.charAt(1) == '+') {
			numeric_grade += PLUS_MINUS_ADJUSTMENT;
		} else if (grade.charAt(1) == '-') {
			numeric_grade -= PLUS_MINUS_ADJUSTMENT;
		} else {
			System.out.println("Invalid letter grade");
			return;
		}
		System.out.printf("\nLetter grade %s = %f", grade, numeric_grade);
	}
}
```

</p>
</details>

## Write a program 
that translates a number between 0 and 4 into the closest letter
grade. For example, the number 2.8 (which might have been the average of several
grades) would be converted to B–. Break ties in favor of the better grade; 
for example 2.85 should be a B.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P3_13 {
	public static void main(String[] args) {
		Scanner input = new Scanner(System.in);
		System.out.print("Numeric grade (0.0 - 4.0): ");
		double numeric_grade = input.nextDouble();
		input.close();
		String letter_grade = "F";
		if (numeric_grade > 4 || numeric_grade < 0) {
			System.out.println("Invalid grade. Grade must be between 0.0 and 4.0.");
			return;
		} else if (numeric_grade == 4 || numeric_grade >= 3.85) {
			letter_grade = "A";
		} else if (numeric_grade > 3.7) {
			letter_grade = "A-";
		} else if (numeric_grade > 3) {
			letter_grade = "B+";
		} else if (numeric_grade >= 2.85) {
			letter_grade = "B";
		} else if (numeric_grade >= 2.7) {
			letter_grade = "B-";
		} else if (numeric_grade > 2) {
			letter_grade = "C+";
		} else if (numeric_grade >= 1.85) {
			letter_grade = "C";
		} else if (numeric_grade >= 1.7) {
			letter_grade = "C-";
		} else if (numeric_grade > 1) {
			letter_grade = "D+";
		} else if (numeric_grade >= 0.85) {
			letter_grade = "D";
		} else if (numeric_grade >= 0.7) {
			letter_grade = "D-";
		} else {
			letter_grade = "F";
		}
		System.out.println("Your grade is: " + letter_grade);
	}
}

```

</p>
</details>

## Write a program 
that takes user input describing a playing card in the following shorthand  notation: A Ace 2 ... 10 Card values J Jack Q Queen K King D Diamonds H Hearts S Spades C Clubs  Your program should print the full description of the card. For example, Enter the card notation:  QS Queen of Spades

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P3_14 {
  public static void main(String[] args) {
    Scanner input = new Scanner(System.in);
    System.out.print("Your card: ");
    String card = input.next();
    input.close();
    String value = card.substring(0, card.length() - 1);
    String suit = card.substring(card.length() - 1);
    String card_name = "";

    if (value.compareTo("A") == 0) {
      card_name = "Ace";
    } else if (value.compareTo("J") == 0) {
      card_name = "Jack";
    } else if (value.compareTo("Q") == 0) {
      card_name = "Queen";
    } else if (value.compareTo("K") == 0) {
      card_name = "King";
    } else {
      card_name = value;
    }

    if (suit.compareTo("D") == 0) {
      card_name += " of Diamonds";
    } else if (suit.compareTo("H") == 0) {
      card_name += " of Hearts";
    } else if (suit.compareTo("S") == 0) {
      card_name += " of Spades";
    } else if (suit.compareTo("C") == 0) {
      card_name += " of Clubs";
    }
    System.out.println(card_name);
  }
}
```

</p>
</details>

## Write a program 
that reads in three floating point numbers and prints the largest of  the three inputs without using the  max function. For example:

     Enter a number: 4
     Enter a number: 9
     Enter a number: 2.5
     The largest number is 9.0

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P3_15 {
	public static void main(String[] args) {
		Scanner input = new Scanner(System.in);
		System.out.print("Enter three numbers seperating them by a space: ");
		double n1 = input.nextDouble();
		double n2 = input.nextDouble();
		double n3 = input.nextDouble();
		input.close();
		double largest;
		
		if (n1 >= n2 && n1 > n3) {
			largest = n1;
		} else if (n2 > n1 && n2 >= n3){
			largest = n2;
		} else {
			largest = n3;
		}
		System.out.println("Largest number: " + largest);
	}
}
```

</p>
</details>

## Write a program 
that reads in three strings and sorts them lexicographically.

     Enter a string: Charlie
     Enter a string: Able
     Enter a string: Baker
     Able
     Baker
     Charlie

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P3_16 {
	public static void main(String[] args) {
		Scanner input = new Scanner(System.in);
		System.out.print("String one: ");
		String string1 = input.next();
		System.out.print("String two: ");
		String string2 = input.next();
		System.out.print("String three: ");
		String string3 = input.next();
		input.close();
		
		if (string1.compareTo(string2) < 0 && string1.compareTo(string3) < 0) {
			System.out.println(string1);
			if (string2.compareTo(string3) < 0) {
				System.out.println(string2);
				System.out.println(string3);
			} else {
				System.out.println(string3);
				System.out.println(string2);
			}
		} else if (string1.compareTo(string2) > 0 && string2.compareTo(string3) < 0) {
			System.out.println(string2);
			if (string1.compareTo(string3) < 0) {
				System.out.println(string1);
				System.out.println(string3);
			} else {
				System.out.println(string3);
				System.out.println(string1);
			}
		} else {
			System.out.println(string3);
			if (string1.compareTo(string2) < 0) {
				System.out.println(string1);
				System.out.println(string2);
			} else {
				System.out.println(string2);
				System.out.println(string1);
			}
		}
	}
}
```

</p>
</details>

## When two points in time are compared, each given as hours (in military time,ranging from 0 and 23) and minutes, the following pseudocode determines which comes first.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P3_17 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Time one: ");
	int time1 = input.nextInt();
	System.out.print("Time two: ");
	int time2 = input.nextInt();
	input.close();
	int hours1 = time1 / 100;
	int minutes1 = time1 % 100 + hours1 * 60;

	int hours2 = time2 / 100;
	int minutes2 = time2 % 100 + hours2 * 60;

	if (hours1 < hours2) {
	    System.out.println(time1);
	}
	else if (hours1 == hours2) {
	    if (minutes1 < minutes2) {
		System.out.println(time1);
	    }
	    else if (minutes1 == minutes2) {
		System.out.println(time1);
	    }
	    else {

	    }
	}
	else {
	    System.out.println(time2);
	}
    }
}
```

</p>
</details>

## The following algorithm yields the season (Spring, Summer, Fall, or Winter) for a  given month and day.
 
     If month is 1, 2, or 3, season = "Winter"
     Else if month is 4, 5, or 6, season = "Spring"
     Else if month is 7, 8, or 9, season = "Summer"
     Else if month is 10, 11, or 12, season = "Fall"
     If month is divisible by 3 and day >= 21
     If season is "Winter", season = "Spring"
     Else if season is "Spring", season = "Summer"
     Else if season is "Summer", season = "Fall"
     Else season = "Winter"
     
 Write a program that prompts the user for a month
 and day and then prints the season, as determined
 by this algorithm.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;

public class P3_18 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Month: ");
	int month = input.nextInt();
	System.out.print("Day: ");
	int day = input.nextInt();
	input.close();
	String season;
	if (month < 1 || month > 12) {
	    System.out.println("Invalid month number. Months are between 1-12");
	    return;
	}
	
	if (day < 1 || day > 31) {
	    System.out.println("Invalid day number. Days are between 1-31");
	    return;
	}
	
	else if (month <= 3) {
	    season = "Winter";
	}
	else if (month <= 6) {
	    season = "Spring";
	}
	else if (month <= 9) {
	    season = "Summer";
	}
	else {
	    season = "Winter";
	}
	System.out.println("Season is: " + season);
    }
}
```

</p>
</details>

## Write a program that reads in two floating­point numbers and tests whether they are the same up to two decimal places. Here are two sample runs.

     Enter a floating-point number: 2.0
     Enter a floating-point number: 1.99998
     They are the same up to two decimal places.
     Enter a floating-point number: 2.0
     Enter a floating-point number: 1.98999
     They are different.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P3_19 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Number one: ");
	double number1 = input.nextDouble();
	System.out.print("Number two: ");
	double number2 = input.nextDouble();
	input.close();
	
	if (Math.abs(number1 - number2) <= 0.01) {
	    System.out.println("They're the same");
	}
	else {
	    System.out.println("They're different");
	}
    }
}
```

</p>
</details>

## Write a program that prompts for the day and month of the user’s birthday and then prints a horoscope. Make up fortunes for programmers, like this:

     Please enter your birthday.
     month: 6
     day: 16
     Gemini are experts at figuring out the behavior of complicated programs.
     You feel where bugs are coming from and then stay one step ahead. Tonight,
     your style wins approval from a tough critic.
     
 Each fortune should contain the name of the astrological sign. (You will find the
 names and date ranges of the signs at a distressingly large number of sites on the
 Internet.)

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;


public class P3_20 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.println("Please enter your birthday.");
	System.out.print("Month: ");
	int month = input.nextInt();
	System.out.print("Day: ");
	int day = input.nextInt();
	input.close();
	String sign;
	if (month < 1 || month > 12) {
	    System.out.println("Invalid month number. Months are between 1-12");
	    return;
	}
	
	else if (day < 1 || day > 31) {
	    System.out.println("Invalid day number. Days are between 1-31");
	    return;
	}
	
	else if (month == 1) {
	    if (day <= 19) {
		sign = "Capricorn";
	    }
	    else {
		sign = "Aquarius";
	    }
	}
	else if (month == 2) {
	    if (day <= 18) {
		sign = "Aquarius";
	    }
	    else {
		sign = "Pisces";
	    }
	}
	else if (month == 3) {
	    if (day <= 20) {
		sign = "Pisces";
	    }
	    else {
		sign = "Aries";
	    }
	}
	else if (month == 4) {
	    if (day <= 19) {
		sign = "Aries";
	    }
	    else {
		sign = "Taurus";
	    }
	}
	else if (month == 5) {
	    if (day <= 20) {
		sign = "Taurus";
	    }
	    else {
		sign = "Gemini";
	    }
	}
	else if (month == 6) {
	    if (day <= 21) {
		sign = "Gemini";
	    }
	    else {
		sign = "Cancer";
	    }
	}
	else if (month == 7) {
	    if (day <= 22) {
		sign = "Cancer";
	    }
	    else {
		sign = "Leo";
	    }
	}
	else if (month == 8) {
	    if (day <= 22) {
		sign = "Leo";
	    }
	    else {
		sign = "Virgo";
	    }
	}
	else if (month == 9) {
	    if (day <= 22) {
		sign = "Virgo";
	    }
	    else {
		sign = "Libra";
	    }
	}
	else if (month == 10) {
	    if (day <= 23) {
		sign = "Libra";
	    }
	    else {
		sign = "Scorpio";
	    }
	}
	else if (month == 11) {
	    if (day <= 21) {
		sign = "Scorpio";
	    }
	    else {
		sign = "Sagittarius";
	    }
	}
	else {
	    if (day <= 21) {
		sign = "Sagittarius";
	    }
	    else {
		sign = "Capricorn";
	    }
	}
	
	System.out.println("Your sign: " + sign);
	String fortune;
	if (sign.equals("Capricorn")) {
	    fortune = "Example Capricorn fortune";
	}
	else if (sign.equals("Aquarius")) {
	    fortune = "Example Aquarius fortune";
	}
	else if (sign.equals("Pisces")) {
	    fortune = "Example Pisces fortune";
	}
	else if (sign.equals("Aries")) {
	    fortune = "Example Aries fortune";
	}
	else if (sign.equals("Taurus")) {
	    fortune = "Example Taurus fortune";
	}
	else if (sign.equals("Gemini")) {
	    fortune = "Example Gemini fortune";
	}
	else if (sign.equals("Cancer")) {
	    fortune = "Example Cancer fortune";
	}
	else if (sign.equals("Leo")) {
	    fortune = "Example Leo fortune";
	}
	else if (sign.equals("Virgo")) {
	    fortune = "Example Virgo fortune";
	}
	else if (sign.equals("Libra")) {
	    fortune = "Example Libra fortune";
	}
	else if (sign.equals("Scorpio")) {
	    fortune = "Example Scorpio fortune";
	}
	else {
	    fortune = "Unknown sign. You're a special one.";
	}
	System.out.println("Your sign: " + fortune);
    }
}
```

</p>
</details>

## The original U.S. income tax of 1913 was quite simple. The tax was

      1 percent on the first $50,000.
      2 percent on the amount over $50,000 up to $75,000.
      3 percent on the amount over $75,000 up to $100,000.
      4 percent on the amount over $100,000 up to $250,000.
      5 percent on the amount over $250,000 up to $500,000.
      6 percent on the amount over $500,000.
     
There was no separate schedule for single or married taxpayers. 
Write a program that computes the income tax according to this schedule.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;

public class P3_21 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Your income: ");
	double income = input.nextDouble();
	input.close();
	double tax = 0;
	if (income < 1) {
	    System.out.println("Income must be greater than 0");
	    return;
	}
	else if (income <= 50000) {
	    tax = income * 0.01;
	}
	else if (income <= 75000) {
	    tax = income * 0.02;
	}
	else if (income <= 100000) {
	    tax = income * 0.02;
	}
	else if (income <= 250000) {
	    tax = income * 0.04;
	}
	else if (income <= 500000) {
	    tax = income * 0.05;
	}
	else {
	    tax = income * 0.06;
	}
	System.out.println("Your tax is: " + tax);
   }
}

```

</p>
</details>

## Write a program
Write a program that computes taxes for the following schedule.
 if your status is single and
 if the taxable income is over   but not over        the tax is          of the amount over
 
     	$0                              $8,000                  10%                 $0
     
	$8,000                             $32,000              $800 +  15%           $8,000

	$32,000                                                 $4,400 + 25%          $32,000
  

 if your status is Married and
 if the taxable income is over    but not over        the tax is           of the amount over
 
	  $0                              $16,000                  10%                     $0
	  $16,000                         $64,000                 $1,600 + 15%            $16,000
	  $64,000                                                  $8,800 + 25%           $64,000

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;

public class P3_22 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Married or single (M/S): ");
	String status = input.next();
	System.out.print("Your income: ");
	double income = input.nextDouble();
	input.close();

	double tax = 0;
	if (status.compareTo("M") != 0 || status.compareTo("S") != 0) {
	    System.out.println("Invalid status. Please use M(arried) or S(ingle).");
	    return;
	}
	else if (income < 1) {
	    System.out.println("Income must be greater than 0!");
	    return;
	}
	else if (status.equals("S")) {
	    if (income <= 8000) {
		tax = income * 0.10;
	    }
	    else if (income <= 32000) {
		tax = (income * 0.15) + 800;
	    }
	    else {
		tax = (income * 0.25) + 4400;
	    }
	}
	else if (status.equals("M")) {
	    if (income <= 16000) {
		tax = income * 0.10;
	    }
	    else if (income <= 64000){
		tax = (income * 0.15) + 1600;
	    }
	    else {
		tax = (income * 0.25) + 8800;
	    }
	}
	System.out.println("Your tax: " + tax);
    }
}
```

</p>
</details>

## Unit conversion. 
Write a unit conversion program that asks the users from which  unit they want to convert (fl. oz, gal, oz, lb, in, ft, mi) and to which unit they want to  convert (ml, l, g, kg, mm, cm, m, km). Reject incompatible conversions (such as gal km). Ask for the value to be converted, then display the result:

     Convert from? gal
     Convert to? ml
     Value? 2.5
     2.5 gal = 9463.5 ml

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;

public class P3_24 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	final double FLUID_OUNCE_TO_LITER = 0.029586;
	final double GALLON_TO_LITER = 3.758;
	final double OUNCE_TO_GRAM = 28.3495;
	final double POUND_TO_GRAM = 453.6;
	final double INCH_TO_METER = 0.00254;
	final double FOOT_TO_METER = 0.305;
	final double MILE_TO_METER = 1609.0;
	System.out.print("Convert from? (fl.oz, gal, oz, lb, in, ft, mi) ");
	String convert_from = input.next();
	System.out.print("Convert to? (ml, l, g, kg, mm, cm, m, km) ");
	String convert_to = input.next();
	System.out.print("Value: ");
	double value = input.nextDouble();
	input.close();
	
	double c_factor = 0.0;
	
	if (convert_from.equals("fl.oz")) {
	    if (convert_to.equals("ml")) {
		c_factor = FLUID_OUNCE_TO_LITER * 1000;
	    }
	    else if (convert_to.equals("l")) {
		c_factor = FLUID_OUNCE_TO_LITER;
	    }
	}
	else if (convert_from.equals("gal")) {
	    if (convert_to.equals("ml")) {
		c_factor = GALLON_TO_LITER * 1000;
	    }
	    else if (convert_to.equals("l")) {
		c_factor = GALLON_TO_LITER;
	    }
	}
	else if (convert_from.equals("oz")) {
	    if (convert_to.equals("g")) {
		c_factor = OUNCE_TO_GRAM;
	    }
	    else if (convert_to.equals("kg")) {
		c_factor = OUNCE_TO_GRAM / 1000;
	    }
	}
	else if (convert_from.equals("lb")) {
	    if (convert_to.equals("g")) {
		c_factor = POUND_TO_GRAM;
	    }
	    else if (convert_to.equals("kg")){
		c_factor = POUND_TO_GRAM / 1000;
	    }
	}
	else if (convert_from.equals("in")) {
	    if (convert_to.equals("mm")) {
		c_factor = INCH_TO_METER * 1000;
	    }
	    else if (convert_to.equals("cm")) {
		c_factor = INCH_TO_METER * 100;
	    }
	    else if (convert_to.equals("m")) {
		c_factor = INCH_TO_METER;
	    }
	    else if (convert_to.equals("km")) {
		c_factor = INCH_TO_METER / 1000;
	    }
	}
	else if (convert_from.equals("ft")) {
	    if (convert_to.equals("mm")) {
		c_factor = FOOT_TO_METER * 1000;
	    }
	    else if (convert_to.equals("cm")) {
		c_factor = FOOT_TO_METER * 100;
	    }
	    else if (convert_to.equals("m")) {
		c_factor = FOOT_TO_METER;
	    }
	    else if (convert_to.equals("km")) {
		c_factor = FOOT_TO_METER / 1000;
	    }
	}
	else if (convert_from.equals("ml")) {
	    if (convert_to.equals("mm")) {
		c_factor = MILE_TO_METER * 1000;
	    }
	    else if (convert_to.equals("cm")) {
		c_factor = MILE_TO_METER * 100;
	    }
	    else if (convert_to.equals("m")) {
		c_factor = MILE_TO_METER;
	    }
	    else if (convert_to.equals("km")) {
		c_factor = MILE_TO_METER / 1000;
	    }
	}
	
	if (c_factor == 0.0) {
	    System.out.println("Conversion is unavailable.");
	}
	else {
	    double converted = value * c_factor;
	    System.out.printf("%.4f %s = %.4f %s", value, convert_from, converted, convert_to);
	}
    }
}
```

</p>
</details>

## Write a program 
That prompts the user to provide a single character from the alphabet. Print Vowel or Consonant, depending on the user input. If the user input is not a letter (between a and z or A and Z), or is a string of length > 1, print an error
message.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;

public class P3_25 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Character: ");
	char character = input.next().charAt(0);
	input.close();
	
	if (Character.isLetter(character)) {
	    if (character == 'a' || character == 'A' || character == 'e' || character == 'E'
	        || character == 'i' || character == 'I' || character == 'o' || character == 'O'
	        || character == 'u' || character == 'U') {
		System.out.println("The character is a vowel.");
	    }
	    else {
		System.out.println("The character is a consonant");
	    }
	}
	else {
	    System.out.println("Invalid input. Not a character!");
	}
    }
}
```

</p>
</details>

## Roman numbers. Write a program that converts a positive integer into the Roman
 number system. The Roman number system has digits
 
     I 1
     V 5
     X 10
     L 50
     C 100
     D 500
     M 1,000
     
 Numbers are formed according to the following rules:
 
   -  a.  Only numbers up to 3,999 are represented.
   
   -  b.  As in the decimal system, the thousands, hundreds, tens, and ones are ex­
     pressed separately.
     
   -  c.  The numbers 1 to 9 are expressed as
   
	 I  1
	 II  2
	 III  3
	 IV  4
	 V  5
	 VI  6
	 VII  7
	 VIII  8
	 IX  9
	 
   As you can see, an I preceding a V or X is subtracted from the value, and you can never have more than three I’s in a row.
   
    - d.Tens and hundreds are done the same way, except that the letters X, L, C and C, D, M are used instead of I, V, X, respectively.
    
 Your program should take an input, such as 1978, and convert it to Roman numerals,
 MCMLXXVIII.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;

public class P3_26 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Integer number (1-4000): ");
	int number = input.nextInt();
	input.close();
	String roman = "";
	
	if (number < 1) {
	    System.out.println("Number must be an integer between 1 and 4000");
	    return;
	}
	int digit = number / 1000;
	
	if (digit == 3) {
	    roman = "MMM";
	}
	else if (digit == 2) {
	    roman = "MM";
	}
	else if (digit == 1) {
	    roman = "M";
	}
	digit = (number % 1000) / 100;
	
	if (digit == 9) {
	    roman += "CM";
	}
	else if (digit == 4) {
	    roman += "CD";
	}
	else {	    
	    if (digit >= 5) {
    	    	roman += "D";
    	    	digit -= 5;
	    }
	    if (digit == 3) {
    	    	roman += "CCC";
	    }
	    else if (digit == 2) {
        	roman += "CC";
	    }
	    else if (digit == 1) {
        	roman += "C";
	    }
	}
	digit = (number % 100) / 10;
	if (digit == 9) {
	    roman += "XC";
	}
	else if (digit == 4) {
	    roman += "XL";
	}
	else {
	    if (digit >= 5) {
		roman += "L";
		digit -= 5;
	    }
	    if (digit == 3) {
		roman += "XXX";
	    }
	    else if (digit == 2) {
		roman += "XX";
	    }
	    else if (digit == 1){
		roman += "X";
	    }
	}
	digit = number % 10;
	
	if (digit == 9) {
	    roman += "IX";
	}
	else if (digit == 4) {
	    roman += "IV";
	}
	else {
	    if (digit >= 5) {
		roman += "V";
		digit -= 5;
	    }
	    if (digit == 3) {
		roman += "III";
	    }
	    else if (digit == 2) {
		roman += "II";
	    }
	    else if (digit == 1) {
		roman += "I";
	    }
	}
	System.out.println("Roman numeral: " + roman);
    }
}
```

</p>
</details>

## Write a program
That asks the user to enter a month (1 for January, 2 for February, and so on) and then prints the number of days in the month. For February, print “28 or 29 days”.

    Enter a month: 5
     30 days
     
Do not use a separate  if/else branch for each month. Use Boolean operators

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;

public class P3_27 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Month number: ");
	int month = input.nextInt();
	input.close();
	
	if (month < 1 || month > 12) {
	    System.out.println("Invalid month number. Months are between 1 and 12");
	    return;
	}
	
	System.out.print("Days in the month: ");
	if (month == 4 || month == 6 || month == 9 || month == 11) {
	    System.out.print("30");
	}
	else if (month == 2) {
	    System.out.print("28 or 29");
	}
	else {
	    System.out.print("31");
	}
    }
}
```

</p>
</details>

## A year
with 366 days is called a leap year. Leap years are necessary to keep the calendar synchronized with the sun because the earth revolves around the sun once every 365.25 days. Actually, that figure is not entirely precise, and for all dates after
1582 the Gregorian correction applies. Usually years that are divisible by 4 are leap years, for example 1996. However, years that are divisible by 100 (for example, 1900) are not leap years, but years that are divisible by 400 are leap years (for exam ple, 2000). Write a program that asks the user for a year and computes whether that year is a leap year. Use a single  if statement and Boolean operators.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;

public class P3_28 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Year: ");
	int year = input.nextInt();
	input.close();
	boolean leap_year = false;
	if ((year % 100 != 0 && year % 4 == 0) || year % 400 == 0) {
	    leap_year = true;
	}
	System.out.printf("Is %d a leap year: %b", year, leap_year);
    }
}
```

</p>
</details>

## French country names are feminine when they end with the letter e, masculine 
otherwise, except for the following which are masculine even though they end with e:

    • le Belize
    • le Cambodge
    • le Mexique
    • le Mozambique
    • le Zaïre
    • le Zimbabwe
    
Write a program that reads the French name of a country and adds the article: le for
masculine or la for feminine, such as le Canada or la Belgique.
However, if the country name starts with a vowel, use l’; for example, l’Afghanistan.
For the following plural country names, use les:

    • les EtatsUnis
    • les PaysBas

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P3_29 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Country: ");
	String country = input.next();
	input.close();
	boolean vowel = false;
	boolean plural = false;
	boolean feminine = false;

	char first_letter = country.charAt(0);
	if (country.equals("Etats-Unis") || country.equals("Pays-Bas")) {
	    plural = true;
	}
	else if (first_letter == 'a' || first_letter == 'A'
		|| first_letter == 'e' || first_letter == 'E'
		|| first_letter == 'i' || first_letter == 'I'
		|| first_letter == 'o' || first_letter == 'O'
		|| first_letter == 'u' || first_letter == 'U') {
	    vowel = true;
	}
	else if (!(country.equals("Belize") || country.equals("Cambodge")
		|| country.equals("Mexique") || country.equals("Mozambique")
		|| country.equals("Zaïre") || country.equals("Zimbabwe"))) {
	    if (country.charAt(country.length() - 1) == 'e') {
		feminine = true;
	    }
	}
	if (vowel) {
	    country = "l’" + country;
	}
	else if (plural) {
	    country = "les " + country;
	}
	else if (feminine) {
	    country = "la " + country;
	}
	else {
	    country = "le " + country;
	}
	System.out.println(country);
    }
}
```

</p>
</details>

## Write a program 
to simulate a bank transaction. There are two bank accounts: checking and savings. First, ask for the initial balances of the bank accounts; reject negative balances. Then ask for the transaction; options are deposit, withdrawal, and transfer. Then ask for the account; options are checking and savings. Then ask for the amount; reject transactions that overdraw an account. At the end, print the balances of both accounts

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;

public class P3_30 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Savings balance: ");
	double savings = input.nextDouble();
	System.out.print("Checkings balance: ");
	double checkings = input.nextDouble();
	
	if (savings < 1 || checkings < 1) {
	    System.out.println("Balances must be greater than 0.");
	    input.close();
	    return;
	}
	System.out.print("Choose an operation: 1) Deposit, 2) Withdraw, 3) Transfer: ");
	int operation_choice = input.nextInt();

	if (operation_choice == 1) {
	    System.out.print("To 1) Savings, 2) Checkings ?: ");
	    int account_choice = input.nextInt();
	    if (account_choice == 1) {
		System.out.print("Amount: ");
		double amount = input.nextDouble();
		savings += amount;
	    }
	    else if (account_choice == 2) {
		System.out.print("Amount: ");
		double amount = input.nextDouble();
		checkings += amount;
	    }
	    else {
		System.out.print("Unknown account number.");
		input.close();
		return;
	    }
	}
	else if (operation_choice == 2) {
	    System.out.print("From 1) Savings, 2) Checkings ?: ");
	    int account_choice = input.nextInt();
	    if (account_choice == 1) {
		System.out.print("Amount: ");
		double amount = input.nextDouble();
		if (savings - amount < 0) {
		    System.out.println("Withdraw amount exceeds savings balance.");
		    input.close();
		    return;
		}
		savings -= amount;
	    }
	    else if (account_choice == 2) {
		System.out.print("Amount: ");
		double amount = input.nextDouble();
		if (savings - amount < 0) {
		    System.out.println("Withdraw amount exceeds savings balance.");
		    input.close();
		    return;
		}
		checkings -= amount;
	    }
	    else {
		System.out.print("Unknown account number.");
		input.close();
		return;
	    }
	}
	else if (operation_choice == 3) {
	    System.out.print("From 1) Savings, 2) Checkings ?: ");
	    int from_choice = input.nextInt();
	    System.out.print("To 1) Savings, 2) Checkings ?: ");
	    int to_choice = input.nextInt();

	    if (from_choice == to_choice) {
		System.out.println("Same account to transfer from and to");
		input.close();
		return;
	    }
	    else if (from_choice == 1) {
		System.out.print("Amount: ");
		double amount = input.nextDouble();
		if (savings - amount < 0) {
		    System.out.print("Transfer amount exceeds balance");
		    input.close();
		    return;
		}
		savings -= amount;
		checkings += amount;
	    }
	    else if (from_choice == 2) {
		System.out.print("Amount: ");
		double amount = input.nextDouble();
		if (checkings - amount < 0) {
		    System.out.print("Transfer amount exceeds balance");
		    input.close();
		    return;
		}
		checkings -= amount;
		savings += amount;
	    }
	    else {
		System.out.println("Unknown accounts chosen");
		input.close();
		return;
	    }
	}
	else {
	    System.out.println("Invalid operation choice");
	    input.close();
	    return;
	}
	input.close();
	System.out.println("Savings balance: " + savings);
	System.out.println("Checkings balance: " + checkings);
    }
}
```

</p>
</details>
v
## Write a program 
That reads in the name and salary of an employee. Here the salary will denote an hourly wage, such as $9.25. Then ask how many hours the employee worked in the past week. Be sure to accept fractional hours. Compute the pay. Any overtime work (over 40 hours per week) is paid at 150 percent of the regular wage. Print a paycheck for the employee.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;

public class P3_31 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Name: ");
	String name = input.next();
	System.out.print("Hourly wage: ");
	double hourly_wage =  input.nextDouble();
	System.out.print("Hours worked: ");
	double hours = input.nextDouble();
	input.close();
	double pay = 0;
	if (hours > 40) {
	    pay = hourly_wage * hours * 1.5;
	}
	else {
	    pay = hourly_wage * hours;
	}
	System.out.println(name + ", your pay is " + pay);
    }
}
```

</p>
</details>

## When you use an automated teller machine (ATM) 
with your bank card, you need to use a personal identification number (PIN) to access your account. If a user fails
more than three times when entering the PIN, the machine will block the card. Assume that the user’s PIN is “1234” and write a program that asks the user for the PIN no more than three times, and does the following:

- `If the user enters the right number, print a message saying, “Your PIN is correct”, and end the program.`

- ` If the user enters a wrong number, print a message saying, “Your PIN is incor rect” and, if you have asked for the PIN less than three times, ask for it again.`

- `If the user enters a wrong number three times, print a message saying “Your bank card is blocked” and end the program.`

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;

import com.sun.org.apache.xerces.internal.dom.CoreDocumentImpl;

public class P3_32 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	int user_pin = 1234;
	int pin_tries = 3;
	boolean correct_pin = false;
	System.out.print("User pin: ");
	int input_pin = input.nextInt();
	while (pin_tries > 1) {
	    if (input_pin == user_pin) {
		correct_pin = true;
		break;
	    }
	    System.out.println("Invalid pin. Try again");
	    pin_tries -= 1;
	    System.out.print("User pin: ");
	    input_pin = input.nextInt();
	}
	input.close();
	if (correct_pin) {
	    System.out.print("Correct PIN code.");	    
	}
	else {
	    System.out.print("Your card has been blocked.");
	}
    }
}
```

</p>
</details>

## Calculating 
The tip when you go to a restaurant is not difficult, but your restaurant wants to suggest a tip according to the service diners receive. Write a program that calculates a tip according to the diner’s satisfaction as follows:

- Ask for the diners’ satisfaction level using these ratings: 1 = Totally satisfied, 2 = Satisfied, 3 = Dissatisfied.

- If the diner is totally satisfied, calculate a 20 percent tip.

- If the diner is satisfied, calculate a 15 percent tip.

- If the diner is dissatisfied, calculate a 10 percent tip.

- Report the satisfaction level and tip in dollars and cents.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P3_33 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Dinner satisfaction - 1)Totally satisfied, 2)Satisfied, 3)Dissatisfied");
	int dinner_satisfaction = input.nextInt();
	input.close();
	int tip = 0;
	switch (dinner_satisfaction) {
	case 1:
	    tip = 20;
	    break;
	case 2:
	    tip = 15;
	    break;
	
	case 3:
	    tip = 10;
	    break;
	    
	default:
	    System.out.println("Unknown number entered.");
	}
	System.out.printf("Your tip is %d percent", tip);
    }
}
```

</p>
</details>

## A supermarket awards coupons depending on how much a customer spends ongroceries.
For example, if you spend $50, you will get a coupon worth eight percent of that amount. The following table shows the percent used to calculate the coupon awarded for different amounts spent. Write a program that calculates and prints the
value of the coupon a person can receive based on groceries purchased. Here is a sample run: Please enter the cost of your groceries: 14 You win a discount coupon of $ 1.12. (8% of your purchase)

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P3_34 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Cost of your groceries: ");
	double groceries_cost = input.nextDouble();
	input.close();
	double discount = (groceries_cost < 10)? 0:
	    		  (groceries_cost < 61)? groceries_cost * 0.08:
	    		  (groceries_cost < 151)? groceries_cost * 0.10:
	    		  (groceries_cost < 211)? groceries_cost * 0.12:
	    		   groceries_cost * 0.14;
	System.out.println("Your discount is " + discount);
    }
}
```

</p>
</details>

