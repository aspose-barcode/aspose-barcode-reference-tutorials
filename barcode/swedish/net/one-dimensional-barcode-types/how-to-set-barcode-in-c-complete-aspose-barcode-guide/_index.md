---
category: general
date: 2026-08-06
description: Hur man ställer in streckkod med Aspose.BarCode i C#. Lär dig hur du
  ändrar makrotecken och skapar streckkodsbilder i C# med steg‑för‑steg‑kod.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- how to change macro
- barcode generator c#
- create barcode image c#
language: sv
lastmod: 2026-08-06
og_description: Hur man ställer in streckkod med Aspose.BarCode i C#. Denna guide
  visar hur man ändrar makrotecken och snabbt skapar en streckkodsbild i C#.
og_image_alt: Screenshot of a MicroPDF417 barcode generated with C# code
og_title: Hur man ställer in streckkod i C# – Aspose.BarCode-handledning
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: How to set barcode using Aspose.BarCode in C#. Learn how to change
    macro characters and create barcode image C# with step‑by‑step code.
  headline: How to set barcode in C# – complete Aspose.BarCode guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Hur man sätter streckkod i C# – komplett Aspose.BarCode-guide
url: /sv/net/one-dimensional-barcode-types/how-to-set-barcode-in-c-complete-aspose-barcode-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man ställer in streckkod i C# – komplett Aspose.BarCode-guide

Om du behöver **how to set barcode** i en .NET-applikation, visar den här handledningen de exakta stegen med Aspose.BarCode. Du kommer att se hur du ändrar makrokartor, justerar visuella parametrar och **create barcode image C#**-filer som kan sparas direkt till disk.

Guiden täcker allt från installation av biblioteket till generering av två MicroPDF417‑streckkoder med olika makrovärden. Ingen extern dokumentation krävs – du kan kopiera koden, köra den och verifiera PNG‑utdata omedelbart.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 eller senare (exemplet använder ett konsolprojekt)
* Visual Studio 2022 eller någon C#‑IDE
* En aktiv Aspose.BarCode-licens (en gratis utvärdering fungerar för testning)
* Grundläggande kunskap om C#‑syntax

Du kommer också att behöva NuGet‑paketet:

```bash
dotnet add package Aspose.BarCode
```

## Hur man ställer in streckkodparametrar – steg 1: skapa generatorn

Den första åtgärden är att instansiera en `BarcodeGenerator` med önskad symbologi och data. Att använda `EncodeTypes.MicroPdf417` talar om för Aspose.BarCode att producera en kompakt PDF417‑variant.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Step 1: Create a MicroPDF417 barcode generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417, // symbology
                "12345ABC");             // data to encode
```

**Varför detta är viktigt:** `BarcodeGenerator` är det centrala objektet; alla senare inställningar modifierar dess `Parameters`‑egenskap. Att välja rätt `EncodeTypes` säkerställer att streckkoden följer MicroPDF417‑specifikationen.

## Hur man ändrar makrokartor – steg 2: justera visuella parametrar

Makrokartor är valfria kontrollkoder som låter dig kedja ihop flera PDF417‑symboler. Exemplet växlar mellan `Macro05` och `Macro06`. Du ställer också in modulbredden (`XDimension`) och antalet kolumner för att kontrollera streckkodens storlek.

```csharp
            // Step 2: Adjust visual parameters – set the X‑dimension (module width) and number of columns
            generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width in pixels
            generator.Parameters.Barcode.Pdf417.Columns = 4;           // number of data columns

            // Encode the first macro character (Macro05) and save the image
            generator.Parameters.Barcode.Pdf417.MacroCharacters = MacroCharacter.Macro05;
            generator.Save("MicroPdf417_Macro05.png", BarCodeImageFormat.Png);
```

**Varför du ändrar makrot:** Makrokartan talar om för en skanner att denna streckkod är en del av en större datamängd. Att växla den visar hur samma data kan kopplas till olika makroidentifierare.

## Hur man ställer in streckkod – steg 3: generera en andra streckkod med ett annat makro

Nu återanvänder vi samma `generator`‑instans och byter bara makrovärdet. Detta undviker att skapa objektet på nytt och demonstrerar att **how to set barcode**‑parametrar kan ändras vid körning.

```csharp
            // Step 3: Switch to the second macro character (Macro06) and save the new image
            generator.Parameters.Barcode.Pdf417.MacroCharacters = MacroCharacter.Macro06;
            generator.Save("MicroPdf417_Macro06.png", BarCodeImageFormat.Png);
        }
    }
}
```

### Förväntat resultat

När programmet körs skapas två PNG‑filer i projektmappen:

* `MicroPdf417_Macro05.png` – streckkod med Macro05
* `MicroPdf417_Macro06.png` – streckkod med Macro06

Båda bilderna visar en kompakt MicroPDF417‑symbol som kodar `12345ABC`. Du kan öppna PNG‑filerna med vilken bildvisare som helst för att verifiera den visuella kvaliteten.

## Bästa praxis för Barcode‑generator C#

* **Återanvänd generatorn:** Att ändra `Parameters` på en befintlig instans är mer effektivt än att skapa en ny generator för varje streckkod.
* **Ställ in X‑dimension tidigt:** Modulbredden påverkar den totala bildstorleken; justera den innan du sparar.
* **Validera makroanvändning:** Inte alla skannrar stödjer makrokartor. Testa med din mål‑hardware om du planerar att använda dem i produktion.
* **Frigör resurser:** `BarcodeGenerator` implementerar `IDisposable`. I en långvarig tjänst, omslut den i ett `using`‑block eller anropa `Dispose()` när du är klar.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "12345ABC"))
{
    // configure parameters...
}
```

## Skapa streckkodbild C# – felsökningstips

| Symptom                              | Trolig orsak                              | Åtgärd |
|--------------------------------------|-------------------------------------------|--------|
| Tom PNG-fil                          | `XDimension` satt till 0 eller mycket högt värde | Använd en rimlig pixelbredd (1‑5) |
| Streckkod oläslig för skanner       | Fel makrokod för skannern                 | Verifiera skannerdokumentation; använd `MacroNone` om det inte behövs |
| Undantag `ArgumentOutOfRangeException` | Kolumnantal utanför tillåtet intervall (1‑30) | Håll `Columns` mellan 1 och 30 |

## Slutsats

Du vet nu hur du **how to set barcode**‑egenskaper, **how to change macro**‑karaktärer, och hur du **create barcode image C#**‑filer med Aspose.BarCode. Det kompletta, körbara exemplet demonstrerar hela arbetsflödet från generator‑skapande till bildexport.

Nästa steg är att utforska andra symbologier (`EncodeTypes.QR`, `EncodeTypes.Code128`) eller bädda in streckkoden direkt i PDF‑filer med Aspose.PDF. Båda ämnena faller under det bredare **barcode generator c#**‑ekosystemet och kan läggas till i detta projekt med minimala kodändringar.

Lycka till med kodandet, och känn dig fri att experimentera med olika makrovärden, dimensioner och exportformat!

## Vad bör du lära dig härnäst?

De följande handledningarna täcker nära besläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar tyst zon för streckkod Code 16K med Aspose.BarCode för .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Hur man skapar dotcode utökad kodtext med Aspose.BarCode för .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Hur man ställer in kant för ITF-14 streckkodsanpassning](/barcode/english/net/itf-14-barcode-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}