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

```

</p>
</details>

## Informacione personale

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java

```

</p>
</details>

## Informacione personale

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java

```

</p>
</details>

## Informacione personale

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java

```

</p>
</details>
