---
category: general
date: 2026-08-06
description: Generera streckkodbild i C# med Aspose.BarCode. Lär dig hur du genererar
  Databar, justerar anpassad streckkodsstorlek och ändrar streckkodshöjden med enkel
  kod.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- how to generate databar
- custom barcode size
- create databar barcode
- change barcode height
language: sv
lastmod: 2026-08-06
og_description: Generera streckkodbild i C# med Aspose.BarCode. Denna handledning
  visar hur du skapar en Databar Omnidirectional‑streckkod, anpassar dess storlek
  och ändrar streckkodens höjd effektivt.
og_image_alt: Screenshot of a Databar barcode generated with custom height in C#
og_title: Generera streckkodbild i C# – fullständig Aspose.BarCode‑guide
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Generate barcode image in C# using Aspose.BarCode. Learn how to generate
    Databar, adjust custom barcode size, and change barcode height with simple code.
  headline: Generate barcode image in C# with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: The evaluation version of Aspose.BarCode works without a license but adds
      a small watermark. For production use, apply a purchased license using `License
      license = new License(); license.SetLicense("Aspose.BarCode.lic");`.
    question: Can I generate a barcode without installing a license?
  - answer: Yes. Very small X‑dimensions can make the barcode unreadable on low‑resolution
      printers. A minimum of 1 px for screen rendering is recommended; for print,
      use at least 0.25 mm.
    question: Does changing the X‑dimension affect readability?
  - answer: 'Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. You
      may also set `generator.Parameters.ImageQuality` to control compression. ##
      Conclusion You now know how to **generate barcode image** in C# using Aspose.BarCode,
      how to **create Databar barcode**, adjust a **custom barcode size**, '
    question: What if I need to generate a barcode in JPEG format?
  type: FAQPage
tags:
- barcode
- C#
- Aspose.BarCode
title: Generera streckkodbild i C# med Aspose.BarCode
url: /sv/python-java/general/generate-barcode-image-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera streckkodbild i C# med Aspose.BarCode

Om du behöver **generera streckkodbild** programatiskt visar den här guiden exakt hur. Oavsett om du bygger ett detaljhandelslagerhanteringssystem eller en logistikspårningsportal, kommer du att se hela arbetsflödet för att skapa en Databar Omnidirectional streckkod, justera dess dimensioner och spara resultatet som en PNG‑fil.

Att generera en streckkodbild är ett vanligt krav, men utvecklare undrar ofta **hur man genererar Databar** med exakt den storlek de behöver. I den här handledningen kommer du att lära dig att skapa en Databar‑streckkod, anpassa dess bredd och höjd, samt ändra streckkodens höjd utan att skriva om hela generatorn.

## Förutsättningar

* .NET 6.0 SDK eller senare (koden fungerar med .NET Core och .NET Framework)
* Visual Studio 2022 (eller någon IDE som stödjer C#)
* En giltig Aspose.BarCode för .NET-licens (den kostnadsfria utvärderingen fungerar för testning)
* Grundläggande kunskap om C#‑syntax

## Steg 1: Installera Aspose.BarCode

Lägg till Aspose.BarCode NuGet‑paketet i ditt projekt:

```bash
dotnet add package Aspose.BarCode
```

Paketet innehåller klassen `BarcodeGenerator` som används genom hela handledningen. Efter installationen återställ projektet för att hämta beroenden.

## Steg 2: Skapa en grundläggande streckkodsgenerator

Den första kodraden skapar en **streckkodsgenerator** som kommer att producera en Databar Omnidirectional‑symbol. Enum‑värdet `EncodeTypes.DatabarOmniDirectional` talar om för biblioteket vilken symbologi som ska användas, och datasträngen följer GS1 Application Identifier‑syntaxen.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a Databar Omnidirectional barcode
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231"); // GS1-14 data (example GTIN)
```

**Varför detta är viktigt:** `BarcodeGenerator`‑objektet är ingångspunkten för varje streckkodsåtgärd. Genom att välja `DatabarOmniDirectional` säkerställer du att resultatet följer GS1‑standarden för detaljhandelsavläsning.

## Steg 3: Ställ in en anpassad X‑dimension (modulbredd)

X‑dimensionen styr bredden på den smalaste stapeln. Att sätta den till ett litet pixelvärde ger en kompakt streckkod, medan större värden ökar den totala bredden.

```csharp
        // Step 3: Define a custom X‑dimension (module width) of 2 px
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Förklaring:** En X‑dimension på 2 pixel är ett vanligt val för högupplösta skärmar. Justera detta värde om du behöver en tätare eller lösare visuell densitet.

## Steg 4: Generera den första streckkodsbilden med en specifik höjd

Streckkodshöjden är oberoende av X‑dimensionen. Här sätter vi stapelhöjden till **30 px**, och sparar sedan bilden som PNG.

```csharp
        // Step 4: Set bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Resultat:** Du har nu en fil med namnet `DatabarBarHeight30Pixels.png` som visar en Databar‑streckkod 30 px hög. Detta demonstrerar möjligheten att **anpassa streckkodsstorlek** för ett specifikt användningsfall, såsom en liten etikett.

## Steg 5: Ändra streckkodshöjd för en större version

Om samma streckkod måste visas på en större etikett behöver du bara ändra höjd‑egenskapen och återanvända samma generatorinstans.

```csharp
        // Step 5: Increase the bar height to 60 px for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
    }
}
```

**Varför du kan återanvända generatorn:** Att ändra `BarHeight.Pixels` uppdaterar den interna layouten utan att återskapa objektet, vilket sparar minne och behåller datasträngen intakt. Detta är det rekommenderade sättet att **ändra streckkodshöjd** dynamiskt.

## Steg 6: Verifiera resultatet

Öppna de två PNG‑filerna i någon bildvisare. Du bör se två Databar Omnidirectional‑streckkoder som kodar samma GTIN men skiljer sig i vertikal storlek:

* `DatabarBarHeight30Pixels.png` – 30 px hög, lämplig för kompakta kvitton.
* `DatabarBarHeight60Pixels.png` – 60 px hög, idealisk för större hyllkantsetiketter.

Båda bilderna behåller samma X‑dimension, så förhållandet mellan stapel och mellanslag förblir konstant medan den totala höjden skalas.

## Vanliga variationer och kantfall

| Situation | Hur man hanterar det |
|-----------|----------------------|
| **Olika streckkodssymbologi** | Byt ut `EncodeTypes.DatabarOmniDirectional` mot ett annat enum‑värde (t.ex. `EncodeTypes.Code128`). Resten av koden förblir oförändrad. |
| **Icke‑pixel dimensioner** | Använd `generator.Parameters.Barcode.XDimension.Millimeters` eller `BarHeight.Millimeters` om du behöver fysiska mått för utskriftsklar output. |
| **Transparent bakgrund** | Sätt `generator.Parameters.ImageBackgroundColor = Color.Transparent;` innan du anropar `Save`. |
| **Högupplöst output** | Öka både `XDimension.Pixels` och `BarHeight.Pixels` proportionellt, eller spara som `BarCodeImageFormat.Tiff` för förlustfri kvalitet. |
| **Flera streckkoder i en bild** | Skapa separata `BarcodeGenerator`‑instanser, rendera var och en till en `Bitmap`, och komponera dem sedan med `Graphics.DrawImage`. |

**Proffstips:** Testa alltid den genererade streckkoden med en riktig scanner innan du driftsätter i produktion. Scannrar kan tolka mycket tunna staplar olika beroende på belysning och sensors kvalitet.

## Fullständig källkod för referens

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator for a Databar Omnidirectional barcode
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231"); // Example GTIN

            // Custom X‑dimension (module width) – 2 px
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // Second image: 60 px height (larger barcode)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

Kopiera koden till ett nytt konsolprojekt, kör det, så kommer du att se de två PNG‑filerna dyka upp i utskriftsmappen.

## Vanliga frågor

**Q: Kan jag generera en streckkod utan att installera en licens?**  
A: Utvärderingsversionen av Aspose.BarCode fungerar utan licens men lägger till ett litet vattenmärke. För produktionsbruk, applicera en köpt licens med `License license = new License(); license.SetLicense("Aspose.BarCode.lic");`.

**Q: Påverkar förändring av X‑dimension läsbarheten?**  
A: Ja. Mycket små X‑dimensioner kan göra streckkoden oläslig på lågupplösta skrivare. En minimum på 1 px för skärmrendering rekommenderas; för utskrift, använd minst 0,25 mm.

**Q: Vad händer om jag behöver generera en streckkod i JPEG‑format?**  
A: Byt ut `BarCodeImageFormat.Png` mot `BarCodeImageFormat.Jpeg`. Du kan också sätta `generator.Parameters.ImageQuality` för att kontrollera komprimeringen.

## Slutsats

Du vet nu hur du **genererar streckkodbild** i C# med Aspose.BarCode, hur du **skapar Databar‑streckkod**, justerar en **anpassad streckkodsstorlek**, och **ändrar streckkodshöjd** på begäran. Det kompletta exemplet demonstrerar det vanligaste arbetsflödet, och variations‑tabellen ger dig verktygen för att hantera verkliga kantfall.

Nästa steg är att utforska relaterade ämnen såsom **inbäddning av streckkoder i PDF‑dokument**, **batch‑generering av flera streckkoder**, och **användning av QR‑koder för mobila betalningar**. Varje scenario bygger på samma principer som behandlats här, så du kan utöka din kunskap med självförtroende.

Lycka till med kodningen, och må dina streckkoder skanna felfritt!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Generera streckkodbild – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Hur man genererar Aztec‑streckkod med anpassat bildförhållande med Aspose.BarCode för .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Hur man genererar streckkod – Code 39‑konfiguration med Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}