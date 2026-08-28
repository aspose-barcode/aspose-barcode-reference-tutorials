---
category: general
date: 2026-07-15
description: Twórz szybkie obrazy kodu kreskowego Planet w C#. Dowiedz się, jak generować
  kod pocztowy i jak zapisać obraz kodu kreskowego jako PNG przy użyciu Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode image
- how to generate postal barcode
- how to save barcode image
language: pl
lastmod: 2026-07-15
og_description: Utwórz obraz kodu kreskowego planet w C#. Ten przewodnik wyjaśnia,
  jak wygenerować kod kreskowy pocztowy oraz jak zapisać obraz kodu kreskowego, podając
  przejrzyste przykłady kodu.
og_image_alt: Screenshot showing a generated Planet barcode image saved as PNG
og_title: Utwórz obraz kodu kreskowego Planet w C# – Szybki przewodnik po kodach pocztowych
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Create planet barcode image quickly with C#. Learn how to generate
    postal barcode and how to save barcode image as PNG using Aspose.BarCode.
  headline: Create Planet Barcode Image in C# – How to Generate Postal Barcode
  type: TechArticle
- description: Create planet barcode image quickly with C#. Learn how to generate
    postal barcode and how to save barcode image as PNG using Aspose.BarCode.
  name: Create Planet Barcode Image in C# – How to Generate Postal Barcode
  steps:
  - name: Why This Structure Works
    text: '- **Separate generators**: We instantiate two `BarcodeGenerator` objects
      because the `FilledBars` property is immutable once an image is rendered. Keeping
      them independent avoids side‑effects. - **X‑dimension choice**: A value of 4
      pixels balances readability and file size. If you need a higher‑reso'
  - name: Changing the Data Payload
    text: 'The `EncodeTypes.Planet` symbology expects numeric data up to 16 digits.
      To encode a different tracking number, just replace `"123456"` with your actual
      string:'
  - name: Adjusting Image Format
    text: If you need a JPEG for web delivery, swap `BarCodeImageFormat.Png` with
      `BarCodeImageFormat.Jpeg`. Remember JPEG introduces compression artifacts—avoid
      it for high‑precision scanning.
  - name: Handling Errors Gracefully
    text: 'When dealing with user‑supplied data, wrap the generation in a try‑catch
      block:'
  type: HowTo
- questions:
  - answer: Yes. Aspose.BarCode supports .NET Framework 4.5 and higher. Just change
      the target framework in your `.csproj` file.
    question: Does this work with .NET Framework 4.5?
  - answer: Replace `EncodeTypes.Planet` with any other enum value (e.g., `EncodeTypes.Code128`).
      The rest of the code stays the same.
    question: What if I need a different barcode symbology?
  - answer: 'Absolutely. Use `generator.Parameters.Barcode.BarColor = Color.Blue;`
      before saving. ## Conclusion You now know **how to create planet barcode image**
      in C#, **how to generate postal barcode** with the Aspose.BarCode library, and
      **how to save barcode image** as PNG files. The full example covered i'
    question: Can I change the bar color?
  type: FAQPage
tags:
- barcode
- C#
- Aspose.BarCode
title: Utwórz obraz kodu kreskowego Planet w C# – Jak wygenerować kod pocztowy
url: /pl/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz obraz kodu kreskowego Planet w C# – Jak wygenerować kod pocztowy

Kiedykolwiek potrzebowałeś **utworzyć obraz kodu kreskowego Planet** w projekcie .NET, ale nie wiedziałeś od czego zacząć? Nie jesteś sam. W tym przewodniku pokażemy **jak wygenerować kod pocztowy** przy użyciu Aspose.BarCode, a następnie **jak zapisać obraz kodu kreskowego** na dysku jako plik PNG.  

Wyobraź sobie, że tworzysz system mailingowy, który na bieżąco drukuje etykiety pocztowe — posiadanie niezawodnego generatora kodów kreskowych oszczędza godziny ręcznej pracy. Po zakończeniu tego samouczka będziesz mieć gotową do uruchomienia aplikację konsolową, która wygeneruje dwa pliki PNG: jeden z wypełnionymi paskami, a drugi tylko z ich konturami.

## Wymagania wstępne

- .NET 6 SDK (lub dowolna nowsza wersja .NET) zainstalowany.
- Visual Studio 2022 lub VS Code z rozszerzeniami C#.
- Pakiet NuGet **Aspose.BarCode for .NET**. Możesz dodać go za pomocą CLI:

```bash
dotnet add package Aspose.BarCode
```

Nie są wymagane żadne inne zewnętrzne zależności.

## Krok 1: Przygotuj szkielet projektu

Najpierw utwórz nowy projekt konsolowy i dodaj bibliotekę kodów kreskowych.

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
dotnet add package Aspose.BarCode
```

Folder teraz zawiera plik `Program.cs`, w którym umieścimy całą naszą logikę.

## Krok 2: Napisz pełny kod – Utwórz obraz kodu kreskowego Planet

Poniżej znajduje się kompletny, samodzielny program. Skopiuj i wklej go do `Program.cs` (nadpisując szablon wygenerowany przez `dotnet new`).

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Namespace and class are optional in a top‑level program (C# 9+), but we keep them for clarity.
namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Create a Planet barcode generator with the desired data.
            // -----------------------------------------------------------------
            // The "Planet" symbology is used by many postal services for
            // tracking and sorting. Here we encode a simple numeric string.
            var generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // ---------------------------------------------------------------
            // 2️⃣  Set the X‑dimension (width of a single bar) to 4 pixels.
            // ---------------------------------------------------------------
            // XDimension controls the visual density of the barcode.
            // 4 px is a common default that works well on most printers.
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // ---------------------------------------------------------------
            // 3️⃣  Save the barcode using the default *filled‑bars* appearance.
            // ---------------------------------------------------------------
            // BarCodeImageFormat.Png ensures a lossless image, perfect for
            // later processing or printing.
            string filledPath = "PlanetFilledBars.png";
            generator.Save(filledPath, BarCodeImageFormat.Png);
            Console.WriteLine($"✔️ Filled bars saved to {filledPath}");

            // -----------------------------------------------------------------
            // 4️⃣  Create another generator for the same data to show empty bars.
            // -----------------------------------------------------------------
            var emptyBarsGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            emptyBarsGenerator.Parameters.Barcode.XDimension.Pixels = 4;

            // ---------------------------------------------------------------
            // 5️⃣  Disable filled bars so only the outlines are drawn.
            // ---------------------------------------------------------------
            emptyBarsGenerator.Parameters.Barcode.FilledBars = false;

            // ---------------------------------------------------------------
            // 6️⃣  Save the barcode with empty bars.
            // ---------------------------------------------------------------
            string emptyPath = "PlanetEmptyBars.png";
            emptyBarsGenerator.Save(emptyPath, BarCodeImageFormat.Png);
            Console.WriteLine($"✔️ Empty bars saved to {emptyPath}");

            // -----------------------------------------------------------------
            // 7️⃣  Quick verification – open the files if you’re on Windows.
            // -----------------------------------------------------------------
            // This is optional but handy when you run the demo locally.
            if (OperatingSystem.IsWindows())
            {
                System.Diagnostics.Process.Start(new System.Diagnostics.ProcessStartInfo
                {
                    FileName = filledPath,
                    UseShellExecute = true
                });
                System.Diagnostics.Process.Start(new System.Diagnostics.ProcessStartInfo
                {
                    FileName = emptyPath,
                    UseShellExecute = true
                });
            }
        }
    }
}
```

### Dlaczego ta struktura działa

- **Oddzielne generatory**: Tworzymy dwa obiekty `BarcodeGenerator`, ponieważ właściwość `FilledBars` jest niezmienna po wyrenderowaniu obrazu. Utrzymanie ich niezależnych zapobiega efektom ubocznym.
- **Wybór wymiaru X**: Wartość 4 piksele zapewnia równowagę między czytelnością a rozmiarem pliku. Jeśli potrzebujesz wydruku o wyższej rozdzielczości, zwiększ ją do 6 lub 8.
- **Zapisywanie jako PNG**: PNG zachowuje ostre krawędzie kodu kreskowego, co jest kluczowe dla skanerów optycznych używanych przez usługi pocztowe.

## Krok 3: Uruchom demonstrację i zweryfikuj wynik

Skompiluj i uruchom program:

```bash
dotnet run
```

Powinieneś zobaczyć komunikaty w konsoli potwierdzające zapisanie dwóch plików. W folderze projektu znajdziesz teraz:

- `PlanetFilledBars.png` – kod kreskowy wypełniony pełnymi paskami.
- `PlanetEmptyBars.png` – tylko kontury pasków.

Poniżej znajduje się wizualna reprezentacja wypełnionej wersji (obraz jest jedynie ilustracją; rzeczywisty wynik może nieco różnić się w zależności od ustawień DPI).

![przykład tworzenia obrazu kodu kreskowego planet](https://example.com/planet-filled.png)

*Tekst alternatywny: przykład tworzenia obrazu kodu kreskowego Planet, pokazujący PNG kodu Planet z wypełnionymi paskami.*

## Krok 4: Dostosowywanie kodu kreskowego – Typowe wariacje

### Zmiana danych wejściowych

Symbologia `EncodeTypes.Planet` oczekuje danych numerycznych do 16 cyfr. Aby zakodować inny numer śledzenia, po prostu zamień `"123456"` na swój rzeczywisty ciąg znaków:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.Planet, "9876543210123456");
```

### Dostosowanie formatu obrazu

Jeśli potrzebujesz JPEG do dostarczania w sieci, zamień `BarCodeImageFormat.Png` na `BarCodeImageFormat.Jpeg`. Pamiętaj, że JPEG wprowadza artefakty kompresji — unikaj go przy skanowaniu o wysokiej precyzji.

### Obsługa błędów w sposób elegancki

Podczas pracy z danymi dostarczonymi przez użytkownika, otocz generowanie w blok try‑catch:

```csharp
try
{
    generator.Save(path, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to save barcode: {ex.Message}");
}
```

Zapewnia to, że aplikacja nie ulegnie awarii przy nieprawidłowym wejściu.

## Krok 5: Integracja z większą aplikacją

W rzeczywistym systemie mailingowym prawdopodobnie generowałbyś kod kreskowy w locie i osadzał go w PDF lub szablonie etykiety. Oto szybki fragment kodu pokazujący, jak uzyskać kod kreskowy jako `byte[]` do dalszego przetwarzania:

```csharp
using System.IO;

// Generate the image in memory
using (MemoryStream ms = new MemoryStream())
{
    generator.Save(ms, BarCodeImageFormat.Png);
    byte[] barcodeBytes = ms.ToArray();

    // Pass barcodeBytes to a PDF library, send over a network, etc.
}
```

Teraz możesz przekazać tablicę bajtów do iTextSharp, QuestPDF lub dowolnego innego generatora dokumentów, nie odwołując się do systemu plików.

## Najczęściej zadawane pytania (FAQ)

**Q: Czy to działa z .NET Framework 4.5?**  
A: Tak. Aspose.BarCode obsługuje .NET Framework 4.5 i wyższe. Wystarczy zmienić docelowy framework w pliku `.csproj`.

**Q: Co zrobić, jeśli potrzebuję innej symbologii kodu kreskowego?**  
A: Zamień `EncodeTypes.Planet` na dowolną inną wartość wyliczenia (np. `EncodeTypes.Code128`). Reszta kodu pozostaje bez zmian.

**Q: Czy mogę zmienić kolor pasków?**  
A: Oczywiście. Użyj `generator.Parameters.Barcode.BarColor = Color.Blue;` przed zapisem.

## Zakończenie

Teraz wiesz **jak utworzyć obraz kodu kreskowego Planet** w C#, **jak wygenerować kod pocztowy** przy użyciu biblioteki Aspose.BarCode oraz **jak zapisać obraz kodu kreskowego** jako pliki PNG. Pełny przykład obejmował inicjalizację, dostosowanie wymiaru X, przełączanie wypełnionych pasków oraz zapisywanie na dysk — plus kilka przydatnych wskazówek do integracji w rzeczywistych aplikacjach.

Gotowy na kolejny krok? Spróbuj osadzić wygenerowany PNG w etykiecie PDF, eksperymentuj z różnymi kolorami lub przejdź na format obrazu o wyższej rozdzielczości. Nie ma ograniczeń, gdy łączysz generowanie kodów kreskowych z nowoczesnymi narzędziami .NET.

Jeśli napotkałeś jakiekolwiek problemy lub masz pomysły na rozszerzenia, zostaw komentarz poniżej. Szczęśliwego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak zapisać PNG przy użyciu DataMatrix C40 z Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [Jak utworzyć strefę ciszy kodu kreskowego dla Code 16K przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Generowanie obrazu kodu kreskowego – Code 93 z Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}