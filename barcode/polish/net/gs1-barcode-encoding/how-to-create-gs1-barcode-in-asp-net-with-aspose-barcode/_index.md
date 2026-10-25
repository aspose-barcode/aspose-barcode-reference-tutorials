---
category: general
date: 2026-10-24
description: Dowiedz się, jak tworzyć kod kreskowy GS1 w ASP.NET przy użyciu Aspose.BarCode.
  Przewodnik krok po kroku, jak wygenerować kod kreskowy z ciągu znaków i wyświetlić
  go jako PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to create GS1 barcode
- generate barcode from string
- barcode generator asp.net
- create barcode with aspose
language: pl
lastmod: 2026-10-24
og_description: Jak utworzyć kod kreskowy GS1 w ASP.NET przy użyciu Aspose.BarCode.
  Postępuj zgodnie z tym samouczkiem, aby wygenerować kod kreskowy z ciągu znaków,
  skonfigurować ustawienia wizualne i zapisać pliki PNG.
og_image_alt: Screenshot of a generated GS1 Micro PDF417 barcode saved as PNG
og_title: Jak utworzyć kod kreskowy GS1 w ASP.NET – kompletny przewodnik Aspose
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  headline: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  type: TechArticle
- description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  name: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  steps:
  - name: 4.1 Prepare the GS1 data string
    text: 'GS1 data must be wrapped in parentheses with the AI code. For a product
      identifier (01) and a batch number (10) the string looks like:'
  - name: 4.2 Build the GS1 Micro PDF417 generator
    text: '```csharp public static byte[] GenerateGs1MicroPdf417(string gs1Data, string
      outputFolder) { // Step 4.2.1: Create a generator for Micro PDF417 using the
      GS1 data. BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417,
      gs1Data);'
  - name: 4.3 Expose the generator through an ASP.NET endpoint
    text: '```csharp app.MapGet("/gs1barcode", (HttpContext context) => { string outputFolder
      = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes"); Directory.CreateDirectory(outputFolder);
      // Ensure the folder exists'
  type: HowTo
tags:
- Aspose.BarCode
- GS1
- ASP.NET
- C#
title: Jak utworzyć kod kreskowy GS1 w ASP.NET z Aspose.BarCode
url: /pl/net/gs1-barcode-encoding/how-to-create-gs1-barcode-in-asp-net-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć kod kreskowy GS1 w ASP.NET z Aspose.BarCode

Jeśli potrzebujesz **jak utworzyć kod kreskowy GS1** w aplikacji ASP.NET, ten przewodnik pokaże Ci dokładne kroki. Zobaczysz, jak wygenerować kod kreskowy z ciągu znaków, skonfigurować wygląd oraz zapisać wynik jako obraz PNG.

Tworzenie kodów kreskowych GS1 nie wymaga własnej logiki kodowania. Korzystając z Aspose.BarCode otrzymujesz niezawodne, zgodne ze standardami rozwiązanie działające na .NET 6+ oraz wcześniejszych frameworkach. Ten tutorial obejmuje wszystko od konfiguracji projektu po weryfikację wyniku, dzięki czemu możesz skopiować kod bezpośrednio do własnego projektu webowego.

## Wymagania wstępne

* Visual Studio 2022 (lub dowolne IDE obsługujące .NET)
* .NET 6 SDK (lub .NET Framework 4.7.2 i wyższy)
* Podstawowa znajomość ASP.NET Core lub ASP.NET Framework
* Licencja Aspose.BarCode (darmowa wersja ewaluacyjna działa do testów)

Nie są wymagane dodatkowe biblioteki firm trzecich, ponieważ Aspose.BarCode obsługuje całe kodowanie i renderowanie wewnętrznie.

## Krok 1: Utwórz nowy projekt ASP.NET

Otwórz Visual Studio i utwórz **ASP.NET Core Web App** (wybierz szablon *Empty*). Dla klasycznego projektu Web Forms ten sam kod działa w pliku code‑behind.

```csharp
// Program.cs (ASP.NET Core minimal API example)
using Microsoft.AspNetCore.Builder;
using Microsoft.Extensions.Hosting;

var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.MapGet("/", () => "GS1 barcode generator is ready.");
app.Run();
```

Uruchomienie projektu powinno wyświetlić *GS1 barcode generator is ready.* w przeglądarce. Potwierdza to, że host webowy działa.

## Krok 2: Zainstaluj Aspose.BarCode za pomocą NuGet

Otwórz **Package Manager Console** i uruchom:

```powershell
Install-Package Aspose.BarCode
```

Pakiet dodaje przestrzeń nazw `Aspose.BarCode.Generation`, która zawiera klasę `BarcodeGenerator` używaną do **generate barcode from string**. Polecenie NuGet aktualizuje również plik projektu o wymaganą referencję.

## Krok 3: Wygeneruj prosty kod kreskowy z ciągu znaków

Aby zilustrować podstawowe użycie, utwórz metodę pomocniczą zwracającą tablicę bajtów PNG. Metodę tę można wywołać z kontrolera, strony Razor lub dowolnego punktu końcowego.

```csharp
using Aspose.BarCode.Generation;
using System.IO;

/// <summary>
/// Generates a barcode image from the supplied text.
/// </summary>
/// <param name="text">The data to encode.</param>
/// <param name="encodeType">The barcode symbology.</param>
/// <returns>PNG image bytes.</returns>
public static byte[] GenerateBarcode(string text, EncodeTypes encodeType)
{
    // Step 3.1: Initialize the generator with the desired symbology and data.
    BarcodeGenerator generator = new BarcodeGenerator(encodeType, text);

    // Step 3.2: Set a modest module width – 2 pixels gives a clear image.
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 3.3: Render the barcode to a memory stream in PNG format.
    using MemoryStream ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return ms.ToArray();
}
```

Możesz teraz wywołać `GenerateBarcode("HelloWorld", EncodeTypes.Code128)` z dowolnego punktu końcowego i zapisać otrzymane bajty w odpowiedzi HTTP. To demonstruje wzorzec **barcode generator asp.net** dla dowolnych ciągów.

## Krok 4: Jak utworzyć kod kreskowy GS1 – przykład Micro PDF417

Kody kreskowe GS1 zawierają identyfikatory aplikacji (AI), które przekazują informacje o produkcie. Aspose.BarCode obsługuje wariant Micro PDF417 zgodny z GS1, idealny do kompaktowej reprezentacji danych.

### 4.1 Przygotuj ciąg danych GS1

Dane GS1 muszą być otoczone nawiasami wraz z kodem AI. Dla identyfikatora produktu (01) i numeru partii (10) ciąg wygląda następująco:

```csharp
string gs1Data = "(01)12345678901234(10)ABCD";
```

Nawiasy są częścią standardu; Aspose.BarCode parsuje je automatycznie.

### 4.2 Zbuduj generator GS1 Micro PDF417

```csharp
public static byte[] GenerateGs1MicroPdf417(string gs1Data, string outputFolder)
{
    // Step 4.2.1: Create a generator for Micro PDF417 using the GS1 data.
    BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);

    // Step 4.2.2: Apply the same visual settings used for other barcodes.
    gs1Generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 4.2.3: Micro PDF417 allows 1‑4 columns; 4 gives a more square shape.
    gs1Generator.Parameters.Barcode.Pdf417.Columns = 4;

    // Step 4.2.4: Save the image to the specified folder.
    string filePath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
    gs1Generator.Save(filePath, BarCodeImageFormat.Png);

    // Return the file bytes for immediate HTTP response if needed.
    return File.ReadAllBytes(filePath);
}
```

### 4.3 Udostępnij generator przez punkt końcowy ASP.NET

```csharp
app.MapGet("/gs1barcode", (HttpContext context) =>
{
    string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes");
    Directory.CreateDirectory(outputFolder); // Ensure the folder exists

    byte[] pngBytes = GenerateGs1MicroPdf417("(01)12345678901234(10)ABCD", outputFolder);

    context.Response.ContentType = "image/png";
    return context.Response.Body.WriteAsync(pngBytes, 0, pngBytes.Length);
});
```

Odwiedzenie `https://localhost:5001/gs1barcode` teraz przesyła wygenerowany PNG. Obraz spełnia specyfikację GS1, a plik jest również zapisywany na dysku do późniejszego użycia.

## Krok 5: Renderowanie dodatkowych typów kodów kreskowych

To samo podejście **create barcode with aspose** działa dla innych symbologii. Poniżej szybki przykład tworzący kod QR z adresu URL:

```csharp
byte[] qrBytes = GenerateBarcode("https://example.com", EncodeTypes.QR);
File.WriteAllBytes(Path.Combine(outputFolder, "ExampleQR.png"), qrBytes);
```

Możesz zamienić `EncodeTypes.QR` na `EncodeTypes.Code128`, `EncodeTypes.DataMatrix` lub dowolny inny obsługiwany typ. Parametry wizualne (`XDimension`, `Resolution`, `Color`) są konfigurowalne za pomocą obiektu `Parameters`.

## Krok 6: Typowe pułapki i wskazówki najlepszych praktyk

| Problem | Dlaczego się pojawia | Jak tego uniknąć |
|-------|----------------|-----------------|
| **Nieprawidłowe formatowanie AI** | Brakujące nawiasy lub nieprawidłowa długość AI powodują błędy kodowania. | Zawsze twórz ciąg GS1 dokładnie zgodnie ze specyfikacją standardu. Użyj metody pomocniczej do łączenia AI. |
| **Zbyt wiele kolumn** | Micro PDF417 obsługuje tylko 1‑4 kolumny; ustawienie 5 powoduje wyjątek. | Sprawdź wartość kolumny przed przypisaniem: `if (columns < 1 || columns > 4) throw …` |
| **Niska rozdzielczość obrazu** | Małe wartości `XDimension` mogą sprawić, że kod kreskowy będzie nieczytelny na drukarkach. | Dla kodów gotowych do druku zwiększ `Resolution` (np. `generator.Parameters.Image.Resolution = 300`). |
| **Problemy ze ścieżkami plików na Linux** | Twardo zakodowane backslashe powodują problemy na hostach nie‑Windowsowych. | Użyj `Path.Combine` do budowania ścieżek plików; obsługuje on separatory specyficzne dla systemu operacyjnego. |
| **Licencja nie zastosowana** | Wersja ewaluacyjna dodaje znak wodny po 30 dniach. | Zastosuj licencję wcześnie: `new License().SetLicense("Aspose.BarCode.lic");` |

## Krok 7: Zweryfikuj wygenerowany kod kreskowy

Po uruchomieniu punktu końcowego otwórz PNG w dowolnym przeglądarce obrazów. Aby potwierdzić, że dane GS1 są poprawnie zakodowane, możesz użyć darmowego skanera mobilnego obsługującego GS1 Micro PDF417 (wiele aplikacji skanujących kod kreskowy wymienia tę symbologię). Zeskanuj obraz; aplikacja powinna zwrócić:

```
(01)12345678901234
(10)ABCD
```

Jeśli skaner zgłosi błąd, sprawdź ponownie formatowanie AI oraz liczbę kolumn.

## Zakończenie

Teraz wiesz **how to create GS1 barcode** w środowisku ASP.NET przy użyciu Aspose.BarCode. Tutorial obejmował:

* Konfigurację projektu ASP.NET i instalację pakietu NuGet Aspose.BarCode.  
* Użycie **generate barcode from string** dla ogólnych kodów kreskowych.  
* Implementację **create barcode with aspose** w celu wygenerowania obrazu Micro PDF417 zgodnego z GS1.  
* Zapisywanie obrazu na dysku i strumieniowanie go przez punkt końcowy HTTP.  

Od tego momentu możesz eksplorować inne symbologie GS1 (np. GS1 DataMatrix) lub zintegrować generator z większym procesem obsługi zamówień. Eksperymentuj z różnymi wartościami `XDimension`, kolorami i poziomami korekcji błędów, aby dopasować je do swojej marki i środowiska skanowania.

Miłego kodowania i niech Twoje aplikacje mówią uniwersalnym językiem kodów kreskowych!

## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak utworzyć kod 128 z GS1 przy użyciu Aspose.BarCode](/barcode/english/net/gs1-barcode-encoding/gs1-code-128-example/)
- [Jak utworzyć strefę ciszy (Quiet Zone) dla ITF-14 przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Jak utworzyć kod ITF-14 .NET – Kompleksowe tutoriale Aspose.BarCode](/barcode/english/net/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}