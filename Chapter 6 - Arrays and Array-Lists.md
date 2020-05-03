#### Write a program that initializes an array with ten random integers and then prints four lines of output, containing

    • Every element at an even index.
    • Every even element.
    • All elements in reverse order.
    • Only the first and last element.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P6_01 {
    public static void main(String[] args) {
        int[] numbers = new int[10];
        for (int i = 0; i < 10; i++) {
            numbers[i] = (int) (Math.random() * 100 + 1);
        }
        System.out.println("Every even index element:");
        for (int i = 0; i < numbers.length; i++) {
            if (i % 2 == 0) {
                System.out.println(numbers[i]);
            }
        }
        System.out.println("Every even element:");
        for (int i = 0; i < numbers.length; i++) {
            if (numbers[i] % 2 == 0) {
                System.out.println(numbers[i]);
            }
        }
        System.out.println("All elements in reverse order:");
        for (int i = numbers.length - 1; i > -1; i--) {
            System.out.println(numbers[i]);
        }
        System.out.println("First and last element:");
        System.out.println(numbers[0]);
        System.out.println(numbers[numbers.length - 1]);
    }
}
```

</p>
</details>

#### Write array methods that carry out the following tasks for an array of integers. For  each method, provide a test program.

     a.   Swap the first and last elements in the array.
     b.   Shift all elements by one to the right and move the last element into the first
     position. For example, 1 4 9 16 25 would be transformed into 25 1 4 9 16.
     c.   Replace all even elements with 0.
     d.   Replace each element except the first and last by the larger of its two neighbors.
     e.   Remove the middle element if the array length is odd, or the middle two
     elements if the length is even.
     f.   Move all even elements to the front, otherwise preserving the order of the
     elements.
     g.   Return the second-largest element in the array.
     h.   Return true if the array is currently sorted in increasing order.
     i.   Return true if the array contains two adjacent duplicate elements.
     j.   Return true if the array contains duplicate elements (which need not be adjacent).

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P6_02 {
    // A
    public static void swap(int[] seq, int a_index, int b_index) {
        int temp = seq[a_index];
        seq[a_index] = seq[b_index];
        seq[b_index] = temp;
    }

    // B
    public static void shift(int[] seq) {
        int last = seq[seq.length - 1];
        System.arraycopy(seq, 0, seq, 1, seq.length - 1);
        seq[0] = last;
    }

    // C
    public static void replace(int[] seq, int replacement) {
        for (int i = 0; i < seq.length; i++) {
            if (seq[i] % 2 == 0) {
                seq[i] = replacement;
            }
        }
    }

    // D
    public static int[] replaceByNeighBours(int[] seq) {
        for (int i = 1; i < seq.length - 1; i++) {
            if (seq[i + 1] > seq[i - 1]) {
                seq[i] = seq[i + 1];
            } else if (seq[i - 1] > seq[i + 1]) {
                seq[i] = seq[i - 1];
            }
        }
        return seq;
    }

    // E
    public static void removeMiddleElement(int[] seq) {
        int middle = seq.length / 2;
        if (seq.length % 2 == 0) {
            for (int i = middle; i < seq.length - 1; i++) {
                seq[i - 1] = seq[i + 1];
            }
            seq[seq.length - 1] = 0;
            seq[seq.length - 2] = 0;
        } else if (seq.length % 2 == 1) {
            for (int i = middle; i < seq.length - 1; i++) {
                seq[i] = seq[i + 1];
            }
            seq[seq.length - 1] = 0;
        }
    }

    // F
    public static void moveEvenElements(int[] seq) {
        int swapPos = 0;
        for (int i = 0; i < seq.length; i++) {
            if (seq[i] % 2 == 0) {
                int temp = seq[swapPos];
                seq[swapPos] = seq[i];
                seq[i] = temp;
                swapPos += 1;
            }
        }
    }

    // G
    public static int secondLargestElement(int[] seq) {
        int largest = seq[0];
        int secondLargest = largest;
        for (int i = 0; i < seq.length; i++) {
            if (seq[i] > largest) {
                int temp = largest;
                largest = seq[i];
                secondLargest = temp;
            }
        }
        return secondLargest;
    }

    // H
    public static boolean isSorted(int[] seq) {
        for (int i = 0; i < seq.length - 1; i++) {
            if (seq[i] > seq[i + 1]) {
                return false;
            }
        }
        return true;
    }

    // I
    public static boolean hasAdjacentDuplicates(int[] seq) {
        for (int i = 0; i < seq.length - 1; i++) {
            if (seq[i] == seq[i + 1]) {
                return true;
            }
        }
        return false;
    }

    // J
    public static boolean hasDuplicateElements(int[] seq) {
        for (int i = 0; i < seq.length; i++) {
            for (int j = 0; j < seq.length; j++) {
                if (i != j && seq[i] == seq[j]) {
                    return true;
                }
            }
        }
        return false;
    }
}
```

</p>
</details>

#### Modify the LargestInArray.java program in Section 6.3 to mark both the smallest and the largest elements.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;

public class P6_03 {
    public static void main(String[] args) {
        final int LENGTH = 100;
        double[] values = new double[LENGTH];
        int currentSize = 0;

        // Read inputs
        System.out.println("Please enter values, Q to quit:");
        Scanner in = new Scanner(System.in);
        while (in.hasNextDouble() && currentSize < values.length) {
            values[currentSize] = in.nextDouble();
            currentSize++;
        }
        in.close();

        // Find the largest and smallest values
        double largest = values[0];
        double smallest = values[0];
        for (int i = 1; i < currentSize; i++) {
            if (values[i] > largest) {
                largest = values[i];
            }
            if (values[i] < smallest) {
                smallest = values[i];
            }
        }

        // Print all values, marking the largest and smallest
        for (int i = 0; i < currentSize; i++) {
            System.out.print(values[i]);
            if (values[i] == largest && smallest != largest) {
                System.out.print(" <== largest value");
            } else if (values[i] == smallest && smallest != largest) {
                System.out.print(" <== smallest value");
            } else {
                System.out.print(" <== smallest and largest value");
            }
            System.out.println();
        }
    }
}
```

</p>
</details>

#### Write a method sumWithoutSmallest that computes the sum of an array of values, except for the smallest one, in a single loop. In the loop, update the sum and the smallest value. After the loop, return the difference.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P6_04 {
    public static int sumWithoutSmallest(int[] seq) {
        int sum = 0;
        for (int i = 0; i < seq.length; i++) {
            sum += seq[i];
        }
        return sum - findSmallest(seq);
    }
    public static int findSmallest(int[] seq) {
        int smallest = seq[0];
        for (int i = 0; i < seq.length; i++) {
            if (seq[i] < smallest) {
                smallest = seq[i];
            }
        }
        return smallest;
    }
}
```

</p>
</details>

#### Write a method public static void removeMin that removes the minimum value from a partially filled array without calling other methods.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P6_05 {
    public static void removeMin(int[] seq) {
        int minElement = seq[0];
        int minIndex = 0;
        for (int i = 1; i < seq.length; i++) {
            if (seq[i] != 0 && seq[i] < minElement) {
                minElement = seq[i];
                minIndex = i;
            }
        }
        for (int i = minIndex; i < seq.length - 1; i++) {
            seq[i] = seq[i + 1];
        }
    }
}
```

</p>
</details>

#### Compute the alternating sum of all elements in an array. For example, if your program reads the input

    1  4  9  16  9  7  4  9  11
    
then it computes

    1 – 4 + 9 – 16 + 9 – 7 + 4 – 9 + 11 = –2

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P6_06 {
    public static int alternatingSum(int seq[]) {
        int alternateSum = 0;
        for (int i = 0; i < seq.length; i++) {
            if (i % 2 == 0) {
                alternateSum += seq[i];
            }
            else {
                alternateSum -= seq[i];
            }
        }
        return alternateSum;
    }
}
```

</p>
</details>

#### Write a method that reverses the sequence of elements in an array. For example, if you call the method with the array

    1  4  9  16  9  7  4  9  11
    
then the array is changed to

    11  9  4  7  9  16  9  4  1

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P6_07 {
    public static void reverse(int[] array) {
        for (int i = 0; i < array.length / 2; i++) {
            int temp = array[i];
            array[i] = array[array.length - 1 - i];
            array[array.length - 1 - i] = temp;
        }
    }
}
```

</p>
</details>

#### Write a method that implements the algorithm developed in Section 6.6.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P6_08 {
    public static void swap(int[] seq) {
        int i = 0;
        int j = seq.length / 2;
        while (i < seq.length / 2) {
            int temp = seq[i];
            seq[i] = seq[j];
            seq[j] = temp;
            i += 1;
            j += 1;
        }
    }
}
```

</p>
</details>

#### Write a method

    public static boolean equals(int[] a, int[] b)
    
that checks whether two arrays have the same elements in the same order.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P6_09 {
    public static boolean arrayEquals(int[] a, int[] b) {
        if (a.length != a.length) {
            return false;
        }
        for (int i = 0; i < b.length; i++) {
            if (a[i] != b[i]) {
                return false;
            }
        }
        return true;
    }
}
```


</p>
</details>

#### A run is a sequence of adjacent repeated values. Write a program that generates a sequence of 20 random die tosses in an array and that prints the die values, marking the runs by including them in parentheses, like this:

    1 2 (5 5) 3 1 2 4 3 (2 2 2 2) 3 6 (5 5) 6 3 1
    
Use the following pseudocode:

    Set a boolean variable inRun to false.
    For each valid index i in the array
         If inRun
             If values[i] is different from the preceding value
                 Print ).
                 inRun = false.
         If not inRun
             If values[i] is the same as the following value
                 Print (.
                 inRun = true.
         Print values[i].
    If inRun, print ).

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P6_12 {
    public static void printRun(int[] values) {
        boolean inRun = false;
        int previousValue = values[0];
        for (int i = 0; i < values.length - 1; i++) {
            if (inRun) {
                if (values[i] != previousValue) {
                    System.out.print(")");
                    inRun = false;
                }
            } else {
                if (values[i] == values[i + 1]) {
                    System.out.print(" (");
                    inRun = true;
                } else {
                    System.out.print(" ");
                }
            }
            previousValue = values[i];
            System.out.print(values[i]);
        }
        if (inRun && values[values.length - 1] == previousValue) {
            System.out.print(" " + values[values.length - 1] + ")");
        } else if (inRun && values[values.length - 1] != previousValue) {
            System.out.print(") " + values[values.length - 1]);
        } else {
            System.out.print(" " + values[values.length - 1]);
        }
    }

    public static int[] generateDieTosses(int n) {
        int[] tosses = new int[n];
        for (int i = 0; i < n; i++) {
            tosses[i] = (int) (Math.random() * 6 + 1);
        }
        return tosses;
    }
}
```

</p>
</details>

#### Write a program that generates a sequence of 20 random die tosses in an array and that prints the die values, marking only the longest run, like this:

    1 2 5 5 3 1 2 4 3 (2 2 2 2) 3 6 5 5 6 3 1
    
If there is more than one run of maximum length, mark the first one.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P6_13 {
    public static int[] generateDieTosses(int n) {
        int[] tosses = new int[n];
        for (int i = 0; i < n; i++) {
            tosses[i] = (int) (Math.random() * 6 + 1);
        }
        return tosses;
    }

    public static void printArrayWithParenthesis(int[] values, int index, int length) {
        boolean inRun = false;
        for (int i = 0; i < values.length; i++) {
            if (inRun) {
                if (length == 0) {
                    System.out.print(") " + values[i] + " ");
                    inRun = false;
                } else {
                    System.out.print(" " + values[i]);
                }
                length--;
            } else if (i == index) {
                inRun = true;
                length--;
                System.out.print("(" + values[i]);
            } else {
                System.out.print(values[i] + " ");
            }
        }
        if (length == 0) {
            System.out.print(")");
        }
    }

    public static void printLongestRun(int[] values) {
        boolean inRun = false;
        int previousValue = values[0];
        int longestRunLength = 0;
        int longestRunIndex = -1;
        int currentRunLength = 0;
        int currentRunIndex = -1;
        for (int i = 0; i < values.length - 1; i++) {
            if (inRun) {
                if (values[i] != previousValue) {
                    inRun = false;
                    if (currentRunLength > longestRunLength) {
                        longestRunLength = currentRunLength;
                        longestRunIndex = currentRunIndex;
                    }
                } else {
                    currentRunLength++;
                }
            } else {
                if (values[i] == values[i + 1]) {
                    inRun = true;
                    currentRunLength = 1;
                    currentRunIndex = i;
                }
            }
            previousValue = values[i];
        }
        if (inRun && values[values.length - 1] == previousValue) {
            currentRunLength++;
            if (currentRunLength > longestRunLength) {
                longestRunLength = currentRunLength;
                longestRunIndex = currentRunIndex;
            }
        }
        printArrayWithParenthesis(values, longestRunIndex, longestRunLength);
    }
}
```

</p>
</details>

#### Write a program that generates a sequence of 20 random values between 0 and 99 in  an array, prints the sequence, sorts it, and prints the sorted sequence. Use the sort method from the standard Java library.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Arrays;
public class P6_14 {
    public static int[] generateSequence(int n) {
        int[] seq = new int[n];
        for (int i = 0; i < n; i++) {
            seq[i] = (int) (Math.random() * 99 + 1);
        }
        return seq;
    }

    public static void printArray(int[] array) {
        Arrays.sort(array);
        System.out.println(Arrays.toString(array));
    }
}
```

</p>
</details>

#### Write a program 

that produces ten random permutations of the numbers 1 to 10. To  generate a random permutation, you need to fill an array with the numbers 1 to 10  so that no two entries of the array have the same contents. You could do it by brute  force, by generating random values until you have a value that is not yet in the array.  But that is inefficient. Instead, follow this algorithm.  Make a second array and fill it with the numbers 1 to 10.  Repeat 10 times  Pick a random element from the second array.  Remove it and append it to the permutation array.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.ArrayList;
public class P6_15 {
    public static void permutations(int[] seq) {
        ArrayList<Integer> tempArray = permutationNumbers();
        for (int i = 0; i < 10; i++) {
            int randPos = (int) (Math.random() * tempArray.size());
            int randElement = tempArray.get(randPos);
            tempArray.remove(randPos);
            seq[i] = randElement;
        }
    }

    public static ArrayList<Integer> permutationNumbers() {
        ArrayList<Integer> tempArray = new ArrayList<Integer>();
        tempArray.add(1);
        tempArray.add(2);
        tempArray.add(3);
        tempArray.add(4);
        tempArray.add(5);
        tempArray.add(6);
        tempArray.add(7);
        tempArray.add(8);
        tempArray.add(9);
        tempArray.add(10);
        return tempArray;
    }
}
```

</p>
</details>

#### It is a well-researched fact that men in a restroom generally prefer to maximize their distance from already occupied stalls, by occupying the middle of the longest sequence of unoccupied places. For example, consider the situation where ten stalls are empty.

    _ _ _ _ _ _ _ _ _ _
The first visitor will occupy a middle position:

    _ _ _ _ _ X _ _ _ _
The next visitor will be in the middle of the empty area at the left.

    _ _ X _ _ X _ _ _ _
    
Write a program that reads the number of stalls and then prints out diagrams in the format given above when the stalls become filled, one at a time. 
Hint: Use an array of boolean values to indicate whether a stall is occupied.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P6_16 {
    public static final int STALL_NUMBER = 10;
    
    public static int nextStall(boolean[] stalls) {
        int longestIndex = -1;
        int longestRun = 0;
        int currentIndex = -1;
        int currentRun = 0;
        boolean inRun = false;
        for (int i = 0; i < stalls.length; i++) {
            if (inRun && stalls[i]) {
                inRun = false;
                if (currentRun >= longestRun) {
                    longestRun = currentRun;
                    longestIndex = currentIndex;
                }
                
            }
            else if (!inRun && !stalls[i]) {
                inRun = true;
                currentIndex = i;
                currentRun = 1;
            }
            else if (inRun && !stalls[i]) {
                currentRun += 1;
            }
        }
        if (inRun) {
            if (currentRun >= longestRun) {
                longestRun = currentRun;
                longestIndex = currentIndex;
            }
        }
        return (longestRun - 1) / 2 + longestIndex;
    }
    
    public static void printStalls(boolean[] stalls) {
        for (int i = 0; i < stalls.length; i++) {
            if (stalls[i]) {
                System.out.print("X ");
            }
            else {
                System.out.print("_ ");
            }
        }
        System.out.println();
    }
    
    public static void main(String[] args) {
        boolean[] stalls = new boolean[STALL_NUMBER];
        for (int i = 0; i < stalls.length; i++) {
            stalls[nextStall(stalls)] = true;
            printStalls(stalls);
        }
    }
}
```

</p>
</details>

#### In this assignment, 
you will model the game of Bulgarian Solitaire. The game starts  with 45 cards. (They need not be playing cards. Unmarked index cards work just as well.) Randomly divide them into some number of piles of random size. For example, you might start with piles of size 20, 5, 1, 9, and 10. In each round, you take one card from each pile, forming a new pile with these cards. For example, the sample  starting configuration would be transformed into piles of size 19, 4, 8, 9, and 5. The  solitaire is over when the piles have size 1, 2, 3, 4, 5, 6, 7, 8, and 9, in some order.   (It can be shown that you always end up with such a configuration.)  In your program, produce a random starting configuration and print it. Then keep  applying the  soli­taire step and print the result. Stop when the solitaire final configuration is reached.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.ArrayList;
public class P6_17 {
    public static ArrayList<Integer> createPile() {
        int cards = 45;
        ArrayList<Integer> pile = new ArrayList<Integer>();
        while (cards > 0) {
            int randomCard = (int) (Math.random() * 45) + 1;
            cards -= randomCard;
            pile.add(randomCard);
        }
        System.out.println("Initial piles: " + pile.toString());
        return pile;
    }

    public static void clearZeros(ArrayList<Integer> pile) {
        for (int i = 0; i < pile.size(); i++) {
            if (pile.get(i) == 0) {
                pile.remove(i);
                i -= 1;
            }
        }
    }

    public static void nextRound(ArrayList<Integer> pile) {
        for (int i = 0; i < pile.size(); i++) {
            pile.set(i, pile.get(i) - 1);
        }
        System.out.println(pile.toString());
    }

    public static boolean finalConfig(ArrayList<Integer> pile) {
        if (pile.size() != 9) {
            return false;
        }
        boolean dupes = false;
        for (int i = 0; i < pile.size(); i++) {
            for (int j = 1; j < pile.size(); j++) {
                if (pile.get(i) == pile.get(j)) {
                    dupes = true;
                }
            }
        }
        if (dupes) {
            return false;
        } else {
            return true;
        }
    }

    public static void main(String[] args) {
        ArrayList<Integer> pile = createPile();
        while (finalConfig(pile) == false) {
            nextRound(pile);
        }
    }
}
```

</p>
</details>

#### Magic squares. An n × n matrix that is filled with the numbers 1, 2, 3, . . ., n 2 is a  magic square if the sum of the elements in each row, in each column, and in the two  diagonals is the same value.

 Write a program that reads in 16 values from the keyboard and tests whether they
 form a magic square when put into a 4 × 4 array. You need to test two features:
 
     1.   Does each of the numbers 1, 2, ..., 16 occur in the user input?
     2.   When the numbers are put into a square, are the sums of the rows, columns,  and diagonals equal to each other?

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P6_18 {
    public static int N = 4;

    public static int[][] readSquare() {
        int[][] square = new int[N][N];
        Scanner input = new Scanner(System.in);
        for (int i = 0; i < N; i++) {
            for (int j = 0; j < N; j++) {
                int number = input.nextInt();
                square[i][j] = number;
            }
        }
        input.close();
        return square;
    }

    public static int leftRightDiagonalSum(int[][] square) {
        int sum = 0;
        for (int i = 0; i < N; i++) {
            sum += square[i][i];
        }
        return sum;
    }

    public static int rightLeftDiagonalSum(int[][] square) {
        int sum = 0;
        for (int i = 0; i < N; i++) {
            sum += square[i][N - i - 1];
        }
        return sum;
    }

    public static int columnSum(int[][] square, int columnNumber) {
        int sum = 0;
        for (int i = 0; i < N; i++) {
            sum += square[i][columnNumber];
        }
        return sum;
    }

    public static int rowSum(int[][] square, int rowNumber) {
        int sum = 0;
        for (int i = 0; i < N; i++) {
            sum += square[rowNumber][i];
        }
        return sum;
    }

    public static boolean correctNumbers(int[][] square) {
        boolean[] seenNumber = new boolean[N * N];
        for (int i = 0; i < N; i++) {
            for (int j = 0; j < N; j++) {
                int number = square[i][j];
                if (number < 1 || number > (N * N)) {
                    return false;
                } else if (seenNumber[number - 1]) {
                    return false;
                } else {
                    square[i][j] = number;
                    seenNumber[number - 1] = true;
                }
            }
        }
        return true;
    }

    public static boolean validMagicSquare(int[][] square) {
        if (!correctNumbers(square)) {
            return false;
        }
        int baseSum = leftRightDiagonalSum(square);
        if (baseSum != rightLeftDiagonalSum(square)) {
            return false;
        }
        for (int i = 0; i < N; i++) {
            if (baseSum != columnSum(square, i)) {
                return false;
            }
        }
        for (int i = 0; i < N; i++) {
            if (baseSum != rowSum(square, i)) {
                return false;
            }
        }
        return true;
    }
}

```

</p>
</details>

#### Implement the following algorithm to construct magic n × n squares; it works only if n is odd.

    Set row = n - 1, column = n / 2.
    For k = 1 ... n * n
         Place k at [row][column].
         Increment row and column.
         If the row or column is n, replace it with 0.
         If the element at [row][column] has already been filled
             Set row and column to their previous values.
             Decrement row.
      
 Write a program whose input is the number n and whose output is the magic square  of order n if n is odd.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class P6_19 {
    public static void printMagicSquare(int[][] square) {
        for (int i = 0; i < square.length; i++) {
            for (int j = 0; j < square[i].length; j++) {
                System.out.printf("%3d", square[i][j]);
            }
            System.out.println();
        }
    }

    public static int[][] makeMagicSquare(int n) {
        int[][] square = new int[n][n];
        int row = n - 1;
        int column = n / 2;
        for (int k = 1; k <= (n * n); k++) {
            square[row][column] = k;
            row = (row + 1) % n;
            column = (column + 1) % n;
            if (square[row][column] != 0) {
                column = (column - 1 + n) % n;
                row = (row - 2 + n) % n;
            }
        }
        return square;
    }

    public static void main(String[] args) {
        System.out.println("Enter an odd number: ");
        Scanner in = new Scanner(System.in);
        int n = in.nextInt();
        in.close();
        int[][] square = makeMagicSquare(n);
        printMagicSquare(square);
    }
}

```

</p>
</details>

#### Write a program that reads a sequence of input values and displays a bar chart of the values, using asterisks, like this:

     **********************
     ****************************************
     ****************************
     **************************
     ***************

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class P6_22 {
    public static void displayCharts(int[] seq) {
        int maxElement = findMaxElement(seq);
        for (int i = 0; i < seq.length; i++) {
            int times = (seq[i] / maxElement) * 40;
            for (int j = 0; j < times; j++) {
                System.out.print("*");
            }
            System.out.println();
        }
    }

    public static int findMaxElement(int[] seq) {
        int maxElement = seq[0];
        for (int i = 1; i < seq.length; i++) {
            if (seq[i] > maxElement) {
                maxElement = seq[i];
            }
        }
        return maxElement;
    }
}
```

</p>
</details>

#### Write a method
 `public static ArrayList<Integer> mergeSorted(ArrayList<Integer> a,  ArrayList<Integer> b)`that merges two sorted array lists, producing a new sorted array list. Keep an index  into each array list, indicating how much of it has been processed already. Each time,  append the smallest unprocessed element from either array list, then advance the  index.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.ArrayList;
public class P6_28 {
    public static ArrayList<Integer> mergeSorted(ArrayList<Integer> a, ArrayList<Integer> b) {
        ArrayList<Integer> mergedList = new ArrayList<Integer>();
        for (int i = 0; i < a.size() + b.size(); i++) {
            int minElementA = findMinElement(a);
            int minElementB = findMinElement(b);
            if (minElementA < minElementB) {
                mergedList.add(minElementA);
            } else {
                mergedList.add(minElementB);
            }
        }
        return mergedList;
    }

    // bad method name that doesn't explicitly say that the min element is
    // removed afterwards
    public static int findMinElement(ArrayList<Integer> list) {
        int minElement = list.get(0);
        int minElementIndex = 0;
        for (int i = 1; i < list.size(); i++) {
            if (list.get(i) < minElement) {
                minElement = list.get(i);
                minElementIndex = i;
            }
        }
        list.remove(minElementIndex);
        return minElement;
    }
}
```

</p>
</details>

#### Write code that fills an array values with each set of numbers below.  
    a.1     2   3   4   5   6   7   8   9   10

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Arrays;
public class R6_01A {
    public static void main(String[] args) {
        int[] numbers = new int[10];
        for (int i = 0; i < numbers.length; i++) {
            numbers[i] = i;
        }
        System.out.println(Arrays.toString(numbers));
    }
}

```

</p>
</details>

#### Write code that fills an array values with each set of numbers below.  
    b.0   2   4   6   8   10   12   14   16   18

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Arrays;
public class R6_01B {
    public static void main(String[] args) {
        int[] numbers = new int[10];
        for (int i = 0; i < numbers.length; i++) {
            numbers[i] = i * 2;
        }
        System.out.println(Arrays.toString(numbers));
    }
}
```

</p>
</details>

#### Write code that fills an array values with each set of numbers below.
    c.1   4   9   16   25   36   49   64   81   100

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Arrays;
public class R6_01C {
    public static void main(String[] args) {
        int[] numbers = new int[10];
        for (int i = 0; i < numbers.length; i++) {
            int k = i + 1;
            numbers[i] = k * k;
        }
        System.out.println(Arrays.toString(numbers));
    }
}

```

</p>
</details>

#### Write code that fills an array values with each set of numbers below.
    0   0   0   0   0   0   0   0   0    0

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Arrays;
public class R6_01D {
    public static void main(String[] args) {
        int[] numbers = new int[10];
        System.out.println(Arrays.toString(numbers));
    }
}
```

</p>
</details>

#### Write code that fills an array values with each set of numbers below.
    1   4   9   16   9   7   4   9   11

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Arrays;
public class R6_01E {
    public static void main(String[] args) {
        int[] numbers = {1, 4, 9, 16, 9, 7, 4, 9, 11};
        System.out.println(Arrays.toString(numbers));
    }
}

```

</p>
</details>

####  Write code that fills an array values with each set of numbers below.
    f.0   1   0   1   0   1   0   1   0   1

/* what is here */

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Arrays;
public class R6_01F {
    public static void main(String[] args) {
        int[] numbers = new int[10];
        for (int i = 0; i < numbers.length; i++) {
            numbers[i] = i % 2;
        }
        System.out.println(Arrays.toString(numbers));
    }
}
```

</p>
</details>

#### Write code that fills an array values with each set of numbers below.

    g.0   1   2   3  4   0   1   2   3    4

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Arrays;
public class R6_01G {
    public static void main(String[] args) {
        int[] numbers = new int[10];
        for (int i = 0; i < numbers.length; i++) {
            numbers[i] = i % 5;
        }
        System.out.println(Arrays.toString(numbers));
    }
}

```

</p>
</details>

#### Write a loop that fills an array values with ten random numbers between 1 and 100. Write code for two nested loops that fill values with ten different random numbers between 1 and 100.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Arrays;
public class R6_04 {
    public static void main(String[] args) {
        // ten random numbers  between 1 and 100
        int[] numbers = new int[10];
        for (int i = 0; i < 10; i++) {
            numbers[i] = (int) (Math.random() * 100 + 1);
        }
        System.out.println(Arrays.toString(numbers));
        
        // ten different random numbers between 1 and 100
        for (int i = 0; i < 10; i++) {
            int count = 0;
            numbers[i] = (int) (Math.random() * 100 + 1);
            for (int j = 0; j < i; j++) {
                if (numbers[i] == numbers[j]) {
                    count += 1;
                }
            }
            if (count > 0) {
                i -= 1;
            }
        }
        System.out.println(Arrays.toString(numbers));
    }
}
```

</p>
</details>

#### Write Java code for a loop that simultaneously computes both the maximum and minimum of an array.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class R6_05 {
    public static void main(String[] args) {
        int[] numbers = { 2, 1, 5, 4, 3, 6, 7, 10, 9 };
        int min = numbers[0];
        int max = numbers[0];
        for (int i : numbers) {
            if (i < min) {
                min = i;
            }
            if (i > max) {
                max = i;
            }
        }
        System.out.println("Min: " + min);
        System.out.println("Max: " + max);
    }
}

```

</p>
</details>

#### Rewrite the following loops without using the enhanced for loop construct. Here, values is an array of floating-point numbers.
    a.   for (double x : values) { total = total + x; }
    b.   for (double x : values) { if (x == target) { return true; } }
    c.   int i = 0;  
         for (double x : values) { values[i] = 2 * x; i++; }

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class R6_08 {
    // A
    public static double total(double[] seq) {
        double total = 0;
        for (int i = 0; i < seq.length; i++) {
            total += seq[i];
        }
        return total;
    }

    // B
    public static boolean findTarget(double[] seq, double target) {
        for (int i = 0; i < seq.length; i++) {
            if (seq[i] == target) {
                return true;
            }
        }
        return false;
    }
    // C
    public static double[] multipleEachByFactor(double[] seq, double factor) {
        for (int i = 0; i < seq.length; i++) {
            seq[i] = 2 * factor;
        }
        return seq;
    }
}
```

</p>
</details>

#### Write a loop that reads ten numbers and a second loop that displays them in the opposite order from which they were entered.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.Scanner;
public class R6_13 {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        int[] numbers = new int[10];
        int count = 0;
        System.out.println("Enter 10 numbers: ");
        do {
            System.out.printf("n %d: ", count+1);
            numbers[count] = input.nextInt();
            count += 1;
        } while (count < 10);
        input.close();
        
        for (int i = numbers.length - 1; i > -1; i--) {
            System.out.println(numbers[i]);
        }
    }
}
```

</p>
</details>

####  Write a loop that counts how many elements in an array are equal to zero. 


<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class S6_13 {
    public static int zerosCount(double[] array) {
        int count = 0;
        for (double element : array) {
            if (element == 0) {
                count += 1;
            }
        }
        return count;
    }
}
```

</p>
</details>

#### When printing separators, we skipped the separator before the initial element. Rewrite the loop so that the separator is printed after each element, except for the last element

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
public class S6_15 {
    public static void addSeparators(String separator, double[] array) {
        for (int i = 0; i < array.length; i++) {
            System.out.print(array[i]);
            if (i < array.length - 1) {
                System.out.printf(" %s ", separator);
            }
        }
    }
}
```

</p>
</details>
