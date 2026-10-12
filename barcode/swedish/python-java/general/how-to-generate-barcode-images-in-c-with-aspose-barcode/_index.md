---
category: general
date: 2026-10-12
description: Hur man snabbt genererar streckkod i C#. Lär dig att skapa en tom streckkod
  och anpassa streckbredden för tydliga poststreckkoder.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create empty barcode
language: sv
lastmod: 2026-10-12
og_description: Hur man genererar streckkod i C# med Aspose.BarCode. Denna guide visar
  hur du skapar en tom streckkod och justerar stapeldimensionerna för poststandarder.
og_image_alt: Screenshot of generated barcode image created with how to generate barcode
  tutorial
og_title: Hur man genererar streckkodsbilder i C# – steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to generate barcode in C# quickly. Learn to create empty barcode
    and customize bar width for clear postal barcodes.
  headline: How to generate barcode images in C# with Aspose.BarCode
  type: TechArticle
- description: How to generate barcode in C# quickly. Learn to create empty barcode
    and customize bar width for clear postal barcodes.
  name: How to generate barcode images in C# with Aspose.BarCode
  steps:
  - name: Why this step matters
    text: '* **Project scaffolding** ensures the tutorial is runnable without extra
      configuration. * The `using Aspose.BarCode.Generation;` and `using Aspose.BarCode;`
      namespaces expose the `BarcodeGenerator` class and image formats. * Creating
      the output folder programmatically avoids “directory not found” er'
  - name: Expected output
    text: Running the program will create an image similar to the one below (the actual
      image is not displayed here, but you’ll see a clear, 6‑digit barcode when you
      open the file).
  - name: Expected output
    text: 'The generated PNG contains only the bar outlines:'
  - name: Expected output
    text: '```text [PostalRM4SCCFilledBars.png] // solid bars representing "123456"
      ```'
  type: HowTo
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Hur man genererar streckkodsbilder i C# med Aspose.BarCode
url: /sv/python-java/general/how-to-generate-barcode-images-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar streckkodsbilder i C# med Aspose.BarCode

Om du behöver **hur man genererar streckkod**‑bilder från en sträng i en .NET‑applikation, ger den här guiden en komplett, färdig‑att‑köra‑lösning. Du får se hur du genererar standard‑Planet‑ och RM4SCC‑streckkoder, justerar stapelbredd för läsbarhet och **skapar tomma streckkoder** där staplarna är oifyllda. Koden fungerar med den senaste Aspose.BarCode för .NET (v.24.10) och körs på .NET 6 eller senare.

Att generera streckkoder är ett vanligt krav för fraktetiketter, lagersystem och biljettplattformar. I slutet av den här tutorialen kommer du att kunna producera både fyllda och tomma streckkoder programatiskt, utan att behöva externa verktyg.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6 SDK (eller någon nyare .NET‑version)
* Visual Studio 2022 eller VS Code
* En giltig Aspose.BarCode för .NET‑licens (den fria utvärderingen fungerar för testning)
* Grundläggande kunskap om C#‑konsolapplikationer

Du kan installera Aspose.BarCode NuGet‑paketet med:

```bash
dotnet add package Aspose.BarCode
```

## Steg 1: Skapa ett minimalt konsolprojekt

Skapa ett nytt konsolprojekt och lägg till de nödvändiga `using`‑direktiven. Följande kod är ett självständigt exempel; kopiera det till `Program.cs` och kör det.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Define output folder (adjust to your environment)
            string outputFolder = @"C:\Barcodes";

            // Ensure the folder exists
            System.IO.Directory.CreateDirectory(outputFolder);

            // Generate filled Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: true);

            // Generate empty Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: false);

            // Generate filled RM4SCC barcode
            GenerateRM4SCCBarcode(outputFolder, "123456");

            Console.WriteLine("All barcodes have been saved to " + outputFolder);
        }

        /// <summary>
        /// Generates a Planet barcode and optionally disables bar filling.
        /// </summary>
        static void GeneratePlanetBarcode(string folder, string data, bool filled)
        {
            // Create generator for Planet symbology
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, data);

            // Set X dimension (bar width) to 4 pixels for better visibility
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // Control whether bars are filled or left empty
            generator.Parameters.Barcode.FilledBars = filled;

            // Choose a file name that reflects the filling mode
            string fileName = filled
                ? "PostalPlanetFilledBars.png"
                : "PostalPlanetEmptyBars.png";

            // Save the image as PNG
            generator.Save(System.IO.Path.Combine(folder, fileName), BarCodeImageFormat.Png);
        }

        /// <summary>
        /// Generates an RM4SCC barcode with default filled bars.
        /// </summary>
        static void GenerateRM4SCCBarcode(string folder, string data)
        {
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.RM4SCC, data);

            // Consistent bar width with Planet example
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            string fileName = "PostalRM4SCCFilledBars.png";
            generator.Save(System.IO.Path.Combine(folder, fileName), BarCodeImageFormat.Png);
        }
    }
}
```

### Varför detta steg är viktigt

* **Projekt‑scaffolding** säkerställer att tutorialen är körbar utan extra konfiguration.
* `using Aspose.BarCode.Generation;` och `using Aspose.BarCode;`‑namnutrymmena exponerar klassen `BarcodeGenerator` och bildformaten.
* Att skapa utdatamappen programatiskt undviker fel som “directory not found” vid första körningen.

## Steg 2: Generera en fylld Planet‑streckkod

Det första anropet till `GeneratePlanetBarcode` skickar `filled: true`. Detta producerar en standard Planet‑streckkod där varje stapel renderas som en solid, svart rektangel.

* **Resulterande fil:** `PostalPlanetFilledBars.png`
* **Visuell indikation:** Staplarna är svarta, i enlighet med postens specifikationer för tryckt post.

### Förväntad utdata

När programmet körs skapas en bild som liknar bilden nedan (den faktiska bilden visas inte här, men du kommer att se en tydlig 6‑siffrig streckkod när du öppnar filen).

```text
[PostalPlanetFilledBars.png]  // image shows solid black bars
```

## Steg 3: Skapa tom streckkod (Planet med oifyllda staplar)

För att **skapa tom streckkod** anropas samma metod med `filled: false`. `FilledBars`‑egenskapen instruerar Aspose.BarCode att endast rita konturerna av staplarna, så att insidan blir transparent.

* **Resulterande fil:** `PostalPlanetEmptyBars.png`
* **Användningsområde:** Tomma streckkoder är användbara när du vill att bakgrunden ska visa en logotyp eller färg samtidigt som streckkoden förblir läsbar.

### Förväntad utdata

Den genererade PNG‑filen innehåller endast stapelkonturerna:

```text
[PostalPlanetEmptyBars.png]  // image shows hollow bar shapes
```

## Steg 4: Generera en fylld RM4SCC‑streckkod

RM4SCC är den nederländska postens streckkodstandard. Exemplet använder samma X‑dimension (4 pixlar) för att behålla visuell konsistens med Planet‑streckkoderna.

* **Resulterande fil:** `PostalRM4SCCFilledBars.png`
* **Varför RM4SCC?** Den kodar numerisk data i ett kompakt format som många europeiska posttjänster accepterar.

### Förväntad utdata

```text
[PostalRM4SCCFilledBars.png]  // solid bars representing "123456"
```

## Praktiska tips och vanliga fallgropar

| Tips | Förklaring |
|-----|-------------|
| **Konsekvent X‑dimension** | Att använda samma `XDimension.Pixels`‑värde över olika symbologier säkerställer ett enhetligt utseende på tryckta etiketter. |
| **Återanvänd inte samma generatorinstans** | Att ändra `FilledBars` på en befintlig generator kan ge oväntade resultat; skapa en ny `BarcodeGenerator` för varje unik streckkod. |
| **Verifiera bildformat** | PNG är förlustfritt och idealiskt för streckkoder; JPEG‑komprimering kan sudda ut tunna staplar och leda till skanningsfel. |
| **Licenshantering** | Om du kör koden utan licens kommer de genererade bilderna att innehålla ett vattenmärke. Applicera din licens tidigt i `Main` med `License license = new License(); license.SetLicense("Aspose.BarCode.lic");`. |
| **Trådsäkerhet** | `BarcodeGenerator` är **inte** trådsäker. Skapa separata instanser per tråd om du genererar streckkoder parallellt. |

## Edge cases du kan stöta på

* **Datalängdsgränser** – Planet‑streckkoder accepterar upp till 6 numeriska tecken. Att ange fler tecken kastar ett `ArgumentException`. Validera indata­längden innan du anropar generatorn.
* **Icke‑numerisk data** – RM4SCC förväntar sig också numerisk indata. För alfanumerisk data behövs en annan symbologi (t.ex. Code128). Samma mönster för att sätta `FilledBars` fungerar för alla streckkodstyper som stödjer det.
* **Högupplöst utskrift** – Om du behöver streckkoder större än skärmstorleken, öka `XDimension.Pixels` (t.ex. 8 eller 10) och eventuellt sätt `Resolution` i `generator.Parameters.Image`. Detta håller staplarna skarpa vid 300 dpi‑utskrift.

## Fullständig källfil‑sammanfattning

Nedan återfinns hela källfilen igen för snabb kopiering‑och‑klistra. Den innehåller alla steg, kommentarer och det valfria licens‑snutten (kommenterad).

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Optional: apply your Aspose.BarCode license here
            // var license = new License();
            // license.SetLicense("Aspose.BarCode.lic");

            string outputFolder = @"C:\Barcodes";
            System.IO.Directory.CreateDirectory(outputFolder);

            // Filled Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: true);

            // Empty Planet barcode (create empty barcode)
            GeneratePlanetBarcode(outputFolder, "123456", filled: false);

            // Filled RM4SCC barcode
            GenerateRM4SCCBarcode(outputFolder, "123456");

            Console.WriteLine("All barcodes saved to " + outputFolder);
        }

        static void GeneratePlanetBarcode(string folder, string data, bool filled)
        {
            var generator = new BarcodeGenerator(EncodeTypes.Planet, data);
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.FilledBars = filled;

            string fileName = filled ? "PostalPlanetFilledBars.png"
                                     : "PostalPlanetEmptyBars.png";

            generator.Save(System.IO.Path.Combine(folder, fileName),
                           BarCodeImageFormat.Png);
        }

        static void GenerateRM4SCCBarcode(string folder, string data)
        {
            var generator = new BarcodeGenerator(EncodeTypes.RM4SCC, data);
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            string fileName = "PostalRM4SCCFilledBars.png";
            generator.Save(System.IO.Path.Combine(folder, fileName),
                           BarCodeImageFormat.Png);
        }
    }
}
```

## Slutsats

Du vet nu **hur man genererar streckkod**‑bilder i C# med Aspose.BarCode, och du kan **skapa tomma streckkoder** genom att växla `FilledBars`‑egenskapen. Tutorialen täckte:

* Att sätta upp ett konsolprojekt och installera Aspose.BarCode‑paketet
* Generering av fyllda Planet‑ och RM4SCC‑streckkoder
* Produktion av en tom (endast kontur) Planet‑streckkod
* Justering av stapelbredd för läsbarhet samt hantering av vanliga fallgropar

Nästa steg är att utforska andra symbologier (Code128, QR, DataMatrix) och experimentera med färg, storlek och bildformat. Att integrera streckkodsgenerering i ett webb‑API eller en Windows‑tjänst följer samma mönster – byt bara ut konsol‑`Main`‑metoden mot din applikations ingångspunkt.

Lycka till med kodningen, och låt dina applikationer börja skanna!

## Vad bör du lära dig härnäst?

De följande tutorialerna behandlar närbesläktade ämnen som bygger vidare på teknikerna i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationssätt i dina egna projekt.

- [How to create postal barcode image in C# using Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)
- [How to generate postal barcode in C# with custom dimensions](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/)
- [How to generate barcode image with Aspose.BarCode in C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}