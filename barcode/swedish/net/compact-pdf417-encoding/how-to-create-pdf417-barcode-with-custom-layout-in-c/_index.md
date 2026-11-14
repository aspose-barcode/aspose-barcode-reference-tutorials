---
category: general
date: 2026-11-14
description: Lär dig hur du snabbt skapar PDF417-streckkod i C#. Denna guide visar
  också hur du genererar PDF417 och hur du anpassar PDF417-inställningarna för exakt
  kontroll.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417
- how to customize pdf417
language: sv
lastmod: 2026-11-14
og_description: Skapa PDF417-streckkod i C# med steg‑för‑steg‑instruktioner. Lär dig
  hur du genererar PDF417 och hur du anpassar PDF417-parametrar för exakta resultat.
og_image_alt: Screenshot showing a generated PDF417 barcode created with C# code
og_title: Skapa PDF417-streckkod i C# – fullständig guide med anpassad layout
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  headline: How to create PDF417 barcode with custom layout in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  name: How to create PDF417 barcode with custom layout in C#
  steps:
  - name: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
    text: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
  - name: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
    text: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
  - name: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
    text: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
  type: HowTo
tags:
- barcode
- pdf417
- C#
title: Hur man skapar PDF417-streckkod med anpassad layout i C#
url: /sv/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-custom-layout-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar PDF417‑streckkod med anpassad layout i C#

Om du behöver **skapa pdf417 barcode** för ett biljettsystem, lageretikett eller mobil‑app‑skanning, visar den här handledningen hela processen. Du får se hur du snabbt genererar PDF417 och hur du anpassar PDF417‑inställningar som kolumner och rader, så att streckkoden passar dina designbegränsningar.

Att generera en streckkod kräver inte ett komplext grafikbibliotek – bara Aspose.BarCode för .NET (eller något kompatibelt API). I slutet av guiden har du en färdig PNG‑fil som du kan bädda in i PDF‑filer, webbsidor eller skriva ut direkt från din applikation.

## Förutsättningar

- .NET 6.0 eller senare (koden fungerar också med .NET Framework 4.7+)
- Aspose.BarCode för .NET (NuGet‑paket `Aspose.BarCode`)
- Grundläggande kunskap om C# och Visual Studio (eller någon IDE)

> **Pro tip:** Om du använder en CI/CD‑pipeline, lägg till NuGet‑paketreferensen i din projektfil så att byggen förblir reproducerbara.

## Steg 1: Installera streckkodsbiblioteket

Öppna din projektmapp i en terminal och kör:

```bash
dotnet add package Aspose.BarCode
```

Paketet innehåller klassen `BarcodeGenerator` som används genom hela handledningen. Inga ytterligare inhemska beroenden krävs.

## Steg 2: Skapa en grundläggande PDF417‑streckkod

Det första målet är att **create pdf417 barcode** med standardinställningar. Följande program sätter upp generatorn, kodar en exempelsträng och sparar resultatet som en PNG‑bild.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417Demo
{
    static void Main()
    {
        // Step 2.1: Initialise the generator for PDF417 with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample text for PDF417");

        // Step 2.2: Save the barcode as PNG
        string outputPath = "Pdf417Default.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

**Varför detta fungerar:**  
`EncodeTypes.Pdf417` talar om för biblioteket att använda PDF417‑symbologin. Konstruktorn skapar automatiskt ett `Barcode`‑objekt med standardvärden för kolumner/rader som garanterar läsbarhet för de flesta användningsfall.

Kör programmet (`dotnet run`). Du hittar `Pdf417Default.png` i projektmappen. När du öppnar bilden ser du en standard‑PDF417‑streckkod redo för skanning.

![Create PDF417 barcode example](https://example.com/images/pdf417-default.png){:alt="Create PDF417 barcode example showing default layout"}

## Steg 3: Så här genererar du PDF417 med anpassade dimensioner

Ibland kräver en etikett med fast storlek eller en UI‑komponent ett specifikt streckkodsområde. Det är då **how to generate pdf417** med anpassade kolumner och rader blir viktigt.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417CustomDemo
{
    static void Main()
    {
        // Initialise generator with the same text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Custom layout text");

        // ---- Customization begins here ----
        // Set the number of columns (2‑30). Fewer columns make the barcode taller.
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // Set the number of rows (1‑90). More rows make the barcode wider.
        generator.Parameters.Barcode.Pdf417.Rows = 9;
        // ------------------------------------

        // Save the customized barcode
        string outputPath = "Pdf417CustomLayout.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Custom barcode saved to {outputPath}");
    }
}
```

**Varför du kan vilja göra detta:**  
- **Begränsad bredd:** Att minska kolumner och öka rader skapar en bredare men kortare streckkod, perfekt för smala etiketter.  
- **Begränsad höjd:** Att öka kolumner och minska rader ger en högre, smalare streckkod, användbar när du har vertikalt utrymme.

Både `Columns` och `Rows` accepterar endast värden inom de dokumenterade intervallen (2‑30 för kolumner, 1‑90 för rader). Att ange ett värde utanför intervallet kastar ett `ArgumentOutOfRangeException`, så validera alltid användarinmatning om du exponerar dessa inställningar i ett UI.

## Steg 4: Så här anpassar du PDF417 ytterligare

Utöver kolumner och rader erbjuder PDF417‑symbologin många valfria parametrar:

| Property | Syfte | Typiska värden |
|----------|-------|----------------|
| `ErrorLevel` | Styr felkorrigeringskapacitet | 0‑8 (högre = mer robust) |
| `MacroPdf417` | Aktiverar macro PDF417 för segmenterad data | `true`/`false` |
| `CompactPdf417` | Skapar en mer kompakt streckkod på bekostnad av minskad felkorrigering | `true`/`false` |
| `SecurityLevel` | Lägger till en säkerhetskontrollsiffra | 0‑2 |

Här är ett snabbt exempel som också sätter felnivån till maximum (8) för en bullrig miljö:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 8;
generator.Parameters.Barcode.Pdf417.CompactPdf417 = true;
```

**Varför det är viktigt:**  
Högre felkorrigering låter skannrar återhämta data även om en del av streckkoden är skadad. Det ökar dock streckkodens storlek, så balansera inställningen mot dina layoutbegränsningar.

## Steg 5: Verifiera att streckkoden fungerar

Efter att PNG‑filen har genererats, testa den med någon streckkodsläsarapp (de flesta smartphones har gratis PDF417‑läsare). Om läsaren returnerar den ursprungliga texten (`Custom layout text`) är streckkoden giltig.

Om du stöter på skanningsproblem:

1. **Kontrollera dimensioner:** Säkerställ att kolumner/rader ligger inom tillåtet intervall.  
2. **Justera felnivå:** Öka `ErrorLevel` för skadat medium.  
3. **Granska bildkvalitet:** Spara med högre DPI (`generator.Save(outputPath, BarCodeImageFormat.Png, 300)`) om du planerar att skriva ut.

## Fullständig källkod för en återanvändbar hjälparklass

Nedan finns en kompakt, återanvändbar klass som du kan släppa in i vilket .NET‑projekt som helst. Den kapslar **how to generate pdf417** och **how to customize pdf417** i en enda metod.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

public static class Pdf417Helper
{
    /// <summary>
    /// Creates a PDF417 barcode image with optional layout parameters.
    /// </summary>
    /// <param name="text">The data to encode.</param>
    /// <param name="outputPath">Full file path for the PNG output.</param>
    /// <param name="columns">Number of columns (2‑30). Pass null to use default.</param>
    /// <param name="rows">Number of rows (1‑90). Pass null to use default.</param>
    /// <param name="errorLevel">Error correction level (0‑8). Null = default.</param>
    public static void CreatePdf417(string text, string outputPath,
                                    int? columns = null,
                                    int? rows = null,
                                    int? errorLevel = null)
    {
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, text);

        // Apply optional customizations
        if (columns.HasValue) generator.Parameters.Barcode.Pdf417.Columns = columns.Value;
        if (rows.HasValue)    generator.Parameters.Barcode.Pdf417.Rows    = rows.Value;
        if (errorLevel.HasValue) generator.Parameters.Barcode.Pdf417.ErrorLevel = errorLevel.Value;

        // Save as high‑resolution PNG (300 DPI) for printing scenarios
        generator.Save(outputPath, BarCodeImageFormat.Png, 300);
    }
}
```

Du kan anropa hjälpen så här:

```csharp
Pdf417Helper.CreatePdf417(
    text: "Order #12345",
    outputPath: "OrderBarcode.png",
    columns: 5,
    rows: 12,
    errorLevel: 6);
```

Metoden abstraherar bort den repetitiva boiler‑plate‑koden, så att du kan fokusera på affärslogiken.

## Vanliga fallgropar och hur du undviker dem

- **Värden utanför intervallet:** Validera alltid `columns` och `rows` innan du tilldelar dem.  
- **Fel bildformat:** Vissa äldre skannrar accepterar bara BMP eller JPEG. Använd `BarCodeImageFormat.Bmp` om det behövs.  
- **Låg DPI för utskrift:** Standard‑DPI är 96. För högkvalitativa utskrifter, ange explicit en högre DPI (t.ex. 300) när du anropar `Save`.  
- **Saknad teckensnittsstöd:** PDF417 kodar binär data, så du behöver i regel inte specificera ett teckensnitt. Om du däremot överlagrar text på bilden, se till att teckensnittet är installerat på målmaskinen.

## Slutsats

Du vet nu hur du **create pdf417 barcode** från början till slut, hur du **generate pdf417** med anpassade kolumn‑/radinställningar, och hur du **customize pdf417** för felkorrigering och kompaktitet. Genom att följa det återanvändbara hjälparmönstret kan du generera streckkoder på begäran, anpassa dem till alla layoutbegränsningar och garantera pålitlig skanning i produktionsmiljöer.

**Nästa steg**

- Utforska andra symbologier såsom QR eller Code128 med samma `BarcodeGenerator`‑klass.  
- Kombinera PNG‑utdata med ett PDF‑genereringsbibliotek (t.ex. iText7) för att bädda in streckkoder i fakturor.  
- Experimentera med `MacroPdf417` för segmenterad dataöverföring, en funktion som är användbar i logistik‑ och transportapplikationer.

Lycka till med kodningen, och må dina streckkoder alltid skannas på första försöket!


## Vad bör du lära dig härnäst?


Följande handledningar täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationssätt i dina egna projekt.

- [How to generate PDF417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [How to generate barcode and customize PDF417 barcode in C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/)
- [How to create PDF417 barcode and export PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}