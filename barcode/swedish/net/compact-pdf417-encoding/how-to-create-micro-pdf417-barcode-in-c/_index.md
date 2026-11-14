---
category: general
date: 2026-11-14
description: Skapa micro PDF417‑streckkod i C# med Aspose.BarCode – steg‑för‑steg‑guide
  som täcker generatorinställning, X‑dimension, kolumner och PNG‑export.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- micro pdf417 barcode generator
- set XDimension pixels
- define barcode columns
- save barcode as PNG
- Aspose.BarCode C# example
language: sv
lastmod: 2026-11-14
og_description: Skapa mikro‑PDF417‑streckkod i C# med Aspose.BarCode. Lär dig att
  konfigurera generatorn, ställa in XDimension, välja kolumner och exportera som PNG.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Skapa mikro-PDF417-streckkod i C# – fullständig programmeringsguide
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  headline: How to create micro PDF417 barcode in C#
  type: TechArticle
- description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  name: How to create micro PDF417 barcode in C#
  steps:
  - name: Open the PNG in an image viewer.
    text: Open the PNG in an image viewer.
  - name: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
    text: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
  - name: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
    text: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
- image generation
title: Hur man skapar mikro‑PDF417‑streckkod i C#
url: /sv/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar micro PDF417 streckkod i C#  

Om du snabbt behöver **skapa micro PDF417 streckkod**, visar den här guiden en komplett, färdig‑att‑köra lösning. Du får se hur du instansierar streckkodsgeneratorn, konfigurerar X‑dimensionen, väljer antalet kolumner och slutligen sparar resultatet som en PNG‑bild — allt med Aspose.BarCode‑biblioteket för .NET.

Att generera en micro PDF417 streckkod kräver ingen komplex byggpipeline. I slutet av den här tutorialen har du en enda C#‑fil som producerar en högkvalitativ streckkodsbild som du kan bädda in i rapporter, etiketter eller mobilappar.

## Förutsättningar  

* .NET 6.0 SDK eller senare (koden fungerar också med .NET Framework 4.7+).  
* En utvecklingsmiljö såsom Visual Studio 2022, VS Code eller Rider.  
* En Aspose.BarCode för .NET‑licens (eller en gratis utvärderingsnyckel). Du kan skaffa den från [Aspose-webbplatsen](https://purchase.aspose.com/barcode/net).  

> **Proffstips:** Om du använder utvärderingsversionen kommer den genererade PNG‑filen att innehålla ett litet “Evaluation”-vattenstämpel. En licensierad version tar bort den automatiskt.

## Steg 1: Ställ in projektet  

Skapa ett nytt konsolprojekt och lägg till Aspose.BarCode‑paketet via NuGet.

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode --version 24.9.0
```

`dotnet add package`‑kommandot hämtar **Aspose.BarCode C#‑exempel**‑beroenden, så du behöver inte hantera DLL‑filer manuellt.

## Steg 2: Skriv den kompletta koden  

Ersätt den automatiskt genererade `Program.cs` med följande kod. Den demonstrerar hur du **skapar micro pdf417 streckkod** från början till slut.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text.
            // The text can contain Unicode characters; here we use a sample string.
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Åspóse.Barcóde©");

            // 2️⃣ Set the X‑dimension (module width) in pixels.
            // This determines the width of the smallest element (a bar or a space).
            generator.Parameters.Barcode.XDimension.Pixels = 2; // secondary keyword: set XDimension pixels

            // 3️⃣ Define the number of columns (allowed values: 1‑4 for MicroPDF417).
            // More columns mean a wider barcode but fewer rows, which can improve readability.
            generator.Parameters.Barcode.Pdf417.Columns = 4; // secondary keyword: define barcode columns

            // 4️⃣ Choose the output format and save the barcode as a PNG image.
            // PNG preserves the sharp edges of the barcode, which is ideal for scanning.
            string outputPath = "MicroPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png); // secondary keyword: save barcode as PNG

            Console.WriteLine($"Micro PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### Varför varje rad är viktig  

* **BarcodeGenerator constructor** – Instansierar **micro pdf417 streckkodsgeneratorn** med den text du vill koda.  
* **XDimension.Pixels** – Styr modulbredden; att sätta den till `2` pixlar ger en tät, högupplöst streckkod som passar de flesta skannrar.  
* **Pdf417.Columns** – MicroPDF417 stöder endast 1‑4 kolumner. Att välja `4` minskar streckkodens höjd, vilket är användbart när du har begränsat vertikalt utrymme.  
* **Save method** – Skriver streckkoden till en PNG‑fil. PNG är förlustfri, vilket säkerställer att skannern läser exakt det mönster du genererat.

## Steg 3: Bygg och kör  

Kompilera och kör programmet:

```bash
dotnet run
```

Du bör se konsolutdata:

```
Micro PDF417 barcode saved to MicroPdf417.png
```

En fil med namnet **MicroPdf417.png** visas i projektmappen. Öppna den med någon bildvisare; du kommer att se en skarp micro PDF417 streckkod som kodar strängen `"Åspóse.Barcóde©"`.

![Genererat micro PDF417 streckkodsexempel](MicroPdf417.png "Genererat micro PDF417 streckkodsexempel"){.center-image width=400 alt="Genererat micro PDF417 streckkodsexempel"}

*Bilden ovan är resultatet av koden som visas i Steg 2.*

## Steg 4: Vanliga variationer och kantfall  

| Situation | Hur du anpassar koden |
|-----------|-----------------------|
| **Olika datalängd** | MicroPDF417 kan koda upp till 1 200 tecken. Ändra bara det andra argumentet till `BarcodeGenerator`. |
| **Högre upplösning** | Öka `XDimension.Pixels` till `3` eller `4`. Större moduler förbättrar läsbarheten på lågupplösta skannrar men ökar bildstorleken. |
| **Anpassade färger** | Efter att ha skapat generatorn, sätt `generator.Parameters.Barcode.BarcodeColor = Color.Blue;` och `generator.Parameters.Barcode.BackgroundColor = Color.White;`. |
| **Spara i andra format** | Ersätt `BarCodeImageFormat.Png` med `Jpeg`, `Bmp` eller `Gif` beroende på dina efterföljande krav. |
| **Bädda in i en PDF** | Använd `generator.Save("barcode.pdf", BarCodeImageFormat.Pdf);` och slå sedan ihop PDF‑filen med andra dokument med Aspose.PDF. |

> **Observera:** Att sätta `XDimension.Pixels` under `1` kastar ett `ArgumentOutOfRangeException`. Håll den alltid på `1` eller högre.

## Steg 5: Verifiera streckkoden  

För att säkerställa att streckkoden skannas korrekt:

1. Öppna PNG‑filen i en bildvisare.  
2. Använd någon smartphone‑app för streckkodsskanning som stödjer PDF417 (de flesta “QR‑kod‑skannrar” innehåller den).  
3. Skanna bilden; appen bör visa den ursprungliga texten `"Åspóse.Barcóde©"`.

Om skanningen misslyckas, dubbelkolla **X‑dimensionen** och **kolumn**‑inställningarna – en för liten modulbredd eller ett kolumnantal som inte stöds kan göra mönstret oläsligt.

## Slutsats  

Du vet nu hur du **skapar micro pdf417 streckkod** i C# med Aspose.BarCode. Tutorialen täckte:

* Instansiering av en **micro pdf417 streckkodsgenerator**.  
* **Ange XDimension‑pixlar** för att styra modulbredden.  
* **Definiera streckkodskolumner** för att justera formen.  
* **Spara streckkoden som PNG** för förlustfri bildutmatning.  

Härifrån kan du utforska ytterligare funktioner såsom färganpassning, inbäddning av streckkoden i PDF‑filer eller generering av streckkoder i realtid i ASP.NET Core‑webb‑API:er. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande tutorials täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Skapa streckkod PNG i C# – fullständig guide till GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Hur man skapar macro PDF417 streckkod i C# med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Skapa PDF417 streckkod i C# med Aspose.BarCode – steg‑för‑steg guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}