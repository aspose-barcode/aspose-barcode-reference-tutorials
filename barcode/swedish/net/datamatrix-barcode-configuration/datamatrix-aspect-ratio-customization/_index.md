---
date: 2026-05-30
description: Lär dig hur du skapar streckkod PNG med ett anpassat DataMatrix-bildförhållande
  med Aspose.BarCode för .NET. Steg-för-steg-guide för streckkodsgenerering och anpassning
  av storlek.
keywords:
- create barcode png
- generate datamatrix barcode
- asp.net barcode generation
- barcode generation visual studio
linktitle: Anpassning av DataMatrix bildförhållande
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  headline: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  name: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  steps:
  - name: Set Up Your Project
    text: Create a new console or Windows Forms project in Visual Studio and add a
      reference to the Aspose.BarCode DLL.
  - name: Initialize a Barcode Generator
    text: 'Instantiate it with the DataMatrix symbology and the data you want to encode:
      `BarcodeGenerator` creates a barcode image from the specified symbology and
      data. > This line creates a generator ready to produce a DataMatrix barcode
      that contains the sample text.'
  - name: Customize Aspect Ratio and Save PNG Files
    text: 'Now you can change the **aspect ratio** and save each version as a PNG
      image: `AspectRatio` sets the width‑to‑height proportion of the DataMatrix modules.
      `Save` writes the generated barcode image to a file in the chosen format. -
      The first call creates a square‑proportioned barcode (`AspectRatio = '
  type: HowTo
- questions:
  - answer: Yes, many 2‑D barcodes (e.g., QR, PDF417) support aspect‑ratio adjustments
      through their specific parameter objects.
    question: Can I customize the aspect ratio of other barcode types using Aspose.BarCode
      for .NET?
  - answer: Yes, you can access a free trial of Aspose.BarCode for .NET [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: You can purchase a license on the Aspose website [here](https://purchase.aspose.com/buy).
    question: Where can I purchase a license for Aspose.BarCode for .NET?
  - answer: Yes, it works with .NET Framework 4.x, .NET Core 3.1+, and the latest
      .NET releases.
    question: Is Aspose.BarCode for .NET compatible with different .NET Framework
      versions?
  - answer: Absolutely – PNG, JPEG, BMP, GIF, TIFF, SVG, and PDF are all supported
      out of the box.
    question: Can I generate barcodes in different formats with Aspose.BarCode for
      .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Skapa streckkod PNG – DataMatrix bildförhållande – Aspose.BarCode
url: /sv/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa barcode PNG – DataMatrix bildförhållande – Aspose.BarCode

Att generera en **barcode PNG** med ett anpassat DataMatrix‑bildförhållande är ett vanligt krav när du behöver **skapa barcode PNG**‑filer som passar specifika layoutbegränsningar. I den här handledningen går vi igenom de exakta stegen för att **skapa barcode PNG**‑filer med Aspose.BarCode för .NET, förklarar varför du kan vilja justera bildförhållandet och visar hur du finjusterar resultatet för din applikation.

## Snabba svar
- **Vad styr “aspect ratio”?** Det definierar bredd‑till‑höjd‑förhållandet för DataMatrix‑modulerna.  
- **Kan jag exportera PNG, JPEG eller SVG?** Ja – `Save`‑metoden stödjer PNG, JPEG, BMP, GIF, TIFF, SVG och PDF.  
- **Behöver jag en licens för den här funktionen?** En gratis provversion fungerar för utveckling; en full licens krävs för produktion.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.x, .NET Core 3.1+, .NET 5/6/7.  
- **Hur många aspect‑ratio‑värden är giltiga?** Alla positiva flyttal; typiska värden är 0.5 – 2.0.

## Vad är en DataMatrix‑streckkod och varför justera dess bildförhållande?
En DataMatrix‑streckkod är en tvådimensionell matris‑kod som lagrar stora mängder data i en kompakt kvadrat. Att justera **aspect ratio** låter dig sträcka eller komprimera modulerna horisontellt, vilket är användbart när du måste passa streckkoden i smala kolumner eller breda etiketter utan att kompromissa med skanningspålitlighet.

## Varför använda Aspose.BarCode för att skapa barcode PNG?
Aspose.BarCode stödjer **7 bildformat** — PNG, JPEG, BMP, GIF, TIFF, SVG och PDF — och kan bearbeta **50+ in‑ och utdataformat** i minnet, hantera dokument med hundratals sidor utan att ladda hela filen. Biblioteket erbjuder ett flytande API som låter dig generera en DataMatrix‑streckkod i en enda kodrad, vilket garanterar pixel‑perfekt rendering och full .NET‑kompatibilitet.

## Förutsättningar

Innan vi börjar anpassa DataMatrix‑bildförhållanden, se till att du har följande förutsättningar på plats:

1. **Visual Studio** – vilken nyare version som helst räcker.  
2. **Aspose.BarCode for .NET** – ladda ner den [here](https://releases.aspose.com/barcode/net/).  
3. Du kan också utforska andra Aspose‑produktutgåvor [here](https://releases.aspose.com/).  
4. **.NET Framework / .NET Core** – ditt projekt måste rikta sig mot en stödd version.

## Importera namnrymder

Först måste du importera den nödvändiga namnrymden i ditt C#‑projekt:

`using Aspose.BarCode.Generation;` importerar namnrymden som innehåller klasserna för streckkodsgenerering.  

```csharp
using Aspose.BarCode.Generation;
```

> **Pro tip:** Behåll detta `using`‑uttalande högst upp i din fil så att `BarcodeGenerator`‑klassen alltid är tillgänglig.

## Hur skapar man barcode PNG med anpassat bildförhållande?

Läs in `BarcodeGenerator`, ange DataMatrix‑typen, justera egenskapen `AspectRatio` och anropa `Save`. Detta enkla‑rad‑mönster skapar en barcode PNG som respekterar det förhållande du anger, och biblioteket hanterar automatiskt modul‑skalning och tysta zoner.

`BarcodeGenerator` skapar en streckkodsbild från den angivna symboliken och data.

### Steg 1: Ställ in ditt projekt
Skapa ett nytt konsol‑ eller Windows Forms‑projekt i Visual Studio och lägg till en referens till Aspose.BarCode‑DLL‑filen.

### Steg 2: Initiera en Barcode Generator
Instansiera den med DataMatrix‑symboliken och den data du vill koda:

`BarcodeGenerator` skapar en streckkodsbild från den angivna symboliken och data.  

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> Denna rad skapar en generator som är redo att producera en DataMatrix‑streckkod som innehåller exempeltexten.

### Steg 3: Anpassa bildförhållande och spara PNG‑filer
Nu kan du ändra **aspect ratio** och spara varje version som en PNG‑bild:

`AspectRatio` anger bredd‑till‑höjd‑förhållandet för DataMatrix‑modulerna.  
`Save` skriver den genererade streckkodsbilden till en fil i det valda formatet.  

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- Det första anropet skapar en kvadratiskt proportionerad streckkod (`AspectRatio = 1`).  
- Det andra anropet komprimerar streckkoden horisontellt (`AspectRatio = 0.5`), vilket ger ett bredare utseende.

Du har nu två **barcode PNG**‑filer med olika bildförhållanden, redo att användas i rapporter, etiketter eller UI‑element.

## Vanliga problem & lösningar
| Problem | Lösning |
|---------|----------|
| **Genererad bild är suddig** | Öka `Resolution`‑parametern innan du sparar (`gen.Parameters.ImageResolution = 300`). |
| **Streckkoden skannar inte** | Se till att bildförhållandet ligger inom 0.5 – 2.0 och behåll tillräcklig tyst zon (`gen.Parameters.Barcode.CodeTextParameters.Margin`). |
| **Fel i filsökväg** | Använd `Path.Combine` för att bygga utdata‑sökvägen och verifiera att mappen finns. |

## Vanliga frågor

**Q: Kan jag anpassa bildförhållandet för andra streckkodstyper med Aspose.BarCode för .NET?**  
A: Ja, många 2‑D‑streckkoder (t.ex. QR, PDF417) stödjer justering av bildförhållande via deras specifika parameterobjekt.

**Q: Finns det en gratis provversion av Aspose.BarCode för .NET?**  
A: Ja, du kan få åtkomst till en gratis provversion av Aspose.BarCode för .NET [here](https://releases.aspose.com/).

**Q: Var kan jag köpa en licens för Aspose.BarCode för .NET?**  
A: Du kan köpa en licens på Aspose‑webbplatsen [here](https://purchase.aspose.com/buy).

**Q: Är Aspose.BarCode för .NET kompatibel med olika .NET Framework‑versioner?**  
A: Ja, den fungerar med .NET Framework 4.x, .NET Core 3.1+ och de senaste .NET‑utgåvorna.

**Q: Kan jag generera streckkoder i olika format med Aspose.BarCode för .NET?**  
A: Absolut – PNG, JPEG, BMP, GIF, TIFF, SVG och PDF stöds alla direkt.

## Slutsats

Att anpassa **aspect ratio** för en DataMatrix‑streckkod och **skapa barcode PNG**‑filer är enkelt med Aspose.BarCode för .NET. Genom att följa stegen ovan kan du generera perfekt dimensionerade streckkoder som uppfyller exakt layoutkrav för ditt projekt. Utforska ytterligare parametrar som `Resolution`, `Margin` och `Color` för att finjustera resultatet ytterligare, och överväg `generate datamatrix barcode`‑funktionerna när du bygger skanningsvänliga applikationer i Visual Studio.

För djupare utforskning, kolla in den officiella [documentation](https://reference.aspose.com/barcode/net/) eller gå med i communityn på [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13).

---

**Senast uppdaterad:** 2026-05-30  
**Testad med:** Aspose.BarCode 24.12 for .NET  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Generera DataMatrix‑streckkod – Pro‑guide med Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/)
- [Hur man genererar DataMatrix‑streckkoder (ECC 200) med Aspose.BarCode för .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Behärska DataMatrix‑kodning i ASCII med Aspose.BarCode för .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}