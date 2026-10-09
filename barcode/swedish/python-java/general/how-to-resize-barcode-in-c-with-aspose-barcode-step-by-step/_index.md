---
category: general
date: 2026-09-23
description: Hur man ändrar storlek på streckkod i C# med Aspose.BarCode. Lär dig
  att generera streckkod med C#‑kod, anpassa storlek och exportera streckkodsbilden
  effektivt.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- generate barcode c#
- barcode generator example
- create databar barcode
- export barcode image
language: sv
lastmod: 2026-09-23
og_description: Hur du ändrar storlek på streckkod i C# med Aspose.BarCode. Följ den
  här guiden för att generera streckkod i C#‑kod, justera dimensioner och exportera
  streckkodsbilden.
og_image_alt: Screenshot showing resized DataBar Omni‑directional barcode generated
  in C#
og_title: Hur man ändrar storlek på streckkod i C# – komplett Aspose.BarCode-handledning
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: How to resize barcode in C# using Aspose.BarCode. Learn to generate
    barcode C# code, customize size, and export barcode image efficiently.
  headline: How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide
  type: TechArticle
- description: How to resize barcode in C# using Aspose.BarCode. Learn to generate
    barcode C# code, customize size, and export barcode image efficiently.
  name: How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide
  steps:
  - name: '**Create Databar barcode** objects with custom data.'
    text: '**Create Databar barcode** objects with custom data.'
  - name: Adjust `BarHeight` (the core of resizing).
    text: Adjust `BarHeight` (the core of resizing).
  - name: Export PNG files for any required size.
    text: Export PNG files for any required size.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- image processing
title: Hur man ändrar storlek på streckkod i C# med Aspose.BarCode – steg‑för‑steg‑guide
url: /sv/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så här ändrar du storlek på streckkod i C# med Aspose.BarCode – steg‑för‑steg guide

Om du behöver **how to resize barcode** i en .NET‑applikation, visar den här handledningen exakt kod som du kan kopiera‑klistra in och köra idag. Du kommer att lära dig hur du **generate barcode C#** kod, justerar stapelhöjden och **export barcode image** filer utan att lämna din IDE.

Att skapa streckkoder är vanligt i lagersystem, fraktetiketter och kassaterminaler. I slutet av den här guiden kommer du att kunna **create Databar barcode** bilder i vilken höjd du än behöver, och du kommer att förstå de viktigaste egenskaperna som styr storlek, upplösning och filformat.

## Förutsättningar

- .NET 6 eller senare (exemplet fungerar även med .NET Framework 4.6+)  
- Aspose.BarCode för .NET NuGet‑paket (`Install-Package Aspose.BarCode`)  
- Grundläggande kunskap om C#‑syntax och Visual Studio (eller någon C#‑IDE)  

Inga ytterligare bibliotek behövs; Aspose.BarCode hanterar rendering, skalning och bildexport internt.

## Steg 1: Ställ in projektet och importera Aspose.BarCode

Skapa ett nytt konsolprojekt (eller integrera i ett befintligt) och lägg till Aspose.BarCode‑namnutrymmet:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;   // required for BarCodeImageFormat
```

> **Pro tip:** Använd den senaste versionen av Aspose.BarCode (från september 2026) för att dra nytta av buggfixar och nya streckkodssymboler.

## Steg 2: Initiera en DataBar Omni‑directional streckkodsgenerator

Det **barcode generator example** börjar med att ange symbolen (`EncodeTypes.DatabarOmniDirectional`) och datapayloaden. Payloaden följer GS1 Application Identifier‑formatet `(01)12345678901231`.

```csharp
// Step 2: Create a DataBar Omni‑directional barcode generator with the desired data
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Detta objekt innehåller alla parametrar du senare kommer att modifiera, såsom X‑dimension, stapelhöjd och bildformat.

## Steg 3: Definiera vanliga storleksparametrar

Innan export, sätt X‑dimensionen (bredden på den smalaste stapeln) och en initial stapelhöjd. X‑dimensionen uttrycks i pixlar; ett värde på `2` fungerar bra för de flesta skärmupplösningar.

```csharp
// Step 3: Set common barcode parameters – X‑dimension and initial bar height (30 px)
barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
barcode.Parameters.Barcode.BarHeight.Pixels = 30; // initial height
```

> **Varför detta är viktigt:** `BarHeight`‑egenskapen påverkar direkt den visuella storleken på streckkoden. Att ändra den är kärnan i **how to resize barcode** i Aspose.BarCode.

## Steg 4: Exportera den första streckkodsbilden (30 px höjd)

Nu kan du **export barcode image** till en PNG‑fil. `Save`‑metoden renderar automatiskt streckkoden med de aktuella parametrarna.

```csharp
// Step 4: Save the barcode image with a 30‑pixel height
barcode.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Den resulterande filen ser ut så här:

![How to resize barcode example](https://example.com/images/databar-30px.png){: .align-center alt="Exempel på hur man ändrar storlek på streckkod – 30 pixel höjd"}

## Steg 5: Ändra stapelhöjden för att skapa en större streckkod

För att demonstrera **how to resize barcode** dynamiskt, justera `BarHeight`‑egenskapen och spara igen. Detta kräver **inte** att du skapar en ny `BarcodeGenerator`‑instans; du modifierar helt enkelt det befintliga objektet.

```csharp
// Step 5: Change the bar height to 60 pixels for a larger barcode
barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

## Steg 6: Exportera den ändrade streckkodsbilden (60 px höjd)

```csharp
// Step 6: Save the barcode image with the new 60‑pixel height
barcode.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Du har nu två PNG‑filer—en på 30 px och en på 60 px—som visar hur samma data kan renderas i olika storlekar.

### Förväntat resultat

| Filnamn                       | Stapelhöjd (px) | Visuellt resultat |
|-------------------------------|----------------|-------------------|
| `DatabarBarHeight30Pixels.png`| 30             | ![30 px barcode](https://example.com/images/databar-30px.png){: alt="30 pixel DataBar Omni‑directional streckkod"} |
| `DatabarBarHeight60Pixels.png`| 60             | ![60 px barcode](https://example.com/images/databar-60px.png){: alt="60 pixel DataBar Omni‑directional streckkod"} |

Båda bilderna är giltiga GS1‑128 DataBar‑streckkoder redo för skanning.

## Steg 7: Valfritt – Justera ytterligare visuella inställningar

Även om huvudmålet är **how to resize barcode**, kan du också vilja justera:

| Egenskap | Beskrivning | Typiska värden |
|----------|-------------|----------------|
| `XDimension.Pixels` | Width of the narrowest bar | 1–4 |
| `BarHeight.Pixels`  | Height of the entire barcode | 20–200 |
| `Resolution` | DPI for raster output | 72, 150, 300 |
| `ForeColor` / `BackColor` | Foreground and background colors | `Color.Black`, `Color.White` |

Exempel:

```csharp
barcode.Parameters.Barcode.XDimension.Pixels = 3;
barcode.Parameters.Barcode.ForeColor = Color.DarkBlue;
barcode.Parameters.Barcode.BackColor = Color.White;
barcode.Parameters.ImageResolution.DpiX = 300;
barcode.Parameters.ImageResolution.DpiY = 300;
```

Dessa justeringar påverkar inte **resize**‑logiken men ger dig full kontroll över den slutliga bildkvaliteten.

## Vanliga fallgropar och hur du undviker dem

| Problem | Symtom | Lösning |
|-------|---------|-----|
| Stapelhöjden ändras inte | Sparade bilder ser identiska ut | Se till att du modifierar `barcode.Parameters.Barcode.BarHeight.Pixels` *innan* varje `Save`‑anrop. |
| Streckkoden blir oläslig | Skannern rapporterar “kan inte läsa” | Behåll `XDimension` ≥ 2 px för DataBar Omni‑directional; mycket tunna staplar kan göra skanningen omöjlig. |
| PNG‑filen är suddig | Exporterad med låg DPI | Ställ in `barcode.Parameters.ImageResolution.DpiX/Y` till minst 150 för utskriftskvalitet. |
| Filen skrivs över av misstag | Ny bild ersätter den gamla | Använd unika filnamn eller inkludera höjdvärdet i filnamnet, som visas ovan. |

## Fullt, körbart exempel

Kopiera hela blocket nedan till en ny konsolapp (`Program.cs`). Koden kompileras och körs som den är, och skapar de två PNG‑filerna i projektets utdata‑mapp.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar Omni‑directional barcode generator
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set common parameters
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first height

        // 3️⃣ Export first image (30 px height)
        barcode.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode.");

        // 4️⃣ Change height to 60 px
        barcode.Parameters.Barcode.BarHeight.Pixels = 60;

        // 5️⃣ Export second image (60 px height)
        barcode.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode.");

        // Optional: tweak additional settings (uncomment if needed)
        // barcode.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;
        // barcode.Parameters.ImageResolution.DpiX = 300;
        // barcode.Parameters.ImageResolution.DpiY = 300;
    }
}
```

När programmet körs får du:

```
Saved 30‑pixel barcode.
Saved 60‑pixel barcode.
```

Kontrollera utdata‑mappen för de två PNG‑filerna. Båda är redo för utskrift, inbäddning i PDF‑filer eller att skickas till en fjärrenhet.

## Slutsats

I den här guiden gick vi igenom **how to resize barcode** i C# med Aspose.BarCode, demonstrerade ett komplett **barcode generator example**, och visade hur man **export barcode image** filer i olika höjder. Du vet nu hur du:

1. **Create Databar barcode** objekt med anpassad data.  
2. Justera `BarHeight` (kärnan i storleksändring).  
3. Exportera PNG‑filer för valfri storlek.  

Härifrån kan du utforska ytterligare anpassningar—olika symboler, färgscheman eller vektorformat som SVG. Samma mönster (`barcode.Parameters.Barcode.BarHeight.Pixels = <value>`) fungerar för alla streckkodstyper som stöds av Aspose.BarCode, så du kan tryggt tillämpa kunskapen om **how to resize barcode** i hela din applikation.

---

**Nästa steg**

- Prova att ändra storlek på andra symboler (QR, Code128) för att se hur höjd och bredd samverkar.  
- Använd `BarCodeImageFormat.Svg` för att generera skalbara vektorgrafik för webbsidor.  
- Integrera de genererade bilderna i PDF‑rapporter med Aspose.PDF eller iTextSharp.  

Lycka till med kodningen, och njut av den flexibilitet som följer med programmatisk streckkodsgenerering!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar och justerar streckkodshöjd för endimensionell Databar med Aspose.BarCode för .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Hur man genererar streckkod – Code 39‑konfiguration med Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Hur man genererar DataMatrix‑streckkoder med Aspose.BarCode för .NET – steg‑för‑steg guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}