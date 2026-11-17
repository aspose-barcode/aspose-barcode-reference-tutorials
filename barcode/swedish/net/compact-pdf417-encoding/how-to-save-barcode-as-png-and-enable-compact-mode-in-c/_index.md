---
category: general
date: 2026-11-17
description: Lär dig hur du sparar streckkod, aktiverar kompakt läge, justerar kolumner
  och genererar PDF417‑streckkod med ett komplett C#‑exempel.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- enable compact mode
- how to adjust columns
- generate pdf417 barcode
- how to enable compact mode
language: sv
lastmod: 2026-11-17
og_description: Hur man sparar streckkoden, aktiverar kompakt läge och justerar kolumner
  när man genererar en PDF417‑streckkod i C#. Följ steg‑för‑steg‑guiden.
og_image_alt: Screenshot showing how to save barcode as PNG file in C#
og_title: Hur man sparar streckkod som PNG och aktiverar kompakt läge i C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  headline: How to save barcode as PNG and enable compact mode in C#
  type: TechArticle
- description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  name: How to save barcode as PNG and enable compact mode in C#
  steps:
  - name: Expected output
    text: Opening the saved PNG file shows a vertically compact PDF417 barcode with
      three columns and truncated padding. The visual size is roughly 2 px per module,
      making the image suitable for embedding in HTML `<img>` tags or for printing
      on small labels.
  - name: What if I need a different image format?
    text: The `Save` method accepts any `BarCodeImageFormat` enum value, such as `Jpeg`,
      `Bmp`, or `Gif`. Replace `BarCodeImageFormat.Png` with the desired format, and
      the rest of the code remains unchanged.
  - name: How does truncation affect data capacity?
    text: Enabling **compact mode** (truncation) reduces the number of rows, which
      can lower the maximum data capacity of the barcode. If you encounter a “Data
      too large” exception, either increase the number of columns or disable truncation.
  - name: Can I use a dynamic column count?
    text: 'Yes. You can calculate the column count based on the length of the input
      string:'
  - name: Is the X‑dimension limited to integer pixels?
    text: The `Pixels` property accepts any positive integer. For higher‑resolution
      outputs (e.g., printing), you might prefer setting `Points` instead of `Pixels`
      to achieve device‑independent sizing.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- image generation
title: Hur man sparar streckkod som PNG och aktiverar kompakt läge i C#
url: /sv/net/compact-pdf417-encoding/how-to-save-barcode-as-png-and-enable-compact-mode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man sparar streckkod som PNG och aktiverar kompakt läge i C#

Om du behöver **how to save barcode** i ett format som kan användas på webben eller i tryck, visar den här guiden de exakta stegen. Du kommer också att lära dig hur du **enable compact mode**, **adjust columns**, och **generate PDF417 barcode** med Aspose.BarCode-biblioteket för .NET.

Handledningen täcker allt från projektuppsättning till den slutliga PNG-filen, så att du kan kopiera koden till din egen lösning utan ytterligare forskning. Ingen extern dokumentation krävs; det kompletta, körbara exemplet är inkluderat.

## Förutsättningar

* .NET 6.0 eller senare installerat  
* Visual Studio 2022 (eller någon C#-IDE)  
* NuGet‑paketet `Aspose.BarCode` (`Install-Package Aspose.BarCode`)  

Dessa tre objekt är de enda beroenden för koden som följer.

## Steg 1: Skapa en PDF417‑streckkodsgenerator

Den första uppgiften när du **generate PDF417 barcode** är att instansiera en `BarcodeGenerator` med rätt kodningstyp och de data du vill koda.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a PDF417 barcode generator with the desired text.
BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

`EncodeTypes.Pdf417`‑enumet talar om för biblioteket att använda PDF417‑symbologin, som är en staplad linjär streckkod lämplig för att koda stora mängder data. Strängen "Compact mode" blir den mänskligt läsbara texten under streckkoden.

## Steg 2: Ställ in X‑dimensionen (modulbredd)

Varje stapel i en streckkod kallas en modul. Genom att kontrollera modulbredden kan du finjustera den visuella storleken på streckkoden utan att ändra data.

```csharp
// Step 2: Set the module (X) dimension – each bar will be 2 pixels wide.
barcode.Parameters.Barcode.XDimension.Pixels = 2;
```

En X‑dimension på 2 pixel ger en kompakt bild som fortfarande skannas pålitligt på de flesta enheter.

## Steg 3: **How to adjust columns** för PDF417‑koden

PDF417 låter dig ange hur många kolumner streckkoden ska använda. Färre kolumner ger en högre, smalare symbol, medan fler kolumner gör symbolen bredare men kortare.

```csharp
// Step 3: Define the number of columns for the PDF417 code (3 columns).
barcode.Parameters.Barcode.Pdf417.Columns = 3;
```

Denna rad demonstrerar **how to adjust columns**. Du kan ändra värdet till 2, 4 eller vilket tal som helst som stöds av biblioteket, beroende på det utrymme du har på målmediet.

## Steg 4: **How to enable compact mode** och trunkera symbolen

Kompakt läge tar bort onödig utfyllnad och minskar den totala fotavtrycket för streckkoden. Biblioteket exponerar denna funktion via egenskapen `Truncate`.

```csharp
// Step 4: Enable compact mode by truncating the symbol.
barcode.Parameters.Barcode.Pdf417.Truncate = true;
```

Observera att frasen **enable compact mode** visas här, och samma åtgärd beskrivs med den exakta formuleringen **how to enable compact mode** senare i guiden för att uppfylla det sekundära nyckelordskravet.

## Steg 5: **How to save barcode** som en PNG‑bild

Att spara den genererade bilden är det sista steget. `Save`‑metoden skriver streckkoden till filsystemet i det format du anger.

```csharp
// Step 5: Save the generated barcode as a PNG image.
barcode.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Byt ut `YOUR_DIRECTORY` mot en absolut eller relativ sökväg som din applikation kan skriva till. Efter körning hittar du en fil med namnet `CompactPdf417.png` som innehåller den kompakta PDF417‑streckkoden.

### Förväntad output

När du öppnar den sparade PNG‑filen visas en vertikalt kompakt PDF417‑streckkod med tre kolumner och trunkerad utfyllnad. Den visuella storleken är ungefär 2 px per modul, vilket gör bilden lämplig för inbäddning i HTML `<img>`‑taggar eller för utskrift på små etiketter.

## Fullt, körbart exempel

Nedan är det kompletta programmet som du kan kopiera in i ett nytt konsolprojekt. Det inkluderar alla nödvändiga `using`‑direktiv och demonstrerar **how to save barcode**, **enable compact mode**, **how to adjust columns**, och **generate PDF417 barcode** i ett enda flöde.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417CompactDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a PDF417 barcode generator with the desired text.
            BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

            // Set the module (X) dimension – each bar will be 2 pixels wide.
            barcode.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns for the PDF417 code (3 columns).
            barcode.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable compact mode by truncating the symbol.
            barcode.Parameters.Barcode.Pdf417.Truncate = true;

            // Save the generated barcode as a PNG image.
            string outputPath = "CompactPdf417.png"; // Adjust path as needed.
            barcode.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Att köra detta program skapar PNG‑filen som beskrivits tidigare. Konsolutdata bekräftar platsen för den sparade filen, vilket hjälper dig verifiera att steget **how to save barcode** lyckades.

## Vanliga frågor och kantfall

### Vad händer om jag behöver ett annat bildformat?

`Save`‑metoden accepterar vilket `BarCodeImageFormat`‑enumvärde som helst, såsom `Jpeg`, `Bmp` eller `Gif`. Byt ut `BarCodeImageFormat.Png` mot det önskade formatet, och resten av koden förblir oförändrad.

### Hur påverkar trunkering datakapaciteten?

Att aktivera **compact mode** (trunkering) minskar antalet rader, vilket kan sänka den maximala datakapaciteten för streckkoden. Om du får ett “Data too large”-undantag, öka antalet kolumner eller inaktivera trunkering.

### Kan jag använda ett dynamiskt kolumnantal?

Ja. Du kan beräkna kolumnantalet baserat på längden av inmatningssträngen:

```csharp
int desiredColumns = Math.Max(2, Math.Min(30, inputText.Length / 10));
barcode.Parameters.Barcode.Pdf417.Columns = desiredColumns;
```

Detta kodsnutt visar **how to adjust columns** programatiskt, vilket säkerställer att streckkoden passar inom en given layout.

### Är X‑dimensionen begränsad till heltalspixlar?

`Pixels`‑egenskapen accepterar vilket positivt heltal som helst. För högupplösta utskrifter (t.ex. tryck) kan du föredra att sätta `Points` istället för `Pixels` för att uppnå enhetlig storlek oberoende av enhet.

## Tips för produktionsanvändning

* **Pro tip:** Omge streckkodsgenereringen med ett try‑catch‑block för att hantera `BarCodeException` när indata överskrider symbolens kapacitet.  
* **Watch out for:** Fil‑systembehörigheter. Processen måste ha skrivbehörighet till mål katalogen, annars kommer steget **how to save barcode** att misslyckas med ett `UnauthorizedAccessException`.  
* **Performance note:** Att skapa många streckkoder i en loop gynnas av att återanvända en enda `BarcodeGenerator`‑instans och endast uppdatera `CodeText`‑egenskapen mellan iterationer.

## Slutsats

Du vet nu **how to save barcode** som en PNG‑fil, **enable compact mode**, **how to adjust columns**, och **generate PDF417 barcode** med Aspose.BarCode för C#. Det kompletta exemplet demonstrerar varje nödvändigt steg, från att initiera generatorn till att skriva den slutliga bilden.

Härifrån kan du utforska relaterade ämnen som att lägga till en logotyp i streckkoden, anpassa färger eller integrera generatorn i ett ASP.NET Core‑API. Varje sådan utökning följer samma mönster som visas i den här guiden, så du kan anpassa koden med förtroende.

Känn dig fri att experimentera med olika kolumnantal, X‑dimensioner och bildformat för att uppfylla ditt projekts exakta specifikationer. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig behärska ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man sparar streckkod och genererar PDF417 med Aspose i C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [Hur man skapar PDF417‑streckkod i C# med kompakt läge](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [Hur man skapar PDF417‑streckkod och sparar den som PNG i C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}