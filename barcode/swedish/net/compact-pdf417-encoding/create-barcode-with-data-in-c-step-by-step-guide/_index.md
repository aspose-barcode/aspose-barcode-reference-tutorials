---
category: general
date: 2026-07-27
description: Skapa streckkod med data i C# snabbt. Lär dig hur du skapar PDF417‑streckkod
  i C# med Aspose.BarCode, ställer in dimensioner och sparar som PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode with data
- create pdf417 barcode c#
language: sv
lastmod: 2026-07-27
og_description: Skapa streckkod med data i C# med Aspose.BarCode. Denna guide visar
  hur du skapar en PDF417‑streckkod i C# med anpassade inställningar och sparar som
  PNG.
og_image_alt: Screenshot of a barcode created with data in a C# application
og_title: Skapa streckkod med data i C# – Komplett programmeringsgenomgång
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create barcode with data in C# quickly. Learn how to create PDF417
    barcode c# using Aspose.BarCode, set dimensions, and save as PNG.
  headline: Create barcode with data in C# – Step‑by‑Step Guide
  type: TechArticle
- description: Create barcode with data in C# quickly. Learn how to create PDF417
    barcode c# using Aspose.BarCode, set dimensions, and save as PNG.
  name: Create barcode with data in C# – Step‑by‑Step Guide
  steps:
  - name: Initialising `BarcodeGenerator` with MicroPdf417 and a Unicode string.
    text: Initialising `BarcodeGenerator` with MicroPdf417 and a Unicode string.
  - name: Tweaking the X‑dimension for finer resolution.
    text: Tweaking the X‑dimension for finer resolution.
  - name: Limiting columns to keep the barcode compact.
    text: Limiting columns to keep the barcode compact.
  - name: Saving the result as a PNG file.
    text: Saving the result as a PNG file.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Skapa streckkod med data i C# – Steg‑för‑steg‑guide
url: /sv/net/compact-pdf417-encoding/create-barcode-with-data-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa streckkod med data i C# – Komplett programmeringsgenomgång

Har du någonsin behövt **skapa streckkod med data** i en .NET‑app men varit osäker på vilka API‑anrop du ska använda? Du är inte ensam. Oavsett om du märker lager, skriver ut biljetter eller bäddar in information i en mobilskanning, är det en användbar färdighet för varje C#‑utvecklare att behärska streckkodsskapande.

I den här handledningen går vi igenom ett praktiskt exempel som visar hur du **skapar PDF417‑streckkod c#** med Aspose.BarCode‑biblioteket, justerar modulbredden, begränsar antalet kolumner och slutligen sparar resultatet som en PNG‑fil. När du är klar har du ett fullt fungerande, färdigt att köra konsolprogram som du kan lägga in i vilket projekt som helst.

## Förutsättningar — Vad du behöver

- **.NET 6.0** eller senare (koden fungerar även med .NET Framework 4.7+)  
- **Aspose.BarCode for .NET** NuGet‑paket (`Install-Package Aspose.BarCode`)  
- En kodredigerare eller IDE (Visual Studio, VS Code, Rider – välj din favorit)  
- Skrivrättighet till en mapp där PNG‑filen ska sparas  

Inga extra konfigurationsfiler krävs; biblioteket är självständigt.

## Steg 1: Ställ in projektet och importera namnrymder

Först, skapa ett nytt konsolprojekt (eller öppna ett befintligt) och lägg till Aspose.BarCode‑referensen.

```csharp
// Program.cs – entry point
using System;
using Aspose.BarCode.Generation;   // Core generator classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll place the barcode generation logic here.
        }
    }
}
```

> **Varför detta är viktigt:** Att importera rätt namnrymder ger dig åtkomst till `BarcodeGenerator` och relaterade inställningar utan att behöva kvalificera varje typ. Det gör också koden renare för framtida underhåll.

## Steg 2: Initiera Barcode‑generatorn med dina data

Nu **skapar vi faktiskt streckkod med data**. `BarcodeGenerator`‑konstruktorn tar två argument: symbologin (`EncodeTypes.MicroPdf417`) och strängen du vill koda.

```csharp
// Inside Main()
string dataToEncode = "Åspóse.Barcóde©";   // Example containing Unicode characters
var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, dataToEncode);
```

> **Tips:** MicroPdf417‑symbologin är en kompakt version av PDF417, perfekt när du behöver en mindre bild men ändå vill ha hög datakapacitet. Biblioteket hanterar Unicode direkt, så tecken som “Å” och “©” fungerar bra.

## Steg 3: Finjustera X‑dimensionen (modulbredd)

Om du behöver en skarpare, högupplöst bild kan du minska modulbredden. Att sätta den till **2 pixlar** ger ett finare rutnät utan att filstorleken ökar kraftigt.

```csharp
// Adjust the module (X‑dimension) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Varför justera X‑dimensionen?** En mindre X‑dimension gör varje stapel smalare, vilket förbättrar läsbarheten på högupplösta skannrar samtidigt som den totala streckkodsstorleken förblir rimlig.

## Steg 4: Begränsa PDF417‑kolumner (valfritt men vanligt)

PDF417 låter dig ange antalet kolumner. För MicroPdf417 är maxgränsen **4**, vilket håller streckkoden kort och bred.

```csharp
// Set the column count to the maximum allowed (4)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

> **Edge case:** Om du anger ett kolumnantal som är högre än det tillåtna maximumet, kommer Aspose automatiskt att begränsa det, men det är god praxis att hålla sig inom det dokumenterade intervallet för att undvika oväntad skalning.

## Steg 5: Spara streckkoden som en PNG‑bild

Till sist, skriv den genererade bilden till disk. `Save`‑metoden tar den fullständiga sökvägen och det önskade bildformatet.

```csharp
// Define output path – adjust as needed
string outputPath = @"C:\Temp\MicroPdf417.png";

// Save as PNG (lossless, widely supported)
generator.Save(outputPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode saved to {outputPath}");
```

> **Pro‑tips:** PNG bevarar exakt pixeldata, vilket är avgörande för streckkoder. Om du behöver ett vektorformat för skalning kan du byta `BarCodeImageFormat.Png` mot `BarCodeImageFormat.Svg`.

### Fullt fungerande exempel

När allt sätts ihop, här är det kompletta, kopiera‑och‑klistra‑klara programmet:

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
            // 1️⃣ Data we want to encode – includes special characters
            string dataToEncode = "Åspóse.Barcóde©";

            // 2️⃣ Initialise generator with MicroPdf417 symbology
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, dataToEncode);

            // 3️⃣ Fine‑tune resolution – 2‑pixel modules
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Use the maximum of 4 columns for a compact barcode
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // 5️⃣ Save the image
            string outputPath = @"C:\Temp\MicroPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode created successfully! Saved at: {outputPath}");
        }
    }
}
```

Att köra detta program skapar en PNG‑fil som ser ungefär ut så här:

![Streckkod skapad med data i C#](barcode-sample.png "Skärmdump av en streckkod skapad med data i en C#‑applikation")

*Bilden ovan är en platshållare—din faktiska streckkod kommer att innehålla den exakta strängen “Åspóse.Barcóde©”.*

## Vanliga frågor & edge‑cases

| Fråga | Svar |
|----------|--------|
| *Vad händer om mina data överskrider MicroPdf417‑kapaciteten?* | Byt till `EncodeTypes.Pdf417` (vanlig PDF417) som stödjer upp till 1 800 tecken. |
| *Kan jag ändra bildformatet till JPEG?* | Ja—byt `BarCodeImageFormat.Png` mot `BarCodeImageFormat.Jpeg`. Kom ihåg att JPEG är förlustkomprimerat; det kan påverka skannerns pålitlighet. |
| *Behöver jag hantera Unicode manuellt?* | Nej. Aspose.BarCode kodar automatiskt Unicode‑tecken, men se till att din källfil sparas med UTF‑8‑kodning. |
| *Vad händer om jag behöver en transparent bakgrund?* | Sätt `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent;` innan du sparar. |
| *Finns det ett sätt att generera streckkoden i minnet?* | Anropa `generator.GenerateBarCodeImage()` för att få ett `System.Drawing.Image`‑objekt som du kan strömma direkt. |

## Sammanfattning – Vad vi har lärt oss

Vi har demonstrerat hur man **skapar streckkod med data** i C# genom att:

1. Initiera `BarcodeGenerator` med MicroPdf417 och en Unicode‑sträng.  
2. Justera X‑dimensionen för finare upplösning.  
3. Begränsa kolumner för att hålla streckkoden kompakt.  
4. Spara resultatet som en PNG‑fil.

Alla dessa steg tillsammans svarar på huvudfrågan “hur man **skapar PDF417‑streckkod c#**” samtidigt som de visar hur du anpassar vanliga parametrar.

## Nästa steg & relaterade ämnen

- **Lägg till mänskligt läsbar text** under streckkoden med `generator.Parameters.Barcode.CodeTextParameters`.  
- **Bädda in PNG‑filen i en PDF** med `Aspose.Pdf` för utskrivbara rapporter.  
- **Generera andra symbologier** (QR, Code128, DataMatrix) genom att byta `EncodeTypes`.  
- **Batch‑behandling** – loopa över en CSV‑fil med produkt‑ID:n och skapa en mapp med streckkoder.

Känn dig fri att experimentera med kolumnantalet, felkorrigeringsnivån och färgscheman. När du väl är bekväm kan du bygga fullständiga märkningslösningar som integreras sömlöst med lager‑ eller biljettsystem.

Lycka till med kodningen, och må dina skanningar alltid vara felfria!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar streckkod – kompakt PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Skapa DotCode‑streckkod bild – rader & kolumner (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Skapa streckkod PNG – DataMatrix‑bildförhållande – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}