---
date: 2026-06-14
description: Lär dig hur du läser datamatrix och genererar strukturerade Append-streckkoder
  i .NET med Aspose.BarCode, det snabba och pålitliga streckkodsbiblioteket.
keywords:
- how to read datamatrix
- DataMatrix structured append
- Aspose.BarCode .NET
linktitle: DataMatrix Structured Append-konfiguration
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  headline: How to Read DataMatrix Append with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  name: How to Read DataMatrix Append with Aspose.BarCode for .NET
  steps:
  - name: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
    text: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
  - name: You can also browse other Aspose products [here](https://releases.aspose.com/).
    text: You can also browse other Aspose products [here](https://releases.aspose.com/).
  - name: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
    text: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET.
    question: What library handles DataMatrix structured append?
  - answer: Up to 16 DataMatrix symbols.
    question: How many symbols can a single structured append sequence contain?
  - answer: A free trial works for development and testing.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes, you can decode from a byte array or stream.
    question: Can I read the barcode without an image file?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Hur man läser DataMatrix Append med Aspose.BarCode för .NET
url: /sv/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# DataMatrix Structured Append‑konfiguration med Aspose.BarCode för .NET

Om du är en utvecklare som letar efter **hur man läser datamatrix** med structured append i dina .NET‑applikationer, är Aspose.BarCode för .NET din lösning. I den här steg‑för‑steg‑guiden går vi igenom hur du genererar och avkodar DataMatrix‑streckkoder som är uppdelade över flera symboler. I slutet av tutorialen kommer du att kunna skapa, konfigurera och läsa DataMatrix structured‑append‑streckkoder med Aspose.BarCode för .NET.

## Snabba svar
- **Vilket bibliotek hanterar DataMatrix structured append?** Aspose.BarCode för .NET.
- **Hur många symboler kan en enda structured append‑sekvens innehålla?** Upp till 16 DataMatrix‑symboler.
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för utveckling och testning.
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Kan jag läsa streckkoden utan en bildfil?** Ja, du kan avkoda från en byte‑array eller ström.

## Vad är **how to read datamatrix**?
**how to read datamatrix** avser processen att avkoda DataMatrix‑symboler och, när tillämpligt, sammanfoga delarna i en structured‑append‑sekvens för att återfå den ursprungliga datapayloaden. Aspose.BarCode erbjuder inbyggt stöd för detta arbetsflöde och hanterar symbolordning samt datakonkatenering automatiskt.

## Varför använda Aspose.BarCode för DataMatrix structured append?
Aspose.BarCode stödjer **30+ streckkodssymbologier** och kan avkoda bilder upp till **10 000 × 10 000 px** på under **200 ms** på vanlig serverhårdvara. Biblioteket erbjuder även **zero‑dependency‑deployment**, vilket betyder att du inte behöver extra inhemska DLL‑filer, och det fungerar på Windows, Linux och macOS .NET‑runtime‑miljöer.

## Förutsättningar

Innan du dyker ner i tutorialen behöver du:

1. Aspose.BarCode för .NET‑biblioteket – ladda ner det [här](https://releases.aspose.com/barcode/net/).
2. Du kan också bläddra bland andra Aspose‑produkter [här](https://releases.aspose.com/).
3. En .NET‑utvecklingsmiljö såsom Visual Studio 2022 eller Visual Studio Code med C#‑tillägget.

Nu börjar vi bygga och läsa DataMatrix structured‑append‑streckkoder.

## Importera namnrymder

Det första steget är att importera namnrymderna som exponerar barcode‑API:t.

Klassen `BarCodeWriter` är Aspose.BarCode:s ingångspunkt för att skapa streckkoder, medan `BarCodeReader` hanterar avkodning.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Nu när du har importerat de nödvändiga namnrymderna, låt oss generera en structured‑append‑streckkod.

## Hur läser man DataMatrix structured append‑streckkoder?

Läs in den genererade bilden (eller strömmen) i en `BarCodeReader`, aktivera alternativet `ReadStructuredAppend` och anropa `ReadBarcode`. Läsaren returnerar automatiskt den kombinerade datan och exponerar sekvensdetaljer såsom `StructuredAppendFileId`, `StructuredAppendTotalCount` och `StructuredAppendSegmentId`. Det kombinerade resultatet returneras som en enda sträng, och du kan även hämta de individuella segmentidentifierarna via läsarens egenskap `StructuredAppendSegmentId` för anpassad bearbetning.

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

I detta steg använder vi läsaren för att extrahera streckkodens ID, totalantal och fil‑ID, vilket bekräftar att structured‑append‑konfigurationen tolkats korrekt.

## Steg 1: Ställ in DataMatrix Structured Append‑konfiguration

För att skapa en DataMatrix structured‑append‑streckkod måste du konfigurera den. Detta inkluderar att definiera katalogsökvägen, streckkodens ID, antalet streckkoder och fil‑ID.

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

I detta steg har vi konfigurerat DataMatrix‑streckkoden med de önskade parametrarna.

## Vanliga problem och lösningar

- **Felaktig segmentordning:** Säkerställ att `StructuredAppendSegmentId`‑värdena är sekventiella med start på 0; annars kan läsaren inte återmontera datan korrekt.
- **Mismatching totalantal:** `StructuredAppendTotalCount` måste vara identiskt i alla symboler; en avvikelse får läsaren att betrakta sekvensen som ofullständig.
- **Bildkvalitet:** Lågresoluta bilder kan leda till avkodningsfel. Sikta på minst **300 dpi** när du renderar streckkoden till en bitmap.

## Vanliga frågor

### Q1: Vad är DataMatrix structured append, och varför används det?

A1: DataMatrix structured append är en funktion som låter dig dela en stor mängd data i flera mindre streckkoder. Detta är särskilt användbart när du har begränsat utrymme för en enda streckkod eller behöver organisera data effektivt. Det används ofta inom logistik, sjukvård och tillverkning.

### Q2: Kan jag använda Aspose.BarCode för .NET i mitt öppen‑källprojekt?

A2: Ja, Aspose.BarCode för .NET erbjuder en gratis provversion som du kan använda i öppen‑källprojekt. Du hittar provversionen [här](https://releases.aspose.com/).

### Q3: Finns det någon community‑support för Aspose.BarCode för .NET?

A3: Ja, du kan söka community‑support och interagera med andra användare på Aspose.BarCode‑forumet [här](https://forum.aspose.com/c/barcode/13).

### Q4: Hur kan jag få en tillfällig licens för Aspose.BarCode för .NET?

A4: Om du behöver en tillfällig licens för utvärdering eller testning kan du skaffa en [här](https://purchase.aspose.com/temporary-license/).

### Q5: Stöder Aspose.BarCode för .NET andra streckkodstyper?

A5: Ja, Aspose.BarCode för .NET stödjer ett brett spektrum av streckkodstyper, inklusive QR‑koder, Code 128, EAN‑13 och många fler. Du kan utforska den fullständiga dokumentationen [här](https://reference.aspose.com/barcode/net/) för att se hela listan över stödda streckkodstyper.

---

**Senast uppdaterad:** 2026-06-14  
**Testad med:** Aspose.BarCode 24.11 för .NET  
**Författare:** Aspose

## Relaterade handledningar

- [DataMatrix‑läsprogrammering med Aspose.BarCode för .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-reader-programming/)
- [Generera DataMatrix‑streckkoder med Aspose.BarCode för .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-versions/)
- [Master DataMatrix‑makrokonfiguration med Aspose.BarCode för .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}