---
category: general
date: 2026-09-07
description: Lär dig hur du genererar micro‑pdf417‑streckkod i C# med ett komplett
  kodexempel, justering av X‑dimension, kolumnkonfiguration och PNG‑export.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate micro pdf417 barcode
- C# barcode generator
- MicroPdf417 encode type
- barcode X-dimension
- barcode column configuration
- save barcode as PNG
language: sv
lastmod: 2026-09-07
og_description: Skapa micro‑pdf417‑streckkod i C# med den här kortfattade handledningen.
  Inkluderar X‑dimensionsinställningar, kolumnval och PNG‑export för omedelbar användning.
og_image_alt: Screenshot showing a generated micro pdf417 barcode saved as a PNG file
og_title: Generera micro‑pdf417‑streckkod i C# – komplett programmeringsguide
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to generate micro pdf417 barcode in C# with a complete code
    example, X‑dimension tuning, column configuration, and PNG export.
  headline: How to generate micro pdf417 barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- MicroPdf417
- image export
title: Hur man genererar micro‑pdf417‑streckkod i C# – steg‑för‑steg‑guide
url: /sv/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar micro pdf417 streckkod i C# – steg‑för‑steg guide

Om du behöver **generera micro pdf417 streckkod** i en .NET‑applikation visar den här handledningen en färdig‑att‑köra‑lösning. Du kommer att se hur du konfigurerar streckkodens X‑dimension, väljer kolumnantalet och exporterar resultatet som en PNG‑bild—allt med Aspose.BarCode C#‑biblioteket.

Att generera en micro pdf417 streckkod är vanligt när du måste koda kompakt data för mobila biljetter, inventarie‑taggar eller säkra dokument. I slutet av den här guiden har du ett återanvändbart kodexempel som du kan klistra in i vilket C#‑projekt som helst.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 eller senare (koden fungerar även med .NET Framework 4.7+)
* Visual Studio 2022 (eller någon IDE som stödjer C#)
* **Aspose.BarCode for .NET** NuGet‑paketet (version 23.9 eller nyare)

Du kan installera paketet från kommandoraden:

```bash
dotnet add package Aspose.BarCode
```

Inga ytterligare beroenden krävs.

## Steg 1: Skapa en streckkodsgenerator för MicroPdf417

Den första uppgiften är att instansiera en `BarcodeGenerator` med enum‑värdet `EncodeTypes.MicroPdf417` och den text du vill koda. Texten kan innehålla Unicode‑tecken, vilket biblioteket hanterar automatiskt.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for MicroPdf417 with the desired text
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,
    "Åspóse.Barcóde©"
);
```

**Varför detta är viktigt:**  
`EncodeTypes.MicroPdf417` talar om för biblioteket att använda den kompakta MicroPdf417‑symbologin, som lagrar mer data i ett mindre utrymme än den fullständiga PDF417. Genom att ange texten vid konstruktionen säkerställer du att generatorn vet exakt vad som ska kodas.

## Steg 2: Justera X‑dimensionen för finare upplösning

X‑dimensionen (modulbredd) styr hur många pixlar varje streckkodskolumn upptar. Ett värde på **2 pixlar** ger en högupplöst streckkod som förblir läsbar på de flesta skannrar.

```csharp
// Step 2: Set the X‑dimension (module width) to 2 pixels for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Proffstips:**  
Om du riktar dig mot lågupplösta skärmar eller skrivare, öka värdet till 3‑4 pixlar för att undvika suddiga kanter. Omvänt, för högdensitetsetiketter kan du sänka det till 1 pixel, men testa resultatet med din skanner.

## Steg 3: Välj antal kolumner

MicroPdf417 tillåter **1 till 4 kolumner**. Fler kolumner ger en kortare streckkod men minskar felkorrigeringskapaciteten. För de flesta biljettscenarier ger **4 kolumner** en kompakt form samtidigt som robustheten bevaras.

```csharp
// Step 3: Choose the number of columns (1‑4 are allowed) to control barcode size
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Varför du kanske vill ändra detta:**  
Om den kodade texten är längre än standardkapaciteten, öka kolumnantalet för att undvika overflow‑fel. Minska det när du behöver en smal streckkod för begränsat utrymme.

## Steg 4: Definiera output‑mapp och filnamn

Välj en mapp där den genererade bilden ska sparas. Genom att använda `Path.Combine` garanteras korrekta sökvägsseparatorer på Windows, Linux och macOS.

```csharp
using System.IO;

// Step 4: Define the output folder and file name
string outputFolder = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "Barcodes"
);
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
string outputPath = Path.Combine(outputFolder, "MicroPdf417.png");
```

**Hantera kantfall:**  
Om mappens sökväg är ogiltig eller programmet saknar skrivbehörighet, kastar `Directory.CreateDirectory` ett undantag. Omslut sparlogiken med ett `try/catch`‑block i produktionskod.

## Steg 5: Spara streckkoden som en PNG‑bild

Slutligen exporterar du streckkoden till en PNG‑fil. PNG bevarar skarpa kanter och stödjer transparens, vilket gör den idealisk för UI‑rendering eller utskrift.

```csharp
using Aspose.BarCode;

// Step 5: Save the generated barcode as a PNG image
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Efter körning hittar du **MicroPdf417.png** i `Barcodes`‑mappen på ditt skrivbord. När du öppnar filen ser du en klar, högupplöst micro pdf417 streckkod redo för skanning.

### Förväntat resultat

Den sparade bilden ser liknande ut som illustrationen nedan (det faktiska mönstret beror på den kodade texten).

![Generated micro pdf417 barcode saved as PNG](https://example.com/placeholder-micro-pdf417.png "Screenshot of a generated micro pdf417 barcode saved as a PNG file")

*Alt text:* generera micro pdf417 streckkod sparad som PNG‑bild

## Fullt, körbart exempel

Genom att samla alla steg får du ett enda, självständigt program:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Create generator with MicroPdf417 and Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©"
        );

        // 2️⃣ Set X‑dimension for high‑resolution output
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Choose 4 columns to keep the barcode compact
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // 4️⃣ Prepare output folder on the desktop
        string outputFolder = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "Barcodes"
        );
        Directory.CreateDirectory(outputFolder);
        string outputPath = Path.Combine(outputFolder, "MicroPdf417.png");

        // 5️⃣ Save as PNG
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

Kör programmet (`dotnet run` från projektmappen) och verifiera att PNG‑filen visas som förväntat.

## Vanliga frågor och felsökning

| Fråga | Svar |
|----------|--------|
| **Kan jag generera streckkoden som JPEG istället för PNG?** | Ja. Byt ut `BarCodeImageFormat.Png` mot `BarCodeImageFormat.Jpeg`. JPEG komprimerar bilden men kan introducera artefakter som påverkar skannerns läsbarhet. |
| **Vad händer om texten innehåller tecken som inte stöds av MicroPdf417?** | MicroPdf417 stödjer hela Unicode‑intervallet. Om du får ett `ArgumentException`, kontrollera att strängen är korrekt kodad (t.ex. undvik surrogatpar som överskrider symbolkapaciteten). |
| **Hur ändrar jag förgrundsfärgen?** | Använd `generator.Parameters.Barcode.BarColor = Color.Blue;` innan du anropar `Save`. |
| **Finns det ett sätt att bädda in streckkoden direkt i en PDF?** | Ja. Använd `generator.Save(stream, BarCodeImageFormat.Pdf);` eller lägg till bilden i ett PDF‑dokument med ett PDF‑bibliotek som Aspose.PDF. |
| **Min skanner kan inte läsa streckkoden—vad bör jag kontrollera?** | Säkerställ att X‑dimensionen är minst 2 pixlar för de flesta skannrar, verifiera att kolumnantalet matchar skannarens stödda intervall, och bekräfta att den tryckta storleken uppfyller skannarens minsta modulstorlek (vanligtvis 0.5 mm). |

## Slutsats

Du vet nu hur du **genererar micro pdf417 streckkod** i C# från början till slut. Guiden täckte hur du skapar `BarcodeGenerator`, konfigurerar X‑dimension och kolumnantal, förbereder en output‑sökväg och sparar resultatet som PNG. Genom att justera sekundära inställningar—såsom streckfärg, bildformat eller felkorrigeringsnivå—kan du anpassa streckkoden till vilken applikation som helst, från mobila biljetter till inventarie‑taggar.

### Nästa steg

* Experimentera med **barcode X-dimension**‑värden för att balansera storlek och läsbarhet.  
* Utforska andra symbologier (t.ex. `EncodeTypes.Pdf417`, `EncodeTypes.QR`) med samma generator‑mönster.  
* Integrera den genererade PNG‑filen i en PDF‑rapport med **Aspose.PDF** eller bädda in den direkt i ett WinForms/WPF‑gränssnitt.  

Lycka till med kodningen, och njut av den flexibilitet som Aspose.BarCode‑biblioteket ger för streckkodsgenerering i C#!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Barcode Generator Tutorial: How to Generate PDF417 Barcode in C#](/barcode/english/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}