
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
same type == same type
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

beispiel PHP
> testFunktion(44,22)

Beispiel Haskell:
> testFunktion 44 22

Die Klammern werden benötigt wenn man eine Funktion in einer Funktion ausführt:
Beispiel:
> testFunktion (43 + 1) (21 + 1)

> funktion01 (funktion02 argument01fuerFunktion02)

Die Reihenfolge wie die Funktionen definiert sind spielt keine Rolle.

### Basic functions:
**succ**
succ type_with_an_successor
nimmt alles was einen definierten successor hat, Z. B. wenn man eine Nummer übergibt rechnet er +1
> succ 10

Resultat 11

**min / max**
Nimmt zwei Argumente welche in eine Reihenfolge gelegt werden können (Z. B. Nummern)
min gibt den kleineren Wert zurück
max gibt den grösseren Wert zurück
> min 11 199

Resultat 11

> max 11 199

Resultat 199


### Expressions
Expression ein ein code welcher ein Wert zurückgibt. Das Resultat ist immer eine Expression.
Versteh ich noch nicht ganz..


### Definition 
eine Funktion welche keine Parameter / Argumente hat nennt man definition oder name
> thisIsADefinition = "ich bin eine definiton"

### If
Jede Expression und Funktion muss in Haskell etwas returnen. Daher muss für jedes if ein else definiert werden!



## GHCI
Statt Prelude einen anderen Namen bei GHCI anzeigen:
> :set prompt "ghci> "

test.hs File einlesen 
> :l test 


## Quellen
- http://learnyouahaskell.com: gute Einführung in Haskell.


