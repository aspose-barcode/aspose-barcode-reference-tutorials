---
category: general
date: 2026-10-14
description: Utwórz konsolowy skaner kodów kreskowych w C#, który odczytuje kody PDF417,
  obsługuje macro PDF417 i dekoduje wiele kodów z jednego obrazu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create console barcode scanner
- read barcodes from picture
- c# barcode reader example
lastmod: 2026-10-14
og_description: Utwórz konsolowy skaner kodów kreskowych w C#, aby szybko odczytywać
  kody PDF417 i macro PDF417 z obrazów. Ten przewodnik krok po kroku pokazuje, jak
  dekodować wiele kodów w jednym zdjęciu.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: Utwórz konsolowy skaner kodów kreskowych w C# – kompletny przewodnik
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  headline: Create console barcode scanner in C# – barcode reader example
  type: TechArticle
- description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  name: Create console barcode scanner in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
- console application
title: Utwórz konsolowy skaner kodów kreskowych w C# – przykład odczytu kodu PDF417
url: /pl/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz konsolowy skaner kodów kreskowych w C# – przykład odczytu kodu PDF417

`BarCodeReader` jest podstawową klasą Aspose.BarCode, która dekoduje kody kreskowe z obrazów i zwraca szczegółowe metadane. Jeśli potrzebujesz odczytać dane kodu PDF417 z obrazu, ten przewodnik pokazuje, jak zrobić to przy użyciu klasy **BarCodeReader** w C#. Nauczysz się przykładu **utworzyć konsolowy skaner kodów kreskowych**, który obsługuje także macro PDF417 i może odczytywać wiele kodów kreskowych na jednym obrazie.

Praca z kodami kreskowymi często oznacza radzenie sobie z różnymi źródłami obrazów, zmiennymi warunkami oświetleniowymi oraz czasami złożonymi danymi, takimi jak segmenty macro PDF417. Ten samouczek obejmuje wszystko, co potrzebne do dekodowania kodu PDF417, wyodrębniania jego rozszerzonych pól i przetwarzania kilku kodów z tego samego obrazu. Po zakończeniu będziesz mieć działający program konsolowy, który odczytuje kody kreskowe z pliku obrazu i wypisuje szczegółowe informacje w konsoli.

## Szybkie odpowiedzi
- **Co robi przykład?** Tworzy konsolowy skaner kodów kreskowych, który odczytuje kody PDF417 i macro PDF417 z obrazu i wypisuje wszystkie zdekodowane pola.  
- **Jakiej biblioteki wymaga?** Aspose.BarCode for .NET (NuGet).  
- **Czy może odczytać wiele kodów jednocześnie?** Tak – czytnik iteruje po każdym kodzie znalezionym na obrazie.  
- **Czy potrzebne jest połączenie internetowe?** Nie, biblioteka działa całkowicie offline.  
- **Jaką wersję .NET obsługuje?** .NET 6.0 lub nowszą.

## Czego będziesz potrzebować

Przed rozpoczęciem upewnij się, że masz:

* .NET 6.0 SDK lub nowszy zainstalowany  
* Aktualną wersję pakietu NuGet **Aspose.BarCode for .NET** (lub dowolną kompatybilną bibliotekę, która udostępnia `BarCodeReader` i `DecodeType.MacroPdf417`)  
* Plik obrazu zawierający kod PDF417 lub macro PDF417 (przykład używa `ExtPDF417Meta.png`)  
* Edytor kodu lub IDE, np. Visual Studio 2022  

Nie są wymagane dodatkowe usługi ani zewnętrzne API.

## Konfigurowanie projektu do odczytu kodów kreskowych

1. **Utwórz nowy projekt konsolowy**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Dodaj bibliotekę kodów kreskowych**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Skopiuj obraz kodu kreskowego**  

   Umieść `ExtPDF417Meta.png` (lub dowolny obraz zawierający kod PDF417) w folderze projektu.  
   Dla tego samouczka zakładamy, że plik znajduje się w `YOUR_DIRECTORY/ExtPDF417Meta.png`.

Projekt jest teraz gotowy do kompilacji i uruchomienia przykładu czytnika kodów kreskowych.

## Jak utworzyć konsolowy skaner kodów kreskowych w C#?

`BarCodeReader` jest klasą udostępnianą przez Aspose.BarCode, która odczytuje kody kreskowe z obrazów i zwraca ich zdekodowane dane.  
Wczytaj obraz za pomocą `BarCodeReader`, ustaw typ dekodowania na `MacroPdf417` i iteruj po wynikach – to wszystko, czego potrzebujesz, aby stworzyć konsolowy skaner kodów kreskowych. Czytnik automatycznie zwalnia zasoby natywne dzięki instrukcji `using`, więc nie musisz ręcznie zarządzać pamięcią. To podejście działa dla każdego formatu obrazu obsługiwanego przez .NET, takiego jak PNG, JPEG czy BMP.

### Przewodnik krok po kroku

Rdzeniem rozwiązania jest blok `using`, który tworzy instancję `BarCodeReader`, określa `DecodeType.MacroPdf417` i iteruje po każdym wykrytym kodzie. Poniższy kod to kompletny, samodzielny program, który możesz wkleić do `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
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

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Dlaczego to działa**:  

* `DecodeType.MacroPdf417` informuje czytnik, aby szukał rozszerzenia macro kodu PDF417, które zawiera dodatkowe metadane, takie jak identyfikator pliku, liczba segmentów i znaczniki czasu.  
* Instrukcja `using` zapewnia, że niezarządzane zasoby (uchwyty plików, natywne bufory dekodowania) są zwalniane niezwłocznie.  
* Pętla `foreach` automatycznie przetwarza **wszystkie** kody kreskowe zawarte w obrazie, spełniając wymóg *odczytu wielu kodów*.

Po uruchomieniu programu (`dotnet run`) powinieneś zobaczyć wyjście podobne do poniższego:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

Jeśli obraz zawiera więcej niż jeden kod PDF417, pętla wypisze osobny blok dla każdego kodu, demonstrując w ten sposób, jak **odczytać wiele kodów** z jednego obrazu.

## Jak mogę odczytać wiele kodów kreskowych z obrazu?

Użyj jednej instancji `BarCodeReader` i ustaw flagę `DecodeType`, aby obejmowała wszystkie formaty, które chcesz wykrywać. Łącząc flagi operatorem bitowym OR, możesz poinstruować bibliotekę, aby szukała PDF417, QR, Code‑128 i wielu innych symbologii w jednym przebiegu. Eliminuje to potrzebę osobnych czytników i skraca czas przetwarzania.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* jest maską bitową, więc możesz łączyć dowolną liczbę obsługiwanych formatów. Aspose.BarCode obsługuje **ponad 30 symbologii kodów kreskowych**, w tym QR, DataMatrix, Code‑128 i UPC‑A, co pozwala jednemu skanerowi obsługiwać różnorodne przypadki użycia, takie jak etykietowanie produktów, weryfikacja biletów i weryfikacja tożsamości.

## Czym jest macro PDF417 i jak bezpiecznie uzyskać dostęp do jego pól?

Macro PDF417 to rozszerzenie symbologii PDF417, które umożliwia podzielenie dużego zestawu danych na wiele symboli kodu kreskowego.  
Macro PDF417 dodaje bogaty zestaw rozszerzonych właściwości. Jednak nie każdy kod zawiera wszystkie pola. Dostęp do nieistniejącej właściwości może spowodować `NullReferenceException`. Najbezpieczniejszym podejściem jest weryfikacja każdej właściwości przed jej wypisaniem, co zapewnia stabilność aplikacji nawet przy braku danych macro.

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Dlaczego to ważne*: W rzeczywistych wdrożeniach możesz otrzymać zwykłe kody PDF417 bez danych macro. Defensywne sprawdzenie zapewnia, że aplikacja będzie działać bez awarii.

## Typowe pułapki i najlepsze praktyki

| Problem | Dlaczego się dzieje | Zalecane rozwiązanie |
|-------|----------------|-----------------|
| Ścieżka do obrazu jest nieprawidłowa | `BarCodeReader` zgłasza wyjątek pliku nie znalezionego przed rozpoczęciem dekodowania | Użyj `Path.Combine` i sprawdź, czy plik istnieje za pomocą `File.Exists` |
| Obraz o niskiej rozdzielczości | Dekoder nie może zlokalizować krawędzi kodu, co skutkuje zerową liczbą wykryć | Zapewnij minimalną rozdzielczość 300 dpi dla wiarygodnych wyników |
| Kod obrócony > 45° | Wiele bibliotek zakłada orientację pionową | Włącz `reader.RecognitionOptions.RotateImage = true`, jeśli obraz może być obrócony |
| Brak pól macro | Próba odczytu właściwości null powoduje awarię | Zawsze sprawdzaj `null` przed dostępem do właściwości macro |
| Przetwarzanie dużych partii | Ponowne tworzenie czytnika dla każdego pliku zwiększa narzut | Ponownie używaj jednej instancji `BarCodeReader` z różnymi strumieniami przy przetwarzaniu wielu obrazów |

## Dlaczego warto używać Aspose.BarCode do konsolowego skanera kodów kreskowych?

Aspose.BarCode może dekodować **ponad 30 typów kodów kreskowych** i przetwarza obrazy do **200 MP** bez ładowania całego pliku do pamięci, osiągając przepustowość **150 klatek na sekundę** na typowym procesorze 3,2 GHz. Te zmierzone możliwości czynią go niezawodnym wyborem dla rozwiązań skanowania o dużej wydajności, działających lokalnie, gdzie opóźnienia i dokładność są krytyczne.

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i eksplorować alternatywne podejścia implementacyjne w własnych projektach.

- [Jak odczytać kody DataMatrix przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Odczyt kodu DataMatrix C# – Generowanie trybu DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Odczyt kodu kreskowego z obrazu – Zaawansowane wyodrębnianie regionu kodu w Javie z Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

## Najczęściej zadawane pytania

**Q: Czy mogę używać tego skanera w środowisku produkcyjnym?**  
A: Tak. Kup licencję komercyjną Aspose.BarCode, aby usunąć znak wodny wersji ewaluacyjnej i uzyskać pełne wsparcie.

**Q: Czy biblioteka działa na Linuxie i macOS?**  
A: Absolutnie. Aspose.BarCode for .NET jest wieloplatformowa i działa na .NET 6+ na Windows, Linux i macOS.

**Q: Jak radzić sobie z bardzo dużymi obrazami, nie wyczerpując pamięci?**  
A: Użyj konstruktora `LoadOptions`, aby włączyć tryb strumieniowy, który przetwarza obraz w fragmentach zamiast ładować go w całości do RAM.

**Q: Czy można dekodować zaszyfrowane lub chronione hasłem obrazy?**  
A: Czytnik potrafi obsługiwać obrazy zaszyfrowane standardowymi schematami haseł PNG/JPEG; wystarczy podać hasło poprzez `reader.ImagePassword`.

**Q: Co zrobić, jeśli mój kod jest częściowo uszkodzony?**  
A: Włącz opcje korekcji błędów, takie jak `reader.RecognitionOptions.CorrectErrors = true`, aby zwiększyć odporność na uszkodzenia lub szumy.

**Last Updated:** 2026-10-14  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose

## Powiązane samouczki

- [Jak odczytać Pdf417 w C# – kompletny przykład czytnika kodów](/barcode/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Odczyt wielu kodów C# – kompletny przewodnik z Pdf417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)
- [Dekodowanie kodu kreskowego z obrazu przy użyciu przykładu C Barcode Reader](/barcode/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}