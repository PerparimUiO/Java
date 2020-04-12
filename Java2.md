## Krahasimi midis dy numrave

Emri i skedarit: `Diferensa.java`

Krijoni një program që kërkon dhe ngarkon dy numër të plotë. Programi do të llogarisë më tej ndryshimin midis dy numrave dhe do të shtypë përgjigjen. Këtu është një shembull i asaj se si mund të duket një program:

```java
Vendosni vlerën e x:
> 25
Vendosni vlerën e y:
> 19
Dallimi midis x dhe y është 6.
```

Ju nuk duhet të mendoni se numri i parë mund të jetë më i vogël se i dyti. Nuk është e nevojshme të llogarisni vlerën absolute të ndryshimit (por përpiquni të zbuloni se si bëhet nëse doni një sfidë shtesë).

<details><summary>💾 Zgjidhje alternative </summary>
<p>
    
```java
import java.util.Scanner;

class Diferensa {
    public static void main(String[] args) {
        // Deklaron variablat
        String lexo;
        int x;
        int y;

        // Krijon skaner për të lexuar nga tastiera.
        Scanner tast = new Scanner(System.in);

        System.out.println("Vendosni vlerën e x:");
        lexo = tast.nextLine(); // azhurnon(përditëso) vlerën për të lexuar.
        x = Integer.parseInt(lexo); // konverton nga String në int.

        System.out.println("Vendosni vlerën e y:");
        lexo = tastatur.nextLine(); //azhurnon vlerën për të lexuar.
        y = Integer.parseInt(lest); //konverton nga String në int.

        System.out.println("Dallimi midis x dhe y është: " + (x-y));
    }
}
```

Vini re se këtu ne ripërdorim ndryshoren e lexuar për të ngarkuar x dhe y. Ne gjithashtu mund të kishim dy ndryshore të `String` për të lexuar, ose i hedhur ato krejt, dhe në vend të kësaj kemi përdorur `Integer.parseInt()` direkt në inputin e përdoruesit.

</p>
</details>

***

## Produkti i dy numrave

Emri i skedarit: `Produkti.java`

a) Krijoni një program që kërkon dhe lexon dy integrues. Programi do të llogarisë më pas produktin e dy numrave dhe do të shtypë përgjigjen.

Këtu është një shembull i asaj se si mund të duket një program:

```java
Vendosni vlerën e x:
> 5
Vendosni vlerën e y:
> 4
Produkti i x dhe y është 20.
```

b) Modifikoni programin në mënyrë që programi të kontrollojë nëse ndryshimi midis numrave është pozitiv apo negativ dhe shtyp një mesazh të përshtatshëm për përdoruesit.

<details><summary>💾 Zgjidhje alternative </summary>
<p>
    
```java
import java.util.Scanner;

class Produkti {
    public static void main(String[] args) {
        int x;
        int y;
        Scanner tast = new Scanner(System.in);

        System.out.println("Vendosni vlerën e x:");
        x = Integer.parseInt(tast.nextLine());

        System.out.println("Vendosni vlerën e y:");
        y = Integer.parseInt(tast.nextLine());

        System.out.println("Produkti i x dhe y është: " + (x*y));
    }
}
```

Këtu mund të përdorni edhe `variabla të përkohshëm String` për të mbajtur vlerat para `parseInt()`. Zgjidhja e mësipërme konverton vlerën e hyrë të llojit `String` në `int` drejtpërdrejt.

</p>
</details>

***

## Më (e vogël se) ose më (e madhe se)

Emri: MeEVogelMadhe.java

a) Krijoni një program që merr një numër nga përdoruesi dhe shtypni nëse numri është më i vogël se ose më i madh se 10.

b) Pastaj shtoni një provë tjetër për të kontrolluar nëse numri është më pak se ose më i madh se 20.

c) Ndryshoni programin në mënyrë që përdoruesi të marrë vetëm një feedback për numrin e futur.

Programi duhet të duket si ky gjatë ekzekutimit:

```java
Vendosni një numër:
> 13
Numri është midis 10 dhe 20

Vendosni një numër:
> 9
Numri është më pak se 10

Vendosni një numër:
> 22
Numri është mbi 20
```
<details><summary>💾 Zgjidhje alternative </summary>
<p>
    
```java
import java.util.Scanner;

class MindreStorre {
    public static void main(String[] args) {
        int numri;
        Scanner tast = new Scanner(System.in);

        System.out.println("Vendosni një numër:");
        numri = Integer.parseInt(tastatur.nextLine());

        if(numri < 10) {
            System.out.println("Numri është më pak se 10");
        } else if(numri > 10 && tall < 20) {
            System.out.println("Numri është midis 10 dhe 20");
        } else {
            System.out.println("Numri është mbi 20");
        }
    }
}
```

</p>
</details>

***

## 3a

```java

```
<details><summary>💾 Zgjidhje alternative </summary>
<p>
    
```java

```

</p>
</details>

***

## 3a

```java

```
<details><summary>💾 Zgjidhje alternative </summary>
<p>
    
```java

```

</p>
</details>

***
