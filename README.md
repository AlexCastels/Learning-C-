## Indice
1. [Introduzione](#introduzione)
2. [Tipizzazione](#tipizzazione)
3. [Variabili](#variabili)
4. [Casting](#casting-conversione)
5. [Manipolazione stringhe](#manipolazione-stringhe)
6. [Metodi stringhe](#metodi-stringhe)
7. [Manipolazione numeri](#manipolazione-numeri)
8. [Input utenti](#Input-utenti-console)
9. [Eccezioni](#eccezioni)
10. [Operatori Logici](#Operatori-Logici)
11. [IF/ELSE](#Costrutti-IF--ELSE--ELSE-IF)
12. [Operatore ternario](#Operatore-Ternario )
13. [Switch case](#Switch-case)
14. [Loop while/dowhile](#Loop-While--dowhile)
15. [For e ForEach](#Ciclo-For-e-Foreach)
16. [Break e continue](#Break-e-Continue)
17. [Overloading Method](#Overloading-Method)
18. [Array](#Array-in-C)
19. [Matrici](#Matrici---Array-Multidimensionali)
20. [Matrici Irregolari](#Matrici-Irregolari)
21. [ArrayList](#ArrayList)
22. [List](#LIST)
23. [Hashtable](#Hashtable)
24. [Dictionary](#Dictionary-Dict)
25. [Stack](#Stack)
26. [Queue (CHIU' | CODA)](#Queue)
27. [OOP - Object Oriented Programming](#OOP---Object-Oriented-Programming)
28. [Constructor](#Constructor)
29. [Overloading constructor](#overloading-constructor-sovraccarico-di-costruttori)
30. [Getter & Setter](#getter--setter)
31. [KeyWord STATIC](#KeyWord-STATIC)
32. [Estendere classi](#Estendere-classi-extends)
33. [VIRTUAL , OVERRIDE , SEALED](#VIRTUAL--OVERRIDE--SEALED)
34. [Interfacce](#INTERFACCE)
35. [Polimorfismo](#POLIMORFISMO)
36. [Classi Astratte](#CLASSI-ASTRATTE)
37. [Modificatori di accesso](#MODIFICATORI-DI-ACCESSO)
38. [Enum](#ENUMERATOR---ENUM)
39. [DateTime](#DATETIME)
40. [Nullable - Valori Opzionali](#NULLABLE---VALORI-OPZIONALI)

***

# Appunti C#

***

# Introduzione

C# E' un linguaggio orientato agli oggetti OOP sviluppato da Microsoft, con tipizzazione statica (cioè dichiarata sul momento).
Ha diversi utilizzi in diversi ambiti, Web front and back, app desktop, Android e IOS con Xamarin e nel gaming con Unity.
Si utilizza L'IDE Visual Studio per gestire i progetti.
Viene utilizzato tramite il framework .NET per la gestione delle applicazioni, e ASP.NET per la gestione dei dati asincroni.

### Compilazione

Il codice C# viene compilato in un formato intermedio chiamato Common Intermediate Language (CIL), che viene poi eseguito dalla Common Language Runtime (CLR) della piattaforma .NET. Questo approccio offre vantaggi in termini di portabilità e ottimizzazione delle prestazioni.

***

# Struttura Progetto

Il progetto può essere suddiviso in più namespace, visti come 'cartelle', comunque spazi logici dove separare porzioni di codice, per definire la struttura complessiva.

- Main() è l'entry point dell'applicazione, è il metodo principale che verrà avviato come primo punto

***

# Tipizzazione

C# è un linguaggio tipizzato, per poter dichiarare un metodo o una variabile che sia bisogna dichiararne il tipo.

I tipi accettati sono leggermente differenti da JS, abbiamo

- string => stringa "" dentro doppi apici
- char => carattere '' dentro singoli apici, contiene un singolo carattere

- int => intero , fino a 2 miliardi circa come numero intero, positivo e negativo
- long => lungo , oltre i 2 miliardi
- float => con virgola , conserva tra i 6-9 numeri (4.5f)
- double => 15-17 num dopo la virgola (mediameente precisi) (4.5)
- decimal => 28-29 num dopo la virgola (precisi) (4.5m)

- bool => booleano

***

# Variabili

Possono essere dichiarate , inizializzate e assegnate.
Esistono sempre let const e var, dove let non viene dichiarato, ma const si, es: `const string name;` .

```
    string name = "Alex" ;  //inizializzata con valore di dafault
    string name ;           //dichiarata
    name = 'Alex' ;         //assegnare il valore ad una variabile esistente 
```

***

# Casting-Conversione

Ci sono 3 tipo di casting:

- Implicito

Un casting per ampliare il valore di una variabile, dunque assegnare una variabile più piccola ad una più grande
```
    int prova = 345;
    long querty = prova;

    float prova = 345f;
    double qwerty = prova;
```

- Esplicito 

Dove forziamo la conversione

```
    double prova = 35.25;
    int qwerty = (int)prova;
```

- Metodi di conversione

Per convertire totalmente il tipo del dato

```
    int prova = 35;
    double doppio = 35.25;
    bool qwerty = true;

    string stringa = Convert.ToString(prova);
    Convert.ToInt32(doppio);
```

Convert è una classe che appartiene a System, contiene diversi metodi.

***

# Manipolazione Stringhe

E' possibile manipolare le stringhe 

- escape (inserire doppi apici in una stringa)

Per manipolare le stringhe si utilizzano \\ (backslash) \n (newLine) 
```
string stringa = "Citazione: \"Si vive una volta sola"\";

Console.WriteLine(stringa);

```

- concat
metodo classico 

```
    string name = 'Alex' ;
    string surname = 'Castelli' ;
    string result = "Ciao sono " + nome + " " + cognome ; 
```

- format (formattazione)

(come in node) la stringa indicizza nelle {} le variabili inserite dopo in maniera ordinata, è possibile grazie al metodo delle stringhe format

```
    string result = string.Format("Ciao sono {0} {1}" , name , surname) ;
```

- interpolation

similmente a js con il ${}
```
    string result = $"Ciao sono {name} {surname}" ;
```

## Metodi stringhe

Accediamo ai metodi delle stringhe tramite la classe `string.` appartentne a System. Possiamo accedervi su qualsiasi variabile stringa

```
    string name = 'Alex' ;
    string surname = 'Castelli' ;

    string result = name.ToUpper() ; 
    int lenghtName = name.Length ;
    char carattere = name[0]; //possiamo accedere agli indici della stringa 
    Console.WriteLine(name.IndexOf("a")); // ritorna l'indice del carattere 
    Console.WriteLine(name.Substring(5)); // divide la stringa a partire dall'indice indicato, per andare a ritroso string.Lenght - n
```

***

# Manipolazione numeri

Abbiamo a disposizione tutte le operazioni aritmetiche , anche il modulo % , e diversi metodi matematici accessibili con Math

```
    int a = 5 ;
    int b = 2 ;
    int result = a + b ;

    //l'incremento a seconda di dove viene scritto ha precedenza di esecuzione, diversamente da JS, se scritto dopo la variabile non verrà
    // calcolato (es a++)
    int c = ++a // incremento di 1 
```

- assegnazione

int a = 5 ;
a += 5 ; //aggiunge 5, come fare a = a + 5, vale con tutti gli operatori 

***

# Input utenti console

Possiamo salvare gli input dell'utente sempre tramite la classe Console, il ritorno sarà sempre sottoforma di stringa

``` 
    Console.WriteLine("Inserisci un numero");
    string first = Console.ReadLine();
    Console.WriteLine("Inserisci un numero");
    string second = Console.ReadLine();

    int firstParsed = int.Parse(first);
    int secondParsed = int.Parse(second);
    int result = firstParsed + secondParsed;

    Console.WriteLine($"Il risultato è: {result}");
```

Gli input non sono vincolati di default, e devono essere controllati

***

# Eccezioni

Bisogna sempre gestire gli input immessi da un utente, con questo utilizziamo try, catch e finally

C# Permette di gestire delle eccezioni che sono classi appartenenti al tipo di dato, e ogni singola eccezione gestisce un caso specifico
Come il formato o l'argomento nullo ad esempio, con il blocco try catch possiamo gestire queste eccezioni.

```
    int firstParsed = 0;
     int secondParsed = int.Parse(second);

     try
     {
         firstParsed = int.Parse(first);
     }
     catch (FormatException)
     {
         Console.WriteLine("Attenzione: Inserire un numero");
     }
     catch (ArgumentNullException)
     {
         Console.WriteLine("Attenzione: Inserire un numero");
     }
     
     int result = firstParsed + secondParsed;
     Console.WriteLine($"Il risultato è: {result}");
```

***

# Operatori Logici

Sono gli stessi di JS solamente che l'uguaglianza è con due `==` 

***

# Costrutti IF / ELSE / ELSE IF

Il costrutto è come quello in JS.

```
    bool isOnline = true ;

    if(isOnline){
        Console.WriteLine("Sei Online")
    } else {
        Console.WriteLine("Sei OffLine")
    }
```

# Operatore Ternario 

Funziona come in JS.

```
    condizione ? caso1 : ( condizione ? caso1 : caso2 ) //esempio annidato
```

# Switch case

La sintassi è simile a JS

```
    int age = 18

    switch (age) {
        case age < 18:
            Console.WriteLine("Minorenne");
            break;
        case age > 18:
            Console.WriteLine("Maggiorenne");
            break;
        default:
            Console.WriteLine("Mai nato");
            break;
    } 
```

# Loop While / dowhile

while(condizione){} il cliclo andrà avanti fintanto che la condizione è rispettata.

```
    int i = 0; //iteratore

    while( i <= 10 ){
        Console.WriteLine(i) ;
        i++ ;
    }
```

- do while

Esegue il controllo dopo, permette di eseguire almeno una volta la funzione da eseguire nel ciclo a priori dalla condizione.

```
    do {
        Console.WriteLine(i);
        i++;
    } while ( i <= 10 ) ;
```

Possiamo inserire if all'interno di un loop while

# Ciclo For e Foreach

Come in JS.
La differenza è che l'iteratore appartiene solo nello scope del For, e non esternament.
- for

```
    for ( int i = 0 ; i < 5; i++ ){ }
```

- foreach

il foreach è simile a quello utilizzato nel template in Angular.

```
    string[] names = { "Alex" , "Marco" , "Luca" };

    foreach(string elemento in names){
        Console.WriteLine(elemento);
    }
```

# Break e Continue

Permettono di gestire i cicli

```
    for ( int i = 0 ; i < 5; i++ ){
        if(i === 3) break ; //esce dal ciclo in base alla condizione
        Console.WriteLine(i);
     }
```

```
    for ( int i = 0 ; i < 5; i++ ){
        if(i === 3) continue ; //salta l'iterazione che corrisponde alla condizione, dunque il 3 viene saltato.
        Console.WriteLine(i);
     }
```

# Metodi e Params

Devono essere dichiarati al di fuori della funzione Main(), possiamo inserire al suo interno dei parametri.

I metodi devono essere definiti con la prima lettera maiuscola in C#

```
    static void Saluta(string name = "default"){
        Console.WriteLine($"Hello {name}");
    }
```

# Overloading Method

E' la possibilita di poter definire più metodi con lo stesso nome, ma con diversa firma (parametri definiti)

Vale cambiare solo il numero o il tipo dei parametri definiti

```
    static void Saluta(string surname = "default"){
        Console.WriteLine($"Hello {surname}");
    }

    static void Saluta(string name , string surname){
        Console.WriteLine($"Hello {name} {surname}");
    }
```

# Array in C#

Sono diversi da JS nella sintassi e nella gestione.

Vengono definite nel tipo con le [] e sono definiti e non modificabili nel numero di elementi contenuti, ma solo nel contenuto.

Gli array devono avere un numero ben definito di elementi contenuti.

- `string[] names = { "Alex" , "Marco" , "Luca" };`

- `string[] surname = new string[3];` definiamo un array che sarà massimo di 3 elementi da poter riempire successivamente

## Matrici - Array Multidimensionali

Possiamo definire Array matrici , costituiti da righe e colonne, formato da array di stessa lunghezza

specifichiamo con `[,]` che l'array sarà costituito da righe e colonne in modo generico

ma è possibile specificare eplicitamente come sarà formata la matrice `[righe , colonne]` inserendo un numero

```
    string[,] details = new string[3,2] = 
    {
        {"Alex","Marco"},
        {"Castelli","Rossi"},
        {"29","40"}
    }
```

per poter leggere questi valori dobbiamo puntare alla giusta posizione nella matrice `Console.WriteLine(details[0,0])` per il primo elemento posto in alto a sinistra della griglia, cioè "Alex"

- iterare matrice

è possibile iterare una matrice tramite un foreach, ma stamperebbe tutto il contenuto, tramite un for possiamo specificare l'indice

con `GetLength()` accediamo alla dimensione della matrice, dove 0 sta nella riga e 1 alla colonna

```

    for(int row: row < details.GetLenght(0) ; row++){
        for(int column ; column < details.GetLenght(1) ; colonna++ ){
            Console.WriteLine("valori: " + details[row,column])
        }
    }
    
```

- Matrice tridimensionale 3D

- `[n,n,n]` 
- - il primo n indica gli array contenuti nell'array padre D1
- - il secondo n indica gli array contenuti dentro un array figlio D2
- - il terzo n indica gli elementi contenuti nel singolo array del figlio D3

```
    string[,,] array3D = new string[2,2,2]{
        {
            {"010","011"},
            {"020","021"}
        },
        {
            {"030","031"},
            {"040","041"}
        }
    } ;

    for(int dim1 = 0; dim1 < array3D.GetLength(0); dim1++){
        for(int dim2 = 0; dim2 < array3D.GetLength(1); dim2++){
            for(int dim3 = 0; dim3 < array3D.GetLength(2); dim3++){
                Console.WriteLine("il valore è: " + array3D[dim1,dim2,dim3]);
            }
        }
    }

```

## Matrici Irregolari

Sono Matrici di array con dimensioni diverse

viene definito come un array di array con `[][]`

```
    int[][] arrayIrregolare = new int[4][] //dunque un array di 4 array che a sua volta possono contenere un numero indefinito di elementi


    for(int row = 0; row < arrayIrregolare.Length(0); row++){
        for(int colonna = 0; colonna < arrayIrregolare[row].Length; colonna++){
            Console.WriteLine("il valore è: " + arrayIrregolare[riga][colonna]);
        }
    }

```

## ArrayList

Sono come gli array ma senza un numero definito, e anche senza l'obbligo di avere un solo tipo di dato al suo interno.
Fanno parte della classe `System.Collection`

```

ArrayList myArr = new ArrayList();
myArr.Add(29);
myArr.Add("Alex");

ArrayList test = new ArrayList(){ //creazione e riempimento diretto
    3 , "prova" , true , null
}

```

ArrayList possiede diversi metodi per poter essere gestito

- .Add() => aggiunge un singolo elemento/obj alla fine (push)
- .AddRange() => aggiunge più elementi o altri array alla fine
- .Insert(index , element) => permette di inserire un elemento ad uno specifico indice
- .Remove(element) => rimuove in base all'elemento
- .RemoveAt(index) => rimuove in base all'indice
- .RemoveRange(start , N el) => rimuove in base alla posizione, e quanti elementi deve rimuovere
- .Contains(el) => ritorna un booleano se esiste l'elemento o meno
- .Count => ritorna il conteggio totale dell'arrayList

il foreach è leggermente diverso `foreach(object/var el in array){}` bisogna specificare una variabile o un object per il singolo elemento da iterare

nel ciclo for invece non useremo .Lenght ma `.Count`

# LIST

Le liste sono il 'contrario' degli ArrayList, sono anch'esse infinite nel numero di elementi, ma hanno obbligo dello stesso tipo.

Fanno parte della classe `System.Collection.Generic` 

i modelli Generici in C# stanno ad indicare modelli più definiti, quindi fanno riferimento ad un genere specifico

i modelli non generici vengono intesi come modelli più liberi

```
    List<int> myList = newList<int>(); //bisogna castare il tipo di dato che dovrà contenere la lista
```

i metodi disponibili sono gli stessi di ArrayList.

***

# Hashtable

Sono collection, sono contenitori con rapporti chiave-valore non vincolate da numero di elementi e tipo.
sono simili agli obj in JS.

`Le key devono essere univoche.`

```
    Hashtable cities = new Hashtable(); //inizilizzazione vuota
    Hashtable cities = new Hashtable(){ //assegnazione diretta
        {"lombardia" , "milano"},
        {"sicilia" , "palermo"},
        {"liguria" , "genova"},
    }
```

Sono disponibili anche dei metodi per manipolare le Hashtable:

- cities.Add({key,value}) => aggiunge elementi
- cities["sicilia"] => legge il valore della key specificata
- cities["lombardia"] = "mantova" => modifica il valore della key specificata
- cities.Remove("lombardia") => rimuove l'elemento con key corrispondente
- cities.ContainsKey("sicilia") => ritorna booleano in base alla condizione
- cities.ContainsValue("palermo") => ritorna booleano in base alla condizione
- cities.Clear() => svuota tutta la collection

```
    foreach(DictionaryEntry city in cities){
        Console.WriteLine(city.Key + city.Value)
    }
```

Il tipo del singolo elemento da iterare sarà `DictionaryEntry` , e possiamo accedere tramite dot notation al suo contenuto.

***

# Dictionary Dict

Sono collection simili alle Hashtable, la differenza è che hanno l'obbligo della definizione del tipo di key e value.

```
    Dictionary<string,string> cities = new Dictionary<string , string>(); // inizializzazione vuota
    Dictionary<string,string> cities = new Dictionary<string , string>(){ // assegnazione diretta
        {"lombardia" , "milano"},
        {"sicilia" , "palermo"},
        {"liguria" , "genova"},
    }
```

Funzionano esattamente come le Hashtable, soltanto che qui bisogna specificare il tipo del dato che conterrà.

```
    foreach(KeyValuePair<string,string> ciity in cities){
        log.(city)
    }
```

`KeyValuePair<T,T>` è un tipo ancora più specifico per definire il tipo della variabile da iterare, si sarebbe potuto usare anche un `var`

# Stack

Un altro tipo di collection generico. `Last in first out LIFO => L'ultimo elemento ad entrare è il primo ad uscire`

ideologia dello stack vero e proprio, un container di elementi ordinati dove l'ultimo elemento che inserisco oggettivamente sarà sempre il primo ad uscire per ordinamento.

```
    Stack<int> inventory = new Stack<int>();

    inventory.Push(10);
    inventory.Push(20);
    inventory.Push(30);
    inventory.Push(40);
```

Sono disponibili dei metodi:

- .Push() => inserisce un elemento all'ultimo posto
- .Peak() => 'sbircia' l'ultimo elemento
- .Pop() => rimuove l'ultimo elemento 
- .Clear() => rimuove tutti gli elementi
- .Count => ritorna il numero di elementi

l'iterazione viene fatta in modo normale, l'ordinamento sarà dall'ultimo al primo, l'esempio è come se fosse un `mazzo di carte`.

# Queue

(CHIU' | CODA)

Altra collection generica come gli stack ma con un ragionamento al contrario `First in first out FIFO => la prima dentro è la prima fuori`

```
    Queue<string> = people = new Queue<string>();

    people.Enqueue("Alex"); // primo in coda
    people.Enqueue("Luca"); // in coda
    people.Enqueue("Marco");
```

Sono disponibili dei metodi:

- .Enqueue(el) => inserisce elemento in coda
- .Dequeue() => elimina il primo elemento della coda
- .Peak() => è possibile leggere il primo elemento della coda
- .Clear() => rimuove tutti gli elementi
- .Count => ritorna il numero di elementi

***

# OOP - Object Oriented Programming

Signifa che qualsiasi cosa nel nostro codice è differenziato e suddiviso per Obj.

La `Classe` è quell'elemento che gestisce la struttura di un obj, delle sue proprietà e metodi, utilizzata per standardizzare gli obj. Lo scheletro in sè

l' `Oggetto` è quel dato che si rifà alla classe, sarà un `istanza` di una determinata classe.

```
    class Person{
        public string name ; 

        public void Jump(name){
            Console.WriteLine($"{this.name} has jumped!")
        }
    }

    Person alex = new Person() ;
    alex.name = "Alex" ;
    alex.Jump() ;
    Person mario = new Person() ;
```

Creando una classe possiamo definire proprietà e metodi, per poter definire una nuova istanza di quella classe su C# `il tipo della variabile sarà la classe stessa`.

tramite `this` accediamo alle proprietà e metodi appartenenti all'istanza della classe, a differenza di JS in C# è possibile accedere direttamente alle proprietà, ma bisogna utilizzare this. in caso di ambiguità tra variabili e proprietà.

Nell'esempio il metodo Jump accetta un parametro con lo stesso nome della proprietà, ma noi vogliamo utilizzare la proprietà della classe accedendo con .this


## Constructor
- Constructor(){} - public Class(){}

Il costruttore si occupa di popolare le nostre proprietà nel momento in cui si istanzia una Classe (quando si crea un nuovo obj con quella classe).

```
    class Person{
        public string name ; 
        public string surname ;
        public string age ;

        public Person(     //-> constructor(){} 
            string name ,
            string surname,
            int age
        ){
            name = this.name ;
            surname = this.surname ;
            age = this.age ;
        } 

        public void Jump(name){
            Console.WriteLine($"{this.name} has jumped!")
        }
    }

    Person alex = new Person("Alex" , "Cast" , 29) ;

```

il costruttore si comporta nella stessa maniera di JS, popola le nostre proprietà appartenenti alla classe, solo che viene dichiarato con il nome stesso della classe
prende come parametri quello che vogliamo, da specificare il tipo, e successivamente questi valori possono essere associati alle nostre proprietà accedendovi con .this

### Overloading constructor (sovraccarico di costruttori)

Come l'overloading dei metodi , è possibile anche nel constructor

```
       class Person{
            public string name ; 
            public string surname ;
            public string age ;

         public Person(string name , string surname,){
                name = this.name ;
                surname = this.surname ;
            } 

         public Person(string surname, int age){
                surname = this.surname ;
                age = this.age
            } 
        }

        Person alex = new Person("Alex" , "Cast") ;
        Person luca = new Person("Rossi" , 29) ;

```

Dunque è possibile definire più constructor con stesso nome, l'importante è che la `firma` sia diversa, cioè numero argomenti e/o tipo del dato. 

***

# Getter & Setter

Di default le proprietà, o metodi, dovrebbero essere `private` in una classe. Getter e setter come su TS ci aiutano per poter accedere alle proprietà di una classe.

- Tramite metodi:

```
    public void SetName(name){
        this.name = name ;
    }

    public string GetName(){
        return this.name ;
    }
```

- Tramite proprietà:
    Simile ad un metodo, ma utilizzato come una proprietà, simile a TS, dove possiamo definire all'interno tramite le kkey words get e set quello che vogliamo fare con la nostra proprietà.
    utilizziamo la arrow func, e la key word `value` di C# per poi settare il valore.

```
    public string Name
    {

        get => this.name ;
        set => this.name = value ;
    }

     Persona alex = new Persona() ;
     alex.Name = "Alessandro" ; //settiamo la proprietà tramite un value
     Console.WriteLine(alex.Name) ; //otteniamo il valore

```

In questa maniera accediamo e gestiamo il valore come se fosse una proprietà.

- prop:

autogenerazione -> prop + TAB

```
    public string Nome { get; set; }
```

Questa è una sintassi più ristretta, ma il funzionamento è identico a quello descritto come proprietà.

***

# KeyWord STATIC

Indichiamo con `static` una proprietà o metodo che appartiene alla classe stessa, non accessibile direttamente al singolo oggetto.

Utilizziamo elementi statici quando vogliamo implementare metodi o proprietà accessibili anche senza un istanza della classe

```
    class Person{
        public string name ; 
        public string surname ;
        public string age ;
        static public int numberPersons = 10 ;

        public Persona(string name , string surname,){
            name = this.name ;
            surname = this.surname ;
            Person.numberPerson ++ ; //ogni volta che il costruttore viene richiamato la variabile viene aumentata
            Console.WriteLine(Person.numberPersons) 
        } 

    }

    Person alex = new Person("Alex" , "Cast") ; //11
    Person luca = new Person("Rossi" , 29) ; //12
```

In questo esempio la variabile statica, facendo riferimento alla classe, aumenterà per tutte le volte che una classe viene richiamata, non riparte da 0 perchè è una variabile che non viene rinizializzata per ogni singolo obj

Una classe statica non può essere istanziata.

```
    Console.WriteLine(Math.Max(2,99)) ; 
```

Un esempio la classe Math è una classe statica, e noi possiamo utilizzare appunto i suoi metodi interni senza doverla istanziare, e questo è un esempio di come e del perchè una classe viene definita statica.

- Rendiamo un metodo di una classe statico nel caso in cui vogliamo poter accedere a quel metodo senza dover necessariamente istanziare la sua classe.

# Estendere classi (extends)

`Progetto -> add class`

E' il concetto di ereditare proprietà da un altra classe, quindi estendere una classe ad un altra, ma è differente da JS.

```
    class Student : Person
    {
        public sring class ;

        public Student(string name , string surname, int age, string class) : base(name, surname, age)
        {
            this.class = class ;
        }
    }
```

Quindi con `public Classe : ClasseEstesa` possiamo estendere una classe ad un altra, mentre nel costruttore possiamo importare le proprietà della classe estesa tramite `base()`. (super in JS)

I metodi vengono ereditati direttamente senza essere specificati. Per importarli dentro la classe possiamo accedervi tramite `base.Metodo()`

# VIRTUAL , OVERRIDE , SEALED

-  (Particolari di C#)

Possiamom utilizzare `override` su metodi ereditati da altre classi che sono `virtual` per poter sovrasciverli e renderli personalizzati per classi.

`sealed` viene inserito nei metodi per evitare che possano essere sovrascritti quando la classe viene ereditata

```
    public sealed override void Metodo(){}
```

questa è un metodo che sovrascrive un altro, ma da questo in poi non potrà più essere sovrascritto.

# INTERFACCE

Come in TS permettono di far sottoscrivere un 'contratto' per definire una classe o obj. Utilizziamo le interfacce per poter utilizzare dei metodi da implementare nelle nostre classi.

C# Mette a dispososizione diverse interfacce con dei metodi specifici che ci danno accesso a diversi metodi per poter manipolarle, ad esempio IEquatable<class> permette di poter paragonare due classsi e di ritornare un valore booleano.

E' possibile implementare più interfacce separate da una virgola, ma estendere solamente una Classe.

```
    class Student : Person , IEquatable<Student>
    {
        public string name ;
        public string surname ;

        public Student(string nome , string surname){
            this.name = name ;
            this.surname = surname ;
        }

        public bool Equals(Student student)
        {
            return this.name == student.name ;
        }
    }

    //nel main
    Student student1 = new Student(ecc, ecc) ;
    Student student2 = new Student(ecc ,ecc) ;

    Console.WriteLine(student1.Equals(student2)) ; //ritorna il risultato della condizione

```

# POLIMORFISMO

Uno dei fondamenti della programmazione ad obj, cioè la capacità degli obj di avere più forme

```
    class Person
    {
        public string name ;
        public string surname ;

        public Student(string nome , string surname){
            this.name = name ;
            this.surname = surname ;

            public virtual void Hello(){
                Console.WriteLine($"ciao sono {name} {surname}")
            }
        }
    }

    class Teacher : Person
    {
        public string discipline ;

        public Teacher(string name , string surname, string discipline) : base(name , surname)
        {
            this.discipline = discipline ;
        }

        public new void Hello(){
            Console.WriteLine($"Buongiorno sono il prof. {name} {surname}") //con new non sovrascriviamo il metodo, ma possiamo scegliere se usare o l'uno o l'altro in base a come lo richiamiamo
        }
    }

    class Student : Person
    {
        public string class ;

        public Studente(string name , string surname, string class) : base(name , surname)
        {
            this.class = class ;
        }

        public override void Hello(){
            Console.WriteLine($"Buongiorno sono lo studente {name} {surname}")
        }
    }

    //nel main

    var persons = new List<Person>
    {
        new Student("Alex" , "Castel" , "1A"),
        new Teacher("Marco" , "Neri" , "Matematica")
    }

    foreach(Person person in persons)
    {
        person.Hello();
    }

    Person teacher1 = new Teacher(ecc,ecc) ;
    Teacher teacher2 = new Teacher(ecc , ecc) ;

    teacher1.Hello() ; //Prenderà il metodo proveniente dalla classe Person
    teacher2.Hello() ; //Prenderà il metodo proveniente dalla classe Teacher

```

Dunque con polimorfismo si intende la possibilità di poter dare più forme alle classi in comune senza dei vincoli stretti, quindi diversi metodi, o liste con elementi interni diversi.

# CLASSI ASTRATTE

Sono delle classi che non possono essere utilizzate per istanziare obj. Vengono utilizzare per definire un 'concetto', dunque vengono utilizzare per definire altre classi, ma non per istanziare ogetti direttamente,
può essere solo `ereditata`

Generalmente nelle classi astratte vengono definite delle proprietà e dei metodi che devono essere obbligatoriamente implementati nelle classi che ereditano ma che devono essere sovrascritti

```

    abstract class Person

    abstract int Age { get; set; } ;

    {
        public abstract void Hello() ;
    }

```

A differenza delle interfacce le classi astratte dunque permettono di rendere obbligatorie certe proprietà o metodi che però devono essere sovrascritti e possono essere resi personalizzati.

La classe astratta comunque viene generalmente utilizzata come base per estendere altre classi. esempio con Person e poi Teacher e Student.

# MODIFICATORI DI ACCESSO

Sono parole chiave che vanno a modificare l'accesso a proprietà e metodi di una classe.

sono public , protected , private , internal .

public = e' possibile utilizzare ovunque il nostro metodo. Ovviamente accedendo tramite la classe di appartenenza

private = il metodo è accessibile solamente all'interno propria classe di appartenenza, anche se la classe padre è estesa ad un altra.

protected = premette di accedere al metodo all'interno della classe ma anche alle classe figlie che ereditano

internal = è accessibile ovunque ma solo all'interno dello stesso assembly (unità di compilazione, inteso come ambiente di esecuzione del codice, file .exe o .dll)

# ENUMERATOR - ENUM

Sono delle costanti di sola lettura, si comportano alla stessa maniera di TS, hanno un valore numerico innato crescente, a meno che non venga associato il valore iniziale '1' ad un elemento che non sia il primo della lista

```

    enum Giorni
    {
        Lunendi,
        Martedi,
        Mercoledi,
        Giovedi,
        Venerdi,
        Sabato,
        Domenica
    }

    Giorni giornoDellaSettimana = "Lunedi" ;

    Console.WriteLine((int)giornoDellaSettimana == 1) ;

```

# DATETIME

```

    DateTime data = new DateTime() ; //ritorna la prima data iniziale
    data.Today // prende la data di oggi
    data.Now // Ora e giorno attuale
    data.Minute // prende i minuti

    DateTime dataUTC = new DateTime.UtcNow ; //si basa sul meridiano inglese (internazionale)

    .AddDays(number) // aggiunge giorni, esiste per ore minuti e millisec
    data.Subtract(dataProva) // sottrae la data impostata

    data.ToString("D") // formatta la data in stringa, ci sono diversi stili di formattazione

    data.ToString("dddd , dd , MMMM") // formatta giornoSett , num , mese 


```

# NULLABLE - VALORI OPZIONALI

E' possibile dare un valore `null` ad una variabile , e dichiarare il tipo con `?` per indicare che quella variabile potrà contenere anche un valore nullo, valori opzionali.

```

    int? prova = null;

```
