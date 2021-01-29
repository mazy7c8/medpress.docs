## Szybkie szablony dla medyków

Projekt służy do odbijania "kopiuj wklejek" lub innych monotonnych czynności tekstowych, które dotychczas były robione ręcznie tak, żeby nastąpiła ich półautomatyzacja. Program opiera się na strukturze szablonu co zostanie przestawione w kolejnych punktach. Program działa bez instalacji, możesz przenosić go na pendrive, wszystkie szablony zostaną wraz z tobą.

### Co to jest szablon?

Szablon to plik tekstowy. Domyślnie znajduje się w katalogu "szablony" MEDpressa ale może być w każdym innym miejscu na komputerze. Aby został prawidłowo odczytany musi posiadać kilka cech:


*   Pierwsza linijka pliku tekstowego musi rozpoczynać się trzema znakami hashtag: o tak "###"

*   Opcjonalnie w pierwszej linijce po znakach hasthag jest dodawane wyrażenie "author=" które przechowuje pamięć o autorze szablonu

*   Potem do końca lini jest zakodowany **kod szablonu** który zaczyna się znakiem "{" i kończy znakiem "}". O kodzie szablonu więcej poniżej.

*   Pomiędzy pierwszą linią tzw nagłówkiem a tekstem szablonu musi istnieć pusta linia. Linia nr 2 jest pusta!

*   Kolejne linie to **tekst szablonu**. W tekście szablonu występują **zmienne**. Zmienne są otoczone znakami "{{" z lewej strony i "}}" z prawej strony. Zmienne podczas wydruku są zamieniane na normalny tekst.

Tak wygląda przykładowy szablon otwarty w notatniku:
![Notatnik](https://i.imgur.com/YTdPVIU.png)

### Co to jest kod szablonu?

Jeżeli wydaje ci się to trudne, to wcale takie nie jest. Program sam generuje większość znaków i kodów potrzebnych do stworzenia kodu szablonu. Więcej o tym później

Kod szablonu to tak naprawdę popularny format danych tzw słownik. Kod szablonu umieszczony jest pomiędzy znakami "{" i "}". W środku znajdują się opisy zmiennych. Format jest następujący:

```python
 "nazwazmiennej": [
  "typzmiennej",
  "wartosc1",
  "wartosc2",
  "wartosc3"
 ],
```

Trzeba pamiętać że nazwa zmiennej to zazwyczaj wyrazy pisane bez znaków specjalnych i cyfr. Każda definicja zmiennej jest oddzielona od drugiej przecinkiem, mogą one występować w dowolnej kolejności w kodzie szablonu jednak nie mogą one się powtarzać. Każda ze zmiennych przyjmuje jeden typ który określa jej rodzaj "typzmiennej" oraz opcjonalne wartości.

### Jakie typy zmiennych obsługuje MEDpress?

MEDpress ma zaimplementowane nastaępujące typy:

*   **TX** = zmienna tekstowa, zamiast zmiennej pojawi się pole tekstowe w ktore mozesz wpisac dowolny inny tekst
*   **RC** = zamiast zmiennej zostanie wyświetlona widoczna lista z okrągłymi przyciskami, gdzie możesz wybrać tylko jedną z opcji
*   **CB** = zamiast zmiennej zostanie wyświetlona lista z kwadratowymi okienkami, możesz wybrać wiele opcji na raz
*   **SB** = zamiast zmiennej zostanie wyświetlona rozwijana lista, z której możesz wybrać tylko jedną opcję
*   **IF** = zmienna logiczna, służy do przechowywania innej zmiennej, która musi zostać osobno zdefiniowana w kodzie szablonu. Jej cechą jest opcja tak, która uaktywnia zmienną bądź opcja nie która zaniecha tworzenia zmiennej
*   **TN** = potocznie zmienna Tak/Nie, za wartości przyjmuje pytanie oraz tekst który wyświetli po kliknięciu na tak lub nie
*   **DT** = zamiast zmiennej pojawi się okienko kalendarza, w którym możesz wybrać datę
*   **NB** = zamiast zmiennej pojawi się suwak na którym możesz wybrać liczbę.

Aby poprawnie definiować kod szablonu przyjżyj się przykładowym zmiennym z kodu poniżej:

```python
'tekstowa':['TX']
'radio choice':['RC','pierwsza opcja','druga opcja','trzecia opcja']
'combo box':['CB','pierwsza opcja','druga opcja','trzecia opcja']
'select box':['SB','pierwsza opcja','druga opcja','trzecia opcja']
'jezeli':['IF','pytanie pomocnicze','nazwa innej zmiennej'] 
'taknie':['TN','pytanie pomocnicze','jezeli tak','jezeli nie']
'data':['DT']
'number':['NB','zakres dol','zakres gora']
```

**Kolejność wartości w definicji zmiennej w kodzie szablonu determinuje sposób interpretacji danych przez program tak więc konieczne jest zachowanie staranności**

Zmienne **RC CB SB** mogą mieć nieskończenie dużo opcji. Zmienne **TX i DT** mogą funkcjonować bez otoczenia ich nawiasem []. W pozostałych przypadkach te nawiasy są konieczne, a każde wartości muszą być oddzielone przecinkami i pozostać w pojedynczym cudzyslowiu.


### Jak stworzyć szablon?

1.  Kliknij na duży żółty przycisk w lewej górnej krawędzi "Stwórz szablon""

1.  Wpisz kolejno tytuł szablonu i wklej tekst który chcesz żeby stał się szablonem

![tekst](https://i.imgur.com/jT0NzCp.png)

1.  Następnie zapisz przyciskiem po prawej stronie lub klawiszami ctrl+s

1.  Stwórz zmienne w polu po lewej stronie dodając enkapsulacje {{ }} i kliknij generuj zmienne na dole

![generuj](https://i.imgur.com/9we1t8x.png)

1.  W kodzie szablonu pojawiły się domyślne zmienne tekstowe, możesz zapisać teraz szablon aby nie stracić danych przez pomyłkę
1.  Teraz zmień kod szablonu np na taki:

![kod](https://i.imgur.com/UeWHTpI.png)

1.  Zapisz szablon guzikiem po prawej stronie
1.  Wyjdź z okna klikając "close" i gotowe.

### Jak wydrukować szablon?

1.  Wybierz szablon z listy i kliknij na niego dwa razy

![wybierz](https://i.imgur.com/6sfmTKs.png)

1.  Pojawi się on w okienku wejściowo wejściowy jako czteroliterowy skrót, skróty możesz wpisywać ręcznie lub wybierać szablony dwuklikiem, wtedy skrót tam się znajdzie. 
1.  Jak masz wpisany skrót klikasz "Rozpocznij wypis"

![rozpocznij](https://i.imgur.com/EzeHbS2.png)

1.  Teraz wyświetlił Ci się obszar roboczy, tutaj wypełnij zmienne myszką lub klawiaturą (przy użyciu klawiszy Tab i Spacja)

![roboczy](https://i.imgur.com/RYFigYE.png)

1.  Możesz kliknąć Zakończ lub szybciej ctrl+z

1.  Wydrukowany szablon pojawił się w górnym oknie. Teraz możesz go skopiować do schowka przyciskiem lub skrótem ctrl+c albo stworzyć dokument worda w katalogu MEDpress który będzie zawierał twój wydruk

![wynik](https://i.imgur.com/198ZQjK.png)

Wybieraj kolejne szablony i drukuj dalej.

**Jeżeli coś ci się nie podoba nie musisz startować szablonu od początku, zmień myszką to co jest nie tak i kliknij zakończ lub ctrl+z, okienko uaktualni się o zmiany które wprowadziłeś**


