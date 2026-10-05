---
date: 2026-08-17
description: Dowiedz się, jak utworzyć DataMatrix barcode z macro characters przy
  użyciu Aspose.BarCode dla .NET oraz odkryj, jak używać DataMatrix w swoich aplikacjach.
keywords:
- create datamatrix barcode
- datamatrix barcode error correction
- aspose barcode macro
- .net barcode generation
lastmod: 2026-08-17
linktitle: DataMatrix Macro Configuration
og_description: Dowiedz się, jak utworzyć DataMatrix barcode z macro characters przy
  użyciu Aspose.BarCode dla .NET. Ten przewodnik zapewnia step‑by‑step code, customization
  options i verification tips dla reliable barcode generation.
og_image_alt: Guide showing creation of DataMatrix barcode with macro characters in
  .NET using Aspose.BarCode
og_title: Utwórz DataMatrix barcode z macro characters przy użyciu Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  headline: How to create DataMatrix barcode with macro characters in .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  name: How to create DataMatrix barcode with macro characters in .NET
  steps:
  - name: setting up your project
    text: Create a new Console Application (or any .NET project) in Visual Studio.
      Add a reference to the Aspose.BarCode DLLs that you obtained from the download.
  - name: DataMatrix macro configuration
    text: The core of the tutorial – here we actually **create DataMatrix barcode**
      with a macro character. > **Pro tip:** Replace `"ASPOSE"` with any string you
      need to encode. The macro character (`Macro05`) tells scanners that this barcode
      is part of a macro sequence.
  - name: customize barcode parameters for error correction
    text: 'Before saving, you can tweak additional settings: - **XDimension** – controls
      the size of each module (pixel). - **Margin**, **ErrorCorrection**, and **EncodingMode**
      – all accessible via `gen.Parameters.Barcode.DataMatrix`.'
  - name: save the barcode
    text: The snippet above saves the image as `DataMatrixMacro.png` in the folder
      you specified. PNG is loss‑less, making it ideal for further processing.
  - name: recognize the barcode
    text: '`BarCodeReader` is Aspose.BarCode''s class for decoding barcodes from images.
      Using `BarCodeReader` we immediately read back the generated image to confirm
      that the macro character and data are correct. This round‑trip validation is
      especially handy during automated testing.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET is a powerful library that allows .NET developers
      to generate and recognize barcodes in various formats, including DataMatrix,
      QR, and more.
    question: What is Aspose.BarCode for .NET?
  - answer: DataMatrix barcodes are compact, highly reliable, and can store large
      amounts of data, making them ideal for manufacturing, logistics, and healthcare.
    question: Why should I use DataMatrix barcodes?
  - answer: You can find the documentation at [the Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).
    question: Where can I find the documentation for Aspose.BarCode for .NET?
  - answer: Yes, you can download a free trial from [the free trial link](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: If you have any questions or need support, you can visit the Aspose.BarCode
      for .NET forum at [the support forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- aspose.barcode
- c# barcode generation
- macro barcode
- barcode error correction
title: Jak utworzyć DataMatrix barcode with macro characters w .NET
url: /pl/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć kod kreskowy DataMatrix z znakami makro w .NET

## Wprowadzenie

Generowanie **kod kreskowy DataMatrix** zawierającego znaki makro pozwala umieścić dodatkowe informacje referencyjne w małym kwadratowym symbolu. W tym samouczku nauczysz się, jak **utworzyć kod kreskowy DataMatrix** ze znakami makro przy użyciu Aspose.BarCode dla .NET, dostosować rozmiar i poziom korekcji błędów oraz natychmiast zweryfikować wynik. Po zakończeniu będziesz gotowy do osadzania kodów kreskowych z włączonymi makrami na etykietach produktów, dokumentach lub urządzeniach medycznych.

## Szybkie odpowiedzi
- **Jaka jest główna biblioteka?** Aspose.BarCode for .NET  
- **Czy mogę utworzyć kod kreskowy DataMatrix ze znakami makro?** Tak – ustaw właściwość `MacroCharacters`.  
- **Czy potrzebuję licencji do produkcji?** Wymagana jest ważna licencja Aspose do użytku produkcyjnego.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Czy dostępna jest darmowa wersja próbna?** Oczywiście – pobierz ją z oficjalnej strony Aspose.

## Wymagania wstępne

Zanim zagłębisz się w konfigurację makr, upewnij się, że masz następujące elementy:

1. **Visual Studio** – dowolna nowsza edycja będzie działać.  
2. **Aspose.BarCode for .NET** – pobierz go z [the download link](https://releases.aspose.com/barcode/net/).  
3. **Podstawowa znajomość .NET** – znajomość C# i ekosystemu .NET.

## Importowanie przestrzeni nazw

Zaczynamy od zaimportowania przestrzeni nazw niezbędnych do generowania i rozpoznawania kodów kreskowych.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

## Co to jest „generowanie kodu kreskowego DataMatrix” ze znakami makro?

`MacroCharacters` umożliwia kodom DataMatrix zawieranie symboli makro, które odwołują się do dodatkowych danych. Używając znaków makro, takich jak Macro05 lub Macro06, pojedynczy kod może wskazywać na większy zestaw danych lub sekwencję powiązanych kodów, co jest przydatne w logistyce, produkcji i śledzeniu dokumentów, gdzie wymagane jest kompaktowe kodowanie powiązanych informacji.

## Dlaczego używać Aspose.BarCode do generowania kodu kreskowego DataMatrix?

Aspose.BarCode zapewnia precyzyjną kontrolę nad rozmiarem DataMatrix, poziomem korekcji błędów i ustawieniami makr, obsługując ponad 30 symbologii kodów kreskowych i obsługując pliki do 10 MB bez ładowania całego obrazu do pamięci. Jego wieloplatformowa implementacja .NET działa na .NET Framework, .NET Core oraz .NET 5/6 i zawiera wbudowane rozpoznawanie, dzięki czemu możesz natychmiast zweryfikować kod kreskowy.

## Przewodnik krok po kroku

### Krok 1: konfiguracja projektu

Utwórz nową aplikację konsolową (lub dowolny projekt .NET) w Visual Studio. Dodaj odwołanie do bibliotek Aspose.BarCode DLL, które pobrałeś.

### Krok 2: konfiguracja makra DataMatrix

Sedno samouczka – tutaj faktycznie **tworzymy kod kreskowy DataMatrix** ze znakiem makro.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixMacro:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    // Set the macro character to 05
    gen.Parameters.Barcode.DataMatrix.MacroCharacters = MacroCharacter.Macro05;
    gen.Save($"{path}DataMatrixMacro.png", BarCodeImageFormat.Png);

    // Try to recognize it
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixMacro:" + result.CodeText);
    }
}
```

> **Wskazówka:** Zastąp `"ASPOSE"` dowolnym ciągiem, który chcesz zakodować. Znak makro (`Macro05`) informuje skanery, że ten kod jest częścią sekwencji makro.

### Krok 3: dostosowanie parametrów kodu kreskowego pod kątem korekcji błędów

Przed zapisaniem możesz dostosować dodatkowe ustawienia:

- **XDimension** – kontroluje rozmiar każdego modułu (piksel).  
- **Margin**, **ErrorCorrection** i **EncodingMode** – wszystkie dostępne poprzez `gen.Parameters.Barcode.DataMatrix`.

### Krok 4: zapis kodu kreskowego

Powyższy fragment zapisuje obraz jako `DataMatrixMacro.png` w określonym folderze. PNG jest bezstratny, co czyni go idealnym do dalszego przetwarzania.

### Krok 5: rozpoznanie kodu kreskowego

`BarCodeReader` to klasa Aspose.BarCode służąca do dekodowania kodów kreskowych z obrazów. Korzystając z `BarCodeReader` natychmiast odczytujemy wygenerowany obraz, aby potwierdzić, że znak makro i dane są prawidłowe. Ta weryfikacja w obie strony jest szczególnie przydatna podczas testów automatycznych.

## Jak używać DataMatrix w rzeczywistych scenariuszach?

Możesz zastosować kody DataMatrix ze znakami makro do etykietowania produktów, łączenia numerów seryjnych z centralną bazą danych, śledzenia dokumentów poprzez osadzenie odwołania do cyfrowego rekordu oraz tagów sprzętu medycznego, które przechowują dane pacjenta lub urządzenia w małym, skanowalnym symbolu. Te przypadki użycia redukują ręczne wprowadzanie danych i zwiększają możliwość śledzenia.

## Typowe problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| Kod nie rozpoznany | Nieprawidłowy `XDimension` lub niska rozdzielczość obrazu | Zwiększ `XDimension.Pixels` do 4‑6 i zapisz jako PNG lub TIFF |
| Znak makro ignorowany | Czytnik nie obsługuje trybu makro | Użyj skanera/czytnika, który wyraźnie obsługuje makro DataMatrix (np. nowsze wersje ZXing) |
| Ścieżka nie znaleziona | Nieprawidłowa zmienna `path` | Upewnij się, że katalog istnieje lub użyj `Path.Combine` z `Environment.CurrentDirectory` |

## Najczęściej zadawane pytania

**P: Co to jest Aspose.BarCode dla .NET?**  
A: Aspose.BarCode for .NET to potężna biblioteka umożliwiająca programistom .NET generowanie i rozpoznawanie kodów kreskowych w różnych formatach, w tym DataMatrix, QR i innych.

**P: Dlaczego powinienem używać kodów DataMatrix?**  
A: Kody DataMatrix są kompaktowe, bardzo niezawodne i mogą przechowywać duże ilości danych, co czyni je idealnymi dla produkcji, logistyki i opieki zdrowotnej.

**P: Gdzie mogę znaleźć dokumentację Aspose.BarCode dla .NET?**  
A: Dokumentację znajdziesz pod adresem [the Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).

**P: Czy dostępna jest darmowa wersja próbna Aspose.BarCode dla .NET?**  
A: Tak, możesz pobrać darmową wersję próbną z [the free trial link](https://releases.aspose.com/).

**P: Gdzie mogę uzyskać wsparcie dla Aspose.BarCode dla .NET?**  
A: Jeśli masz pytania lub potrzebujesz wsparcia, możesz odwiedzić forum Aspose.BarCode dla .NET pod adresem [the support forum](https://forum.aspose.com/c/barcode/13).

---

**Ostatnia aktualizacja:** 2026-08-17  
**Testowano z:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose

## Powiązane samouczki

- [Utwórz kod kreskowy aspose .net - Konfigurowanie tekstu kodu DataMatrix](/barcode/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Jak generować kody DataMatrix (ECC 200) przy użyciu Aspose.BarCode dla .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Konfiguracja Structured Append DataMatrix z Aspose.BarCode dla .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}