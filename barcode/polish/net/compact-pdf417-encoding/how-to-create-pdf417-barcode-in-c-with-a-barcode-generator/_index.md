---
category: general
date: 2026-11-17
description: Dowiedz się, jak stworzyć kod kreskowy PDF417 w C# – kompletny przewodnik,
  jak generować kod kreskowy z ciągu znaków przy użyciu generatora kodów kreskowych
  w C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode
- c# barcode generator
- generate barcode from string
- create gs1 barcode
language: pl
lastmod: 2026-11-17
og_description: Szybko utwórz kod kreskowy PDF417 w C#. Ten samouczek pokazuje, jak
  wygenerować kod kreskowy z ciągu znaków przy użyciu generatora kodów kreskowych
  w C# i zawiera pełny kod źródłowy.
og_image_alt: Screenshot of a generated PDF417 barcode created with a C# barcode generator
og_title: Tworzenie kodu kreskowego PDF417 w C# – przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  headline: How to create PDF417 barcode in C# with a barcode generator
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  name: How to create PDF417 barcode in C# with a barcode generator
  steps:
  - name: Expected output
    text: '![Generated PDF417 barcode showing the GTIN (01)12345678901234](/images/pdf417-sample.png){:
      .center-image alt="Generated PDF417 barcode created with a C# barcode generator"}'
  - name: Changing the image format
    text: If you prefer JPEG or BMP, just replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`
      or `BarCodeImageFormat.Bmp`. The rest of the code stays identical.
  - name: Adjusting error correction level
    text: PDF417 supports error correction levels 0‑8. Higher levels increase redundancy
      but also enlarge the barcode.
  - name: Generating other GS1 barcodes
    text: 'The same `BarcodeGenerator` can produce **create GS1 barcode** for other
      symbologies, such as `EncodeTypes.Gs1DataMatrix` or `EncodeTypes.Gs1Qr`. Just
      swap the enum value:'
  - name: Handling empty or null data
    text: 'When you **generate barcode from string**, always validate the input:'
  type: HowTo
- questions:
  - answer: Yes. The Aspose.BarCode library targets .NET Standard 2.0, which is compatible
      with .NET Framework 4.6 and later.
    question: Can I use this code on .NET Framework 4.6?
  - answer: 'Set the `Resolution` property before saving: ```csharp generator.Parameters.ImageResolution.DpiX
      = 300; generator.Parameters.ImageResolution.DpiY = 300; ```'
    question: What if I need a higher‑resolution image?
  - answer: 'It will be a standard PDF417 barcode, but it won’t be recognized as a
      GS1‑compliant symbol. Include the `(01)` prefix when you need **create GS1 barcode**
      compliance. ## Conclusion You now know how to **create PDF417 barcode** in C#
      using a robust **c# barcode generator**. The tutorial covered: * In'
    question: Is the barcode still valid without the GS1 Application Identifier?
  type: FAQPage
tags:
- barcode
- C#
- PDF417
- GS1
- code generation
title: Jak utworzyć kod kreskowy PDF417 w C# przy użyciu generatora kodów kreskowych
url: /pl/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć kod kreskowy PDF417 w C# przy użyciu generatora kodów kreskowych

Jeśli potrzebujesz **utworzyć kod kreskowy PDF417** w aplikacji .NET, ten przewodnik pokazuje dokładnie, jak to zrobić. Dowiesz się **jak generować kod kreskowy** z prostego ciągu znaków, skonfigurować rozmiar symbolu i zapisać wynik jako plik PNG — wszystko przy użyciu niezawodnego generatora kodów kreskowych w C#.

Programowe generowanie kodów kreskowych eliminuje ręczne czynności i zapewnia jednolitą jakość. W tym samouczku omówimy wszystko, od konfiguracji projektu po ostateczny obraz, abyś mógł już dziś zintegrować tworzenie kodów kreskowych z dowolnym rozwiązaniem w C#.

## Wymagania wstępne

* .NET 6.0 SDK lub nowszy (kod działa z .NET Core i .NET Framework)
* Visual Studio 2022 (lub dowolne IDE obsługujące C#)
* Licencja lub bezpłatna wersja próbna **Aspose.BarCode for .NET** – biblioteka używana w przykładach
* Podstawowa znajomość składni C#

Nie są wymagane dodatkowe pakiety; pakiet NuGet `Aspose.BarCode` zawiera wszystkie potrzebne klasy.

## Krok 1 – Konfiguracja generatora kodów kreskowych w C#

Pierwszą rzeczą, którą robisz przy **tworzeniu kodu kreskowego PDF417**, jest utworzenie obiektu `BarcodeGenerator`. Obiekt ten reprezentuje **generator kodów kreskowych w C#**, który zajmuje się kodowaniem, renderowaniem i zapisywaniem.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for PDF417 with the data to encode
        // The data string follows the GS1 Application Identifier (01) for a GTIN
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417, "(01)12345678901234");
```

*Dlaczego to jest ważne*: Enum `EncodeTypes.Pdf417` informuje bibliotekę, aby użyła symbologii PDF417, która jest tym samym standardem stosowanym w kartach identyfikacyjnych i etykietach transportowych. Ciąg `"(01)12345678901234"` jest przykładem **generowania kodu kreskowego z ciągu znaków**, który jednocześnie pokazuje, jak **utworzyć kod GS1**.

## Krok 2 – Konfiguracja wymiaru X (szerokość modułu)

Wymiar X kontroluje szerokość najmniejszego paska (modułu). Typową wartością przy renderowaniu na ekranie jest 2 piksele.

```csharp
        // Step 2: Set the X‑dimension (module width) to 2 pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Ustawienie wymiaru X explicite zapobiega użyciu domyślnej wartości przez generator, co mogłoby spowodować, że kod kreskowy będzie zbyt mały dla niektórych skanerów.

## Krok 3 – Definiowanie liczby kolumn

PDF417 pozwala dostosować liczbę kolumn, co wpływa zarówno na kształt kodu kreskowego, jak i pojemność danych. Dla kompaktowej etykiety dobrze sprawdzają się cztery kolumny.

```csharp
        // Step 3: Define the number of columns (e.g., 4) for a compact barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

Jeśli potrzebujesz wyższego kodu kreskowego, zwiększ liczbę kolumn; biblioteka automatycznie obliczy wymaganą liczbę wierszy.

## Krok 4 – Zapisz kod kreskowy jako obraz

Na koniec wyeksportuj kod kreskowy do pliku PNG. PNG zachowuje ostre krawędzie i obsługuje przezroczystość.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("output/Gs1Pdf417.png", BarCodeImageFormat.Png);
    }
}
```

Uruchomienie programu tworzy `output/Gs1Pdf417.png`. Otwórz plik w dowolnej przeglądarce obrazów — zobaczysz czysty **kod kreskowy PDF417**, który koduje podane przez Ciebie dane GS1.

### Oczekiwany wynik

![Wygenerowany kod kreskowy PDF417 pokazujący GTIN (01)12345678901234](/images/pdf417-sample.png){: .center-image alt="Wygenerowany kod kreskowy PDF417 utworzony przy użyciu generatora kodów kreskowych w C#"}

*Powyższy obraz przedstawia wynik pełnego przykładu kodu. Kod kreskowy może być zeskanowany przez dowolny czytnik kompatybilny z PDF417.*

## Dodatkowe opcje i typowe wariacje

### Zmiana formatu obrazu

Jeśli wolisz JPEG lub BMP, po prostu zamień `BarCodeImageFormat.Png` na `BarCodeImageFormat.Jpeg` lub `BarCodeImageFormat.Bmp`. Reszta kodu pozostaje niezmieniona.

### Dostosowanie poziomu korekcji błędów

PDF417 obsługuje poziomy korekcji błędów od 0 do 8. Wyższe poziomy zwiększają nadmiarowość, ale także powiększają kod kreskowy.

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // medium redundancy
```

### Generowanie innych kodów GS1

Ten sam `BarcodeGenerator` może generować **utworzyć kod GS1** dla innych symbologii, takich jak `EncodeTypes.Gs1DataMatrix` lub `EncodeTypes.Gs1Qr`. Wystarczy zamienić wartość enum:

```csharp
BarcodeGenerator gs1Generator = new BarcodeGenerator(
    EncodeTypes.Gs1DataMatrix, "(01)12345678901234");
```

### Obsługa pustych lub null danych

Kiedy **generujesz kod kreskowy z ciągu znaków**, zawsze waliduj dane wejściowe:

```csharp
string data = GetUserInput();
if (string.IsNullOrWhiteSpace(data))
{
    throw new ArgumentException("Data to encode cannot be null or empty.");
}
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
```

Zapobiega to wyjątkom w czasie wykonywania i zapewnia, że kod kreskowy spełnia zasady formatowania GS1.

## Pełny, gotowy do uruchomienia przykład

Poniżej znajduje się pełny program, który możesz skopiować i wkleić do nowego projektu konsolowego. Zawiera wszystkie niezbędne dyrektywy `using`, tworzenie folderu oraz obsługę błędów.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Input data – GS1 GTIN with Application Identifier (01)
        const string gs1Data = "(01)12345678901234";

        // Validate input
        if (string.IsNullOrWhiteSpace(gs1Data))
        {
            Console.WriteLine("Error: Barcode data cannot be empty.");
            return;
        }

        // Ensure output directory exists
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);

        // Create the generator for PDF417 (GS1 optional)
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417, gs1Data);

        // Configure appearance
        generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
        generator.Parameters.Barcode.Pdf417.Columns = 4;    // compact layout
        generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // optional

        // Save as PNG
        string outputPath = Path.Combine(outputDir, "Gs1Pdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

**Uruchom program** (`dotnet run`) i znajdziesz `Gs1Pdf417.png` w folderze *output*. Zeskanuj go dowolnym czytnikiem PDF417, aby zweryfikować, że GTIN `(01)12345678901234` jest poprawnie zakodowany.

## Najczęściej zadawane pytania

**Q: Czy mogę używać tego kodu na .NET Framework 4.6?**  
A: Tak. Biblioteka Aspose.BarCode jest przeznaczona dla .NET Standard 2.0, który jest kompatybilny z .NET Framework 4.6 i nowszymi.

**Q: Co zrobić, jeśli potrzebuję obrazu o wyższej rozdzielczości?**  
A: Ustaw właściwość `Resolution` przed zapisem:

```csharp
generator.Parameters.ImageResolution.DpiX = 300;
generator.Parameters.ImageResolution.DpiY = 300;
```

**Q: Czy kod kreskowy jest nadal ważny bez identyfikatora aplikacji GS1?**  
A: Będzie to standardowy kod PDF417, ale nie zostanie rozpoznany jako symbol zgodny z GS1. Dodaj prefiks `(01)`, gdy potrzebujesz **utworzyć kod GS1**.

## Zakończenie

Teraz wiesz, jak **utworzyć kod kreskowy PDF417** w C# przy użyciu solidnego **generatora kodów kreskowych w C#**. Samouczek obejmował:

* Tworzenie instancji `BarcodeGenerator` z danymi GS1  
* Konfigurację wymiaru X i liczby kolumn  
* Zapis wyniku jako obrazu PNG  
* Rozszerzenie rozwiązania o korekcję błędów, różne formaty i walidację danych wejściowych  

Mając tę podstawę, możesz generować dowolny kod PDF417 lub GS1 bezpośrednio z ciągu znaków, osadzać go w raportach lub wysyłać do drukarek. Zapoznaj się z API Aspose.BarCode, aby dodać kolory, marginesy lub połączyć wiele kodów kreskowych w jeden obraz.

**Kolejne kroki**: spróbuj wygenerować **utworzyć kod GS1** dla DataMatrix, eksperymentuj z dynamicznymi obliczeniami kolumn lub zintegrować generator z usługą webową ASP.NET Core, która zwraca obrazy kodów kreskowych na żądanie.

Miłego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak wygenerować kod kreskowy PDF417 w C# – kompletny przewodnik](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-guide/)
- [Jak utworzyć mikro kod PDF417 i wygenerować PNG w C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)
- [Jak utworzyć makro kod PDF417 w C# przy użyciu Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}