## Studentët dhe rezultatet e kuizit

a) Implementimi i një klase 'Studenti'. Një student ka një emër, një rezultat të përgjithshëm kuizi dhe një numër kuizesh në të cilat ka marrë pjesë studenti. Këto vlera duhet të shprehen në konstruktor.

Klasa duhet të ketë metodat e mëposhtme (përveç konstruktorit):

```java
merrEmrin();
shtoRezNeKuiz(int rezultati);
merrRezPergjithshem();
merrRezMesatar();
```
b) Krijoni metodën AddQuizScore në mënyrë që të shtojë 1 në numrin e kuizeve studenti ka marrë pjesë në çdo herë që të shtohet një rezultat.

c) Krijoni një klasë të re duke përdorur një metodë kryesore.

d) Krijoni tre objekte të reja Studenti, me emrin "Joakim", "Kristin" dhe "Dita".

e) Pastaj thirrni metodën AddQuizScore për të gjithë studentët të paktën dy herë secila.

f) Shtypni të gjitha pikët e përgjithshme të studentëve dhe notat mesatare.

<details><summary>💾 Zgjidhje alternative </summary>
<p>
    
```java
a-b)
class Student{
  private String emri;
  private int rezulltatiIKuizit;
  private int nrIKuizeve;

  public Student(String emri, int rezIKuizit, int nrIKuizeve){
    this.emri = emri;
    this.rezIKuizit = rezIKuizit;
    this.nrIKuizeve = nrIKuizeve;
  }

  public String merrEmrin(){
    return navn;
  }

  public void shtoRezNeKuiz(int rezultati){
    rezulltatiIKuizit += rezultati;
    nrIKuizeve++;
  }

  public int merrRezPergjithshem(){
    return rezulltatiIKuizit;
  }

  public int merrRezMesatar(){
    return rezulltatiIKuizit/nrIKuizeve;
  }
}

c-f)
class RezulltatiIKuizit{
  public static void main(String[] args) {
    Student ajan = new Student("Ajan", 234, 79);
    Student ajana = new Student("Ajana", 34, 1);
    Student ti = new Student("Ti", 46325, 358);

    for(int i = 0; i < 3; i++){
      ajan.shtoRezNeKuiz((i + 1) * 2);
      ajana.shtoRezNeKuiz((i + 1) * 3);
      ti.shtoRezNeKuiz(i + 1);
    }

    shfaqStudent(ajan);
    shfaqStudent(ajana);
    shfaqStudent(ti);
  }

  // krijon një metodë për shfaqje(shtypje) për të lëshuar të njëjtin kod
  // disa herë
  public static void shfaqStudent(Student student){
    System.out.println("--------------");
    System.out.println(student.merrEmrin());
    System.out.println("Rezultati i Përgjithshëm: " + student.merrRezPergjithshem());
    System.out.println("Rezultati mesatar: "  + student.hentGjennomsnitteligScore());
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
