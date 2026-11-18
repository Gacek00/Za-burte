# Dziennik testów

Obserwacje z moich notatek po sesjach testowych, uporządkowane według wersji. Każdy wiersz to jedna zapisana obserwacja, a nie osobna rozmowa.

| # | Wersja | Typ | Obserwacja | Wniosek / poprawka |
|---|---|---|---|---|
| 1 | v1 | Pomysł | Jedyną drogą do uspokojenia kapitana były dodatkowe wachty. | Dodana druga droga: kapitan żąda donosu na kamrata. Zgoda go uspokaja, ale obniża uczciwość (v2). |
| 2 | v1 | Błąd | Kapitan mógł wyrzucić za burtę już po pierwszej odpowiedzi gracza. | Wyrok najwcześniej po 2. wypowiedzi, najpierw ostrzeżenie (v2). |
| 3 | v1 | Błąd | Kapitan groził „jeszcze jedno słowo i lecisz za burtę”, po czym wyrzucał bez szansy na odpowiedź. | Ostrzeżenie naprawdę czeka na odpowiedź, a wyrok jest wygłaszany bez pytań (v2). |
| 4 | v1 | Błąd | Kapitan zadawał kolejne pytania, a gra mówiła, że gracz wyleciał za burtę. | Rozdzielenie decyzji (kod) od wypowiedzi (model) (v2). |
| 5 | v1 | Tempo | Idealnie poprowadzona rozmowa ciągnęła się za długo. | Szybsze ustępowanie przy szczerości i ustępstwach. |
| 6 | v1 | Emocje | Brakowało emocjonalnego wydźwięku, np. gdy gracz pyta, dlaczego Ahab ściga wieloryba. | Dodana rana (utrata nogi), ujawniana przy szczerej trosce (v2). |
| 7 | v1 | Konflikt | Zaśnięcie na wachcie to słaby konflikt emocjonalny. | Nowy konflikt: bunt i lojalność, dwie fazy, cztery zakończenia (v2). |
| 8 | v2 | Błąd | Gdy skłamałem, że nie wypowiedziałem tych słów, wyrzucono mnie za burtę. Trener doradził klarowne zaprzeczanie, ale w kolejnej sesji Ahab i tak mnie wyrzucił. | Trener dostaje premisę (słowa padły naprawdę) i dziennik sędziego, i ma nie doradzać tego, co nie zadziałało (v3). |
| 9 | v2 | Błąd | Wydanie kamrata (Flaska) zwiększało gniew Ahaba. | W regułach sędziego brakowało zasady. Teraz donos obniża złość i uczciwość, a Ahab okazuje wzgardę (v3). |
| 10 | v2 | Potwierdzenie | Mówienie prawdy i przyznanie się do winy uspokajają Ahaba. | Hipoteza projektowa potwierdzona. |
| 11 | v2 | UX | Niezrozumiała druga część dialogu, brak jasnego celu. | Cel widoczny w interfejsie (v3). |
| 12 | v2 | Błąd | Ahab zapowiadał koniec rozmowy, po czym ciągnął ją jeszcze przez kilka linijek. | Zakaz zapowiadania końca, koniec ustala kod (v3). |
| 13 | v2 | UX | Osoby nieznające „Moby Dicka” mogą nie rozumieć sytuacji. | Przycisk „Wyjaśnij kontekst” (v3). |
| 14 | v3 | Powtarzalność | Ahab powtarzał podobne pytania („czy staniesz za mną”, „czy będziesz wołać moje imię, czy swojej matki”), a droga najmniejszego oporu wymagała 6 wypowiedzi. | 5 wypowiedzi, szybsze spadki złości, zakaz powtarzania pytań (v4). |
| 15 | v3 | UX | Cel i wskazówki w fazie 2 były na górze strony i gracz ich nie zauważał. | Panel nastroju i celu przyklejony do góry, ramka sceny w dialogu (v4). |
| 16 | v3 | UX | Przyciski „Wskazówka”, „Wyjaśnij kontekst” i „Zagraj ponownie” były mało widoczne. | Ten sam jasny kolor co „Powiedz” (v4). |
| 17 | v3 | Projekt | Odgadywanie prawdy sprowadzało się do podążania za wskazówkami, a trzeciej prawdy nie dało się osiągnąć mimo wskazówki. | Jedna prawda, Ahab opowiada ją sam przy szczerej trosce, na końcu narrator (v4). |
| 18 | v4 | Błąd | Otwarcie Ahaba nie mówiło wprost, o co pyta. | Dodane „Mów, co masz na swoją obronę” (v5). |
| 19 | v4 | Błąd | Czcionka bez polskich znaków. | Zmiana na EB Garamond (v5). |
| 20 | v5 | Obserwacja | Rozmowa 1 (szczera droga): ocalony, Ahab sam opowiada prawdę przy sterze. | Zakończenie „Ocalony i wiesz”. Zapis w replayu. |
| 21 | v5 | Obserwacja | Rozmowa 2 (donos na Stubba i pochlebstwo): wyrzucony za burtę, Ahab okazał wzgardę donosicielowi. | Moralne rozwidlenie działa. Zapis w replayu. |
| 22 | v5 | Znane, niepoprawione | Po analizie transkryptów: Ahab ujawnia sedno już w pierwszej odpowiedzi przy sterze i często powtarza „dotykam kości”. | Zostawione do ewentualnej wersji v6. |
