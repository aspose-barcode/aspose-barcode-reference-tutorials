---
category: general
date: 2026-10-21
description: Jak odczytać kod kreskowy PDF417 w C# przy użyciu czytnika kodów kreskowych
  z obrazu. Postępuj zgodnie z tym krok po kroku przykładem czytnika kodów kreskowych
  w C# dla niezawodnego dekodowania.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode from image c#
- c# barcode reader example
- macro pdf417 decoding
- barcode extended fields c#
language: pl
lastmod: 2026-10-21
og_description: Jak odczytać kod kreskowy PDF417 w C# przy użyciu pełnego przykładu
  czytnika kodów. Dowiedz się, jak dekodować obrazy Macro PDF417 i uzyskać dostęp
  do wszystkich rozszerzonych pól.
og_image_alt: Console output showing decoded PDF417 barcode fields in a C# application
og_title: Jak odczytać kod kreskowy PDF417 w C# – szczegółowy przewodnik
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  headline: How to read PDF417 barcode in C# – full barcode reader guide
  type: TechArticle
- description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  name: How to read PDF417 barcode in C# – full barcode reader guide
  steps:
  - name: Initialise the `BarCodeReader` for the specific `DecodeType`.
    text: Initialise the `BarCodeReader` for the specific `DecodeType`.
  - name: Iterate through the returned `BarCodeResult` collection.
    text: Iterate through the returned `BarCodeResult` collection.
  - name: Access both basic and extended PDF417 fields.
    text: Access both basic and extended PDF417 fields.
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the Aspose.BarCode package** (as shown earlier).'
    text: '**Add the Aspose.BarCode package** (as shown earlier).'
  - name: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
    text: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
  - name: '**Build and run**'
    text: '**Build and run**'
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Jak odczytać kod PDF417 w C# – pełny przewodnik po czytniku kodów kreskowych
url: /pl/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-full-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak odczytać kod kreskowy PDF417 w C# – pełny przewodnik po czytniku kodów kreskowych

Jeśli potrzebujesz **jak odczytać kod kreskowy PDF417** w aplikacji .NET, ten przewodnik pokaże Ci gotowe rozwiązanie. Zobaczysz, jak **odczytać kod kreskowy z obrazu w C#** przy użyciu popularnej biblioteki kodów kreskowych i uzyskać wszystkie atrybuty Macro PDF417 bez dodatkowych narzędzi.

Samouczek obejmuje wszystko, co potrzebne do **przykładu czytnika kodów kreskowych w C#**: konfigurację projektu, przegląd kodu oraz wskazówki dotyczące obsługi przypadków brzegowych. Po zakończeniu możesz wkleić kod do projektu konsolowego i od razu rozpocząć dekodowanie obrazów PDF417.

## Czego będziesz potrzebować

| Wymaganie | Powód |
|--------------|--------|
| .NET 6.0 SDK lub nowszy | Zapewnia środowisko uruchomieniowe dla aplikacji konsolowej C# |
| Visual Studio 2022 (lub dowolne IDE C#) | Umożliwia łatwe tworzenie projektów i debugowanie |
| Aspose.BarCode for .NET (pakiet NuGet) | Dostarcza klasy `BarCodeReader` i `DecodeType` |
| Plik obrazu Macro PDF417 (np. `MacroPdf417.png`) | Służy jako dane wejściowe do dekodowania |

Możesz zainstalować bibliotekę przy użyciu interfejsu dotnet CLI:

```bash
dotnet add package Aspose.BarCode
```

## Jak odczytać kod kreskowy PDF417 z obrazu w C#

Podstawą przepływu **odczytywania kodu kreskowego z obrazu w C#** jest trzy działania:

1. Zainicjalizuj `BarCodeReader` dla konkretnego `DecodeType`.
2. Przejdź iteracyjnie po zwróconej kolekcji `BarCodeResult`.
3. Uzyskaj dostęp zarówno do podstawowych, jak i rozszerzonych pól PDF417.

Poniżej znajduje się kompletny, gotowy do uruchomienia kod. Zapisz go jako `Program.cs` w projekcie konsolowym.

```csharp
using System;
using Aspose.BarCode;               // Provides BarCodeReader, DecodeType, BarCodeResult
using Aspose.BarCode.BarCodeRecognition; // Contains extended PDF417 structures

class Program
{
    static void Main()
    {
        // Step 1: Initialise a BarCodeReader for a Macro PDF417 image
        // Replace the path with the location of your MacroPdf417.png file
        string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes present in the image
            foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
            {
                // Step 3: Display basic barcode information
                Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
                Console.WriteLine($"CodeText: {barcodeResult.CodeText}");

                // Step 4: Show Macro PDF417 specific extended fields
                Console.WriteLine($"File ID: {barcodeResult.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name: {barcodeResult.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {barcodeResult.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size: {barcodeResult.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"TimeStamp: {barcodeResult.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {barcodeResult.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {barcodeResult.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {barcodeResult.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

### Wyjaśnienie każdego kroku

* **Krok 1 – Inicjalizacja czytnika**  
  Konstruktor `BarCodeReader` przyjmuje ścieżkę do pliku obrazu oraz `DecodeType`. `DecodeType.MacroPdf417` informuje bibliotekę, aby szukała symboli Macro PDF417, które zawierają dodatkowe metadane poza zwykłymi kodami PDF417.

* **Krok 2 – ReadBarCodes()**  
  Ta metoda zwraca `IEnumerable<BarCodeResult>`, które może zawierać wiele kodów kreskowych, jeśli obraz zawiera ich więcej niż jeden. Pętla `foreach` zapewnia, że każdy wykryty symbol zostanie przetworzony.

* **Krok 3 – Podstawowe informacje**  
  `CodeTypeName` identyfikuje format kodu kreskowego (np. „MacroPDF417”). `CodeText` zawiera surowy ciąg danych zakodowany w symbolu.

* **Krok 4 – Rozszerzone pola**  
  Macro PDF417 dodaje zestaw rozszerzonych właściwości pod `barcodeResult.Extended.Pdf417`. Te pola udostępniają dane na poziomie pliku, takie jak `FileID`, `SegmentID` i `FileName`. Bezpośredni dostęp pozwala odtworzyć dokumenty wielosegmentowe lub zweryfikować integralność.

#### Oczekiwany wynik w konsoli

```
CodeType: MacroPDF417
CodeText: 1234567890
File ID: 5
Segment ID: 1
Segments Count: 3
File Name: invoice_2024.pdf
Checksum: 0A3F
File Size: 254321
TimeStamp: 2024-03-15T10:45:12Z
Addressee: Acme Corp.
Sender: Warehouse 12
Terminator: END
----------------------------------------
```

Dokładne wartości odzwierciedlają zawartość zakodowaną w Twoim pliku `MacroPdf417.png`. Jeśli obraz zawiera pojedynczy segment, `SegmentsCount` będzie równe 1, a `SegmentID` będzie równe 0.

## Skonfiguruj środowisko czytnika kodów kreskowych w C#

Solidny **przykład czytnika kodów kreskowych w C#** zależy od czystej konfiguracji projektu:

1. **Utwórz nowy projekt konsolowy**  
   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```
2. **Dodaj pakiet Aspose.BarCode** (jak pokazano wcześniej).  
3. **Skopiuj plik obrazu** do folderu projektu lub odwołaj się do niego za pomocą ścieżki bezwzględnej.  
4. **Zbuduj i uruchom**  
   ```bash
   dotnet run
   ```

Jeśli kompilacja zakończy się niepowodzeniem z błędem brakującego odwołania, sprawdź, czy instrukcje `using Aspose.BarCode;` odpowiadają zainstalowanej wersji pakietu. API biblioteki jest stabilne w .NET 6 i .NET 8, więc możesz zaktualizować środowisko uruchomieniowe bez zmian w kodzie.

## Zdekoduj kod Macro PDF417

Gdy wywołujesz `ReadBarCodes()`, biblioteka wykonuje wewnętrznie następujące czynności:

* **Przetwarzanie wstępne obrazu** – konwertuje bitmapę na macierz binarną, korygując rotację i szumy.  
* **Wykrywanie wzorca** – skanuje wzorce start/stop PDF417 i wyodrębnia szerokość modułu.  
* **Korekcja błędów** – stosuje kody Reed‑Solomon do odzyskiwania uszkodzonych słów kodowych.  
* **Ekstrakcja makra** – analizuje rozszerzony nagłówek segmentu PDF417 i wypełnia obiekt `Extended.Pdf417`.  

Zrozumienie tego potoku pomaga zdecydować, kiedy dostosować opcje dekodera. Na przykład, jeśli Twoje obrazy mają niski kontrast, możesz włączyć właściwość `BarCodeReader` `ReadQuality` (dostępną w późniejszych wersjach), aby poprawić wskaźniki wykrywania.

## Interpretacja rozszerzonych pól PDF417

Rozszerzone pola mapują się bezpośrednio do specyfikacji Macro PDF417:

| Pole | Znaczenie |
|-------|-----------|
| `MacroPdf417FileID` | Unikalny identyfikator całego pliku we wszystkich segmentach |
| `MacroPdf417SegmentID` | Indeks bieżącego segmentu zaczynający się od zera |
| `MacroPdf417SegmentsCount` | Łączna liczba segmentów tworzących plik |
| `MacroPdf417FileName` | Oryginalna nazwa pliku zapisana podczas kodowania |
| `MacroPdf417Checksum` | 16‑bitowa suma kontrolna weryfikująca integralność |
| `MacroPdf417FileSize` | Rozmiar oryginalnego pliku w bajtach |
| `MacroPdf417TimeStamp` | Znacznik czasu UTC, kiedy kod został wygenerowany |
| `MacroPdf417Addressee` | Docelowy odbiorca dokumentu |
| `MacroPdf417Sender` | Nadawca dokumentu |
| `MacroPdf417Terminator` | Literał „END” oznaczający ostatni segment |

Możesz użyć tych wartości do odtworzenia wielosegmentowego PDF, sprawdzenia, czy żaden segment nie brakuje, lub zapisania informacji audytowych w celach zgodności.

## Typowe problemy i rozwiązywanie ich

| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|-------|--------------------------|-------------|
| Brak wyjścia | Nieprawidłowa ścieżka obrazu lub nieobsługiwany format | Użyj ścieżki bezwzględnej i upewnij się, że plik jest PNG/JPEG obsługiwany przez Aspose.BarCode |
| `CodeType` wyświetla „PDF417” zamiast „MacroPDF417” | Obraz zawiera zwykły symbol PDF417, a nie wariant makro | Sprawdź, czy źródłowy kod kreskowy jest zakodowany z rozszerzeniami Macro PDF417 |
| Niektóre pola są puste | Kod kreskowy został wygenerowany bez tych pól makro | Zakoduj kod kreskowy z pełnym ładunkiem makro lub obsłuż wartości null w kodzie |
| Dekoder rzuca `ArgumentException` | Podano nieprawidłowy `DecodeType` | Zmień `DecodeType.MacroPdf417` na `DecodeType.Pdf417`, jeśli potrzebujesz tylko standardowych danych PDF417 |

**Porada:** Owiń dostęp do pól w sprawdzanie null, jeśli spodziewasz się kodów nie‑makro. Obiekt `Extended.Pdf417` zwraca wartości domyślne (np. `0` dla pól numerycznych), gdy dane są nieobecne.

```csharp
int fileId = barcodeResult.Extended?.Pdf417?.MacroPdf417FileID ?? -1;
```

## Podsumowanie pełnego działającego przykładu

Łącząc wszystko razem, końcowy program składa się z dyrektyw using, metody `Main` oraz czterokrokowej pętli pokazanej wcześniej. Nie są wymagane dodatkowe pliki konfiguracyjne. Skompiluj i uruchom projekt, aby zobaczyć wynik w konsoli ze wszystkimi właściwościami Macro PDF417.

## Zakończenie

Teraz wiesz, **jak odczytać kod kreskowy PDF417** w C# używając zwięzłego **przykładu czytnika kodów kreskowych w C#**. Przewodnik poprowadził Cię przez konfigurację środowiska, implementację kodu oraz interpretację każdego rozszerzonego pola Macro PDF417. Dzięki tej bazie możesz zintegrować skanowanie kodów kreskowych z systemami inwentaryzacji, przepływami zarządzania dokumentami lub backendami mobilnymi.

### Next

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak odczytać PDF417 w C# – kompletny przewodnik po czytniku kodów kreskowych](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/)
- [Jak zdekodować PDF417 w C# przy użyciu przykładu czytnika kodów kreskowych](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/)
- [Jak utworzyć obraz kodu PDF417 w C# z opcjami Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}