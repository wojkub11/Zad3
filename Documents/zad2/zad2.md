# Lekcja 1 - Markdown lekki język znaczników

## Spis treści

Lekcja 1 – Markdown lekki język znaczników....................................................................................1
Wstęp...............................................................................................................................................1
Podstawy składni.............................................................................................................................3
Definiowanie nagłówków...........................................................................................................3
Definiowanie list.........................................................................................................................4
Wyróżnianie tekstu......................................................................................................................4
Tabele..........................................................................................................................................5
Odnośniki do zasobów................................................................................................................5
Obrazki........................................................................................................................................5
Kod źródłowy dla różnych języków programowania.................................................................5
Tworzenie spisu treści na podstawie nagłówków.......................................................................6
Edytory dedykowane.......................................................................................................................7
Pandoc – system do konwersji dokumentów Markdown do innych formatów...............................8
Lekcja 2 – Git – system kontroli wersji................................................................................................9
Git - podstawowe cechy...................................................................................................................9
Idea pracy:........................................................................................................................................9
Git – tworzenie pustego archiwum lokalnego...............................................................................11
Zadania do wykonania na punkty.......................................................................................................21
Zadanie 1 – 2pkt............................................................................................................................21
Zadanie 2 – 4pkt............................................................................................................................21
Zadanie 3 - 4pkt.............................................................................................................................21

### Wstęp

Obecnie powszechnie wykorzystuje się języki ze znacznikami do opisania dodatkowych informacji
umieszczanych w plikach tekstowych. Z pośród najbardziej popularnych można wspomnieć o:

1. **html** – służącym do opisu struktury informacji zawartych na stronach internetowych,
2. **Tex** (Latex) – poznany na zajęciach język do „profesjonalnego” składania tekstów,
3. **XML** (Extensible Markup Language) - uniwersalnym języku znaczników przeznaczonym do
   reprezentowania różnych danych w ustrukturalizowany sposób.

Przykład kodu html i jego interpretacja w przeglądarce:

\<!DOCTYPE **html**>
\<**html**>
\<**head**>
\<**meta** <span style="color: darkblue;"> charset</span><span style="color: rgba(74, 232, 77, 1);">=</span><span style="color: red;">"utf-8"</span> />
\<<span style="color: darkblue;">title</span>>Przykład\<<span style="color:darkblue;"><span style="color: rgba(74, 232, 77, 1);">/</span>title</span>>                                                                                			
\</**head**>                                                                                                   	
\<**body**>
\<**p**> Jakiś paragraf tekstu\<<span style="color: rgba(74, 232, 77, 1);">/</span>**p**>                  	
\<<span style="color: rgba(77, 230, 77, 1);">/</span>**body**>
\<<span style="color: rgba(74, 230, 77, 1);">/</span>**html**>

![1](C:\Users\Wojci\Documents\zad2\zad2.assets\1.jpg)



Przykład kodu Latex i wygenerowanego pliku  w formacie pdf

\\<span style="color: darkred;">documentclass</span>[]{<span style="color: blue;">letter</span>}
\\<span style="color: darkred;">usepackage</span>{<span style="color: blue;">lipsum</span>}
\\<span style="color: darkred;">usepackage</span>{<span style="color: blue;">polyglossia</span>}
\\<span style="color: darkred;">setmainlanguage</span>{<span style="color: blue;">polish</span>}
\\<span style="color: blue;">**begin**</span>{<span style="color: blue;">**document**</span>}
\\<span style="color: blue;">**begin**</span>{<span style="color: blue;">**letter**</span>}{<span style="color: blue;">**Szanowny** **Panie** **XY**</span>}
\\<span style="color: darkred;">address</span>{<span style="color: blue;">Adres do korespondencji</span>}
\\<span style="color: darkred;">opening</span>{}
\\<span style="color: darkred;">lipsum</span>[2]
\\<span style="color: darkred;">signature</span>{<span style="color: blue;">Nadawca</span>}
\\<span style="color: darkred;">closing</span>{<span style="color: blue;">Pozdrawiam</span>}
\\<span style="color: blue;">**end**</span>{<span style="color: blue;">**letter**</span>}
\\<span style="color: blue;">**end**</span>{<span style="color: blue;">**document**</span>}

![2](C:\Users\Wojci\Documents\zad2\zad2.assets\2.jpg)





Przykład kodu XML - fragment dokumentu SVG (Scalar Vector Graphics)

\<!DOCTYPE **html**>
\<**html**>
\<**body**>
\<svg height=<span style="color: red;">"100"</span> width=<span style="color: red;">"100"</span>>																				
  \<circle cx=<span style="color: red;">"50"</span> cy=<span style="color: red;">"50"</span> r=<span style="color: red;">"40"</span> stroke=<span style="color: red;">"black"</span> stroke-width=<span style="color: red;">"3"</span> fill=<span style="color: red;">"red"</span> />
\</svg>
 \</**body**>
\</**html**>				

![3](C:\Users\Wojci\Documents\zad2\zad2.assets\3.jpg)

W tym przypadku mamy np. znacznik np. \<circle> opisujący parametry koła i który może być
właściwie zinterpretowany przez dedykowaną aplikację (np. przeglądarki www).

Jako ciekawostkę można podać fakt, że również pakiet MS Office wykorzystuje format XML do
przechowywania informacji o dodatkowych parametrach formatowania danych. Na przykład pliki z
rozszerzeniem docx, to nic innego jak spakowane algorytmem zip katalogi z plikami xml.

<span style="color: forestgreen;">$unzip</span> <span style="color: purple;">**-l** **test**</span>.docx
Archive: <span style="color: purple;">**test**</span>.docx
Length <span style="color: orchid;">**Date**</span> **Time** Name
\--------- ---------- ----- ----
573 2020-10-11 18:20 _rels/.rels
731 2020-10-11 18:20 docProps/core.xml
508 2020-10-11 18:20 docProps/app.xml
531 2020-10-11 18:20 word/_rels/document.xml.rels
1421 2020-10-11 18:20 word/document.xml
2429 2020-10-11 18:20 word/styles.xml
853 2020-10-11 18:20 word/fontTable.xml
241 2020-10-11 18:20 word/settings.xml
1374 2020-10-11 18:20 [Content_Types].xml



<div style="text-align:justify">Wszystkie te języki znaczników cechują się rozbudowaną i złożoną składnią i dlatego do ich edycji
wymagają najczęściej dedykowanych narzędzi w postaci specjalizowanych edytorów. By
    wyeliminować powyższą niedogodność powstał <b>Markdown</b> - uproszczony język znaczników
służący do formatowania dokumentów tekstowych (bez konieczności używania specjalizowanych
narzędzi). Dokumenty w tym formacie można bardzo łatwo konwertować do wielu innych
formatów: np. html, pdf, ps (postscript), epub, xml i wiele innych. Format ten jest powszechnie
używany do tworzenia plików README.md (w projektach open source) i powszechnie
obsługiwany przez serwery git’a. Język ten został stworzony w 2004 r. a jego twórcami byli John
Gruber i Aaron Swartz. W kolejnych latach podjęto prace w celu stworzenia standardu rozwiązania
i tak w 2016 r. opublikowano dokument <u>RFC 7764</u> który zawiera opis kilku odmian tegoż języka:</div>


* CommonMark,
* GitHub Flavored Markdown (GFM),
* Markdown Extra.





# Podstawy składni

Podany link: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet zawiera opis
podstawowych elementów składni w języku angielskim. Poniżej zostanie przedstawiony ich krótki
opis w języku polskim.



## Definiowanie nagłówków



W tym celu używamy znaku kratki

Lewe okno zawiera kod źródłowy – prawe -podgląd przetworzonego tekstu



![3_1](C:\Users\Wojci\Documents\zad2\zad2.assets\3_1.jpg)





## Definiowanie list



![4](C:\Users\Wojci\Documents\zad2\zad2.assets\4.jpg)

Listy numerowane definiujemy wstawiając numery kolejnych pozycji zakończone kropką.
Listy nienumerowane definiujemy znakami: *,+,-





## Wyróżnianie tekstu



![5](C:\Users\Wojci\Documents\zad2\zad2.assets\5.jpg)



## Tabele

![6](C:\Users\Wojci\Documents\zad2\zad2.assets\6.jpg)

Centrowanie zawartości kolumn realizowane jest poprzez odpowiednie użycie znaku dwukropka:





## Odnośniki do zasobów

\[odnośnik do zasobów](www.gazeta.pl)
\[odnośnik do pliku](LICENSE.md)
\[odnośnik do kolejnego zasobu][1]
\[1]: htp://google,com



## Obrazki

\!\[alt text](htps://server.com/images/icon48.png "Logo 1") – obrazek z zasobów
internetowych
\!\[](logo.png) – obraz z lokalnych zasobów



## Kod źródłowy dla różnych języków programowania

![7](C:\Users\Wojci\Documents\zad2\zad2.assets\7.jpg)





## Tworzenie spisu treści na podstawie nagłówków



![8](C:\Users\Wojci\Documents\zad2\zad2.assets\8.jpg)



# Edytory dedykowane

Pracę nad dokumentami w formacie Markdown( rozszerzenie md) można wykonywać w
dowolnym edytorze tekstowym. Aczkolwiek istnieje wiele dedykowanych narzędzi

1. Edytor Typora - https://typora.io/
2. Visual Studio Code z wtyczką „markdown preview”

![9](C:\Users\Wojci\Documents\zad2\zad2.assets\9.jpg)





## Pandoc – system do konwersji dokumentów Markdown do innych formatów



Jest oprogramowanie typu open source służące do konwertowania dokumentów
pomiędzy różnymi formatami.
Pod poniższym linkiem można obejrzeć przykłady użycia:
https://pandoc.org/demos.html

Oprogramowanie to można pobrać z spod adresu: https://pandoc.org/installing.html
Jeżeli chcemy konwertować do formatu latex i pdf trzeba doinstalować oprogramowanie
składu Latex (np. Na windows najlepiej sprawdzi się Miktex https://miktex.org/)
Gdyby podczas konwersji do formatu pdf pojawił się komunikat o niemożliwości
znalezienia programu pdflatex rozwiązaniem jest wskazanie w zmiennej środowiskowej
PATH miejsca jego położenia.

![10](C:\Users\Wojci\Documents\zad2\zad2.assets\10.jpg)

![11-1603973995359](C:\Users\Wojci\Documents\zad2\zad2.assets\11-1603973995359.jpg)

![12](C:\Users\Wojci\Documents\zad2\zad2.assets\12.jpg)





Pod adresem (https://gitlab.com/mniewins66/templatemn.git) znajduje się przykładowy plik
Markdown z którego można wygenerować prezentację w formacie pdf wykorzystując
klasę latexa beamer.
W tym celu należy wydać polecenie z poziomu terminala:
$pandoc templateMN.md -t beamer -o prezentacja.pdf