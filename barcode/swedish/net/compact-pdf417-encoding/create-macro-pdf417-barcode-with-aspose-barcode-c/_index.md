---
category: general
date: 2026-09-22
description: Skapa macro PDF417‑streckkod med Aspose.BarCode i C#. Lär dig steg‑för‑steg
  hur du genererar streckkod med Aspose, konfigurerar metadata och sparar som PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- generate barcode with Aspose
- Aspose.BarCode PDF417
- C# barcode generation
- barcode metadata configuration
language: sv
lastmod: 2026-09-22
og_description: Skapa macro PDF417‑streckkod med Aspose.BarCode i C#. Den här guiden
  visar hur du genererar streckkoden med Aspose, ställer in macro‑metadata och exporterar
  bilden.
og_image_alt: Screenshot of a created macro PDF417 barcode using Aspose.BarCode in
  C#
og_title: Skapa macro-PDF417-streckkod med Aspose.BarCode (C#) – steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Create macro PDF417 barcode using Aspose.BarCode in C#. Learn step‑by‑step
    how to generate barcode with Aspose, configure metadata, and save as PNG.
  headline: Create macro PDF417 barcode with Aspose.BarCode (C#)
  type: TechArticle
tags:
- Aspose
- PDF417
- C#
- Barcode
title: Skapa macro PDF417-streckkod med Aspose.BarCode (C#)
url: /sv/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa macro PDF417 streckkod med Aspose.BarCode (C#)

Om du behöver **skapa macro PDF417 streckkod** i en .NET‑applikation visar den här handledningen exakt hur du gör det med Aspose.BarCode. Du kommer att se ett komplett, körbart exempel som **genererar streckkod med Aspose**, konfigurerar alla macro‑specifika fält och sparar resultatet som en PNG‑bild.

Streckkoder används ofta för lager, frakt eller dokumentspårning, och Macro PDF417‑varianten låter dig bädda in ytterligare fil‑nivå metadata i själva streckkoden. I slutet av den här guiden kommer du att kunna generera en fullständigt utrustad macro PDF417‑streckkod som följer ISO/IEC 15438‑standarden.

## Vad du behöver

* .NET 6.0 SDK eller senare (koden fungerar med .NET Core och .NET Framework)
* Visual Studio 2022 (eller någon C#‑IDE)
* En NuGet‑kompatibel internetanslutning för att hämta Aspose.BarCode‑paketet
* Grundläggande kunskap om C#‑syntax

Dessa förutsättningar säkerställer att koden kompileras utan ytterligare konfiguration.

## Steg 1: Installera Aspose.BarCode NuGet‑paketet

Aspose.BarCode‑biblioteket tillhandahåller `BarcodeGenerator`‑klassen som används genom hela den här handledningen.

```bash
dotnet add package Aspose.BarCode
```

Att köra kommandot lägger till den senaste stabila versionen i din projektfil (`*.csproj`). Paketet inkluderar stöd för PDF417, Macro PDF417 och många andra symbologier.

## Steg 2: Skapa ett nytt konsolprojekt (valfritt)

Om du föredrar en ren start, generera en konsolapp:

```bash
dotnet new console -n MacroPdf417Demo
cd MacroPdf417Demo
```

Den genererade `Program.cs` kommer att innehålla koden för streckkodsgenerering.

## Steg 3: Initiera streckkodsgeneratorn

Generatorn skapas med enum‑värdet `EncodeTypes.MacroPdf417` och den text du vill koda. Aspose.BarCode hanterar automatiskt Unicode‑tecken, så du kan inkludera accentuerade bokstäver eller symboler direkt.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

class Program
{
    static void Main()
    {
        // Step 3: Create a Macro PDF417 barcode generator with the desired text
        using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // The rest of the configuration follows...
```

### Varför detta är viktigt
`EncodeTypes.MacroPdf417` talar om för biblioteket att använda macro‑versionen av PDF417, vilket ger möjlighet att bädda in fil‑nivå metadata (fil‑ID, segmentantal osv.). Texten `"Åspóse.Barcóde©"` visar att generatorn korrekt kodar UTF‑8‑tecken.

## Steg 4: Ställ in grundläggande streckkodsdimensioner

PDF417 låter dig kontrollera antalet kolumner och X‑dimensionen (bredden på en enskild modul). Att justera dessa värden påverkar streckkodens fysiska storlek och skanningspålitlighet.

```csharp
            // Step 4: Set basic barcode dimensions
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

* **XDimension** – Små värden ger en tätare streckkod; större värden gör det lättare för låg‑upplösta skannrar.
* **Columns** – Styr antalet datakolumner; vanliga värden ligger mellan 1 och 30.

## Steg 5: Konfigurera Macro PDF417‑metadata

Macro PDF417 innehåller ytterligare fält som beskriver filen som streckkoden representerar. Varje fält är valfritt, men att sätta dem förbättrar interoperabiliteten med skannrar som förstår macro‑formatet.

```csharp
            // Step 5: Configure Macro PDF417 metadata
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // demo checksum
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // bytes
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### Förklaring av varje fält

| Property | Purpose | Typical range |
|----------|---------|---------------|
| **MacroPdf417FileID** | Unik identifierare för den logiska filen som kan vara uppdelad över flera streckkoder. | 0‑2³²‑1 |
| **MacroPdf417SegmentID** | Index för det aktuella segmentet (börjar på 0). | 0‑(SegmentsCount‑1) |
| **MacroPdf417SegmentsCount** | Totalt antal segment som utgör hela filen. | 1‑99 |
| **MacroPdf417FileName** | Mänskligt läsbart namn på filen. | Up to 255 characters |
| **MacroPdf417Checksum** | Valfri kontrollsumma för felupptäckt. | 0‑65535 |
| **MacroPdf417FileSize** | Storlek på den ursprungliga filen i byte. | 0‑2³²‑1 |
| **MacroPdf417TimeStamp** | Tidsstämpel för filens skapande eller ändring. | Any `DateTime` |
| **MacroPdf417Addressee** | Destinationsidentifierare (t.ex. avdelning eller maskin). | Free‑form string |
| **MacroPdf417Sender** | Ursprungsidentifierare (t.ex. företagsnamn). | Free‑form string |
| **MacroPdf417Terminator** | Anger om detta segment är det sista. | `Set` or `Unset` |

**Proffstips:** Om du delar upp en stor fil över flera streckkoder, se till att varje segments `SegmentID` är sekventiell och att `SegmentsCount` förblir konstant för alla segment. Skannrar förlitar sig på dessa värden för att återskapa den ursprungliga filen.

## Steg 6: Spara streckkodsbilden

Aspose.BarCode stödjer många utdataformat (PNG, JPEG, BMP, SVG osv.). PNG ger förlustfri kvalitet, vilket är idealiskt för testning och dokumentation.

```csharp
            // Step 6: Save the barcode image as PNG
            barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }
    }
}
```

När programmet körs skapas en fil med namnet `ExtPDF417Meta.png` i projektets utdata‑katalog (`bin/Debug/net6.0/`). Öppna bilden med någon visare för att verifiera att streckkoden renderas korrekt.

## Steg 7: Verifiera den genererade streckkoden (valfritt)

Om du har en PDF417‑skannerapp (mobil eller desktop), skanna den sparade PNG‑filen. Skannern bör returnera:

* Den kodade texten `"Åspóse.Barcóde©"`
* Alla macro‑fält du konfigurerade (fil‑ID, segment‑ID osv.)

För automatiserad verifiering erbjuder Aspose.BarCode även en `BarCodeReader`‑klass:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

using (var reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Text: {result.CodeText}");
        Console.WriteLine($"Macro File ID: {result.GetMacroPdf417FileID()}");
        // Access other macro properties similarly
    }
}
```

Detta kodsnutt demonstrerar hur man läser tillbaka macro‑metadata programatiskt, vilket bekräftar att **generera streckkod med Aspose** fungerar från början till slut.

## Edge‑fall och bästa praxis

| Situation | Recommended handling |
|-----------|----------------------|
| **Unicode‑tecken** | Se till att källsträngen är UTF‑8 (standard i .NET). Aspose.BarCode kodar automatiskt Unicode, men verifiera skannarens teckenuppsättning. |
| **Stor filstorlek** | Macro PDF417 delar upp filer i upp till 99 segment. Om filen överstiger 400 KB, öka `SegmentsCount` och generera flera streckkoder, var och en med ett sekventiellt `SegmentID`. |
| **Tidsstämpelns precision** | Använd `DateTime.UtcNow` för universell tid; vissa skannrar förväntar sig UTC. |
| **Kontrollsumme‑validering** | Tillhandahåll en korrekt kontrollsumma om du planerar att validera integriteten på mottagarsidan. |
| **Olika bildformat** | Använd `BarCodeImageFormat.Svg` för vektorgrafik när du behöver oändligt skalbara streckkoder. |
| **Prestanda** | Återanvänd en enda `BarcodeGenerator`‑instans när du genererar många streckkoder; ändra bara `Parameters` mellan iterationerna. |

## Fullständigt, körbart exempel

Nedan är det kompletta programmet som du kan kopiera, klistra in och köra utan ändringar (förutsatt att NuGet‑paketet är installerat).



## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Aspose streckkodsexempel: generera Macro PDF417 i C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [Skapa PDF417 streckkodmetadata i C# – Komplett steg‑för‑steg‑guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [Hur man genererar PDF417 streckkodsbild i C# med Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}