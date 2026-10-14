---
category: general
date: 2026-10-14
description: Lär dig hur du genererar pdf417 med Aspose.BarCode, lägger till anpassad
  text, makrometadata och exporterar resultatet som en PNG i en steg‑för‑steg C#‑handledning.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- generate barcode aspose
- pdf417 macro metadata
- custom text barcode
- Aspose.BarCode C#
lastmod: 2026-10-14
og_description: Lär dig hur du genererar pdf417 med Aspose.BarCode. Denna guide visar
  steg‑för‑steg hur du lägger till anpassad text, makrometadata och sparar streckkoden
  som en PNG‑bild.
og_image_alt: Screenshot of a MacroPdf417 barcode generated with Aspose.BarCode in
  C#
og_title: Hur man genererar pdf417 – komplett C#-guide
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Learn how to generate pdf417 with Aspose.BarCode, add custom text,
    macro metadata, and export the result as a PNG.
  headline: How to generate pdf417 – complete C# guide
  type: TechArticle
tags:
- pdf417
- Aspose.BarCode
- C# barcode generation
- macro barcode
title: Hur man genererar pdf417 – komplett C#-guide
url: /sv/net/compact-pdf417-encoding/generate-barcode-aspose-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar pdf417 – komplett C#-guide

Om du behöver **generera pdf417** för en MacroPdf417-symbol, guidar den här handledningen dig genom hela processen. Du får se hur du konfigurerar makro‑specifika alternativ, bäddar in anpassad Unicode‑text och sparar streckkoden som en PNG‑bild. I slutet av guiden har du ett färdigt C#‑snutt som kan placeras i vilket .NET‑projekt som helst, oavsett om det är en konsolapp, en Windows‑tjänst eller en molnbaserad mikrotjänst.

## Snabba svar
- **Vilket bibliotek behöver jag?** Aspose.BarCode för .NET (stödjer över 70 symbologier).  
- **Kan jag lägga till Unicode‑tecken?** Ja – API:et stöder fullt ut UTF‑8‑strängar som `"Åspóse.Barcóde©"`.  
- **Behöver jag en licens för produktion?** En giltig Aspose.BarCode‑licens krävs för obegränsad användning; en gratis utvärdering fungerar för testning.  
- **Vilka .NET‑versioner stöds?** .NET 6+, .NET 5, .NET Core 3.1, och .NET Framework 4.7+.  
- **Är PNG det bästa formatet för utskrift?** PNG bevarar förlustfri kvalitet och är idealiskt för högupplöst streckkodsskrivning.

## Vad är pdf417?
`PDF417` är en staplad linjär streckkod som kan koda upp till cirka 1 700 tecken per symbol. Den används ofta för transportbiljetter, ID‑kort och lagerhantering eftersom den kan lagra stora mängder data i ett kompakt, maskinläsbart format.

## Varför använda Aspose.BarCode för pdf417‑generering?
Aspose.BarCode stödjer **70+ streckkodssymbologier**, bearbetar filer upp till **2 GB** utan att ladda hela dokumentet i minnet, och garanterar **100 % efterlevnad av ISO/IEC 15438**. I benchmark‑tester skapar biblioteket en full‑storlek MacroPdf417‑streckkod på under **150 ms** på en vanlig utvecklingslaptop, vilket gör det tillräckligt snabbt för hög‑genomströmning server‑scenarier.

## Förutsättningar

Innan du börjar, se till att du har:

* **.NET 6.0 eller senare** (koden fungerar även på .NET Framework 4.7+).  
* En **giltig Aspose.BarCode för .NET‑licens** (den kostnadsfria provversionen fungerar för utveckling).  
* **Visual Studio 2022** eller någon annan C#‑IDE du föredrar.  
* Grundläggande kunskap om C#‑syntax och objekt‑orienterade koncept.  

Inga ytterligare NuGet‑paket krävs utöver **Aspose.BarCode**.

## Hur man genererar pdf417 med makroalternativ?

Läs in `BarcodeGenerator` med `EncodeTypes.MacroPdf417`‑enum, ställ in modulstorleken, konfigurera makrofält och spara slutligen bilden. Följande steg visar den exakta ordning du bör följa för att undvika vanliga fallgropar.

### Steg 1: installera Aspose.BarCode‑NuGet‑paketet

Open ditt projekt i Visual Studio, kör sedan följande kommando i Package Manager Console:

```powershell
Install-Package Aspose.BarCode
```

Paketet lägger till `Aspose.BarCode`‑namnrymden, som innehåller `BarcodeGenerator`‑klassen som används i hela den här handledningen.

### Steg 2: skapa en streckkodsgenerator för MacroPdf417

`BarcodeGenerator` är kärnklassen som används för att generera streckkoder i Aspose.BarCode.  
Den första raden skapar en `BarcodeGenerator`‑instans som riktar sig mot **MacroPdf417**‑symbologin och bäddar in den anpassade text du vill koda.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

// Step 2: Initialize the generator with custom text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the configuration goes here
}
```

`BarcodeGenerator` är Aspose.BarCode:s kärnklass för att skapa vilken streckkod som helst; den innehåller alla kodningsalternativ och renderingsinställningar.

### Steg 3: definiera grundläggande modulstorlek

`XDimension` anger bredden på en enskild modul (pixel) i streckkoden.  
Modulstorleken styr den visuella densiteten i streckkoden. Ett pixelvärde på `2` ger en skarp bild som skrivs ut bra på vanliga etikettprinterar.

```csharp
    // Step 3: Set the X‑dimension (module width) in pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Att öka värdet gör streckkoden större, medan en minskning kan orsaka skanningsproblem på lågupplösta enheter.

### Steg 4: konfigurera PDF417‑specifika layoutalternativ för makro

`Columns` bestämmer antalet datakolumner i PDF417‑streckkoden.  
MacroPdf417 kräver flera ytterligare parametrar. Dessa inställningar låter dig dela upp data i flera filer, identifiera varje segment och verifiera integriteten.

```csharp
    // Step 4: Macro‑specific layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

`Columns`‑egenskapen påverkar streckkodens bredd, medan makrofälten (`FileID`, `SegmentID`, `SegmentsCount`, `FileName`) låter efterföljande system återmontera den ursprungliga datan korrekt.

### Steg 5: lägg till ytterligare makro‑metadata

`MacroPdf417Terminator` anger om det aktuella segmentet är det sista i en makroserie.  
Aspose.BarCode låter dig bädda in valfria makrofält som kontrollsumma, filstorlek, tidsstämpel och avsändar‑/mottagarinformation. Dessa fält är användbara för revisionsspår och felupptäckt.

```csharp
    // Step 5: Optional macro metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                 // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // Approximate size in bytes
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                       // Creation date
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                       // Marks the last segment
```

Kontrollsumman skyddar mot överföringsfel, medan tidsstämpeln och avsändarfälten ger kontext för efterföljande bearbetning. Att sätta `MacroPdf417Terminator` till `Set` signalerar att detta är det sista segmentet i makroserien.

### Steg 6: spara streckkoden som en PNG‑bild

`Save` skriver den genererade streckkodsbilden till en fil i det angivna formatet.  
Slutligen skriv den genererade streckkoden till disk. PNG bevarar förlustfri kvalitet, vilket är idealiskt för skanning.

```csharp
    // Step 6: Export the barcode
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

När koden är klar innehåller filen `ExtPDF417Meta.png` en högupplöst MacroPdf417‑streckkod som kodar den anpassade texten och all makro‑metadata.

#### Förväntat resultat

Att öppna `ExtPDF417Meta.png` visar en vertikalt orienterad streckkod med tydligt definierade rader och kolumner. Skanning av bilden med någon PDF417‑läsare returnerar den ursprungliga strängen **Åspóse.Barcóde©** och de makrofält du konfigurerade (fil‑ID, segment‑ID, kontrollsumma, etc.).

## Hur man genererar pdf417 utan makroalternativ?

För att skapa en standard PDF417‑streckkod behöver du bara sätta symbologin till `EncodeTypes.Pdf417`, ange texten som ska kodas, eventuellt justera storleksparametrar som `XDimension` och `Columns`, och sedan anropa `Save`. Detta tillvägagångssätt utelämnar alla makro‑specifika egenskaper och producerar en enkelsegment‑streckkod som är lämplig för de flesta tillämpningar.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(
           EncodeTypes.Pdf417, "Standard PDF417 data"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 3;
    generator.Parameters.Barcode.Pdf417.Columns = 6;
    generator.Save("StandardPdf417.png", BarCodeImageFormat.Png);
}
```

Detta kodsnutt demonstrerar **hur man genererar pdf417** snabbt när makrofunktionalitet inte krävs. Det enkla svaret: skapa en `BarcodeGenerator` med `EncodeTypes.Pdf417`, sätt `CodeText`, justera eventuellt `XDimension` och `Columns`, och anropa sedan `Save` med önskat bildformat.

## Vanliga fallgropar och pro‑tips

| Problem | Varför det händer | Lösning |
|-------|----------------|-----|
| Streckkoden är för liten för att skannas | X‑dimension satt till 1 pixel eller kolumner för höga | Använd minst `2` pixlar för `XDimension` och håll kolumner mellan `3` och `9` för typiska etikettstorlekar |
| Unicode‑tecken visas som � | Kodningsfel i projektfilen | Se till att projektfilen sparas som UTF‑8 och källfilen innehåller korrekt BOM |
| Makrofält ignoreras av skannern | `MacroPdf417Terminator` är inte satt för sista segmentet | Sätt `MacroPdf417Terminator = Pdf417MacroTerminator.Set` på det sista segmentet |
| Bildfilen är korrupt | Utdatastreamen stängs inte korrekt | Använd `using`‑satsen (som visas) för att garantera att generatorn tas bort |

## Fullt, körbart exempel

`BarcodeGenerator` är klassen som skapar streckkodsbilden.  
Kopiera följande kod till en ny konsolapplikation och kör den. Programmet skapar streckkoden, sparar den och skriver ut sökvägen till konsolen.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace AsposeBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with custom Unicode text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Basic size
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // Macro layout
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Optional macro metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputFile = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
                barcodeGenerator.Save(outputFile, BarCodeImageFormat.Png);

                Console.WriteLine($"Barcode saved to: {outputFile}");
            }
        }
    }
}
```

Att köra programmet skriver ut en rad liknande:

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Öppna filen för att verifiera den visuella utskriften.

## Vanliga frågor

**Q: Kan jag använda den här koden i ett ASP.NET Core‑webb‑API?**  
A: Ja. Samma `BarcodeGenerator`‑klass fungerar i alla .NET‑miljöer, inklusive ASP.NET Core, så länge `Aspose.BarCode`‑assemblyn refereras.

**Q: Stöder Aspose.BarCode andra bildformat?**  
A: Absolut. Du kan spara till PNG, JPEG, BMP, TIFF och till och med SVG genom att skicka motsvarande `BarCodeImageFormat`‑enumvärde till `Save`‑metoden.

**Q: Hur stor kan den kodade datan vara?**  
A: En enskild PDF417‑symbol kan innehålla upp till 1 700 tecken; med MacroPdf417 kan du dela upp data över flera segment, vilket i praktiken stödjer obegränsad längd.

**Q: Finns det ett sätt att lägga till färg på streckkoden?**  
A: Ja. Ställ in `ForeColor` och `BackColor`‑egenskaperna på `BarcodeGenerator` innan du anropar `Save` för att skapa färgade streckkoder.

**Q: Vad händer om jag behöver bädda in streckkoden direkt i en PDF?**  
A: Använd Aspose.PDF för att infoga den genererade PNG‑ eller SVG‑bilden i en PDF‑sida, eller använd Aspose.BarCode:s inbyggda PDF‑exportfunktion.

## Slutsats

Du vet nu **hur man genererar pdf417** för MacroPdf417‑symbologin, bäddar in anpassad Unicode‑text, konfigurerar makro‑metadata och exporterar resultatet som en PNG‑bild. Samma mönster låter dig generera en vanlig PDF417‑streckkod när makroalternativ inte krävs, och du kan anpassa koden till andra streckkodformat som stöds av Aspose.BarCode. Experimentera med olika `XDimension`‑värden, kolumnantal och makrofältkombinationer för att finjustera streckkoden för din specifika skrivare eller skanner.

Nästa steg, utforska relaterade ämnen som **skapa streckkod med anpassad text** för QR‑koder, lägga till färgfilter med `Color`‑parametrar, eller bädda in streckkoder direkt i PDF‑dokument med Aspose.PDF. Flexibiliteten i Aspose.BarCode innebär att du kan hantera allt från enkla enradiga streckkoder till komplexa flersegment‑makrostreckkoder med bara några rader C#.

Lycklig kodning, och njut av den pålitlighet som Aspose.BarCode ger till dina .NET‑streckkodslösningar!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Hur man skapar streckkod – kompakt PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hur man genererar DataMatrix‑streckkod med Aspose.BarCode för .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Generera streckkod Java – ange kodtext med Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)

---

**Last Updated:** 2026-10-14  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose

## Relaterade handledningar

- [Skapa Macro Pdf417‑streckkod med Aspose Barcode C](/barcode/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/)
- [Justera streckkodsstorlek C‑guide för att generera Pdf417‑streckkoder](/barcode/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Läs streckkod från bild C – komplett guide med Macro Pdf417](/barcode/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}