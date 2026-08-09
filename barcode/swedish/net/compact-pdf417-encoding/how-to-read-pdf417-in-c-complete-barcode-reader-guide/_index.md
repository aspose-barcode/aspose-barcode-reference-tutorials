---
category: general
date: 2026-08-09
description: Hur man läser PDF417 i C# med BarCodeReader. Lär dig att läsa streckkod‑PNG‑filer,
  hantera flera streckkoder och extrahera utökad metadata.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- c# barcode reader
- read multiple barcodes
- read barcode png
- read barcode extended
language: sv
lastmod: 2026-08-09
og_description: Hur man läser PDF417 i C# med Aspose.BarCode. Denna handledning visar
  hur du läser streckkod PNG‑filer, bearbetar flera streckkoder i en bild och hämtar
  utökad PDF417‑metadata.
og_image_alt: Screenshot of C# BarCodeReader console output displaying PDF417 metadata
og_title: Hur man läser PDF417 i C# – streckkodsläsarhandledning
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  headline: How to read PDF417 in C# – complete barcode reader guide
  type: TechArticle
- description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  name: How to read PDF417 in C# – complete barcode reader guide
  steps:
  - name: Verify the file exists before creating the reader.
    text: Verify the file exists before creating the reader.
  - name: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
    text: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
  - name: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
    text: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Hur man läser PDF417 i C# – komplett guide för streckkodsläsare
url: /sv/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man läser PDF417 i C# – komplett guide för streckkodsläsare

Om du behöver **läsa PDF417** i en .NET‑applikation, ger den här guiden en färdig‑att‑köra‑lösning. Du får se hur du läser en streckkod‑PNG, bearbetar flera streckkoder i samma bild och hämtar de utökade PDF417‑fälten som många skannrar döljer.

Att läsa PDF417‑streckkoder är vanligt inom logistik, biljettförsäljning och dokumenthantering. När du är klar med den här tutorialen kan du avkoda en Macro PDF417‑bild, visa varje resultat och använda den extra informationen (fil‑ID, segmentantal, tidsstämplar osv.) i din egen affärslogik.

## Förutsättningar

- .NET 6.0 eller senare (koden fungerar också med .NET Framework 4.7+)
- Visual Studio 2022 eller någon annan C#‑IDE
- **Aspose.BarCode for .NET** (gratis provversion eller licensierat NuGet‑paket)
- En PNG‑bild som innehåller en Macro PDF417‑streckkod (exempel‑filen heter `ExtPDF417Meta.png`)

> **Proffstips:** Installera biblioteket via NuGet‑konsolen:  
> `dotnet add package Aspose.BarCode`

## Hur man läser PDF417 med BarCodeReader i C#

Kärnan i lösningen är klassen `BarCodeReader`. Den tar emot en bildsökväg och en `DecodeType`‑enum som talar om för motorn vilken symbolik som ska sökas efter.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.ReadEngine;

class Pdf417Demo
{
    static void Main()
    {
        // Step 1: Create a BarCodeReader for a Macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Display Macro PDF417 extended metadata
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

### Varför detta fungerar

- **`DecodeType.MacroPdf417`** talar om för läsaren att leta efter Macro PDF417‑varianten, som lagrar de extra fält du ser i steg 4.
- `using`‑blocket disponerar läsaren automatiskt och frigör filhandtag.
- `ReadBarCodes()` returnerar **alla** streckkoder som matchar den begärda typen, vilket uppfyller kravet *läsa flera streckkoder* även om bilden bara innehåller en.

När programmet körs skrivs en output liknande följande ut:

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: invoice_2023.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254321
Pdf417MacroTimeStamp: 2023-03-15T10:45:00Z
Pdf417MacroAddressee: ACME Corp.
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: True
----------------------------------------
```

## Använda C#‑streckkodsläsare för att läsa flera streckkoder

Om en bild innehåller flera Macro PDF417‑symboler (t.ex. en skannad sida med en bunt biljetter), bearbetar samma `foreach`‑loop varje symbol. Ingen extra kod behövs; läsaren samlar resultaten internt.

```csharp
// Example: processing a batch image
using (BarCodeReader batchReader = new BarCodeReader(
    "batch.png", DecodeType.MacroPdf417))
{
    int index = 0;
    foreach (BarCodeResult item in batchReader.ReadBarCodes())
    {
        Console.WriteLine($"--- Barcode #{++index} ---");
        Console.WriteLine($"Text: {item.CodeText}");
        // extended fields are accessed the same way
    }
}
```

### Vanliga fallgropar

- **Bildformat:** Läsaren stödjer PNG, JPEG, BMP och TIFF. Om du försöker med ett format som den inte kan avkoda får du en tom samling. Därför betonas *läsa streckkod PNG* i tutorialen.
- **Upplösning:** Låguppslösta bilder (< 300 dpi) kan leda till missade segment. Skala upp eller begär en högkvalitativ skanning när det är möjligt.
- **Macro‑flagga:** Att glömma `DecodeType.MacroPdf417` begränsar motorn till vanlig PDF417 och kastar bort den utökade datan. Ange alltid macro‑typen när du behöver *läsa streckkodens utökade* fält.

## Läsa streckkod PNG‑filer – bästa praxis

Att arbeta med PNG‑filer är enkelt eftersom formatet bevarar förlustfri pixeldata. Här är en snabb checklista:

1. Verifiera att filen finns innan du skapar läsaren.  
   ```csharp
   if (!File.Exists(path))
       throw new FileNotFoundException($"File not found: {path}");
   ```
2. Använd `Image.FromFile` endast när du behöver förbehandla (rotera, beskära). `BarCodeReader` kan öppna filen direkt, vilket undviker extra minnesallokering.
3. Om PNG‑filen innehåller transparens fungerar läsaren fortfarande eftersom streckkoden renderas på opaka pixlar.

## Åtkomst till utökad PDF417‑metadata

Objektet `Extended.Pdf417` exponerar varje valfritt fält som definieras i PDF417‑specifikationen. Du kan mappa dessa fält till en domänmodell, lagra dem i en databas eller använda dem för validering.

```csharp
public class Pdf417Metadata
{
    public int FileID { get; set; }
    public int SegmentID { get; set; }
    public int SegmentsCount { get; set; }
    public string FileName { get; set; }
    public string Checksum { get; set; }
    public long FileSize { get; set; }
    public DateTime TimeStamp { get; set; }
    public string Addressee { get; set; }
    public string Sender { get; set; }
    public bool Terminator { get; set; }
}
```

Fyll i modellen:



## Vad bör du lära dig härnäst?

De följande tutorialerna täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man läser DataMatrix‑streckkoder med Aspose.BarCode för .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Hur man skapar streckkod – Compact PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Läs DataMatrix‑streckkod C# – Generera DataMatrix‑läge (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}