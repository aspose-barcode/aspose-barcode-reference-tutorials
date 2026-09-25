---
date: 2026-08-17
description: Lär dig hur du skapar datamatrix barcode aspose med Aspose.BarCode för
  .NET – idealiskt för barcode generation, inventory management och C# barcode generator-projekt.
keywords:
- create datamatrix barcode aspose
- datamatrix barcode error correction
- barcode generation with visual studio
lastmod: 2026-08-17
linktitle: DataMatrix ECC 000-140-konfiguration
og_description: Skapa datamatrix barcode aspose med Aspose.BarCode för .NET – en snabb,
  högpresterande lösning för inventory management och C# barcode-projekt.
og_image_alt: Guide showing C# code to generate DataMatrix ECC 000-140 barcode with
  Aspose.BarCode
og_title: Skapa datamatrix barcode aspose med Aspose.BarCode för .NET
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Learn how to create datamatrix barcode aspose using Aspose.BarCode
    for .NET – ideal for barcode generation inventory management and C# barcode generator
    projects.
  headline: How to create datamatrix barcode aspose with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Yes. The library is fully cross‑platform and runs on .NET 5+, .NET 6+,
      and .NET Core on Linux without additional dependencies.
    question: Can I use Aspose.BarCode for .NET on Linux servers?
  - answer: You can reuse a single `BarcodeGenerator` instance in a loop; each call
      to `Save` re‑renders the image in roughly 40‑60 ms, making it suitable for generating
      thousands of labels per minute.
    question: How does the library handle large batches of barcodes?
  - answer: No. Setting `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc140`
      automatically applies the correct error‑correction algorithm.
    question: Do I need to encode the data manually for ECC 140?
  - answer: The free trial provides full feature access, including ECC 140, but adds
      a watermark to the generated images. Apply a license for production to remove
      the watermark.
    question: Is a trial version sufficient for development?
  - answer: Absolutely. Use `generator.Parameters.Barcode.Color` and `generator.Parameters.Barcode.BackColor`
      to match your branding.
    question: Can I customize the barcode’s colors?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- C# barcode generation
- inventory management
title: Hur man skapar datamatrix barcode aspose med Aspose.BarCode
url: /sv/net/datamatrix-barcode-configuration/datamatrix-ecc-000-140-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar datamatrix streckkod aspose med Aspose.BarCode

I modern mjukvara för leveranskedjan behöver du ofta **skapa datamatrix streckkod aspose** snabbt och pålitligt. Den här handledningen guidar dig genom att generera en DataMatrix ECC 000‑140-symbol med Aspose.BarCode för .NET, ett bibliotek som hanterar den tunga lyftningen av kodning, felkorrigering och bildrendering. I slutet av guiden har du ett färdigt C#‑kodexempel som kan infogas i vilket .NET‑lagerhanteringsprojekt som helst.

## Snabba svar
- **Vad är det primära biblioteket?** Aspose.BarCode for .NET  
- **Vilken streckkodstyp täcks?** DataMatrix ECC 000‑140  
- **Vilket språk används?** C# (C Sharp)  
- **Behöver jag en licens?** En gratis provversion finns tillgänglig; en licens krävs för produktion  
- **Typisk implementeringstid?** Ungefär 10‑15 minuter för en grundläggande generator  

## Vad är DataMatrix ECC 000‑140?
DataMatrix är en tvådimensionell streckkod som lagrar stora datamängder i en kompakt kvadrat. **ECC 000‑140** felkorrigeringsnivå kan återställa upp till 140 % av skadade kodord, vilket gör den perfekt för tuffa lagerförhållanden där etiketter kan repas eller smetas.

## Varför välja Aspose.BarCode för .NET?
Aspose.BarCode för .NET erbjuder ett omfattande, högpresterande API som förenklar skapandet av streckkoder över många symboler, med inbyggd felkorrigering, automatisk storleksanpassning och omfattande plattformsstöd, vilket gör det idealiskt för företagsnivå lager- och märkningslösningar.

- **Robust API:** Hanterar 30+ streckkodssymboler och tillämpar automatiskt kodningsregler.  
- **Cross‑platform:** Körs på Windows, macOS och Linux utan inhemska beroenden.  
- **High performance:** Genererar en 200 × 200 pixel DataMatrix på under 50 ms på en typisk 2,5 GHz‑CPU, vilket möjliggör högkapacitets märkningslinjer.  

## Förutsättningar
Innan du börjar, se till att du har:

1. **Visual Studio** – någon nyare version (Community, Professional eller Enterprise).  
2. **Aspose.BarCode for .NET** – ladda ner den från [download link](https://releases.aspose.com/barcode/net/). Du kan också besöka [this link](https://releases.aspose.com/) för ytterligare resurser.  
3. **Ett .NET‑projekt** – redo att referera Aspose.BarCode‑assemblyn.  

## Importera namnrymder
I din C#‑fil, lägg till den nödvändiga using‑direktivet så att du kan komma åt streckkodsklasserna.

```csharp
using Aspose.BarCode.Generation;
```

**Klassen `BarcodeGenerator` är Aspose.BarCode:s kärnmotor för att skapa streckkodbilder.**  
**Klassen `BarcodeGenerator` är Aspose.BarCode:s kärnmotor som skapar och konfigurerar streckkodbilder.**

```csharp
using Aspose.BarCode.Generation;
```

## Generering av streckkoder för lagerhantering
Föreställ dig att du behöver märka tusentals pallar i ett distributionscenter. Genom att generera DataMatrix ECC 000‑140‑streckkoder kan du bädda in produkt‑ID:n, batch‑nummer och utgångsdatum i en enda, felresistent symbol som handhållna skannrar läser omedelbart, vilket minskar manuella inmatningsfel med upp till 95 %.

## Hur man skapar datamatrix streckkod aspose i C#
Läs in data, konfigurera generatorn och spara bilden – allt i tre koncisa steg. `BarcodeGenerator` väljer automatiskt optimal modulstorlek och tillämpar ECC 140‑korrektionsnivån, så du behöver inte själv beräkna kontrollsummor, snabbt och effektivt.

### Steg 1: definiera utdatamappen
Välj en mapp där PNG‑filen ska skrivas. Sökvägen måste finnas innan du anropar `Save`.

```csharp
string path = "Your Directory Path";
```

### Steg 2: skapa streckkodsgeneratorn
Instansiera `BarcodeGenerator`, sätt symbologin till DataMatrix, ange nyttolasten och välj den högsta felkorrigeringsnivån.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Set the XDimension in Pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set DataMatrix ECC to 140
    gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;

    // Save the generated barcode image
    gen.Save($"{path}DataMatrixEcc000140.png", BarCodeImageFormat.Png);
}
```

I detta kodexempel:

* Välj **DataMatrix** som streckkodstyp.  
* Ange ett exempelvärde (`"Åspóse.Barcóde©"`).  
* Ställ in **XDimension** för att kontrollera modulstorleken (4 pixlar här).  
* Välj den högsta felkorrigeringsnivån (**ECC 140**).  
* Spara resultatet som en PNG‑fil.

## Vanliga problem och lösningar
| Problem | Lösning |
|-------|----------|
| **Ogiltig sökväg** | Se till att `path` slutar med en katalogseparator (`\` eller `/`) och att mappen finns. |
| **Ej stödda tecken** | DataMatrix stöder UTF‑8; undvik kontrolltecken och använd korrekt kodning. |
| **Licens inte tillämpad** | `Aspose.BarCode.License`‑klassen tillämpar en kommersiell licens för att låsa upp full funktionalitet. Anropa den innan du genererar någon streckkod. |

## Vanliga frågor

**Q: Kan jag använda Aspose.BarCode för .NET på Linux‑servrar?**  
A: Ja. Biblioteket är helt plattformsoberoende och körs på .NET 5+, .NET 6+ och .NET Core på Linux utan ytterligare beroenden.

**Q: Hur hanterar biblioteket stora batcher av streckkoder?**  
A: Du kan återanvända en enda `BarcodeGenerator`‑instans i en loop; varje anrop till `Save` renderar om bilden på ungefär 40‑60 ms, vilket gör det lämpligt för att generera tusentals etiketter per minut.

**Q: Måste jag koda data manuellt för ECC 140?**  
A: Nej. Att sätta `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc140` tillämpar automatiskt den korrekta felkorrigeringsalgoritmen.

**Q: Är en provversion tillräcklig för utveckling?**  
A: Den kostnadsfria provversionen ger full åtkomst till funktioner, inklusive ECC 140, men lägger till ett vattenmärke på de genererade bilderna. Använd en licens för produktion för att ta bort vattenmärket.

**Q: Kan jag anpassa streckkodens färger?**  
A: Absolut. Använd `generator.Parameters.Barcode.Color` och `generator.Parameters.Barcode.BackColor` för att matcha ditt varumärke.

---

**Senast uppdaterad:** 2026-08-17  
**Testad med:** Aspose.BarCode 24.11 för .NET  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man genererar DataMatrix‑streckkoder (ECC 200) med Aspose.BarCode för .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Behärska DataMatrix‑kodning i ASCII med Aspose.BarCode för .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Hur man läser DataMatrix‑streckkoder med Aspose.BarCode för .NET](/barcode/net/datamatrix-barcode-reading/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}