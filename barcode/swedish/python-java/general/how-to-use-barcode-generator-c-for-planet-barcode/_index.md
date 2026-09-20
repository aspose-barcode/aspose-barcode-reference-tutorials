---
category: general
date: 2026-09-19
description: barcode generator C#‑guide visar hur man genererar en Planet‑streckkod
  och exporterar streckkodsbilden som PNG på bara några rader.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- how to generate barcode
- create planet barcode
- export barcode image
language: sv
lastmod: 2026-09-19
og_description: barcode generator C# låter dig snabbt skapa en Planet-streckkod och
  exportera bilden som PNG för vilken .NET‑app som helst.
og_image_alt: Screenshot of a Planet barcode generated with barcode generator C# showing
  empty bars
og_title: streckkodsgenerator C# – skapa Planet‑streckkod och exportera bild
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator C# guide shows how to generate a Planet barcode and
    export barcode image as PNG in just a few lines.
  headline: How to use barcode generator C# for Planet barcode
  type: TechArticle
tags:
- barcode
- C#
- image export
title: Hur man använder streckkodsgeneratorn C# för Planet‑streckkod
url: /sv/python-java/general/how-to-use-barcode-generator-c-for-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så använder du barcode generator C# för Planet-streckkod

Om du behöver en **barcode generator C#** som kan producera en Planet-streckkod, ger den här guiden dig en komplett lösning. Du kommer att lära dig **hur man genererar streckkod** data, anpassa utseendet och **exportera streckkodsbild** som en PNG-fil med bara några rader kod.

Att skapa streckkoder är ett vanligt krav för lagersystem, biljettplattformar och IoT‑enheter. I slutet av den här tutorialen kommer du att ha en självständig konsolapplikation som genererar en ren Planet-streckkod, inaktiverar fyllning av staplar och sparar resultatet till disk. Inga externa verktyg krävs utöver streckkodsbiblioteket.

## Förutsättningar

* .NET 6.0 SDK eller senare installerat  
* Ett C#‑kompatibelt streckkodsbibliotek (exemplet använder **Aspose.BarCode for .NET**, som stödjer Planet‑symbologi)  
* En IDE eller redigerare såsom Visual Studio 2022, VS Code eller Rider  

The library can be added via NuGet:

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Använd den senaste stabila versionen av paketet för att dra nytta av buggfixar och prestandaförbättringar.

## Så här använder du barcode generator C# för att skapa en Planet-streckkod

Det första steget är att instansiera generatorn med Planet‑symbologi och den data du vill koda.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for the Planet symbology with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

`BarcodeGenerator` är ingångspunkten för alla streckkodsoperationer. Konstruktorn tar emot symbologin (`EncodeTypes.Planet`) och den råa datan (`"123456"`). Denna kod **skapar en Planet-streckkod** som senare kan renderas som en bild.

## Justera streckkodens parametrar

För att kontrollera visuell kvalitet kan du ändra X‑dimensionen (modulbredd) och bestämma om staplarna ska fyllas.

```csharp
        // Step 2: Adjust the X-dimension (module width) to 4 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 3: Disable filling of the bars so that only the outlines are drawn
        generator.Parameters.Barcode.FilledBars = false;
```

* Att sätta `XDimension.Pixels` till **4** ger en högre upplösning på streckkoden utan att filstorleken ökar dramatiskt.  
* `FilledBars = false` ger enbart kontur‑stil, vilket är användbart när du vill att streckkoden ska smälta in i en bakgrund eller vid utskrift på enheter med låg bläckförbrukning.

## Exportera streckkodsbild

Efter att ha konfigurerat generatorn, spara resultatet till en PNG-fil. Metoden `Save` accepterar en fullständig sökväg och det önskade bildformatet.

```csharp
        // Step 4: Save the generated barcode image as a PNG file
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "PlanetEmptyBars.png");

        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

Koden skriver **exportera streckkodsbild** `PlanetEmptyBars.png` till användarens skrivbord. PNG är ett förlustfritt format som bevarar de skarpa kanterna på streckkoden, vilket gör det idealiskt för både skärmvisning och högupplöst utskrift.

> **Edge case:** Om du behöver ett annat format (JPEG, BMP, GIF), ersätt `BarCodeImageFormat.Png` med det lämpliga enum‑värdet. JPEG introducerar komprimeringsartefakter som kan påverka skannerns läsbarhet, så använd det endast när filstorlek är en kritisk faktor.

## Fullt, körbart exempel

Nedan är det kompletta programmet som du kan kopiera, klistra in och köra omedelbart.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Create a barcode generator for the Planet symbology with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Adjust the X-dimension (module width) to 4 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 4;

        // Disable filling of the bars so that only the outlines are drawn
        generator.Parameters.Barcode.FilledBars = false;

        // Define the output file path (Desktop folder is used for convenience)
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "PlanetEmptyBars.png");

        // Export the barcode image as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

När du kör programmet bör du se ett meddelande liknande:

```
Barcode saved to: C:\Users\YourName\Desktop\PlanetEmptyBars.png
```

Att öppna PNG-filen visar en ren Planet-streckkod med tomma staplar, exakt som konfigurerat.

![barcode generator C# example](/images/barcode-generator-csharp.png){alt="barcode generator C# exempel"}

## Vanliga frågor och felsökning

| Question | Answer |
|----------|--------|
| **Kan jag generera andra symbologier med samma kod?** | Ja. Ersätt `EncodeTypes.Planet` med någon annan stödjande typ, såsom `EncodeTypes.Code128` eller `EncodeTypes.QR`. |
| **Vad händer om streckkoden inte läses?** | Verifiera att datalängden följer Planet‑specifikationen (exakt 6 numeriska tecken). Säkerställ också tillräcklig kontrast mellan streckkoden och bakgrunden. |
| **Hur ändrar jag bildstorleken?** | Justera `generator.Parameters.ImageWidth` och `generator.Parameters.ImageHeight` eller ändra `XDimension` för att skala streckkoden proportionellt. |
| **Är det möjligt att lägga till en bildtext under streckkoden?** | Använd `generator.Parameters.Barcode.CodeTextVisible = true;` och anpassa `CodeTextParameters` för teckensnitt, justering och marginal. |

## Nästa steg

Nu när du har bemästrat **hur man genererar streckkod** bilder med en **barcode generator C#**, kan du utforska:

* Generera batch‑streckkods‑filer med en CSV‑lista av värden.  
* Bädda in PNG‑filen i PDF‑fakturor med Aspose.PDF.  
* Byta till `exportera streckkodsbild`‑format som SVG för skalbar webb‑grafik.  

Dessa tillägg fördjupar din förståelse för streckkodautomation i .NET och förbereder dig för verkliga integrationsscenarier.

---

**Sammanfattning:** Denna tutorial demonstrerade ett komplett **barcode generator C#**‑arbetsflöde—skapa en Planet-streckkod, anpassa dess utseende och **exportera streckkodsbilden** som PNG. Du kan anpassa samma mönster för andra symbologier, bildformat och utskriftsmål. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Barcode generator C# – generera streckkodsbild](/barcode/english/python-java/general/barcode-generator-c-generate-barcode-image/)
- [Skapa Planet-streckkodsbild i C# – Hur man genererar poststreckkod](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Barcode Generator‑exempel i C# – Ställ in kolumner, rader och exportera bild](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}