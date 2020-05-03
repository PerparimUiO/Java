#### Write a program that carries out the following tasks:

     Open a file with the name hello.txt.
     Store the message “Hello, World!” in the file.
     Close the file.
     Open the same file again.
     Read the message into a string variable and print it.


<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.io.FileNotFoundException;
import java.io.PrintWriter;
import java.util.Scanner;

public class P7_01 {
    public static void writeToFile(String filename) throws FileNotFoundException {
        try (PrintWriter outputFile = new PrintWriter(filename)) {
            outputFile.println("Hello, World!");
        } catch (FileNotFoundException exception) {
            System.out.println("File not found!");
        }
    }

    public static void printFileContents(String filename) {
        Scanner inputFile = new Scanner(filename);
        String contents = inputFile.nextLine();
        inputFile.close();
        System.out.println(contents);
    }
}
```

</p>
</details>

#### Write a program that reads a file containing text. Read each line and send it to the output file, preceded by line numbers. The line numbers are enclosed in delimiters so that the program can  be used for numbering Java source files. Prompt the user for the input and output file names.

    Mary had a little lamb
    Whose fleece was white as snow.
    And everywhere that Mary went,
    The lamb was sure to go!
    then the program produces the output file
    
then the program produces the output file

    /* 1 /* Mary had a little lamb
    /* 2 /* Whose fleece was white as snow.
    /* 3 /* And everywhere that Mary went,
    /* 4 /* The lamb was sure to go!

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.io.PrintWriter;
import java.util.Scanner;

public class P7_02 {
    static int lineNumber = 1;

    public static void writeLine(String line, PrintWriter fileOut) {
        fileOut.println(String.format("/* %d */ %s", lineNumber, line));
        lineNumber += 1;
    }

    public static void main(String[] args) throws FileNotFoundException {
        Scanner console = new Scanner(System.in);
        System.out.print("Filename to read: ");
        String filenameRead = console.next();
        System.out.print("Filename to write to: ");
        String filenameWrite = console.next();
        console.close();

        File fileRead = new File(filenameRead);
        Scanner fileIn = new Scanner(fileRead);
        PrintWriter fileOut = new PrintWriter(filenameWrite);
        while (fileIn.hasNextLine()) {
            String line = fileIn.nextLine();
            System.out.println(line);
            writeLine(line, fileOut);
        }
        fileIn.close();
        fileOut.close();
    }
}
```

</p>
</details>

#### Repeat Exercise P7.2, but allow the user to specify the file name on the commandline. If the user doesn’t specify any file name, then prompt the user for the name. 

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.io.PrintWriter;
import java.util.Scanner;

public class P7_03 {
    static int lineNumber = 1;

    public static void writeLine(String line, PrintWriter fileOut) {
        fileOut.println(String.format("/* %d */ %s", lineNumber, line));
        lineNumber += 1;
    }

    public static void main(String[] args) throws FileNotFoundException {
        Scanner console = new Scanner(System.in);
        String filenameRead;
        String filenameWrite;
        if (args.length == 2) {
            filenameRead = args[0];
            filenameWrite = args[1];
        } else {
            System.out.print("Filename to read: ");
            filenameRead = console.next();
            System.out.print("Filename to write to: ");
            filenameWrite = console.next();
            console.close();
        }
        
        File fileRead = new File(filenameRead);
        Scanner fileIn = new Scanner(fileRead);
        PrintWriter fileOut = new PrintWriter(filenameWrite);
        while (fileIn.hasNextLine()) {
            String line = fileIn.nextLine();
            System.out.println(line);
            writeLine(line, fileOut);
        }
        fileIn.close();
        fileOut.close();
    }
}
```

</p>
</details>

#### Write a program that reads a file containing two columns of floating-point ­numbers. Prompt the user for the file name. Print the average of each column.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class P7_04 {
    public static void main(String[] args) throws FileNotFoundException {
        Scanner console = new Scanner(System.in);
        System.out.print("Read from file name: ");
        String fileRead = console.next();
        console.close();

        Scanner fileInput = new Scanner(new File(fileRead));
        
        while (fileInput.hasNext()) {
            String[] line = fileInput.nextLine().split("\\s+");
            double columnA = Double.parseDouble(line[0]);
            double columnB = Double.parseDouble(line[1]);
            double average = (columnA + columnB) / 2;
            System.out.print("Column average: " + average);
            System.out.println();
        }
        fileInput.close();
    }
}
```

</p>
</details>

#### Write a program that asks the user for a file name and prints the number of charac­ters, words,and lines in that file.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class P7_05 {
    public static int countCharacters(String filenameRead) throws FileNotFoundException {
        Scanner fileRead = new Scanner(new File(filenameRead));
        int charactersCount = 0;
        while (fileRead.hasNextLine()) {
            String line = fileRead.nextLine();
            charactersCount += line.trim().length();
        }
        fileRead.close();
        return charactersCount;
    }

    public static int countLines(String filenameRead) throws FileNotFoundException {
        Scanner fileRead = new Scanner(new File(filenameRead));
        int linesCount = 0;
        while (fileRead.hasNextLine()) {
            String line = fileRead.nextLine();
            linesCount += 1;
        }
        fileRead.close();
        return linesCount;
    }

    public static int countWords(String filenameRead) throws FileNotFoundException {
        Scanner fileRead = new Scanner(new File(filenameRead));
        int wordsCount = 0;
        while (fileRead.hasNext()) {
            String word = fileRead.next();
            wordsCount += 1;
        }
        fileRead.close();
        return wordsCount;
    }

    public static void main(String[] args) throws FileNotFoundException {
        Scanner console = new Scanner(System.in);
        System.out.print("Read from file name: ");
        String filenameRead = console.next();
        console.close();

        int charactersCount = countCharacters(filenameRead);
        int wordsCount = countWords(filenameRead);
        int linesCount = countLines(filenameRead);

        System.out.println("Number of characters: " + charactersCount);
        System.out.println("Number of words: " + wordsCount);
        System.out.println("Number of lines: " + linesCount);
    }
}
```

</p>
</details>

#### Write a program Find that searches all files specified on the command line and prints out all lines containing a specified word. For example, if you call

    java Find ring report.txt address.txt Homework.java
    
then the program might print

    report.txt: has broken up an international ring of DVD bootleggers that
    address.txt: Kris Kringle, North Pole
    address.txt: Homer Simpson, Springfield
    Homework.java: String filename;
    
The specified word is always the first command line argument.


<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.ArrayList;
import java.util.Arrays;
import java.util.Scanner;

public class P7_06 {
    public static String findWord;
    public static void main(String[] args) throws FileNotFoundException {
        ArrayList<String> filenames = new ArrayList<String>();
        if (args.length >= 2) {
            findWord = args[0];
            for (int i = 1; i < args.length; i++) {
                filenames.add(args[i]);
            }
            System.out.println(filenames.toString());
        }
        
        for (int i = 0; i < filenames.size(); i++) {
            find(filenames.get(i));
        }
    }
    
    public static void find(String filename) throws FileNotFoundException {
        String output = "";
        Scanner fileRead = new Scanner(new File(filename));
        while (fileRead.hasNextLine()) {
            String[] line = fileRead.nextLine().split("\\s+");
            if (Arrays.asList(line).contains(findWord)) {
                if (output.length() < 1) {
                    output = String.format("%s: %s", filename, line);
                }
                else {
                    output += " " + line;
                }
            }
        }
        fileRead.close();
        System.out.println(output);
    }
}

```

</p>
</details>

####  Write a program that checks the spelling of all words in a file. It should read each word of a file and check whether it is contained in a word list. A word list is available on most Linux systems in the file /usr/share/dict/words . The program should print out all words that it cannot find in the word list.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.HashSet;
import java.util.Scanner;

public class P7_07 {
    public static void main(String[] args) throws FileNotFoundException {
        Scanner console = new Scanner(System.in);
        System.out.print("File to spellcheck: ");
        String fileToRead = console.next();
        console.close();
        HashSet<String> fileWords = wordSet(fileToRead);
        HashSet<String> dictionary = dictionarySet();
        spellcheck(fileWords, dictionary);
    }
    
    public static HashSet<String> wordSet(String filename) throws FileNotFoundException {
        Scanner fileRead = new Scanner(new File(filename));
        HashSet<String> words = new HashSet<String>();
        while (fileRead.hasNext()) {
            String word = fileRead.next();
            words.add(word);
        }
        fileRead.close();
        return words;
    }
    
    public static HashSet<String> dictionarySet() throws FileNotFoundException {
        Scanner dictionaryRead = new Scanner(new File("~/usr/share/dict/words"));
        HashSet<String> dictionary = new HashSet<String>();
        while (dictionaryRead.hasNext()) {
            String word = dictionaryRead.next();
            dictionary.add(word);
        }
        dictionaryRead.close();
        return dictionary;
    }
    
    public static void spellcheck(HashSet<String> words, HashSet<String> dictionary) throws FileNotFoundException {
        for (String word : words) {
            if (!dictionary.contains(word)) {
                System.out.println(word);
            }
        }
    }
}

```

</p>
</details>

#### Write a program that replaces each line of a file with its reverse. For example, if you run
    java Reverse HelloPrinter.java
 then the contents of HelloPrinter.java are changed to

     retnirPolleH ssalc cilbup
     {
     )sgra ][gnirtS(niam diov citats cilbup
     {
     wodniw elosnoc eht ni gniteerg a yalpsiD //
     ;)"!dlroW ,olleH"(nltnirp.tuo.metsyS
     }
     }
     
 Of course, if you run Reverse twice on the same file, you get back the original file.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class P7_08 {
    public static void main(String[] args) throws FileNotFoundException {
        String filename;
        if (args.length == 1) {
            filename = args[0];
        } else {
            System.out.print("File name: ");
            Scanner console = new Scanner(System.in);
            filename = console.next();
            console.close();
        }

        Scanner fileRead = new Scanner(new File(filename));
        while (fileRead.hasNextLine()) {
            String line = fileRead.nextLine();
            line = reverse(line);
            System.out.println(line);
        }
        fileRead.close();
    }

    public static String reverse(String line) {
        return new StringBuilder(line).reverse().toString();
    }
}
|
```

</p>
</details>

#### Write a program that reads each line in a file, reverses its lines, and writes them to  another file. For example, if the file input.txt contains the lines
     Mary had a little lamb
     Its fleece was white as snow
     And everywhere that Mary went
     The lamb was sure to go.
     
 and you run  reverse input.txt output.txt
 then output.txt contains
 
     The lamb was sure to go.
     And everywhere that Mary went
     Its fleece was white as snow
     Mary had a little lamb

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.io.PrintWriter;
import java.util.ArrayList;
import java.util.Scanner;

public class P7_09 {
    public static void main(String[] args) throws FileNotFoundException {
        String filenameRead;
        String filenameWrite;
        if (args.length == 2) {
            filenameRead = args[0];
            filenameWrite = args[1];
        } else {
            Scanner console = new Scanner(System.in);
            System.out.print("File to read: ");
            filenameRead = console.next();
            System.out.print("File to output in: ");
            filenameWrite = console.next();
            console.close();
        }

        ArrayList<String> fileLines = fileLines(filenameRead);
        writeLinesReverse(fileLines, filenameWrite);
    }

    public static ArrayList<String> fileLines(String filename) throws FileNotFoundException {
        ArrayList<String> lines = new ArrayList<String>();
        Scanner fileRead = new Scanner(new File(filename));
        while (fileRead.hasNextLine()) {
            String line = fileRead.nextLine();
            lines.add(line);
        }
        fileRead.close();
        return lines;
    }

    public static void writeLinesReverse(ArrayList<String> lines, String filename) throws FileNotFoundException {
        PrintWriter fileWrite = new PrintWriter(new File(filename));
        for (int i = lines.size() - 1; i > -1; i--) {
            fileWrite.write(lines.get(i));
        }
        fileWrite.close();
    }
}
```

</p>
</details>

#### Get the data for names in prior decades from the Social Security Administration.  Paste the table data in files named babynames80s.txt , etc. Modify the worked_example_1/BabyNames.java program so that it prompts the user for a file name. The numbers in  the files have comma separators, so modify the program to handle them. Can you  spot a trend in the frequencies?

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.io.IOException;
import java.io.PrintWriter;
import java.util.ArrayList;

import org.jsoup.Jsoup;
import org.jsoup.nodes.Document;
import org.jsoup.nodes.Element;
import org.jsoup.select.Elements;


public class P7_10 {
    public static void main(String[] args) throws IOException {
        ArrayList<String> babyNames = scrapeBabyNames("http://www.ssa.gov/oact/babynames/");

        ArrayList<String> maleNames = new ArrayList<String>();
        ArrayList<String> femaleNames = new ArrayList<String>();
        for (int i = 0; i < babyNames.size(); i++) {
            if (i % 2 == 0) {
                maleNames.add(babyNames.get(i));
            } else {
                femaleNames.add(babyNames.get(i));
            }
        }
        System.out.println(maleNames.toString());
        writeBabyNames("male_names.txt", maleNames);
        System.out.println(femaleNames.toString());
        writeBabyNames("female_names.txt", femaleNames);
    }

    public static ArrayList<String> scrapeBabyNames(String url) throws IOException {
        ArrayList<String> babyNames = new ArrayList<String>();
        Document site = Jsoup.connect("http://www.ssa.gov/oact/babynames/").userAgent("Mozilla").get();
        Elements tables = site.select("td");
        for (Element element : tables) {
            String name = element.text();
            if (!isNumeric(name)) {
                babyNames.add(name);
            }
        }
        return babyNames;
    }

    public static boolean isNumeric(String str) {
        return str.matches("-?\\d+(\\.\\d+)?");
    }

    public static void writeBabyNames(String filename, ArrayList<String> names) throws FileNotFoundException {
        PrintWriter fileWrite = new PrintWriter(new File(filename));
        for (int i = 0; i < names.size(); i++) {
            fileWrite.println(names.get(i));
        }
        fileWrite.close();
    }
}

```

</p>
</details>

#### Write a program that reads in worked_example_1/babynames.txt and produces two files,boynames.txt and girlnames.txt , separating the data for the boys and girls.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.io.PrintWriter;
import java.util.HashSet;
import java.util.Scanner;

public class P7_11 {
    public static void main(String[] args) throws FileNotFoundException {
        HashSet<String> maleNames = new HashSet<String>();
        HashSet<String> femaleNames = new HashSet<String>();
        
        Scanner fileRead = new Scanner(new File("babynames.txt"));
        while (fileRead.hasNext()) {
            int rank = fileRead.nextInt();
            String maleName = fileRead.next();
            int matches = fileRead.nextInt();
            double percent = fileRead.nextDouble();
            String femaleName = fileRead.next();
            matches = fileRead.nextInt();
            percent = fileRead.nextDouble();
            
            maleNames.add(maleName);
            femaleNames.add(femaleName);
        }
        fileRead.close();
        writeBabyNames("male_baby_names", maleNames);
        writeBabyNames("female_baby_names", femaleNames);
    }

    public static void writeBabyNames(String filename, HashSet<String> names) throws FileNotFoundException {
        PrintWriter fileWrite = new PrintWriter(new File(filename));
        for (String name : names) {
            fileWrite.println(name);
        }
        fileWrite.close();
    }
}

```

</p>
</details>

#### Write a program that reads a file in the same format as worked_example_1/babynames.txt and prints all names that are both boy and girl names (such as Alexis or Morgan).

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.HashSet;
import java.util.Scanner;

public class P7_12 {
    public static void main(String[] args) throws FileNotFoundException {
        HashSet<String> maleNames = getNames("male_names.txt");
        HashSet<String> femaleNames = getNames("female_names.txt");
        HashSet<String> babyNames = getNames("babynames.txt");

        String output = "";
        for (String name : babyNames) {
            if (maleNames.contains(name) && femaleNames.contains(name)) {
                output += " " + name;
            }
        }
        System.out.println((output.length() < 1)? "No matches" : output);
    }

    public static HashSet<String> getNames(String filename) throws FileNotFoundException {
        HashSet<String> names = new HashSet<String>();
        Scanner fileRead = new Scanner(new File(filename));
        while (fileRead.hasNext()) {
            String name = fileRead.next();
            names.add(name);
        }
        fileRead.close();
        return names;
    }
}

```

</p>
</details>

#### Write a program that asks the user to input a set of floating-point values. When the user enters a value that is not a number, give the user a second chance to enter the value. After two chances,quit reading input. Add all correctly specified values and print the sum when the user is done entering data. Use exception handling to detect improper inputs.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
import java.util.InputMismatchException;
import java.util.Scanner;

public class P7_13 {
    public static void main(String[] args) {
        Scanner console = new Scanner(System.in);
        System.out.print("Number: ");
        int tries = 2;
        double sum = 0;
        int count = 0;
        while (tries > 0) {
            try {
                sum += console.nextDouble();
                count += 1;
            } catch (InputMismatchException e) {
                String badInput = console.next();
                tries -= 1;
            }
        }
        console.close();
        double average = sum / count;
        System.out.println("Average: " + average);
    }
}
```

</p>
</details>
