---
category: general
date: 2026-10-15
description: Lär dig hur du genererar PDF417‑streckkod i C# med Macro‑PDF417‑parametrar,
  ställer in streckkodens dimensioner och sparar som PNG. Komplett kodexempel inkluderat.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417 barcode
- C# PDF417 barcode
- Macro PDF417 parameters
- set barcode dimensions
- barcode image format
- barcode checksum
language: sv
lastmod: 2026-10-15
og_description: Hur man genererar PDF417-streckkod i C# med full Macro‑PDF417-konfiguration,
  dimensionkontroll och PNG-utdata. Följ det kompletta exemplet.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Hur man genererar PDF417-streckkod i C# – steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to generate PDF417 barcode in C# using Macro‑PDF417 parameters,
    set barcode dimensions, and save as PNG. Complete code example included.
  headline: How to generate PDF417 barcode in C# with Macro‑PDF417 settings
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- Aspose.Barcode
title: Hur man genererar PDF417-streckkod i C# med Macro‑PDF417-inställningar
url: /sv/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-macro-pdf417-settin/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar PDF417-streckkod i C# med Macro‑PDF417-inställningar

Om du behöver **hur man genererar PDF417-streckkod** för ett dokumentflöde, visar den här guiden de exakta stegen. Du kommer att se hur du konfigurerar Macro‑PDF417-parametrar, ställer in streckkodens dimensioner och exporterar resultatet som en PNG-bild – allt i ett enda körbart C#-program.

Att generera en PDF417-streckkod kräver inte flera bibliotek eller komplex efterbehandling. Genom att använda Aspose.Barcode för .NET kan du kontrollera varje aspekt av streckkoden, från modulbredd till kontrollsumma, och producera en högkvalitativ bild klar för utskrift eller skanning.

## Förutsättningar

* .NET 6.0 (eller senare) SDK installerad  
* Visual Studio 2022 eller någon C#-IDE du föredrar  
* Aspose.Barcode för .NET NuGet‑paket (`Install-Package Aspose.Barcode`)  

Dessa förutsättningar säkerställer att koden kompileras utan ytterligare konfiguration.

## Steg 1: Skapa en streckkodsgenerator för en Macro‑PDF417-streckkod

Den första operationen skapar en `BarcodeGenerator`‑instans som riktar sig mot formatet `EncodeTypes.MacroPdf417`. Konstruktorn tar emot den data du vill koda – i detta fall strängen `"Sample text"`.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

// Step 1: Initialize the generator with Macro‑PDF417 and data to encode
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps configure the barcode
```

Att skapa generatorn initierar det interna `Parameters`‑objektet, som du kommer att använda för att justera **C# PDF417-streckkod**‑egenskaper.

## Steg 2: Ställ in grundläggande streckkodens utseende – ange streckkodens dimensioner

Att kontrollera den visuella storleken på en streckkod förbättrar skanningspålitligheten. `XDimension.Pixels`‑egenskapen definierar modulens (prickens) bredd, medan `Pdf417.Columns` bestämmer hur många kolumner streckkoden ska innehålla.

```csharp
    // Step 2: Define module width and column count
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

Att ställa in dessa dimensioner säkerställer att streckkoden passar inom vanliga etikettstorlekar och uppfyller scannerspecifikationer.

## Steg 3: Tillhandahåll Macro‑PDF417 filidentifiering

Macro‑PDF417 utökar den standard PDF417-streckkoden med metadata på filnivå. Du måste tilldela ett unikt fil‑ID, segment‑ID, totalt antal segment och ett människoläsbart filnamn.

```csharp
    // Step 3: Assign macro file identification
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";
```

Dessa **Macro PDF417‑parametrar** möjliggör för nedströmsystem att återskapa den ursprungliga filen från flera streckkodsegment.

## Steg 4: Lägg till ytterligare macro‑metadata – inkludera streckkodens kontrollsumma

Utöver identifiering kan Macro‑PDF417 lagra kontrollsumma, filstorlek, tidsstämpel, mottagare, avsändare och en terminatorflagga. Att tillhandahålla en kontrollsumma förbättrar dataintegritetskontroller under avkodning.

```csharp
    // Step 4: Populate extra macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // UTC timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

Att inkludera en **streckkodskontrollsumma** och annan metadata gör streckkoden självbeskrivande, vilket är värdefullt för automatiserade dokumentbehandlingspipelines.

## Steg 5: Spara den genererade streckkoden som en PNG-bild – välj streckkodens bildformat

Det sista steget skriver streckkoden till en fil. `Save`‑metoden accepterar en filsökväg och en `BarCodeImageFormat`‑enum. PNG ger förlustfri komprimering, vilket bevarar skarpa kanter för pålitlig skanning.

```csharp
    // Step 5: Export the barcode to PNG
    generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

Efter körning innehåller filen `MacroPdf417.png` en skarp PDF417-streckkod klar för inbäddning i PDF‑filer, utskrift på etiketter eller visning på skärmar.

## Förväntat resultat

När du öppnar `C:/Barcodes/MacroPdf417.png` visas en rektangulär streckkod med den kodade texten “Sample text”. Streckkoden innehåller den macro‑metadata du angav, vilket du kan verifiera med vilken PDF417‑scanner som helst som stöder Macro‑PDF417. Bildens dimensioner speglar modulbredden (2 px) och antalet kolumner (5), vilket resulterar i en kompakt men läsbar streckkod.

## Vanliga variationer och kantfall

| Situation | Anpassning |
|-----------|------------|
| **Olika datalängd** | Byt ut `"Sample text"` mot någon UTF‑8‑sträng; generatorn justerar automatiskt streckkodens storlek. |
| **Högre upplösning** | Öka `XDimension.Pixels` till 3 eller 4 för större moduler, användbart för lågupplösta skrivare. |
| **Fler segment** | Ändra `MacroPdf417SegmentsCount` så att den matchar det totala antalet streckkodsdeler du planerar att generera. |
| **Alternativt bildformat** | Använd `BarCodeImageFormat.Jpeg` eller `BarCodeImageFormat.Bmp` om ditt nedströmsystem föredrar dessa format. |
| **Anpassad felkorrigering** | Modifiera `generator.Parameters.Barcode.Pdf417.ErrorLevel` (intervall 0‑8) för att balansera datatäthet mot fel tolerans. |

**Proffstips:** Validera alltid den genererade streckkoden med en fysisk scanner innan du distribuerar den i produktion. Scannrar kan ha firmware‑specifika begränsningar för modulbredd eller kolumnantal.

## Fullständig källkod

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace Pdf417MacroDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator for Macro‑PDF417 with sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Set visual dimensions
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // column count

                // Provide macro file identification
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";

                // Add macro metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // timestamp
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export as PNG
                generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("PDF417 barcode generated successfully.");
        }
    }
}
```

När du kör detta program skapas `MacroPdf417.png` i mappen `C:/Barcodes`. Konsolen bekräftar att genereringen lyckades.

## Slutsats

Du vet nu **hur man genererar PDF417-streckkod** i C# med full Macro‑PDF417‑kontroll, hur man **ställer in streckkodens dimensioner**, hur man bäddar in **streckkodens kontrollsumma** och annan macro‑metadata, samt hur man exporterar resultatet med ett valt **streckkodens bildformat**. Det kompletta exemplet kan kopieras in i vilket .NET‑projekt som helst, modifieras för olika datapayloads och integreras i större dokument‑automatiseringspipelines.

### Nästa steg

* Utforska **C# PDF417-streckkod** felkorrigeringsnivåer för att förbättra skanningspålitligheten.  
* Kombinera flera Macro‑PDF417‑segment för att koda stora filer såsom PDF‑filer eller bilder.  
* Byt **streckkodens bildformat** till SVG för skalbar vektorgrafik i webbapplikationer.  

Känn dig fri att experimentera med parametrarna och dela dina resultat i kommentarerna eller på community‑forum. Lycka till med kodandet!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Generera streckkod C# med Macro PDF417 – fullständigt exempel](/barcode/english/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/)
- [Hur man genererar PDF417-streckkod – komplett programmeringsguide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)
- [Hur man genererar PDF417-streckkod i C# med anpassade dimensioner](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}