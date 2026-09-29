---
date: 2026-08-02
description: Lär dig hur du skapar DataMatrix‑streckkod, genererar datamatrix och
  utforskar generering av högdensitetsstreckkod med Aspose.BarCode för .NET‑projekt.
keywords:
- create datamatrix barcode
- high density barcode
- generate datamatrix barcode
- barcode generation asp.net
- temporary aspose license
lastmod: 2026-08-02
linktitle: DataMatrix ECC 200‑konfiguration
og_description: Skapa DataMatrix‑streckkod med Aspose.BarCode för .NET. Denna handledning
  visar generering av högdensitetsstreckkod, tillfällig Aspose‑licensinställning och
  steg‑för‑steg C#‑kod.
og_image_alt: Guide showing C# code to create a DataMatrix barcode using Aspose.BarCode
og_title: Skapa DataMatrix‑streckkod – Aspose.BarCode .NET‑guide
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  headline: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  name: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is Aspose.BarCode''s core class that creates and renders
      barcodes. It accepts the symbology type and the text to encode. Replace `"Your
      Directory Path"` with the folder where you’d like the image saved.'
  - name: Set XDimension and ECC Type
    text: '`XDimension` defines the pixel size of each DataMatrix module, while `DataMatrixEcc`
      selects the error‑correction level. ECC 200 provides the highest correction
      capability for this symbology. Adjust the pixel value if you need larger or
      smaller modules; typical values are 4‑6 px for on‑screen displa'
  - name: Generate and Save the Barcode Image
    text: The `Save` method writes the barcode to a file. You can choose PNG, JPEG,
      or TIFF by passing the corresponding `BarCodeImageFormat` enum value. Switch
      `BarCodeImageFormat.Png` to `BarCodeImageFormat.Jpeg` or `BarCodeImageFormat.Tiff`
      if your workflow requires a different format.
  type: HowTo
- questions:
  - answer: Yes, the same API works in .NET Core, .NET 5, and .NET 6 projects.
    question: Can I use this code in a .NET Core console application?
  - answer: Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` in the
      `Save` call.
    question: How do I change the output format to JPEG?
  - answer: Yes – generate the image first, then add it to a PDF using Aspose.PDF
      or any PDF library.
    question: Is it possible to embed the barcode directly into a PDF?
  - answer: DataMatrix supports UTF‑8; simply pass the Unicode string to the generator
      as shown.
    question: What if I need to encode Unicode characters?
  - answer: Absolutely – place the generation code inside a loop and change the data/value
      for each iteration.
    question: Does the library support batch generation of multiple barcodes?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- .NET barcode generation
- C# barcode tutorial
title: Hur man skapar DataMatrix‑streckkod (ECC 200) med Aspose.BarCode för .NET
url: /sv/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar DataMatrix-streckkod (ECC 200) med Aspose.BarCode för .NET

## Introduktion

I den här guiden kommer du att **skapa DataMatrix-streckkod** (ECC 200) med Aspose.BarCode för .NET. Oavsett om du bygger ett lagerhanteringssystem, ett kassasystem eller automatiserar dokumentarbetsflöden, kan en högdensitetsstreckkod lagra mycket data på ett litet utrymme. Vi går igenom varje konfigurationssteg, förklarar varför varje inställning är viktig och ger dig färdiga C#‑kodsnuttar.

## Snabba svar
- **Vilket bibliotek är bäst för DataMatrix i .NET?** Aspose.BarCode for .NET  
- **Vilken ECC-nivå ger ECC 200?** Högdensitetsfelkorrigering för robust skanning.  
- **Behöver jag en licens för att köra exemplet?** En tillfällig licens fungerar för utvärdering; en full licens krävs för produktion.  
- **Vilka .NET-versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Kan jag exportera PNG, JPEG eller TIFF?** Ja – `Save`‑metoden stöder flera bildformat.

## Vad är DataMatrix ECC 200?

DataMatrix ECC 200 är en högdensitets tvådimensionell streckkod som kan lagra upp till 2 335 alfanumeriska tecken eller 1 556 byte binär data i ett kompakt fyrkantigt eller rektangulärt mönster. Den använder Reed‑Solomon felkorrigering för att återställa förlorade eller skadade moduler, vilket gör den idealisk för tillämpningar såsom märkning av flygplansdelar, farmaceutisk märkning och logistik där tillförlitlighet är kritisk.

## Varför använda Aspose streckkodsgenerering?

Aspose.BarCode stödjer **30+ symbologier**, kan rendera bilder upp till 10 000 × 10 000 px utan att ladda hela filen i minnet, och ger deterministisk output på Windows, Linux och macOS. Dess API låter dig kontrollera varje renderingsparameter, vilket gör den till det mest flexibla valet för **barcode generation ASP.NET**‑scenarier.

## Förutsättningar

1. **Utvecklingsmiljö** – Visual Studio med lämplig .NET‑ramverk installerad.  
2. **Aspose.BarCode for .NET** – Ladda ner och installera från webbplatsen, [här](https://releases.aspose.com/barcode/net/).  
3. **Licens** – Skaffa en tillfällig licens för testning från [här](https://purchase.aspose.com/temporary-license/).  
4. **C#‑grunder** – Bekantskap med C#‑syntax och projektstruktur.

Nu när vi har grunderna täckta, låt oss gå vidare till att konfigurera DataMatrix ECC 200.

## Importera namnrymder

`Aspose.BarCode.Generation`‑namnrymden innehåller alla klasser som krävs för streckkodsskapande. Importera den högst upp i din fil:

```csharp
using Aspose.BarCode.Generation;
```

## Så skapar du DataMatrix-streckkod (ECC 200) steg för steg

För att producera en DataMatrix ECC 200‑streckkod laddar du helt enkelt den data du vill koda, konfigurerar några nyckelparametrar på `BarcodeGenerator` och anropar sedan `Save` för att skriva bildfilen. Detta trestegsflöde hanterar kodning, felkorrigering och val av utdataformat, vilket låter dig integrera streckkodsskapande i vilken .NET‑applikation som helst med minimal kod.

### Steg 1: Initiera BarcodeGenerator

`BarcodeGenerator` är Aspose.BarCode:s kärnklass som skapar och renderar streckkoder. Den tar emot symbologityp och texten som ska kodas.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixEcc200:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Your code goes here
}
```

Byt ut `"Your Directory Path"` mot den mapp där du vill spara bilden.

### Steg 2: Ställ in XDimension och ECC-typ

`XDimension` definierar pixelstorleken för varje DataMatrix‑modul, medan `DataMatrixEcc` väljer felkorrigeringsnivån. ECC 200 ger den högsta korrigeringskapaciteten för denna symbologi.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

Justera pixelvärdet om du behöver större eller mindre moduler; typiska värden är 4‑6 px för skärmvisning och 8‑10 px för tryckta etiketter.

### Steg 3: Generera och spara streckkodsbilden

`Save`‑metoden skriver streckkoden till en fil. Du kan välja PNG, JPEG eller TIFF genom att skicka motsvarande `BarCodeImageFormat`‑enumvärde.

```csharp
gen.Save($"{path}DataMatrixEcc200.png", BarCodeImageFormat.Png);
```

Byt `BarCodeImageFormat.Png` till `BarCodeImageFormat.Jpeg` eller `BarCodeImageFormat.Tiff` om ditt arbetsflöde kräver ett annat format.

## Vanliga problem & felsökning

| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| Streckkoden är suddig | XDimension för låg | Öka `XDimension.Pixels` till 6‑8 |
| Skanning misslyckas på mobil | Fel ECC-nivå | Säkerställ `DataMatrixEcc = DataMatrixEccType.Ecc200` |
| Filen skapades inte | Ogiltig sökvägssträng | Använd en absolut sökväg eller säkerställ att mappen finns |

## Vanliga frågor

**Q: Kan jag använda den här koden i en .NET Core‑konsolapplikation?**  
A: Ja, samma API fungerar i .NET Core, .NET 5 och .NET 6‑projekt.

**Q: Hur ändrar jag utdataformatet till JPEG?**  
A: Byt `BarCodeImageFormat.Png` till `BarCodeImageFormat.Jpeg` i `Save`‑anropet.

**Q: Är det möjligt att bädda in streckkoden direkt i en PDF?**  
A: Ja – generera bilden först, lägg sedan till den i en PDF med Aspose.PDF eller något PDF‑bibliotek.

**Q: Vad händer om jag behöver koda Unicode‑tecken?**  
A: DataMatrix stödjer UTF‑8; skicka helt enkelt Unicode‑strängen till generatorn som visat.

**Q: Stöder biblioteket batch‑generering av flera streckkoder?**  
A: Absolut – placera genereringskoden i en loop och ändra data/värde för varje iteration.

## Slutsats

Vi har gått igenom allt du behöver för att **skapa DataMatrix-streckkod** (ECC 200) med Aspose.BarCode för .NET: från förutsättningar och namnrymdimporter till konfiguration av X‑dimension, val av ECC‑nivå och sparande av bilden i önskat format. Experimentera med de många extra egenskaperna — såsom marginal, bakgrundsfärg och rotation — för att finjustera resultatet för ditt specifika användningsområde.

Om du stöter på några problem är communityn redo att hjälpa till på [Aspose.BarCode‑forumet](https://forum.aspose.com/c/barcode/13). Lycka till med kodningen!

---

**Last Updated:** 2026-08-02  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Hur man genererar DataMatrix ECC 000-140 streckkoder med Aspose.BarCode för .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-000-140-configuration/)
- [Hur man läser DataMatrix-streckkoder med Aspose.BarCode för .NET](/barcode/net/datamatrix-barcode-reading/)
- [Skapa streckkod PNG – DataMatrix-aspektförhållande – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}