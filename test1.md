 IN1010 V19 - Seminaroppgaver uke 1

## Oppgave 1 
Følgende program er skrevet i Python. Skriv programmet på nytt med Java-syntaks (merk at alle metodene i dette tilfellet skal være offentlige):

``` python
class Person:
	def __init__(self, alder, navn):
		self._alder = alder
		self._navn = navn
	
	def skrivUt(self):
		print(self._navn, self._alder)
	
	def haBursdag(self):
		self._alder +=1
```
<details><summary>💾 Løsningsforslag </summary>
<p>

```java
class Person {
    private int alder;
    private String navn;

    public Person(int alder, String navn) {
        this.alder = alder;
        this.navn = navn;
    }
    
    public void skrivUt() {
        System.out.println(this.navn + " " + this.alder);
    }

    public void haBursdag() {
        this.alder += 1;
    }
}
```

</p>
</details>


***

## Oppgave 2
### 2a
Skriv en klasse Motorsykkel.java. Klassen skal inneholde følgende instansvariabler:
- `private int kilometerstand`
- `private String registreringsnummer`
- `private int produksjonsnummer`

Klassen skal også inneholde en konstruktør som tar inn registreringsnummeret. Instansvariabelen `kilometerstand` skal starte med verdien `0`.

I tillegg skal klassen inneholde en `private static int teller`, som starter med verdien `0`. Denne skal dere ta i bruk i konstruktøren, slik at hvert nye `Motorsykkel`-objekt får et unikt produksjonsnummer.

<details><summary>💾 Løsningsforslag </summary>
<p>

```java
class Motorsykkel {
    private int kilometerstand;
    private String registreringsnummer;
    private int produksjonsnummer;
    private static int teller = 0;
    
    public Motorsykkel (String regnr) {
        this.kilometerstand = 0;
        registreringsnummer = regnr;
        
        this.produksjonsnummer = teller;
        teller++;
    }
}
```

</p>
</details>


### 2b
Skriv en metode `public int hentKilometerstand`. Metoden tar ikke imot noen parametere, men skal returnere antall kilometer motorsykkelen har kjørt. Skriv deretter en tilsvarende metode `public int hentProduksjonsnummer`.

<details><summary>💾 Løsningsforslag </summary>
<p>

```java
public int hentKilometerstand() {
    return kilometerstand;
}

public int hentProduksjonsnummer() {
    return produksjonsnummer;
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
Hvilke feil finnes i følgende klasse?

``` java
class Baat {
    private String regNr;
    private int kilometer;

    public Baaten(String regNr){
        this.regNr = regNr;
        this.kilometerstand = 0;
    }
    
    //Skriver info om baaten
    public void skrivBaat() {
        print(regNr);
        print(kilometerstand);
    }
}
```


<details><summary>💾 Løsningsforslag </summary>
<p>

```java
class Baat {
    private String regNr;
    private int kilometer;

    public Baaten(String regNr){    // Feil navn på konstruktør
        this.regNr = regNr;
        this.kilometerstand = 0;    // Feil navn (kilometer/kilometerstand)
    }

    // Skriver info om baaten
    public void skrivBaat() {
        print(regNr);               //Skal være System.out.println()
        print(kilometerstand);
    }
}
```

</p>
</details>

### 3b
Gitt følgende variabler:
```java
int a = 3;
String b = "4";
double c = 10.2;
```
Er følgende kodesnutter lovlige? Hvis ja, hva skrives ut?

`System.out.println(a + 5);`
<details><summary>💾 Fasit </summary>
<p>

`8`

</p>
</details>

___

`System.out.println(a + b);`
<details><summary>💾 Fasit </summary>
<p>

`34`

</p>
</details>

___

```java
int sum = a + b;
System.out.println(sum);
```
<details><summary>💾 Fasit </summary>
<p>

Nei, kan ikke legge `String` inn i `int`

</p>
</details>

___

```java
int sum = a + c;
System.out.println(sum);
```


<details><summary>💾 Fasit </summary>
<p>

Nei, mister presisjon. Bruk `(int)` for å caste

</p>
</details>


***


### Oppgave 4
Følgende klasseskjelett er gitt:

```java
class Kaningaard {
    
    private Kanin [] kaniner = new Kanin[100];
    
    public boolean full() { . . . }
    public boolean tom () { . . . }
    public Kanin finnEn(String navn) { . . . }
    public void settInn (Kanin kanin) { . . . }
    public void fjern(String navn) { . . . }
}
```

### 4a
Skriv ferdig klassen `Kaningaard` ved å fylle ut metodene. Dere kan gå ut fra at alle kaniner skal ha forskjellig navn, og derfor må dere ta høyde for at det ikke er lov å sette inn en kanin to ganger (altså med samme navn som en i lista). Dere skal også ta høyde for noen andre problemer som kan oppstå og gi gode feilmeldinger. To eksempler er dersom man forsøker å sette inn en eller når man forsøker å fjerne en kanin som ikke er i listen. Dere kan anta at klassen `Kanin` inneholder en metode `hentNavn`.

### 4b
Skriv et hovedprogram der dere gjør minst tre tester av de forskjellige delene av klassen `Kaningaard`. Test for eksempel tilfeller som innsetting av kanin ved full kaningård eller fjerning av ikke-eksisterende kanin.

### 4c
Tegn datastrukturen slik den ser ut etter at dere har kjørt hovedprogrammet deres. (Tips: Se notatet om datastrukturtegninger på emnets semesterside).



<details><summary>💾 Løsningsforslag </summary>
<p>

```java
class Kaningaard {

    private Kanin[] kaniner = new Kanin[100];

    public boolean full() {
        for (int i = 0; i < kaniner.length; i++) {
            if (kaniner[i] == null) {
                return false;
            }
        }
        return true;
    }

    public boolean tom() {
        for (int i = 0; i < kaniner.length; i++) {
            if (kaniner[i] != null) {
                return false;
            }
        }
        return true;
    }

    public Kanin finnEn(String navn) {
        for (int i = 0; i < kaniner.length; i++) {
            if (kaniner[i] != null && kaniner[i].hentNavn().equals(navn)) {
                return kaniner[i];
            }
        }
        return null;
    }

    public void settInn(Kanin kanin) {

        if (finnEn(kanin.hentNavn()) != null) {
            System.out.println("Kaninen finnes alt i kaningaarden!");
        } else if (full()) {
            System.out.println("Det er ikke plass til flere kaniner!");
        } else {

            boolean sattInn = false;
            int teller = 0;

            while (teller < kaniner.length && !sattInn) {
                if (kaniner[teller] == null) {
                    kaniner[teller] = kanin;
                    sattInn = true;
                }
                teller++;
            }
        }
    }

    public void fjern(String navn) {
        boolean funnet = false;
        int teller = 0;

        while (teller < kaniner.length && !funnet) {
            if (kaniner[teller] != null && kaniner[teller].hentNavn().equals(navn)) {
                kaniner[teller] = null;
                funnet = true;
            }
            teller++;
        }

        if (!funnet) {
            System.out.println("Fant ikke kaninen " + navn + ".");
        }
    }

    // Et par tester ...
    public static void main(String[] args) {
        Kaningaard kg = new Kaningaard();
        kg.settInn(new Kanin("Kaare"));
        kg.settInn(new Kanin("Kaare"));
        kg.fjern("Kaare");
        kg.fjern("Kaare");

    }
}
```

</p>
</details>
