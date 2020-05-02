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

#### Informacion4 

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

```  

</p>
</details>

#### Informacion4 

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

```  

</p>
</details>

#### Informacion4 

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

```  

</p>
</details>

#### Informacion4 

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

```  

</p>
</details>

#### Informacion4 

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

```  

</p>
</details>

#### Informacion4 

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

```  

</p>
</details>

#### Informacion4 

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

```  

</p>
</details>

#### Informacion4 

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

```  

</p>
</details>

#### Informacion4 

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

```  

</p>
</details>

#### Informacion4 

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

```  

</p>
</details>

#### Informacion4 

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

```  

</p>
</details>

#### Informacion4 

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

```  

</p>
</details>

#### Informacion4 

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java

```  

</p>
</details>

