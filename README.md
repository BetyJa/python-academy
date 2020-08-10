Minula [lekce#07](https://github.com/Bralor/python-academy/tree/lekce07)

<p align="center">
  <img src="https://engeto.cz/wp-content/uploads/2019/01/engeto-square.png" width="300" height="300">
</p>

# Python academy, lesson 08
## Dulezite odkazy
- Portal [Engeto.com](https://engeto.com/)
- Python Academy [repozitar](https://github.com/Bralor/python-academy)
- [Anotace](https://www.python.org/dev/peps/pep-3107/) v Pythonu
- Monkaroo (generator nahodnych udaju - testovaci data)

## Co nas dneska ceka?
Hlavnim cilem dnesni lekce bude prace s textovymi soubory pomoci Pythonu. Dale
si povime neco vic k formatovani retezcu. Tuto problematiku jsme jiz castecne
nacnuli, ale dneska zabrousime do detailu. V bodech:
1. Prace s .txt soubory
2. Kontextovy manazer
3. Formatovaci vyraz
4. Formatovaci metoda
5. f-strings

## Obesenec
Dalsim ukolem bude napsat v Pythonu hru v prikazovem radku. Hra se jmenuje
__obesenec__. Opet se budeme snazit aplikovat maximum z nove ziskanych
teoretickych znalosti.

## Ukazka na zacatek
Spustime skript v nasem adresari:
```
$ ./obesenec
```
Vystup muzeme vypadat nasledovne:
```
KOD
```

## Co budeme potrebovat?
- python 3.6.9+
- text. editor
- while smycky
- for smycky
- funkce v Pythonu

## Co nejdriv?

## Otevreme novy soubor
## Ridici funkce
## Novy hrac
## Otevirani txt souboru
## Schovani slova
## Stav hry
## Tah hrace
## Overeni tahu
## Dalsi a dalsi kolo
## Zaver hry
## Formatovani retezcu

Formatovani retezcu muzeme chapat jako operaci, ktera udela retezce vizualne prehlednejsi a umozni nam jednodussi manipulaci s nimi.

Teorie:
```
JMENO = "Zdenek"
VEK = 22
ADRESA = "Hrncirska 11, Brno"
VETA1 = "Jmenuji se " + JMENO + ". Je mi " + str(VEK) + " a momentalne jsem k dispozici na " + ADRESA
Jmenuji se Zdenek. Je mi 22 a momentalne jsem k dispozici na Hrncirska 11, Brno
```
## Jake mame zpusoby?
1. %-formatting, formatovaci vyraz
2. str.format(), formatovaci metoda
3. f-string, 

## Formatovaci vyraz
Jde o prapuvodni [formatovani](https://engeto.com/cs/kurz/online-python-akademie/studium/Xja-0nBPQvuISQQy8lJdYA/formatovani-stringu-a-textove-soubory/formatovani-stringu/vkladani-formatovaci-vyrazy) v Pythonu jiz od jeho zacatku.  

Priklad:
```
JMENO = "Lukas"
VEK = 26
"Ahoj, jmenuji se %s a je mi %d let" % (JMENO, VEK)
```
Dneska se jiz oficialne nedoporucuje pouzivat, jelikoz casto selhava, prip. nespravne zobrazuje tuple nebo slovniky. Soucasne je vypisovani az prilis podrobne.

## Formatovaci metoda
Od verze Pythonu 2.6 mame k dispozici dalsi zpusob pro [formatovani](https://engeto.com/cs/kurz/online-python-akademie/studium/hMIgHcH5TqaFSJJzKF9X7g/formatovani-stringu-a-textove-soubory/formatovani-stringu/formatovani-hodnot-metoda-format) retezcu.

Priklad:
```
JMENO = "Eliska"
VEK = 25
"Ahoj, jmenuji se {} a je mi {} let" .format(JMENO, VEK)
```
Pouziti je trochu mene explicitni. Nicmene zapis muze byt pri pouziti vice promennych porad dost narocny na vypisovani.

## F-string
Od verze Pythonu 3.6 mame dostupnou dalsi, jeste lepsi variantu pro rychle formatovani retezcu. 

Priklad:
```
JMENO = "Lucie"
VEK = 27
f"Ahoj, jmenuji se {JMENO} a je mi {VEK} let"
```
Syntaxe je velice strucna ale rozhodne ne na ukor citelnosti. Zvlada ruzne platne operace v Pythonu i volani funkci. Akorat u slovniku pamatovat, ze pokud pouziju napr. dvojite uvozovky u retezce, potom vnitrni musim psat jako jednoduche, abych ty puvodni predcasne neukoncoval.

## Prace se soubory pomoci Pythonu
### open()
Pro praci s konkretnim souborem uvnitr Python souboru jej musime nejprve nahrat do nejake promenne.

### Cist/zapisovat?
K ucelu, za kterym chceme soubor pouzivat musime vhodne specifikovat rezim/mod. Jakym soubor otevreme.
1. "w" - zapis
2. "r" - cteni
3. "a" - pripisuji informace bez smazani stavajiciho obsahu

### Pracujeme se souborem
1. .write() - zapisujeme
2. .read() - cteme

### close()
Jakmile dokoncime celou proceduru. Soubor zavirame! Soubor, ktery zapomeneme zavrit muze zpomalit nas program/programy. Neulozime nektere provedene zmeny, hypoteticky nebudeme moci otevrit dalsi soubory.

Priklad:
```
nacteny_soubor = open("slova.txt", "a+")  # nahraji soubor
nacteny_soubor.seek(0)  # nastavim kurzor na pozici 0
nacteny_soubor.read()  # prectu vse za nim
nacteny_soubor.write("jahoda")  # pridam dalsi radek
nacteny_soubor.close()  # ukoncim praci na souboru
```

## Kontextovy manazer
Varianta jak zoptimalizovat praci se soubory v Pythonu je pouzit kontextovy manazer. Tento proces totiz automaticky po otevreni a provedeni veskerych kroku soubor automaticky zavira.

Priklad:
```
with open("slova.txt", "r") as txt:
    obsah = txt.readlines()

>>> obsah  # vypise,co promenna obsahuje
```
