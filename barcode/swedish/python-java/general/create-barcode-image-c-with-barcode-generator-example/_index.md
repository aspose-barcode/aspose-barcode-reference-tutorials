---
category: general
date: 2026-09-10
description: Skapa streckkodbild i C# snabbt med ett streckkodsgenerator‑exempel i
  C# som visar hur man ställer in dimensioner och sparar PNG‑filer.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image c#
- barcode generator example c#
language: sv
lastmod: 2026-09-10
og_description: Skapa streckkodbild i C# med ett koncist exempel på streckkodsgenerator
  i C#. Lär dig att konfigurera storlek, höjd och exportera PNG-filer på några minuter.
og_image_alt: Screenshot of a barcode image created with C# code
og_title: Skapa streckkodsbild i C# – steg‑för‑steg generatorexempel
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create barcode image C# quickly using a barcode generator example C#
    that shows how to set dimensions and save PNG files.
  headline: Create barcode image C# with barcode generator example
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: Skapa streckkodbild i C# med exempel på streckkodsgenerator
url: /sv/python-java/general/create-barcode-image-c-with-barcode-generator-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa streckkodbild C# med exempel på streckkodsgenerator

Om du behöver **create barcode image C#** för produktmärkning, lagerhantering eller mobilskanning, visar den här guiden en komplett lösning. Du kommer att se ett **barcode generator example C#** som konfigurerar modulbredd, stapelhöjd och sparar PNG-filer på bara några kodrader.

Handledningen täcker allt från att installera det erforderliga biblioteket till att köra ett färdigt att kompilera konsolprogram. I slutet kommer du att ha två streckkod-PNG-filer – en med 30‑pixel stapelhöjd och en annan med 60‑pixel stapelhöjd – redo att användas i vilken .NET-applikation som helst.

## Förutsättningar

* .NET 6.0 SDK eller senare installerat  
* En utvecklingsmiljö såsom Visual Studio 2022 eller VS Code  
* NuGet‑paketet **Aspose.BarCode** (koden använder `BarcodeGenerator` från detta bibliotek)  

Du kan lägga till paketet med följande CLI‑kommando:

```bash
dotnet add package Aspose.BarCode
```

## Steg 1: Ställ in konsolprojektet

Skapa ett nytt konsolprojekt och referera till streckkodsbiblioteket.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Kommandot skapar en `Program.cs`‑fil där du kommer att placera **barcode generator example C#**‑koden.

## Steg 2: Skriv hela programmet för streckkodsgenerering

Ersätt innehållet i `Program.cs` med det kompletta, körbara exemplet nedan. Programmet demonstrerar hur man **create barcode image C#** med anpassade dimensioner och hur man sparar resultatet som PNG‑filer.

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
            // 1️⃣ Create a DataBar Omnidirectional barcode generator with the desired data.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set the X‑dimension (module width) to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Configure a 30‑pixel bar height and save the first image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            SaveBarcode(generator, "DatabarBarHeight30Pixels.png");

            // 4️⃣ Change the bar height to 60 pixels and save the second image.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            SaveBarcode(generator, "DatabarBarHeight60Pixels.png");

            Console.WriteLine("Barcode images have been saved to the output folder.");
        }

        /// <summary>
        /// Saves the current barcode image as a PNG file.
        /// </summary>
        /// <param name="generator">The configured BarcodeGenerator instance.</param>
        /// <param name="fileName">The file name for the PNG image.</param>
        private static void SaveBarcode(BarcodeGenerator generator, string fileName)
        {
            // Ensure the output directory exists.
            string outputPath = System.IO.Path.Combine(
                AppDomain.CurrentDomain.BaseDirectory, "output");
            System.IO.Directory.CreateDirectory(outputPath);

            // Combine the directory and file name.
            string fullPath = System.IO.Path.Combine(outputPath, fileName);

            // Save the barcode as a PNG image.
            generator.Save(fullPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Varför varje rad är viktig

* **EncodeTypes.DatabarOmniDirectional** – väljer DataBar Omnidirectional‑symbologi, som kodar numerisk data och är allmänt använd inom detaljhandel.  
* **XDimension.Pixels = 2** – sätter modulbredden; ett mindre värde ger en mer kompakt streckkod.  
* **BarHeight.Pixels** – styr den visuella höjden på staplarna. Genom att justera detta värde kan du skapa streckkoder som passar olika etikettstorlekar.  
* **Save method** – skriver streckkoden till en PNG‑fil, ett format som bevarar skarpa kanter och fungerar med de flesta bildbibliotek.

## Steg 3: Bygg och kör programmet

Kör följande kommando från projektmappen:

```bash
dotnet run
```

När programmet är klart kommer du att se två PNG‑filer i `output`‑undermappen:

* `DatabarBarHeight30Pixels.png` – 30‑pixel stapelhöjd  
* `DatabarBarHeight60Pixels.png` – 60‑pixel stapelhöjd  

Båda bilderna innehåller samma kodade data men skiljer sig i visuell höjd, vilket visar hur **barcode generator example C#** kan anpassas för olika etikettkrav.

## Steg 4: Verifiera de genererade streckkoderna

Öppna PNG‑filerna med någon bildvisare. Du bör se en tydlig, högkontrast DataBar‑streckkod. För att bekräfta att streckkoderna är läsbara kan du använda en mobil skannerapp (t.ex. ZXing‑baserade appar) eller ett skrivbordsbibliotek som **Aspose.BarCode** i avkodningsläge:

```csharp
var reader = new BarCodeReader(fullPath, DecodeType.DatabarOmniDirectional);
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"Decoded value: {result.CodeText}");
}
```

Om utdata matchar `(01)12345678901231` har genereringen lyckats.

## Vanliga variationer och kantfall

| Situation | Justering | Kodsnutt |
|-----------|------------|--------------|
| **Olika symbologi** (t.ex. QR, Code128) | Ändra `EncodeTypes`‑värde | `new BarcodeGenerator(EncodeTypes.QR, "Hello World")` |
| **Anpassat bildformat** (JPEG, BMP) | Använd en annan `BarCodeImageFormat`‑enum | `generator.Save(path, BarCodeImageFormat.Jpeg)` |
| **Dynamisk data** (användarinmatning) | Ersätt den hårdkodade strängen med en variabel | `string data = Console.ReadLine(); var generator = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data);` |
| **Ogiltig datalängd** | Fånga `ArgumentException` som kastas av generatorn | ```csharp try { ... } catch (ArgumentException ex) { Console.WriteLine(ex.Message); }``` |

Proffstips: validera alltid indata‑längden för den valda symbologin; Aspose.BarCode kastar ett undantag om data inte uppfyller specifikationen.

## Felsökningschecklista

* **Directory not found** – Hjälpfunktionen `SaveBarcode` skapar automatiskt `output`‑mappen, men se till att applikationen har skrivbehörighet.  
* **Unexpected image size** – Verifiera att `XDimension.Pixels` och `BarHeight.Pixels` är satta innan du anropar `Save`. Att ändra dessa värden efter sparning påverkar inte redan skrivna filer.  
* **Unreadable barcode** – Se till att den kodade strängen följer GS1‑formatet när du använder DataBar‑symbologier. Saknade parenteser eller felaktiga Application Identifiers orsakar avkodningsfel.

## Slutsats

Du vet nu hur man **create barcode image C#** med ett praktiskt **barcode generator example C#**. Det kompletta programmet sätter modulbredd, justerar stapelhöjd och sparar PNG‑filer med minimal kod. Härifrån kan du utforska ytterligare funktioner såsom färganpassning, flersidig PDF‑export eller realtidsgenerering i ASP.NET Core‑webb‑API:er.

**Nästa steg**

* Experimentera med andra symbologier (`EncodeTypes.Code128`, `EncodeTypes.QR`) för att bredda dina skanningsalternativ.  
* Integrera generatorn i en webbtjänst som returnerar streckkodsbilder på begäran.  
* Kombinera streckkoden med produktmetadata i en PDF‑faktura med hjälp av Aspose.PDF.

Lycka till med kodandet, och njut av den flexibilitet som C# erbjuder för skapande av streckkodsbilder!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Barcode Generator Example i C# – Ställ in kolumner, rader och exportera bild](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Skapa streckkodbild C# – GS1 DataMatrix‑exempel](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Barcode Generator Example – Bygg DataBar‑bild i C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}