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

