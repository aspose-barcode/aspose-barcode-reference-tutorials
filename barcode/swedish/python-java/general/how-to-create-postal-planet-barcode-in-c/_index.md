---
category: general
date: 2026-11-23
description: Skapa postplanetstreckkod i C# med Aspose.BarCode. Lär dig hur du genererar
  planetstreckkod, ställer in X‑dimension och sparar fyllda eller tomma staplar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal planet barcode
- how to generate planet barcode
- Aspose.BarCode C#
- postal barcode example
- Planet barcode settings
language: sv
lastmod: 2026-11-23
og_description: Skapa en postplanetkod i C# och lär dig hur du genererar planetkod
  med Aspose.BarCode. Följ det kompletta exemplet för att producera fyllda och tomma
  streck.
og_image_alt: Example of a created postal planet barcode with filled bars
og_title: Hur man skapar Postal Planet-streckkod i C# – steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  headline: How to create postal planet barcode in C#
  type: TechArticle
- description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  name: How to create postal planet barcode in C#
  steps:
  - name: Changing the image format
    text: If your downstream system prefers JPEG, replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. JPEG introduces compression artifacts, so use
      it only when file size is a critical constraint.
  - name: Scaling the barcode
    text: 'You can enlarge the barcode while preserving the module width by adjusting
      the `Resolution` property:'
  - name: Using a custom background color
    text: 'The background can be set with:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Hur man skapar Postal Planet-streckkod i C#
url: /sv/python-java/general/how-to-create-postal-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar postal planet-streckkod i C#

Om du behöver **skapa postal planet-streckkod** i en .NET-applikation, visar den här guiden exakt **hur man genererar planet-streckkod** med hjälp av Aspose.BarCode-biblioteket. Du kommer att se hur du konfigurerar X‑dimensionen, växlar mellan fyllda och tomma staplar, och sparar bilderna i PNG-format.

Att generera en Planet-streckkod är vanligt för posttjänster som kräver högdensitets, maskinläsbara symboler. I slutet av den här handledningen kommer du att ha två PNG-filer – en med solida staplar och en med ihåliga staplar – redo för integration i vilket postflöde som helst.

## Förutsättningar

* .NET 6.0 SDK eller senare installerat.
* Visual Studio 2022 (eller någon C#-redigerare) konfigurerad för .NET-utveckling.
* En aktiv NuGet-licens för **Aspose.BarCode for .NET**. Installera paketet med:

```bash
dotnet add package Aspose.BarCode
```

Inga ytterligare externa tjänster krävs; biblioteket utför all kodning lokalt.

## Steg 1 – skapa postal planet-streckkod

Den första operationen är att instansiera en `BarcodeGenerator` för **Planet**-symbologin och tillhandahålla data att koda. Datat strängen måste vara numerisk och upp till 12 siffror enligt postens specifikation.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Att skapa generatorn allokerar alla interna strukturer som behövs för rendering. `EncodeTypes.Planet`-enumvärdet väljer rätt kodningsalgoritm för postformatet.

## Steg 2 – ställ in X‑dimensionen för bättre synlighet

X‑dimensionen definierar bredden på en enskild modul (det minsta stapel-elementet). Ett värde på 4 pixlar ger en tydlig visuell representation utan att förstora hela bilden.

```csharp
// Step 2: Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
```

Justering av X‑dimensionen är avgörande när streckkoden ska skrivas ut på lågupplöst media. Samma inställning kommer att återanvändas för versionen med tomma staplar för att hålla båda bilderna konsekventa.

## Steg 3 – spara streckkoden med fyllda staplar

Som standard renderar generatorn **fyllda staplar** (solida svarta moduler). Att spara bilden är ett enda metodanrop som skriver PNG-filen till disk.

```csharp
// Step 3: Save the barcode with the default setting (filled bars)
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Ersätt `YOUR_DIRECTORY` med den faktiska sökvägen där du vill ha utdatafilerna. `BarCodeImageFormat.Png`-enumerationen garanterar förlustfri kompression, vilket är idealiskt för efterföljande bearbetning.

## Steg 4 – skapa en annan Planet-streckkodsgenerator för tomma staplar

För att producera en version som använder **tomma staplar** (vita moduler på en svart bakgrund) behöver du en andra `BarcodeGenerator`-instans. Återanvändning av samma datat sträng säkerställer att båda bilderna representerar samma postkod.

```csharp
// Step 4: Create another Planet barcode generator for the same data
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Att skapa en separat generator isolerar `FilledBars`-egenskapen, vilket låter dig växla den visuella stilen utan att påverka den första bilden.

## Steg 5 – konfigurera generatorn för att rendera tomma staplar

`FilledBars`-flaggan vänder renderingsläget. Att sätta den till `false` instruerar biblioteket att rita staplarna som tomma (transparenta) samtidigt som bakgrunden förblir solid.

```csharp
// Step 5: Apply the same X‑dimension and configure empty bars
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
planetEmpty.Parameters.Barcode.FilledBars = false;
```

Att hålla X‑dimensionen identisk med den fyllda versionen garanterar att båda PNG-filerna har samma dimensioner, vilket förenklar layoutberäkningar i utskriftsmallar.

## Steg 6 – spara streckkoden som renderar tomma staplar

Slutligen, skriv den tomma‑staplar-bilden till disk. Samma PNG-format används, men du kan byta till JPEG eller BMP genom att ändra `BarCodeImageFormat`-värdet.

```csharp
// Step 6: Save the barcode that renders empty bars
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

Vid detta tillfälle har du två filer:

* `PostalPlanetFilledBars.png` – solida svarta staplar.
* `PostalPlanetEmptyBars.png` – ihåliga staplar på en svart bakgrund.

Båda uppfyller postens specifikation för Planet-symbologin.

## Komplett källkod

Att sätta ihop alla steg ger en kompakt konsolapplikation som du kan köra direkt.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a Planet barcode with filled bars
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Create a Planet barcode with empty bars
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

Kompilera och kör programmet:

```bash
dotnet run
```

Konsolen skriver ut *Barcodes generated successfully.* och de två PNG-filerna visas i projektmappen.

## Förväntad output

Nedan är en visuell representation av bilden med fyllda staplar. Den tomma‑staplar-motsvarigheten ser identisk ut förutom att staplarna är transparenta.

![Exempel på en skapad postal planet-streckkod med fyllda staplar](postal-planet-filled.png)

*Bildens alt‑text:* **Exempel på en skapad postal planet-streckkod med fyllda staplar** (innehåller huvudnyckelordet).

Båda bilderna är 150 × 150 pixlar som standard, men du kan kontrollera den totala storleken med `ImageWidth` och `ImageHeight`-parametrarna om en annan upplösning krävs.

## Valfria variationer

### Ändra bildformatet

Om ditt efterföljande system föredrar JPEG, ersätt `BarCodeImageFormat.Png` med `BarCodeImageFormat.Jpeg`. JPEG introducerar komprimeringsartefakter, så använd det endast när filstorlek är en kritisk begränsning.

### Skala streckkoden

Du kan förstora streckkoden samtidigt som du bevarar modulbredden genom att justera `Resolution`-egenskapen:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI
```

Högre DPI‑värden förbättrar utskriftskvaliteten på laserskrivare.

### Använd en anpassad bakgrundsfärg

Bakgrunden kan sättas med:

```csharp
planetEmpty.Parameters.Barcode.BackColor = System.Drawing.Color.LightGray;
```

Detta är användbart för visuell testning men bör undvikas i produktionspostetiketter, som kräver en vit bakgrund.

## Vanliga frågor

**Fungerar detta med .NET Core?**  
Ja. Aspose.BarCode-biblioteket riktar sig mot .NET Standard 2.0, vilket är kompatibelt med .NET 5, .NET 6 och .NET Core 3.1.

**Vad händer om datat strängen innehåller icke‑numeriska tecken?**  
Planet-streckkoder accepterar endast numerisk inmatning. Att ange bokstäver eller symboler utlöser ett `BarcodeException`. Validera inmatningen innan du skapar generatorn.

**Kan jag generera en streckkod i minnet utan att skriva till disk?**  
Använd `GenerateBarCodeImage`-metoden för att få ett `System.Drawing.Image`-objekt, och strömma det direkt till ett svar eller en databas.

## Slutsats

Du vet nu hur man **skapar postal planet-streckkod** i C# och förstår **hur man genererar planet-streckkod** med både fyllda och tomma stapelstilar. Handledningen täckte hela arbetsflödet – från att initiera generatorn, konfigurera X‑dimensionen, växla `FilledBars`-flaggan, till att spara PNG-filer. Experimentera med bildformat, DPI‑inställningar och bakgrundsfärger för att anpassa streckkoden till ditt specifika postningssystem.

För nästa steg, utforska andra post‑symbologier som **POSTNET** eller **Intelligent Mail** med samma Aspose.BarCode API. Att justera parametrar som `EncodeTypes.Postnet` följer samma mönster som demonstrerats här, vilket låter dig bygga en omfattande streckkodsgenereringssvit i en enda kodbas.

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Skapa tom planet-streckkod, generera postal streckkod i C#](/barcode/english/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/)
- [Hur man ställer in bredd och genererar en Planet-streckkod i C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Generera postal streckkod i C# – Komplett guide med Planet-streckkod](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}