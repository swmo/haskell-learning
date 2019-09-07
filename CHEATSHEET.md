
# Cheatsheet 

## Generell
- Negative Nummern immer in Klammern angeben (GHCI wird sonst einen Fehler melden)
> 2 * (-4)

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
Bei den Aufrufen von Funktionen werden Leerzeichen statt wie meist in ander Programmiersprachen üblich Klammern verwendet 
beispiel PHP
> testFunktion(44,22)

Beispiel Haskell:
> testFunktion 44 22

Die Klammern werden benötigt wenn man eine Funktion in einer Funktion ausführt:
Beispiel:
> testFunktion (43 + 1) (21 + 1)

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

## GHCI
Statt Prelude einen anderen Namen bei GHCI anzeigen:
> :set prompt "ghci> "

test.hs File einlesen 
> :l test 

