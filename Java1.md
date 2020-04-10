## Emri i klasës në Java 

Cili është një emër i mirë i klasës në Java?

a) class bok

b) class BOK

c) class Bok


<details><summary>💾 Løsningsforslag </summary>
<p>
💡 Sugjerim: Opsioni `c) class Bok` është përgjigjja e saktë. Asnjë nga emrat e klasave nuk do të shkaktojë gabime të përpilimit, por në Java, konventa është që të shkruani emrat e klasave me një shkronjë të parë të madhe, dhe shkronjat e mbetura në emrin e klasës duhet të jenë të vogla. Mos harroni gjithashtu se emri i skedarit të kësaj klase duhet të jetë Bok.java.

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
class ShumaNr {
    public static void main(String[] args) {
        int a;
        int b;

        a = 4;
        b = 5;

        System.out.println("Shuma eshte: " + (a + b));
    }
}
```

</p>
</details>

## Gjeni gabime sintaksore

Gjeni 5 gabime në programin vijues:

```
class Printim {
    public stitac void main(String args) (
        System.out.println("Lumenjtë kryesor të Kosovës janë:Drini i Bardhe,Ereniku, Ibri")
        System.out.println("po edhe Lumi Drenica etj..);
    }
}
```

<details><summary>💾 Zgjidhje alternative </summary>
<p>
    
Rreshti 2: "stitac" duhet të jetë "**static**".
    
Rreshti 2: "(String args)" duhet të jetët "**(String[] args)**".

Rreshti 2: Kllapa në fund të rreshtit duhet të jenë kllapë e madhe **{**.

Rreshti 3: Një pikëpresje **;** që mungon në fund të rreshtit.

Rreshti 4: Mungojnë thonjëzat **"** përmbyllëse në varg brenda deklarimit të `println`.


</p>
</details>

## Krahasimi i dy numrave

Emri i Skedarit: `Krahasim.java`

Krijoni një program që përmban dy ndryshore të numrave të plotë; `a` dhe `b`. Jepni vlerat e variablave sipas zgjedhjes suaj.

Bëni një kontroll nëse `a` është më i madh se `b`. Shtypja në ekran ose `a` është më e madhe se `b` ose `a` nuk është më e madhe se `b`.

Ndryshoni vlerat që keni vendosur për `a` dhe `b` dhe kontrolloni që rezultati të pritet në të gjitha rastet.

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
class Sammenlign {
    public static void main(String[] args) {
        int a = 4;
        int b = 2;

        if(a > b) {
            System.out.println("a er storre enn b");
        } else {
            System.out.println("a er ikke storre enn b");
        }
    }
}
```

</p>
</details>

## Vlerat logjike

Emri i Skedarit: `VleraLogjike.java`

a) Krijoni një program që përmban dy ndryshore logjike `(boolean)` me emra të `saktë` dhe `pasaktë`, dhe jepni vlerat e variablave të **`true`** dhe **`false`**. Shtypni përmbajtjen e një ndryshore duke përdorur komandën **`System.out.println`** dhe shikoni se si duket në kohën e funksionimit.

b) Zgjeroni programin tuaj me dy nëse testoni. E para është që të krahasohen dy variablat në mënyrë që rezultati të jetë i vërtetë me vlerat që i keni dhënë në a) dhe pastaj të shtypni "Testi i parë u ekzekutu!".

Testi i dytë është krahasimi i dy ndryshoreve në atë mënyrë që rezultati të jetë i rremë (me të njëjtat dy vlera). Ky test duhet të ketë një degë tjetër që shtyp "Testet e tjera nuk u ekzekut!"

<details><summary>💾 Zgjidhje alternative </summary>
<p>

```java
class VleraLogjike {
    public static void main(String[] args) {
        boolean sakte = true;
        boolean pasakte = false;

        if (sakte != pasakte) {
            System.out.println("Testi i parë u ekzekutu!");
        } else {
            System.out.println("Diqka shkoi gabim!");
        }

        if (sakte == pasakte) {
            System.out.println("Diqka shkoi gabim!");
        } else {
            System.out.println("Testi i dytë u ekzekutu!");
        }
    }
}
```

</p>
</details>

## Drejtkëndësh

Emri i Skedarit: `Drejtkendesh.java`

a) Ju duhet të shkruani një klasë Drejtkëndësh me përfaqësimin e të dhënave dhe metodat. Drejtkëndëshat kanë një gjerësi dhe një gjatësi, dhe ofrojnë ndërfaqet e mëposhtme:
```java
class Rektangel {

  public Rektangel (double gjatesia, double gjeresia) {   // Konstruktør
  }

  public void rritjeGjatesise (int rritje) {  // Gjatësia siç përcaktohet
  }

  public void rritjeGjeresise (int rritje) {  // Gjatësia siç përcaktohet
  }

  public double sperfaqe() {     // Llogarit sipërfaqen
  }

  public double perimetri() {   // Llogarit perimetrin
  }
}
```

b) Shkruaj një program kryesor siç janë:

- krijon dy drejtkëndësha të madhësive opsionale
- shtyp(shfaq) të dy zonat
- Rritni gjatësinë e njërit dhe gjerësinë e tjetrit
- shtyp(shfaq) të dy perimetrat

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
