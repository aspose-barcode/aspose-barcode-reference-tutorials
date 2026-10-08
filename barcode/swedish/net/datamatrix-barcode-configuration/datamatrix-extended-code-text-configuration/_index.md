---
date: 2026-09-23
description: Lär dig hur du använder Aspose.BarCode för att generera en DataMatrix‑streckkod
  med utökad kodtext i .NET, idealisk för lager- och logistikapplikationer.
keywords:
- how to use aspose
- create barcode for inventory
- barcode generation .net core
- generate barcode image c#
lastmod: 2026-09-23
linktitle: DataMatrix – konfiguration av utökad kodtext
og_description: Hur du använder Aspose.BarCode för att generera en DataMatrix‑streckkod
  med utökad kodtext i .NET. Följ en snabb steg‑för‑steg‑guide för lager- och logistiklösningar.
og_image_alt: Screenshot of a DataMatrix barcode generated with Aspose.BarCode in
  a .NET console app
og_title: Hur man använder Aspose.BarCode för att skapa DataMatrix‑kodtext i .NET
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  headline: How to use Aspose.BarCode to create DataMatrix code text in .NET
  type: TechArticle
- description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  name: How to use Aspose.BarCode to create DataMatrix code text in .NET
  steps:
  - name: Define the output folder
    text: Specify where the generated barcode image will be saved. Replace the placeholder
      with a valid path on your machine.
  - name: Build the extended code text
    text: '`DataMatrixExtCodetextBuilder` is a helper class that assembles the extended
      code text according to the DataMatrix specification. It automatically inserts
      the required ECI (Extended Channel Interpretation) markers. This mix demonstrates
      how you can combine Unicode characters, C40 encoding, plain tex'
  - name: Generate the final codetext string
    text: After configuring all parts, retrieve the combined string that Aspose.BarCode
      will embed into the barcode.
  - name: Create the DataMatrix barcode
    text: '`BarcodeGenerator` is the core class that produces barcode images. Instantiate
      it with `EncodeTypes.DataMatrix` and the extended codetext, then set visual
      parameters such as X‑dimension, image format, and optional human‑readable text.
      The above code **creates barcode aspose .net** with the desired e'
  - name: Verify the barcode by reading it back
    text: '`BarCodeReader` validates that the generated symbol can be decoded correctly,
      which is essential for automated test pipelines and quality assurance. If everything
      is set up properly, the console will output the exact extended code text you
      built earlier.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library is needed?
  - answer: DataMatrix with extended code text
    question: Which barcode type?
  - answer: Yes, the API is cross‑platform
    question: Can I use .NET Core / .NET 6?
  - answer: A free trial works for development; a license is required for production
    question: Do I need a license for testing?
  - answer: About 10‑15 minutes for a basic example
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- Aspose.BarCode
- DataMatrix
- .NET barcode
- C# barcode generation
- inventory labeling
title: Hur man använder Aspose.BarCode för att skapa DataMatrix‑kodtext i .NET
url: /sv/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man använder Aspose.BarCode för att skapa DataMatrix-kodtext i .NET

Integrating barcodes into modern .NET applications is no longer a niche task—it’s a core requirement for inventory, logistics, and mobile scanning solutions. In this guide you’ll **learn how to use Aspose.BarCode** to configure a DataMatrix barcode with extended code text, generate the image, and verify it programmatically. You’ll see why this approach is ideal for creating barcode for inventory and how it fits into .NET Core or .NET 6 projects.

## Snabba svar
- **Vilket bibliotek behövs?** Aspose.BarCode för .NET  
- **Vilken streckkodstyp?** DataMatrix med utökad kodtext  
- **Kan jag använda .NET Core / .NET 6?** Ja, API:et är plattformsoberoende  
- **Behöver jag en licens för testning?** En gratis provversion fungerar för utveckling; en licens krävs för produktion  
- **Hur lång tid tar implementeringen?** Ungefär 10‑15 minuter för ett grundexempel  

## Vad är Aspose.BarCode för .NET?
Aspose.BarCode för .NET är ett kommersiellt bibliotek som gör det möjligt för utvecklare att generera och känna igen mer än 30 streckkodssymboler, inklusive DataMatrix, QR och Code 128, samt att producera bilder upp till 10 000 × 10 000 pixlar utan externa beroenden. Det stöder .NET Framework 4.5+, .NET Core 3.1+ och .NET 5/6/7.

## Varför använda DataMatrix med utökad kodtext?
DataMatrix med utökad kodtext låter dig bädda in flera kodningsscheman—UTF‑8, C40, Text, X12—i en enda symbol, vilket möjliggör upp till **3116 kodord** (ungefär 155 KB data) i en kompakt fyrkant. Denna funktion är perfekt för flerspråkig produktmärkning, spårning av medicintekniska produkter och smart förpackning där du behöver kombinera alfanumeriska ID:n med binära data.

## Förutsättningar

Innan du börjar, verifiera att du har följande:

1. **Aspose.BarCode för .NET** – ladda ner det från den officiella webbplatsen **[Aspose.BarCode .NET download page](https://releases.aspose.com/barcode/net/)**.  
2. **En .NET‑utvecklingsmiljö** – Visual Studio, Rider eller VS Code med .NET SDK.  
3. **Grundläggande C#‑kunskaper** – du bör vara bekväm med klasser, namnrymder och `using`‑direktivet.

## Importera namnrymder

Lägg till de nödvändiga namnrymderna högst upp i din C#‑fil så kompilatorn vet var den ska hitta streckkodsklasserna.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Dessa namnrymder ger dig åtkomst till både streckkodsgenerering och -igenkänning.

## Hur man konfigurerar DataMatrix med utökad kodtext?

Load the builder, add the desired segments, and let Aspose.BarCode handle the ECI markers automatically. This direct‑answer paragraph tells you the exact steps: create a `DataMatrixExtCodetextBuilder`, add Unicode, C40, plain‑text, and Text mode segments, then retrieve the combined string for the generator.

### Steg 1: Definiera utdatamappen

Ange var den genererade streckkodsbilden ska sparas. Ersätt platshållaren med en giltig sökväg på din maskin.

```csharp
string path = "Your Directory Path";
```

### Steg 2: Bygg den utökade kodtexten

`DataMatrixExtCodetextBuilder` är en hjälparklass som samlar den utökade kodtexten enligt DataMatrix‑specifikationen. Den infogar automatiskt de nödvändiga ECI‑markörerna (Extended Channel Interpretation).

```csharp
DataMatrixExtCodetextBuilder codetextBuilder = new DataMatrixExtCodetextBuilder();
codetextBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
codetextBuilder.AddECICodetextWithEncodeMode(ECIEncodings.UTF8, DataMatrixEncodeMode.C40, "ABCDE");
codetextBuilder.AddPlainCodetext("test");
codetextBuilder.AddCodetextWithEncodeMode(DataMatrixEncodeMode.Text, "abcde");
```

Detta exempel visar hur du kan kombinera Unicode‑tecken, C40‑kodning, vanlig text och Text‑läge i en enda DataMatrix‑symbol.

### Steg 3: Generera den slutgiltiga kodtextsträngen

Efter att ha konfigurerat alla delar, hämta den kombinerade strängen som Aspose.BarCode kommer att bädda in i streckkoden.

```csharp
string codetext = codetextBuilder.GetExtendedCodetext();
```

### Steg 4: Skapa DataMatrix‑streckkoden

`BarcodeGenerator` är kärnklassen som producerar streckkods‑bilder. Instansiera den med `EncodeTypes.DataMatrix` och den utökade kodtexten, och ställ sedan in visuella parametrar såsom X‑dimension, bildformat och valfri mänskligt läsbar text.

```csharp
using (var generator = new BarcodeGenerator(EncodeTypes.DataMatrix, codetext))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended Codetext";
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ExtendedCodetext;

    generator.Save($"{path}DataMatrixExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Koden ovan **skapar streckkod aspose .net** med den önskade utökade kodtexten och sparar den som en PNG‑fil.

### Steg 5: Verifiera streckkoden genom att läsa tillbaka den

`BarCodeReader` validerar att den genererade symbolen kan avkodas korrekt, vilket är viktigt för automatiserade test‑pipelines och kvalitetssäkring.

```csharp
using (var reader = new BarCodeReader(generator.GenerateBarCodeImage(), DecodeType.DataMatrix))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine("DataMatrixExtendedCodetext:" + result.CodeText);
}
```

Om allt är korrekt konfigurerat kommer konsolen att skriva ut exakt den utökade kodtext du byggde tidigare.

## Vanliga fallgropar och felsökning

| Problem | Orsak | Lösning |
|---------|-------|---------|
| Streckkoden läses inte | X‑dimension för låg | Öka `XDimension.Pixels` (t.ex., 4 → 6) |
| Förvrängda tecken | Fel ECI‑kodning | Säkerställ att `ECIEncodings.UTF8` matchar teckenuppsättningen |
| Filen sparas inte | Ogiltig sökväg | Använd en absolut sökväg eller säkerställ att mappen finns |
| Licensundantag | Provperioden har gått ut | Applicera en temporär eller full licens (se FAQ) |

## Vanliga frågor

### Q1: Vad är Aspose.BarCode för .NET?
A1: Aspose.BarCode för .NET är ett kraftfullt bibliotek som gör det möjligt för utvecklare att generera och känna igen ett brett utbud av streckkodssymboler, inklusive DataMatrix, QR, Code128 och mer.

### Q2: Var kan jag hitta dokumentationen för Aspose.BarCode för .NET?
A2: Du kan komma åt den fullständiga API‑referensen **[Aspose.BarCode .NET API reference](https://reference.aspose.com/barcode/net/)**.

### Q3: Finns det en gratis provversion av Aspose.BarCode för .NET?
A3: Ja, en gratis provversion kan laddas ner från **[Aspose.BarCode free trial download](https://releases.aspose.com/)**.

### Q4: Hur får jag en temporär licens för testning?
A4: Temporära licenser tillhandahålls för utvärderingsändamål och kan begäras via **[Aspose temporary license request page](https://purchase.aspose.com/temporary-license/)**.

### Q5: Var kan jag få support eller ställa frågor om Aspose.BarCode för .NET?
A5: Det officiella Aspose.BarCode‑forumet är den bästa platsen för att få hjälp: **[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)**.

---

**Senast uppdaterad:** 2026-09-23  
**Testat med:** Aspose.BarCode 24.11 för .NET  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man genererar DataMatrix‑streckkoder med Aspose.BarCode för .NET – Steg‑för‑steg‑guide](/barcode/net/datamatrix-barcode-configuration/)
- [Generera en DataMatrix‑streckkod i ASCII‑läge med Aspose.BarCode för .NET (C#)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Generera Aztec‑streckkod med textkodning med Aspose.BarCode för .NET](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}