---
date: 2026-08-02
description: Steg‑för‑steg‑guide om hur man läser DataMatrix streckkod C# och genererar
  streckkodbild C# med Aspose.BarCode for .NET med automatisk kodning.
keywords:
- how to read datamatrix
- read barcode from file
- how to generate datamatrix
- datamatrix encoding auto
lastmod: 2026-08-02
linktitle: DataMatrix kodningsläge (Auto)
og_description: Lär dig hur du läser DataMatrix streckkod C# och genererar den i Auto‑läge
  med Aspose.BarCode for .NET. Denna handledning täcker installation, kod och felsökning.
og_image_alt: 'Guide: Read and generate DataMatrix barcode in C# with Aspose.BarCode'
og_title: Hur man läser DataMatrix streckkod C# – Auto‑läge
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: Step‑by‑step guide on how to read DataMatrix barcode C# and generate
    barcode image C# using Aspose.BarCode for .NET with auto encoding.
  headline: How to read DataMatrix barcode C# – Auto mode
  type: TechArticle
- questions:
  - answer: It allows Aspose.BarCode to automatically select the optimal encoding
      method for the provided data, simplifying the **how to generate datamatrix**
      process.
    question: What is DataMatrix encoding mode "Auto"?
  - answer: Yes – adjust `generator.Parameters.Barcode.XDimension.Pixels` to change
      module size.
    question: Can I customize the dimensions of the generated barcode?
  - answer: Absolutely. Purchase a license from the [website](https://purchase.aspose.com/buy).
    question: Is Aspose.BarCode for .NET suitable for commercial use?
  - answer: Yes, you can explore Aspose.BarCode with a free trial from [this link](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Aspose.BarCode supports UTF‑8, ASCII, and other ECI encodings; set the
      desired value via `ECIEncoding`.
    question: What encoding options are available for DataMatrix barcodes?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- C# barcode generation
title: Hur man läser DataMatrix streckkod C# – Auto‑läge
url: /sv/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man läser DataMatrix-streckkod C# – Auto‑läge

I dagens snabbrörliga digitala värld är **hur man läser datamatrix** snabbt och pålitligt avgörande för lagerhantering, säker dokumenthantering och många andra företags scenarier. Denna handledning guidar dig genom att generera en DataMatrix‑streckkod i *Auto*‑läge med Aspose.BarCode för .NET och visar sedan hur du läser tillbaka streckkoden i C#. Oavsett om du följer en streckkodshandledningsguide eller behöver ett färdigt kodexempel, avslutar du med en produktionsklar lösning som du kan lägga in i vilket .NET‑projekt som helst.

## Snabba svar
- **Vad gör “Auto”‑läget?** Det låter Aspose.BarCode automatiskt välja det bästa kodningsschemat för dina data.  
- **Vilket bibliotek krävs?** Aspose.BarCode för .NET (gratis provversion tillgänglig).  
- **Kan jag läsa streckkoden i samma app?** Ja – använd `BarCodeReader` med `DecodeType.DataMatrix`.  
- **Behöver jag en licens för produktion?** En kommersiell licens krävs för produktionsbruk.  
- **Stödda .NET‑versioner?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  

`BarCodeReader` är Aspose.BarCode:s klass för att skanna bilder och hämta streckkodsinformation.

## Vad är läsning av DataMatrix‑streckkod i C#?
Att läsa en DataMatrix‑streckkod i C# innebär att avkoda den tvådimensionella matrisen av svarta och vita moduler tillbaka till den ursprungliga texten eller datan. Aspose.BarCode abstraherar den lågnivå bildbehandlingen, så att du kan fokusera på affärslogik medan biblioteket automatiskt hanterar felkorrigering, val av symbolstorlek och Unicode‑stöd.

## Varför använda Aspose.BarCode för att generera streckkodsbild i C#?
Aspose.BarCode väljer automatiskt den optimala kodningen, stöder **30+ streckkodssymboler**, och kan generera DataMatrix‑symboler upp till **1558 × 1558 moduler** – mycket större än de flesta konkurrenter. Det körs på Windows, Linux och macOS utan inhemska beroenden, vilket ger dig ett enda, plattformsoberoende API för både generering och läsning.

## Förutsättningar

1. **.NET‑miljö** – Installera den senaste .NET‑runtime från [.NET‑webbplatsen](https://dotnet.microsoft.com/download/dotnet).  
2. **Aspose.BarCode för .NET** – Ladda ner biblioteket från [webbplatsen](https://releases.aspose.com/barcode/net/).  

## Importera namnrymder
`Aspose.BarCode`‑namnrymden innehåller alla klasser du behöver för streckkodsskapande och läsning. Importera den högst upp i din fil innan någon annan kod.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Nu när namnrymderna är på plats, låt oss gå igenom koden steg för steg.

## Steg 1: Ange katalogsökvägen
Välj en mapp där den genererade PNG‑filen (eller något annat stödd format) ska sparas. Denna sökväg kan vara absolut eller relativ till ditt projekt.

```csharp
string path = "Your Directory Path";
```

Byt ut `"Your Directory Path"` mot den mapp du föredrar. Att hålla utdata‑mappen konfigurerbar gör handledningen återanvändbar i olika miljöer.

## Steg 2: Skapa en DataMatrix‑streckkod i Auto‑läge
`DataMatrixEncodeMode.Auto` instruerar generatorn att automatiskt välja det optimala kodningsschemat för de angivna data.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose常に先を行く"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Auto;
    generator.Parameters.Barcode.DataMatrix.ECIEncoding = ECIEncodings.UTF8;
    Bitmap bitmap = generator.GenerateBarCodeImage();
}
```

Byt gärna ut exempeltexten mot vilken sträng du än behöver **hur man genererar datamatrix** för. Auto‑läget kommer automatiskt att växla mellan Base‑256, ASCII eller andra scheman för att uppnå den minsta möjliga symbolen.

## Steg 3: Läs streckkoden (läs DataMatrix‑streckkod i C#)
`BarCodeReader` är Aspose.BarCode:s klass för att skanna bilder och hämta streckkodsinformation. Den stöder läsning från strömmar, filer och bitmap‑objekt, vilket gör den idealisk för scenarier med **läsa streckkod från fil**.

```csharp
using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
{
    reader.ReadBarCodes();
    Console.WriteLine(reader.FoundBarCodes[0].CodeText);
}
```

Detta kodsnutt avkodar bilden vi just genererade och skriver ut den ursprungliga texten till konsolen, vilket demonstrerar en fullständig rundresa från generering till läsning.

## Vanliga problem och lösningar

| Issue | Cause | Fix |
|-------|-------|-----|
| **Ingen streckkod upptäckt** | Bildens upplösning för låg | Öka `XDimension.Pixels` (t.ex. till 6) |
| **Felaktiga tecken** | Fel ECI‑kodning | Ställ in `ECIEncoding` så att den matchar dina data (UTF‑8, ASCII, etc.) |
| **Undantag på `ReadBarCodes`** | Bitmap har frigjorts innan läsning | Behåll `Bitmap`‑instansen levande tills efter läsning |

## Vanliga frågor

**Q: Vad är DataMatrix‑kodningsläge "Auto"?**  
A: Det låter Aspose.BarCode automatiskt välja den optimala kodningsmetoden för de tillhandahållna data, vilket förenklar processen **hur man genererar datamatrix**.

**Q: Kan jag anpassa dimensionerna på den genererade streckkoden?**  
A: Ja – justera `generator.Parameters.Barcode.XDimension.Pixels` för att ändra modulstorlek.

**Q: Är Aspose.BarCode för .NET lämplig för kommersiell användning?**  
A: Absolut. Köp en licens från [webbplatsen](https://purchase.aspose.com/buy).

**Q: Finns det en gratis provversion tillgänglig?**  
A: Ja, du kan utforska Aspose.BarCode med en gratis provversion via [denna länk](https://releases.aspose.com/).

**Q: Vilka kodningsalternativ finns tillgängliga för DataMatrix‑streckkoder?**  
A: Aspose.BarCode stöder UTF‑8, ASCII och andra ECI‑kodningar; ställ in önskat värde via `ECIEncoding`.

## Slutsats

Du har nu ett komplett, produktionsklart exempel som **läser DataMatrix‑streckkod i C#**, genererar streckkoden i Auto‑läge och verifierar resultatet – allt med Aspose.BarCode för .NET. Experimentera med olika texter, storlekar och ECI‑inställningar för att passa ditt specifika scenario, och hänvisa till den officiella [dokumentationen](https://reference.aspose.com/barcode/net/) för djupare anpassning.

---

**Senast uppdaterad:** 2026-08-02  
**Testat med:** Aspose.BarCode 24.12 for .NET  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man läser DataMatrix‑streckkoder med Aspose.BarCode för .NET](/barcode/net/datamatrix-barcode-reading/)
- [DataMatrix strukturerad tilläggskonfiguration med Aspose.BarCode för .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)
- [DataMatrix‑läsarprogrammering med Aspose.BarCode för .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-reader-programming/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}