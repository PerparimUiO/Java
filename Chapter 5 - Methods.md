#### Write the following methods and provide a program to test them:

  a. `double smallest(double x, double y, double z)` , returning the smallest of the arguments
  
  b. `double average(double x, double y, double z)` , returning the average of the arguments

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P5_01 {
    public static double smallest(double x, double y, double z) {
	return ((x <= y && x < z) || (x < y && x <= z))? x :
		(y < x && y < z)? y: z;
    }
    public static double average(double x, double y, double z) {
	return (x + y + z) / 3;
    }
}
```  

</p>
</details>

#### Write the following methods and provide a program to test them:

a. `boolean allTheSame(double x, double y, double z)`, returning true if the arguments are all the same

b. `boolean allDifferent(double x, double y, double z)`, returning true if the arguments are all different

c. `boolean sorted(double x, double y, double z)`, returning true if the arguments are sorted, with the largest one coming first

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P5_02 {
    public static boolean allTheSame(double x, double y, double z) {
	return x == y && y == z;
    }
    public static boolean allDifferent(double x, double y, double z) {
	return x != y && x != z && y != z;
    }
    public static boolean sorted(double x, double y, double z) {
	return ((x > y && y > z) || (x >= y && y > z));
    }
}
```  

</p>
</details>

#### Write the following methods.

	a. int firstDigit(int n) , returning the first digit of the argument
	b. int lastDigit(int n) , returning the last digit of the argument
	c. int digits(int n) , returning the number of digits of the argument

For example, firstDigit(1729) is 1, lastDigit(1729) is 9, and digits(1729) is 4 Provide a program that tests your methods. 

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P5_03 {
    
    public static int firstDigit(int number) {
	   char firstDigit = Integer.toString(number).charAt(0);
	   return Character.getNumericValue(firstDigit);
    }

    public static int lastDigit(int number) {
	   return number % 10;
    }

    public static int digits(int number) {
	   return Integer.toString(number).length();
    }
}
```  

</p>
</details>

#### Write a method `public static String middle(String str)` that `returns a string` containing the middle character in str if the length of str is odd, or the two middle characters if the length is even. For example, middle("middle") returns "dd" . 

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P5_04 {
    public static String middle(String sentence) {
	String output = "";
	int sentence_middle = sentence.length() / 2;
	if (sentence.length() % 2 == 0) {
	    output = sentence.substring(sentence_middle - 1, sentence_middle + 1);
	}
	else {
	    output = sentence.substring(sentence_middle, sentence_middle + 1);
	}
	return output;
    }
}
```  

</p>
</details>

#### Write a method public static String repeat(String str, int n) that returns the string str repeated n times. For example, repeat("ho", "hohoho").

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P5_05 {
    public static String repeat(String sentence, int times) {
	String output = "";
	for (int i = 0; i < times; i++) {
	    output += sentence;
	}
	return output;
    }
}
```  

</p>
</details>

#### Write a method `public static int countVowels(String str)` that `returns a count of all vowels` in the `string str`. Vowels are the letters a, e, i, o, and u, and their upper­case variants.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P5_06 {
    public static int countVowels(String sentence) {
		int vowels_count = 0;

		for (int i = 0; i < sentence.length(); i++) {
		    char current_char = Character.toLowerCase(sentence.charAt(i));
		    if (current_char == 'a' || current_char == 'e' || current_char == 'o'
		        || current_char == 'i' || current_char == 'u' || current_char == 'y') {
				vowels_count += 1;
		    }
		}
		return vowels_count;
    }
}
```  

</p>
</details>

#### Write a method `public static int countWords(String str)` that returns a count of all words in the string str . Words are separated by spaces. For example, count­Words("Mary had a little lamb") should return 5

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P5_07 {
    public static int countWords(String sentence) {
		sentence = sentence.trim();
		int wordsCount = 0;
		
		if (!sentence.isEmpty()) {
		    wordsCount += 1;
		    for (int i = 1; i < sentence.length() - 1; i++) {
				if (sentence.charAt(i) == ' ' && sentence.charAt(i + 1) != ' ') {
				    wordsCount += 1;
				}
		    }
		}
		return wordsCount;
    }
}

```  

</p>
</details>

#### It is a well-known phenomenon that most people are easily able to read a text whose words have two characters flipped, provided the first and last letter of each word are not changed. For example,
	I dn’ot gvie a dman for a man taht can olny sepll a wrod one way. (Mrak Taiwn)
	
Write a method`String scramble(String word)`that constructs a scrambled version of a given word, ran­domly flipping two characters other than the first and last one. Then write a program that reads words and prints the scrambled words.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P5_08 {
    public static String scramble(String word) {
        if (word.length() > 3) {
            int pos1 = (int) (Math.random() * (word.length() - 3)) + 1;
            int pos2 = (int) (Math.random() * (word.length() - pos1 - 2)) + pos1 + 1;

            if (pos2 >= word.length() - 1) {
                System.out.println(pos1 + " " + pos2);
                System.exit(0);
            }
            return word.substring(0, pos1) + word.charAt(pos2) + word.substring(pos1 + 1, pos2)
                    + word.charAt(pos1) + word.substring(pos2 + 1);
        }
        else {
            return word;
        }
    }
}
```  

</p>
</details>

#### Write methods

	public static double sphereVolume(double r)
	public static double sphereSurface(double r)
	public static double cylinderVolume(double r, double h)
	public static double cylinderSurface(double r, double h)
	public static double coneVolume(double r, double h)
	public static double coneSurface(double r, double h)

that compute the volume and surface area of a sphere with radius r , a cylinder with a circular base with radius r and height h , and a cone with a circular base with radius r and height h . Then write a program that prompts the user for the values of r and h , calls the six methods, and prints the results. 

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P5_09 {
    public static double sphereVolume(double radius) {
        return 4 / 3 * Math.PI * Math.pow(radius, 3);
    }
    public static double sphereSurface(double radius) {
        return 4 * Math.PI * radius * radius;
    }
    public static double cylinderVolume(double radius, double height) {
        return Math.PI * radius * radius * height;
    }
    public static double cylinderSurface(double radius, double height) {
        return 2 * Math.PI * radius * (radius + height);
    }
    public static double coneVolume(double radius, double height) {
        return 1 / 3 * Math.PI * radius * radius * height;
    }
    public static double coneSurface(double radius, double height) {
        return Math.PI * radius * (radius + Math.sqrt(radius * radius + height * height));
    }
}
```  

</p>
</details>

#### Write a method

	public static double readDouble(String prompt)

that displays the prompt string, followed by a space, reads a floating-point number in, and returns it. Here is a typical usage:

	salary = readDouble("Please enter your salary:");
	percentageRaise = readDouble("What percentage raise would you like?");

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P5_10 {
    public static double readDouble(String prompt) {
        Scanner input = new Scanner(System.in);
        System.out.print(prompt + " ");
        double input_number = input.nextDouble();
        input.close();
        return input_number;
    }
}

```  

</p>
</details>

#### Enhance the intName method so that it works correctly for values < 1,000,000,000.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;

public class P5_11 {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        System.out.print("Please enter a positive integer < 1000: ");
        int input = in.nextInt();
        System.out.println(intName(input));
        in.close();
    }

    /**
     * Turns a number into its English name.
     * 
     * @param number
     *            a positive integer < 1,000
     * @return the name of the number (e.g. "two hundred seventy four")
     */
    public static String intName(int number) {
        int part = number; // The part that still needs to be converted
        String name = ""; // The name of the number

        if (part >= 1000000) {
            name = digitName(part / 1000000) + " million";
            part %= 1000000;
        }
        
        if (part >= 1000) {
            name = digitName(part / 100) + " thousand";
            part %= 1000;
        }
        if (part >= 100) {
            name = digitName(part / 100) + " hundred";
            part = part % 100;
        }

        if (part >= 20) {
            name = name + " " + tensName(part);
            part = part % 10;
        } else if (part >= 10) {
            name = name + " " + teenName(part);
            part = 0;
        }

        if (part > 0) {
            name = name + " " + digitName(part);
        }

        return name;
    }

    /**
     * Turns a digit into its English name.
     * 
     * @param digit
     *            an integer between 1 and 9
     * @return the name of digit ("one" ... "nine")
     */
    public static String digitName(int digit) {
        if (digit == 1) {
            return "one";
        }
        if (digit == 2) {
            return "two";
        }
        if (digit == 3) {
            return "three";
        }
        if (digit == 4) {
            return "four";
        }
        if (digit == 5) {
            return "five";
        }
        if (digit == 6) {
            return "six";
        }
        if (digit == 7) {
            return "seven";
        }
        if (digit == 8) {
            return "eight";
        }
        if (digit == 9) {
            return "nine";
        }
        return "";
    }

    /**
     * Turns a number between 10 and 19 into its English name.
     * 
     * @param number
     *            an integer between 10 and 19
     * @return the name of the given number ("ten" ... "nineteen")
     */
    public static String teenName(int number) {
        if (number == 10) {
            return "ten";
        }
        if (number == 11) {
            return "eleven";
        }
        if (number == 12) {
            return "twelve";
        }
        if (number == 13) {
            return "thirteen";
        }
        if (number == 14) {
            return "fourteen";
        }
        if (number == 15) {
            return "fifteen";
        }
        if (number == 16) {
            return "sixteen";
        }
        if (number == 17) {
            return "seventeen";
        }
        if (number == 18) {
            return "eighteen";
        }
        if (number == 19) {
            return "nineteen";
        }
        return "";
    }

    /**
     * Gives the name of the tens part of a number between 20 and 99.
     * 
     * @param number
     *            an integer between 20 and 99
     * @return the name of the tens part of the number ("twenty" ... "ninety")
     */
    public static String tensName(int number) {
        if (number >= 90) {
            return "ninety";
        }
        if (number >= 80) {
            return "eighty";
        }
        if (number >= 70) {
            return "seventy";
        }
        if (number >= 60) {
            return "sixty";
        }
        if (number >= 50) {
            return "fifty";
        }
        if (number >= 40) {
            return "forty";
        }
        if (number >= 30) {
            return "thirty";
        }
        if (number >= 20) {
            return "twenty";
        }
        return "";
    }
}

```  

</p>
</details>

#### Enhance the intName method so that it works correctly for negative values and zero.
Caution: Make sure the improved method doesn’t print 20 as "twenty zero"

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java

```  

</p>
</details>

#### Informacion4 

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;

public class P5_12 {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        System.out.print("Please enter a positive integer < 1000: ");
        int input = in.nextInt();
        System.out.println(intName(input));
        in.close();
    }

    /**
     * Turns a number into its English name.
     * 
     * @param number
     *            a positive integer < 1,000
     * @return the name of the number (e.g. "two hundred seventy four")
     */
    public static String intName(int number) {
        if (number == 0) {
            return "zero";
        }
        int part = number; // The part that still needs to be converted
        String name = ""; // The name of the number

        if (part < 0) {
            name = "negative";
            part = -part;
        }
        if (part >= 100) {
            name = digitName(part / 100) + " hundred";
            part = part % 100;
        }

        if (part >= 20) {
            name = name + " " + tensName(part);
            part = part % 10;
        } else if (part >= 10) {
            name = name + " " + teenName(part);
            part = 0;
        }

        if (part > 0) {
            name = name + " " + digitName(part);
        }

        return name;
    }

    /**
     * Turns a digit into its English name.
     * 
     * @param digit
     *            an integer between 1 and 9
     * @return the name of digit ("one" ... "nine")
     */
    public static String digitName(int digit) {
        if (digit == 1) {
            return "one";
        }
        if (digit == 2) {
            return "two";
        }
        if (digit == 3) {
            return "three";
        }
        if (digit == 4) {
            return "four";
        }
        if (digit == 5) {
            return "five";
        }
        if (digit == 6) {
            return "six";
        }
        if (digit == 7) {
            return "seven";
        }
        if (digit == 8) {
            return "eight";
        }
        if (digit == 9) {
            return "nine";
        }
        return "";
    }

    /**
     * Turns a number between 10 and 19 into its English name.
     * 
     * @param number
     *            an integer between 10 and 19
     * @return the name of the given number ("ten" ... "nineteen")
     */
    public static String teenName(int number) {
        if (number == 10) {
            return "ten";
        }
        if (number == 11) {
            return "eleven";
        }
        if (number == 12) {
            return "twelve";
        }
        if (number == 13) {
            return "thirteen";
        }
        if (number == 14) {
            return "fourteen";
        }
        if (number == 15) {
            return "fifteen";
        }
        if (number == 16) {
            return "sixteen";
        }
        if (number == 17) {
            return "seventeen";
        }
        if (number == 18) {
            return "eighteen";
        }
        if (number == 19) {
            return "nineteen";
        }
        return "";
    }

    /**
     * Gives the name of the tens part of a number between 20 and 99.
     * 
     * @param number
     *            an integer between 20 and 99
     * @return the name of the tens part of the number ("twenty" ... "ninety")
     */
    public static String tensName(int number) {
        if (number >= 90) {
            return "ninety";
        }
        if (number >= 80) {
            return "eighty";
        }
        if (number >= 70) {
            return "seventy";
        }
        if (number >= 60) {
            return "sixty";
        }
        if (number >= 50) {
            return "fifty";
        }
        if (number >= 40) {
            return "forty";
        }
        if (number >= 30) {
            return "thirty";
        }
        if (number >= 20) {
            return "twenty";
        }
        return "";
    }
}
```  

</p>
</details>

#### For some values (for example, 20), the intName method returns a string with a leading space (" twenty"). Repair that blemish and ensure that spaces are inserted only  when necessary. 
Hint: There are two ways of accomplishing this. Either ensure that  leading spaces are never inserted, or remove leading spaces from the result before  returning it.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;

public class P5_13 {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        System.out.print("Please enter a positive integer < 1000: ");
        int input = in.nextInt();
        System.out.println(intName(input));
        in.close();
    }

    /**
     * Turns a number into its English name.
     * 
     * @param number
     *            a positive integer < 1,000
     * @return the name of the number (e.g. "two hundred seventy four")
     */
    public static String intName(int number) {
        if (number == 0) {
            return "zero";
        }
        int part = number; // The part that still needs to be converted
        String name = ""; // The name of the number

        if (part < 0) {
            name = "negative";
            part = -part;
        }
        if (part >= 100) {
            name = digitName(part / 100) + " hundred";
            part = part % 100;
        }

        if (part >= 20) {
            name = name + " " + tensName(part);
            part = part % 10;
        } else if (part >= 10) {
            name = name + " " + teenName(part);
            part = 0;
        }

        if (part > 0) {
            name = name + " " + digitName(part);
        }
        return (name.charAt(0) == ' ') ? name.substring(1) : name;
    }

    /**
     * Turns a digit into its English name.
     * 
     * @param digit
     *            an integer between 1 and 9
     * @return the name of digit ("one" ... "nine")
     */
    public static String digitName(int digit) {
        if (digit == 1) {
            return "one";
        }
        if (digit == 2) {
            return "two";
        }
        if (digit == 3) {
            return "three";
        }
        if (digit == 4) {
            return "four";
        }
        if (digit == 5) {
            return "five";
        }
        if (digit == 6) {
            return "six";
        }
        if (digit == 7) {
            return "seven";
        }
        if (digit == 8) {
            return "eight";
        }
        if (digit == 9) {
            return "nine";
        }
        return "";
    }

    /**
     * Turns a number between 10 and 19 into its English name.
     * 
     * @param number
     *            an integer between 10 and 19
     * @return the name of the given number ("ten" ... "nineteen")
     */
    public static String teenName(int number) {
        if (number == 10) {
            return "ten";
        }
        if (number == 11) {
            return "eleven";
        }
        if (number == 12) {
            return "twelve";
        }
        if (number == 13) {
            return "thirteen";
        }
        if (number == 14) {
            return "fourteen";
        }
        if (number == 15) {
            return "fifteen";
        }
        if (number == 16) {
            return "sixteen";
        }
        if (number == 17) {
            return "seventeen";
        }
        if (number == 18) {
            return "eighteen";
        }
        if (number == 19) {
            return "nineteen";
        }
        return "";
    }

    /**
     * Gives the name of the tens part of a number between 20 and 99.
     * 
     * @param number
     *            an integer between 20 and 99
     * @return the name of the tens part of the number ("twenty" ... "ninety")
     */
    public static String tensName(int number) {
        if (number >= 90) {
            return "ninety";
        }
        if (number >= 80) {
            return "eighty";
        }
        if (number >= 70) {
            return "seventy";
        }
        if (number >= 60) {
            return "sixty";
        }
        if (number >= 50) {
            return "fifty";
        }
        if (number >= 40) {
            return "forty";
        }
        if (number >= 30) {
            return "thirty";
        }
        if (number >= 20) {
            return "twenty";
        }
        return "";
    }
}
```  

</p>
</details>

#### Write a recursive method`public static String reverse(String str)`that computes the reverse of a string. For example, reverse("flow") should return "wolf" . Hint: Reverse the substring starting at the second character, then add the first character at the end. For example, to reverse "flow" , first reverse "low" to "wol" , then add the "f" at the end. 

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P5_15 {
    public static String reverse(String sentence) {
        if (sentence.length() > 1) {
            return reverse(sentence.substring(1)) + sentence.charAt(0);
        }
        return sentence;
    }
}
```  

</p>
</details>

#### Write a recursive method

    public static boolean isPalindrome(String str)
    
that returns true if str is a palindrome, that is, a word that is the same when reversed. Examples of palin­drome are “deed”, “rotor”, or “aibohphobia”. Hint: A word is a palindrome if the first and last letters match and the remainder is also a palindrome.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P5_16 {
    public static boolean isPalindrome(String str) {
        if (str.length() <= 1) {
            return true;
        }
        else if (str.charAt(0) == str.charAt(str.length() - 1)) {
            return isPalindrome(str.substring(1, str.length() - 1));
        }
        else {
            return false;
        }
    }
}
```  

</p>
</details>

#### Use recursion to implement a method 

	public static boolean find(String str, Stringmatch) 
	
that tests whether match is contained in str : boolean b = find("Mississippi", "sip"); // Sets b to true 
Hint: If str starts with match , then you are done. If not, consider the string that you obtain by removing the first character.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P5_17 {
    public static boolean find(String str, String match) {
        if (str.length() < match.length()) {
            return false;
        }
        if (str.charAt(0) == match.charAt(0)) {
            boolean equal = true;
            for (int i = 0; i < match.length(); i++) {
                if (str.charAt(i) != match.charAt(i)) {
                    equal = false;
                }
            }
            if (equal) {
                return true;
            }
        }
        return find(str.substring(1), match);
    }
}
```  

</p>
</details>

#### Use recursion to determine the number of digits in an integer n . Hint: If n is < 10, it has one digit. Otherwise, it has one more digit than n / 10 .

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P5_18 {
    public static int numberOfDigits(int number) {
        if (number < 0) {
            return numberOfDigits(-number);
        }
        if (number < 10) {
            return 1;
        }
        else {
            return 1 + numberOfDigits(number / 10);
        }
    }
}
```  

</p>
</details>

#### Use recursion to compute a n , where n is a positive integer. Hint: If n is 1, then n = a. If n is even, then a n = (a n/2 ) 2 . Otherwise, a n = a × a n–1 .

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P5_19 {
    public static double power(double a, int n) {
        if (n == 0) {
            return 1;
        }
        if (n % 2 == 1) {
            return a * power(a, n-1);
        }
        return Math.pow(power(a, n / 2), 2);
    }
}
```  

</p>
</details>

#### Leap years. Write a method

    public static boolean isLeapYear(int year)
    
that tests whether a year is a leap year: that is, a year with 366 days. Exercise P3.28 describes how to test whether a year is a leap year. In this exercise, use multiple if statements and return statements to return the result as soon as you know it.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P5_20 {
    public static boolean isLeapYear(int year) {
        if (year % 400 == 0) {
            return true;
        }
        else if (year % 4 == 0 && year % 100 != 0) {
            return true;
        }
        return false;
    }
}
```  

</p>
</details>

#### In Exercise P3.26 you were asked to write a program to convert a number to its rep­resentation in Roman numerals. At the time, you did not know how to eliminate duplicate code, and as a consequence the resulting program was rather long. Rewrite that program by implementing and using the following method:

    public static String romanDigit(int n, String one, String five, String ten)
    
That method translates one digit, using the strings specified for the one, five, and ten values. You would call the method as follows:

    romanOnes = romanDigit(n % 10, “I”, “V”, “X”);
    n = n / 10;
    romanTens = romanDigit(n % 10, “X”, “L”, “C”);

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
ublic class P5_21 {
    public static String romanDigit(int number, String one, String five, String ten) {
        if (number == 1) {
            return one;
        }
        if (number == 2) {
            return one + one;
        }
        if (number == 3) {
            return one + one + one;
        }
        if (number == 4) {
            return one + five;
        }
        if (number == 5) {
            return five;
        }
        if (number == 6) {
            return five + one;
        }
        if (number == 7) {
            return five + one + one;
        }
        if (number == 8) {
            return five + one + one + one;
        }
        return one + ten;
    }
    public static String integerToRoman(int number) {
        String ones = romanDigit(number % 10, "I", "V", "X");
        number /= 10;
        String tens = romanDigit(number % 10, "X", "L", "C");
        number /= 10;
        String hundreds = romanDigit(number % 10, "C", "D", "M");
        number /= 10;
        String thousands = romanDigit(number % 10, "M", "M", "M");
        return thousands + hundreds + tens + ones;
    }
}
```  

</p>
</details>

#### Write a method that computes the balance of a bank account with a given initial balance and interest rate, after a given number of years. Assume interest is com­pounded yearly.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P5_22 {
    public static double computeBalance(double init_balance, double interest, int years) {
        return init_balance * Math.pow((1 + interest), years);
    }
}

```  

</p>
</details>

#### Write a program that prints instructions to get coffee, asking the user for input whenever a decision needs to be made. Decompose each task into a method, for example:

    public static void brewCoffee()
    {
        System.out.println(“Add water to the coffee maker.”);
        System.out.println(“Put a filter in the coffee maker.”);
        grindCoffee();
        System.out.println(“Put the coffee in the filter.”);
        . . .
    }

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;

public class P5_23 {
    public static void grindCoffee() {
        System.out.println("Add coffee beans to the coffee grinder.");
        System.out.println("Push the button for 60 seconds.");
    }
    public static void brewCoffee() {
        System.out.println("Add water to the coffee maker.");
        System.out.println("Put a filter in coffee maker.");
        grindCoffee();
        System.out.println("Add coffee beans to filer.");
        System.out.println("Trun coffee maker on.");
    }
    public static void boilWater() {
        System.out.println("Is there a microwave available? (yes/no) ");
        Scanner input = new Scanner(System.in);
        String result = input.next();
        if (result.equals("yes"))
        {
            System.out.println("Fill cup with water.");
            System.out.println("Place cup in microwave.");
            System.out.println("Heat for three minutes.");
        }
        else
        {
            System.out.println("Fill a kettle with water.");
            System.out.println("Heat kettle on stove until water comes " + "to a boil.");
        }
        input.close();
    }
    public static void makeCoffee() {
        System.out.println("Is there instant coffee available? (yes/no)");
        Scanner input = new Scanner(System.in);
        String result = input.next();
        if (result.equals("yes"))
        {
            boilWater();
            System.out.println("Mix boiling water with instant coffee.");
        }
        else
        {
            brewCoffee();
        }
        input.close();
    }
    public static void getCoffee() {
        System.out.println("Can you ask someone? (yes/no) ");
        Scanner input = new Scanner(System.in);
        String result = input.next();
        if (result.equals("no"))
        {
            System.out.println("You must make coffee.");
            makeCoffee();
        }
        else
        {
            System.out.println("Ask for some.");
        }
        input.close();
    }
}
```  

</p>
</details>

#### Write a program that prints a paycheck. Ask the program user for the name of the employee, the hourly rate, and the number of hours worked. If the number of hours exceeds 40, the employee is paid “time and a half”, that is, 150 percent of the hourly rate on the hours exceeding 40. Your check should look similar to that in the figure below. Use fictitious names for the payer and the bank. Be sure to use stepwi­se refinement and break your solution into several methods. Use the intName method to print the dollar amount of the check.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;

public class P5_24 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Enter the name of the employee: ");
        String name = input.nextLine();
        System.out.print("Enter the hourly rate: ");
        double hourlyRate = input.nextDouble();
        System.out.print("Enter the hours worked: ");
        double hoursWorked = input.nextDouble();
        input.close();

        printCheckHeader();
        double pay = totalPay(hourlyRate, hoursWorked);
        printPayAmount(pay);
        int dollars = (int) pay;
        int cents = (int) ((pay * 100) % 100);
        printCheckFooter(name, intName(dollars).toUpperCase(), cents);
    }

    public static String intName(int number) {
        if (number == 0) {
            return "zero";
        }
        int part = number; // The part that still needs to be converted
        String name = ""; // The name of the number

        if (part < 0) {
            name = "negative";
            part = -part;
        }
        if (part >= 100) {
            name = digitName(part / 100) + " hundred";
            part = part % 100;
        }

        if (part >= 20) {
            name = name + " " + tensName(part);
            part = part % 10;
        } else if (part >= 10) {
            name = name + " " + teenName(part);
            part = 0;
        }

        if (part > 0) {
            name = name + " " + digitName(part);
        }
        return (name.charAt(0) == ' ') ? name.substring(1) : name;
    }

    public static String digitName(int digit) {
        if (digit == 1) {
            return "one";
        }
        if (digit == 2) {
            return "two";
        }
        if (digit == 3) {
            return "three";
        }
        if (digit == 4) {
            return "four";
        }
        if (digit == 5) {
            return "five";
        }
        if (digit == 6) {
            return "six";
        }
        if (digit == 7) {
            return "seven";
        }
        if (digit == 8) {
            return "eight";
        }
        if (digit == 9) {
            return "nine";
        }
        return "";
    }

    public static String teenName(int number) {
        if (number == 10) {
            return "ten";
        }
        if (number == 11) {
            return "eleven";
        }
        if (number == 12) {
            return "twelve";
        }
        if (number == 13) {
            return "thirteen";
        }
        if (number == 14) {
            return "fourteen";
        }
        if (number == 15) {
            return "fifteen";
        }
        if (number == 16) {
            return "sixteen";
        }
        if (number == 17) {
            return "seventeen";
        }
        if (number == 18) {
            return "eighteen";
        }
        if (number == 19) {
            return "nineteen";
        }
        return "";
    }

    public static String tensName(int number) {
        if (number >= 90) {
            return "ninety";
        }
        if (number >= 80) {
            return "eighty";
        }
        if (number >= 70) {
            return "seventy";
        }
        if (number >= 60) {
            return "sixty";
        }
        if (number >= 50) {
            return "fifty";
        }
        if (number >= 40) {
            return "forty";
        }
        if (number >= 30) {
            return "thirty";
        }
        if (number >= 20) {
            return "twenty";
        }
        return "";
    }

    public static void printCheckHeader() {
        System.out.printf("Acme Corp \t\t\t\t\tBig Bank\t\t\t\tCheckNumber: " + "1234\n");
        System.out.printf("123 St. \t\t\t\t\t321 Small St.\t\t\t\t\n");
        System.out.printf("Big City, NY 012345 \t\t\t\tSmall City, AK 543210" + "\t\t\t\t\n");
        System.out.printf("\t\t\t\t\t\t\t\t\t\tDate:\t\tAmount:\n");
        System.out.printf("\t\t\t\t\t\t\t\t\t\t04/29/09\t$");
    }

    public static void printPayAmount(double amount) {
        System.out.print("***");
        if (amount < 100) {
            System.out.print("*");
        } else if (amount < 10) {
            System.out.print("*");
        }
        System.out.printf("%.2f", amount);
    }

    public static void printCheckFooter(String payee, String dollarAmount, int cents) {
        System.out.println("PAY");
        dollarAmount += " " + cents + " / 100";
        System.out.print(dollarAmount);
        for (int i = 0; i < 106 - dollarAmount.length(); i++) {
            System.out.print("*");
        }
        System.out.println();
        System.out.println("TO THE ORDER OF: ");
        System.out.printf("\t\t\t\t\t\t%s\n", payee);
        System.out.println("\t\t\t\t\t\t124 Fake Rd");
        System.out.println("\t\t\t\t\t\tSmall Town, NK 43251");

        System.out.println("\t\t\t\t\t\t\t\t\t\t\t\t___________________");
        System.out.println("\t\t\t\t\t\t\t\t\t\t\t\t___________________");
        System.out.println("\t\t\t\t\t|:478108240|: 200620375\"*1301");
    }

    public static double totalPay(double hourlyRate, double hoursWorked) {
        double basePay = hourlyRate * hoursWorked;
        if (hoursWorked > 40) {
            basePay += 0.5 * hourlyRate * (hoursWorked - 40);
        }
        return basePay;
    }
}
```  

</p>
</details>

#### Postal bar codes. 
For faster sorting of letters, the United States Postal Service encourages companies that send large volumes of mail to use a bar code denoting the zip code (see Figure 6). The encoding scheme for a five-digit zip code is shown in Figure 7. There are full-height frame bars on each side. The five encoded digits are followed by a check digit, which is computed as follows: Add up all digits, and choose the check digit to make the sum a multiple of 10. For example, the zip code 95014 has a sum of 19, so the check digit is 1 to make the sum equal to 20. Each digit of the zip code, and the check digit, is encoded. The digit can be easily computed from the bar code using the column weights 7, 4, 2,1, 0. For example, 01100 is 0 × 7 + 1 × 4 + 1 × 2 + 0 × 1 + 0 × 0 = 6. The only exception is 0, which would yield 11 according to the weight formula. Write a program that asks the user for a zip code and prints the bar code. Use : for half bars, | for full bars. For example, 95014 becomes

    ||:|:::|:|:||::::::||:|::|:::|||
    
Provide these methods:

    public static void printDigit(int d)
    public static void printBarCode(int zipCode)

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;

public class P5_25 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Enter a zip code: ");
        int zip = input.nextInt();
        input.close();
        int checkDigit = checkDigit(zip);

        String barcode = "|";
        barcode = digitToBarCode(checkDigit) + barcode;
        for (int i = 0; i < 5; i++) {
            barcode = digitToBarCode(checkDigit) + barcode;
            zip /= 10;
        }
        barcode = "|" + barcode;
        System.out.println(barcode);
    }

    public static int checkDigit(int zip) {
        int remaining = zip;
        int sum = 0;
        while (remaining > 0) {
            sum += remaining % 10;
            remaining /= 10;
        }
        return 10 - (sum % 10);
    }

    public static String digitToBarCode(int digit) {
        if (digit == 1) {
            return ":::||";
        }
        if (digit == 2) {
            return "::|:|";
        }
        if (digit == 3) {
            return "::||:";
        }
        if (digit == 4) {
            return ":|::|";
        }
        if (digit == 5) {
            return ":|:|:";
        }
        if (digit == 6) {
            return ":||::";
        }
        if (digit == 7) {
            return "|:::|";
        }
        if (digit == 8) {
            return "|::|:";
        }
        if (digit == 9) {
            return "|:|::";
        }
        return "||:::";
    }
}
```  

</p>
</details>

#### Write a program that reads in a bar code (with : denoting half bars and | denoting full bars) and prints out the zip code it represents. Print an error message if the bar code is not correct.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;

public class P5_26 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        System.out.print("Enter a bar code: ");
        String barcode = input.next();
        input.close();
        if (barcode.length() != 32) {
            System.out.println("Barcode is invalid.");
        } else {
            int sum = 0;
            int zip = 0;
            for (int i = 0; i < 5; i++) {
                int digit = barcodeToZip(barcode.substring(i + i * 5, 7 + i * 5));
                if (digit == -1) {
                    System.out.println("Encountered an invalid barcode digit.");
                    return;
                }
                zip = digit + 10 * zip;
                sum += digit;
            }
            int checkDigit = barcodeToZip(barcode.substring(1 + 5 * 5, 7 + 5 * 5));
            if ((checkDigit + sum) % 10 != 0) {
                System.out.println("Error checkdigit mismatch.");
            } else {
                System.out.println(zip);
            }
        }
    }

    public static int barcodeToZip(String barCode) {
        if (barCode.equals("||:::")) {
            return 0;
        }
        int digit = 0;
        if (barCode.charAt(0) == '|') {
            digit += 7;
        }
        if (barCode.charAt(1) == '|') {
            digit += 4;
        }
        if (barCode.charAt(2) == '|') {
            digit += 2;
        }
        if (barCode.charAt(3) == '|') {
            digit += 1;
        }
        if ((digit == 1 || digit == 2 || digit == 4 || digit == 7) && barCode.charAt(4) != '|') {
            return -1;
        } else if (digit < 1 || digit > 9) {
            return -1;
        } else {
            return digit;
        }
    }
}
```  

</p>
</details>

#### Having a secure password is a very important practice, when much of our information is stored online. Write a program that validates a new password, following these rules:

	• The password must be at least 8 characters long.
	• The password must have at least one uppercase and one lowercase letter
	• The password must have at least one digit.

Write a program that asks for a password, then asks again to confirm it. If the
passwords don’t match or the rules are not fulfilled, prompt again. Your program
should include a method that checks whether a password is valid.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P5_30 {
    public static boolean checkLength(String password) {
        return password.length() > 8;
    }

    public static boolean hasUppercaseAndLowercase(String password) {
        boolean uppercase = false;
        boolean lowercase = false;
        for (int i = 0; i < password.length(); i++) {
            if (Character.isUpperCase(password.charAt(i))) {
                uppercase = true;
            }
            else if (Character.isLowerCase(password.charAt(i))) {
                lowercase = true;
            }
        }
        if (lowercase == true && uppercase == true) {
            return true;
        }
        return false;
    }
    public static boolean hasDigit(String password) {
        for (int i = 0; i < password.length(); i++) {
            if (Character.isDigit((password.charAt(i)))) {
                return true;
            }
        }
        return false;
    }
    public static boolean passwordsMatch(String input, String expected) {
        return input == expected;
    }
}
```  

</p>
</details>

#### Implement a method shout that prints a line consisting of a string followed by three exclamation marks. For example, shout("Hello") should print Hello!!! . The method should not return a value.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class S05_18 {
    public static void shout(String message) {
	System.out.println(message + "!!!");
    }
}

```  

</p>
</details>

#### Provide an alternative implementation of the body of cubeVolume method by calling the Math.pow method

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class S5_07 {
    public static void main(String[] args) {
	System.out.print("Side length: ");
	Scanner input = new Scanner(System.in);
	double sideLength = input.nextDouble();
	input.close();
	System.out.println("Cube volume: " + cubeVolume(sideLength));
    }
    public static double cubeVolume(double sideLength) {
	return Math.pow(sideLength, 3);
    }
}
```  

</p>
</details>

#### Declare a method squareArea that computes the area of a square of a given side length

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class S5_08 {
    public static void main(String[] args) {
	Scanner input = new Scanner(System.in);
	System.out.print("Side length: ");
	double sideLength = input.nextDouble();
	input.close();
	System.out.println("Square area: " + squareArea(sideLength));
    }
    public static double squareArea(double sideLength) {
	return sideLength * sideLength;
    }
}

```  

</p>
</details>

