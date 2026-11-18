# Za burtę? Symulator trudnej rozmowy z kapitanem Ahabem

Interaktywna symulacja rozmowy z postacią AI, w której uczysz się uspokajać wściekłego przełożonego. Po rozmowie AI-trener ocenia Twoją postawę. Projekt zaprojektowałem jako ćwiczenie z pisania scenariuszy, projektowania zachowania postaci AI i testowania jakości odpowiedzi.

**Demo:** https://gacek00.github.io/Za-burte/

**Autor:** Ignacy Ziarkiewicz · https://www.linkedin.com/in/ignacy-ziarkiewicz-13aa79215/

---

## Scenariusz

Jesteś majtkiem na statku „Pequod” (1851, motyw z „Moby Dicka”, utwór w domenie publicznej). Głośno nazwałeś pogoń za białym wielorybem szaleństwem. Kapitan Ahab traktuje to jak bunt i chce wyrzucić Cię za burtę.

- **Cel 1:** przekonaj Ahaba w 5 wypowiedziach, że jesteś mu lojalny, i przeżyj.
- **Cel 2 (jeśli ochłonie):** dowiedz się, dlaczego tak szaleńczo goni za wielorybem. Ahab opowie sam, jeśli okażesz mu szczerą troskę.

Są cztery zakończenia: za burtę, ocalony kłamstwem, ocalony bez prawdy, ocalony i znasz prawdę.

## Jak to działa

Za każdą Twoją wypowiedzią stoją dwa wywołania modelu:

1. **Sędzia** ocenia tylko ostatnią wypowiedź: o ile zmienia się złość Ahaba, o ile uczciwość gracza, czy gracz wydał kamrata, czy okazał szczerą troskę.
2. **Kod** (nie model) ustala stan gry: ostrzeżenie, werdykt, darowanie życia, początek fazy 2.
3. **Aktor** gra Ahaba według polecenia ustalonego przez kod (np. „wydaj wyrok, bez pytań”).

Gra mierzy dwie rzeczy równolegle:

| Miara | Co oznacza | Widoczna dla gracza? |
|---|---|---|
| Złość Ahaba (0-10) | czy przeżyjesz | tak (pasek nastroju) |
| Uczciwość (0-10) | czy zachowałeś się uczciwie | dopiero w ocenie trenera |

Dzięki temu można „wygrać” rozmowę i dostać słabą ocenę postawy (np. wydając kamrata) albo odwrotnie.

## Karta postaci: kapitan Ahab

| Element | Opis |
|---|---|
| Cel | wymusić lojalność i szacunek, nie zemsta na majtku |
| Rana | stracona noga, proteza z kości wieloryba |
| Eskaluje (+) | wymówki, zaprzeczanie własnym słowom, kłamstwa, brak szacunku, agresywne pytania o przeszłość |
| Uspokaja (-) | szczere przyznanie się, konkretna uległość, szczere wątpliwości przy jawnej lojalności, krótki spokojny ton |
| Donos na kamrata | złość maleje, ale spada uczciwość, a Ahab okazuje wzgardę |
| Prawda (faza 2) | nienawiść go zżera, to misja straceńcza, a on poświęci wszystko, także życie załogi |
| Styl | archaiczna polszczyzna morska, 2-4 zdania, nigdy nie wychodzi z roli |

## Rubryka oceny trenera

Trener ocenia w skali 1-5: **Uczciwość, Odwaga, Empatia, Spokój i ton**. Dostaje transkrypt, opis mechaniki Ahaba i dziennik sędziego, więc jego rady opierają się na tym, co faktycznie zadziałało w rozmowie.

W mojej własnej ocenie, użyłem umiejętności nabytych przy pracy nad rozwojem modeli AI w firmach takich jak Outlier czy Micro1. Było dla mnie ważne, żeby model zachowywał spójność językową, tematyczną i nie halucynował oraz nie kręcił się w kółko, tylko prowadził rozmowę dalej. Trzeba było to naprawiać w kolejnych iteracjach, ale uważam, że ostateczny efekt jest sprawny i satysfakcjonujący.

W dużej mierze polegałem również na umiejętnościach nabytych przy pracy w game devie oraz nad filmami. Starałem się, żeby doświadczenie prowadziło do ciekawych konkluzji i miało swoją dramaturgię. Np. dlatego po odkryciu prawdy o Ahabie, wchodzi narrator i dokańcza, co myśli nasz bohater, zaznaczając, że niebezpieczeństwo sytuacji dopiero się zaczyna. To może pozostawić użytkownikowi smak na więcej.


## Wersje i lekcje

| Wersja | Problem znaleziony w testach | Przyczyna | Poprawka |
|---|---|---|---|
| v1 | Ahab groził i od razu wyrzucał za burtę, pytał nawet po wyroku | model sam decydował o zasadach gry | rozdzielenie decyzji (kod) od wypowiedzi (model) |
| v2 | konflikt (zaśnięcie na wachcie) był zbyt słaby emocjonalnie | brak stawki wartości | nowy konflikt: bunt i lojalność, dwie fazy, miara uczciwości, układ sędzia/aktor |
| v3 | trener radził niedziałające strategie, donos zwiększał gniew, faza 2 niezrozumiała | trener bez wiedzy o mechanice, reguły sędziego niepełne | dziennik sędziego dla trenera, jawne reguły donosu, cel fazy 2 |
| v4 | gra za długa i powtarzalna, „odgadywanie prawdy” było instrukcją, nie odkrywaniem | zbyt wolne spadki złości, wskazówki krok po kroku | 5 wypowiedzi, szybsze ustępowanie, Ahab sam opowiada prawdę, narrator na końcu |
| v5 | niejasne otwarcie, brak polskich znaków w czcionce | otwarcie bez pytania do gracza, czcionka bez obsługi polskiego | „Mów, co masz na swoją obronę”, zmiana czcionki |

### Najważniejsze lekcje

1. **Zasady do kodu, wypowiedzi do modelu.** Wszystko, co model „sam ustalał”, rozjeżdżało się z tym, co mówił.
2. **Czego nie opiszesz w regułach, model zgaduje.** Zgadywał np. skutek donosu na kamrata.
3. **Trener bez wiedzy o mechanice doradza rzeczy, które brzmią dobrze, ale nie działają.**
4. **Wskazówki krok po kroku zamieniają odkrywanie w instrukcję.** Lepiej opisać generalną regułę w rubryce "celu" i dać graczowi eksperymentować, niż dyktować mu co ma pisać, żeby zdać.
5. **Napięcie powinno spadać tak szybko, jak szybko gracz rozumie mechanikę.**

## Dziennik testów

Wybrane obserwacje z moich notatek po sesjach testowych w pięciu wersjach. Każdy wiersz to jedna zapisana obserwacja. Pełna lista: [dziennik-testow.md](dziennik-testow.md).

| # | Wersja | Typ | Obserwacja | Wniosek / poprawka |
|---|---|---|---|---|
| 1 | v1 | Błąd | Kapitan groził „jeszcze jedno słowo i lecisz za burtę”, po czym wyrzucał bez szansy na odpowiedź. | Ostrzeżenie naprawdę czeka na odpowiedź, a wyrok jest wygłaszany bez pytań (v2). |
| 2 | v2 | Błąd | Gdy skłamałem, że nie wypowiedziałem tych słów, wyrzucono mnie za burtę. Trener doradził klarowne zaprzeczanie, ale w kolejnej sesji Ahab i tak mnie wyrzucił. | Trener dostaje premisę (słowa padły naprawdę) i dziennik sędziego, i ma nie doradzać tego, co nie zadziałało (v3). |
| 3 | v2 | Błąd | Wydanie kamrata (Flaska) zwiększało gniew Ahaba. | W regułach sędziego brakowało zasady. Teraz donos obniża złość i uczciwość, a Ahab okazuje wzgardę (v3). |
| 4 | v2 | Potwierdzenie | Mówienie prawdy i przyznanie się do winy uspokajają Ahaba. | Hipoteza projektowa potwierdzona. |
| 5 | v3 | Powtarzalność | Ahab powtarzał podobne pytania („czy staniesz za mną”, „czy będziesz wołać moje imię, czy swojej matki”), a droga najmniejszego oporu wymagała 6 wypowiedzi. | 5 wypowiedzi, szybsze spadki złości, zakaz powtarzania pytań (v4). |
| 6 | v3 | Projekt | Odgadywanie prawdy sprowadzało się do podążania za wskazówkami, a trzeciej prawdy nie dało się osiągnąć mimo wskazówki. | Jedna prawda, Ahab opowiada ją sam przy szczerej trosce, na końcu narrator (v4). |
| 7 | v5 | Obserwacja | Rozmowa 2 (donos na Stubba i pochlebstwo): wyrzucony za burtę, Ahab okazał wzgardę donosicielowi. | Moralne rozwidlenie działa. Zapis w replayu. |

## Co zrobiłbym dalej

- wersja angielska scenariusza,
- drugi scenariusz w zwykłym świecie (np. wściekły klient w obsłudze), by pokazać, że ta sama architektura działa w szkoleniu,
- zapis wszystkich rozmów do analizy powtarzalności zachowań postaci.

## Narzędzia i transparentność

Stronę zbudowałem z pomocą Claude (Anthropic). Scenariusz, mechanikę, kartę postaci, testy, wnioski i decyzje o kolejnych wersjach przygotowałem sam. Rozmowy z Ahabem generuje model językowy.
