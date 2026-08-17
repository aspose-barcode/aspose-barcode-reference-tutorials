---
date: 2026-08-17
description: Lär dig hur du skapar DataMatrix-streckkod med macro characters med Aspose.BarCode
  för .NET och upptäck hur du använder DataMatrix i dina applikationer.
keywords:
- create datamatrix barcode
- datamatrix barcode error correction
- aspose barcode macro
- .net barcode generation
lastmod: 2026-08-17
linktitle: DataMatrix Macro-konfiguration
og_description: Lär dig hur du skapar DataMatrix-streckkod med macro characters med
  Aspose.BarCode för .NET. Denna guide erbjuder steg‑för‑steg‑kod, anpassningsalternativ
  och verifieringstips för pålitlig streckkodsgenerering.
og_image_alt: Guide showing creation of DataMatrix barcode with macro characters in
  .NET using Aspose.BarCode
og_title: Skapa DataMatrix-streckkod med macro characters med Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  headline: How to create DataMatrix barcode with macro characters in .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  name: How to create DataMatrix barcode with macro characters in .NET
  steps:
  - name: setting up your project
    text: Create a new Console Application (or any .NET project) in Visual Studio.
      Add a reference to the Aspose.BarCode DLLs that you obtained from the download.
  - name: DataMatrix macro configuration
    text: The core of the tutorial – here we actually **create DataMatrix barcode**
      with a macro character. > **Pro tip:** Replace `"ASPOSE"` with any string you
      need to encode. The macro character (`Macro05`) tells scanners that this barcode
      is part of a macro sequence.
  - name: customize barcode parameters for error correction
    text: 'Before saving, you can tweak additional settings: - **XDimension** – controls
      the size of each module (pixel). - **Margin**, **ErrorCorrection**, and **EncodingMode**
      – all accessible via `gen.Parameters.Barcode.DataMatrix`.'
  - name: save the barcode
    text: The snippet above saves the image as `DataMatrixMacro.png` in the folder
      you specified. PNG is loss‑less, making it ideal for further processing.
  - name: recognize the barcode
    text: '`BarCodeReader` is Aspose.BarCode''s class for decoding barcodes from images.
      Using `BarCodeReader` we immediately read back the generated image to confirm
      that the macro character and data are correct. This round‑trip validation is
      especially handy during automated testing.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET is a powerful library that allows .NET developers
      to generate and recognize barcodes in various formats, including DataMatrix,
      QR, and more.
    question: What is Aspose.BarCode for .NET?
  - answer: DataMatrix barcodes are compact, highly reliable, and can store large
      amounts of data, making them ideal for manufacturing, logistics, and healthcare.
    question: Why should I use DataMatrix barcodes?
  - answer: You can find the documentation at [the Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).
    question: Where can I find the documentation for Aspose.BarCode for .NET?
  - answer: Yes, you can download a free trial from [the free trial link](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: If you have any questions or need support, you can visit the Aspose.BarCode
      for .NET forum at [the support forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- aspose.barcode
- c# barcode generation
- macro barcode
- barcode error correction
title: Hur du skapar DataMatrix-streckkod med macro characters i .NET
url: /sv/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar DataMatrix-streckkod med makrotecken i .NET

## Introduktion

Att generera en **DataMatrix-streckkod** som innehåller makrotecken låter dig packa extra referensinformation i en liten fyrkantig symbol. I den här handledningen kommer du att lära dig hur du **skapar DataMatrix-streckkod** med makrotecken med Aspose.BarCode för .NET, anpassar storlek och felkorrigering, och omedelbart verifierar resultatet. När du är klar är du redo att bädda in makro‑aktiverade streckkoder i produktetiketter, dokument eller medicintekniska enheter.

## Snabba svar
- **Vad är det primära biblioteket?** Aspose.BarCode för .NET  
- **Kan jag skapa en DataMatrix-streckkod med makrotecken?** Ja – ange egenskapen `MacroCharacters`.  
- **Behöver jag en licens för produktion?** En giltig Aspose-licens krävs för produktionsanvändning.  
- **Vilka .NET-versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Finns en gratis provversion?** Absolut – ladda ner den från den officiella Aspose-webbplatsen.

## Förutsättningar

Innan du dyker ner i makrokonfigurationen, se till att du har följande:

1. **Visual Studio** – någon nyare version fungerar.  
2. **Aspose.BarCode för .NET** – ladda ner den från [nedladdningslänken](https://releases.aspose.com/barcode/net/).  
3. **Grundläggande .NET-kunskap** – bekantskap med C# och .NET-ekosystemet.

## Importera namnrymder

Vi börjar med att importera namnrymderna som krävs för streckkodsgenerering och -igenkänning.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

## Vad är “generera DataMatrix-streckkod” med makrotecken?

`MacroCharacters` möjliggör att DataMatrix-streckkoder kan innehålla makrosymboler som refererar till ytterligare data. Genom att använda makrotecken som Macro05 eller Macro06 kan en enda streckkod peka på en större datamängd eller en sekvens av relaterade streckkoder, vilket är värdefullt inom logistik, tillverkning och dokumentspårning där kompakt kodning av länkad information krävs.

## Varför använda Aspose.BarCode för att generera DataMatrix-streckkod?

Aspose.BarCode ger dig exakt kontroll över DataMatrix-storlek, felkorrigeringsnivå och makroinställningar, stödjer över 30 streckkodssymboler och hanterar filer upp till 10 MB utan att ladda hela bilden i minnet. Dess plattformsoberoende .NET-implementation fungerar på .NET Framework, .NET Core och .NET 5/6, och inkluderar inbyggd igenkänning så att du kan validera streckkoden omedelbart.

## Steg‑för‑steg guide

### Steg 1: konfigurera ditt projekt

Skapa en ny Konsolapplikation (eller något .NET‑projekt) i Visual Studio. Lägg till en referens till Aspose.BarCode‑DLL‑erna som du hämtade från nedladdningen.

### Steg 2: DataMatrix-makrokonfiguration

Kärnan i handledningen – här **skapar vi faktiskt DataMatrix-streckkod** med ett makrotecken.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixMacro:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    // Set the macro character to 05
    gen.Parameters.Barcode.DataMatrix.MacroCharacters = MacroCharacter.Macro05;
    gen.Save($"{path}DataMatrixMacro.png", BarCodeImageFormat.Png);

    // Try to recognize it
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixMacro:" + result.CodeText);
    }
}
```

> **Proffstips:** Ersätt `"ASPOSE"` med vilken sträng du än behöver koda. Makrotecknet (`Macro05`) talar om för skannrar att denna streckkod är en del av en makrosekvens.

### Steg 3: anpassa streckkodens parametrar för felkorrigering

Innan du sparar kan du justera ytterligare inställningar:

- **XDimension** – styr storleken på varje modul (pixel).  
- **Margin**, **ErrorCorrection** och **EncodingMode** – alla åtkomliga via `gen.Parameters.Barcode.DataMatrix`.

### Steg 4: spara streckkoden

Kodsnutten ovan sparar bilden som `DataMatrixMacro.png` i den mapp du angav. PNG är förlustfri, vilket gör den idealisk för vidare bearbetning.

### Steg 5: identifiera streckkoden

`BarCodeReader` är Aspose.BarCode:s klass för avkodning av streckkoder från bilder. Med `BarCodeReader` läser vi omedelbart tillbaka den genererade bilden för att bekräfta att makrotecknet och data är korrekta. Denna rundresa‑validering är särskilt praktisk under automatiserade tester.

## Hur använder man DataMatrix i verkliga scenarier?

Du kan använda DataMatrix-streckkoder med makrotecken för produktmärkning, länka serienummer till en central databas, för dokumentspårning genom att bädda in en referens till en digital post, och för sjukvårdsutrustningstagg som lagrar patient‑ eller enhetsdata i en liten, skanningsbar symbol. Dessa användningsområden minskar manuell datainmatning och förbättrar spårbarheten.

## Vanliga problem & lösningar

| Problem | Orsak | Åtgärd |
|---------|-------|--------|
| Streckkod inte igenkänd | Felaktig `XDimension` eller låg bildupplösning | Öka `XDimension.Pixels` till 4‑6 och spara som PNG eller TIFF |
| Makrotecken ignoreras | Läsaren stödjer inte makroläge | Använd en skanner/läsare som uttryckligen stödjer DataMatrix-makro (t.ex. nyare ZXing-versioner) |
| Sökväg ej hittad | Ogiltig `path`-variabel | Säkerställ att katalogen finns eller använd `Path.Combine` med `Environment.CurrentDirectory` |

## Vanliga frågor

**Q: Vad är Aspose.BarCode för .NET?**  
A: Aspose.BarCode för .NET är ett kraftfullt bibliotek som låter .NET‑utvecklare generera och känna igen streckkoder i olika format, inklusive DataMatrix, QR och mer.

**Q: Varför bör jag använda DataMatrix-streckkoder?**  
A: DataMatrix-streckkoder är kompakta, mycket pålitliga och kan lagra stora mängder data, vilket gör dem idealiska för tillverkning, logistik och sjukvård.

**Q: Var kan jag hitta dokumentationen för Aspose.BarCode för .NET?**  
A: Du kan hitta dokumentationen på [Aspose.BarCode för .NET-dokumentationen](https://reference.aspose.com/barcode/net/).

**Q: Finns en gratis provversion för Aspose.BarCode för .NET?**  
A: Ja, du kan ladda ner en gratis provversion från [den gratis provversionslänken](https://releases.aspose.com/).

**Q: Var kan jag få support för Aspose.BarCode för .NET?**  
A: Om du har frågor eller behöver support kan du besöka Aspose.BarCode för .NET‑forumet på [supportforumet](https://forum.aspose.com/c/barcode/13).

---

**Senast uppdaterad:** 2026-08-17  
**Testad med:** Aspose.BarCode 24.11 för .NET  
**Författare:** Aspose

## Relaterade handledningar

- [Skapa streckkod Aspose .NET - Konfigurera DataMatrix-kodtext](/barcode/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Hur man genererar DataMatrix-streckkoder (ECC 200) med Aspose.BarCode för .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [DataMatrix Structured Append-konfiguration med Aspose.BarCode för .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}