## Emri i klasës në Java 

💡 Sugjerim: Cili është një emër i mirë i klasës në Java?

a) class bok

b) class BOK

c) class Bok


<details><summary>💾 Løsningsforslag </summary>
<p>
Opsioni c) është përgjigjja e saktë. Asnjë nga emrat e klasave nuk do të shkaktojë gabime të përpilimit, por në Java, konventa është që të shkruani emrat e klasave me një shkronjë të parë të madhe, dhe shkronjat e mbetura në emrin e klasës duhet të jenë të vogla. Mos harroni gjithashtu se emri i skedarit të kësaj klase duhet të jetë Bok.java.

</p>
</details>

***

## Informacione personale

Emri i Skedarit: `Personinfo.java`

1. Krijoni një skedar të ri në një redaktues teksti (për shembull, Atom, Sublime Text,Vim, Emacs, apo Notepad++) dhe ruajeni skedarin si `Personinfo.java`
2. Krijoni metodën `public static void main(String[] args)` në klasë.
3. Përdorni `System.out.println ()` për të shtypur emrin tuaj terminali.
4. Pastaj zgjeroni aplikacionin tuaj në mënyrë që të printojë edhe numrin tuaj të telefonit dhe adresën e rrugës në terminal, në linjën e tij shtesë.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
class Personinfo {
    public static void main(String[] args) {
        System.out.println("Perparim Shala");
        System.out.println("222000111");
        System.out.println("Rr.Ilaz Kodra, Drenas");
    }
}
```
Për të kompajluar dhe ekzekutuar në terminal:

- `javac Personinfo.java`
- `java Personinfo`

</p>
</details>


## Shuma e numrave të plotë
Emri i Skedarit: `ShumaNr.java`

Shkruaj një program me një klasë `ShumaNr` duke përdorur një metodë kryesore. Krijoni dy ndryshore të tipit **int** dhe i quajini ato `a` dhe `b`. Ruani vlerat `4` dhe `5` në variabla. Shfaq shumën e numrave.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
class ShumaNr.java {
    public static void main(String[] args) {
        int a;
        int b;

        a = 4;
        b = 5;

        System.out.println("Summen er: " + (a + b));
    }
}
```

</p>
</details>

### 2c
Skriv en metode `public void kjoer` som tar imot et parameter `int antallKilometer`. Metoden skal legge `antallKilometer` til instansvariabelen `int kilometerstand`.

<details><summary>💾 Løsningsforslag </summary>
<p>

```java
public void kjoer(int antallKilometer) {
    kilometerstand += antallKilometer;
}
```

</p>
</details>

### 2d
Skriv en klasse `MotorsykkelProgram.java`. Klassen skal inneholde en `main`-metode. Opprett et objekt av klassen `Motorsykkel` inne i `main`-metoden med et registreringsnummer.

Deretter skal dere skrive en `while`-løkke som skal gå 5 ganger. For hver gjennomkjøring av løkken skal dere kalle på `Motorsykkel`-objektets `kjoer`-metode med `10` som parameter.

<details><summary>💾 Løsningsforslag </summary>
<p>

```java
class MotorsykkelProgram {
    public static void main(String[] args) {
        Motorsykkel m1 = new Motorsykkel("AB1234");

        int t = 0;
        while (t < 5) {
            m1.kjoer(10);
            t++;
        }
    }
}
```

</p>
</details>

### 2e
Hvis vi kalte på `Motorsykkel`-objektets `hentKilometerstand`-metode nå, hvilket resultat får vi?

<details><summary>💾 Løsningsforslag </summary>
<p>

```java
System.out.println(m1.hentKilometerstand()); // 50
```

</p>
</details>

### 2f
Vi tenker oss at vi oppretter to `Motorsykkel`-objekter til. Hvilke produksjonsnummere vil de ha?

<details><summary>💾 Løsningsforslag </summary>
<p>

```java
Motorsykkel m2 = new Motorsykkel("HELLO1");
Motorsykkel m3 = new Motorsykkel("22TUUT");
System.out.println("m2: " + m2.hentProduksjonsnummer()); //1
System.out.println("m3: " + m3.hentProduksjonsnummer()); //2
```

</p>
</details>


***

## Oppgave 3
### 3a
