---
category: general
date: 2026-09-19
description: Jak dekodować PDF417 w C# – naucz się odczytywać kody kreskowe z obrazu,
  używając zwięzłego przykładu czytnika kodów, który wyodrębnia pełne dane Macro PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcodes from image
- decode pdf417 barcode
- c# barcode reader example
language: pl
lastmod: 2026-09-19
og_description: Jak dekodować PDF417 w C# z przykładem czytnika kodów kreskowych krok
  po kroku. Wyodrębnij każde pole Macro PDF417 z obrazu w kilka sekund.
og_image_alt: Screenshot showing how to decode PDF417 in C# using a barcode reader
og_title: Jak dekodować PDF417 w C# – pełny przewodnik po czytniku kodów kreskowych
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to decode PDF417 in C# – learn to read barcodes from image using
    a concise barcode reader example that extracts full Macro PDF417 data.
  headline: How to decode PDF417 in C# with a barcode reader example
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Jak zdekodować PDF417 w C# przy użyciu przykładu czytnika kodów kreskowych
url: /pl/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dekodować PDF417 w C# – przykład użycia czytnika kodów kreskowych

Jeśli potrzebujesz dekodować PDF417 w C#, ten przewodnik pokaże Ci dokładnie, jak odczytać PDF417 z pliku obrazu. Nauczysz się czytać kody kreskowe z obrazu, uzyskiwać dostęp do rozszerzonych pól Macro PDF417 oraz integrować rozwiązanie w dowolnym projekcie .NET.

Dekodowanie kodów PDF417 jest powszechne w logistyce, biletowaniu i weryfikacji tożsamości. Ten tutorial obejmuje wszystko, co potrzebne do gotowej do produkcji implementacji, w tym wymagane biblioteki, pełny kod źródłowy oraz wskazówki dotyczące obsługi przypadków brzegowych.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

- .NET 6.0 lub nowszy zainstalowany  
- Visual Studio 2022 (lub dowolne IDE obsługujące C#)  
- Pakiet NuGet **Aspose.BarCode for .NET** (wersja 23.11 lub nowsza)  

Pakiet możesz dodać przy pomocy następującego polecenia:

```bash
dotnet add package Aspose.BarCode
```

Klasa `BarCodeReader` z tej biblioteki obsługuje typ dekodowania `MacroPdf417` potrzebny do pełnego wyodrębnienia PDF417.

## Krok 1: Jak dekodować PDF417 w C# – inicjalizacja czytnika

Pierwszy krok tworzy instancję `BarCodeReader`, która wskazuje na obraz Macro PDF417. Flaga `DecodeType.MacroPdf417` informuje bibliotekę, aby analizowała rozszerzone pola Macro.

```csharp
using System;
using Aspose.BarCode;               // Core barcode classes
using Aspose.BarCode.BarCodeRecognition; // Reader and result types

// Path to the Macro PDF417 image
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for Macro PDF417 decoding
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Continue with step 2...
```

**Dlaczego to ważne:** Inicjalizacja z `MacroPdf417` włącza właściwość `Extended.Pdf417` w każdym `BarCodeResult`, dając dostęp do metadanych na poziomie pliku, takich jak identyfikatory segmentów i znaczniki czasu.

## Krok 2: Odczyt kodów kreskowych z obrazu

Obraz PDF417 może zawierać wiele segmentów macro. Metoda `ReadBarCodes()` zwraca kolekcję wszystkich wykrytych kodów, więc możesz bezpiecznie iterować po nich.

```csharp
    // Step 2: Read every barcode present in the image
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Continue with step 3...
```

**Wskazówka:** Jeśli spodziewasz się tylko jednego kodu, możesz przerwać pętlę po pierwszej iteracji, ale iterowanie po wszystkich wynikach gwarantuje, że przechwycisz każdy segment w dokumentach wielostronicowych.

## Krok 3: Dekodowanie kodu PDF417 – wyodrębnianie podstawowych i rozszerzonych danych

Wewnątrz pętli wypisz zarówno ogólne informacje o kodzie, jak i pola specyficzne dla Macro. Obiekt `Extended.Pdf417` zawiera wszystkie metadane zdefiniowane w standardzie PDF417.

```csharp
        // Basic barcode information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");

        // Macro PDF417 extended data
        Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
    }
}
```

**Wyjaśnienie kluczowych pól**

| Pole | Znaczenie |
|------|-----------|
| `MacroPdf417FileID` | Identyfikator grupujący wszystkie segmenty należące do tego samego logicznego pliku |
| `MacroPdf417SegmentID` | Indeks bieżącego segmentu (zaczyna się od 0) |
| `MacroPdf417SegmentsCount` | Łączna liczba segmentów oczekiwanych dla pliku |
| `MacroPdf417FileName` | Opcjonalna nazwa pliku osadzona w macro |
| `MacroPdf417Checksum` | Suma kontrolna CRC‑16 zapewniająca integralność danych |
| `MacroPdf417FileSize` | Oryginalny rozmiar pliku w bajtach |
| `MacroPdf417TimeStamp` | Znacznik czasu, kiedy macro zostało wygenerowane |
| `MacroPdf417Addressee` | Odbiorca danych macro |
| `MacroPdf417Sender` | Nadawca danych macro |
| `MacroPdf417Terminator` | Flaga logiczna wskazująca ostatni segment |

Dostęp do tych pól pozwala odtworzyć oryginalny dokument, zweryfikować integralność lub kierować dane w oparciu o informacje o nadawcy/odbiorcy.

## Krok 4: Pełny przykład czytnika kodów w C# – połączenie wszystkiego

Poniżej znajduje się kompletny, gotowy do uruchomienia program. Zamień `YOUR_DIRECTORY` na folder zawierający plik `MacroPdf417.png`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417Decoder
{
    class Program
    {
        static void Main()
        {
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // Initialise the reader for Macro PDF417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate through all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic information
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // Extended Macro PDF417 data
                    Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete.");
        }
    }
}
```

**Oczekiwany wynik w konsoli (przykład)**

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 452312
Pdf417MacroTimeStamp: 2024-03-15T14:27:00Z
Pdf417MacroAddressee: LogisticsDept
Pdf417MacroSender: Warehouse01
MacroPdf417Terminator: False
----------------------------------------
Decoding complete.
```

Dokładne wartości będą się różnić w zależności od zawartości Twojego kodu Macro PDF417.

## Obsługa typowych przypadków brzegowych

| Sytuacja | Zalecane podejście |
|----------|--------------------|
| **Nie wykryto kodu** | Sprawdź ścieżkę obrazu, upewnij się, że plik nie jest uszkodzony i potwierdź, że kod jest widoczny (odpowiedni kontrast). |
| **Częściowe segmenty macro** | Użyj `MacroPdf417SegmentsCount`, aby wykryć brakujące części. Możesz poprosić system źródłowy o brakujące segmenty i ponownie uruchomić dekoder. |
| **Duże obrazy powodujące obciążenie pamięci** | Wczytaj obraz do `System.Drawing.Bitmap` z obniżoną rozdzielczością przed przekazaniem go do `BarCodeReader`. |
| **PDF417 bez Macro** | Zmień `DecodeType.MacroPdf417` na `DecodeType.Pdf417`, jeśli potrzebujesz tylko zwykłego tekstu kodu. |

## Porady profesjonalne

- **Przetwarzanie wsadowe:** Umieść logikę czytnika w metodzie przyjmującej listę ścieżek plików. Ponownie używaj jednej instancji `BarCodeReader` na wątek, aby zmniejszyć narzut alokacji.  
- **Wydajność:** W scenariuszach o wysokim przepływie włącz właściwość `ReaderOptions` `ReadQuality`, aby zbalansować szybkość i dokładność.  
- **Bezpieczeństwo:** Waliduj `CodeText` przed użyciem go w operacjach systemu plików, aby zapobiec atakom typu path traversal.

## Podsumowanie

W tym tutorialu nauczyłeś się, jak dekodować PDF417 w C# poprzez odczyt kodów z obrazu, wyodrębnianie wszystkich pól Macro PDF417 oraz budowanie kompletnego przykładu czytnika kodów w C#. Rozwiązanie działa z najnowszą biblioteką Aspose.BarCode, obsługuje makra wielosegmentowe i dostarcza praktycznych wskazówek dla projektów produkcyjnych.

Następnie poznaj tematy pokrewne, takie jak **odczyt kodów QR**, **przetwarzanie wsadowe kodów kreskowych** oraz **generowanie kodów PDF417**, aby poszerzyć swój zestaw narzędzi automatyzacji dokumentów. Śmiało eksperymentuj z różnymi źródłami obrazów, integruj kod w usługach ASP.NET lub rozszerz go o zapisywanie wyodrębnionych metadanych w bazie danych. Powodzenia w kodowaniu!

## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu oraz szczegółowe wyjaśnienia krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Read barcode from image – C# barcode reader example](/barcode/english/net/one-dimensional-barcode-types/read-barcode-from-image-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}