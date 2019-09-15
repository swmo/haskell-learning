
# Cheatsheet 

## Generell
- Negative Nummern immer in Klammern angeben (GHCI wird sonst einen Fehler melden)
> 2 * (-4)

- https://hoogle.haskell.org/
- https://hackage.haskell.org/package/CheatSheet-1.11/src/CheatSheet.pdf

### Operators
Operaters are functions in Haskell! 

**and**:
bool && bool
> true && true 

Resulat: true

**equal: same type == same type**
> 1 == 1 

Resultat: true
 
**or**:

> False || True

Resultat: true

**not equal**:
> not (1 == 1)


**+**:
number + number

Resultat: False

> 1 /= 1

Resultat False


## Functions
- Bei den Aufrufen von Funktionen werden Leerzeichen statt wie meist in ander Programmiersprachen üblich Klammern verwendet
- Functions können nicht mit einem Grossbuchstaben beginnen.
- ' Astrophe kann im Funktionsname verwendet werden. Normlarweise wird dies genutzt bei der es um eine leicht modifzierte Version oder eine stricte Version (nicht lazy) der Funktion geht.

beispiel PHP
> testFunktion(44,22)

Beispiel Haskell:
> testFunktion 44 22

Die Klammern werden benötigt wenn man eine Funktion in einer Funktion ausführt:
Beispiel:
> testFunktion (43 + 1) (21 + 1)

> funktion01 (funktion02 argument01fuerFunktion02)

Die Reihenfolge wie die Funktionen definiert sind spielt keine Rolle.

- infix function. Jede Funktion mit zwei Argumenten lässst sich als infix Function aufrufen. dies kann mit dem  \`  gemacht werden: Beispiel: 1 \`drop\` [1,4,5]. Z. B. + ist eine infix Function (1 + 1). Infix kann bei der lesbarkeit helfen

> 4 `elem` [3,4,5,6] 

### Basic functions:
**succ**
succ type_with_an_successor
nimmt alles was einen definierten successor hat, Z. B. wenn man eine Nummer übergibt rechnet er +1
> succ 10

Resultat 11

**min / max**
Nimmt zwei Argumente welche in eine Reihenfolge gelegt werden können (Z. B. Nummern)
min gibt den kleineren Wert zurück
max gibt den grösseren Wert zurück. Bei Strings wird das erste Zeichen verglichen, falls diese gleiche sind wird der zweite Wert verglichen -> wie bei den Listen, da ein String auch eine List ist..

> min 11 199

Resultat 11

> max 11 199

Resultat 199

>min "bert" "cber"
Resultat "bert"

### Expressions
Expression ein ein code welcher ein Wert zurückgibt. Das Resultat ist immer eine Expression.
Versteh ich noch nicht ganz..

### Definition 
eine Funktion welche keine Parameter / Argumente hat nennt man definition oder name -> ist aber troztdem eine "Funktion"
> thisIsADefinition = "ich bin eine definiton"

### If
Jede Expression und Funktion muss in Haskell etwas returnen. Daher muss für jedes if ein else definiert werden!

> doubleSmallNumber x = if x < 100 then x * 2 else x

### lists
- sind homogenous data struktur bedeutet es können nur Elemente vom gleichen Typ gespeichert werden.
- strings sind in haskell auch lists "hello" ist dann ['h','e','l','l','o']

**++ zwei Listen zusammenführen**
- Mit dem ++ Operator können zwei Listen zusammengeführt werden
> ['1','2'] ++ ['3','4']
> ['1','2','3'] ++ ['4'] beide Werte müssen eine List sein!

 - Achtung: Haskell muss mit dem ++ Operator die ganze linke Liste durchgehen -> ein Problem wenn die Liste extrem gross ist.
 - Eine Lösung dazu ist mit : (auch cons operator genannt) fügt ein Wert zu Beginn einer Liste hinzu

**: in Element der Liste hinzugefügen**
> 'D' : "as Haus ist schön"  
>  1 : [2,3,4]

Im Prinzip ist [1,2,3] das gleiche wie 1:2:3:[]

**!! ein Element aus einer Liste entnehmen**
- mit dem !! kan ein Elment über den Index ausgelesen werden. Der index startet mit 0
>[1 .. 1000] !! 444

Resultat 445

**<,<=,>,>= Vergleichen**
- Eine Liste kann verglichen werden, wenn der Inhalt vergleichbar ist
- es wird der Kopf / Head verglichen, respektive zuerst dass erste Element, sind beide gleich, dann das zweite
- Bei strings wird die Liste alphabetisch verglichen, bei Zahlen nummerisch

>Prelude> ["b"] > ["a"]

>True

>Prelude> ["b"] > ["c"]

>False

>Prelude> ["bb"] > ["ba"]

> True

>Prelude> ["ba"] > ["bb"]

>False


**head** 
- nimmt eine Liste und gibt das erste Element zurück

> head [1,2,3,4,5]

Wert: 1

**tail**
- nimmt eine Liste und gibt alle Elemente bis auf das erste Element die Liste zurück

> tail [1,2,3,4,5]

Wert: [2,3,4,5]

**last** 
- nimmt eine Liste und gibt das letzte Element zurück

> last [1,2,3,4,5]

Wert: 5

**init** 
- nimmt eine Liste und gibt alle Elemente bis auf das letzte zurück

> init [1,2,3,4,5]

Wert: [1,2,3,4]

Achtung!: Die Funktionen head, tail, last, init unterstützen keine empty list! Zudem erkennt der compiler das nicht ob es möglich ist -> dies muss der Programmierer im Griff haben.


**length** 
Nimmt eine Liste und gibt die Länge zurück

> length [1,2,3]

Resultat: 3


**null** 
Prüft ob die Liste leer ist (true) oder elmente besitz (false)

> null []

Resultat: true

**reverse** 
Kehrt die Reichenfolge der Elemente

> reverse [1,2,3]

[3,2,1]

> reverse [[1],[1,2],[1,2,3]]

[[1,2,3],[1,2],[1]]


**take**
nimmt eine Nummer und eine Liste. extrahiert die Anzahl Elemente vom Anfang der Liste

> take 3 [1,2,3,4,5,6,7,8]

[1,2,3]

**drop**
nimmt eine Nummer und eine Liste. Löscht die Anzahl Element vom Anfang der Liste

> drop 3 [1,2,3,4,5,6,7,8]

[4,5,6,7,8]

**maximum**
**minimum**
Nimmt eine Liste und gibt das kleinste / grösste Element zurück.

> minimum [8,4,2,1,5,6]

Resultat: 1

> maximum [8,4,2,1,5,6]

Resultat 8

**sum**
Nimmt eine Liste und gibt die Summe zurück

> sum [1,4,5]

Resultat: 10

**product**
Nimmt eine Liste und gibt das produkt zurück (mutlipliziert jedes Element)

> product [1,4,5]

Resultat 20


**elem** 
Prüft ob ein Element in der Liste existiert.
Wird oft als infix aufgerufen (einfacher lesbar)

> 4 `elem` [3,4,5,6]  

Resultat: true

#### Texas ranges (..)
Es ist möglich in Haskell Liste mit bestimmten Schritten zu generieren

> [1..10] 

Resultat: [1,2,3,4,5,6,7,8,9,10]

> ['a'..'z']  

Resultat: "abcdefghijklmnopqrstuvwxyz"

Auch in Schritte ist möglich:
> [1,3..11] 
Resultat: [1,3,5,7,9,11]

Resultat: "abcdefghijklmnopqrstuvwxyz" 

Achtung Floating Nummer besser nicht verwenden:
> [0.1, 0.3 .. 1]  
[0.1,0.3,0.5,0.7,0.8999999999999999,1.0999999999999999] 

zum Herunterzählen braucht Haskell die Angabe des schrittes 

> [20,19..1]

Resultat: [20,19,18,17,16,15,14,13,12,11,10,9,8,7,6,5,4,3,2,1]

> [20..1] Funktioniert nicht!

## GHCI
Statt Prelude einen anderen Namen bei GHCI anzeigen:
> :set prompt "ghci> "

test.hs File einlesen 
> :l test 

Funktionen können mit let on the fly in der prompt gesetzt werden.
Beispiel:
> let doubleSmallNumber x = if x < 100 then x * 2 else x

Ist das gleiche wie im hs file:
> doubleSmallNumber ....



## Quellen
- http://learnyouahaskell.com: gute Einführung in Haskell.


