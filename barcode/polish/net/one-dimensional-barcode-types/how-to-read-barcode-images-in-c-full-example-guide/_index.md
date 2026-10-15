---
category: general
date: 2026-10-15
description: Jak szybko odczytywać obrazy kodów kreskowych w C# przy użyciu BarCodeReader.
  Dowiedz się, jak odczytywać wiele kodów kreskowych i zobacz przykład czytnika kodów
  kreskowych w C#, który działa z Macro‑PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode
- read multiple barcodes
- c# barcode reader example
- Macro‑PDF417 decoding
- barcode metadata extraction
language: pl
lastmod: 2026-10-15
og_description: Jak odczytać kod kreskowy w C# przy użyciu BarCodeReader. Ten samouczek
  pokazuje kompletny przykład czytnika kodów kreskowych w C#, który obsługuje wiele
  kodów i wyodrębnia metadane Macro‑PDF417.
og_image_alt: Screenshot showing how to read barcode with C# BarCodeReader
og_title: Jak odczytać kod kreskowy w C# – przykład krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  headline: How to read barcode images in C# – full example guide
  type: TechArticle
- description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  name: How to read barcode images in C# – full example guide
  steps:
  - name: Initialise the `BarCodeReader`
    text: '```csharp using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Read all barcodes present in the image
    text: '```csharp // Step 2: Read all barcodes in the image BarCodeResult[] results
      = reader.ReadBarCodes(); ```'
  - name: Display basic barcode details
    text: '```csharp foreach (BarCodeResult result in results) { Console.WriteLine($"CodeType:
      {result.CodeTypeName}"); Console.WriteLine($"CodeText: {result.CodeText}");
      ```'
  - name: Retrieve and show Macro‑PDF417 specific metadata
    text: '```csharp // Macro‑PDF417 extended data Console.WriteLine($"FileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Segment: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Count: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
      Console.WriteLine($"FileName'
  - name: Full runnable program
    text: Below is a self‑contained console application that puts all four steps together.
      Copy the code into a new `.cs` file, adjust the `imagePath`, and run `dotnet
      run`.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak odczytać obrazy kodów kreskowych w C# – pełny przewodnik z przykładami
url: /pl/net/one-dimensional-barcode-types/how-to-read-barcode-images-in-c-full-example-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak odczytywać obrazy kodów kreskowych w C# – pełny przewodnik z przykładami

Jeśli potrzebujesz **jak odczytywać kod kreskowy** z obrazu w aplikacji .NET, ten przewodnik dostarcza gotowe rozwiązanie. Zobaczysz kompletny **przykład czytnika kodów kreskowych w C#**, który działa z symbolami Macro‑PDF417 i może **odczytywać wiele kodów kreskowych** z jednego obrazu.

Odczytywanie kodów kreskowych jest powszechnym wymogiem w systemach inwentaryzacji, weryfikacji biletów i przetwarzaniu dokumentów. Po zakończeniu tego samouczka będziesz w stanie:

* Zainicjalizować `BarCodeReader` dla dowolnego obsługiwanego formatu.  
* Wyodrębnić podstawowe informacje, takie jak typ kodu i zdekodowany tekst.  
* Pobrać specyficzne dla Macro‑PDF417 metadane (identyfikator pliku, segment, suma kontrolna, …).  
* Obsłużyć obrazy zawierające kilka kodów kreskowych bez dodatkowego kodu.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

* .NET 6.0 SDK lub nowszy zainstalowany.  
* Środowisko programistyczne (Visual Studio 2022, VS Code lub Rider).  
* Pakiet NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`) – dostarcza klasę `BarCodeReader` używaną w przykładzie.  
* Plik obrazu zawierający kod Macro‑PDF417 (np. `MacroPdf417.png`).  

Możesz zainstalować pakiet NuGet za pomocą następującego polecenia:

```bash
dotnet add package Aspose.BarCode
```

## Jak odczytywać kod kreskowy przy użyciu BarCodeReader w C#

Rdzeń rozwiązania składa się z czterech zwięzłych kroków. Każdy krok jest otoczony blokiem `using`, aby zapewnić szybkie zwolnienie niezarządzanych zasobów.

### Krok 1: Inicjalizacja `BarCodeReader`

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Path to the image that contains the Macro‑PDF417 barcode(s)
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for the specific DecodeType
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The remaining steps are inside this block
}
```

**Dlaczego to ważne:**  
`BarCodeReader` przyjmuje ścieżkę do pliku oraz `DecodeType`. Określenie `DecodeType.MacroPdf417` informuje bibliotekę, aby szukała wyłącznie symboli Macro‑PDF417, co zwiększa szybkość wykrywania i zmniejsza liczbę fałszywych trafień.

### Krok 2: Odczyt wszystkich kodów kreskowych znajdujących się na obrazie

```csharp
    // Step 2: Read all barcodes in the image
    BarCodeResult[] results = reader.ReadBarCodes();
```

**Dlaczego to ważne:**  
Metoda `ReadBarCodes()` zwraca tablicę, która może zawierać jeden lub wiele obiektów `BarCodeResult`. To właśnie w tym miejscu funkcja **odczytywania wielu kodów kreskowych** błyszczy – nie potrzebujesz osobnej pętli dla każdego możliwego kodu.

### Krok 3: Wyświetlenie podstawowych informacji o kodzie

```csharp
    foreach (BarCodeResult result in results)
    {
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

**Dlaczego to ważne:**  
`CodeTypeName` informuje, jaka symbologia została wykryta (np. „MacroPDF417”), natomiast `CodeText` zawiera zdekodowaną treść. Te dwa pola są najczęściej używane w dalszej logice.

### Krok 4: Pobranie i wyświetlenie specyficznych metadanych Macro‑PDF417

```csharp
        // Macro‑PDF417 extended data
        Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
        Console.WriteLine(new string('-', 40));
    }
}
```

**Dlaczego to ważne:**  
Macro‑PDF417 rozszerza standardowy format PDF417 o metadane na poziomie dokumentu. Dostęp do właściwości `Extended.Pdf417` zapewnia wszystko, co potrzebne do odtworzenia oryginalnego pliku, weryfikacji integralności lub przekierowania danych do właściwego odbiorcy.

### Pełny, uruchamialny program

Poniżej znajduje się samodzielna aplikacja konsolowa, która łączy wszystkie cztery kroki. Skopiuj kod do nowego pliku `.cs`, dostosuj `imagePath` i uruchom `dotnet run`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // 1️⃣ Initialise the BarCodeReader for Macro‑PDF417 images
            // ------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // ------------------------------------------------------------
                // 2️⃣ Read all barcodes present in the image
                // ------------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes were detected.");
                    return;
                }

                // ------------------------------------------------------------
                // 3️⃣ Iterate over each result – this is where we **read multiple barcodes**
                // ------------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // ------------------------------------------------------------
                    // 4️⃣ Extract Macro‑PDF417 metadata (c# barcode reader example)
                    // ------------------------------------------------------------
                    Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

#### Oczekiwany wynik w konsoli

```
CodeType: MacroPDF417
CodeText: https://example.com/document
FileID:    12
Segment:   3
Count:     5
FileName:  report.pdf
Checksum:  0x1A2B3C4D
FileSize:  1048576
Time:      2024-08-15T14:23:00Z
Addressee: John Doe
Sender:    Acme Corp.
Terminator:END
----------------------------------------
```

Jeśli obraz zawiera więcej niż jeden symbol Macro‑PDF417, program wypisuje osobny blok dla każdego kodu, demonstrując możliwość **odczytywania wielu kodów kreskowych** bez dodatkowego kodu.

## Obsługa typowych przypadków brzegowych

| Sytuacja | Co zrobić | Powód |
|-----------|------------|--------|
| **Plik nie znaleziony** | Otocz konstrukcję `BarCodeReader` blokiem `try/catch (FileNotFoundException)` i wyświetl przyjazny komunikat. | Zapobiega awarii aplikacji i informuje użytkownika o brakującym zasobie. |
| **Nie wykryto kodu kreskowego** | Sprawdź `results.Length == 0` (jak pokazano w pełnym programie) i obsłuż to łagodnie. | Daje jasną informację zwrotną, gdy obraz nie zawiera żadnej obsługiwanej symbologii. |
| **Inny typ kodu kreskowego** | Zmień `DecodeType.MacroPdf417` na `DecodeType.AllSupportedTypes` lub inną konkretną wartość wyliczenia. | Umożliwia tej samej bazie kodu pracę z QR, Code128, DataMatrix itp., jednocześnie wspierając **odczytywanie wielu kodów kreskowych**. |
| **Duże obrazy** | Ustaw `reader.AutoSize = true` lub zmniejsz skalę obrazu przed przekazaniem go do czytnika. | Poprawia wydajność i zmniejsza obciążenie pamięci w CLR. |
| **Użycie w środowisku wielowątkowym** | Utwórz osobną instancję `BarCodeReader` dla każdego wątku; klasa nie jest bezpieczna wątkowo. | Unika warunków wyścigu w wielowątkowych skanerach lub usługach webowych. |

## Profesjonalne wskazówki dla kodu produkcyjnego

* **Wczesne zwalnianie:** Instrukcja `using` zapewnia szybkie zwolnienie natywnych zasobów (np. buforów obrazu). W usługach działających długo, zwalniaj czytnik natychmiast po zakończeniu przetwarzania każdego obrazu.  
* **Przetwarzanie wsadowe**

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne, działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Odczyt kodu kreskowego z obrazu C# – kompletny przewodnik z Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Jak utworzyć kod macro PDF417 w C# przy użyciu Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Jak odczytać PDF417 w C# – kompletny przykład czytnika kodów kreskowych](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}