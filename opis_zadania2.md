``` 1. Kontekst
Pracujesz w PharmaTrack Sp. z o.o. — firmie dostarczającej producentom farmaceutycznym dane o sprzedaży aptecznej (sell-out).
PharmaTrack utrzymuje panel 420 aptek w Polsce, które co miesiąc przekazują dane transakcyjne. Na ich
podstawie zespół analiz przygotowuje comiesięczne raporty dla klientów.
Jednym z klientów jest NordFarm Polska Sp. z o.o. — producent suplementów i leków OTC. Jego portfel objęty panelem
to pięć produktów: VITARIS D3 2000, VITARIS D3 4000, MAGNOVIT B6, GINKOMAX 120 i ALLERTIS 10.
2 kwietnia 2026 r. wysłaliśmy klientowi raport za marzec. 6 kwietnia dostaliśmy odpowiedź. Sprawa trafiła do Ciebie.
```

``` 2. Materiały
<table>
<tr><td>Plik</td><td>Co to jest</td><tr>
<tr><td>raport_marzec_2026.md</td><td>Raport, który został wysłany klientowi 2 kwietnia. To jest dokument, który kwestionuje klient. Zawiera tabele wg produktu, kanału, województwa, TOP 10 aptek oraz notę metodologiczną.</td><tr>
<tr><td>dane_wsadowe_202603</td><td>Surowy eksport tabeli z systemu panelowego, na którym zbudowano raport.</td><tr>
</table>

<table>
<tr>Kolumna<td></td> Opis</tr>
<tr><td>load_id</td><td>Identyfikator przebiegu ładowania danych<td></tr>
<tr><td>data_sprzedazy</td><td>Data transakcji<td></tr>
<tr><td>apteka_id</td><td>Identyfikator apteki w panelu<td></tr>
<tr><td>nazwa_apteki</td><td>Nazwa handlowa placówki<td></tr>
<tr><td>wojewodztwo</td><td>Województwo placówki<td></tr>
<tr><td>kanal</td><td>Kanał: apteka sieciowa lub indywidualna<td></tr>
<tr><td>Zadanie</td><td>rekrutacyjne · analiza danych rynku aptecznego | 2<td></tr>
<tr><td>Kolumna</td><td>Opis<td></tr>
<tr><td>ean</td><td>Kod EAN produktu<td></tr>
<tr><td>nazwa_produktu</td><td>Nazwa produktu podana przez aptekę<td></tr>
<tr><td>opakowania</td><td>Liczba sprzedanych opakowań<td></tr>
<tr><td>wartosc_pln</td><td>Wartość sprzedaży w PLN<td></tr>
<tr><td>typ_transakcji</td><td>SPRZEDAZ — sprzedaż detaliczna; ZWROT — zwrot towaru przez pacjenta lub korekta; PROMO —wydanie promocyjne bez opłaty<td></tr>
</table>
```

``` 3. Zadania
Poziom A — odtworzenie liczb (obowiązkowy)
1. Wczytaj i przygotuj dane wsadowe. Krótko opisz, jakie problemy z jakością danych napotkałeś i jak każdy z nich rozwiązałeś.
2. Policz za marzec 2026: łączną sprzedaż wartościową (PLN), łączny wolumen (opakowania) oraz liczbę aptek, które w marcu raportowały sprzedaż.
3. Policz sprzedaż wartościową i wolumenową w podziale na produkt oraz na kanał dystrybucji.
4. Zestaw swoje wyniki z liczbami z raportu PDF w jednej tabeli: wartość z raportu, wartość poprawna, różnica w PLN, różnica w procentach.
```
```
Poziom B — diagnoza (obowiązkowy)
1. Wskaż wszystkie przyczyny rozbieżności między raportem a danymi źródłowymi. Dla każdej podaj: na czym polega błąd, ile wynosi jego wpływ w PLN i na których przekrojach się objawia.
2. Zbuduj tabelę uzgodnienia (reconciliation), która krok po kroku prowadzi od kwoty z raportu do kwoty poprawnej. Suma korekt musi zgadzać się co do grosza.
3. Odpowiedz osobno na każde z czterech pytań klienta:
3.1. Sprzedaż VITARIS D3 2000 w kanale sieciowym wykazują Państwo na 78 679,71 PLN. U nas wychodzi ok. 70 100 PLN. To ponad 12% różnicy na jednym przekroju i nie potrafimy tego uzasadnić.
3.2. Liczba aptek raportujących spadła z 421 w lutym do 417 w marcu. Czy tracimy dystrybucję? Dział handlowy nie zgłaszał żadnych wypowiedzeń.
3.3. W rankingu województw śląskie wyprzedziło dolnośląskie. W naszych danych z hurtowni jest odwrotnie i tak było przez cały ubiegły rok.
3.4. Średnia cena za opakowanie VITARIS D3 2000 wychodzi z Państwa raportu 23,94 PLN. Nasza cena katalogowa to 24,90 PLN i w marcu nie było żadnej akcji cenowej. Skąd ta różnica? 
4. Policz sprzedaż wg województwa oraz TOP 10 aptek według wartości sprzedaży. Porównaj z raportem.
5. Załącz zapytanie SQL, które z załadowanych danych produkuje poprawną tabelę sprzedaży w podziale na produkt i kanał. Dialekt dowolny (PostgreSQL, MS SQL, BigQuery, SQLite, DuckDB). Jeżeli pracowałeś wyłącznie w Excelu — załącz plik z widocznymi formułami lub krokami Power Query i opisz, jak wyglądałoby to zapytanie.
```
```
Poziom C — dla chętnych (opcjonalny)
1. Dla każdego produktu policz, jaki udział w jego sprzedaży mają jego trzy największe apteki (koncentracja). Użyj funkcji okna.
2. Znajdź apteki o nietypowym rozkładzie sprzedaży w czasie — na przykład takie, w których jeden dzień odpowiada za nieproporcjonalnie dużą część miesiąca. Zaproponuj próg i uzasadnij go.
3. Zaproponuj zestaw automatycznych kontroli jakości danych, które wychwyciłyby te błędy przed wysłaniem raportu do klienta. Dla każdej kontroli podaj warunek i próg alarmu.
4. Wskaż, co należałoby zmienić w nocie metodologicznej raportu, żeby takie nieporozumienie się nie powtórzyło.
``` 