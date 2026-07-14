---
date: 2026-02-25
description: Dowiedz się, jak generować obrazy kodów kreskowych przy użyciu Aspose.BarCode
  dla .NET. Ten przewodnik krok po kroku pokazuje, jak generować kody kreskowe Code 39
  z sumą kontrolną i bez niej.
linktitle: One-Dimensional Code 39 Configuration
second_title: Aspose.BarCode .NET API
title: Jak wygenerować kod kreskowy – konfiguracja Code 39 w Aspose.BarCode
url: /pl/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jednowymiarowa konfiguracja Code 39

## Wprowadzenie

W tym samouczku dowiesz się **jak generować obrazy kodów kreskowych**, konkretnie jednowymiarowe kody kreskowe Code 39, przy użyciu Aspose.BarCode for .NET. Kody kreskowe odgrywają kluczową rolę w nowoczesnych firmach, od śledzenia zapasów po umożliwianie szybkiego i dokładnego pobierania danych. Aspose.BarCode for .NET to potężna biblioteka, która upraszcza generowanie i dostosowywanie kodów kreskowych w aplikacjach .NET. Ten przewodnik krok po kroku dzieli proces na łatwe do przyswojenia fragmenty, zapewniając, że nawet deweloperzy nowi w generowaniu kodów kreskowych będą mogli podążać za instrukcjami.

## Szybkie odpowiedzi
- **Jaka jest główna biblioteka?** Aspose.BarCode for .NET  
- **Czy mogę utworzyć kod kreskowy z sumą kontrolną?** Tak – ustaw `IsChecksumEnabled = EnableChecksum.Yes`  
- **Czy suma kontrolna jest obowiązkowa?** Nie – możesz wygenerować kod kreskowy bez sumy kontrolnej, wyłączając ją  
- **Jaki format obrazu jest używany w przykładach?** PNG (`BarCodeImageFormat.Png`)  
- **Czy potrzebuję licencji do rozwoju?** Dostępna jest tymczasowa licencja do oceny  

## Czym jest generowanie kodów kreskowych przy użyciu Aspose.BarCode?
Generowanie kodów kreskowych to proces konwertowania tekstu lub danych liczbowych na wizualny wzór odczytywany maszynowo. Aspose.BarCode for .NET obsługuje dziesiątki symbologii, w tym Code 39, i pozwala kontrolować wszystko, od rozmiaru i koloru po obliczanie sumy kontrolnej.

## Dlaczego używać Code 39 i opcji sumy kontrolnej?
Code 39 jest szeroko stosowany w logistyce i produkcji, ponieważ koduje dane alfanumeryczne bez znaków specjalnych. Dodanie sumy kontrolnej (lub jej pominięcie) pozwala zrównoważyć wykrywanie błędów z prostotą — idealne dla etykiet inwentaryzacyjnych, etykiet wysyłkowych lub prostych systemów punktu sprzedaży.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz następujące elementy:

1. **Środowisko programistyczne .NET** – praktyczna znajomość platformy .NET oraz IDE, takiego jak Visual Studio. Jeśli jesteś nowy w .NET, rozpocznij od oficjalnej dokumentacji: [Microsoft .NET Documentation](https://docs.microsoft.com/en-us/dotnet/).  
2. **Aspose.BarCode for .NET** – pobierz i zainstaluj bibliotekę. Dokumentacja i pliki do pobrania są dostępne tutaj: [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/) oraz [Download Aspose.BarCode for .NET](https://releases.aspose.com/barcode/net/).

Teraz, gdy omówiliśmy wymagania wstępne, przejdźmy do głównych kroków tworzenia jednowymiarowych kodów kreskowych Code 39.

## Jak generować kod kreskowy: importowanie przestrzeni nazw
Aby rozpocząć pracę z Aspose.BarCode for .NET, zaimportuj niezbędne przestrzenie nazw do swojego projektu. Dodanie tych instrukcji `using` zapewnia dostęp do klas generowania kodów kreskowych.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Jak generować kod kreskowy Code 39 (z sumą kontrolną i bez niej)

Poniżej utworzymy dwa kody kreskowe: jeden **bez sumy kontrolnej** i jeden **z sumą kontrolną**. Kod jest identyczny, z wyjątkiem flagi `IsChecksumEnabled`.

```csharp
// The path to the documents directory.
string path = "Your Directory Path";
System.Console.WriteLine("OneCSCode39:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code39Extended, "CODE");

// Example 1: Create a Code 39 barcode without checksum
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.No;
gen.Save($"{path}OneCSCode39WithoutChecksum.png", BarCodeImageFormat.Png);

// Example 2: Create a Code 39 barcode with checksum
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Save($"{path}OneCSCode39WithChecksum.png", BarCodeImageFormat.Png);
```

**Co robi kod**

1. **Utwórz** instancję `BarcodeGenerator` z `EncodeTypes.Code39Extended` oraz ciągiem danych `"CODE"`.  
2. **Przełącz** `IsChecksumEnabled`, aby kontrolować, czy zostanie dodana cyfra sumy kontrolnej.  
3. **Zapisz** każdy kod kreskowy jako plik PNG w określonym folderze.

Masz teraz dwa gotowe do użycia obrazy kodów kreskowych: `OneCSCode39WithoutChecksum.png` i `OneCSCode39WithChecksum.png`.

## Typowe problemy i rozwiązania
| Problem | Dlaczego się pojawia | Rozwiązanie |
|-------|----------------|-----|
| **Ścieżka pliku nie znaleziona** | Zmienna `path` wskazuje na nieistniejący folder. | Upewnij się, że katalog istnieje lub użyj `Directory.CreateDirectory(path)`. |
| **Nieprawidłowe znaki w danych** | Code 39 obsługuje tylko znaki alfanumeryczne i kilka symboli specjalnych. | Użyj rozszerzonego Code 39 (`Code39Extended`), który obsługuje pełny zestaw ASCII, jak pokazano powyżej. |
| **Błąd sumy kontrolnej** | Zapomnienie ustawienia `IsChecksumEnabled`, gdy jest wymagane. | Jawnie ustaw flagę na `EnableChecksum.Yes` lub `No` w zależności od scenariusza. |

## Najczęściej zadawane pytania (FAQ):

### P: Czy mogę używać Aspose.BarCode for .NET z innymi językami programowania?
O: Aspose.BarCode jest głównie przeznaczony dla .NET, ale Aspose oferuje biblioteki kodów kreskowych również dla innych platform.

### P: Czy dostępne są opcje licencjonowania Aspose.BarCode for .NET?
O: Tak, możesz zapoznać się z opcjami licencjonowania i poprosić o tymczasową licencję na stronie Aspose: [Aspose.BarCode Licensing](https://purchase.aspose.com/temporary-license/).

### P: Czy Aspose.BarCode for .NET nadaje się do aplikacji webowych?
O: Tak, Aspose.BarCode for .NET może być używany w aplikacjach webowych, co czyni go odpowiednim dla szerokiego zakresu projektów programistycznych.

### P: Czy mogę dostosować wygląd generowanych kodów kreskowych?
O: Oczywiście, możesz dostosować różne aspekty kodu kreskowego, w tym rozmiar, kolory i czcionki.

### P: Gdzie mogę uzyskać wsparcie lub zadać pytania dotyczące Aspose.BarCode for .NET?
O: Odpowiedzi na pytania i wsparcie znajdziesz na forum Aspose.BarCode: [Aspose.BarCode Forum](https://forum.aspose.com/c/barcode/13).

## Dodatkowe często zadawane pytania

**P: Jaka jest różnica między kodem kreskowym z sumą kontrolną a bez niej?**  
O: Suma kontrolna dodaje dodatkową cyfrę, która pomaga wykrywać błędy transkrypcji. Używaj jej, gdy integralność danych jest krytyczna.

**P: Jak duży może być wygenerowany plik PNG?**  
O: Rozmiar jest kontrolowany przez `gen.Parameters.ImageWidth/Height`. Dostosuj te właściwości przed wywołaniem `Save`.

**P: Czy mogę generować kody kreskowe w innych formatach obrazu?**  
O: Tak, Aspose.BarCode obsługuje JPEG, BMP, GIF, TIFF i inne — wystarczy zmienić wartość wyliczenia `BarCodeImageFormat`.

**P: Czy istnieje sposób generowania kodów kreskowych w aplikacji webowej bez zapisywania na dysk?**  
O: Możesz zapisać do `MemoryStream` i zwrócić tablicę bajtów bezpośrednio do klienta.

## Zakończenie
Postępując zgodnie z tymi prostymi krokami, możesz **generować obrazy kodów kreskowych** w .NET z pełną kontrolą nad obsługą sumy kontrolnej, formatem obrazu i stylizacją wizualną. Niezależnie od tego, czy zarządzasz zapasami, przetwarzasz zamówienia, czy budujesz portal internetowy z obsługą kodów kreskowych, Aspose.BarCode for .NET zapewnia niezawodne i przyjazne dla dewelopera rozwiązanie.

---

**Ostatnia aktualizacja:** 2026-02-25  
**Testowano z:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}