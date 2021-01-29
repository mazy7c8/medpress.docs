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

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/mazy7c8/medpress.docs/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
