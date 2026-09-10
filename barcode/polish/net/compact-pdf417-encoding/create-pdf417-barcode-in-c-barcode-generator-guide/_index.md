---
category: general
date: 2026-07-18
description: Utwórz kod kreskowy PDF417 w C# przy użyciu generatora PDF417 w C#. Postępuj
  zgodnie z instrukcją krok po kroku, aby zbudować rozszerzony tekst kodu, ustawić
  wygląd i zapisać obraz.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- c# pdf417 barcode generator
language: pl
lastmod: 2026-07-18
og_description: Twórz kod kreskowy PDF417 w C# natychmiast. Ten przewodnik pokazuje,
  jak używać generatora kodów kreskowych PDF417 w C#, skonfigurować tryb rozszerzony
  i wyeksportować PNG.
og_image_alt: Generated PDF417 barcode image created with C# PDF417 barcode generator
og_title: Tworzenie kodu kreskowego PDF417 w C# – Kompletny przewodnik po generatorze
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  headline: Create PDF417 Barcode in C# – Barcode Generator Guide
  type: TechArticle
- description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  name: Create PDF417 Barcode in C# – Barcode Generator Guide
  steps:
  - name: 1. Install the barcode library
    text: 'Open your terminal in the project folder and run:'
  - name: 2. Build the extended codetext
    text: 'PDF417 supports **extended encoding**, allowing you to mix different character
      sets in a single barcode. Below we create three segments:'
  - name: 3. Initialise the **C# PDF417 barcode generator**
    text: Now that we have a valid codetext string, we hand it to the generator. The
      `using` statement ensures the underlying resources are released automatically.
  - name: 4. Configure appearance and encoding mode
    text: 'The default settings give you a tiny barcode that might be hard to read.
      Let’s tweak a few parameters:'
  - name: 5. Save the barcode image
    text: Finally, write the image to disk. The library supports PNG, JPEG, BMP, and
      several vector formats—PNG is a safe default because it preserves crisp edges.
  - name: Handling Unicode and special characters
    text: When you feed Unicode symbols directly into a plain‑text barcode, the generator
      may fall back to a fallback encoding, resulting in garbled output. By using
      `AddECICodetext` you explicitly tell the encoder which character set to apply,
      eliminating guesswork. If you ever need to support **Arabic**, **
  - name: Adjusting error correction level
    text: 'PDF417 offers four error‑correction levels (0‑8). Higher levels increase
      resilience but also enlarge the barcode. Adjust it via:'
  - name: Scaling for print vs. screen
    text: 'For on‑screen display you might keep the default 96 dpi. For high‑resolution
      printing (300 dpi or more), set:'
  - name: Common pitfalls
    text: '- **Missing `using` directive** – Forgetting `using Aspose.BarCode.Encoding;`
      will cause `ECIEncodings` to be undefined. - **Directory not found** – The `Save`
      method won’t create intermediate folders; create them beforehand or use `Path.Combine`
      with `Environment.CurrentDirectory`. - **Wrong encode'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Tworzenie kodu kreskowego PDF417 w C# – Przewodnik generatora kodów kreskowych
url: /pl/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-barcode-generator-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tworzenie kodu kreskowego PDF417 w C# – Przewodnik po generatorze kodów kreskowych

Kiedykolwiek potrzebowałeś **utworzyć kod kreskowy PDF417** w aplikacji C#, ale nie wiedziałeś, od czego zacząć? Nie jesteś sam — wielu programistów napotyka ten sam problem, gdy po raz pierwszy zajmuje się kodami kreskowymi dwuwymiarowymi. Dobra wiadomość? Dzięki wbudowanemu **generatorowi kodów kreskowych PDF417 w C#** możesz stworzyć w pełni funkcjonalny kod kreskowy w zaledwie kilku linijkach.

W tym samouczku przejdziemy krok po kroku przez cały proces: budowanie rozszerzonego tekstu kodu, który miesza różne zestawy znaków, konfigurowanie generatora pod odpowiedni styl wizualny oraz ostateczne zapisanie kodu kreskowego jako plik PNG. Po zakończeniu będziesz mieć gotowy fragment kodu, który możesz wkleić do dowolnego projektu .NET, oraz wskazówki dotyczące obsługi przypadków brzegowych, takich jak znaki Unicode czy własne szerokości modułów.

---

## Czego będziesz potrzebować

Zanim zaczniemy, upewnij się, że masz na swoim komputerze następujące elementy:

- **.NET 6.0** lub nowszy (przykład działa również z .NET Framework 4.6+)
- **Aspose.BarCode for .NET** (lub dowolną kompatybilną bibliotekę udostępniającą `BarcodeGenerator`, `EncodeTypes.Pdf417` itp.)
- Edytor kodu — Visual Studio, Rider lub nawet VS Code
- Folder, do którego możesz zapisywać pliki, ponieważ generator zapisze tam PNG

To wszystko — nie potrzebujesz dodatkowych pakietów NuGet poza samą biblioteką kodów kreskowych.

---

## Przewodnik krok po kroku do **utworzenia kodu kreskowego PDF417**

### 1. Zainstaluj bibliotekę kodów kreskowych

Otwórz terminal w folderze projektu i uruchom:

```bash
dotnet add package Aspose.BarCode
```

Pakiet dodaje przestrzeń nazw `Aspose.BarCode`, w której znajduje się klasa `BarcodeGenerator` używana w dalszej części.

### 2. Zbuduj rozszerzony tekst kodu

PDF417 obsługuje **rozszerzone kodowanie**, pozwalające mieszać różne zestawy znaków w jednym kodzie kreskowym. Poniżej tworzymy trzy segmenty:

- Segment Windows‑1251 (cyrylica)
- Segment UTF‑8 zawierający znaki Unicode (japońskie kanji „pies” i „prawo”)
- Segment zwykłego tekstu

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

// Step 1: Build the extended codetext for the PDF417 barcode
Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();

// Add a Win1251‑encoded segment
builder.AddECICodetext(ECIEncodings.Win1251, "Will");

// Add a UTF‑8 segment with Unicode characters
builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");

// Add a plain‑text segment
builder.AddPlainCodetext("Plain text");

// Retrieve the combined codetext string
string extendedCodetext = builder.GetExtendedCodetext();
```

**Dlaczego to ważne:**  
Jeśli używasz wyłącznie zwykłego tekstu, jesteś ograniczony do domyślnego podzbioru ASCII. Deklarując wyraźnie segmenty ECI (Extended Channel Interpretation), zapewniasz, że skanery prawidłowo interpretują każdą część, niezależnie od języka czy użytych symboli.

### 3. Zainicjuj **generator kodu kreskowego PDF417 w C#**

Mając już prawidłowy ciąg tekstowy, przekazujemy go generatorowi. Instrukcja `using` zapewnia automatyczne zwolnienie zasobów.

```csharp
// Step 2: Create a PDF417 barcode generator using the extended codetext
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
{
    // Configuration goes here (see next step)
}
```

### 4. Skonfiguruj wygląd i tryb kodowania

Domyślne ustawienia dają mały kod kreskowy, który może być trudny do odczytania. Dostosujmy kilka parametrów:

- **X‑Dimension** – kontroluje szerokość każdego modułu (rozmiar w pikselach)
- **EncodeMode** – informuje silnik, że wejście ma być traktowane jako tryb rozszerzony
- **TwoDDisplayText** – opcjonalny tekst czytelny dla człowieka wyświetlany pod kodem kreskowym

```csharp
    // Step 3: Configure barcode appearance and encoding mode
    generator.Parameters.Barcode.XDimension.Pixels = 15; // Wider modules for better scannability
    generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended; // Activate extended encoding
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode"; // Display text under the symbol
```

**Wskazówka dla profesjonalistów:** Jeśli drukujesz kod kreskowy na drukarce etykiet, zwiększ `XDimension` do 20 px lub więcej; większość skanerów lubi nieco dodatkowej przestrzeni.

### 5. Zapisz obraz kodu kreskowego

Na koniec zapisz obraz na dysku. Biblioteka obsługuje PNG, JPEG, BMP oraz kilka formatów wektorowych — PNG jest bezpiecznym domyślnym wyborem, ponieważ zachowuje ostre krawędzie.

```csharp
    // Step 4: Save the generated barcode image
    generator.Save("YOUR_DIRECTORY/Pdf417Extended.png", BarCodeImageFormat.Png);
}
```

Upewnij się, że `YOUR_DIRECTORY` istnieje i jest zapisywalny. Po uruchomieniu programu powinieneś zobaczyć plik podobny do zrzutu ekranu poniżej.

![Wygenerowany kod kreskowy PDF417 utworzony przy użyciu generatora kodów kreskowych PDF417 w C#](https://example.com/images/pdf417-extended.png "Wygenerowany kod kreskowy PDF417 utworzony przy użyciu generatora kodów kreskowych PDF417 w C#")

---

## Użycie **generatora kodów kreskowych PDF417 w C#** – głębsze spojrzenie

### Obsługa Unicode i znaków specjalnych

Gdy wprowadzisz symbole Unicode bezpośrednio do kodu kreskowego zwykłego tekstu, generator może przejść na kodowanie awaryjne, co skutkuje zniekształconym wynikiem. Używając `AddECICodetext`, wyraźnie informujesz enkoder, którego zestaw znaków ma zastosować, eliminując zgadywanie. Jeśli kiedykolwiek będziesz musiał obsłużyć **arabskie**, **hebrajskie** lub **emoji**, po prostu wybierz odpowiednią wartość `ECIEncodings`.

### Dostosowanie poziomu korekcji błędów

PDF417 oferuje cztery poziomy korekcji błędów (0‑8). Wyższe poziomy zwiększają odporność, ale także powiększają kod kreskowy. Dostosuj je za pomocą:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // Balanced level
```

### Skalowanie dla druku vs. ekranu

Do wyświetlania na ekranie możesz pozostać przy domyślnych 96 dpi. Dla druku wysokiej rozdzielczości (300 dpi lub więcej) ustaw:

```csharp
generator.Parameters.ImageResolution = 300;
```

Zapewni to, że zapisany PNG zachowa wystarczającą szczegółowość dla drukarek laserowych.

### Typowe pułapki

- **Brak dyrektywy `using`** – Zapomnienie o `using Aspose.BarCode.Encoding;` spowoduje, że `ECIEncodings` będzie niezdefiniowane.
- **Nie znaleziono katalogu** – Metoda `Save` nie tworzy pośrednich folderów; utwórz je wcześniej lub użyj `Path.Combine` z `Environment.CurrentDirectory`.
- **Nieprawidłowy tryb kodowania** – Jeśli pozostawisz `EncodeMode` jako `Pdf417EncodeMode.Auto`, biblioteka może potraktować Twój rozszerzony tekst jako zwykły, usuwając znaczniki ECI.

---

## Pełny, gotowy do uruchomienia przykład

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

class Program
{
    static void Main()
    {
        // 1️⃣ Build extended codetext
        Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();
        builder.AddECICodetext(ECIEncodings.Win1251, "Will");
        builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
        builder.AddPlainCodetext("Plain text");
        string extendedCodetext = builder.GetExtendedCodetext();

        // 2️⃣ Initialise generator with the extended codetext
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
        {
            // 3️⃣ Configure appearance
            generator.Parameters.Barcode.XDimension.Pixels = 15;
            generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended;
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
            generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode";

            // 4️⃣ Save to PNG (ensure the folder exists)
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "Pdf417Extended.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }

        Console.WriteLine("PDF417 barcode generated successfully!");
    }
}
```


## Co powinieneś nauczyć się dalej?


Poniższe samouczki dotyczą ściśle powiązanych tematów, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu wraz z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}