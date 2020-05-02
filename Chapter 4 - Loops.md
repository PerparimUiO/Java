💡 
### Write programs with loops that compute

     a.  The sum of all even numbers between 2 and 100 (inclusive).
     b.  The sum of all squares between 1 and 100 (inclusive).
     c.  All powers of 2 from 2 0 up to 2 20 .
     d.  The sum of all odd numbers between  a and  b (inclusive), where  a and  b are inputs.
     e.  The sum of all odd digits of an input. (For example, if the input is 32677, the sum would be 3 + 7 + 7 = 17.)



<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_01 {
    public static void main(String[] args) {
	double even_sum = 0;
	for (int i = 0; i < 101; i += 2) {
	    even_sum += i;
	}
	System.out.println("Evens sum: " + even_sum);
	
	double square_sum = 0;
	for (int i = 1; i < 101; i++) {
	    square_sum += i * i;	    
	}
	System.out.println("Squares sum: " + square_sum);
	
	double powers_sum = 0;
	for (int i = 0; i < 21; i++) {
	    powers_sum 	+= Math.pow(2, i);
	}
	System.out.println("Powers of 2 sum: " + powers_sum);
	
	
	Scanner input = new Scanner(System.in);
	System.out.print("Range a: ");
	int a_range = input.nextInt();
	System.out.print("Range b: ");
	int b_range = input.nextInt();
	double odd_sum = 0;
	for (int i = a_range; i <= b_range; i++) {
	    if (i % 2 == 0) {
		odd_sum += i;
	    }
	}
	System.out.println("Odd numbers in range a-b sum: " + odd_sum);
	
	System.out.print("Number: ");
	int number = input.nextInt();
	input.close();
	int odd_digits_sum = 0;
	while (number > 0) {
	    int digit = number % 10;
	    if (digit % 2 != 0) {
		odd_digits_sum += digit;
	    }
	    number /= 10;
	}
	System.out.printf("Sum of %s's odd digits: %f", number, odd_digits_sum);
    }
}
``` 

</p>
</details>

### Write programs that read a sequence of integer inputs and print

    a.  The smallest and largest of the inputs.
    b.  The number of even and odd inputs.
    c.  Cumulative totals. For example, if the input is 1 7 2 9, the program should print 1 8 10 19.
    d.  All adjacent duplicates. For example, if the input is 1 3 3 4 5 5 6 6 6 2, the  program should print 3 5 6.



<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_02A {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Number: ");
	double input_number = input.nextDouble();
	double smallest_number = input_number;
	double largest_number = input_number;
	System.out.print("Number: ");
	while (input.hasNextDouble()) {
	    System.out.print("Number: ");
	    input_number = input.nextDouble();
	    if (input_number < smallest_number) {
		smallest_number = input_number;
	    }
	    else if (input_number > largest_number) {
		largest_number = input_number;
	    }
	}
	System.out.println("Smallest number: " + smallest_number);
	System.out.println("Largest number: " + largest_number);
	input.close();
    }
}
``` 

</p>
</details>

###  2b. The number of even and odd inputs.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_02B {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	int odd_numbers = 0;
	int even_numbers = 0;
	System.out.print("Number: ");
	while (input.hasNextDouble()) {
	    double input_number = input.nextDouble();
	    if (input_number % 2 == 0) {
		even_numbers += 1;
	    }
	    else {
		odd_numbers += 1;
	    }
	    System.out.print("Number: ");
	}
	input.close();
	System.out.println("Odd numbers: " + odd_numbers);
	System.out.println("Even numbers: " + even_numbers);
    }
}
``` 

</p>
</details>

### 2c. Cumulative totals. 

For example, if the input is 1 7 2 9, the program should print 1 8 10 19.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;

public class P4_02C {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Numbers: ");
	double cumulative_sum = 0;
	String output_cumulative_sum = "";
	while (input.hasNextDouble()) {
	    double input_number = input.nextDouble();
	    cumulative_sum += input_number;
	    output_cumulative_sum += String.format("%s ", String.valueOf(cumulative_sum));
	}
	input.close();
	System.out.println(output_cumulative_sum);
    }
}

``` 

</p>
</details>

### 2d. All adjacent duplicates. 

For example, if the input is 1 3 3 4 5 5 6 6 6 2, the program should print 3 5 6.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_02D {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	String adjacent_duplicates = "";
	System.out.print("Number: ");
	double input_number = input.nextDouble();
	double previous = input_number;
	boolean first_input = true;
	while (input.hasNextDouble()) {
	    System.out.print("Number: ");
	    input_number = input.nextDouble();
	    if (first_input != true && input_number == previous) {
		adjacent_duplicates += String.format("%s ", input_number);
	    }
	    first_input = false;
	    previous = input_number;
	}
	input.close();
	System.out.println(adjacent_duplicates);
    }
}

``` 

</p>
</details>

### Write programs that read a line of input as a string and print

	d.  The number of digits in the string.
	e.  The positions of all vowels in the string.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_03D {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("String: ");
	String user_input = input.next();
	input.close();
	int string_digits = 0;
	for (int i = 0; i < user_input.length(); i++) {
	    char current_char = user_input.charAt(i);
	    if (Character.isDigit(current_char)) {
		string_digits += 1;
	    }
	}
	System.out.println("Number of digits: " + string_digits);
    }
}

import java.util.Scanner;
public class P4_03E {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("String: ");
	String input_string = input.next();
	input.close();
	String output = "";
	for (int i = 0; i < input_string.length(); i++) {
	    char current_letter = Character.toLowerCase(input_string.charAt(i));
	    if (current_letter == 'a' || current_letter == 'e' || current_letter == 'o'
                || current_letter == 'i' || current_letter == 'u') {
		output += String.format("%d ", i);
	    }
	}
	System.out.println("Positions of vowels: " + output);
    }
}

``` 

</p>
</details>


###  Complete the program in How To 4.1 on page 182. Your program should read twelve temperature values and print the month with the highest temperature.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_04 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	double max_temperature = 0;
	int max_temperature_month = 1;
	for (int i = 1; i <= 12; i++) {
	    System.out.printf("Month %d: ", i);
	    double input_temperature = input.nextDouble();
	    if (input_temperature > max_temperature) {
		max_temperature = input_temperature;
		max_temperature_month = i;
	    }
	}
	input.close();
	System.out.println("Max temperature month: " + max_temperature_month);
	System.out.println("Max temperature: " + max_temperature);
    }
}
``` 

</p>
</details>

### Write a program that reads a set of floating-point values. Ask the user to enter the values, then print

     • the average of the values.
     • the smallest of the values.
     • the largest of the values.
     • the range, that is the difference between the smallest and largest.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_05 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Sequence of numbers: ");
	boolean first = true;
	double min = 0;
	double max = 0;
	double sum = 0;
	int total_numbers = 0;
	while (input.hasNextDouble()) {
	    double number = input.nextDouble();
	    sum += number;
	    total_numbers += 1;
	    if (first) {
		min = number;
		max = number;
		first = false;
	    }
	    else {
		if (number > max) {
		    max = number;
		}
		if (number < min) {
		    min = number;
		}
	    }
	}
	input.close();
	double average = sum / total_numbers;
	double difference = Math.abs(max - min);
	System.out.println("Average: " + average);
	System.out.println("Smallest: " + min);
	System.out.println("Largest: " + max);
	System.out.println("Difference: " + difference);
    }
}
``` 

</p>
</details>

### Translate the following pseudocode for finding the minimum value from a set of inputs into a Python program.

     Set a Boolean variable "first" to true.
     While another value has been read successfully
         If first is true
             Set the minimum to the value.
             Set first to false.
         Else if the value is less than the minimum
             Set the minimum to the value.
     Print the minimum.


<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_06 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	boolean first = true;
	double minimum = 0;
	System.out.print("Sequence of numbers: ");
	while (input.hasNextDouble()) {
	    double value = input.nextDouble();
	    if (first) {
		minimum = value;
		first = false;
	    }
	    else if (value < minimum) {
		minimum = value;
	    }
	}
	input.close();
	System.out.println("Min value: " + minimum);
    }
}
``` 

</p>
</details>

### Translate the following pseudocode for randomly permuting the characters in a string into a Java program.

     Read a word.
     Repeat word.length() times
         Pick a random position i in the word, but not the last position.
         Pick a random position j > i in the word.
         Swap the letters at positions j and i.
     Print the word.
     
 To swap the letters, construct substrings as follows:
 Then replace the string with
 **`first + word.chartAt(j) + middle + word.charAt(i) + last`**

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_07 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Enter a word: ");
	String word = input.next();
	for (int n = 0; n < word.length(); n++) {
	    int i = (int) (Math.random() * word.length() - 1);
	    int j = (int) (Math.random() * (word.length() - i - 1)) + i + 1;
	    String first = word.substring(0, i);
	    String middle = word.substring(i + 1, j);
	    String last = word.substring(j + 1);
	    word = first + word.charAt(j) + middle + word.charAt(i) + last;
	}
	input.close();
	System.out.println("Permuted word: " + word);
    }
}

``` 

</p>
</details>

###  Write a program that reads a word and prints each character of the word on a separate line. For example, if the user provides the input  "Perparim" , the program prints:

     P
     e
     r
     p
     a
     r
     i
     m

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_08 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Word: ");
	String word = input.next();
	input.close();
	for (int i = 0; i < word.length(); i++) {
	    System.out.println(word.charAt(i));
	}
    }
}
``` 

</p>
</details>

###  Write a program that reads a word and prints the word in reverse. For example, if the  user provides the input  "Perparim" , the program prints:

     mirapreP   

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_09 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Word: ");
	String word = input.next();
	input.close();
	StringBuilder new_word = new StringBuilder(word);
	word = new_word.reverse().toString();
	System.out.println("Reverse: " + word);
    }
}
``` 

</p>
</details>

###  Write a program that reads a word and prints the number of vowels in the word. For this exercise, assume that  `a e i o u y` are vowels. For example, if the user provides the input "Harry", the program prints  `2 vowels`.
   

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_10 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Word: ");
	String word = input.next();
	input.close();
	int n_vowels = 0;
	for (int i = 0; i < word.length(); i++) {
	    char current_letter = Character.toLowerCase(word.charAt(i));
	    if (current_letter == 'a' || current_letter == 'e' || current_letter == 'o'
                || current_letter == 'i' || current_letter == 'u' || current_letter == 'y') {
		n_vowels += 1;
	    }
	}
	System.out.println("Number of vowels: " + n_vowels);
    }
}
``` 

</p>
</details>

###  Write a program that reads a word and prints the number of syllables in the word.  For this exercise, assume that syllables are determined as follows: Each sequence of  adjacent vowels  `a e i o u y`, except for the last  e in a word, is a syllable. However, if  that algorithm yields a count of 0, change it to 1. For example,

     Word 	Syllables
     Harry 	2
     hairy 	2
     hare 	1
     the  	1   

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_11 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Word: ");
	String word = input.next();
	input.close();
	int n_syllables = 0;
	boolean syllable = false;
	for (int i = 0; i < word.length(); i++) {
	    char current_letter = Character.toLowerCase(word.charAt(i));
	    if (current_letter == 'a' || (current_letter == 'e' && i != word.length() - 1)
		|| current_letter == 'i' || current_letter == 'o' || current_letter == 'u'
		|| current_letter == 'y') {
		if (!syllable) {
		   n_syllables += 1;
		   syllable = true;
		}
		else {
		    syllable = false;
		}
	    }
	}
	n_syllables = (n_syllables > 0)? n_syllables: 1;
	System.out.printf("%d syllable%s", n_syllables, (n_syllables > 1)? "s" : "");
    }
}
``` 

</p>
</details>

### Write a program that reads a word and prints all substrings, sorted by length. For  example, if the user provides the input `"rum"`, the program prints:

     r
     u
     m
     ru
     um
     rum
   

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_12 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Word: ");
	String word = input.next();
	input.close();
	for (int length = 1; length <= word.length(); length++) {
	    for (int pos = 0; pos <= word.length() - length; pos++) {
		System.out.println(word.substring(pos, pos + length));
	    }
	}
    }
}

``` 

</p>
</details>

### Write a program that prints all power of 2 from 2 of power 0 up to 2 of power 20  

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P4_13 {
    public static void main(String[] args) {
	for (int i = 0; i < 21; i++) {
	    System.out.println(Math.pow(2, i));
	}
    }
}
``` 

</p>
</details>

### Write a program that reads an integer value and prints all of its binary digits in  reverse order: Print the remainder  number % 2 , then replace the number with  number //  2 . Keep going until the number is 0. For example, if the user provides the input 13,  the output should be

     1
     0
     1
     1   

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_14 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Number: ");
	int number = input.nextInt();
	input.close();
	while (number > 0) {
	    System.out.println(number % 2);
	    number /= 2;
	}
    }
}

``` 

</p>
</details>

### Mean and standard deviation. Write a program that reads a set of floating-point data  values. Choose an appropriate mechanism for prompting for the end of the data set.  When all values have been read, print out the count of the values, the aver age, and  the standard deviation.   

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_15 {
    public static void main(String[] args ) {
	Scanner input = new Scanner(System.in);
	System.out.print("Series of numbers: ");
	int count = 0;
	double sum = 0;
	double sum_squares = 0;
	while (input.hasNextDouble()) {
	    double number = input.nextDouble();
	    sum += number;
	    sum_squares += number * number;
	    count += 1;
	}
	input.close();
	System.out.println("Total count: " + count);
	System.out.println("Average: " + sum / count);
	
	double standard_deviation = Math.sqrt((sum_squares - Math.pow(sum, 2) / count) / (count-1));
	System.out.println("Standard deviation: " + standard_deviation);
    }
}
``` 

</p>
</details>

### The Fibonacci numbers.  Reformulate that as

     fold1 = 1
     fold2 = 1
     fnew = fold1 + fold2
     
After that, discard `fold2`, which is no longer needed, and set `fold2` to `fold1` and `fold1` to `fnew`. Repeat an appropriate number of times.  Implement a program that prompts the user for an integer n and prints the nth  Fibonacci number, using the above algorithm.   

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_16 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Number: ");
	int number = input.nextInt();
	input.close();
	int fold1 = 1;
	int fold2 = 1;
	
	if (number >= 1) {
	    System.out.println("Fib 1 = " + fold1);
	}
	if (number >= 2) {
	    System.out.println("Fib 2 = " + fold2);
	}
	
	for (int i = 3; i <= number; i++) {
	    int fnew = fold1 + fold2;
	    System.out.println("Fib " + i + " = " + fnew);
	    fold2 = fold1;
	    fold1 = fnew;
	}
    }

``` 

</p>
</details>

### `Factoring of integers`. Write a program that asks the user for an integer and then  prints out all its factors. For example, when the user enters 150, the program should print

     2
     3
     5
     5
   

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_17 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Number: ");
	int number = input.nextInt();
	input.close();
	int factor = 2;
	while (number > 1) {
	    if (number % factor == 0) {
		System.out.println(factor);
		number /= factor;
	    }
	    else {
		factor += 1;
	    }
	}
    }
}
``` 

</p>
</details>

### `Prime numbers`. Write a program that prompts the user for an integer and then prints  out all prime numbers up to that integer. For example, when the user enters 20, the  program should print

     2
     3
     5
     7
     11
     13
     17
     19
     
 Recall that a number is a prime number if it is not divisible by any number except 1
 and itself.
   

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_18 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Number: ");
	int number = input.nextInt();
	input.close();
	for (int current_number = 2; current_number <= number; current_number++) {
	    boolean prime = true;
	    int test_number = 2;
	    while (prime && test_number < current_number) {
		if (current_number % test_number == 0) {
		    prime = false;		    
		}
		test_number += 1;
	    }
	    if (prime) {
		System.out.println(current_number);
	    }
	}
    }
}
``` 

</p>
</details>

### Write a program that prints a multiplication table, like this:

     1    2   3   4   5   6   7   8   9   10
     2    4   6   8   10  12  14  16  18  20
     3    6   9   12  15  18  21  24  27  30
     . . .
     10   20  30  40  50  60  70  80  90  100 
   

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P4_19 {
    public static void main(String[] args) {
	for (int i = 1; i < 11; i++) {
	    for (int j = 1; j < 11; j++) {
		int product = i * j;
		System.out.printf("%4d", product);
	    }
	    System.out.println();
	}
    }
}
``` 

</p>
</details>

### Write a program that reads an integer and displays, using asterisks, a filled and hol-low square, placed next to each other. For example if the side length is 5, the pro gram  should display

     *****   *****
     *****   *   *
     *****   *   *
     *****   *   *
     *****   *****
   

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_20 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Number: ");
	int side_length = input.nextInt();
	input.close();
	for (int row = 1; row <= side_length; row++) {
	    // first square
	    for (int column = 1; column <= side_length; column++) {
		System.out.print("*");
	    }
	    System.out.print(" ");
	    // second square
	    for (int column = 1; column <= side_length; column++) {
		if (column == 1 || column == side_length || row == 1 || row == side_length) {
		    System.out.print("*");
		}
		else {
		    System.out.print(" ");
		}
	    }
	    System.out.println();
	}
    }
}

``` 

</p>
</details>

### Write a program that reads an integer and displays, using asterisks, a filled diamond of the given side length. For example, if the side length is 4, the program should display

     *
    ***
   *****
  *******
   *****
    ***
     *
   

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;

public class P4_21 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Side length: ");
	int side_length = input.nextInt();
	input.close();
	int max_width = side_length * 2 - 1;
	int half_width = max_width / 2;
	int dot_num = 1;
	// top half
	for (int i = 0; i < side_length; i++) {
	    for (int j = 0; j < half_width; j++) {
		System.out.print(" ");
	    }
	    for (int j = 0; j < dot_num; j++) {
		System.out.print("*");
	    }
	    System.out.println();
	    dot_num += 2;
	    half_width -= 1;
	}
	// bottom half
	dot_num = max_width - 2;
	half_width = 1;
	for (int i = 0; i < side_length; i++) {
	    for (int j = 0; j < half_width; j++) {
		System.out.print(" ");
	    }
	    for (int j = 0; j < dot_num; j++) {
		System.out.print("*");
	    }
	    System.out.println();
	    dot_num -= 2;
	    half_width += 1;
	}
    }
}
``` 

</p>
</details>

### `The game of Nim`. 

`This is a well-known game with a number of variants. The following  variant has an interesting winning strategy. Two players alternately take marbles from a pile. In each move, a player chooses how many marbles to take. The player must take at least one but at most half of the marbles. Then the other player takes a turn. The player who takes the last marble loses.
Write a program in which the computer plays against a human opponent. Generate a random integer between 10 and 100 to denote the initial size of the pile. Generate a random integer between 0 and 1 to decide whether the computer or the human takes
the first turn. Generate a random integer between 0 and 1 to decide whether the computer plays smart or stupid. In stupid mode the computer simply takes a random legal value (between 1 and n/2) from the pile whenever it has a turn. In smart mode
the computer takes off enough marbles to make the size of the pile a power of two minus 1—that is, 3, 7, 15, 31, or 63. That is always a legal move, except when the size of the pile is currently one less than a power of two. In that case, the computer makes a random legal move. You will note that the computer cannot be beaten in smart mode when it has the first move, unless the pile size happens to be 15, 31, or 63. Of course, a human player who has the first turn and knows the win ning strategy can win against the computer.`
   

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_22 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	int size_of_pile = (int) (Math.random() * 91) + 10;
	int current_turn = (int) (Math.random() * 2);
	int smart_or_stupid = (int) (Math.random() * 2);
	while (size_of_pile > 0) {
	    System.out.println("Current number of marlbes in pile: " +  size_of_pile);
	    int marbles_to_remove = 0;
	    if (current_turn == 0) {
		if (smart_or_stupid == 1 || (size_of_pile == 1 || size_of_pile == 3
                    || size_of_pile == 7 || size_of_pile == 15 || size_of_pile == 31
                    || size_of_pile == 63)) {
		    marbles_to_remove = (int) (Math.random() * (size_of_pile / 2 + 1)) + 1;
		}
		else {
		    if (size_of_pile > 63) {
			marbles_to_remove = size_of_pile - 63;
		    }
		    else if (size_of_pile > 31) {
			marbles_to_remove = size_of_pile - 31;
		    }
		    else if (size_of_pile > 15) {
			marbles_to_remove = size_of_pile - 15;
		    }
		    else if (size_of_pile > 7) {
			marbles_to_remove = size_of_pile - 7;
		    }
		    else if (size_of_pile > 3) {
			marbles_to_remove = size_of_pile - 3;
		    }
		    else {
			marbles_to_remove = size_of_pile - 1;
		    }
		}
		System.out.println("Computer removes " + marbles_to_remove  + " marble" + ((marbles_to_remove > 1)? "s": ""));
		current_turn = 1;
	    }
	    else {
		do {
		    System.out.println("How many marbles do you want to remove: ");
		    marbles_to_remove = input.nextInt();
		} while ((marbles_to_remove != 1) && (marbles_to_remove <= 0 || marbles_to_remove > size_of_pile / 2));
		current_turn = 0;
	    }
	    size_of_pile -= marbles_to_remove;
	}
	input.close();
	if (current_turn == 0) {
	    System.out.println("Human took last marble, computer wins!");
	}
	else {
	    System.out.println("Computer took the last  marble, human wins!");
	}
    }
}
``` 

</p>
</details>

### `The Drunkard’s Walk`.

`A drunkard in a grid of streets randomly picks one of four directions and stumbles to the next intersection, then again randomly picks one of four directions, and so on. You might think that on average the drunkard doesn’t move very far because the choices cancel each other out, but that is actually not the case. Represent locations as integer pairs (x, y). Implement the drunkard’s walk over 100 intersections, starting at (0, 0), and print the ending location.`   

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_23 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Initial location X: ");
	int loc_x = input.nextInt();
	System.out.print("Initial location Y: ");
	int loc_y = input.nextInt();
	System.out.printf("Initial location is (%d, %d)\n", loc_x, loc_y);
		
	System.out.print("Number of steps: ");
	int number_of_steps = input.nextInt();
	input.close();
	for (int i = 0; i < number_of_steps; i++) {
	    int direction = (int) (Math.random() * 4);
	    if (direction == 0) {
		loc_x += 1;
		System.out.println("Moved east");
	    }
	    else if (direction == 1) {
		loc_x -= 1;
		System.out.println("Moved west");
	    }
	    else if (direction == 2) {
		loc_y += 1;
		System.out.println("Moved north");
	    }
	    else if (direction == 3) {
		loc_y -= 1;
		System.out.println("Moved south");
	    }
	}
	System.out.printf("Final location: (%d, %d)", loc_x, loc_y);
    }
}
``` 

</p>
</details>

### `Currency conversion`. Write a program that first asks the user to type today’s price for one dollar in Japanese yen, then reads U.S. dollar values and converts each to yen. Use 0 as a sentinel.   

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_27 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Today's price for one USD to JPY: ");
	double exchange_rate = input.nextDouble();
	System.out.print("USD: ");
	while (input.hasNextDouble()) {
	   double dollars = input.nextDouble();
	   if (dollars == 0) {
	       break;
	   }
	   System.out.println("Japanese yen: " + (dollars * exchange_rate));
	}
	input.close();
    }
}
``` 

</p>
</details>

### Write a program that first asks the user to type in today’s price of one dollar in Jap­anese yen, then reads U.S. dollar values and converts each to Japanese yen. Use 0 as the sentinel value to denote the end of dollar inputs. Then the program reads a sequence of yen amounts and converts them to dollars. The second sequence is ter­minated by another zero value.   

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_28 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Today's price for one USD to JPY: ");
	double exchange_rate = input.nextDouble();
	System.out.print("USD: ");
	while (input.hasNextDouble()) {
	   double dollars = input.nextDouble();
	   if (dollars == 0) {
	       break;
	   }
	   System.out.println("Japanese yen: " + (dollars * exchange_rate));
	   System.out.print("USD: ");
	}
	System.out.print("JPY: ");
	while (input.hasNextDouble()) {
	    double yen = input.nextDouble();
	    if (yen == 0) {
		break;
	    }
	    System.out.printf("United states dollars: %.2f\n", (yen / exchange_rate));
	    System.out.print("JPY: ");
	}
	input.close();
    }
}

``` 

</p>
</details>

### Your company has shares of stock it would like to sell when their value exceeds a certain target price. Write a program that reads the target price and then reads the current stock price until it is at least the target price. Your program should read a sequence of floating-point values from standard input. Once the minimum is reached, the program should report that the stock price exceeds the target price.   

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_29 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Target price: ");
	double target_price = input.nextDouble();
	System.out.print("Stock price: ");
	double stock_price = 0;
	while (stock_price < target_price) {
	    stock_price = input.nextDouble();
	    if (stock_price >= target_price) {
		System.out.println("Minimum reached. Stock price exceeds target price");
		break;
	    }
	    System.out.print("Stock price: ");
	}
	input.close();
    }
}
``` 

</p>
</details>

###  Write an application to pre-sell a limited number of cinema tickets. Each buyer can buy as many as 4 tickets. No more than 100 tickets can be sold. Implement a pro- gram called TicketSeller that prompts the user for the desired number of tickets and then displays the number of remaining tickets. Repeat until all tickets have been sold, and then display the total number of buyers.   

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_30 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	int available_tickets = 100;
	int n_buyers = 0;
	do {
	    System.out.print("Tickets to buy: ");
	    int tickets_to_buy = input.nextInt();
	    if (tickets_to_buy < 5 && tickets_to_buy > 0) {
		System.out.println("Bought " + tickets_to_buy + " ticket" + ((tickets_to_buy > 1)? "s": ""));
		available_tickets -= tickets_to_buy;
		n_buyers += 1;
	    }
	    else {
		System.out.println("Each buyer can buy not more than 4 tickets.");
	    }
	    System.out.println("Available tickets: " + available_tickets);
	} while (available_tickets > 0);	
	input.close();
	System.out.println("Tickets sold out!");
	System.out.println("Total buyers: " + n_buyers);
    }
}

``` 

</p>
</details>

###  You need to control the number of people who can be in an oyster bar at the same time. Groups of people can always leave the bar, but a group cannot enter the bar if they would make the number of people in the bar exceed the maximum of 100 occupants. Write a program that reads the sizes of the groups that arrive or depart. Use negative numbers for departures. After each input, display the current number of occupants. As soon as the bar holds the maximum number of people, report that the bar is full and exit the program.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;

public class P4_31 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	final int MAXIMUM_PEOPLE = 100;
	int current_people = 0;
	do {
	    System.out.print("Size of group entering: ");
	    int entering_people = input.nextInt();
	    if (current_people + entering_people <= MAXIMUM_PEOPLE) {
		System.out.println("Welcome in !");
		current_people += entering_people;
	    }
	    else {
		System.out.println("Group exceeds bar capacity.");
	    }
	    System.out.println("~~~Currently " + current_people + " in the oyster bar");
	} while (current_people < MAXIMUM_PEOPLE);
	input.close();
	System.out.println("Oyster bar is full.");
    }
}
``` 

</p>
</details>

###  Credit Card Number Check. The last digit of a credit card number is the check digit, which protects against transcription errors such as an error in a single digit or switching two digits. The following method is used to verify actual credit card  numbers but, for simplicity, we will describe it for numbers with 8 digits instead  of 16:

     • Starting from the rightmost digit, form the sum of every other digit. For example, if the credit card number is 43589795, then you form the sum 5 + 7 + 8 + 3 = 23.
     
     • Double each of the digits that were not included in the preceding step. Add all digits of the resulting numbers. For example, with the number given above, doubling the digits, starting with the next-to-last one, yields 18 18 10 8. Adding      all digits in these values yields 1 + 8 + 1 + 8 + 1 + 0 + 8 = 27.
     
     • Add the sums of the two preceding steps. If the last digit of the result is 0, the number is valid. In our case, 23 + 27 = 50, so the number is valid.
     
 Write a program that implements this algorithm. The user should supply an 8-digit number, and you should print out whether the number is valid or not. If it is not  valid, you should print out the value of the check digit that would make the number valid. 
 
<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P4_32 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("8-digit credit card number: ");
	int credit_card_number = input.nextInt();
	input.close();
	int digit_7 = credit_card_number % 10;
	credit_card_number /= 10;
	int digit_6 = credit_card_number % 10;
	credit_card_number /= 10;
	int digit_5 = credit_card_number % 10;
	credit_card_number /= 10;
	int digit_4 = credit_card_number % 10;
	credit_card_number /= 10;
	int digit_3 = credit_card_number % 10;
	credit_card_number /= 10;
	int digit_2 = credit_card_number % 10;
	credit_card_number /= 10;
	int digit_1 = credit_card_number % 10;
	credit_card_number /= 10;
	int digit_0 = credit_card_number % 10;
	
	int part1 = digit_7 + digit_5 + digit_3 + digit_1;
	// part 2
	int twice = 2 * digit_6;
	int part2 = 0;
	part2 = part2 + ((twice % 10) + (twice / 10));
	twice = 2 * digit_4;
	part2 = part2 + ((twice % 10) + (twice / 10));
	twice = 2 * digit_2;
	part2 = part2 + ((twice % 10) + (twice / 10));
	twice = 2 * digit_0;
	part2 = part2 + ((twice % 10) + (twice / 10));
	
	int total = part1 + part2;
	int remaining = total % 10;
	if (remaining == 0) {
	    System.out.println("Card number is valid");
	}
	else {
	    System.out.println("Card number is invaid");
	    int check_digit = 0;
	    if (digit_7 - remaining < 0) {
		check_digit = digit_7 + (10 - remaining);
	    }
	    else {
		check_digit = digit_7 - remaining;
	    }
	    System.out.println("Check digit should be: " + check_digit);
	}
    }
}
``` 

</p>
</details>

