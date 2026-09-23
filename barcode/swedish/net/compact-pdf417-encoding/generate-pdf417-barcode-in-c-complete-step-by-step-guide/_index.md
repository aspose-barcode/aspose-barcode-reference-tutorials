---
category: general
date: 2026-09-23
description: Lär dig hur du snabbt genererar PDF417‑streckkod i C#, justerar dess
  storlek och ställer in anpassade dimensioner med Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- generate pdf417 barcode c#
- adjust barcode size c#
- custom barcode dimensions
lastmod: 2026-09-23
og_description: Hur du genererar PDF417‑streckkod i C# på några minuter. Denna guide
  visar hur du kodar text, styr X‑dimension och anpassar kolumn‑rad‑layout med Aspose.BarCode.
og_image_alt: 'Developer guide: generate PDF417 barcode with custom dimensions using
  C#'
og_title: Så genererar du PDF417‑streckkod i C# – steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to generate PDF417 barcode quickly with C#. Includes text
    encoding, size adjustment, and custom dimensions.
  headline: How to generate PDF417 barcode in C# – complete step‑by‑step guide
  type: TechArticle
tags:
- pdf417
- barcode
- csharp
- Aspose.BarCode
title: Så genererar du PDF417‑streckkod i C# – komplett steg‑för‑steg‑guide
url: /sv/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar PDF417‑streckkod i C# – komplett steg‑för‑steg‑guide

Har du någonsin behövt **generera PDF417‑streckkod** men varit osäker på vilka inställningar som måste justeras? Du är inte ensam – många utvecklare stöter på samma hinder när de först börjar arbeta med 2‑D‑streckkoder. Den goda nyheten? Med några rader C# kan du förvandla vilken sträng som helst till en skannbar PDF417‑bild, kontrollera dess exakta storlek och till och med definiera ett eget kolumn‑rad‑layout.

I den här handledningen går vi igenom hur du **genererar streckkod från text**, justerar streckkodens storlek och ställer in anpassade streckkodsdimensioner — allt med det populära Aspose.BarCode‑biblioteket. När du är klar har du ett färdigt exempel som du kan klistra in i vilket .NET‑projekt som helst.

![Generate PDF417 barcode example](https://example.com/og-image.png "Generate PDF417 barcode example")
[Generate PDF417 barcode example](https://example.com/og-image.png "Generate PDF417 barcode example")

## Snabba svar
- **Vilket bibliotek skapar PDF417‑streckkoder i .NET?** Aspose.BarCode for .NET.
- **Hur många kodrader behövs för en grundläggande streckkod?** Endast tre rader: skapa en generator, sätt X‑dimension, spara bilden.
- **Kan jag anpassa kolumner och rader?** Ja, du kan sätta `Columns` och `Rows` på PDF417‑parametrarna.
- **Vilka bildformat stöds?** PNG, JPEG, BMP, GIF, SVG och PDF.
- **Fungerar Unicode‑tecken?** Absolut; API:et stödjer fullt ut UTF‑8‑kodning.

## Vad betyder “how to generate PDF417”?
Frasen “how to generate PDF417” avser processen att skapa en PDF417‑2‑D‑streckkodsbild från textdata med ett programmeringsbibliotek. Med Aspose.BarCode kan du göra detta på under en minut. Det innebär att du tar en vanlig textsträng, matar in den i en streckkodsgenerator som implementerar PDF417‑specifikationen, och producerar en matris av svarta och vita moduler som kan renderas som en bild eller bäddas in i ett dokument.

## Varför använda Aspose.BarCode för PDF417‑generering?
Aspose.BarCode stödjer **50+ in‑ och utdataformat** och kan bearbeta **hundratals‑sidiga dokument utan att ladda hela filen i minnet**. Biblioteket körs på **.NET 6+, .NET Framework 4.8 och .NET Core**, vilket ger dig flexibilitet på skrivbord, server och moln.

## Förutsättningar
- .NET 6.0 eller senare (koden fungerar också på .NET Framework 4.8).
- Visual Studio 2022 eller någon C#‑kompatibel IDE.
- Aspose.BarCode for .NET (gratis provversion eller licensierad version). Installera via NuGet:

```bash
dotnet add package Aspose.BarCode
```

Det är allt – när paketet är refererat är du redo att köra.

## Hur man genererar PDF417‑streckkod i C#?

Läs in din text, konfigurera generatorn och spara bilden i tre enkla steg. Detta direkta svar ger dig hela arbetsflödet innan någon ytterligare förklaring. Först skapar du en `BarcodeGenerator` med PDF417‑symbologi och dina data. Därefter justerar du visuella parametrar som X‑dimension, kolumner och rader. Slutligen anropar du `Save` för att skriva bilden till disk i önskat format.

### Steg 1 – generera PDF417‑streckkod med textdata

Klassen `BarcodeGenerator` skapar streckkodsbilder baserat på angiven symbologi och data.  
Det första vi behöver är en instans av `BarcodeGenerator` som vet att vi arbetar med PDF417‑symbologi och den exakta text vi vill koda.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the barcode generator with PDF417 symbology and the data to encode
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

> **Varför detta är viktigt:**  
> `EncodeTypes.Pdf417` talar om för biblioteket att använda PDF417‑2‑D‑formatet, medan det andra argumentet är **generate barcode from text**‑payloaden. Allt du skickar hit blir data som lagras i streckkodsmatrisen.

### Steg 2 – justera streckkodens storlek (X‑dimension)

Egenskapen `XDimension` definierar pixelbredden på en enskild modul (den minsta svarta eller vita fyrkanten) i streckkodsbilden.  

`XDimension` styr bredden på en enskild modul (den minsta svarta eller vita fyrkanten) i pixlar.

```csharp
// Step 2: Set the module (X) dimension in pixels to control barcode size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module
```

> **Proffstips:**  
> Ett värde på 2 px fungerar bra för de flesta skärm‑display‑scenarier. För högupplösta utskrifter kan du öka detta till 3 eller 4 px. Kom bara ihåg att större X‑dimensioner ökar den totala bildstorleken.

### Steg 3 – ange anpassade streckkodsdimensioner (kolumner & rader)

PDF417 låter dig bestämma hur många kolumner och rader streckkoden ska uppta. Här kommer **custom barcode dimensions** in i bilden.  

`Pdf417`‑parametrarna låter dig specificera exakt kolumn‑rad‑grid för streckkoden.

```csharp
// Step 3: Define the layout of the PDF417 barcode: number of columns and rows
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

> **Vad händer under huven?**  
> Biblioteket fördelar den kodade datan över det angivna grid‑et. Färre kolumner ger högre streckkoder; fler rader gör dem kortare. Lek med siffrorna tills den visuella balansen känns rätt för ditt program.

### Steg 4 – spara streckkodsbilden

Nu när allt är konfigurerat ber vi helt enkelt generatorn skriva en PNG‑fil. PNG är förlustfri, så modulerna behåller sin skärpa.  
`Save` skriver den genererade streckkoden till en fil i valt bildformat.

```csharp
// Step 4: Save the generated barcode as a PNG image
barcodeGenerator.Save(@"C:\Barcodes\CustomLayout.png", BarCodeImageFormat.Png);
```

När du kör programmet bör du få en fil på `C:\Barcodes\CustomLayout.png` som liknar skärmdumpen ovan. Att skanna den med någon PDF417‑kompatibel läsare returnerar den ursprungliga strängen `Åspóse.Barcóde©`.

## Fullständigt fungerande exempel

Nedan är hela programmet som du kan kopiera‑klistra in i en konsolapp. Det innehåller alla `using`‑direktiv och felhantering du förväntar dig i produktionskod.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        try
        {
            // 1️⃣ Initialize generator with PDF417 symbology and text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // 2️⃣ Adjust X‑dimension to control overall size
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Apply custom layout: 4 columns × 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows    = 9;

            // 4️⃣ Save as PNG
            string outPath = @"C:\Barcodes\CustomLayout.png";
            generator.Save(outPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode generated successfully → {outPath}");
        }
        catch (Exception ex)
        {
            Console.WriteLine($"❌ Error: {ex.Message}");
        }
    }
}
```

### Förväntad utdata

När koden körs skrivs följande till konsolen:

```
✅ Barcode generated successfully → C:\Barcodes\CustomLayout.png
```

…och en PNG‑fil skapas som kan öppnas i vilken bildvisare som helst. Om du skannar den med en mobilapp (t.ex. “Barcode Scanner” på iOS/Android) bör den avkodade texten vara exakt **Åspóse.Barcóde©**.

## Vanliga frågor & edge cases

| Fråga | Svar |
|----------|--------|
| **Kan jag använda ett annat bildformat?** | Ja—`BarCodeImageFormat.Jpeg`, `Bmp`, `Gif` eller `Svg` stöds alla. Ändra bara det andra argumentet i `Save`. |
| **Vad händer om min text innehåller Unicode‑tecken?** | Aspose.BarCode stödjer fullt ut UTF‑8, så exemplet med `Å` och `©` fungerar direkt. |
| **Hur ändrar jag felkorrigeringsnivån?** | Använd `generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = Pdf417ErrorCorrectionLevel.Level5;` (nivåer 0‑8). Högre nivåer ökar redundansen men också storleken. |
| **Jag behöver en transparent bakgrund—är det möjligt?** | Sätt `generator.Parameters.Barcode.Image.TransparentBackground = true;` innan du sparar. |
| **Finns det ett sätt att bädda in streckkoden direkt i en PDF?** | Absolut. Byt ut `Save`‑anropet mot `generator.Save("output.pdf", BarCodeImageFormat.Pdf);` så får du en en‑sidig PDF med streckkoden. |

## Vanliga frågor

**Q: Fungerar biblioteket på .NET Core och .NET 5/6?**  
A: Ja, Aspose.BarCode for .NET stödjer .NET Core 3.1, .NET 5, .NET 6 och senare versioner.

**Q: Kan jag generera flera streckkoder i en loop?**  
A: Absolut. Skapa en ny `BarcodeGenerator` för varje sträng eller återanvänd samma instans efter att ha ändrat `CodeText`‑egenskapen.

**Q: Hur stor kan den genererade bilden bli?**  
A: API:et kan skapa bilder upp till **10 000 × 10 000 pixlar**; minnesförbrukningen skalar med X‑dimensionen samt kolumn‑/rad‑inställningarna.

**Q: Krävs licens för produktionsanvändning?**  
A: Ja, en kommersiell licens tar bort evalueringsvattenmärken och låser upp hela funktionsuppsättningen. En gratis provversion finns för testning.

**Q: Måste jag manuellt disponera generatorn?**  
A: `BarcodeGenerator` implementerar `IDisposable`. Använd en `using`‑block eller anropa `Dispose()` för att frigöra resurser omedelbart.

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger vidare på teknikerna i den här guiden. Varje resurs innehåller kompletta kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra fler API‑funktioner och utforska alternativa implementeringssätt i egna projekt.

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

---

**Senast uppdaterad:** 2026-09-23  
**Testat med:** Aspose.BarCode 24.11 for .NET  
**Författare:** Aspose  






```bash
dotnet add package Aspose.BarCode
```

## Relaterade handledningar

- [Adjust Barcode Size C Guide To Generate Pdf417 Barcodes](/barcode/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Aspose Barcode Example Generate Macro Pdf417 In C](/barcode/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [Generate Micro Pdf417 Barcode In C Complete Guide](/barcode/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}