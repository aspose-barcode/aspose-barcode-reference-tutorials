---
date: 2026-01-20
description: Lär dig hur du genererar DataMatrix‑streckkod och avkodar DataMatrix‑streckkod
  med strukturerad tilläggskonfiguration i .NET med Aspose.BarCode för hög effektiv
  dataorganisation.
linktitle: DataMatrix Structured Append Configuration
second_title: Aspose.BarCode .NET API
title: Hur man genererar DataMatrix‑streckkod med Structured Append med Aspose.BarCode
  för .NET
url: /sv/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# DataMatrix Structured Append-konfiguration med Aspose.BarCode för .NET

Om du är en utvecklare som vill **generera DataMatrix‑streckkod** med strukturerad append‑konfiguration i dina .NET‑applikationer, är Aspose.BarCode för .NET din lösning. I den här steg‑för‑steg‑guiden går vi igenom hur du skapar och läser dessa streckkoder, delar upp varje exempel i lätt‑följda delar så att du snabbt kan behärska arbetsflödet.

## Snabba svar
- **Vilket bibliotek ska jag använda?** Aspose.BarCode for .NET  
- **Hur många kodrader?** Ungefär 30 rader för att generera och läsa en strukturerad DataMatrix‑streckkod  
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion  
- **Stödda plattformar?** .NET .NET 5/6/7  
- **Kan jag decode DataMatrix barcode”  

## Förutsättningar

1. **Aspose.BarCode för .NET Library** – ladda ner det från [here](https://releases.aspose.com/barcode/net/).  
2. **Utvecklingsmiljö** – Visual Studio (valfri nyare version) eller en annan .NET‑kompatibel IDE.

Nu, låt oss börja med steg‑för‑steg‑guiden för att arbeta med DataMatrix structured append med Aspose.BarCode för .NET.

## Importera namnrymder

Först, importera namnrymderna som ger dig åtkomst till klasserna för streckkodsgenerering och -igenkänning.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Nu är du redo att generera och läsa en **DataMatrix‑streckkod**.

## Så genererar du DataMatrix‑streckkod med Structured Append

För att skapa en DataMatrix‑structured‑append‑streckkod måste du konfigurera flera parametrar såsom streckkodens ID, det totala antalet streckkoder i sekvensen och fil‑ID‑t som binder dem ihop.

```csharp
string path = "Your Directory Path";

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;

    // Set DataMatrix structured append mode
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodeId = 3;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodesCount = 5;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendFileId = 150;

    // Generate the barcode image
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

I detta kodexempel har vi ställt in de väsentliga egenskaperna som möjliggör structured‑append‑funktionen.

## Så avkodar du DataMatrix‑streckkod med Aspose.BarCode

Efter att ha genererat streckkoden behöver du ofta läsa dess inbäddade information. Följande kod använder `BarCodeReader` för att extrahera structured‑append‑detaljerna från bilden vi just skapade.

```csharp
    using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
    {
        reader.ReadBarCodes();

        Console.WriteLine("Barcode ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodeId);
        Console.WriteLine("Barcodes count: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodesCount);
        Console.WriteLine("File ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendFileId);
    }
}
```

Detta block **avkodar DataMatrix‑streckkod**‑information såsom streckkodens ID, det totala antalet och fil‑ID‑t, vilket bekräftar att structured‑append‑data har inbäddats korrekt.

## **Felaktiga dimensioner:** Se till att `XDimension.Pixels` matchar skrivarens eller skärmens upplösning; annars kan streckkoden bli oläslig.  
- **Ej matchande antal:** `Structured Om du ser licensvarningar eller kommersiell licensfil är korrekt refererad i ditt projekt.

## Slutsats

Aspose.BarCode för .NET gör det enkelt att **generera DataMatrix‑streckkod** och **avkoda DataMatrix‑streckkod** med structured‑append‑konfigurationer. Genom att följa stegen ovan kan du integrera dessa streckkoder i lagersystem, dokumentspårning eller någon situation där det är fördelaktigt att dela upp stora datamängder över flera streckkoder.

## Vanliga frågor

### Q1: Vad är DataMatrix structured append, och varför används det?

A1: DataMatrix structured append är en funktion som låter dig dela upp en stor mängd data i flera mindre streckkoder. Detta är särskilt användbart när du har begränsat utrymme för en enda streckkod eller behöver organisera data effektivt. Det används ofta i branscher som logistik, sjukvård och tillverkning.

### Q2: Kan jag använda Aspose.BarCode för .NET i mitt öppen‑källprojekt?

A2: Ja, Aspose.BarCode för .NET erbjuder en gratis provversion som du kan använda i öppen‑källprojekt. Du kan hitta provversionen [here](https://releases.aspose.com/).

### Q3: Finns det någon community‑support för Aspose.BarCode för .NET?

A3: Ja, du kan söka community‑support och interagera med andra användare på Aspose.BarCode‑forumet [here](https://forum.aspose.com/c/barcode/13).

### Q4: Hur kan jag skaffa en tillfällig licens för Aspose.BarCode för .NET?

A4: Om du behöver en tillfällig licens för utvärdering eller testning, kan du skaffa en från [here](https://purchase.aspose.com/temporary-license/).

### Q5: Stöder Aspose.BarCode för .NET andra streckkodstyper?

A5: Ja, Aspose.BarCode för .NET stöder ett brett spektrum av streckkodstyper, inklusive QR‑koder, Code 128, EAN‑13 och många fler. Du kan utforska den fullständiga dokumentationen [here](https://reference.aspose.com/barcode/net/) för att se den kompletta listan över stödda streckkodstyper.

---

**Senast uppdaterad:** 2026-01-20  
**Testad med:** Aspose.BarCode 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}