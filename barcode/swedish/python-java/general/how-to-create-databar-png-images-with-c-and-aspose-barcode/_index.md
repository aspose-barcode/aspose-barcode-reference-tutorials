---
category: general
date: 2026-08-19
description: Skapa databar‑PNG‑filer i C# med Aspose.BarCode. Lär dig hur du genererar
  databar‑bilder, konfigurerar databar‑parametrar och sparar PNG‑utdata.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar png
- how to generate databar
- configure databar parameters
language: sv
lastmod: 2026-08-19
og_description: Skapa databar PNG-filer i C# med Aspose.BarCode. Denna handledning
  guidar dig genom hur du genererar databar‑bilder, konfigurerar databar‑parametrar
  såsom X‑dimension och bildförhållande, och sparar högkvalitativa PNG-filer för utskrift
  eller webbbruk.
og_image_alt: create databar PNG example
og_title: Skapa databar PNG‑bilder i C# – steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Create databar PNG files in C# with Aspose.BarCode. Learn how to generate
    databar images, configure databar parameters, and save PNG output.
  headline: How to create databar PNG images with C# and Aspose.BarCode
  type: TechArticle
tags:
- barcode
- databar
- C#
- PNG
- Aspose.BarCode
title: Hur man skapar databar PNG-bilder med C# och Aspose.BarCode
url: /sv/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar databar PNG‑bilder med C# och Aspose.BarCode

Om du behöver **skapa databar PNG**‑filer i en .NET‑applikation visar den här guiden exakt hur du gör. Du får se ett komplett, körbart exempel som genererar staplade omnidirektionella DataBar‑koder, konfigurerar nyckelparametrar och sparar två PNG‑filer med olika bildförhållanden.

Att generera en DataBar‑bild handlar inte bara om att anropa en enda metod. Du måste också **konfigurera databar‑parametrar** som X‑dimension (modulbredd) och bildförhållandet för att uppfylla utskrifts‑ eller skanningsspecifikationer. I slutet av den här handledningen förstår du **hur man genererar databar**‑grafik som fungerar pålitligt i verkliga scenarier.

## Förutsättningar

- .NET 6.0 eller senare (koden fungerar även med .NET Framework 4.7+)
- Visual Studio 2022 eller någon C#‑kompatibel IDE
- En giltig licens för **Aspose.BarCode for .NET** (den fria utvärderingsversionen fungerar för test)
- Grundläggande kunskap om C#‑syntax

> **Pro tip:** Om du ännu inte har en licens kan du begära en tillfällig utvärderingsnyckel från Aspose‑portalen. API‑et beter sig likadant; endast vattenstämpeln ändras.

## Steg 1: Installera Aspose.BarCode‑NuGet‑paketet

Öppna ditt projekt i Visual Studio, högerklicka på lösningen och välj **Manage NuGet Packages**. Sök efter `Aspose.BarCode` och installera den senaste stabila versionen.

```bash
dotnet add package Aspose.BarCode
```

Detta kommando lägger till `Aspose.BarCode`‑assemblyn i ditt projekt och gör klassen `BarcodeGenerator` tillgänglig.

## Steg 2: Initiera streckkodsgeneratorn för en staplad omnidirektionell DataBar

Konstruktorn för `BarcodeGenerator` tar två argument: streckkodstypen och den råa datasträngen. För en staplad omnidirektionell DataBar använder du `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace DatabarPngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Initialize the generator with the desired DataBar type
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // GS1 Application Identifier for a 14‑digit GTIN
```

**Varför detta är viktigt:** Konstanten `EncodeTypes.DatabarStackedOmniDirectional` talar om för biblioteket att producera en streckkod som kan läsas från vilken orientering som helst, vilket är idealiskt för hylletiketter i detaljhandeln.

## Steg 3: Konfigurera X‑dimensionen (modulbredd) i pixlar

X‑dimensionen styr storleken på det minsta stapel­elementet. Att ange den i pixlar ger dig exakt kontroll över den slutliga bildstorleken.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Ett värde på **2 pixlar** är en bra balans mellan läsbarhet och kompaktitet för de flesta etikett‑skrivare. Justera detta värde om du behöver större eller mindre moduler.

## Steg 4: Ställ in första bildförhållandet och spara PNG‑filen

Bildförhållandet påverkar höjden på den staplade DataBar‑koden. Ett bildförhållande på **15** ger en relativt kort streckkod, medan **30** gör den högre.

```csharp
            // Step 4: Set an aspect ratio of 15 and save the image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Metoden `Save` skriver den genererade streckkoden till en PNG‑fil. PNG är förlustfritt, vilket bevarar de skarpa kanterna som behövs för streckkodsläsare.

## Steg 5: Ändra bildförhållandet och spara en andra PNG‑fil

Du kan återanvända samma `BarcodeGenerator`‑instans för att skapa variationer genom att helt enkelt ändra bildförhållandet.

```csharp
            // Step 5: Change the aspect ratio to 30 and save a new image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        }
    }
}
```

Nu har du två PNG‑filer — `DatabarAspectRatio15.png` och `DatabarAspectRatio30.png` — var och en med en annan visuell densitet.

## Steg 6: Verifiera resultatet

Öppna de genererade PNG‑filerna i någon bildvisare. Du bör se en ren, högkontrast‑DataBar‑streckkod. Att skanna bilderna med en smartphone‑streckkodsläsare bekräftar att båda bildförhållandena avkodar till det ursprungliga GTIN‑värdet `12345678901231`.

![exempel på skapad databar PNG](databar_example.png)

*Bilden ovan visar de två PNG‑filerna sida vid sida. Den vänstra bilden använder bildförhållande 15, den högra använder bildförhållande 30.*

## Vanliga variationer och kantfall

| Scenario | Vad som ska ändras | Orsak |
|----------|-------------------|-------|
| **Olika data** | Ersätt strängen `(01)12345678901231` med någon giltig GS1‑applikationsidentifierare och data | Gör det möjligt att koda produkt‑ID:n, serienummer osv. |
| **Högre upplösning** | Öka `XDimension.Pixels` till 3 eller 4 | Krävs när streckkoden ska skrivas ut i stor storlek eller skannas på avstånd. |
| **Andra DataBar‑typer** | Använd `EncodeTypes.DatabarStacked` eller `EncodeTypes.DatabarExpanded` | Välj den typ som bäst passar din etikettlayout. |
| **Transparent bakgrund** | Skicka `BarCodeImageFormat.Png` med `barcodeGenerator.Save(..., BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })` | Användbart för att lägga streckkoden ovanpå färgade etiketter. |

> **Se upp för:** Att sätta en X‑dimension som är för liten (< 1 pixel) kan leda till en streckkod som blir suddig efter

## Vad bör du lära dig härnäst?

De följande handledningarna täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Create One-Dimensional Databar GS1 Encoding with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}