# System aukcyjny

## Wprowadzenie

Specyfikacja wymagań funkcjonalnych w ramach informatyzacji procesu sprzedaży produktów w oparciu o mechanizm aukcyjny. 

## Procesy biznesowe

---
<a id="bc1"></a>
### BC1: Sprzedaż aukcyjna 

**Aktorzy:** [Sprzedający](#ac1), [Kupujący](#ac2)

**Opis:** Proces biznesowy opisujący sprzedaż za pomocą mechanizmu aukcyjnego. |

**Scenariusz główny:**
1. [Sprzedający](#ac1) wystawia produkt na aukcję. ([UC1](#uc1))
2. [Kupujący](#ac2) oferuje kwotę za produkt wyższą od aktualnie najwyższej oferty. ([BR1](#br1)) ([UC2](#uc2))
3. [Kupujący](#ac2) wygrywa aukcję ([BR2](#br2)) ([UC3](#uc3))
4. [Kupujący](#ac2) przekazuje należność Sprzedającemu. ([UC4](#uc4))
5. [Sprzedający](#ac1) przekazuje produkt Kupującemu. ([UC5](#uc5))

**Scenariusze alternatywne:** 

2.A. Oferta Kupującego została przebita, a [Kupujący](#ac2) pragnie przebić aktualnie najwyższą ofertę. ([UC6](#uc6))
* 2.A.1. Przejdź do kroku 2.

3.A. Czas aukcji upłynął i [Kupujący](#ac2) przegrał aukcję. ([BR2](#br2)) ([UC3](#uc3))
* 3.A.1. Koniec przypadku użycia.

---

## Aktorzy

<a id="ac1"></a>
### AC1: Sprzedający

Osoba oferująca towar na aukcji.

<a id="ac2"></a>
### AC2: Kupujący

Osoba chcąca zakupić produkt na aukcji.


## Przypadki użycia poziomu użytkownika

### Aktorzy i ich cele

[Sprzedający](#ac1):
* [UC1](#uc1): Wystawienia produktu na aukcję
* [UC3](#uc3): Zamknięcie aukcji
* [UC5](#uc5): Dostawa

[Kupujący](#ac2)
* [UC2](#uc2): Oferta zakupu
* [UC3](#uc3): Zamknięcie aukcji
* [UC4](#uc4): Finalizacja zamówienia
* [UC6](#uc6): Przebicie oferty

---
<a id="uc1"></a>
### UC1: Wystawienia produktu na aukcję

**Aktorzy:** [Sprzedający](#ac1)

**Scenariusz główny:**
1. [Sprzedający](#ac1) zgłasza do systemu chęć wystawienia produktu na aukcję.
2. System prosi o podanie danych produktu i ceny wywoławczej.
3. [Sprzedający](#ac1) podaje dane produktu oraz cenę wywoławczą.
4. System weryfikuje poprawność danych.
5. System informuje o pomyślnym wystawieniu produktu na aukcję.

**Scenariusze alternatywne:** 

4.A. Podano niepoprawne lub niekompletne dane produktu.
* 4.A.1. System informuje o błędnie podanych danych.
* 4.A.2. Przejdź do kroku 2.

---

<a id="uc2"></a>
### UC2: Oferta zakupu

**Aktorzy:** [Kupujący](#ac2)

**Scenariusz główny:**
1. [Kupujący](#ac2) zgłasza do systemu chęć złożenia oferty zakupu produktu.
2. System prosi o podanie kwoty oferty.
3. [Kupujący](#ac2) podaje kwotę oferty.
4. System weryfikuje wprowadzoną kwotę.
5. System informuje o pomyślnym dodaniu oferty.

**Scenariusze alternatywne:** 

5.A. Podana kwota jest niepoprawna lub zbyt niska. ([BR1](#br1))
* 5.A.1. System informuje o błędnie podanych danych.
* 5.A.2. Przejdź do kroku 2.

---

<a id="uc3"></a>
### UC3: Zamknięcie aukcji

**Aktorzy:** [Sprzedający](#ac1), [Kupujący](#ac2)

**Scenariusz główny:**
1. System sprawdza kto został zwycięzcą aukcji. ([BR2](#br2))
2. System informuje [Sprzedający](#ac1)ego oraz [Kupujący](#ac2)ch o wyniku aukcji i dalszych krokach.

---

<a id="uc3"></a>
### UC4: Finalizacja zamówienia

**Aktorzy:** [Kupujący](#ac2)

**Scenariusz główny:**
1. System prosi [Kupujący](#ac2)ego o wybranie sposobu dostawy.
2. [Kupujący](#ac2) wybiera sposób dostawy.
3. System prosi [Kupujący](#ac2)ego o wprowadzenie adresu dostawy.
4. [Kupujący](#ac2) kupujący wprowadza adres dostawy.
5. System weryfikuje wprowadzone dane.
6. System informuje o poprawności wprowadzonych danych.
7. System prosi [Kupujący](#ac2)ego o wybranie metody płatności.
8. [Kupujący](#ac2) wybiera metodę płatności.
9. System przekierowuje [Kupujący](#ac2)ego do wybranej metody płatności.
10. System weryfikuje płatność.
11. System przekazuje płatność na konto sprzedawcy.
12. System informuje o poprawnym zakończeniu operacji.

**Scenariusze alternatywne:** 

1.A. ...
* 4.A.1. ...

---

<a id="uc3"></a>
### UC5: Dostawa

**Aktorzy:** [Kupujący](#ac2)

**Scenariusz główny:**
1. [Kupujący](#ac2) zgłasza do systemu chęć złożenia oferty zakupu produktu.
2. System prosi o podanie kwoty oferty.
3. [Kupujący](#ac2)

**Scenariusze alternatywne:** 

1.A. ...
* 4.A.1. ...

---

<a id="uc3"></a>
### UC6: Przebicie

**Aktorzy:** [Kupujący](#ac2)

**Scenariusz główny:**
1. [Kupujący](#ac2) zgłasza do systemu chęć złożenia oferty zakupu produktu.
2. System prosi o podanie kwoty oferty.
3. [Kupujący](#ac2)

**Scenariusze alternatywne:** 

1.A. ...
* 4.A.1. ...

---

## Obiewkty biznesowe (inaczje obiekty dziedzinowe lub informatycjne)

### BO1: Aukcja

Aukcja jest formą zawierania transakcji kupna-sprzedaży, w której Sprzedający określa cenę wywoławczą produktu, natomiast Kupujący mogą oferować własną ofertę zakupu każdorazowo proponując kwotę wyższą od aktualnie oferowanej kwoty. Aukcja kończy się po upływie określonego czasu. Jeśli złożona została co najmniej jedna oferta zakupy produkt nabywa ten Kupujący, który zaproponował najwyższą kwotę. 

### BO2: Produkt

Fizyczny lub cyfrowy obiekt, który ma zostać sprzedany w ramach aukcji.

## Reguły biznesowe

<a id="br1"></a>
### BR1: Złożenie oferty

Złożenie oferty wymaga zaproponowania kwoty wyższej niż aktualnie oferowana o minimum 1,00 PLN.


<a id="br2"></a>
### BR2: Rozstrzygnięcie aukcji

Aukcję wygrywa ten z [Kupujący](#ac2)ch, który w momencie jej zakończenia (upłynięcia czasu) złożył najwyższą ofertę.

## Macierz CRUDL


| Przypadek użycia                                  | Aukcja | Produkt | ... |
| ------------------------------------------------- | ------ | ------- | --- |
| UC1: Wystawienia produktu na aukcję               |    C   |    C    | ... |
| ???                                               |  ...   |  ...    | ... |


