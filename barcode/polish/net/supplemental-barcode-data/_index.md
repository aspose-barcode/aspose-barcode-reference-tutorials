---
date: 2026-03-07
description: Dowiedz się, jak tworzyć kod kreskowy EAN‑2 i generować kody kreskowe
  w .NET przy użyciu Aspose.BarCode for .NET. Opanuj dziś personalizację dodatkowych
  danych kodu kreskowego!
linktitle: Supplemental Barcode Data
second_title: Aspose.BarCode .NET API
title: Utwórz kod kreskowy EAN‑2 za pomocą Aspose.BarCode dla .NET
url: /pl/net/supplemental-barcode-data/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz kod kreskowy EAN-2 przy użyciu Aspose.BarCode dla .NET

## Wprowadzenie

Jeśli jesteś programistą .NET i chcesz **utworzyć kod kreskowy EAN-2** oraz wykorzystać możliwości dodatkowych danych w kodach kreskowych, jesteś we właściwym miejscu. W tym kompleksowym przewodniku przeprowadzimy Cię przez wszystko, co musisz wiedzieć — od podstawowej konfiguracji po precyzyjne dostosowanie odstępów wokół symboli. Niezależnie od tego, czy budujesz nowy system inwentaryzacji, czy ulepszasz istniejącą aplikację punktu sprzedaży, opanowanie tych funkcji uczyni generowanie kodów kreskowych w projektach .NET bardziej elastycznym i niezawodnym.

## Szybkie odpowiedzi
- **Co mogę wygenerować?** Kody kreskowe uzupełniające EAN‑2 i EAN‑5.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna wystarcza do rozwoju; licencja komercyjna jest wymagana w środowisku produkcyjnym.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Ile kodu jest potrzebne?** Tylko kilka linii — Aspose.BarCode zajmuje się ciężką pracą.  
- **Czy mogę dostosować odstępy?** Tak, możesz bezpośrednio kontrolować wymiar X oraz odstęp uzupełniający.

## Co to są dodatkowe dane w kodzie kreskowym?

Dodatkowe dane w kodzie kreskowym to małe dodatkowe symbole (EAN‑2, EAN‑5), które pojawiają się obok głównego kodu kreskowego, zazwyczaj używane do numerów wydań, rozszerzeń cenowych lub innych informacji pomocniczych. Aspose.BarCode dla .NET umożliwia generowanie tych symboli programowo, dając pełną kontrolę nad ich wyglądem i pozycjonowaniem.

## Dlaczego warto używać Aspose.BarCode dla .NET?

- **Pełna integracja z .NET** – działa z C#, VB.NET i F#.  
- **Renderowanie wysokiej jakości** – tworzy skanowalne kody kreskowe w dowolnej rozdzielczości.  
- **Rozbudowane możliwości dostosowania** – od typu symbolu po wymiar X, strefy ciszy i odstęp uzupełniający.  
- **Brak zewnętrznych zależności** – czysta biblioteka zarządzana, łatwa do wdrożenia.

## Konfiguracja dodatkowych danych w kodzie kreskowym

Zacznijmy od zagłębienia się w obszar konfiguracji dodatkowych danych w kodzie kreskowym. Aspose.BarCode dla .NET oferuje narzędzia umożliwiające łatwe generowanie kodów uzupełniających, dając pełną kontrolę nad kodami EAN‑2 i EAN‑5. Jak więc rozpocząć?

Po pierwsze, pobierz i zainstaluj Aspose.BarCode dla .NET. Możesz wypróbować darmową wersję próbną, aby przetestować możliwości i zobaczyć potężne funkcje w działaniu. Po skonfigurowaniu, postępuj zgodnie z naszym przewodnikiem krok po kroku, który przeprowadzi Cię przez cały proces, zapewniając łatwe opanowanie konfiguracji dodatkowych danych w kodzie kreskowym.

Pod koniec tej sekcji będziesz mieć solidną wiedzę na temat tworzenia kodów EAN‑2 i EAN‑5, co uczyni Cię bardziej wszechstronnym programistą .NET.

## Jak utworzyć kod kreskowy EAN-2? (Kroki konfiguracji)

1. **Utwórz generator kodów kreskowych** – wybierz klasę `BarcodeGenerator` i ustaw symbolikę na `EncodeTypes.EAN13` (lub inny typ podstawowy).  
2. **Włącz część uzupełniającą** – ustaw właściwość `SupplementData` na żądany ciąg numeryczny (np. `"12"` dla uzupełnienia EAN‑2).  
3. **Dostosuj ustawienia wizualne** – opcjonalnie zmodyfikuj `XDimension`, `BarHeight` i `QuietZone`, aby dopasować je do wymagań układu.  
4. **Zapisz lub renderuj** – wywołaj `Save`, aby zapisać obraz do pliku lub strumienia.

> *Wskazówka:* Utrzymuj długość danych uzupełniających dokładnie 2 cyfry dla EAN‑2 i 5 cyfr dla EAN‑5; w przeciwnym razie kod kreskowy może stać się nieczytelny.

## Dostosowanie odstępu w kodzie kreskowym uzupełniającym

W świecie kodów kreskowych kluczowa jest możliwość dostosowywania, a właśnie w tym Aspose.BarCode dla .NET błyszczy. Teraz skupmy się na dostosowywaniu odstępu w kodzie kreskowym uzupełniającym. Ten aspekt dotyczy kontroli wymiaru X oraz odstępu uzupełniającego w Twoich kodach.

Ponownie, rozpoczniesz od zainstalowania Aspose.BarCode dla .NET i skorzystania z darmowej wersji próbnej. Następnie postąpisz zgodnie z naszymi wskazówkami, jak dostroić odstępy w kodach. To dostosowanie może być niezwykle przydatne w różnych zastosowaniach, od zarządzania zapasami po systemy punktu sprzedaży.

Swoboda dopasowywania kodów do konkretnych potrzeb to cenna umiejętność, a ta sekcja zapewni Ci niezbędne narzędzia.

## Jak dostosować odstęp uzupełniający?

- **X‑Dimension** – określa szerokość pojedynczego modułu; większe wartości zwiększają ogólny rozmiar kodu kreskowego.  
- **Supplement Space** – odstęp między głównym kodem kreskowym a częścią uzupełniającą; reguluj za pomocą właściwości `SupplementSpace`.  
- **Quiet Zone** – obowiązkowy pusty margines wokół całego kodu kreskowego; utrzymuj go przynajmniej 10 jednostek X‑Dimension dla niezawodnego skanowania.

Eksperymentuj z tymi ustawieniami w projekcie testowym, aż osiągniesz wymaganą równowagę wizualną dla sprzętu skanującego.

## Typowe przypadki użycia

| Scenariusz | Dlaczego dodatkowe dane są przydatne |
|------------|--------------------------------------|
| **Rozszerzenia cen w handlu detalicznym** | EAN‑5 może kodować informacje o cenie bezpośrednio na etykiecie. |
| **Numery wydań czasopism** | EAN‑2 identyfikuje wydanie, umożliwiając szybkie sortowanie. |
| **Logistyka i śledzenie** | Dodanie małego uzupełnienia do głównego kodu kreskowego dostarcza dodatkowych danych routingu bez zwiększania rozmiaru etykiety. |

## Samouczki dotyczące dodatkowych danych w kodzie kreskowym
### [Supplemental Barcode Data Configuration](./supplemental-barcode-data-configuration/)
Generuj dodatkowe dane w kodzie kreskowym przy użyciu Aspose.BarCode dla .NET. Łatwo dostosowuj kody EAN-2 i EAN-5. Przewodnik krok po kroku dla programistów .NET.
### [Supplemental Barcode Space Customization](./supplemental-barcode-space-customization/)
Dostosuj kody kreskowe łatwo przy użyciu Aspose.BarCode dla .NET. Kontroluj X‑Dimension i odstęp uzupełniający. Wypróbuj darmową wersję próbną!

## Najczęściej zadawane pytania

**Q: Czy mogę generować zarówno EAN‑2, jak i EAN‑5 tym samym kodem?**  
A: Tak. Wystarczy zmienić długość `SupplementData` (2 cyfry dla EAN‑2, 5 cyfr dla EAN‑5), a biblioteka wygeneruje właściwą symbolikę.

**Q: Czy muszę obliczać wartości sumy kontrolnej dla uzupełnienia?**  
A: Nie. Aspose.BarCode automatycznie oblicza i dołącza wymaganą sumę kontrolną.

**Q: Czy istnieje limit liczby kodów kreskowych, które mogę generować w pętli?**  
A: Biblioteka jest zoptymalizowana pod kątem masowej generacji; należy jednak zwracać uwagę na zużycie pamięci przy obsłudze bardzo dużych kolekcji obrazów.

**Q: Jak wstawić kod kreskowy do dokumentu PDF lub Word?**  
A: Zapisz kod kreskowy jako obraz (PNG, JPEG itp.), a następnie wstaw go przy użyciu wybranego API do generowania dokumentów (np. Aspose.PDF lub Aspose.Words).

**Q: Co zrobić, jeśli mój skaner nie odczytuje części uzupełniającej?**  
A: Sprawdź, czy `SupplementSpace` wynosi co najmniej 2 jednostki X‑Dimension oraz czy strefa ciszy spełnia specyfikacje skanera.

**Ostatnia aktualizacja:** 2026-03-07  
**Testowano z:** Aspose.BarCode for .NET 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}