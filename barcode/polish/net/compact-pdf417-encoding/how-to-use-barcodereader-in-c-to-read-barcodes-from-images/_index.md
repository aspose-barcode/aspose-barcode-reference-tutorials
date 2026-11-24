---
category: general
date: 2026-11-23
description: Dowiedz się, jak używać BarCodeReader w C#, aby odczytywać kody kreskowe
  z obrazu, w tym dekodowanie Macro PDF417, z kompletnym przykładem kodu i jasnymi
  wyjaśnieniami.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use barcodereader
- read barcodes from image c#
language: pl
lastmod: 2026-11-23
og_description: Jak używać BarCodeReader w C#, aby odczytywać kody kreskowe z obrazu.
  Postępuj zgodnie z tym przewodnikiem krok po kroku, aby dekodować Macro PDF417 i
  inne formaty przy użyciu gotowego kodu do uruchomienia.
og_image_alt: Screenshot of BarCodeReader console output showing decoded Macro PDF417
  data
og_title: Jak używać BarCodeReader w C# – szybko odczytywać kody kreskowe z obrazów
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  headline: How to use BarCodeReader in C# to read barcodes from images
  type: TechArticle
- description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  name: How to use BarCodeReader in C# to read barcodes from images
  steps:
  - name: 1. Decoding multiple barcode formats
    text: 'If you need to detect more than one format, pass a combined `DecodeType`
      flag:'
  - name: 2. Managing large images
    text: 'Large images can cause high memory usage. Downscale the image before passing
      it to the reader:'
  - name: 3. Error handling
    text: 'Wrap the reading logic in a try‑catch block to surface decoding failures:'
  type: HowTo
tags:
- barcode
- C#
- image-processing
title: Jak używać BarCodeReader w C# do odczytywania kodów kreskowych z obrazów
url: /pl/net/compact-pdf417-encoding/how-to-use-barcodereader-in-c-to-read-barcodes-from-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak używać BarCodeReader w C# do odczytywania kodów kreskowych z obrazów

Jeśli potrzebujesz **jak używać BarCodeReader** do szybkiego skanowania kodów kreskowych, ten przewodnik pokaże Ci dokładnie to. Niezależnie od tego, czy tworzysz system punktu sprzedaży, czy automatyzujesz przyjmowanie dokumentów, nauczysz się odczytywać kody kreskowe z obrazów w projektach C# przy użyciu kilku linijek kodu.

W tym samouczku zobaczysz kompletny, działający przykład, który dekoduje kod Macro PDF417, wyodrębnia jego rozszerzone właściwości i wypisuje przydatne informacje na konsolę. Nie jest wymagana żadna zewnętrzna dokumentacja – wszystko, czego potrzebujesz, znajduje się tutaj.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

* .NET 6.0 (lub nowszy) zainstalowany – kod jest skierowany do najnowszej wersji LTS.
* Odwołanie do pakietu NuGet **Aspose.BarCode** (lub dowolnego kompatybilnego), który udostępnia `BarCodeReader`.
* Plik obrazu zawierający kod Macro PDF417 (przykład używa `ExtPDF417Meta.png`).

> **Pro tip:** Jeśli używasz Visual Studio, dodaj pakiet za pomocą `dotnet add package Aspose.BarCode` lub interfejsu NuGet Package Manager UI.

## Krok 1: Utwórz instancję BarCodeReader

Pierwszą rzeczą, którą robisz przy pracy z biblioteką kodów kreskowych, jest utworzenie czytnika wskazującego na obraz źródłowy i określającego API, jakie typy kodów ma szukać.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Step 1: Initialise BarCodeReader for a Macro PDF417 image
using (BarCodeReader barcodeReader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png",
           DecodeType.MacroPdf417))
{
    // The using block guarantees proper disposal of native resources.
```

*Dlaczego ten krok ma znaczenie:*  
`BarCodeReader` otwiera obraz, przydziela pamięć natywną i przygotowuje algorytmy dekodowania dla określonego `DecodeType`. Ograniczając typ do `MacroPdf417`, zmniejszasz obciążenie CPU i poprawiasz dokładność wykrywania.

## Krok 2: Odczytaj wszystkie kody kreskowe znalezione na obrazie

Pojedynczy obraz może zawierać wiele kodów kreskowych, szczególnie przy danych makro‑zakodowanych. Metoda `ReadBarCodes` zwraca kolekcję obiektów `BarCodeResult`, z których każdy reprezentuje jeden wykryty kod.

```csharp
    // Step 2: Iterate over every barcode found
    foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
    {
```

*Dlaczego ten krok ma znaczenie:*  
Iterowanie po kolekcji zapewnia przechwycenie każdej instancji, co jest niezbędne w scenariuszach przetwarzania wsadowego lub gdy dokument zawiera kilka kodów.

## Krok 3: Uzyskaj dostęp do rozszerzonych właściwości Macro PDF417

Macro PDF417 przechowuje dodatkowe metadane, takie jak identyfikatory plików, numery segmentów i łączna liczba segmentów. Wartości te są udostępniane przez właściwość `Extended.Pdf417` obiektu `BarCodeResult`.

```csharp
        // Step 3: Pull extended Macro PDF417 information
        var macroInfo = barcodeResult.Extended.Pdf417;
```

*Dlaczego ten krok ma znaczenie:*  
Rozszerzone pola pozwalają odtworzyć dokumenty wielosegmentowe lub zweryfikować, że wszystkie części pochodzą z tego samego źródła. Pominięcie tego kroku dałoby jedynie surowy tekst, tracąc cenny kontekst.

## Krok 4: Wyświetl najbardziej przydatne informacje

Na koniec zapisz dane na konsoli (lub w dowolnym loggerze), aby móc zweryfikować operację odczytu. Przykład wypisuje typ kodu, zdekodowany tekst oraz kilka pól makro.

```csharp
        // Step 4: Display key details
        Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
        Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
        Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
        // Additional macro fields are available:
        // macroInfo.MacroPdf417SegmentID
        // macroInfo.MacroPdf417SegmentsCount
    }
}
```

**Oczekiwany wynik w konsoli**

```
Code Type: MacroPdf417
Code Text: 1234567890
Macro PDF417 File ID: 42
```

> **Uwaga:** Jeśli obraz nie zawiera kodu Macro PDF417, `ReadBarCodes()` zwróci pustą kolekcję i ciało pętli nie zostanie wykonane. Zawsze sprawdzaj, czy wynik nie jest pusty w kodzie produkcyjnym.

## Odczyt kodów kreskowych z obrazu w C# – obsługa typowych scenariuszy

### 1. Dekodowanie wielu formatów kodów kreskowych

Jeśli musisz wykrywać więcej niż jeden format, przekaż połączoną flagę `DecodeType`:

```csharp
using (BarCodeReader reader = new BarCodeReader(
           "sample.png",
           DecodeType.Pdf417 | DecodeType.QR | DecodeType.DataMatrix))
{
    // Same iteration logic as before
}
```

### 2. Zarządzanie dużymi obrazami

Duże obrazy mogą powodować wysokie zużycie pamięci. Zmniejsz rozmiar obrazu przed przekazaniem go do czytnika:

```csharp
using (Bitmap original = new Bitmap("large.png"))
using (Bitmap resized = new Bitmap(original, new Size(1024, 768)))
{
    // Save resized image to a temporary stream and feed it to BarCodeReader
}
```

### 3. Obsługa błędów

Otocz logikę odczytu blokiem try‑catch, aby wyłapać niepowodzenia dekodowania:

```csharp
try
{
    // reading code from previous steps
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Pełny działający przykład

Poniżej znajduje się kompletny program, który możesz skopiować, wkleić i uruchomić. Zawiera wszystkie kroki, niezbędne dyrektywy `using` oraz prostą strukturę obsługi błędów.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(
                       imagePath,
                       DecodeType.MacroPdf417))
            {
                bool anyFound = false;

                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    anyFound = true;
                    var macroInfo = barcodeResult.Extended.Pdf417;

                    Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
                    Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
                    Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {macroInfo.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments Count: {macroInfo.MacroPdf417SegmentsCount}");
                    Console.WriteLine(new string('-', 40));
                }

                if (!anyFound)
                {
                    Console.WriteLine("No barcodes were detected in the image.");
                }
            }
        }
        catch (BarCodeException ex)
        {
            Console.Error.WriteLine($"Error reading barcode: {ex.Message}");
        }
    }
}
```

**Uruchomienie programu** wypisuje każdy wykryty kod Macro PDF417 oraz jego rozszerzone pola, albo informuje, że nie znaleziono żadnych kodów.

## Podsumowanie

Teraz wiesz **jak używać BarCodeReader** do odczytywania kodów kreskowych z obrazów w aplikacjach C#, w tym jak wyodrębniać metadane Macro PDF417. Rozwiązanie obejmuje inicjalizację, iterację, dostęp do rozszerzonych właściwości oraz praktyczne wskazówki dotyczące obsługi wielu formatów, dużych obrazów i błędów.

Następnie możesz zgłębić:

* **Odczyt kodów QR** – zamień `DecodeType.MacroPdf417` na `DecodeType.QR`.
* **Zapisywanie odczytanych danych** do bazy danych lub pliku JSON w celu dalszego przetwarzania.
* **Integrację z ASP.NET Core** w celu przyjmowania przesłanych obrazów poprzez API webowe.

Śmiało eksperymentuj z różnymi typami kodów i źródłami obrazów. Powodzenia w kodowaniu!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu oraz wyjaśnienia krok po kroku, pomagające opanować dodatkowe funkcje API i odkrywać alternatywne podejścia w własnych projektach.

- [samouczek czytnika kodów kreskowych C# – odczyt kodów Macro PDF417 krok po kroku przy użyciu GroupDocs.Barcode](/barcode/english/net/compact-pdf417-encoding/c-barcode-reader-tutorial-read-macro-pdf417-barcodes-step-by/)
- [Jak używać generatora kodów kreskowych C# dla Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/)
- [Odczyt kodu kreskowego z obrazu C# – kompletny przewodnik z Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}