---
category: general
date: 2026-08-03
description: Barcode‑generator C#‑handledning visar hur man genererar streckkodsbilder
  med Aspose.BarCode, ställer in kolumner och rader samt sparar PNG‑filer för DataBar
  Expanded Stacked.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
language: sv
lastmod: 2026-08-03
og_description: Barcode generator C#‑handledning förklarar hur man genererar en streckkodbild
  med Aspose.BarCode, konfigurerar DataBar Expanded Stacked‑kolumner och -rader samt
  sparar PNG‑filer.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: Streckkodsgenerator C# – steg‑för‑steg guide för att generera streckkodsbild
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial shows how to generate barcode image with
    Aspose.BarCode, set columns and rows, and save PNG files for DataBar Expanded
    Stacked.
  headline: Barcode generator C# – generate barcode image
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Streckkodsgenerator C# – generera streckkodsbild
url: /sv/python-java/general/barcode-generator-c-generate-barcode-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generator C# – generera streckkodsbild

Om du behöver en barcode generator C# som kan generera streckkodsbild för DataBar Expanded Stacked, guidar den här artikeln dig genom hela processen. Du kommer att lära dig hur du konfigurerar kolumn‑ och radinställningar, sparar resultatet som PNG och anpassar koden för andra symbologier.

Att programatiskt generera streckkodsbilder eliminerar manuella steg och säkerställer konsekvens i fakturor, fraktetiketter och lagersystem. Denna handledning täcker allt du behöver, från projektuppsättning till fullständig källkod, så att du kan köra exemplet omedelbart.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 eller senare installerat  
* En IDE såsom Visual Studio 2022 (vilken editor som helst som stödjer C# fungerar)  
* En licens för **Aspose.BarCode for .NET** – den kostnadsfria utvärderingen fungerar för testning  
* Grundläggande kunskap om C#‑syntax  

Om någon av dessa komponenter saknas, installera .NET SDK från dotnet.microsoft.com och hämta Aspose.BarCode NuGet‑paketet med:

```bash
dotnet add package Aspose.BarCode
```

## Steg 1: Skapa ett barcode generator C#‑projekt

Skapa en ny konsolapplikation och lägg till de nödvändiga `using`‑direktiven:

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
            // The implementation starts in the next sections
        }
    }
}
```

Klassen `BarcodeGenerator` är kärnan i barcode generator C#‑API:et. Den tar emot symbology‑typen och texten som ska kodas.

## Steg 2: Generera en DataBar Expanded Stacked‑streckkod och ange kolumner

Det första exemplet skapar en streckkod med fyra kolumner. Genom att justera egenskapen `Columns` förändras den visuella tätheten i DataBar Expanded Stacked‑symbologin.

```csharp
// Step 2: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of columns to 4
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the barcode image as PNG
string colsPath = @"YOUR_DIRECTORY\DatabarCols4.png";
barcodeGenerator.Save(colsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 4 columns saved to {colsPath}");
```

**Varför detta är viktigt:** Antalet kolumner påverkar hur mycket data som kan lagras i ett kompakt utrymme. Att sätta det till 4 ger en bredare streckkod som fortfarande är läsbar av de flesta skannrar.

## Steg 3: Generera en streckkod med anpassat radantal

Det andra exemplet visar hur du styr den vertikala layouten genom att sätta egenskapen `Rows`. En konfiguration med tre rader är användbar när du behöver en högre streckkod för begränsat horisontellt utrymme.

```csharp
// Step 3: Create a second barcode generator for the same type
BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of rows to 3
barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

// Save the barcode image as PNG
string rowsPath = @"YOUR_DIRECTORY\DatabarRows3.png";
barcodeGeneratorRows.Save(rowsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 3 rows saved to {rowsPath}");
```

**Varför detta är viktigt:** Genom att justera rader kan du passa streckkoden i en smal kolumn samtidigt som läsbarheten bevaras. barcode generator C# beräknar automatiskt modulstorleken för att uppfylla specifikationen.

## Steg 4: Fullständigt, körbart exempel

Nedan finns ett fristående program som kombinerar de föregående stegen. Kopiera koden till `Program.cs`, ersätt `YOUR_DIRECTORY` med en befintlig mappväg och kör applikationen.

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
            // ---------- Generate barcode with 4 columns ----------
            BarcodeGenerator colsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            colsGenerator.Parameters.Barcode.DataBar.Columns = 4;

            string colsFile = @"YOUR_DIRECTORY\DatabarCols4.png";
            colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with columns saved to {colsFile}");

            // ---------- Generate barcode with 3 rows ----------
            BarcodeGenerator rowsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            rowsGenerator.Parameters.Barcode.DataBar.Rows = 3;

            string rowsFile = @"YOUR_DIRECTORY\DatabarRows3.png";
            rowsGenerator.Save(rowsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with rows saved to {rowsFile}");
        }
    }
}
```

### Förväntat resultat

När du kör programmet visas två PNG‑filer i mål‑katalogen:

* **DatabarCols4.png** – en DataBar Expanded Stacked‑streckkod med fyra kolumner  
* **DatabarRows3.png** – samma data kodad i tre rader  

Öppna bilderna med någon bildvisare; de visar skarpa, skannbara streckkoder redo för utskrift eller inbäddning i PDF‑filer.

## Hur du genererar streckkodsbild med anpassade dimensioner

Om du behöver en specifik bildstorlek, justera egenskaperna `ImageHeight` och `ImageWidth` innan du anropar `Save`:

```csharp
colsGenerator.Parameters.ImageHeight = 150; // pixels
colsGenerator.Parameters.ImageWidth = 300;  // pixels
colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
```

Att ändra dimensioner påverkar inte den kodade datan; det skalar bara den visuella representationen. Denna teknik är användbar när streckkoder integreras i UI‑komponenter med fasta layout‑restriktioner.

## Vanliga fallgropar och pro‑tips

* **Sökvägsseparatorer:** Använd verbatim‑strängar (`@"C:\Path\file.png"`) eller `Path.Combine` för att undvika escape‑tecken‑problem på Windows.  
* **Licens‑verkställighet:** Utan en giltig licens innehåller de genererade bilderna ett vattenmärke. Applicera din licens tidigt i applikationen:

  ```csharp
  Aspose.BarCode.License license = new Aspose.BarCode.License();
  license.SetLicense("Aspose.BarCode.lic");
  ```

* **Kodningsgränser:** DataBar Expanded Stacked stödjer upp till 74 numeriska tecken. Att överskrida denna gräns kastar ett undantag. Validera inmatningslängden innan du skapar generatorn.  
* **Prestanda:** Återanvänd en enda `BarcodeGenerator`‑instans för flera sparningar för att minska minnesallokering. Ändra endast `Rows` eller `Columns` mellan sparningar om den kodade texten förblir densamma.

## Nästa steg

Nu när du kan generera streckkodsbilder med barcode generator C#, överväg att utforska:

* **Olika symbologier** – prova `EncodeTypes.QR`, `EncodeTypes.Code128` eller `EncodeTypes.Pdf417`.  
* **Färganpassning** – sätt `Parameters.Barcode.ForeColor` och `BackColor` för att matcha varumärket.  
* **Inbäddning i PDF‑filer** – kombinera den genererade PNG‑filen med Aspose.PDF för att skapa utskrivbara dokument.  

Dessa tillägg låter dig bygga en fullständigt funktionell streckkodslösning för lager, logistik eller detaljhandelsapplikationer.

---


## Vad bör du lära dig härnäst?


Följande handledningar täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Generera streckkodsbild – GS1 Coupon UPC‑A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Skapa DotCode streckkod – rader & kolumner (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Hur man genererar DataMatrix‑streckkoder (ECC 200) med Aspose.BarCode för .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}