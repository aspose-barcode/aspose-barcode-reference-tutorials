---
category: general
date: 2026-08-03
description: Generera PDF417‑streckkod i C# med Aspose.BarCode. Lär dig steg för steg
  hur du lägger till Macro PDF417‑metadata och sparar som PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode C#
- Macro PDF417 barcode
- Aspose.BarCode
- C# barcode generation
- PDF417 metadata
- barcode image PNG
language: sv
lastmod: 2026-08-03
og_description: Generera PDF417-streckkod i C# med Aspose.BarCode. Denna handledning
  visar hur du bäddar in Macro PDF417-metadata och exporterar resultatet som en PNG-bild.
og_image_alt: Screenshot of a generated PDF417 barcode created with C#
og_title: Generera PDF417‑streckkod C# – steg‑för‑steg Aspose.BarCode‑handledning
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Generate PDF417 barcode C# using Aspose.BarCode. Learn step‑by‑step
    how to add Macro PDF417 metadata and save as PNG.
  headline: Generate PDF417 barcode C# – complete guide with Aspose.BarCode
  type: TechArticle
- description: Generate PDF417 barcode C# using Aspose.BarCode. Learn step‑by‑step
    how to add Macro PDF417 metadata and save as PNG.
  name: Generate PDF417 barcode C# – complete guide with Aspose.BarCode
  steps:
  - name: Create a Macro PDF417 barcode generator
    text: First, instantiate `BarcodeGenerator` with the `EncodeTypes.MacroPdf417`
      enum. The constructor also accepts the text you want to encode – in this example
      we use a string that contains Unicode characters to demonstrate full‑width support.
  - name: Adjust basic barcode appearance
    text: Next, define the visual size of the barcode. `XDimension.Pixels` controls
      the width of a single module (the smallest black/white square), while `Pdf417.Columns`
      influences the overall shape by setting the number of columns.
  - name: Populate Macro PDF417 metadata
    text: Macro PDF417 allows you to embed file‑level information that many back‑office
      systems rely on (e.g., file ID, segment ID, timestamp). The following properties
      illustrate the most common fields.
  - name: Save the barcode image as PNG
    text: Finally, call `Save` to write the barcode to disk. PNG is lossless, making
      it ideal for high‑quality scanning.
  - name: How to verify the result
    text: 1. Open `ExtPDF417Meta.png` in any image viewer. 2. Use a PDF417 scanner
      app (e.g., *Zebra Scanner* or *BarCode Reader* on Android/iOS). 3. Confirm that
      the decoded payload includes the original text and a JSON‑like block with the
      macro fields you set.
  - name: Next steps
    text: '- Experiment with other barcode formats (e.g., QR, Code128) by changing
      `EncodeTypes`. - Explore `Pdf417.ErrorCorrectionLevel` to improve scan reliability
      under poor lighting. - Integrate the generated image into a PDF report using
      Aspose.PDF for end‑to‑end document automation.'
  type: HowTo
tags:
- PDF417
- C#
- Barcode
title: Generera PDF417‑streckkod C# – komplett guide med Aspose.BarCode
url: /sv/net/compact-pdf417-encoding/generate-pdf417-barcode-c-complete-guide-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera PDF417-streckkod C# – komplett guide

Om du behöver **generera PDF417-streckkod C#** för ett logistik- eller dokumenthanteringssystem, visar den här handledningen exakt hur du gör det med Aspose.BarCode. Du kommer att se hur du konfigurerar streckkoden, bäddar in Macro PDF417-metadata och sparar resultatet som en PNG‑bild på bara några kodrader.

Att generera en PDF417-streckkod i C# innebär ofta att hantera extra information såsom filidentifierare, segmentnummer eller tidsstämplar. Denna guide täcker dessa detaljer, så att du slipper leta igenom spridd dokumentation. I slutet av artikeln har du ett färdigt program som producerar en kompatibel Macro PDF417‑streckkodsbild.

## Vad du behöver

- .NET 6.0 eller senare (koden fungerar också med .NET Framework 4.7+)
- Aspose.BarCode för .NET (v23.9 eller nyare) – installera via NuGet `Install-Package Aspose.BarCode`
- En utvecklingsmiljö som Visual Studio 2022 eller Visual Studio Code
- Grundläggande kunskap om C#‑syntax

> **Proffstips:** Använd den senaste versionen av Aspose.BarCode för att dra nytta av buggfixar och stöd för de senaste PDF417-specifikationerna.

## Hur man genererar PDF417-streckkod C# med Aspose.BarCode

Processen består av fyra logiska steg. Varje steg är omslutet av ett tydligt kodblock så att du kan kopiera, klistra in och köra det omedelbart.

### Steg 1: Skapa en Macro PDF417‑streckkodsgenerator

Först instansierar du `BarcodeGenerator` med enum‑värdet `EncodeTypes.MacroPdf417`. Konstruktorn accepterar också den text du vill koda – i detta exempel använder vi en sträng som innehåller Unicode‑tecken för att demonstrera stöd för full bredd.

```csharp
using System;
using Aspose.BarCode.Generation;

// Create a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417,
           "Åspóse.Barcóde©"))
{
    // Subsequent steps go inside this using block
```

*Varför detta är viktigt*: `MacroPdf417`‑typen talar om för Aspose.BarCode att behandla symbolen som en macro‑streckkod, som kan bära extra metadata på filnivå. Utan denna flagga skulle de extra fälten du anger senare ignoreras.

### Steg 2: Justera grundläggande streckkodens utseende

Nästa steg är att definiera den visuella storleken på streckkoden. `XDimension.Pixels` styr bredden på en enskild modul (den minsta svarta/vita fyrkanten), medan `Pdf417.Columns` påverkar den övergripande formen genom att ange antalet kolumner.

```csharp
    // Adjust basic barcode appearance
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // size of a single module
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol
```

*Varför detta är viktigt*: En mindre `XDimension` ger en högre upplösning, vilket är användbart när streckkoden måste skannas från en skärm. Att ändra kolumnantalet kan hjälpa till att få streckkoden att passa i begränsat utrymme utan att offra datakapacitet.

### Steg 3: Fyll i Macro PDF417‑metadata

Macro PDF417 låter dig bädda in filnivåinformation som många back‑office‑system förlitar sig på (t.ex. fil‑ID, segment‑ID, tidsstämpel). Följande egenskaper illustrerar de vanligaste fälten.

```csharp
    // Populate Macro PDF417 metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;          // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Varför detta är viktigt*: Varje fält mappar direkt till ett segment av macro‑streckkodsspecifikationen. Till exempel identifierar `MacroPdf417FileID` unikt den logiska filen, medan `MacroPdf417SegmentsCount` talar om för skannern hur många delar som förväntas. Att ange korrekt metadata säkerställer att efterföljande system kan rekonstruera originaldokumentet utan fel.

### Steg 4: Spara streckkodsbilden som PNG

Till sist anropar du `Save` för att skriva streckkoden till disk. PNG är förlustfri, vilket gör den idealisk för högkvalitativ skanning.

```csharp
    // Save the barcode image as PNG
    barcodeGenerator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Varför detta är viktigt*: `BarCodeImageFormat.Png`‑enum garanterar att utdatafilen innehåller exakt de pixeldata du konfigurerat. Om du behöver ett vektorformat för skalning, ersätt `Png` med `Svg` – Aspose.BarCode stödjer det direkt.

#### Förväntat resultat

När du kör hela programmet skapas en fil med namnet **ExtPDF417Meta.png**. Bilden visar en tät, flerradig PDF417‑symbol som innehåller texten “Åspóse.Barcóde©” samt den macro‑metadata du angav. Skannar du streckkoden med en PDF417‑kompatibel läsare får du tillbaka originaltexten plus ett strukturerat datablok som innehåller fil‑ID, segment‑ID, tidsstämpel och andra fält.

![Skärmbild av genererad PDF417-streckkod](/images/pdf417-example.png){: .center-image alt="exempel på genererad PDF417-streckkod C# output"}

## Fullständig källkod (klar för kopiera‑klistra)

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417MacroDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a Macro PDF417 barcode generator with the desired text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417,
                       "Åspóse.Barcóde©"))
            {
                // Step 2: Adjust basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // size of a single module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol

                // Step 3: Populate Macro PDF417 metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;          // CCITT‑16 example
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the barcode image as PNG
                barcodeGenerator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

### Så verifierar du resultatet

1. Öppna `ExtPDF417Meta.png` i någon bildvisare.  
2. Använd en PDF417‑skannerapp (t.ex. *Zebra Scanner* eller *BarCode Reader* på Android/iOS).  
3. Bekräfta att den avkodade nyttolasten innehåller originaltexten och ett JSON‑liknande block med de macro‑fält du angav.

## Vanliga frågor och hantering av kantfall

| Fråga | Svar |
|----------|--------|
| **Kan jag generera en vektorbild istället för PNG?** | Ja. Byt ut `BarCodeImageFormat.Png` mot `BarCodeImageFormat.Svg`. Resten av koden förblir oförändrad. |
| **Vad händer om mina data överskrider standardkapaciteten?** | Öka `Pdf417.Columns` eller sätt `Pdf417.Rows` manuellt. Större värden tillåter fler kodord per segment. |
| **Stöds Unicode i den kodade texten?** | Absolut. Exemplet använder “Åspóse.Barcóde©”. Aspose.BarCode byter automatiskt till UTF‑8‑kodning när det behövs. |
| **Behöver jag signera en licens för Aspose.BarCode?** | För produktion bör du tillämpa en licens för att undvika utvärderingsvattenstämpeln. Anropa `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` innan du skapar generatorn. |
| **Hur hanterar jag fel när filen sparas?** | Omge `Save`‑anropet med ett try/catch‑block och logga `IOException` eller `BarCodeException` för felsökning. |

## Slutsats

Du vet nu hur du **genererar PDF417-streckkod C#** med Aspose.BarCode, bäddar in fullständig Macro PDF417‑metadata och exporterar resultatet som en högkvalitativ PNG‑bild. Stegen – att skapa generatorn, justera utseendet, fylla i metadata och spara bilden – bildar ett återanvändbart mönster som du kan anpassa för fakturor, fraktsedlar eller alla scenarier som kräver rik streckkodsdata.

### Nästa steg

- Experimentera med andra streckkodformat (t.ex. QR, Code128) genom att ändra `EncodeTypes`.  
- Utforska `Pdf417.ErrorCorrectionLevel` för att förbättra skanningspålitlighet under dålig belysning.  
- Integrera den genererade bilden i en PDF‑rapport med Aspose.PDF för helautomatiserad dokumenthantering.  

Känn dig fri att modifiera metadata‑fälten så att de matchar dina affärsregler, och låt streckkodsgenereringen bli en sömlös del av dina C#‑applikationer. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar streckkod – Kompakt PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Så skapar du en streckkod – Kompakt PDF417 med Aspose.BarCode](/barcode/german/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [java streckkodsbibliotek – Lägg till streckkod i PDF med Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}