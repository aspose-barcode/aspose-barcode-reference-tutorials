---
date: 2026-05-30
description: Lär dig hur du genererar DataMatrix barcode i Bytes mode och läser DataMatrix
  barcode med Aspose.BarCode for .NET – en steg‑för‑steg barcode‑guide.
keywords:
- generate datamatrix barcode
- read datamatrix barcode
- barcode generator settings
- step by step barcode
- create barcode asp.net
linktitle: DataMatrix Encoding Mode (Bytes)
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to generate DataMatrix barcode in Bytes mode and read DataMatrix
    barcode using Aspose.BarCode for .NET – a step‑by‑step barcode guide.
  headline: Generate DataMatrix Barcode in Bytes Mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to generate DataMatrix barcode in Bytes mode and read DataMatrix
    barcode using Aspose.BarCode for .NET – a step‑by‑step barcode guide.
  name: Generate DataMatrix Barcode in Bytes Mode with Aspose.BarCode for .NET
  steps:
  - name: Initialize the BarcodeGenerator
    text: '`BarcodeGenerator` is the main class used to generate barcode images for
      a given symbology and data.'
  - name: Set DataMatrix Encode Mode to Bytes
    text: '`DataMatrixEncodeMode.Bytes` tells the generator to treat the input as
      raw binary bytes rather than text.'
  - name: Set Display Text
    text: '`CodeText` property sets the human‑readable text displayed below the barcode
      symbol.'
  - name: Save the Barcode Image
    text: '`Save` method writes the generated barcode to an image file in the specified
      format.'
  - name: Try to Recognize
    text: '`BarCodeReader` reads barcode images and extracts the encoded data.'
  - name: Iterate and Display Results
    text: Iterate over `reader.ReadBarCodes()` to access each detected barcode and
      its `CodeText`. With these steps, you have successfully **generated a DataMatrix
      barcode** in Bytes mode and verified it using Aspose.BarCode for .NET. The library
      abstracts the low‑level encoding details, so you can focus on b
  type: HowTo
- questions:
  - answer: DataMatrix encoding mode defines how input data is transformed into the
      two‑dimensional pattern; Bytes mode stores raw binary bytes directly.
    question: What is DataMatrix encoding mode?
  - answer: You can obtain a free trial of Aspose.BarCode for .NET from [here](https://releases.aspose.com/).
    question: How can I get a free trial of Aspose.BarCode for .NET?
  - answer: The documentation for Aspose.BarCode for .NET is available [here](https://reference.aspose.com/barcode/net/).
    question: Where can I find documentation for Aspose.BarCode for .NET?
  - answer: Yes, Aspose.BarCode for .NET is suitable for commercial use. You can purchase
      a license from [here](https://purchase.aspose.com/buy).
    question: Is Aspose.BarCode for .NET suitable for commercial use?
  - answer: Yes, you can obtain a temporary license for Aspose.BarCode for .NET from
      [here](https://purchase.aspose.com/temporary-license/).
    question: Can I use a temporary license for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Generera DataMatrix Barcode i Bytes Mode med Aspose.BarCode for .NET
url: /sv/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera DataMatrix-streckkod i Bytes-läge med Aspose.BarCode för .NET

I den här handledningen lär du dig hur du **generate DataMatrix barcode** med Bytes-kodningsläget och sedan **read DataMatrix barcode** igen med Aspose.BarCode för .NET. Oavsett om du bygger ett lager‑hanteringssystem eller en mobilbiljettapp, visar steg‑för‑steg‑guiden nedan exakt hur du konfigurerar inställningarna för streckkodsgeneratorn, skapar en bild av hög kvalitet och avkodar den igen — allt på bara några rader C#.

## Snabba svar
- **Kan jag generera en DataMatrix‑streckkod i .NET?** Ja, använd `BarcodeGenerator` med `EncodeTypes.DataMatrix` och sätt `DataMatrixEncodeMode.Bytes`.
- **Vilken metod läser streckkoden?** `BarCodeReader` läser bilden och returnerar den kodade texten.
- **Behöver jag en licens för produktion?** En kommersiell licens krävs; en gratis provversion är tillgänglig.
- **Vilka .NET-versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Hur många byte kan jag koda?** Upp till 1 555 byte i en enda DataMatrix‑symbol.

## Vad är generate DataMatrix barcode?
**Generate DataMatrix barcode** betyder att skapa en tvådimensionell, fyrkantig streckkod som kan lagra binär data. Aspose.BarCode renderar symbolen som en PNG-, JPG- eller SVG‑bild som vilken scanner som helst kan avkoda. Den används ofta för lagerhantering, dokumenthantering och autentisering eftersom den ger hög datadensitet och felkorrigeringsförmåga, vilket gör den pålitlig även på utskrifter av låg kvalitet.

## Varför använda Bytes encoding mode?
Bytes‑läget låter dig bädda in rå binär data (upp till 1 555 byte) utan att konvertera den till text, vilket är idealiskt för serienummer, GUID:er eller krypterade nyttolaster. Aspose.BarCode stöder **30+ barcode symbologies** och kan bearbeta **multi‑hundred‑page documents** utan att ladda hela filen i minnet, vilket säkerställer hög prestanda även i scenarier med hög genomströmning.

## Förutsättningar

Innan vi dyker ner i kodningsprocessen behöver du ha följande förutsättningar på plats:

1. Aspose.BarCode for .NET: För att komma igång måste du ha Aspose.BarCode for .NET‑biblioteket installerat. Du kan ladda ner det från [här](https://releases.aspose.com/barcode/net/). Du kan också hitta andra Aspose‑produkter på [här](https://releases.aspose.com/).
2. Din utvecklingsmiljö: Se till att du har en utvecklingsmiljö installerad, inklusive Visual Studio eller någon annan IDE du föredrar.
3. Grundläggande kunskap i C#: Denna handledning förutsätter att du har en grundläggande förståelse för C#‑programmering.

För hjälp, besök [Aspose.BarCode Support](https://forum.aspose.com/c/barcode/13).

Med dessa förutsättningar på plats är du redo att börja koda data i DataMatrix‑formatet med Bytes‑läget.

## Importera namnrymder

För att använda Aspose.BarCode för .NET, importera de nödvändiga namnrymderna högst upp i din C#‑fil:

```csharp
using System;
using System.Text;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Nu när miljön är klar, låt oss gå igenom de exakta stegen för att **generate DataMatrix barcode** och sedan läsa tillbaka den.

## Hur genererar man DataMatrix barcode i Bytes‑läge?

Läs in `BarcodeGenerator`, sätt kodningsläget till Bytes, konfigurera valfri displaytext, spara bilden och använd slutligen `BarCodeReader` för att verifiera resultatet — allt i sex koncisa steg. Detta tillvägagångssätt garanterar en pålitlig streckkod som följer ISO/IEC 16022‑standarden.

### Steg 1: Initiera BarcodeGenerator

`BarcodeGenerator` är huvudklassen som används för att generera streckkods‑bilder för en given symbolik och data.

```csharp
string path = "Your Directory Path";
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, strBld.ToString()))
{
    // Set the XDimension in Pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
```

### Steg 2: Ställ in DataMatrix Encode Mode till Bytes

`DataMatrixEncodeMode.Bytes` talar om för generatorn att behandla indata som råa binära byte snarare än text.

```csharp
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Bytes;
```

### Steg 3: Ställ in Visningstext

`CodeText`‑egenskapen anger den mänskligt läsbara texten som visas under streckkodssymbolen.

```csharp
    gen.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Bytes mode";
```

### Steg 4: Spara streckkodsbilden

`Save`‑metoden skriver den genererade streckkoden till en bildfil i det angivna formatet.

```csharp
    gen.Save($"{path}DataMatrixEncodeModeBytes.png", BarCodeImageFormat.Png);
```

### Steg 5: Försök att känna igen

`BarCodeReader` läser streckkods‑bilder och extraherar den kodade datan.

```csharp
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
```

### Steg 6: Iterera och visa resultat

Iterera över `reader.ReadBarCodes()` för att komma åt varje upptäckt streckkod och dess `CodeText`.

```csharp
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixEncodeModeBytes:" + BitConverter.ToString(result.CodeBytes));
    }
}
```

Med dessa steg har du framgångsrikt **generated a DataMatrix barcode** i Bytes‑läge och verifierat den med Aspose.BarCode för .NET. Biblioteket abstraherar de lågnivå‑kodningsdetaljerna, så du kan fokusera på affärslogik snarare än streckkodsmatematik.

## Vanliga problem och lösningar

- **Encoded data is truncated** – Se till att byte‑arrayen inte överskrider 1 555 byte; annars kommer biblioteket automatiskt att byta till en större symbolstorlek eller kasta ett undantag.
- **Image appears blurry** – Spara bilden i högre upplösning (t.ex. 300 dpi) genom att sätta `generator.Parameters.ImageResolution` innan du anropar `Save`.
- **Reader returns null** – Verifiera att bildsökvägen är korrekt och att filen inte är skadad; bekräfta också att `BarCodeReader` är instansierad med `DecodeType.DataMatrix`.

## Vanliga frågor

**Q: Vad är DataMatrix encoding mode?**  
A: DataMatrix encoding mode definierar hur indata omvandlas till det tvådimensionella mönstret; Bytes‑läget lagrar råa binära byte direkt.

**Q: Hur kan jag få en gratis provversion av Aspose.BarCode för .NET?**  
A: Du kan få en gratis provversion av Aspose.BarCode för .NET från [här](https://releases.aspose.com/).

**Q: Var kan jag hitta dokumentation för Aspose.BarCode för .NET?**  
A: Dokumentationen för Aspose.BarCode för .NET finns [här](https://reference.aspose.com/barcode/net/).

**Q: Är Aspose.BarCode för .NET lämplig för kommersiell användning?**  
A: Ja, Aspose.BarCode för .NET är lämplig för kommersiell användning. Du kan köpa en licens från [här](https://purchase.aspose.com/buy).

**Q: Kan jag använda en tillfällig licens för Aspose.BarCode för .NET?**  
A: Ja, du kan få en tillfällig licens för Aspose.BarCode för .NET från [här](https://purchase.aspose.com/temporary-license/).

---

**Senast uppdaterad:** 2026-05-30  
**Testad med:** Aspose.BarCode 24.12 för .NET  
**Författare:** Aspose

## Relaterade handledningar

- [Mästra DataMatrix‑kodning i ASCII med Aspose.BarCode för .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Läs DataMatrix‑streckkod C# – Generera DataMatrix‑läge (Auto)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Hur man genererar DataMatrix‑streckkoder (ECC 200) med Aspose.BarCode för .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}