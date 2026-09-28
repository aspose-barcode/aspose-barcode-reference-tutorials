---
category: general
date: 2026-07-18
description: Skapa Planet‑streckkod snabbt med C#. Lär dig hur du genererar fyllda
  och tomma staplar, ställer in X‑dimensionen och sparar PNG‑bilder – allt i en handledning.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode generator
- BarcodeGenerator parameters
- XDimension pixels
- filled bars vs empty bars
language: sv
lastmod: 2026-07-18
og_description: Skapa Planet‑streckkod omedelbart. Den här guiden visar hur du ställer
  in X‑dimension, växlar mellan fyllda och tomma staplar och exporterar PNG‑filer
  med Aspose.BarCode.
og_image_alt: Screenshot of a generated Planet barcode saved as PNG
og_title: Skapa Planet Barcode i C# – Fullständig programmeringsgenomgång
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create Planet barcode quickly with C#. Learn how to generate filled
    and empty bars, set X‑dimension, and save PNG images – all in one tutorial.
  headline: Create Planet Barcode in C# – Full Step‑by‑Step Guide
  type: TechArticle
- description: Create Planet barcode quickly with C#. Learn how to generate filled
    and empty bars, set X‑dimension, and save PNG images – all in one tutorial.
  name: Create Planet Barcode in C# – Full Step‑by‑Step Guide
  steps:
  - name: “Can I change the image format?”
    text: Absolutely. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `Bmp`,
      `Gif`, etc. Just replace `BarCodeImageFormat.Png` with your desired format.
  - name: “What if I need a different barcode height?”
    text: 'Use `planetBarcode.Parameters.Barcode.BarHeight` (in points) to increase
      or decrease the vertical size. For example:'
  - name: “Is there a way to add a human‑readable caption?”
    text: 'Yes. Set the `CodeText` property on `planetBarcode.Parameters.Caption`:'
  - name: “Do I need to dispose the generator?”
    text: 'The `BarcodeGenerator` implements `IDisposable`. Wrap it in a `using` block
      if you’re creating many barcodes in a loop:'
  - name: “What about error handling?”
    text: 'Enclose the `Save` calls in a `try…catch` block to capture `IOException`
      (disk issues) or `ArgumentException` (invalid parameters). Example:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Skapa Planet Barcode i C# – Fullständig steg‑för‑steg‑guide
url: /sv/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa Planet-streckkod i C# – Fullständig steg‑för‑steg‑guide

Har du någonsin behövt **create planet barcode** bilder men var osäker på vilka egenskaper som ska justeras? Du är inte ensam. Många utvecklare stöter på problem när de förifyllda staplarna inte är vad specifikationen kräver, eller när stapelbredden måste matcha en skrivarens DPI.  

I den här handledningen kommer du att lära dig exakt hur du **create planet barcode** filer med Aspose.BarCode-biblioteket, hur du styr **XDimension pixels**, och hur du växlar mellan **filled bars** och **empty bars** utan att skriva om någon kod. I slutet har du två PNG-filer – en med solida staplar och en med ihåliga staplar – redo för vilket postsystem som helst som förväntar sig Planet‑symbologi.

## Förutsättningar

- .NET 6.0 eller senare (koden fungerar även på .NET Framework 4.7 +)  
- Aspose.BarCode för .NET NuGet‑paket (`Install-Package Aspose.BarCode`)  
- Grundläggande C#‑kunskaper (du kommer att se varför vi använder `using`‑satser senare)  
- En skrivbar mapp på disken där PNG‑filerna ska sparas  

Om du har dessa kan vi hoppa rakt in i implementeringen.

## Steg 1 – Ställ in projektet och lägg till biblioteket

Först, skapa en ny konsolapp (eller något C#‑projekt) och referera till **Planet barcode generator**‑biblioteket.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The rest of the code lives here
        }
    }
}
```

> **Proffstips:** I Visual Studio, högerklicka på projektet → *Manage NuGet Packages* → sök efter **Aspose.BarCode** och klicka på *Install*. Detta ger dig åtkomst till `BarcodeGenerator` och alla **BarcodeGenerator parameters** du kommer att behöva.

## Steg 2 – Initiera Planet Barcode Generator

Nu skapar vi faktiskt en **create planet barcode**‑generatorinstans och matar den med de data vi vill koda (`"123456"` i detta exempel). Enum‑värdet `EncodeTypes.Planet` talar om för biblioteket vilken symbologi som ska användas.

```csharp
// Step 2: Initialise the generator with Planet symbology and data
BarcodeGenerator planetBarcode = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

> **Varför detta är viktigt:** Flaggan `EncodeTypes.Planet` tillämpar automatiskt korrekt kontrollsumma och layoutregler för Planet‑poststapelkod, så du behöver inte beräkna dem manuellt.

## Steg 3 – Konfigurera X‑Dimension (stapelförhållande)

De flesta skrivare förväntar sig att varje stapel har ett specifikt antal pixlar. Här sätter vi **XDimension pixels** till `4`, vilket är ett vanligt värde för 203 dpi termiska skrivare.

```csharp
// Step 3: Set the width of each bar (X‑dimension) to 4 pixels
planetBarcode.Parameters.Barcode.XDimension.Pixels = 4;
```

> **Edge case:** Om du riktar dig mot en 300 dpi‑skrivare kan du behöva `3` eller `5` pixlar istället. Justera detta värde baserat på din enhets dokumentation.

## Steg 4 – Spara versionen med fyllda staplar

Som standard genererar generatorn **filled bars** (solida svarta rektanglar). Låt oss skriva detta till disk:

```csharp
// Step 4: Save the barcode with default (filled) bars
planetBarcode.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Ersätt `YOUR_DIRECTORY` med en absolut eller relativ sökväg som din app kan skriva till. Efter att den här raden har körts hittar du en PNG‑fil som ser ut som en klassisk Planet‑stapelkod – perfekt för testning mot en postskanner.

## Steg 5 – Växla till tomma staplar

Ibland kräver posttjänster stilen “empty bars”, där staplarna är urholkade i en vit bakgrund istället för målade svarta. Biblioteket erbjuder en enkel växel:

```csharp
// Step 5: Re‑configure the generator to produce empty bars
planetBarcode.Parameters.Barcode.FilledBars = false;
```

Att sätta `FilledBars` till `false` instruerar renderaren att invertera stapelfyllningslogiken. Ingen anledning att skapa en ny `BarcodeGenerator`‑instans; vi justerar bara de befintliga **BarcodeGenerator parameters**.

## Steg 6 – Spara versionen med tomma staplar

Slutligen, exportera den andra bilden:

```csharp
// Step 6: Save the barcode with empty bars
planetBarcode.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

Nu har du två separata PNG‑filer, var och en som uppfyller ett annat visuellt krav.

## Fullt fungerande exempel

När vi sätter ihop alla bitarna, här är det kompletta, kopiera‑och‑klistra‑klara programmet:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Initialise the Planet barcode generator with data
            BarcodeGenerator planetBarcode = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // Configure bar width (X‑dimension) – 4 pixels works for most 203 dpi printers
            planetBarcode.Parameters.Barcode.XDimension.Pixels = 4;

            // Save the default filled‑bars version
            planetBarcode.Save(@"C:\Barcodes\PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Switch to empty‑bars style
            planetBarcode.Parameters.Barcode.FilledBars = false;

            // Save the empty‑bars version
            planetBarcode.Save(@"C:\Barcodes\PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Both Planet barcode images have been generated successfully.");
        }
    }
}
```

**Förväntad output** (i konsolen):

```
Both Planet barcode images have been generated successfully.
```

Och i `C:\Barcodes\` kommer du att se:

- `PostalPlanetFilledBars.png` – solida svarta staplar  
- `PostalPlanetEmptyBars.png` – vita staplar med svarta konturer  

Öppna dem i någon bildvisare; de bör båda följa Planet‑specifikationen.

## Vanliga frågor & tips

### “Kan jag ändra bildformatet?”

Absolut. Metoden `Save` accepterar `BarCodeImageFormat.Jpeg`, `Bmp`, `Gif` osv. Byt bara ut `BarCodeImageFormat.Png` mot det format du önskar.

### “Vad händer om jag behöver en annan stapelhöjd?”

Använd `planetBarcode.Parameters.Barcode.BarHeight` (i punkter) för att öka eller minska den vertikala storleken. Till exempel:

```csharp
planetBarcode.Parameters.Barcode.BarHeight = 30; // 30 points tall
```

### “Finns det ett sätt att lägga till en mänskligt läsbar bildtext?”

Ja. Sätt egenskapen `CodeText` på `planetBarcode.Parameters.Caption`:

```csharp
planetBarcode.Parameters.Caption.Visible = true;
planetBarcode.Parameters.Caption.TopMargin = 5; // space between barcode and text
planetBarcode.Parameters.Caption.Text = "123456";
```

### “Behöver jag avyttra generatorn?”

`BarcodeGenerator` implementerar `IDisposable`. Omge den med ett `using`‑block om du skapar många stapelkoder i en loop:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(...))
{
    // configure and save
}
```

### “Hur hanterar man fel?”

Omge `Save`‑anropen med ett `try…catch`‑block för att fånga `IOException` (diskproblem) eller `ArgumentException` (ogiltiga parametrar). Exempel:

```csharp
try
{
    planetBarcode.Save(path, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to save barcode: {ex.Message}");
}
```

## Sammanfattning

Vi har gått igenom allt du behöver för att **create planet barcode** bilder i C#:

1. Initiera **Planet barcode generator** med dina data.  
2. Justera **XDimension pixels** för att matcha skrivarens specifikationer.  
3. Spara en **filled bars** PNG.  
4. Växla `FilledBars` för att producera **empty bars**.  
5. Spara den andra PNG‑filen.  

Härifrån kan du utforska fler **BarcodeGenerator parameters**, experimentera med andra symbologier (`EncodeTypes.Postnet`, `EncodeTypes.Code128`, osv.), eller integrera bilderna i ett posthanteringsflöde.

---

**Redo för nästa steg?** Försök lägga till en QR‑kod i samma dokument, eller generera en batch av Planet‑stapelkoder från en CSV‑lista med en `foreach`‑loop. Aspose.BarCode‑API:n är tillräckligt flexibel för att hantera massoperationer, anpassade färger och till och med vektorbaserad SVG‑output.

Om du stöter på problem, lämna en kommentar nedan eller kolla den officiella Aspose.BarCode‑dokumentationen för djupare insikter i avancerade funktioner. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstreras i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Skapa streckkod med Aspose – Ställ in X‑ och Y‑dimensioner i Java](/barcode/english/java/barcode-configuration/managing-x-y-dimension-barcode/)
- [Hur man skapar code128‑streckkods bilder i Java med Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)
- [Hur man skapar code128‑streckkod i Java och ställer in stapelhöjd](/barcode/english/java/barcode-configuration/setting-bars-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}