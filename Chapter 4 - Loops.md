💡 

## Write programs that read a sequence of integer inputs and print

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

### Informacione personale



<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java

``` 

</p>
</details>

### Informacione personale



<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java

``` 

</p>
</details>

### Informacione personale



<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java

``` 

</p>
</details>

### Informacione personale



<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java

``` 

</p>
</details>

### Informacione personale



<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java

``` 

</p>
</details>

### Informacione personale



<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java

``` 

</p>
</details>

### Informacione personale



<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java

``` 

</p>
</details>

