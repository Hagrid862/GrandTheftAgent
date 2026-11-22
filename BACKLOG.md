# GrandTheftAgent · backlog projektu

Nagłówki M0–M7 to kamienie milowe. Główne punkty pod nimi to issues, a zagnieżdżone zadania można przenosić do GitHuba jako sub-issues. Drobne czynności sprawdzające są częścią kryteriów odbioru.

Zadania oznaczone warunkiem wchodzą do zakresu po spełnieniu tego warunku. Platformy wydania, minimalny sprzęt, liczba dzielnic, misji i pojazdów oraz progi wydajności wymagają decyzji w odpowiednich etapach. Roadmapa zakłada oryginalne miasto, postacie, historię i zawartość.

Każde issue ma wskazać oczekiwany efekt, zależności i sposób weryfikacji. Przy odbiorze zapisujemy wersję builda, wykonaną próbę, wynik i znane ograniczenia. Powtarzalne pakiety produkcji rozwijamy w osobne issues dla konkretnych dzielnic, misji lub zestawów assetów.

Przed przekazaniem builda uczestnikom sprawdzić jego diagnostykę na konfiguracji używanej w próbie. Jeśli build zapisuje lub wysyła dane, określić ich zakres, miejsce zapisu, osoby z dostępem, okres przechowywania i sposób usunięcia. Poinformować uczestników, co się dzieje z danymi, i przejść procedurę na próbnym zgłoszeniu.

Przed próbą z graczami, która decyduje o zakresie, wykończeniu lub publikacji, zapisać pytanie, profil uczestników, minimalną liczbę ważnych sesji dla istotnych wariantów, zachowania potrzebne do zaliczenia i regułę ponowienia. Ustalić dostępność uczestników, czas rekrutacji i rezerwę na powtórkę. Utknięcie lub rezygnacja z powodu gry wliczają się do wyniku, a awaria stanowiska niezwiązana z grą może uzasadnić powtórkę. Do badania orientacji zapewnić osoby, które pierwszy raz widzą obszar, także w próbie powtórnej. Przy odbiorze zapisać build, wyniki, odstępstwa i decyzję.

Przy przenoszeniu zadania do GitHuba użyj jego identyfikatora i dopisz wykonawcę, osobę odbierającą, wymagany build lub dane wejściowe oraz odnośniki do zadań blokujących. W zadaniu warunkowym zapisz decyzję aktywującą zakres. Gdy warunek nie zachodzi, zapisz podstawę zamknięcia. Jeśli dwa kroki mają odrębne zależności lub dają się odebrać w różnych buildach, otrzymują osobne sub-issues.

## Przejścia między etapami

| Etap | Decyzja przy odbiorze |
| --- | --- |
| M0 | Czy lokalny build jest powtarzalny i czy można bezpiecznie powierzyć Codexowi potrzebne operacje? Jeśli próba ujawniła luki, przypisać alternatywną procedurę lub właściciela przed zleceniem zależnych prac. |
| M1 | Czy gracze rozumieją pętlę i chcą ją kontynuować? Na podstawie spisanych kryteriów wybrać rozwinięcie, poprawkę z ponowną próbą albo inną pętlę. |
| M2 | Czy dopracowana sesja spełnia kryteria rozgrywki i budżety techniczne? Jeśli wynik odbiega od celu, poprawić przyczynę, ograniczyć zakres lub ponowić próbę przed zatwierdzeniem zależnych prac. |
| M3 | Czy powtórna próba, platformy i budżet uzasadniają zakres produkcji? Zatwierdzić plan, powtórzyć potrzebne próby dla mniejszego zakresu lub wstrzymać produkcję i wrócić do wizji. |
| M4 | Czy wszystkie zatwierdzone pakiety są zintegrowane i przechodzą podstawową regresję? Braki prowadzą do poprawki lub jawnej zmiany zakresu. |
| M5 | Czy gra przechodzi pełną ścieżkę bez blokerów? Przed betą zatwierdzić progi i klasy błędów zatrzymujące wydanie. |
| M6 | Czy wskazany pakiet spełnia warunki wydania, a obsługa premiery działa? Jeśli warunek nie jest spełniony, poprawić pakiet i powtórzyć odpowiednie próby. |
| M7 | Czy gracze dostają zatwierdzony pakiet i czy zgłoszenia można odtwarzać? Publikować poprawkę po potwierdzeniu potrzeby. |

Przy każdej decyzji osoba odpowiedzialna za etap zapisuje wersję builda, kryteria, wyniki, decyzję, dalszy zakres i otwarte ryzyka. Progi ustala się przed próbą. Jeżeli próg trzeba zmienić, odnotować powód i porównać wynik według obu kryteriów. Wyniki odbioru dotyczą integrowanej rewizji lub wskazanego artefaktu. Gdy zmiana podstawy, konfiguracji lub zawartości może wpłynąć na wynik, powtórzyć dotkniętą próbę przed odbiorem. Przy przeniesieniu ważnego wyniku z wcześniejszej wersji udokumentować podstawę.

Przy zamknięciu M1 i M2 zapisać wydatki, czas człowieka i pozostałe środki względem limitu M0. Przed kolejną próbą odjąć koszt przygotowania i rezerwę na powtórkę. Jeśli środków brakuje, zatwierdzić mniejszy wariant lub wstrzymać zależne prace.

### Kolejność najważniejszych prac

Identyfikatory w tytułach nadają się do odwołań jeszcze przed utworzeniem issues. Numer identyfikuje zadanie, a kolejność wynika z zależności.

| Etap | Co musi być gotowe przed rozpoczęciem zależnej pracy |
| --- | --- |
| M0 | M0.02 i próbka wersjonowania z M0.03 przed odbiorem M0.04. M0.02 i uprawnienia z M0.05 przed M0.06. M0.04 przed próbami M0.07 i M0.08. Przed pierwszym zleceniem M1 użyć wzoru sprawdzonego w M0.09 i zasad z M0.10. |
| M1 | M1.01 przed wyborem sesji M1.02. Po zatwierdzeniu sesji robocza mapa M1.03 i mechaniki M1.04 mogą powstawać równolegle. Obie prace muszą być zintegrowane przed M1.05. |
| M2 | Po M2.01 można równolegle prowadzić M2.02 i M2.03. Lista miejsc z M2.03 rozpoczyna roboczą część M2.04. Do próby układu potrzebne są tymczasowy cel M2.06 i sygnały M2.07. Przed wykończeniem miejsc zależnych od M2.02 trzeba powtórzyć próbę z wczesną M2.05, jeśli początkowo użyto zastępnika. M2.08 odbiera zintegrowany wynik M2.03–M2.07. |
| M3 | Stan aktywnej misji z M2.06 jest wejściem do M3.01. Druga sesja dostarcza wejścia do M3.02 i dowody powtórzenia pracy dla M3.03–M3.06. Jeśli gra utrwala postęp, kontrakt M3.03 poprzedza zatwierdzenie formatu M3.06. Kontrole M3.07 korzystają z kontraktu M3.03 i zatwierdzonego rejestru M3.06 dla trwałego postępu. Obie sesje służą do M3.07, a typowe pakiety do M3.08. Wyniki ograniczają zakres zatwierdzany w M3.09. |
| M4 | M3.09 określa progi i pakiety zależne od M4.14. Wymagana próbka M4.16 zasila M4.14, a odbiór M4.14 poprzedza M4.02. Obie próby korzystają z roboczego interfejsu M4.11 i właściwych roboczych pakietów dzielnic, misji i interakcji. M4.02 odblokowuje wykończenie i nagrania po zatwierdzeniu scen. Zależności symulacji są w tabeli poniżej. M4.15 odblokowuje kolejne zależne pakiety wykończeniowe, M4.03 sprawdza partie, a M4.13 odbiera pełny build. |
| M5 | M5.01 dostarcza scenariusze do M5.02 i M5.04. Wyniki tych prób i weryfikacja poprawek M5.03 są wejściem do M5.05. |
| M6 | M5.05 dostarcza warunki publikacji. Po rundzie M6.01 i poprawkach M6.05 oznacza kandydata. M6.02–M6.04 mogą rozpocząć się wcześniej, a ich wyniki dotyczące pakietu muszą być potwierdzone dla oznaczonego kandydata. M6.07 odbiera te wyniki i próbę M6.06. |
| M7 | Decyzja M6.07 jest potrzebna przed M7.01. M7.02 dostarcza zweryfikowane zgłoszenia. M7.03 uruchamiamy, gdy potrzebna jest poprawka. M7.04 może się odbyć po odbiorze premiery i przekazaniu zgłoszeń do obsługi. |

W M4 roboczy interfejs z M4.11 zasila M4.14 i M4.02. Scenariusz roboczy M4.05 zasila roboczą część M4.06. Po M4.02 zatwierdzone teksty M4.05 oraz odbiór skryptu dla każdego nagrywanego języka w M4.12 odblokowują zamówienie nagrań M4.10. Odbiór plików audio pozwala podłączyć je w M4.06. Odsłuch i zgodność z napisami sprawdzamy po integracji.

| Podzadanie tras lub symulacji | Wejście i odbiór |
| --- | --- |
| M4.04a · Trasy robocze | Robocza geometria i połączenia wystarczające do scenariusza. Wynik przekazać do M4.08a. |
| M4.08a · Robocza symulacja | Trasy M4.04a i minimalne zachowania potrzebne w sesji. Wynik zasila M4.02 i M4.14, jeśli pierwsza partia go potrzebuje. |
| M4.04b · Odcinek docelowych połączeń | Wynik M4.02 i układ przewidziany do wydania. Odbiór odcinka może odbyć się na roboczej geometrii. |
| M4.08b · Pomiar przed wykończeniem | Odcinek M4.04b i scenariusz M3.09. Wynik odblokowuje wskazane pakiety oprawy. |
| M4.04c · Pełna sieć | Sprawdzone trasy dzielnic. Przekazać do finalnej symulacji. |
| M4.08c · Finalna symulacja | Odebrana sieć M4.04c. Wspólny wynik symulacji, dzielnic i misji sprawdzić w M4.03. |

### Próby utrwalania stanu

W M2 dla każdej kategorii zapisujemy, czy należy do wydania. W zależnych issues uruchamiamy tylko próby kategorii zatwierdzonych. Odbiór wskazuje, które próby były nieaktywne i dlaczego.

| Kategoria | Jak ją sprawdzamy |
| --- | --- |
| Punkt kontrolny w bieżącej sesji | Ponowić misję lub odtworzyć jej stan w działającym procesie. Sprawdzić cele, aktorów i skutki powtórzonej interakcji. |
| Trwały postęp | Zamknąć grę, uruchomić nowy proces i odczytać postęp. Przy aktualizacji sprawdzić obsługiwane wersje, a przy zapisie przerwanym zachowanie ostatniego poprawnego stanu. |
| Ustawienia | Zmienić wskazane opcje, uruchomić nowy proces i sprawdzić ich zachowanie po aktualizacji. |

## M0 · Gotowe środowisko i sprawdzony workflow Codexa

- **M0.01 · Zapisać założenia i ograniczenia projektu**
  - Określić dostępny czas, maksymalny nakład człowieka i budżet na narzędzia, infrastrukturę oraz produkcję. Uwzględnić możliwe koszty nagrań, lokalizacji i testów zewnętrznych.
  - Wskazać sprzęt do pierwszych prób i zapisać kandydatów na platformy docelowe.
    - Zapisać model komputera, pamięć, przestrzeń na silnik i cache oraz dostęp do maszyn testowych.
    - Zapisać, które ryzyka wpływają na kolejny etap, kto podejmuje decyzje i od czego zależy ich termin.
  - **Odbiór.** Mamy zapisane założenia, otwarte decyzje i moment, w którym trzeba je podjąć. Ustalenie platformy wydania może poczekać. Do pomiarów M2 potrzebujemy już sprzętu referencyjnego.

- **M0.02 · Zweryfikować instalację Unreal Engine na Apple Silicon**
  - Sprawdzić zainstalowaną wersję Unreal, Xcode, SDK i kompilator.
  - Na tymczasowym projekcie sprawdzić kompilację prostego modułu C++, uruchomienie mapy w edytorze oraz przygotowanie i uruchomienie samodzielnego builda na Macu.
    - Utworzyć prosty Blueprint, skompilować go, zapisać i ponownie otworzyć.
    - Sprawdzić, czy pakiet uruchamia się poza edytorem i ładuje właściwą mapę.
  - Zapisać wersję silnika wybraną do projektu. Jeśli odbiega od 5.9.0, odnotować przyczynę, zgodność wtyczek i skutki dla dalszych prób.
  - **Odbiór.** Mamy zapisaną wersję narzędzi potrzebną do powtórzenia udanego otwarcia edytora, kompilacji i uruchomienia pakietu. Niezaliczone próby zatrzymują zależne prace, dopóki nie zostaną rozwiązane.

- **M0.03 · Ustalić zasady przechowywania projektu Unreal w GitHubie**
  - Określić, które pliki wersjonujemy, które ignorujemy i które obejmujemy Git LFS.
  - Sprawdzić dodanie, pobranie i aktualizację przykładowej mapy `.umap` i assetu `.uasset` ze świeżego checkoutu.
  - Sprawdzić dostępny sposób koordynowania pracy nad tym samym plikiem binarnym oraz koszty przechowywania i transferu.
  - **Odbiór.** Wybór sposobu wersjonowania wynika z próby na rzeczywistych plikach Unreal. Wiadomo, jak uniknąć równoczesnych zmian tego samego assetu.

- **M0.04 · Przygotować minimalny projekt GrandTheftAgent**
  - Utworzyć projekt z prostą mapą testową i ustalić podstawowy układ kodu oraz zawartości.
  - Zapisać sposób otwarcia projektu i przygotować jeden lokalny punkt wejścia do kompilacji, cook, pakowania i sprawdzenia załadowania właściwej mapy.
    - Zwrócić wynik możliwy do odczytania z kodu wyjścia. Powiązać rewizję, wersję silnika, ustawienia, log i wygenerowany artefakt.
    - Ustalić limit czasu automatycznych kroków. Po przekroczeniu zachować log, zakończyć procesy potomne danej próby i oznaczyć uruchomienie jako nieudane. Wynik wcześniejszej próby nie może zaliczyć nowego uruchomienia.
  - Zapisać wymagane wersje silnika i wtyczek. Sprawdzić, czy katalogi generowane zostają poza repozytorium.
    - Zapisać źródła instalacji silnika, SDK, wtyczek i danych LFS. Na świeżym checkoutcie sprawdzić build bez zależności od istniejącego cache i osobistych ustawień edytora.
    - Dla instalatorów i paczek zapisać niezmienny identyfikator lub sumę kontrolną i sposób odzyskania. Dla zależności budowanych ze źródeł zapisać rewizję. Zaktualizować wykaz przed M4 i potwierdzić go przy odtwarzaniu M6.05.
  - Ustalić konwencje nazewnictwa map i assetów oraz miejsce przechowywania decyzji technicznych.
  - **Odbiór.** Ze świeżego checkoutu da się zbudować projekt i uruchomić mapę. Instrukcja wskazuje, gdzie znaleźć logi i wynik builda.

- **M0.05 · Ustalić uprawnienia i zasady samodzielnej pracy Codexa**
  - Określić, które operacje agent może wykonywać samodzielnie, a które wymagają Twojej decyzji. Uwzględnić edycję projektu, instalację wtyczek, zmiany w GitHubie i publikowanie buildów.
  - Ustalić, jak agent zapisuje postęp długich zadań, wznawia pracę i zgłasza blokady.
  - Rozdzielić uprawnienia do zmian roboczych i operacji zastrzeżonych do decyzji człowieka. W środowisku testowym, bez wysyłania zmian na publiczny kanał, potwierdzić, że dostęp zwykłego wykonawcy nie pozwala samodzielnie wykonać zastrzeżonych operacji.
  - **Odbiór.** Reguły, wynik sprawdzenia dostępu i oczekiwany dowód przy oddaniu zmian są zapisane. Każda czynność wymagająca decyzji człowieka ma wskazaną ścieżkę wykonania.

- **M0.06 · Sprawdzić autonomię Codexa na jednym zadaniu w Unreal**
  - Sprawdzić dostępne integracje MCP i wybrać sposób wykonania próby. W razie potrzeby użyć skryptu edytora lub CLI.
    - Zapisać wersję wybranej integracji lub skryptu, wymagane zależności i sposób uruchomienia na czystej konfiguracji.
  - Zlecić Codexowi zmianę testowego Blueprintu lub poziomu z efektem widocznym po uruchomieniu mapy. Codex zapisuje zmianę, ponownie otwiera projekt i sprawdza zachowanie.
    - Zapisać stan początkowy i listę zmienionych pakietów po wykonaniu zadania.
    - Sprawdzić, czy atrybut lub zachowanie przetrwało zamknięcie edytora.
    - Ustalić, jak agent wraca do poprzedniej wersji testowej po nieudanej edycji, bez naruszania cudzych zmian.
  - **Odbiór.** Raport wskazuje oczekiwany i zaobserwowany efekt, kroki wykonane przez Codexa, użyte narzędzia oraz ewentualną pomoc człowieka. Wynik pokazuje rzeczywisty poziom autonomii. Kolejne próby wynikają z potrzeb M1.

- **M0.07 · Ocenić wykonalność zdalnych buildów i testów**
  - Użyć lokalnego polecenia builda jako podstawy próby zdalnej i porównać wyniki dla tej samej rewizji.
  - Sprawdzić dostępność runnera, wymagania dotyczące silnika, czas buildu i przewidywany koszt. Jeśli środowisko jest dostępne, uruchomić próbny build.
    - Porównać pierwszy build z kolejnym buildem po małej zmianie.
    - Zmierzyć rozmiar artefaktów i ustalić okres przechowywania logów.
  - **Odbiór.** Wiemy, które kontrole warto uruchamiać zdalnie i które zostają lokalne. Zdalny build jest opcjonalny. Cały etap podlega odbiorowi M0.10.

- **M0.08 · Sprawdzić import i aktualizację assetu 3D**
  - Przygotować prosty obiekt w Blenderze, zaimportować go, zmienić źródło i wykonać ponowny import.
  - Przy pierwszym imporcie zapisać pochodzenie assetu, jego licencję lub autorstwo i lokalizację pliku roboczego.
    - Zapisać format eksportu, jednostki, ustawienia importu i miejsce przechowywania mapy testowej.
    - Ustalić, jak dokumentować asset wygenerowany narzędziem AI lub pobrany z biblioteki, jeśli wejdzie do projektu.
    - Inny wykonawca pobiera wskazaną wersję źródła i ponawia import na świeżym checkoutcie według zapisanych ustawień. Jeżeli projekt prowadzi jedna osoba, wykonać próbę w osobnym czystym katalogu bez odwołań do kopii roboczej autora.
  - **Odbiór.** Ponowny import jest odtwarzalny z zapisanego źródła i ustawień. Model zachowuje oczekiwaną skalę, orientację, materiał i kolizję.

- **M0.09 · Przygotować tablicę i wzór issue**
  - Utworzyć etykiety obszarów i statusy `Backlog`, `Gotowe do pracy`, `W toku`, `Do sprawdzenia` i `Zrobione`.
    - Rozróżnić zaliczony odbiór od zamknięcia zakresu nieuruchomionego. Wypróbować oba wyniki na tablicy i sprawdzić, czy odebrana partia wskazuje, które zadania zaliczono.
  - Wzór issue ma zawierać oczekiwany wynik, wykonawcę, osobę odbierającą, wymagany build lub dane wejściowe, zadania blokujące, kryteria odbioru i sposób sprawdzenia. Dla zakresu warunkowego wskazać decyzję aktywującą. Zadanie trafia do `Gotowe do pracy`, gdy ma te informacje i można je rozpocząć.
  - Przygotować wzór zgłoszenia błędu z identyfikatorem builda, platformą, krokami odtworzenia i logiem.
  - Użyć wzoru na jednym przykładowym zadaniu i sprawdzić przejście od przypisania do odbioru.
  - **Odbiór.** Na tablicy widać, co można podjąć, co czeka na inną pracę i co wymaga odbioru. Sprawdzony wzór jest dostępny przed pierwszym zleceniem M1.

- **M0.10 · Odebrać M0**
  - Powtórzyć build ze świeżego checkoutu i uruchomić mapę testową.
  - Zatwierdzić wynik próby Codexa i zapisać ograniczenia, które wpływają na wykonanie M1.
  - Do odbioru dołączyć zasady wersjonowania plików binarnych z M0.03, zakres uprawnień M0.05, sposób uruchamiania kontroli z M0.07 i wynik ponownego importu M0.08. Jeśli późniejsze użycie źródeł 3D nie jest potrzebne w M1, można odłożyć próbę do pierwszego pakietu, który od niej zależy. Zapisać ten pakiet w decyzji.
  - Potwierdzić sprawdzony wzór zadania M0.09 i użyć go przy pierwszym zleceniu M1.
  - **Odbiór.** Lokalny build, zasady pracy z binariami, sprawdzone uprawnienia i wynik próby Codexa są potwierdzone. Decyzja wskazuje sposób kontroli i gotowość importu lub blokadę pierwszego zależnego zadania.

**Kolejność M0.** Sprawdzenie instalacji, przygotowanie zasad repozytorium i zapisanie ograniczeń można zacząć równolegle. Próbę Codexa można wykonać na projekcie tymczasowym po potwierdzeniu działania edytora i ustaleniu uprawnień do próby.

## M1 · Jedna sprawdzona pętla rozgrywki

- **M1.01 · Zatwierdzić jednostronicową wizję gry**
  - Ustalić rolę gracza, charakter fikcyjnego miasta i to, co ma wyróżniać grę.
  - Zapisać ton narracji i to, ile swobody ma gracz między zadaniami oraz w trakcie misji.
    - Określić minimalną swobodę wymaganą od otwartego świata. Zapisać, które wybory celu, zmiany trasy i powroty do misji są częścią tożsamości gry. Zmiana tego minimum wymaga aktualizacji zatwierdzonej wizji.
  - Wybrać główną aktywność, którą chcemy sprawdzić jako pierwszą.
    - Określić perspektywę kamery i oczekiwaną swobodę eksploracji.
    - Spisać, czym prototyp ma się wyróżnić i które elementy wizji odkładamy na późniejsze etapy.
  - Określić, do jakich graczy ma trafić gra, w tym jakie doświadczenie z gatunkiem i urządzeniami może wpływać na ich pierwszą sesję.
  - **Odbiór.** Jest jasne, co gracz robi regularnie i dlaczego ta aktywność ma być ciekawa.

- **M1.02 · Zaprojektować i zatwierdzić pierwszą grywalną sesję**
  - Zapisać jedną hipotezę. Przykładowo, gracz rozumie cel po pierwszej interakcji i potrafi sam wybrać sposób jego osiągnięcia. Właściwy test zależy od wybranej pętli.
  - Określić punkt startowy, cel, przewidywany czas sesji, możliwy wynik i sposób ponowienia próby.
  - Wskazać, jakie zachowania gracza uznamy za potwierdzenie hipotezy.
    - Przed próbą zapisać, ilu uczestników i jakiego wyniku potrzebujemy, by rozwinąć, poprawić lub zmienić pętlę.
    - Dobrać uczestników do pytania badawczego i profilu z M1.01. Zapisać istotne różnice w znajomości podobnych gier i urządzeń wejściowych, żeby uwzględnić je przy interpretacji.
    - Ustalić, jak zaobserwować chęć dalszej gry lub ponownej próby i jak ustalić jej przyczynę w rozmowie po teście.
    - Do głównego wyróżnika z M1.01 przypisać obserwowalne zachowanie i pytanie do gracza. Jeśli M1 jeszcze go nie pokazuje, wskazać próbę w M2 lub M3 potrzebną przed decyzją M3.09.
  - Zapisać urządzenia wejściowe, oczekiwany przebieg bez podpowiedzi oraz warunek przerwania próby.
  - Ustalić limit czasu i nakładu na zbudowanie oraz sprawdzenie prototypu i termin decyzji. Po przekroczeniu limitu uprościć próbę, zmienić hipotezę lub zakończyć badanie wariantu.
  - Przypisać wymagane operacje Codexa do wyników M0.06. Jeśli w sesji agent ma zmienić mapę lub Blueprint w projekcie docelowym, przed zleceniem implementacji powtórzyć potrzebną operację na tym projekcie. Sprawdzić zmienione pakiety, pakowany build z czystego checkoutu i lokalne cofnięcie próby bez utraty niezależnych zmian. W razie braku potwierdzenia zlecić ten krok innemu wykonawcy.
  - **Odbiór.** Zatwierdzona sesja ma wyraźne granice, zamkniętą listę potrzebnych systemów i scenariusz testu. Dopiero wtedy powstają issues implementacyjne dla wybranych mechanik.

- **M1.03 · Zbudować roboczą mapę do pierwszej sesji**
  - Rozmieścić punkt startowy, cel, potrzebne trasy i miejsca interakcji.
  - Użyć roboczej geometrii i sprawdzić skalę z perspektywy gracza.
    - Sprawdzić widoczność celu i alternatywną trasę, jeśli sesja ją przewiduje.
    - Sprawdzić granice obszaru, miejsca utknięcia i sposób powrotu gracza do sesji.
  - **Odbiór.** Mapę można przejść w przewidziany sposób, a jej układ pozwala sprawdzić hipotezę sesji.

- **M1.04 · Zaimplementować zatwierdzoną sesję**
  - Przygotować sterowanie postacią, kamerę i interakcje w zakresie potrzebnym do sesji.
  - Wykonać issues dla mechanik wybranych przy odbiorze zakresu.
  - Połączyć początek sesji, cel, informację o wyniku i ponowienie próby.
    - Sprawdzić przywrócenie pozycji gracza, obiektów i celów po restarcie.
    - Dodać proste komunikaty potrzebne do odbycia próby.
  - **Odbiór.** Całą sesję da się rozegrać i powtórzyć w samodzielnym buildzie. Sprawdzono również przewidziane niepowodzenie i zejście z głównej trasy.

- **M1.05 · Przetestować prototyp z osobami, które go nie tworzyły**
  - Poprosić uczestników o rozegranie sesji bez podpowiadania celu ani sterowania podczas pierwszej próby.
  - Zapisać, co zrozumieli, gdzie się zatrzymali i jakie zachowania potwierdziły lub podważyły hipotezę.
    - Zapisać czas do pierwszej istotnej decyzji, ukończenie próby i momenty wymagające pomocy.
    - Oddzielić obserwację zachowania od opinii zebranej po próbie.
    - Zanotować, czy uczestnik wybiera dalszą grę lub ponowną próbę, oraz jego powód.
  - **Odbiór.** Na podstawie obserwacji zapada decyzja, czy rozwijamy pętlę w M2, poprawiamy ją i powtarzamy próbę, czy sprawdzamy inną.

Jazda, piesi, ruch uliczny, policja, wnętrza i zapis gry pozostają kandydatami do kolejnych sesji. Konkretne issue powstaje, gdy mechanika jest potrzebna w zatwierdzonym zakresie.

## M2 · Reprezentatywny fragment gry

- **M2.01 · Zatwierdzić zakres i cele techniczne fragmentu**
  - Wybrać pętlę potwierdzoną w M1, obszar miasta, przebieg misji i docelową jakość prezentacji.
  - Ustalić limit czasu i nakładu na fragment także z poprawką i ponowną próbą. Po przekroczeniu ograniczyć obszar lub listę mechanik albo zakończyć wariant. Zapisać decyzję przy odbiorze M2.08.
  - Spisać listę mechanik i assetów niezbędnych do ukończenia sesji. Każdej pozycji przypisać miejsce w scenariuszu lub cel testu.
    - Przed produkcją spisać kryteria odbioru z graczami, w tym czytelność celu i chęć dalszej gry, oraz sposób podjęcia decyzji przy przekroczeniu budżetu.
    - Dla M2.08 zatwierdzić profil graczy, minimalną liczbę ważnych sesji i regułę ponowienia przy rozbieżnych lub niepełnych wynikach.
    - Osobno zdecydować o punktach kontrolnych w sesji, trwałym postępie i ustawieniach. Wskazać kategorie pokazywane w M2 i wymagane do wydania.
    - Ustalić próbę swobody w mieście. Gracz dostaje okazję wybrać kolejne działanie, zboczyć z trasy i wrócić do celu. Zapisać, co uzasadni rozwój dzielnic.
    - Zaplanować wczesną próbę na roboczej mapie oraz powtórkę po dopracowaniu. Kryteria orientacji i powrotu do celu stosujemy w obu próbach.
  - Wybrać sprzęt referencyjny, rozdzielczość i konfigurację grafiki.
    - Ustalić cele dla czasu klatki, pamięci, wczytywania i płynności przemieszczania się w miejscach o największym obciążeniu. Dodać próbę szybkiej jazdy, jeśli jest w zakresie.
    - Zapisać sposób pomiaru typowej klatki i skoków czasu klatki oraz rozróżnić pierwsze wczytanie od kolejnej próby na tej samej trasie.
      - Określić stan cache renderowania dla pierwszego przejścia i powtórki w pakowanym buildzie. Zachować ten wymiar w pomiarze kandydata na każdej platformie.
    - Ustalić reprezentatywną liczbę aktywnych pieszych i pojazdów, jeśli wchodzą do zakresu.
    - Sprawdzić wybrane ustawienia renderowania i oświetlenia na sprzęcie referencyjnym przed produkcją docelowych assetów.
  - **Odbiór.** Zatwierdzony scenariusz i ustawienia pomiarów pozwalają powtórzyć próbę na kolejnych buildach.

- **M2.02 · Sprawdzić platformy i ryzyka techniczne na roboczej mapie**
  - Dla poważnie rozważanych platform przeprowadzić próbę pakowania, instalacji, uruchomienia i pomiaru. Odnotować dostępność sprzętu, działanie potrzebnych wtyczek i zgodność ustawień renderowania.
  - Przed wykonaniem docelowej geometrii wybrać roboczy podział mapy. Przygotować dwa obszary o reprezentatywnej gęstości. W pakowanym buildzie sprawdzić czas przekroczenia granicy, wczytywanie obiektów i ciągłość nawigacji przy przewidywanej maksymalnej prędkości.
    - Sprawdzić, czy zmiana i zapis jednego obszaru omija pakiety należące do drugiego.
    - Odtworzyć obciążenie przez najdroższy wybrany system i ustalić warunek zmiany zakresu lub ustawień.
    - Gdy obciążenie jest zastępcze, powtórzyć krytyczną trasę z wczesną działającą wersją mechaniki z M2.05 przed wykończeniem miejsc zależnych od wyniku.
  - **Odbiór.** Zapisano roboczy podział, trasę, konfigurację i wyniki platform. Problemy wymagające zmian w projekcie mają decyzję przed rozpoczęciem docelowej oprawy.

- **M2.03 · Rozpisać miejsce, postacie i reprezentatywną misję**
  - Opisać charakter wybranego obszaru, jego funkcję w mieście i powody, dla których gracz chce go odwiedzić.
  - Rozpisać postacie, cel misji, dialogi, kolejność zdarzeń i wynik.
    - Ustalić dostępne wybory oraz to, co gracz może zrobić poza główną trasą.
    - Wskazać skutki ukończenia, niepowodzenia i porzucenia zadania.
    - Oznaczyć potrzebne lokacje, rekwizyty, animacje, napisy i dźwięk.
  - **Odbiór.** Scenariusz można przejść krok po kroku, a wymagania dają się powiązać z konkretnymi pracami.

- **M2.04 · Zbudować i dopracować reprezentatywny fragment miasta**
  - Wykorzystać listę lokacji i interakcji z M2.03. Z roboczymi assetami można zacząć przed decyzją techniczną M2.02.
  - **Odbiór roboczego układu**
    - Ustalić przebieg ulic, skrzyżowań, chodników, miejsc interakcji i wnętrz potrzebnych w sesji.
    - Sprawdzić widoczność punktów orientacyjnych, kolizje, nawigację i miejsca wczytywania mapy.
    - Przejść obszar pieszo oraz przejechać go, jeśli jazda jest częścią sesji.
    - Przed wykończeniem zależnych miejsc odebrać oddzielnie roboczą mapę z działającym celem M2.06 i sygnałami M2.07. Sprawdzić z graczami zbaczanie z trasy, orientację i samodzielny powrót. Jeśli wynik nie spełnia kryterium, poprawić układ i powtórzyć próbę.
    - Jeśli orientację testujemy podczas jazdy, potrzebny jest roboczy pojazd M2.05 z kamerą i zakresem prędkości odpowiadającym próbie.
  - **Wykończenie po odbiorze układu i zależnych prób technicznych**
    - Przygotować modułowe modele, materiały i zestaw dekoracji miejskich.
    - Sprawdzić skalę, punkty obrotu, kolizje, poziomy szczegółowości i koszty renderowania.
    - Zapisać wersje plików źródłowych, autorstwo, licencje i ustawienia importu. Potwierdzić ponowny import wybranego elementu na świeżym checkoutcie zgodnie z M0.08.
  - Przygotować światło i charakterystyczne kadry używane jako wzorzec dla kolejnych obszarów.
    - Zapisać wzorce skali, kolorystyki, gęstości detali i oświetlenia dla grafiki oraz level designu.
    - Jeżeli sesja obejmuje różne pory dnia, sprawdzić czytelność trasy i wymagania sprzętowe w każdej z nich.
  - **Odbiór.** Odcinek działa w buildzie, zachowuje zamierzony wygląd i można go zmierzyć na powtarzalnej trasie.

- **M2.05 · Dopracować sterowanie i mechaniki potrzebne w sesji**
  - Dopracować ruch, kamerę, animacje i interakcje obecne w zatwierdzonym scenariuszu.
    - Sprawdzić zachowanie kamery przy ścianach, w ciasnych miejscach i podczas zmiany trybu sterowania.
    - Sprawdzić wejście z urządzeń przewidzianych dla tego builda.
    - Przed testem ustalić scenariusz i kryterium panowania nad ruchem, kamerą lub pojazdem. Sprawdzić dla każdego przewidzianego urządzenia, czy gracz sam wykonuje manewr i rozumie przyczynę niepowodzenia.
  - Jeżeli zakres obejmuje jazdę, przygotować reprezentatywny pojazd.
    - Oddzielnie odebrać roboczy pojazd do M2.04, jeśli układ miasta ma być testowany podczas jazdy.
    - Dostosować przyspieszenie, hamowanie, skręcanie i zachowanie na wybranych nawierzchniach.
    - Sprawdzić wsiadanie, wysiadanie, zmianę kamery i obsługę zablokowanego miejsca wyjścia.
  - Jeżeli zakres obejmuje ruch lub pieszych, zbudować lokalną próbę symulacji.
    - Sprawdzić przejazd przez skrzyżowanie, przekraczanie ulicy, przeszkodę i ponowne znalezienie drogi.
    - Sprawdzić wpływ gęstości symulacji na przebieg misji i wydajność.
  - Jeżeli sesja obejmuje policję, wdrożyć jeden scenariusz reakcji w ramach reguł gry.
    - Sprawdzić rozpoczęcie, eskalację i zakończenie stanu poszukiwania oraz powrót do stanu misji.
  - Uzgodnić z M2.06 sygnały mechanik potrzebne do rozpoczęcia i zakończenia celów oraz do obsługi niepowodzenia.
  - Jeżeli M2.02 używa zastępnika obciążenia, dostarczyć do ponownego pomiaru działającą wersję odpowiedniej mechaniki przed jej finalną oprawą.
  - **Odbiór.** Każda wybrana mechanika działa w sesji i ma sprawdzony przypadek niepowodzenia.

- **M2.06 · Wdrożyć misję i zatwierdzone formy wznowienia**
  - Użyć scenariusza M2.03 i sygnałów M2.05. Na czas równoległej pracy korzystać z zastępczych zdarzeń o tym samym formacie.
  - Odrębnie odebrać tymczasowy cel do M2.04. Wystarczy start, wskazanie celu, odejście i powrót z zachowaniem stanu potrzebnego do próby układu. Odbiór może poprzedzić pozostałe mechaniki misji.
  - Podłączyć cele, dialogi, wyzwalacze, zakończenie i stan świata po ukończeniu.
  - Obsłużyć opuszczenie obszaru misji, powtórzenie interakcji i niepowodzenie.
    - Stan aktywnego celu przechowuje system misji niezależnie od aktora ładowanego wraz z mapą. Po ponownym wejściu odtworzyć cel i potwierdzić, że nagroda ani wyzwalacz nie uruchomią się drugi raz, również bez trwałego zapisu.
    - Identyfikować cel i instancję obiektu przez cały czas trwania sesji, także między wczytaniami obszaru. Sprawdzić dwie instancje tego samego Blueprintu, aby odtworzenie jednej nie zmieniło stanu drugiej.
  - Dla punktu kontrolnego odtworzyć stan w tej samej sesji. Sprawdzić cele, obecne w scenie postacie i pojazdy oraz jednokrotne przyznanie nagród.
  - Dla trwałego postępu przypisać celom i obiektom stabilne identyfikatory niezależne od nazwy i lokalizacji assetu. Sprawdzić wczytanie w nowym procesie gry.
  - **Odbiór.** Sesję można ukończyć i przerwać. Zatwierdzone formy wznowienia odtwarzają właściwy stan.

- **M2.07 · Przygotować HUD, dźwięk i dostępność sesji**
  - Przed implementacją wybrać wymagania dla napisów, czytelności, urządzeń wejściowych i ustawień. Jeśli plan obejmuje tłumaczenia, ustalić identyfikatory tekstów i sposób przekazania kontekstu.
  - Pokazać cel, dostępne interakcje i wynik w sposób sprawdzony w teście z graczem.
    - Odrębnie odebrać roboczy zestaw sygnałów orientacji i celu do M2.04 przed testem układu. Docelowy HUD i audio mogą powstać później.
  - Przygotować dźwięk otoczenia, postaci i mechanik używanych w sesji.
    - Sprawdzić słyszalność dialogu w scenach z hałasem, czytelność napisów oraz przejścia między sceneriami.
  - Sprawdzić czytelność interfejsu, napisy, sterowanie i dostępne ustawienia w reprezentatywnych warunkach.
    - Dla kluczowej funkcji dostępności przewidzieć próbę z osobą, która jej potrzebuje. Sprawdzić, czy samodzielnie znajduje ustawienie i używa go w sesji.
  - **Odbiór.** Gracz otrzymuje potrzebne informacje w działającym buildzie i może ukończyć sesję z przewidzianym urządzeniem wejściowym.

- **M2.08 · Zmierzyć koszt fragmentu i odebrać M2**
  - Zebrać obserwacje graczy o rozgrywce, czytelności celu i kierunku wizualnym.
    - Porównać zachowanie podczas swobodnego wyboru następnego działania z kryteriami zapisanymi przed próbą.
    - Powtórzyć próbę orientacji i powrotu do celu z roboczej mapy M2.04 na dopracowanym buildzie.
    - Porównać wynik jakości sterowania z kryterium M2.05 dla każdego przewidzianego urządzenia.
  - Zmierzyć wydajność na trasie referencyjnej i w najcięższej scenie.
    - Zapisać konfigurację, logi, wyniki pomiaru i momenty spadków płynności.
  - Zapisać czas oraz zależności przygotowania ulicy, assetu, scenariusza i działającej misji.
  - Ocenić, które elementy projektu mogą ograniczyć skalę miasta lub liczbę aktywnych systemów.
  - Dołączyć wynik dla każdej kategorii utrwalania wybranej do pokazania w M2. Ustawienia sprawdzić po uruchomieniu nowego procesu, jeśli wchodzą do próby.
  - Dołączyć status prób M2.02 dla każdej rozważanej platformy. Wskazać wyniki konieczne do rozpoczęcia kolejnych prac i braki z terminem decyzji w M3.
  - Przed M3.01 zatwierdzić limit nakładu na M3, datę decyzji i listę prób blokujących produkcję. Wskazać, które opcjonalne elementy odkładamy po wyczerpaniu limitu i jaka próba wystarczy do zaakceptowania ograniczonego zakresu.
  - **Odbiór.** Wyniki graczy, pomiarów i aktywnych prób utrwalania porównano z wcześniej zatwierdzonymi kryteriami. Przy odchyleniu zapisano decyzję i potrzebną powtórkę. Zatwierdzono limit i zakres M3.

## M3 · Sprawdzenie, czy rozwiązania da się wykorzystać ponownie

- **M3.01 · Wykonać drugi przypadek użycia**
  - Wybrać drugą grywalną sesję z przejściem między obszarami. Jeśli M4 obejmuje produkcję misji, użyć w niej co najmniej jednego wspólnego elementu misji z M2 w odmiennych warunkach.
    - Przed próbą dopasować kryteria eksploracji z M2.01 do przejścia między obszarami. Zapisać, jakie wyniki uzasadniają utrzymanie zakresu dzielnic, jego ograniczenie lub kolejną próbę.
    - Określić profil graczy, minimum ważnych sesji i regułę dla niepełnych lub rozbieżnych wyników. Do oceny samodzielnej orientacji użyć osób, które jeszcze nie znają drugiego obszaru.
  - Użyć istniejących komponentów, assetów i reguł. Zapisywać miejsca wymagające kopiowania, ręcznej konfiguracji lub poprawek.
    - Dać graczom połączony build i sprawdzić powrót do głównej ścieżki po jej opuszczeniu.
    - Jeśli eksploracja jest celem wydania, sprawdzić, czy uczestnicy sami znajdują powód, by pozostać w drugim obszarze. Wynik wykorzystać przy wyborze wielkości i zawartości dzielnic.
  - Porównać czas pracy i liczbę problemów z M2. Wskazać powtarzalne problemy, które uzasadniają rozwój narzędzia.
  - **Odbiór.** Drugi przypadek działa w buildzie. Wnioski z obu sesji zawierają wyniki według ustalonych kryteriów i uzasadnienie decyzji o skali dzielnic.

- **M3.02 · Sprawdzić podział mapy i nawigację między obszarami**
  - Potwierdzić roboczy wariant M2 na tej samej trasie i w porównywalnych warunkach. Dodać obciążenie dwóch sesji, w tym przejście granicy podczas aktywnej misji.
  - Sprawdzić wczytywanie i zwalnianie obszarów przy szybkim dojściu lub dojeździe oraz powrocie.
    - Jeśli wydanie utrwala postęp, wydzielić próbę wczytania aktywnej misji na granicy. Użyć działającego zapisu i stanu testowego M3.06. Pozostałe pomiary mogą ruszyć przed tym odbiorem.
    - Sprawdzić ciągłość dróg, chodników, nawigacji, oświetlenia i dźwięku na granicach.
    - Sprawdzić pamięć, opóźnienia wczytywania i zachowanie aktywnych misji na granicy.
    - Przed próbą ustalić liczbę cykli przejścia tam i z powrotem z aktywną misją oraz dopuszczalny przyrost pamięci i liczby obiektów po powrocie. Zmierzyć pierwszy i ostatni cykl w porównywalnym stanie.
  - Przygotować kontrolę błędnych połączeń i brakujących referencji, jeśli próba wykazała powtarzalny problem.
    - Zapisać niezależne zmiany dwóch obszarów w oddzielnych checkoutach tej samej rewizji. Próbę może wykonać jedna osoba. Po integracji sprawdzić oba efekty w mapie i listę zmodyfikowanych współdzielonych pakietów.
    - Gdy podział wymaga zmiany, utworzyć zadania migracji i ponownej próby, obejmującej aktywną misję, nawigację i niezależny zapis zmian. Są poprzednikami zależnych dzielnic.
  - **Odbiór.** Potwierdzony podział działa w budżecie dla przewidzianych sposobów poruszania. Jeśli powstało zadanie migracji, nowe dzielnice czekają na odbiór powtórnej próby.

- **M3.03 · Ustalić granice systemów i kontrakty danych**
  - Opisać, który system odpowiada za postać, pojazd, zdarzenie, misję i utrwalony stan świata.
  - Ustalić stabilne identyfikatory zawartości oraz sposób zgłaszania zmian stanu i błędów.
    - Zdefiniować zakres unikalności identyfikatorów sesji oraz utrwalanych obiektów. Sprawdzić, czy reguła działa po duplikacji lub ponownym załadowaniu obiektu.
  - Uporządkować podział C++ i Blueprintów na podstawie tego, kto zmienia dane i jak da się je sprawdzać.
  - Sprawdzić współdziałanie systemów na obu przypadkach użycia przed zmianą ich wspólnych interfejsów.
  - **Odbiór.** Granice i zależności są zapisane. Obie sesje przechodzą regresję po każdej zatwierdzonej zmianie wspólnych interfejsów.

- **M3.04 · Rozwinąć systemy symulacji potrzebne w zatwierdzonym zakresie**
  - Jeśli zatwierdzono pojazdy, określić wspólne dane konfiguracji i zakres strojenia przykładowych klas pojazdów.
  - Jeśli zatwierdzono ruch i pieszych, sprawdzić sieć tras, skrzyżowania, przejścia, zatory i limity aktywnych obiektów.
    - Sprawdzić pojawianie się i usuwanie obiektów poza obszarem obserwacji oraz po powrocie gracza.
    - Sprawdzić priorytet obiektów misji i zachowanie przy zablokowanej trasie.
  - Jeśli zatwierdzono reakcje miasta, sprawdzić rozpoczęcie, zakończenie i przywrócenie zwykłych zachowań świata.
  - Jeśli zatwierdzono cykl dnia i nocy, sprawdzić zmiany oświetlenia i zachowań świata podczas przejścia między porami.
    - Jeśli oba systemy są aktywne, sprawdzić zmianę pory dnia podczas reakcji miasta.
  - Jeżeli zakres łączy kosztowne systemy, przed M3.09 zmierzyć ich wspólne obciążenie w pakowanym buildzie na granicy obszarów z aktywną misją. Uwzględnić reprezentatywną gęstość ruchu, jeśli jest w zakresie.
  - **Odbiór.** Wybrane systemy zachowują się poprawnie przy granicy obszaru, w zatłoczonym miejscu i w trakcie misji.

- **M3.05 · Usprawnić tworzenie misji i zawartości na podstawie prób**
  - Uogólnić wspólne elementy celów, warunków uruchomienia, dialogów i wyników, jeśli powtórzyły się w obu misjach.
  - Przygotować podgląd lub walidację danych misji, jeśli w próbach powtarzały się te same błędy.
    - Wykrywać brakujące powiązania, cele bez zakończenia, niepoprawne identyfikatory i brakujące napisy.
  - Uzupełnić reguły importu modeli, materiałów i kolizji, jeśli skrócą przygotowanie kolejnego pakietu.
  - **Odbiór.** Wynik obu prób uzasadnia rezygnację z narzędzia lub wskazuje korzyść zmierzoną na realnym zadaniu. Jeśli narzędzie powstało, obie sesje przechodzą regresję.

- **M3.06 · Ustalić format i zgodność zapisów gry**
  - Jeśli zatwierdzono trwały postęp, określić dane zapisu, moment zapisu i wersjonowanie formatu.
    - Oddzielnie odebrać zapis aktywnej misji i dane do próby granicy M3.02. Można je przekazać przed zakończeniem pozostałych prac nad zgodnością.
  - Dla trwałego postępu obsłużyć brakujący i uszkodzony zapis, przerwanie podmiany pliku oraz zapis z nieobsługiwanej wersji.
  - Dla zatwierdzonych danych sprawdzić przejście między obsługiwanymi wersjami.
    - Dla trwałego postępu przygotować zapisy z początku gry, aktywnej misji i ukończonego wątku do kolejnych regresji.
    - Dla trwałego postępu sprawdzić wczytanie po przeniesieniu lub usunięciu obiektu i wykrywanie konfliktów identyfikatorów po zduplikowaniu zawartości.
    - Przy zastąpieniu obiektu określić, jak nowa wersja rozpoznaje poprzedni identyfikator. Przy usunięciu obiektu potrzebnego aktywnej misji sprawdzić kontynuację albo powrót do ustalonego punktu bez utraty wcześniejszego postępu.
    - Chronić identyfikatory występujące w zapisach wspieranych wersji. Zastąpienie obiektu wymaga jawnej migracji. Sprawdzić, czy starszy zapis nie przypisuje stanu nowemu obiektowi z celowo ponownie użytym identyfikatorem.
  - Dla utrwalanych ustawień sprawdzić wartości domyślne, zapis i odczyt po aktualizacji. Punkty kontrolne sprawdzić niezależnie w bieżącej sesji, jeśli są w zakresie.
  - **Odbiór.** Zatwierdzone dane przechodzą przypisane im próby. Błąd nie niszczy ostatniego poprawnego zapisu, jeśli wydanie utrwala postęp.

- **M3.07 · Przygotować kontrole integracji**
  - Wybrać automatyczne kontrole kodu, map, assetów i danych misji według obserwacji z M2 i M3.
  - Rozszerzyć punkty wejścia M0.04 o kontrole integracji. Z czystego checkoutu powtórzyć kompilację i pakowanie, uruchomić obie sesje i pomiar na trasie referencyjnej.
  - Ustalić krótki zestaw prób dla każdej zmiany i pełny zestaw dla zintegrowanej partii M4. Zmierzyć koszt czasowy obu zestawów i zapisać zmiany wyzwalające odpowiednie próby pakowanego builda. Proces może działać lokalnie lub zdalnie zależnie od wyniku M0.
    - Ustalić kontrole wymagane na połączonej rewizji. Walidacja danych i zależności pakowania obejmuje faktyczny wynik integracji, także gdy oba pakiety przechodziły próby osobno.
    - Dla każdej kontroli rozróżnić powodzenie, błąd, przerwanie i uzasadnione pominięcie próby warunkowej. Sprawdzić na błędnych danych i przerwanym uruchomieniu, że wynik nie jest zgłaszany jako poprawny.
    - W próbie kontrolowanej zatrzymać krok bez zakończenia. Zweryfikować limit M0.04, zwolnienie stanowiska i brak ponownego użycia starego raportu.
    - Przygotować próbę ładowania nowej i zmienionej zawartości z pakowanego builda. Zasymulować brak zależności dynamicznej w istniejącej misji i potwierdzić błąd blokujący odbiór.
    - Sprawdzać unikalność identyfikatorów we wszystkich integrowanych danych z aktywnych kategorii M3.03. Potwierdzić, że kolizja między dwoma poprawnymi osobno pakietami blokuje odbiór.
    - Jeśli gra utrwala postęp, uwzględnić rejestr identyfikatorów chronionych z M3.06. Sprawdzić, że przyjęcie danych bez wymaganej migracji jest blokowane.
  - **Odbiór.** Każdą próbę można ponowić dla konkretnej rewizji lub builda. Logi, raport i identyfikator wersji są powiązane.

- **M3.08 · Zweryfikować autonomię Codexa na pakiecie produkcyjnym**
  - Zlecić Codexowi wykonanie typowego pakietu produkcyjnego w zakresie ustalonych uprawnień i ustalić oczekiwany efekt w buildzie.
    - Co najmniej jedną próbę zacząć od odtworzenia konfiguracji integracji lub skryptu według M0.06. Sprawdzić, czy sama edycja działa bez ustawień stanowiska autora.
    - Jeśli produkcja ma polegać na edycji map albo Blueprintów przez agenta, próba obejmuje reprezentatywny plik binarny i jego zależności.
    - Przerwać i wznowić pracę w oddzielnej sesji. Porównać listę zmienionych pakietów z oczekiwaną i odebrać wynik ze świeżego checkoutu.
    - Dla wieloplikowej zmiany przerwać próbę po zapisaniu części pakietów. Codex ma wykryć niepełny stan, dokończyć zmianę lub wrócić do spójnej wersji i potwierdzić wynik w pakowanym buildzie.
    - Jeśli plan przewiduje równoczesną pracę przy współdzielonych assetach, przećwiczyć kolizję edycji tego samego pakietu binarnego po wznowieniu zadania. Obie wersje muszą pozostać dostępne do rozstrzygnięcia, a konflikt musi być widoczny przed integracją.
    - Wskazać momenty przejęcia pracy i właściciela kroków wymagających pomocy człowieka.
    - Na rolach przewidzianych w produkcji potwierdzić ograniczenia dostępu z M0.05, w tym przy publikowaniu buildów, jeśli plan obejmuje udział agenta.
    - Osobno zmierzyć czas wykonania, interwencji, ręcznych poprawek i odbioru. Przypisać poziom autonomii do faktycznie sprawdzonych typów zadań.
    - Dla odrębnych, kosztownych trybów pracy w M4 wykonać osobne próby. Typ pracy bez potwierdzenia ma przypisanego wykonawcę czynności wymagających człowieka, dopóki próba go nie obejmie.
    - Dla każdego trybu, którego wynik wpływa na prognozę, utworzyć podzadanie odbioru. Powiązać je z odblokowywanymi pakietami i osobą przejmującą wymagane czynności ręczne.
    - Jeśli prognoza zakłada równoległą pracę agentów, zmierzyć dwa reprezentatywne pakiety od przypisania do wspólnego odbioru na planowanym stanowisku. Uwzględnić oczekiwanie na edytor, build i odbiór człowieka. Do uzyskania wyniku kalkulować te prace sekwencyjnie.
    - Jeśli prognoza zakłada równoległe buildy, przerwać jeden podczas działania drugiego. Potwierdzić oddzielne logi i artefakty oraz poprawne zakończenie niezależnego buildu po sprzątnięciu przerwanej próby.
  - **Odbiór.** Powtarzalne rodzaje pracy w M4 mają sposób przekazania i odbioru oparty na próbie, z osobnym wykonawcą dla kroków wymagających człowieka.

- **M3.09 · Zatwierdzić skalę i plan produkcji M4**
  - Wydzielić podzadania na dowód sprzętowy każdej platformy, gotowość kanału, założenia zakresu i prognozę nakładu. Każde ma własny wynik i osobę odbierającą. Decyzja M3.09 korzysta z ich wyników.
  - Na podstawie prób zatwierdzić platformy potrzebne w produkcji, dostęp do sprzętu, budżet techniczny i sposób pakowania. Sprawdzić wymagania rozważanego kanału wydania, które zmieniają zawartość lub interfejs.
    - Dla każdej platformy ustalić roboczą konfigurację minimalną oraz progi, które wstrzymują integrację pakietów M4.
      - Ustalić, jakie zmiany wymagają regresji na wszystkich dotkniętych platformach oraz które pomiary trzeba powtórzyć dla każdej konfiguracji minimalnej przy odbiorze M4.13.
      - Przy każdym progu zapisać konfigurację pakowanego builda, trasę, metodę liczenia skoków czasu klatki, liczbę prób i sposób rozstrzygania wyników blisko granicy. Uwzględnić wymagania wydania, których późniejsza zmiana wymagałaby kosztownej przeróbki.
      - Dla kosztów rosnących wraz z zawartością określić sposób pomiaru czasu cooka, rozmiaru instalacji i startu gry. Użyć roboczej zawartości o reprezentatywnej skali lub ustalić pomiary po każdej partii M4.
    - Dla każdej zatwierdzanej platformy przygotować pakiet z czystej rewizji na przewidzianym stanowisku według M3.07. Na tym pakiecie wykonać najcięższą zatwierdzoną próbę na roboczym minimum. Dla łączonej symulacji użyć scenariusza M3.04. Zapisać rewizję, pakiet, platformę, sprzęt, ustawienia, trasę, wynik i progi.
      - Bez wymaganego wyniku platforma pozostaje warunkowa. Zapisać datę decyzji, wymagany pomiar i pakiety, których produkcja czeka na potwierdzenie.
    - Sprawdzić wzrost pamięci danych świata wraz z liczbą obszarów i zależności. Wykonać tanią próbę z dodatkową roboczą zawartością lub wyznaczyć próg dla M4.14 i zapisać, jaki zakres ograniczamy po przekroczeniu.
    - Sprawdzić terminy dostępu do kanału, ewentualnej certyfikacji i oceny wiekowej. Dla wymaganych zgłoszeń wpisać do harmonogramu złożenie pakietu, uzyskanie decyzji i czas na poprawkę oraz ponowne zgłoszenie. Jeżeli kanał ma osobny proces podpisania lub instalacji, przeprowadzić próbę na dostępnym kanale testowym.
    - Sprawdzić, czy obrany sposób dystrybucji wymaga wcześniejszej strony sklepu, dema lub zgłoszenia do wydarzenia. Jeśli dotyczy, utworzyć zadanie z terminem, materiałami i wymaganym buildem.
    - Gdy brakuje dostępu do wymaganego kanału, zapisać datę graniczną, wymagany dowód, zablokowane pakiety i wariant zakresu na wypadek przekroczenia terminu.
  - Rozpisać główną ścieżkę gry. Powiązać kolejność misji i odblokowań z dzielnicami, systemami oraz warunkami wejścia.
    - Ustalić roboczą długość odcinków, odstępy między istotnymi decyzjami i częstotliwość użycia głównych mechanik. Na tej podstawie oszacować zawartość, a w M4.02 potwierdzić albo skorygować założenia z graczami.
    - Potwierdzić minimalną swobodę z M1.01 i powiązać ją z roboczą próbą M4.02.
    - Wskazać wynik próby głównego wyróżnika z M1.01. Jeśli dotychczasowe sesje go nie pokazują, odebrać próbę przed zatwierdzeniem podstawowego zakresu.
    - Dla mechanik z warunkiem porażki opisać, kiedy gracz poznaje zasadę, kiedy ma ją zastosować bez podpowiedzi i gdzie rośnie trudność.
    - Przed zatwierdzeniem podstawowego zakresu rozstrzygnąć próby funkcji, których niepowodzenie zmieniłoby główną pętlę, platformę, budżet lub liczbę pakietów. Dla innych otwartych prób zapisać termin, poprzedników i wariant ograniczenia zakresu.
    - Dla każdej funkcji wydania wskazać, co pokrywa jej dotychczasowy dowód i czego wymaga docelowy zakres. Przypisać pozostałe wdrożenie, integrację i odbiór do konkretnych issues produkcyjnych. Pakiet potrzebujący funkcji rusza po odbiorze wymaganego wejścia. Dotyczy to również spięcia trwałego postępu między misjami, wolną grą i menu, jeżeli zatwierdzono tę funkcję.
  - Zatwierdzić na podstawie M2.07 zakres dostępności, ustawień, urządzeń wejściowych, języków, napisów i nagrań dla całego wydania. Dla pozycji wskazać nakład, dowód odbioru i zależne pakiety M4.10–M4.12.
    - Dla każdej pozostawionej decyzji zapisać termin, pakiet, który na nią czeka, i koszt obu rozważanych wariantów.
  - Oszacować zakres produkcji według wyników M2 i M3. Uwzględnić nakład na dzielnice, misje, assety, integrację, regresje, poprawki i pracę człowieka przy odbiorze.
    - Oszacować typowy i trudny pakiet oraz rezerwę na poprawki. Ująć przewidziane nagrania, lokalizację, testy zewnętrzne, alfę, betę, premierę i pierwszy okres utrzymania.
    - Wskazać kosztowne rodzaje pracy, dla których prognoza opiera się na zmierzonych pakietach, oraz rodzaje wymagające pomiaru pierwszego wykończonego pakietu.
    - Porównać całość z czasem i budżetem z M0. Wskazać, które elementy ograniczamy najpierw przy przekroczeniu.
    - Oszacować rozmiar wersjonowanych źródeł, transfer i limity LFS oraz czas czystego checkoutu na podstawie pakietów próbnych i częstotliwości czystych buildów.
    - Wybrać zakres podstawowy i opcjonalny oraz kolejność integracji. Powiązać pakiety z wymaganymi poprzednikami.
    - Rozłożyć zależne pakiety na kalendarzu według dostępności wykonawców, osób odbierających pracę i sprzętu. Uwzględnić czynności wymagające człowieka z M3.08 oraz rezerwę na próby i akceptacje zewnętrzne.
  - Ustalić, kiedy prototypujemy nowe zachowanie, kto je odbiera i jak włączamy je do pełnego builda.
  - Rozpisać pierwsze gotowe do wykonania issues produkcyjne. Przypisać właścicieli i zależności.
    - Dobrać pierwszą partię M4.14 tak, aby sprawdzała założenia prognozy. Zapisać, jakie typy roboczych dzielnic, misji, mechanik i zależności reprezentuje oraz czego koszt nadal pozostaje szacunkiem.
    - Wskazać scenę, gotowe zachowania i pomiary wymagane już w M4.14 oraz moment powtórki z symulacją na docelowych trasach. Wskazać listę dalszych pakietów, których koszt, grywalność lub wydajność zależą od wyniku pierwszej partii.
    - Dla każdej zatwierdzonej kategorii utrwalania określić w M4.14 wymagany stan i próbę albo wskazać późniejszą partię, która ma je odebrać. Podać przyczynę odroczenia i zależne zadania.
    - Wskazać wykończenia wrażliwe na zmianę układu tras. Rozpocząć je po zaliczonym pomiarze symulacji na reprezentatywnym odcinku docelowej sieci M4.04 i M4.08, zanim powstanie kosztowna oprawa zależnych miejsc.
    - Jeśli nieznany koszt wykończenia mógłby zmienić zakres podstawowy, zatwierdzić limit na pierwszą partię i próbkę M4.16. Określić wejścia próbki i pakiety, których nie zlecamy przed przeliczeniem zakresu w M4.14.
  - Rozliczyć limit M3 zapisany przy M2.08. Jeśli otwarte próby blokują produkcję, zakończyć je lub zaproponować mniejszy zakres, powtórzyć wymagane próby i przeliczyć nakład.
    - Jeśli nawet ograniczony wykonalny zakres traci główną pętlę lub minimum swobody z M1.01, wstrzymać produkcję lub wrócić do zmiany wizji i powtórnej próby.
  - **Odbiór.** Zapisano decyzję i jej podstawę. Zatwierdzenie M4 wymaga zaliczenia prób wybranego zakresu oraz planu łączącego główną ścieżkę, platformy, dostępny nakład i kolejność pakietów.

## M4 · Produkcja zatwierdzonej zawartości

- **M4.01 · Rozpisać pozostałe pakiety produkcyjne**
  - Uzupełniać issues startowe z M3 w miarę gotowości zależności dla dzielnic, misji i zestawów.
    - Każdy współdzielony model, pojazd i rekwizyt ma jedno issue dotyczące jego produkcji. Misja lub dzielnica osobno sprawdza jego użycie.
    - Przed zamówieniem nagrań albo dodaniem zewnętrznych assetów potwierdzić możliwość użycia materiałów na planowanych platformach i w kanałach dystrybucji. Wynik przypisać do źródłowego issue przed rozpoczęciem zależnej pracy.
    - Dla assetów przeznaczonych do ponownego importu podać wersję i sposób pobrania źródła oraz ustawienia eksportu i importu.
    - Zachować oznaczenie elementów opcjonalnych i kolejność prac uzgodnioną w M3.
  - Zweryfikować zależności pakietu i kryteria jego odbioru przed rozpoczęciem prac.
  - Dla każdej partii utworzyć issue odbioru według M4.03 i podpiąć jej pakiety. Przypisać osobę odbierającą, integrowaną rewizję i miejsce raportu o wspólnych blokerach.
  - **Odbiór.** Gotowe pakiety mają właścicieli, konkretne zależności i własne próby w buildzie.

- **M4.14 · Odebrać pierwszą partię roboczą i zaktualizować prognozę**
  - Zintegrować pierwsze dzielnice i misje. Sprawdzić z graczami start, tempo kilku zadań i orientację.
    - Użyć składu partii zatwierdzonego w M3.09. Podpiąć odbiory właściwych roboczych dzielnic, misji, mechanik i interfejsu oraz wymagane kontrole M4.03.
    - Sprawdzić tylko przydzielone tej partii kategorie utrwalania, ze wskazanym stanem wejścia. Dla pozostałych potwierdzić odbiór, który je przejmie, i prace czekające na ten wynik.
    - Ustalić wymagane minimum prób, profil uczestników i regułę ponowienia. Osoby oceniające start i orientację powinny widzieć build po raz pierwszy.
  - Porównać rzeczywisty czas produkcji, integracji i pomiary z prognozą M3.09. Przy przekroczeniu przeliczyć nakład i zastosować kolejność ograniczeń.
    - Dołączyć wynik M4.16, jeśli został wymagany. Jeśli w M3.09 odłożono próbę wzrostu pamięci danych, wykonać ją teraz i zastosować uzgodnioną regułę decyzji.
    - Wskazać, które pozycje prognozy nadal są tylko szacunkiem. Przy niezaliczonym kryterium grywalności poprawić albo zmienić zakres i powtórzyć próbę przed zleceniem zależnej partii. Zapisać, które prace mogą ruszyć niezależnie.
  - **Odbiór.** Wskazano sprawdzony build pierwszej partii, zaliczone próby graczy i aktualną prognozę. Zatwierdzono zakres zależnych partii roboczych.

- **M4.16 · Zmierzyć koszt wczesnej próbki docelowej jakości**
  - Uruchomić po zatwierdzeniu limitu w M3.09, jeśli potrzebna jest wycena przed zleceniem następnych partii. Wybrać oddzielną scenę testową, lokację M2 lub roboczy wycinek z pierwszej partii. Ustalić oczekiwany efekt i źródła materiałów dostępne przed odbiorem M4.14.
  - Wykonać wyłącznie próbkę potrzebną do wyceny. Zadanie może ruszyć przed M4.02 na podstawie własnych wejść i nie odblokowuje wykończenia całej dzielnicy ani misji.
  - **Odbiór.** Przekazać do M4.14 wynik na wskazanym buildzie, koszt i granice jego zastosowania. Jeśli wynik wykracza poza limit, zapisać wpływ na zakres przed zleceniem zależnych partii.

- **M4.02 · Przejść główną ścieżkę w roboczym buildzie**
  - **Pełna robocza ścieżka po M4.14**
    - Złożyć całą ścieżkę do finału z roboczą geometrią, tymczasowymi dialogami i zastępczymi assetami.
    - Sprawdzić kolejność odblokowań i przejścia między obszarami przed zamówieniem końcowych nagrań i wykończeniem zależnych lokacji.
    - Przed próbą ustalić akceptowalne tempo, powtarzalność i czytelność odblokowań. Wykonać pełne przejście integracyjne. Z uczestnikami spoza zespołu sprawdzić początek, środek, zakończenie i powrót po eksploracji. Dla dłuższej gry można użyć odcinków z odtwarzalnym stanem wejścia. Gdy pytanie dotyczy ciągłości tempa lub fabuły, przeprowadzić pełne sesje graczy.
    - Ustalić minimum ważnych sesji dla istotnych wariantów, dobór graczy i regułę powtórki przy rozbieżnych wynikach.
    - Przed sesją sprawdzić roboczą mapę, informacje o celu i porażce, sygnały odblokowań oraz wskazówki orientacyjne z M4.11. W raporcie rozróżnić problemy interfejsu od problemów wynikających z układu miasta lub misji.
    - W kluczowych scenach zapytać po próbie, dlaczego gracz podjął dane zadanie i co według niego zmieniło ukończenie. Zweryfikować rozumienie fabuły przed zamknięciem tekstów i nagrań.
    - Jeżeli wybory wpływają na późniejsze dialogi lub dostęp do misji, sprawdzić na roboczym buildzie istotne rozgałęzienia i kombinacje przed zamknięciem dotkniętych tekstów i skryptów. Zapisać oczekiwany stan i użyć tej listy w M5.01.
    - Jeżeli pętla zależy od symulacji lub aktywności poza misjami, dołączyć robocze zachowania z M4.08 lub M4.09. Sprawdzić, jak swobodne działanie zmienia stan świata i wpływa na misję po powrocie.
    - Sprawdzić minimalną swobodę z M1.01 oraz przebieg nauki z M3.09. W mechanikach z porażką gracz powinien rozpoznać jej przyczynę i użyć poznanej zasady w późniejszym zadaniu.
    - Dla istotnych porażek ustalić akceptowalny czas i nakład powrotu do decyzji. Obserwować samodzielne ponowienie i sprawdzić, czy dojazd lub powtarzanie scen nie zniechęcają do dalszej próby. Zachować kryterium w becie, gdy dotyczy głównej pętli.
    - Jeśli eksploracja jest celem wydania, przeprowadzić próbę w kilku roboczych obszarach bez listy celów. Ustalić przed próbą akceptowalny czas między wyborami gracza i jakie dobrowolne zboczenia z trasy potwierdzą gęstość zawartości.
    - Przy niespełnieniu kryterium poprawić przyczynę lub jawnie skorygować zakres i powtórzyć odpowiednią część próby z graczami.
  - Zapisać oddzielny wynik względem odbioru pierwszej partii i wskazać, które pakiety mogą przejść do wykończenia.
  - **Odbiór.** Główna ścieżka działa do finału i spełnia ustalone kryteria grywalności w roboczym buildzie. Wykończenie pakietu dotkniętego niepowodzeniem czeka na zaliczoną próbę po korekcie.

- **M4.03 · Prowadzić regresję przy integracji pakietów**
  - Przy każdej zmianie wykonać krótki zestaw M3.07. Zmiana wczytywania świata, nawigacji, danych misji lub trwałego stanu uruchamia odpowiednią próbę pakowanego builda.
    - Po zmianie odblokowań sprawdzić dotknięte przejścia między misjami na połączonej rewizji, w tym dostęp do następnego celu.
    - Dla zmian wpływających na platformy uruchomić przypisane próby na dotkniętych konfiguracjach z M3.09. W protokole partii wskazać platformę każdej wymaganej próby.
    - Po zmianie wczytywania świata powtórzyć próbę wielokrotnego przejścia M3.02 i porównać wzrost pamięci oraz liczbę obiektów.
  - Przy odbiorze partii uruchomić w pakowanym buildzie reprezentatywną sesję, przejście między obszarami i próby utrwalania przypisane tej partii. W pełnym buildzie wymagane są wszystkie aktywne kategorie.
    - Dla pierwszej partii użyć sceny i zakresu zachowań ustalonych w M3.09. Powtórzyć pomiar po podłączeniu docelowych tras w terminie wskazanym w planie.
    - Sprawdzić połączoną rewizję. Jeśli po próbie zmieniła się podstawa integracji, ponowić na nowej rewizji wymagane kontrole M3.07, na które zmiana może wpłynąć.
    - Dla integrowanych danych uruchomić kontrolę unikalności identyfikatorów M3.07 przed przyjęciem partii.
    - W konfiguracji pakowania planowanej do wydania sprawdzić ładowanie nowych map i misji oraz dotkniętej istniejącej zawartości. Zmiana współdzielonego zasobu, dynamicznych referencji, wtyczki lub reguł cooka uruchamia próbę M3.07 dla zależnych map, misji i obiektów.
    - Przy odbiorze partii i zmianach wpływających na wydajność zmierzyć trasę referencyjną oraz najcięższy zatwierdzony zestaw systemów na granicy obszarów.
    - Rejestrować czas cooka, rozmiar instalacji i czas startu zgodnie z planem pomiarów M3.09. Gdy trend grozi przekroczeniem budżetu, ocenić zakres następnej partii przed jej integracją.
    - Porównać wynik z progami M3. Po przekroczeniu wstrzymać zależną integrację do uzyskania poprawki lub zatwierdzenia zmiany zakresu.
  - Przy odbiorze partii porównać nakład wykonania, integracji, poprawek i odbioru z prognozą. Gdy pozostały nakład przekracza budżet, zastosować kolejność ograniczeń M3.09 przed zleceniem zależnej partii.
  - **Odbiór.** Każda przyjęta partia ma identyfikator builda, wyniki regresji i pomiarów. Nieudana, przerwana lub pominięta wymagana próba wstrzymuje odbiór do czasu wykonania udanej próby na właściwym buildzie. Pominięcia prób warunkowych zapisujemy osobno.

- **M4.15 · Zmierzyć nakład pierwszych wykończonych pakietów**
  - Po M4.02 dla każdego kosztownego rodzaju pracy bez wiarygodnego pomiaru utworzyć podzadanie na pierwszy wykończony pakiet. Uwzględnić czas oprawy, integracji, poprawek i odbioru przez człowieka.
    - Przy zleceniu zapisać kolejne pakiety tego rodzaju, które czekają na wynik, oraz te, które mają już niezależną podstawę kosztową i mogą ruszyć.
  - Przeliczyć pozostały nakład po odebraniu każdego takiego pakietu. Jeśli szacunek przekracza budżet, zastosować kolejność ograniczeń z M3.09.
  - **Odbiór.** Zwiększenie tempa wykończenia w danym rodzaju pracy zależy od odbioru jego pakietu i aktualnego oszacowania. Cykliczne kontrole z M4.03 pozostają częścią odbioru kolejnych partii.

- **M4.04 · Wyprodukować zatwierdzone dzielnice (epik)**
  - Dla każdej dzielnicy opisać funkcję, charakter, główne punkty orientacyjne, plan ulic i miejsca wykorzystywane przez misje.
  - Dla każdej dzielnicy przygotować osobne issue z odrębnym odbiorem roboczego układu i wykończenia.
  - **Robocza dzielnica do M4.02**
    - Zbudować roboczy układ ulic, chodników, przejść, wejść, wnętrz i połączeń z sąsiednimi obszarami.
    - Sprawdzić punkty startowe, dostęp do celów misji, granice eksploracji i miejsca utknięcia.
    - W dzielnicy przeznaczonej do eksploracji przed wykończeniem sprawdzić z graczami, czy zauważają punkt zainteresowania i potrafią wrócić do własnego celu. Użyć roboczych sygnałów i poprawić układ przed wykończeniem, jeśli kryterium nie jest spełnione.
    - **M4.04a · Trasy robocze.** Jeśli robocza ścieżka wymaga symulacji, dostarczyć minimalną sieć tras pieszych lub pojazdów z połączeniami potrzebnymi w M4.08a.
    - Przekazać pakiet roboczy do M4.02 po sprawdzeniu dojść i celów powiązanych misji.
  - **Wykończenie po odbiorze M4.02**
    - **M4.04b · Odcinek docelowych połączeń.** Na odcinku z M3.09 odebrać układ i połączenia na geometrii roboczej. Przekazać odcinek do M4.08b przed kosztowną oprawą.
    - Przygotować budynki, materiały, wyposażenie ulic, oznakowanie, detale i oświetlenie.
      - Dodać kolizje i poziomy szczegółowości. Sprawdzić pojawianie się obiektów przy ruchu kamery.
      - Sprawdzić pochodzenie każdego zestawu assetów i przypisać pliki źródłowe.
    - **M4.04c · Pełna sieć.** Odebrać lokację i sieć tras ze sprawdzoną nawigacją i kolizją. Przekazać je do M4.06 i M4.08c przed podłączeniem misji i finalnej symulacji.
    - Podłączyć dźwięk przestrzenny. Wspólną próbę dzielnicy z działającą misją lub symulacją wykonać po ich integracji w M4.03.
    - Przejść granice z sąsiednimi obszarami w obie strony. Powtórzyć próbę pojazdem, jeśli dzielnica obejmuje jazdę.
    - Na trasie referencyjnej ocenić skalę, oświetlenie, gęstość detali i czytelność punktów orientacyjnych względem wzorców M2.04.
    - W dzielnicach przeznaczonych do eksploracji powtórzyć próbę z docelową oprawą po integracji.
  - **Odbiór.** Dzielnica ma własny wynik sprawdzenia dojść, audio, nawigacji i wydajności. Wynik wspólnej próby po integracji zapisuje M4.03.

- **M4.05 · Rozpisać fabułę główną i zatwierdzone wątki poboczne**
  - Rozwinąć zatwierdzoną ścieżkę M3 o scenariusze, cele scen i relacje postaci. Sprawdzić je względem ustalonej kolejności odblokowań.
  - Przygotować opisy postaci i dzielnic, aby dialogi i zdarzenia były spójne między misjami.
  - Zdefiniować, które decyzje zmieniają przebieg zadania, które wpływają na miasto i jakie informacje gracz otrzymuje o ich skutkach.
  - Rozpisać dialogi, napisy, rozmowy opcjonalne i krótkie komunikaty używane w trakcie gry.
    - Sprawdzić ciągłość wątków po odegraniu scen w różnej kolejności.
    - Przekazać robocze scenariusze i teksty zastępcze do M4.02. Końcowe teksty przekazać do nagrań i lokalizacji po odbiorze roboczej ścieżki i zatwierdzeniu kontekstu.
  - **Odbiór.** Każda misja ma miejsce w historii, wymagania wejścia i spójny stan po zakończeniu.

- **M4.06 · Wyprodukować i zweryfikować każdą zatwierdzoną misję (epik)**
  - Dla każdej misji utworzyć osobne issue. Budowę roboczą uruchamia odebrany scenariusz roboczy M4.05. Wykończenie zależy od odbioru M4.02 i pakietów finalnych.
  - **Robocza misja do M4.02**
    - Rozpisać cele, interakcje, dialogi i warunki ukończenia. Jeśli w wydaniu będą punkty kontrolne, rozpisać ich stan oddzielnie od restartu misji.
    - Wdrożyć cele i zdarzenia z zamiennikami lokacji, modeli, animacji i nagrań. Sprawdzić rozpoczęcie, ukończenie i stan kolejnej misji przed przekazaniem do M4.02.
  - **Finalna misja po odbiorze M4.02**
    - Użyć odebranej lokacji z M4.04 oraz zatwierdzonych modeli, animacji i nagrań. Podłączyć zasoby i sprawdzić ich użycie w M4.03 po integracji.
    - Podłączyć HUD, napisy, nagrody i kolejne odblokowania, jeśli wynikają ze scenariusza. Zapis postępu podłączyć tylko przy zatwierdzonym trwałym postępie.
    - Sprawdzić rozpoczęcie, sukces, porażkę, restart i przerwanie. Wczytanie w nowym procesie sprawdzić tylko przy trwałym postępie.
      - Spróbować ominąć cel, wcześniej dotrzeć do kolejnej lokacji i opuścić obszar misji.
      - Sprawdzić stan powiązanych postaci, obiektów i zdarzeń po ponownym wejściu na obszar.
  - **Odbiór.** Misja działa w pakowanym buildzie, informuje o wyniku i pozostawia grę w stanie pozwalającym kontynuować.

- **M4.07 · Wyprodukować pojazdy, postacie i wyposażenie świata (epik)**
  - Podzielić zawartość na zestawy według klas pojazdów, ról postaci i zastosowania assetów.
  - Dla każdego pojazdu przygotować model, materiały, kolizję, konfigurację fizyki, animacje i dźwięki wymagane przez zatwierdzoną klasę.
    - Sprawdzić zachowanie pojazdu na trasach i nawierzchniach przewidzianych dla tej klasy.
    - Sprawdzić wejście, wyjście, kamerę i zapis stanu, jeśli dotyczy.
  - Dla postaci przygotować modele, materiały, animacje, warianty wyglądu i konfiguracje zachowań.
    - Sprawdzić przejścia między ruchem, bezczynnością, interakcją i kluczowymi animacjami.
    - Sprawdzić poprawne użycie w scenie na zbliżeniu i w większym tłumie.
  - Dla wyposażenia świata przygotować modele i materiały zgodne z zestawami modułowymi.
    - Sprawdzić odmiany, ponowny import, licencję, wydajność i zależności od pozostałych pakietów.
  - **Odbiór.** Każdy zatwierdzony zestaw ma zapis źródeł i wynik próby w mapie. Lista zestawów wskazuje zamknięte zadania poszczególnych elementów lub zatwierdzoną zmianę zakresu.

- **M4.08 · Rozmieścić i zrównoważyć działanie symulacji miejskiej**
  - **M4.08a · Robocza symulacja.** Jeśli pętla tego wymaga, użyć M4.04a i zbudować zachowania potrzebne do roboczego odbioru M4.02 lub M4.14. Przekazać działającą próbę przed właściwym odbiorem.
  - **M4.08b · Pomiar przed wykończeniem.** Użyć odcinka M4.04b i scenariusza M3.09. W pakowanym buildzie sprawdzić gęstość, zachowanie przy przejściu i najcięższą sytuację. Wynik odblokowuje wskazane pakiety oprawy.
  - **M4.08c · Finalna symulacja.** Po M4.02 wykorzystać pełną sieć M4.04c. Dopracować zachowania pieszych i pojazdów, interakcje NPC i reakcje miasta objęte zakresem. Sprawdzić wspólny efekt w M4.03.
  - Rozmieścić scenariusze zachowań odpowiadające charakterowi dzielnic. Uwzględnić pory dnia, jeśli zatwierdzono cykl dnia i nocy.
  - Sprawdzić współdziałanie systemów w miejscach i misjach objętych symulacją. Przetestować skrzyżowania i zmianę pory dnia, jeśli należą do zakresu.
    - Dla zatwierdzonych zachowań zapisać oczekiwany wynik. Przy ruchu ulicznym określić powrót do zwykłego ruchu po zatorze i zachowanie postaci potrzebnej misji w czasie blokady. Przenieść te scenariusze do M5.01.
    - Sprawdzić zachowanie po oddaleniu i powrocie gracza, podczas zatoru i przy wysokiej liczbie aktywnych postaci.
    - Jeżeli zatwierdzono policję, sprawdzić reakcję systemu po opuszczeniu dzielnicy i przerwaniu misji. Przy trwałym postępie sprawdzić również wczytanie.
  - **Odbiór.** Symulacja w zatwierdzonych scenariuszach nie blokuje głównej ścieżki ani ruchu między dzielnicami.

- **M4.09 · Zintegrować interakcje i postęp w otwartym świecie**
  - Skatalogować zatwierdzone interakcje poza misjami, miejsca ich użycia i wymagania dostępu.
    - Jeśli interakcje są potrzebne do próby M4.02, wdrożyć ich robocze warianty przed odbiorem ścieżki, korzystając z roboczych lokacji.
    - Sprawdzić wejście do dostępnych budynków, korzystanie z obiektów i powrót do eksploracji.
    - Zweryfikować spójne komunikaty dla interakcji dostępnych, aktualnie zablokowanych i już wykonanych.
  - Jeśli zatwierdzono nagrody lub odblokowania poza misjami, podłączyć przyznawanie i prezentację w UI. Dane utrwalać, jeśli należą do trwałego postępu.
    - Sprawdzić powtórzenie interakcji, restart i ponowne wejście do obszaru. Wczytanie wykonać przy trwałym postępie.
  - **Odbiór.** Gracz może wykonywać zatwierdzone działania poza misją. Ich wyniki pozostają spójne po przejściu do misji oraz przy zatwierdzonych formach wznowienia.

- **M4.10 · Przygotować docelowe audio**
  - Przygotować dźwięki otoczenia dzielnic, kroki, pojazdy, efekty, dialogi i muzykę przewidzianą w zakresie gry.
    - Użyć dialogów zastępczych do M4.02. Końcowe nagrania rozpocząć po jego odbiorze i otrzymaniu zatwierdzonych tekstów z M4.05.
    - Przed zamówieniem sesji odebrać skrypt w M4.12 dla każdego nagrywanego języka, również przy jednej wersji głosowej. Zapisać wersję skryptu wraz z nagraniem.
  - Oddzielnie odebrać pliki audio gotowe do integracji. Zweryfikować kompletność, format, identyfikatory i przypisanie do wersji skryptu. Przekazać pliki do M4.06 bez czekania na odbiór miksu w misji.
    - Ustalić priorytety dźwięków, przejścia między scenami i poziomy głośności.
    - Po integracji w M4.06 sprawdzić w M4.03 czytelność głosów w pojazdach, tłumie i scenach ulicznych w zakresie gry.
  - **Odbiór.** Ścieżki audio grają w odpowiednich sytuacjach i nie zagłuszają ważnych sygnałów ani dialogów.

- **M4.11 · Dokończyć interfejs i ustawienia**
  - Do prób M4.14 i M4.02 dostarczyć roboczy HUD, mapę lub sygnały orientacji, informacje o celu, wyniku i porażce oraz komunikaty o odblokowaniu. Zakres wyznaczają pytania każdej próby.
  - Po odbiorze roboczej ścieżki dokończyć HUD, mapę, menu i zatwierdzone ustawienia. Ekrany zapisu i wczytywania przygotować, jeśli wymaga ich zatwierdzony sposób utrwalania postępu.
    - Sprawdzić nawigację obsługiwanymi urządzeniami i zachowanie po zmianie urządzenia.
    - Sprawdzić czytelność przy różnych rozdzielczościach, rozmiarach tekstu i konfigurowalnych ustawieniach.
  - **Odbiór.** Ekrany da się obsłużyć przewidzianymi urządzeniami i w zatwierdzonych konfiguracjach.

- **M4.12 · Przygotować lokalizację i napisy**
  - **Teksty i skrypty do nagrań**
    - Przygotować teksty do zatwierdzonych wersji językowych.
    - Dla każdego języka rozliczyć wszystkie zatwierdzone identyfikatory tekstów, w tym wątki poboczne i teksty pojawiające się warunkowo.
    - Użyć ustalonych identyfikatorów tekstów, utrzymać słownik nazw i przekazać kontekst scen.
    - Dla każdego nagrywanego języka utworzyć podzadanie odbioru skryptu. Jego zaliczenie odblokowuje nagranie M4.10.
  - **Napisy w buildzie**
    - Sprawdzić napisy w grze, zawijanie tekstu i brakujące tłumaczenia.
    - Po integracji nagrań M4.10 w osobnym podzadaniu sprawdzić zgodność napisów z głosem.
  - **Odbiór.** Rejestr potwierdza kompletność zatwierdzonych identyfikatorów w każdym języku. Próby w buildzie potwierdzają kontekst, czytelność i zgodność z nagraniami.

- **M4.13 · Zintegrować zawartość i odebrać M4**
  - Zbudować pełną wersję z zatwierdzonymi dzielnicami, misjami, assetami i systemami.
    - Porównać zakres wszystkich funkcji z decyzją M3.09. Sprawdzić zamknięcie pozostałych zadań wdrożenia i integracji przed uznaniem funkcji za gotową.
  - Przejść główną ścieżkę od rozpoczęcia do zakończenia. Sprawdzić przejścia między dzielnicami i odblokowywanie treści.
  - Wykonać pomiary pełnego builda na każdej zatwierdzonej konfiguracji minimalnej zgodnie z M3.09.
  - Zapisać braki i znane problemy z miejscem odtworzenia oraz właścicielem zadania.
  - Jeżeli pełny build przekracza budżet, poprawić przyczynę lub wprowadzić zatwierdzoną zmianę zakresu. Powtórzyć pomiary na zintegrowanym artefakcie i porównać wynik z aktualnymi progami przed rozpoczęciem alfy.
  - **Odbiór.** Wszystkie zatwierdzone pakiety są w jednym buildzie, pełna ścieżka i regresja działają, a wynik końcowych pomiarów mieści się w zatwierdzonym budżecie.

## M5 · Alfa

- **M5.01 · Przygotować macierz testów alfy**
  - Wybrać scenariusze od ukończenia głównej ścieżki po ruch między dzielnicami, misje poboczne i powrót do rozgrywki.
  - Przypisać konfiguracje sprzętu, urządzenia i ustawienia. Wersje zapisu przypisać tylko do aktywnych prób trwałego postępu.
  - Przygotować dane startowe dla przypadków wymagających konkretnej misji, pory dnia lub stanu świata.
    - Dla istotnego odchylenia wskazać oczekiwaną drogę dalszej gry, wznowienia lub ponowienia zadania. Brak wszystkich przewidzianych dróg wyjścia jest blokerem.
    - Jeśli decyzje gracza zmieniają późniejsze zadania lub stan świata, uwzględnić pary decyzja i oczekiwany skutek. Zapisać wpływ na odblokowania, reakcje świata i możliwość kontynuacji.
    - Dla decyzji, które zbiegają się w tej samej misji, na tej samej postaci lub w tym samym odblokowaniu, zapisać istotne kombinacje i oczekiwany wspólny stan. Powtórzyć te próby w M5.02.
    - Oznaczyć próby ręczne, automatyczne i wymagające konkretnego środowiska.
    - Ustalić czas i trasy prób długiej sesji oraz kryteria przerwania testu.
  - **Odbiór.** Każda istotna ścieżka ma warunki wejścia, oczekiwany wynik i powtarzalny sposób wykonania.

- **M5.02 · Sprawdzić kompletność gry i jej stany brzegowe**
  - Przejść pełną grę od nowej sesji. Sprawdzić osobno punkty kontrolne oraz wczytanie w nowym procesie w kluczowych zadaniach, jeśli zatwierdzono odpowiednie kategorie.
  - Przetestować alternatywne kolejności działań, przerwanie misji i ponowienie zadania.
    - Dla zatwierdzonych wyborów fabularnych sprawdzić oczekiwany skutek w późniejszej misji lub obszarze oraz możliwość dalszego przejścia z obu stanów.
    - Jeżeli trwałe zapisy są w zakresie, powtórzyć przypadek zmienionego lub usuniętego obiektu z M3.06 na zintegrowanej zawartości.
  - Sprawdzić brakujących aktorów, ponowne wykonanie interakcji, zmianę sceny podczas wczytywania i powrót z obszaru poza trasą.
  - **Odbiór.** Główną ścieżkę da się ukończyć. Z każdego sprawdzanego stanu brzegowego można kontynuować, wznowić albo powtórzyć zadanie zgodnie z macierzą M5.01.

- **M5.03 · Naprawić błędy blokujące i sprawdzić regresje**
  - Uporządkować błędy według wpływu na możliwość grania, zapis, stabilność i wydajność.
  - Dla każdego blokera ustalić minimalne kroki odtworzenia i zweryfikować poprawkę w pakowanym buildzie.
    - Przy utracie zatwierdzonych trwałych danych sprawdzić przerwany zapis i odzyskanie ostatniego poprawnego stanu.
    - Przy blokadzie misji sprawdzić zarówno właściwą kolejność, jak i przypadek prowadzący do utknięcia.
    - Przy awarii zapisać log i konfigurację, na której da się ją odtworzyć.
  - Dodać regresję automatyczną tam, gdzie scenariusz da się wiarygodnie uruchamiać powtórnie.
  - **Odbiór.** Blokery przejścia gry, uruchomienia i utraty postępu są poprawione i ponownie sprawdzone.

- **M5.04 · Zoptymalizować wydajność i sprawdzić długie sesje**
  - Zmierzyć CPU, GPU, pamięć, czas wczytywania i opóźnienia klatek na trasach referencyjnych.
    - Zebrać wyniki w zatwierdzonych scenach obciążeniowych, w tym przy przejściu między obszarami i szybkiej jeździe, jeśli ta należy do zakresu.
    - Sprawdzić wzrost pamięci i liczbę aktywnych obiektów podczas długiej sesji i powrotów do tej samej dzielnicy.
  - Określić źródła najdroższych klatek i wdrożyć poprawki w kolejności ich wpływu.
  - Powtórzyć pomiary dla tej samej konfiguracji oraz sprawdzić wpływ zmian na oprawę i zachowania NPC.
  - **Odbiór.** Wyniki po poprawkach można porównać z pomiarami bazowymi. Odchylenia mają opis i priorytet przed betą.

- **M5.05 · Odebrać alfę**
  - Wybrać build z pełną ścieżką gry. Zapisać wersję, znane problemy i wyniki aktywnych prób utrwalania stanu.
    - Na wskazanym buildzie wykonać pełne przejście. Po połączeniu poprawek powtórzyć dotknięte scenariusze, pomiary i aktywne próby utrwalania. Powiązać wyniki M5.02–M5.04 z odebraną wersją.
  - Zatwierdzić listę poprawek, obszary testów z graczami i konfiguracje do bety.
    - Przenieść najważniejsze kryteria rozgrywki z M1–M4 do prób finalnej gry. Wskazać, które wyniki są warunkiem publikacji oraz które wymagają poprawki z ponowną próbą albo jawnej zmiany zakresu.
    - Zatwierdzona w M1.01 minimalna swoboda jest warunkiem publikacji. Wskazać odpowiednią próbę w M6.01 i dowód potrzebny w M6.07.
    - W ten sam sposób przenieść obserwowalne kryterium głównego wyróżnika potwierdzonego w M3.09, jeśli należy do aktualnej wizji.
    - Dla głównej pętli zachować kryterium kosztu powtórki po porażce z M4.02 i sprawdzić je w dopracowanym buildzie.
    - Ująć w próbach tempa początek, środek i finał. Zaplanować pełne przejście lub odcinki z odtwarzalnym stanem wejścia, zależnie od długości gry.
    - Jeśli warunek wydania dotyczy tempa całej gry lub ciągłości wcześniejszych wyborów, ustalić minimum pełnych sesji graczy. Próby odcinkowe pomagają wtedy diagnozować konkretne miejsca.
    - Przed rekrutacją ustalić minimalną liczbę ważnych prób dla kryteriów wydania, rozstrzygnięcie wyników rozbieżnych oraz warunek powtórzenia przy zbyt małej próbie.
    - Dla stabilności na każdej platformie zapisać jednostkę, minimalny czas gry lub liczbę sesji, sposób rejestrowania awarii i zawieszeń oraz postępowanie, gdy brakuje danych do decyzji.
  - Przed rozpoczęciem bety ustalić klasy błędów wstrzymujących publikację i progi wydajności oraz stabilności na każdej platformie. Jeśli zatwierdzono trwały postęp, uwzględnić zgodność zapisów.
  - **Odbiór.** Alfa ma sprawdzone pełne przejście. Lista prac do bety i warunki publikacji są zatwierdzone.

## M6 · Beta i gotowość do wydania

- **M6.01 · Zorganizować i przeprowadzić testy z graczami**
  - Przygotować instrukcję instalacji, zakres prób i sposób zgłaszania problemów.
    - Przed przekazaniem builda zarchiwizować rewizję, ustawienia, logi i dostępne symbole. Wykonać próbne zgłoszenie, aby potwierdzić możliwość diagnozy tej wersji.
  - Sprawdzić pierwsze uruchomienie, czytelność celu, orientację w mieście, sterowanie i zrozumienie zasad.
    - Dobrać uczestników do profilu gracza i pytań testu. Porównać obserwacje z kryteriami M5.05, w tym z próbami powrotu po eksploracji i dobrowolnego podjęcia kolejnego zadania, jeśli należą do zakresu.
    - Dla priorytetowych funkcji dostępności uwzględnić osoby, które ich potrzebują. Sprawdzić samodzielne znalezienie opcji i wykonanie zadania z jej użyciem.
  - Zebrać obserwacje z misji, dłuższej eksploracji i sytuacji, w których uczestnicy wybrali inną kolejność działań.
    - Sprawdzić tempo środkowego odcinka i czytelność zakończenia według scenariusza z M5.05.
  - Oddzielić powtarzalne problemy od pojedynczych obserwacji i powtórzyć próby, których dotyczy poprawka.
    - Zestawić liczbę ważnych prób i czas gry z wymaganym minimum. Dla niepełnych lub rozbieżnych wyników wykonać działania ustalone w M5.05 przed decyzją o publikacji.
    - Przy niespełnionym kryterium publikacji z M5.05 oznaczyć bloker wydania. Po poprawce lub zatwierdzonej zmianie zakresu powtórzyć dotkniętą próbę.
  - **Odbiór.** Wnioski zawierają wersje buildów, konkretne scenariusze, wpływ na graczy i wyniki sprawdzeń po poprawkach.

- **M6.02 · Zweryfikować instalację i działanie na platformach docelowych**
  - Sprawdzić świeżą instalację, pierwszy start, aktualizację poprzedniej wersji oraz uruchomienie po zmianie ustawień.
    - Przed premierą wskazać build źródłowy próby. Jeśli kanał udostępniał betę, sprawdzić przejście ze wspieranej wersji bety.
  - Sprawdzić działanie na minimalnym i referencyjnym sprzęcie oraz na zatwierdzonych systemach i urządzeniach wejściowych.
    - Sprawdzić utratę fokusu, zmianę trybu wyświetlania i odłączenie urządzenia podczas gry, jeśli dotyczy.
    - Dla trwałego postępu sprawdzić ograniczoną przestrzeń dyskową, wznowienie w nowym procesie i zgodne starsze zapisy. Dla utrwalanych ustawień sprawdzić zachowanie po aktualizacji.
    - Powtórzyć długie sesje i pomiary w scenach referencyjnych.
  - **Odbiór.** Każda zatwierdzona konfiguracja ma udokumentowany wynik, a deklarowane wymagania sprzętowe odpowiadają pomiarom.

- **M6.03 · Sprawdzić dostępność, języki i wykończenie prezentacji**
  - Zweryfikować sterowanie, ustawienia i czytelność przewidzianą w zakresie gry.
    - Sprawdzić kluczowe ekrany, napisy, rozpoznawalność komunikatów i korzystanie z menu bez myszy, jeśli gra wspiera kontroler.
    - Sprawdzić po ponownym uruchomieniu te ustawienia, których utrwalanie zatwierdzono.
  - Przejść reprezentatywne misje i menu we wszystkich zatwierdzonych wersjach językowych.
    - Ponowić na kandydacie kontrolę kompletności M4.12 dla całego zatwierdzonego zakresu. Próby reprezentatywne sprawdzają kontekst i czytelność.
    - Usunąć brakujące teksty, ucięcia i rozbieżności między głosem a napisami.
  - **Odbiór.** Sprawdzono deklarowane funkcje dostępności i wersje językowe w buildzie kandydującym do wydania.

- **M6.04 · Sprawdzić prawa do zawartości i wymagania dystrybucji**
  - Zweryfikować rejestr modeli, tekstur, fontów, muzyki, głosów i wtyczek wraz z wymaganymi informacjami o autorach.
  - Rozstrzygnąć pozycje z niejasnym pochodzeniem lub ograniczeniem istotnym dla publikacji.
  - Sprawdzić wymagania wybranego kanału dystrybucji dla pakietu, wersjonowania, oznaczeń i ewentualnych ocen wiekowych.
    - Dla każdego kanału wymagającego formalnej akceptacji utworzyć osobne sub-issue z terminem i wynikiem. Złożyć pakiet według M3.09, odnotować decyzję, ograniczenia i ponowne zgłoszenie. Wymagana akceptacja blokuje publikację w M6.07.
  - Jeśli build zbiera dane diagnostyczne, potwierdzić zakres, sposób przekazania, dostęp, retencję, usuwanie danych i informację dla gracza. Odnieść wynik do procedury użytej w próbach z graczami i do konfiguracji wydania.
  - **Odbiór.** Zatwierdzony pakiet ma komplet wymaganych informacji, a wszystkie użyte materiały mają udokumentowany status.

- **M6.05 · Przygotować pakiet wydania i informacje dla graczy**
  - Przygotować opis gry, zrzuty z działającego builda, wymagania sprzętowe, listę języków oraz deklaracje dostępności.
  - Przygotować informacje o wydaniu, znanych problemach i sposobie zgłaszania błędów.
  - Zbudować pakiet zgodny z zatwierdzonym kanałem i sprawdzić go na konfiguracji jak u gracza.
    - Przed odbiorem M6.07 odtworzyć środowisko ze wskazanych źródeł silnika, SDK, wtyczek i plików LFS. Powtórzyć build z rewizji kandydata w czystym środowisku bez wcześniejszego cache i ustawień użytkownika.
    - Wykonać próbę z uprawnieniami osoby, która ma przygotować poprawkę. Zapisać właściciela archiwum i okres dostępu do zależności i danych potrzebnych do odtworzenia wydania.
    - Przygotować podpisanie i dodatkową weryfikację pakietu, jeśli wymaga ich platforma.
    - Zapisać rozmiar pobierania i instalacji oraz sprawdzić, czy pakiet obejmuje wszystkie wymagane pliki.
    - Zachować wewnętrzne logi i dane potrzebne do diagnozy awarii dokładnie tej wersji.
    - Oznaczyć pakiet po poprawkach z bety. Powiązać identyfikator artefaktu i manifest kanału, jeśli jest dostępny, z rewizją, wersją silnika, konfiguracją, danymi diagnostycznymi i wynikami odbioru.
  - **Odbiór.** Wskazano identyfikator pakietu i manifest kanału, jeśli jest dostępny. Pakiet przekazano do końcowych prób M6.02–M6.04. Materiały odpowiadają udokumentowanym funkcjom i pomiarom tej wersji.

- **M6.06 · Przygotować obsługę premiery i przećwiczyć aktualizację**
  - Uruchomić kanał zgłoszeń i przypisać odpowiedzialność za rozpoznanie awarii, utraty postępu oraz innych pilnych błędów.
    - Wyznaczyć okno obsługi premiery, częstotliwość przeglądu zgłoszeń, zastępstwo i ścieżkę eskalacji poza tym oknem.
  - Dla każdej pary platformy i kanału przećwiczyć pobranie kandydata oraz instalację aktualizacji w środowisku testowym kanału, jeśli jest dostępne. W pozostałych przypadkach użyć lokalnego odpowiednika i zapisać ograniczenia dowodu.
    - Dla każdej pary zapisać, które operacje wymagają dowodu z kanału, a dla których lokalna próba jest wystarczająca. Brak wymaganego dowodu wstrzymuje publikację danej pary. Dla zaakceptowanych ograniczeń przypisać osobę odpowiedzialną i pierwszą próbę na publicznym pakiecie.
    - Powtórzyć aktywne próby zgodności zapisów i ustawień. Przy lokalnej próbie zapisać, których zachowań kanału nie sprawdzono, jakie operacje są dostępne i kto ma uprawnienia do ich wykonania.
    - Zidentyfikować pobrany pakiet i przypisać próbne zgłoszenie oraz przykładowy log do właściwej wersji.
    - Dla platform z dostępnymi symbolami sprawdzić, czy archiwum pozwala odczytać stos próbnej awarii z tej wersji.
    - Sprawdzić dostępny sposób wycofania pakietu lub przygotowania zastępczej aktualizacji zgodnie z możliwościami dystrybucji.
    - Dla każdej zatwierdzonej kategorii trwałych danych, której format, interpretacja, dozwolone stany lub miejsce zapisu ulegają zmianie, sprawdzić aktualizację, zapis w nowszej wersji i wycofanie, jeśli kanał je wspiera. Gdy poprzednia wersja nie odczytuje danych, potwierdzić ich zachowanie i przećwiczyć aktualizację zastępczą. Uwzględnić ustawienia obok postępu.
  - **Odbiór.** Osoba odpowiedzialna potrafi powiązać zgłoszenie z wersją oraz przeprowadzić procedurę poprawki w przećwiczonym środowisku.

- **M6.07 · Odebrać kandydata do wydania**
  - Powiązać pakiet z dokładną wersją kodu, konfiguracji i zawartości. Zachować artefakt i wyniki prób.
  - Powtórzyć instalację, uruchomienie i przejście kluczowej ścieżki oraz aktywne próby utrwalania stanu.
  - Porównać wyniki z zatwierdzonymi warunkami publikacji z M5 i dołączyć wynik próby obsługi premiery.
    - W zestawieniu odbioru zapisać platformę, kanał, warunek, identyfikator pakietu, wynik i odnośnik do dowodu. Warunki dystrybucji przypisać do każdej pary. Wskazać osobę zatwierdzającą publikację.
    - Potwierdzić wymagane akceptacje kanału oraz uprawnienia osoby odpowiedzialnej za operacje przy premierze.
    - Przy każdym warunku wskazać wynik dla zatwierdzanego artefaktu albo udokumentować, dlaczego wynik z poprzedniego pozostaje ważny.
    - Warunki obejmują kryteria grywalności z M5.05. Wymagana jest udana próba lub zatwierdzona zmiana zakresu z powtórnym sprawdzeniem.
    - Wskazać dowód potwierdzający minimalną swobodę z aktualnej wizji M1.01. Jej zmiana wymaga przyjęcia nowej wersji wizji i powtórzenia odpowiedniej próby.
    - Wskazać dowód dla głównego wyróżnika aktualnej wizji. Ująć wyniki procedury aktualizacji i odzyskania dla każdej pary platformy i kanału.
    - Po zmianie zawartości, konfiguracji, cooka lub pakowania powtórzyć próby, na które mogła wpłynąć, i ponownie powiązać wynik z pakietem.
  - **Odbiór.** Wskazano konkretną wersję, wyniki odbioru i decyzję o publikacji. Otwarte blokery wstrzymują publikację.

## M7 · Wydanie i utrzymanie

- **M7.01 · Opublikować zatwierdzony build**
  - Oznaczyć wersję, zarchiwizować pakiet i powiązać go z odpowiednią wersją kodu oraz plików projektu.
  - Opublikować zatwierdzony pakiet i materiały w wybranym kanale.
  - Dla każdej zatwierdzonej pary platformy i kanału pobrać publiczny pakiet. Powiązać identyfikator artefaktu lub manifest z zatwierdzonym kandydatem. Sprawdzić instalację, start, nową grę i aktywne próby utrwalania stanu. Zapisać osobny wynik dla każdej pary.
    - Jeśli gra utrwala dane, zachować reprezentatywne zapisy lub ustawienia wytworzone przez publiczny pakiet do prób aktualizacji. Powiązać je z identyfikatorem wydania i przechowywać w okresie wsparcia danej wersji.
    - Gdy publiczna wersja jest błędna lub wystąpi bloker, osoba odpowiedzialna za wydanie uruchamia przećwiczone wycofanie albo aktualizację zastępczą i publikuje informację w uzgodnionym kanale.
  - **Odbiór.** Każda opublikowana wersja odpowiada zatwierdzonemu pakietowi i przeszła próbę po publikacji.

- **M7.02 · Obsłużyć zgłoszenia po wydaniu**
  - W przygotowanym kanale zebrać zgłoszenia z platformą, wersją i wpływem problemu na rozgrywkę.
  - Powiązać powtarzające się zgłoszenia i odtworzyć problemy na wersji używanej przez gracza.
    - Oddzielić priorytet awarii, utraty postępu i niemożności uruchomienia od usterek zawartości.
    - Gdy jest dostępna diagnostyka, powiązać sygnały awarii z właściwą wersją i konfiguracją.
  - Zapisać znane problemy i obejścia potwierdzone w buildzie.
  - **Odbiór.** Po zamknięciu okna premiery z M6.06 potwierdzone zgłoszenia mają wersję, sposób odtworzenia, priorytet i decyzję. Otwarte sprawy przeszły do kolejki z osobą odpowiedzialną za utrzymanie.

- **M7.03 · Przygotować, przetestować i opublikować poprawkę**
  - Uruchomić to zadanie po potwierdzeniu problemu wymagającego aktualizacji.
  - Wybrać zgłoszenia do poprawki i sprawdzić ich odtworzenie przed zmianą.
    - Przed pierwszą poprawką ustalić wspierane wersje źródłowe i ścieżki aktualizacji, w tym pominięcie poprzedniej wersji, jeśli kanał na to pozwala.
  - Przygotować nowy pakiet i zweryfikować regresje w systemach, których dotknęła poprawka.
    - Dla każdej dotkniętej pary platformy i kanału odnotować wymagany test dostarczenia, podpis oraz ponowną akceptację, jeśli dotyczy. Przed publikacją dołączyć wyniki odpowiednich kontroli z M6.04–M6.06 i powiązać pakiet z rewizją i danymi diagnostycznymi.
    - Zainstalować aktualizację ze wszystkich wspieranych wersji źródłowych. Sprawdzić te zapisy i ustawienia, których utrwalanie zatwierdzono.
    - Jeśli poprawka zmienia format, interpretację, dozwolone stany lub miejsce przechowywania zatwierdzonych trwałych danych, w tym ustawień, wykonać odpowiednią próbę wycofania lub aktualizacji zastępczej według M6.06.
    - Wykonać świeżą instalację i test uruchomienia na zatwierdzonych platformach.
    - Powtórzyć próby, przy których występował błąd.
  - Przygotować opis zmian i zatwierdzić wskazany artefakt wraz z identyfikatorem i wynikami prób. Po publikacji sprawdzić, czy publiczny pakiet lub manifest kanału odpowiada odebranemu artefaktowi, i zapisać wynik próby uruchomienia.
    - Dla każdej opublikowanej pary platformy i kanału sprawdzić pobranie i uruchomienie. Gdy kanał dostarcza aktualizację, pobrać ją na poprzednią publiczną wersję i sprawdzić dotknięte zapisy i ustawienia.
    - Jeśli publiczna próba ujawni bloker, osoba odpowiedzialna za wydanie stosuje procedurę M7.01. Wycofuje pakiet lub przygotowuje aktualizację zastępczą i informuje graczy.
  - **Odbiór.** Poprawka rozwiązuje wskazane problemy w publicznym buildzie. Aktywne próby zgodności zapisów i ustawień przechodzą w zatwierdzonych konfiguracjach.

- **M7.04 · Przekazać projekt do regularnego utrzymania**
  - Zapisać procedury budowy i wydawania poprawek, miejsca przechowywania artefaktów oraz sposób odtworzenia poprzedniej wersji.
    - Odtworzyć wskazane wcześniejsze wydanie z archiwum i wykonać budowę próbnej poprawki w czystym katalogu. Sprawdzić, czy dostępne są wymagane wersje silnika, wtyczki, źródła, pakiet i dane potrzebne do jego diagnozowania.
  - Ustalić częstotliwość przeglądu zgłoszeń, status obsługiwanych wersji oraz warunki wydania pilnej poprawki.
  - Podsumować problemy z produkcji i premiery wymagające osobnych zadań przed dalszą rozbudową gry.
  - **Odbiór.** Aktualny build, historia wydań, znane problemy i ścieżka przygotowania poprawki są zapisane w jednym miejscu.
