---
category: general
date: 2026-09-10
description: Dowiedz się, jak dekodować kod kreskowy z obrazu, używając zwięzłego
  przykładu czytnika kodów kreskowych w C#, który odczytuje kody Macro PDF417 w kilku
  linijkach.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- decode barcode from image
- c# barcode reader example
- read barcode C#
- barcode decoding tutorial
- Macro PDF417 C#
language: pl
lastmod: 2026-09-10
og_description: Odczytaj kod kreskowy z obrazu przy użyciu krótkiego przykładu czytnika
  kodów w C#. Postępuj zgodnie z instrukcją krok po kroku, aby natychmiast odczytać
  dane Macro PDF417.
og_image_alt: Screenshot of console output showing decoded Macro PDF417 barcode information
og_title: Odczytaj kod kreskowy z obrazu przy użyciu przykładu czytnika kodów kreskowych
  w C#
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to decode barcode from image using a concise C# barcode reader
    example that reads Macro PDF417 codes in just a few lines.
  headline: Decode barcode from image with a C# barcode reader example
  type: TechArticle
- description: Learn how to decode barcode from image using a concise C# barcode reader
    example that reads Macro PDF417 codes in just a few lines.
  name: Decode barcode from image with a C# barcode reader example
  steps:
  - name: '**Initialize** a `BarCodeReader` for the target image.'
    text: '**Initialize** a `BarCodeReader` for the target image.'
  - name: '**Iterate** over every detected barcode.'
    text: '**Iterate** over every detected barcode.'
  - name: '**Print** the standard and extended Macro PDF417 data.'
    text: '**Print** the standard and extended Macro PDF417 data.'
  type: HowTo
tags:
- barcode
- C#
- image processing
title: Dekoduj kod kreskowy z obrazu przy użyciu przykładu czytnika kodów kreskowych
  w C#
url: /pl/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dekodowanie kodu kreskowego z obrazu przy użyciu przykładu czytnika kodów kreskowych w C#

Jeśli potrzebujesz **dekodować kod kreskowy z obrazu**, ten przewodnik pokaże Ci dokładnie, jak to zrobić w C#. Korzystając z kompaktowego **przykładu czytnika kodów kreskowych w C#**, odczytasz dane Macro PDF417 przy użyciu zaledwie kilku linii kodu.

Zobaczysz kompletny, działający program, zrozumiesz, dlaczego każdy element ma znaczenie, oraz poznasz wskazówki zapobiegające typowym pułapkom. Nie potrzebna jest żadna zewnętrzna dokumentacja — wszystko, czego potrzebujesz, znajduje się tutaj.

## Czego się nauczysz

- Zainstaluj wymagany pakiet NuGet do dekodowania kodów kreskowych.  
- Napisz **przykład czytnika kodów kreskowych w C#**, który otwiera plik obrazu i wyodrębnia każdy kod kreskowy.  
- Uzyskaj dostęp do rozszerzonych pól Macro PDF417, takich jak identyfikator pliku.  
- Zweryfikuj wynik i dostosuj kod do innych typów kodów kreskowych.

### Wymagania wstępne

- .NET 6.0 SDK lub nowszy (kod działa również z .NET Core 3.1 i .NET Framework 4.7+).  
- Podstawowa znajomość aplikacji konsolowych w C#.  
- Plik obrazu zawierający kod Macro PDF417 (np. `MacroPdf417.png`).  

## Krok 1: Zainstaluj bibliotekę do odczytu kodów kreskowych

Przykład używa **Aspose.BarCode for .NET**, szeroko stosowanej biblioteki obsługującej dekodowanie Macro PDF417.

```bash
dotnet add package Aspose.BarCode
```

> **Dlaczego ta biblioteka?**  
> Dostarcza pojedynczą klasę `BarCodeReader`, która obsługuje wiele formatów, zapewnia wysoką dokładność i zwraca rozszerzone informacje dla kodów Macro PDF417 — wszystko bez dodatkowej konfiguracji.

## Krok 2: Utwórz przykład czytnika kodów kreskowych w C#

Utwórz nowy projekt konsolowy i zamień wygenerowany plik `Program.cs` na poniższy kod. Przykład realizuje trzy wyraźne kroki:

1. **Zainicjalizuj** `BarCodeReader` dla docelowego obrazu.  
2. **Iteruj** po każdym wykrytym kodzie kreskowym.  
3. **Wypisz** standardowe i rozszerzone dane Macro PDF417.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Path to the image that contains the Macro PDF417 barcode
            const string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            // 1️⃣ Create a BarCodeReader configured for Macro PDF417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Read all barcodes found in the image
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Display basic information
                    Console.WriteLine($"Code Type: {result.CodeTypeName}");
                    Console.WriteLine($"Code Text: {result.CodeText}");

                    // 3️⃣ Display Macro PDF417 extended fields (if available)
                    if (result.Extended?.Pdf417?.MacroPdf417FileID != null)
                    {
                        Console.WriteLine($"Macro PDF417 File ID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

### Wyjaśnienie poszczególnych sekcji

- **Konstruktor `BarCodeReader`** – Pierwszy argument to ścieżka do obrazu; drugi informuje bibliotekę, aby szukała konkretnie kodów Macro PDF417. Takie ukierunkowane dekodowanie zwiększa wydajność w porównaniu ze skanowaniem wszystkich możliwych formatów.  
- **`ReadBarCodes()`** – Zwraca enumerable wszystkich kodów kreskowych wykrytych na obrazie, co pozwala obsłużyć wiele kodów w jednym pliku.  
- **`result.Extended.Pdf417.MacroPdf417FileID`** – Macro PDF417 przechowuje dodatkowe metadane (identyfikator pliku, liczba segmentów itp.). Przykład sprawdza, czy wartość nie jest null, aby uniknąć `NullReferenceException`, gdy obraz zawiera kod nie‑Macro.  

## Krok 3: Uruchom program i zweryfikuj wynik

Zbuduj i uruchom aplikację konsolową:

```bash
dotnet run
```

Powinieneś zobaczyć wyjście podobne do:

```
Code Type: MacroPdf417
Code Text: 1234567890ABCDEF
Macro PDF417 File ID: 42
----------------------------------------
```

Jeśli obraz nie zawiera kodu Macro PDF417, program nadal wypisze inne wykryte formaty, ale pole rozszerzone zostanie pominięte.

## Porada: Dekoduj inne typy kodów kreskowych bez dużych zmian w kodzie

Aby **dekodować kod kreskowy z obrazu** dla innego formatu, zmień wartość wyliczenia `DecodeType`:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.QR))
```

Możesz również przekazać `DecodeType.AllSupportedTypes`, aby biblioteka wykryła dowolny znany kod kreskowy.

## Typowe problemy i jak ich uniknąć

| Objaw | Przyczyna | Rozwiązanie |
|---------|-------|-----|
| Brak jakiegokolwiek wyjścia | Nieprawidłowa ścieżka do obrazu lub nieobsługiwany format pliku | Sprawdź ścieżkę, upewnij się, że plik jest obsługiwanym obrazem (PNG, JPEG, BMP) |
| `result.Extended` jest null dla Macro PDF417 | Kod kreskowy nie jest wariantem Macro PDF417 | Potwierdź, że źródłowy obraz faktycznie zawiera kod Macro PDF417 |
| Wyjątek `System.IO.FileNotFoundException` | Brak pakietu NuGet w czasie wykonywania | Uruchom `dotnet restore` i upewnij się, że `Aspose.BarCode.dll` został skopiowany do folderu wyjściowego |

## Pełny listing źródłowy do szybkiego kopiowania

Poniżej znajduje się cały program, gotowy do skopiowania do `Program.cs`. Nie są wymagane żadne dodatkowe pliki.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            const string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type: {result.CodeTypeName}");
                    Console.WriteLine($"Code Text: {result.CodeText}");

                    if (result.Extended?.Pdf417?.MacroPdf417FileID != null)
                    {
                        Console.WriteLine($"Macro PDF417 File ID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

## Kolejne kroki

- **Zbadaj inne pola rozszerzone** takie jak `MacroPdf417SegmentID` lub `MacroPdf417FileSize`, aby zbudować przepływy rekonstrukcji pełnych dokumentów.  
- **Zintegruj czytnik z API webowym**, aby klienci mogli przesyłać obrazy i natychmiast otrzymywać zdekodowane dane.  
- **Przeprowadź benchmark wydajności** dekodując duże partie obrazów; `BarCodeReader` obsługuje przetwarzanie asynchroniczne w nowszych wersjach Aspose.  

---

Postępując zgodnie z tym **przykładem czytnika kodów kreskowych w C#**, masz teraz niezawodny sposób na **dekodowanie kodu kreskowego z obrazu** i wyodrębnianie bogatych informacji Macro PDF417. Eksperymentuj z różnymi wartościami `DecodeType`, łącz tę logikę z obserwatorami plików lub osadzaj ją w backendach mobilnych — Twoje możliwości przetwarzania kodów kreskowych są gotowe do skalowania.

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak odczytać PDF417 w C# – Kompletny przykład czytnika kodów kreskowych](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Generowanie kodu kreskowego z tekstem – Pełny przewodnik po PDF417 Macro](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)
- [Jak stworzyć kod PDF417 przy użyciu Aspose – Kompletny przewodnik krok po kroku](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}