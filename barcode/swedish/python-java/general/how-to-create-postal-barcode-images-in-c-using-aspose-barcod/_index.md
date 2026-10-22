---
category: general
date: 2026-10-21
description: Lär dig hur du skapar poststreckkodsbilder i C# med Aspose.BarCode –
  generera Planet‑ och RM4SCC‑streckkoder, kontrollera fyllda staplar och spara PNG‑filer.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- generate planet barcode
- how to generate barcode c#
language: sv
lastmod: 2026-10-21
og_description: Skapa poststreckkodsbilder i C# med Aspose.BarCode. Denna handledning
  visar hur du genererar Planet- och RM4SCC-streckkoder, växlar fyllda staplar och
  sparar PNG-filer.
og_image_alt: Screenshot of a generated Planet postal barcode with filled bars
og_title: Skapa poststreckkodsbilder i C# – steg‑för‑steg guide
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to create postal barcode images in C# with Aspose.BarCode
    – generate Planet and RM4SCC barcodes, control filled bars, and save PNG files.
  headline: How to create postal barcode images in C# using Aspose.BarCode
  type: TechArticle
- description: Learn how to create postal barcode images in C# with Aspose.BarCode
    – generate Planet and RM4SCC barcodes, control filled bars, and save PNG files.
  name: How to create postal barcode images in C# using Aspose.BarCode
  steps:
  - name: 1. Prepare the output folder
    text: The barcode images need a writable directory. The code creates the folder
      if it does not exist, preventing a runtime `DirectoryNotFoundException`.
  - name: 2. Generate a Planet barcode with filled bars
    text: Planet barcodes are used by many postal services for domestic mail. The
      default `FilledBars` setting renders solid bars, which is the most common visual
      style.
  - name: 3. Generate a Planet barcode with empty bars
    text: Some postal specifications require **empty** (hollow) bars. You can toggle
      this behavior via the `FilledBars` property.
  - name: 4. Generate an RM4SCC barcode with filled bars
    text: RM4SCC (Royal Mail 4‑State Customer Code) is the UK postal barcode. Like
      Planet, the default appearance uses solid bars.
  - name: Full source code in one block
    text: Copy the following snippet into a new C# console project. It compiles with
      .NET 6.0 and produces three PNG files in the `Barcodes` subfolder.
  - name: Next steps
    text: '* **Generate other postal barcodes** – try `EncodeTypes.Postnet` or `EncodeTypes.USPSIntelligentMail`.
      * **Customize appearance** – experiment with `BarHeight`, `ForeColor`, and `BackColor`
      to match your branding. * **Integrate into a web service** – expose the generation
      logic via ASP.NET Core endp'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Hur man skapar poststreckkodsbilder i C# med Aspose.BarCode
url: /sv/python-java/general/how-to-create-postal-barcode-images-in-c-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar poststreckkodsbilder i C# med Aspose.BarCode

Om du behöver **skapa poststreckkoder** i ett .NET‑projekt visar den här guiden en komplett, färdig‑att‑köra lösning. Du får se hur du genererar Planet‑ och RM4SCC‑streckkoder, växlar mellan fyllda och tomma staplar och sparar resultaten som PNG‑filer – allt med några få rader C#‑kod.

Att generera pålitliga poststreckkoder är avgörande för postautomatisering, massutskrift av etiketter och integration med logistikplattformar. I slutet av den här handledningen har du ett återanvändbart kodsnutt som du kan kopiera in i vilken C#‑konsol‑ eller webbapplikation som helst.

## Förutsättningar

* .NET 6.0 SDK eller senare installerat  
* Visual Studio 2022 (eller någon IDE som stödjer .NET)  
* Ett aktivt **Aspose.BarCode** NuGet‑paket (`Install-Package Aspose.BarCode`)  

Dessa verktyg räcker för att kompilera och köra exemplet utan ytterligare beroenden.

## Steg‑för‑steg‑guide för att **skapa poststreckkoder** bilder

Processen består av fyra logiska steg:

1. Förbered utdatamappen.  
2. Generera en Planet‑streckkod med fyllda staplar (standardutseendet).  
3. Generera en Planet‑streckkod med tomma staplar.  
4. Generera en RM4SCC‑streckkod med fyllda staplar.  

Varje steg förklaras nedan, och den fullständiga källkoden visas efter förklaringarna.

### 1. Förbered utdatamappen

Streckkodsbilderna kräver en skrivbar katalog. Koden skapar mappen om den inte finns, vilket förhindrar ett runtime‑`DirectoryNotFoundException`.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Define the output folder (adjust the path to your environment)
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

        // Ensure the folder exists
        Directory.CreateDirectory(outputFolder);
```

*Varför detta är viktigt*: En saknad katalog stoppar programmet innan någon streckkod genereras. Att använda `Directory.CreateDirectory` är säkert eftersom det inte gör något om mappen redan finns.

### 2. Generera en Planet‑streckkod med fyllda staplar

Planet‑streckkoder används av många posttjänster för inrikespost. Standardinställningen `FilledBars` renderar solida staplar, vilket är den vanligaste visuella stilen.

```csharp
        // Step 2: Generate a Planet barcode with filled bars (default)
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        // XDimension controls the width of a single bar; 4 pixels works well for screen display
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
        planetFilled.Save(Path.Combine(outputFolder, "PostalPlanetFilledBars.png"),
                          BarCodeImageFormat.Png);
```

*Förklaring*:  
* `EncodeTypes.Planet` talar om för Aspose.BarCode att använda Planet‑standarden.  
* Datatsträngen `"123456"` är en giltig Planet‑payload (6 numeriska tecken).  
* `XDimension.Pixels = 4` ger en stapelbredd på 4 px, vilket balanserar läsbarhet och filstorlek.  
* `Save` sparar bilden som PNG, ett förlustfritt format som lämpar sig för vidare bearbetning.

### 3. Generera en Planet‑streckkod med tomma staplar

Vissa poststandarder kräver **tomma** (håliga) staplar. Du kan växla detta beteende via egenskapen `FilledBars`.

```csharp
        // Step 3: Generate a Planet barcode with empty bars
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        // Setting FilledBars to false creates hollow bars
        planetEmpty.Parameters.Barcode.FilledBars = false;
        planetEmpty.Save(Path.Combine(outputFolder, "PostalPlanetEmptyBars.png"),
                         BarCodeImageFormat.Png);
```

*Tips*: När du växlar mellan fyllda och tomma staplar, behåll `XDimension`‑värdet oförändrat för att upprätthålla konsekvent storlek över bilderna.

### 4. Generera en RM4SCC‑streckkod med fyllda staplar

RM4SCC (Royal Mail 4‑State Customer Code) är den brittiska poststreckkoden. Liksom Planet använder standardutseendet solida staplar.

```csharp
        // Step 4: Generate an RM4SCC barcode with filled bars (default)
        BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFilled.Save(Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png"),
                          BarCodeImageFormat.Png);
    }
}
```

*Varför RM4SCC*: RM4SCC‑formatet kodar en 6‑siffrig numerisk sträng plus en kontrollsumma, vilket gör det idealiskt för brittiska posttjänster.

### Fullständig källkod i ett block

Kopiera följande kodsnutt till ett nytt C#‑konsolprojekt. Det kompileras med .NET 6.0 och skapar tre PNG‑filer i undermappen `Barcodes`.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // -------------------------------------------------
        // 1. Prepare the output folder
        // -------------------------------------------------
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // -------------------------------------------------
        // 2. Planet barcode – filled bars (default)
        // -------------------------------------------------
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
        planetFilled.Save(Path.Combine(outputFolder, "PostalPlanetFilledBars.png"),
                          BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 3. Planet barcode – empty bars
        // -------------------------------------------------
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmpty.Parameters.Barcode.FilledBars = false;
        planetEmpty.Save(Path.Combine(outputFolder, "PostalPlanetEmptyBars.png"),
                         BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 4. RM4SCC barcode – filled bars (default)
        // -------------------------------------------------
        BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFilled.Save(Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png"),
                          BarCodeImageFormat.Png);

        Console.WriteLine("All barcode images have been saved to: " + outputFolder);
    }
}
```

#### Förväntat resultat

När programmet körs skrivs en bekräftelserad ut och tre filer skapas:

* `PostalPlanetFilledBars.png` – solid‑staplad Planet‑streckkod  
* `PostalPlanetEmptyBars.png` – hålig‑staplad Planet‑streckkod  
* `PostalRM4SCCFilledBars.png` – solid‑staplad RM4SCC‑streckkod  

Varje bild är 4 px per stapel bred, lämplig för skärmpreview eller för inbäddning i utskriftsklar PDF.

## Vanliga frågor och hantering av kantfall

| Fråga | Svar |
|----------|--------|
| **Vad händer om datasträngen är ogiltig?** | Aspose.BarCode kastar `ArgumentException`. Validera inmatningens längd (Planet = 6 numeriska, RM4SCC = 6 numeriska) innan generatorn skapas. |
| **Kan jag ändra bildformatet?** | Ja. Byt ut `BarCodeImageFormat.Png` mot `Jpeg`, `Gif`, `Bmp` eller `Tiff` efter behov. |
| **Hur justerar jag stapelhöjden?** | Använd `planetFilled.Parameters.Barcode.BarHeight` (standard är 50 px). |
| **Är det säkert att använda denna kod i ett web‑API?** | Absolut. Generatorn är trådsäker för skriv‑skyddade operationer, men skapa en ny `BarcodeGenerator` per begäran för att undvika delat tillstånd. |
| **Vad sägs om andra poststandarder?** | Aspose.BarCode stödjer även `EncodeTypes.Postnet`, `EncodeTypes.USPSIntelligentMail` osv. Samma mönster gäller – byt bara `EncodeTypes`‑värdet. |

## Slutsats

Du vet nu hur du **skapar poststreckkodsbilder** i C# med Aspose.BarCode, både för Planet‑ och RM4SCC‑formaten, och hur du växlar mellan fyllda och tomma staplar. Det kompletta, körbara exemplet kan klistras in i vilket .NET‑projekt som helst och ger dig omedelbart visuellt resultat.

### Nästa steg

* **Generera andra poststreckkoder** – prova `EncodeTypes.Postnet` eller `EncodeTypes.USPSIntelligentMail`.  
* **Anpassa utseendet** – experimentera med `BarHeight`, `ForeColor` och `BackColor` för att matcha ditt varumärke.  
* **Integrera i en webbtjänst** – exponera genereringslogiken via ASP.NET Core‑endpoints för efterfrågan‑baserad streckkodsskapning.  

Genom att behärska dessa tekniker kan du **generera planet‑streckkoder** och svara på frågor som “**hur genererar man streckkod i C#**” med självförtroende, oavsett om du bygger ett skrivbordsverktyg för post eller ett molnbaserat frakt‑API. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar planet‑streckkod med fyllda och tomma staplar](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [Hur man skapar RM4SCC‑streckkod och genererar planet‑streckkod i C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [Generera poststreckkod i C# – Komplett guide med planet‑streckkod](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}