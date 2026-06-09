---
date: 2026-06-09
description: Lär dig hur du genererar DataMatrix-streckkoder och sparar PNG med C40-kodning
  med Aspose.BarCode – fullständig guide för .NET Core-streckkodsgenerering.
keywords:
- how to generate datamatrix
- barcode generation .net core
- datamatrix c40 png
linktitle: DataMatrix-kodningsläge (C40)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  headline: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  type: TechArticle
- description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  name: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  steps:
  - name: Define the Directory Path
    text: Set the folder where the PNG image will be stored. Replace the placeholder
      with an actual path on your machine.
  - name: Set Up Barcode Generation
    text: Create a `BarcodeGenerator` instance, specify `EncodeTypes.DataMatrix`,
      and provide the data you want to encode.
  - name: Customize Barcode
    text: Configure the X‑dimension (pixel width of the modules) and switch the encoding
      mode to C40.
  - name: Save the Barcode Image
    text: Finally, save the generated barcode as a PNG file. This is the concrete
      answer to **how to save png** with Aspose.BarCode. When you run the program,
      you’ll find `DataMatrixEncodeModeC40.png` in the folder you specified, ready
      to be used in reports, labels, or web pages.
  type: HowTo
- questions:
  - answer: C40 is a compact alphanumeric encoding scheme for DataMatrix symbols,
      ideal for text that includes letters, numbers, and a limited set of special
      characters.
    question: What is DataMatrix Encoding Mode (C40)?
  - answer: You can find the documentation [here](https://reference.aspose.com/barcode/net/).
      It provides detailed guidance on all barcode types and encoding options.
    question: Where can I find the Aspose.BarCode for .NET documentation?
  - answer: Yes, the library supports a wide range of .NET versions, from .NET Framework
      4.5+ to .NET 6 and later.
    question: Is Aspose.BarCode for .NET compatible with all .NET versions?
  - answer: Yes, you can explore a free trial of Aspose.BarCode for .NET by visiting
      [this link](https://releases.aspose.com/). It allows you to test the library’s
      features and capabilities.
    question: Can I try Aspose.BarCode for .NET before purchasing?
  - answer: You can find a supportive community and access support for Aspose.BarCode
      for .NET on the [Aspose forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Hur du genererar DataMatrix PNG med C40 med Aspose.BarCode
url: /sv/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Master DataMatrix-kodningsläge (C40) med Aspose.BarCode för .NET

## Introduktion

I den här handledningen kommer du att lära dig **hur man genererar datamatrix** streckkoder och sparar dem som PNG‑filer med C40‑kodningsläget i Aspose.BarCode för .NET. Oavsett om du bygger ett lagersystem, en fraktetikett‑generator eller någon annan lösning som kräver kompakta, högdensitets‑symboler, ger dig kunskapen om C40 mindre symboler utan att kompromissa med läsbarheten. Vi går igenom varje steg – från att konfigurera miljön till att producera den slutgiltiga PNG‑filen – så att du kan integrera koden omedelbart i ditt projekt.

## Snabba svar
- **Vad betyder “hur man genererar datamatrix”?** Skapa en DataMatrix streckkod bild programatiskt.  
- **Vilket kodningsläge behandlas?** DataMatrix C40, ett effektivt alfanumeriskt schema.  
- **Behöver jag en licens?** En gratis provversion fungerar för testning; en kommersiell licens krävs för produktion.  
- **Kan jag köra detta på .NET Core?** Ja, Aspose.BarCode stöder fullt ut .NET Core, .NET 5, .NET 6 och senare.  
- **Vilket filformat genereras?** PNG – ett förlustfritt, webbvänligt bildformat.

## Så genererar du DataMatrix med C40‑kodning

Läs in dina data, konfigurera generatorn och anropa `Save` – det är hela arbetsflödet i tre koncisa steg. Klassen `BarcodeGenerator` hanterar symbolskapandet, medan enum‑värdet `BarCodeImageFormat.Png` instruerar Aspose.BarCode att skriva resultatet som en PNG‑fil. `Save` sparar den genererade streckkodsbilden till den angivna filsökvägen i det valda formatet. Detta direkt‑svars‑stycke ger dig en helhetslösning innan vi dyker ner i varje kodrad.

## Vad är DataMatrix‑kodningsläge (C40)?

`DataMatrixEncodeMode` är en uppräkning som specificerar vilket kodningsschema Aspose.BarCode ska använda för DataMatrix‑symboler. Alternativet `DataMatrixEncodeMode.C40` väljer den alfanumeriska C40‑kodningen, som packar bokstäver, siffror och ett begränsat antal skiljetecken i färre moduler, vilket minskar den totala symbolstorleken samtidigt som läsbarheten för typisk lagertext bibehålls. Detta effektiva schema är idealiskt när du behöver koda alfanumerisk data i en kompakt form.

## Varför använda Aspose.BarCode för .NET?

Aspose.BarCode erbjuder **30+ konfigurerbara parametrar** för dimensioner, felkorrigeringsnivåer och kodningslägen, och stöder **50+ bild‑ och streckkodformat**. Biblioteket körs på **.NET Framework 4.5+, .NET Core 2.0+, .NET 5/6+**, vilket ger generering utan beroenden som fungerar på servrar, stationära datorer och mobila enheter.

## Förutsättningar

Innan vi dyker ner i koden, se till att du har följande:

1. **.NET‑utvecklingsmiljö** – Visual Studio, Rider eller någon IDE som stödjer C#.  
2. **Aspose.BarCode för .NET** – installerad via NuGet eller den officiella installationsprogrammet. Se [documentation](https://reference.aspose.com/barcode/net/) för detaljer.  
3. **Grundläggande C#‑kunskaper** – du bör vara bekväm med namnrymder, klasser och using‑satser.  
4. **Skrivbehörig mapp** – en katalog på din maskin där PNG‑filen kommer att sparas.

## Importera nödvändiga namnrymder

Klassen `BarcodeGenerator` är startpunkten för att skapa någon streckkod som helst. Lägg till den nödvändiga namnrymden högst upp i din C#‑källfil så att du kan komma åt genererings‑API‑et:

```csharp
using Aspose.BarCode.Generation;
```

## Steg‑för‑steg streckkodsgenerering

Nedan följer en **steg‑för‑steg streckkod**‑genomgång. Varje steg förklaras på enkel svenska, och de ursprungliga platshållarna behålls oförändrade för enkel kopiering och inklistring.

### Steg 1: Definiera katalogsökvägen
Ange den mapp där PNG‑bilden ska lagras. Ersätt platshållaren med en faktisk sökväg på din maskin.

```csharp
string path = "Your Directory Path";
```

### Steg 2: Ställ in streckkodsgenerering
Skapa en `BarcodeGenerator`‑instans, specificera `EncodeTypes.DataMatrix` och ange de data du vill koda.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### Steg 3: Anpassa streckkoden
Konfigurera X‑dimensionen (pixelbredden på modulerna) och byt kodningsläget till C40.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### Steg 4: Spara streckkodsbilden
Spara slutligen den genererade streckkoden som en PNG‑fil. Detta är det konkreta svaret på **hur man sparar png** med Aspose.BarCode.

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

När du kör programmet hittar du `DataMatrixEncodeModeC40.png` i den mapp du angav, redo att användas i rapporter, etiketter eller webbsidor.

## Vanliga problem & tips

- **Ogiltig sökväg** – Säkerställ att katalogen finns och att du har skrivrättigheter; annars kommer `gen.Save` att kasta ett undantag.  
- **Fel kodningsläge** – Om du behöver koda tecken utanför C40‑uppsättningen, byt till `DataMatrixEncodeMode.Auto` eller ett annat lämpligt läge.  
- **Bildstorlek** – Justera `XDimension.Pixels` för att öka eller minska den totala streckkodsstorleken utan att påverka läsbarheten.

## Vanliga frågor

**Q: Vad är DataMatrix‑kodningsläge (C40)?**  
A: C40 är ett kompakt alfanumeriskt kodningsschema för DataMatrix‑symboler, idealiskt för text som innehåller bokstäver, siffror och ett begränsat antal specialtecken.

**Q: Var kan jag hitta dokumentationen för Aspose.BarCode för .NET?**  
A: Du kan hitta dokumentationen [here](https://reference.aspose.com/barcode/net/). Den ger detaljerad vägledning om alla streckkodstyper och kodningsalternativ.

**Q: Är Aspose.BarCode för .NET kompatibel med alla .NET‑versioner?**  
A: Ja, biblioteket stöder ett brett spektrum av .NET‑versioner, från .NET Framework 4.5+ till .NET 6 och senare.

**Q: Kan jag prova Aspose.BarCode för .NET innan jag köper?**  
A: Ja, du kan utforska en gratis provversion av Aspose.BarCode för .NET genom att besöka [this link](https://releases.aspose.com/). Den låter dig testa bibliotekets funktioner och möjligheter.

**Q: Var kan jag få support för Aspose.BarCode för .NET?**  
A: Du kan hitta ett stödjande community och få support för Aspose.BarCode för .NET på [Aspose forum](https://forum.aspose.com/c/barcode/13).

## Slutsats

Genom att följa denna **steg‑för‑steg streckkod**‑guide vet du nu exakt **hur man genererar datamatrix** streckkoder och sparar dem som PNG‑filer med C40‑kodningsläget i Aspose.BarCode för .NET. Detta tillvägagångssätt ger dig full kontroll över streckkodens utseende, storlek och datarepresentation, vilket gör det enkelt att bädda in högkvalitativa streckkoder i vilken .NET‑applikation som helst.

---

**Senast uppdaterad:** 2026-06-09  
**Testad med:** Aspose.BarCode 24.11 för .NET  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [DataMatrix‑kodning i byte med Aspose.BarCode för .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Master DataMatrix‑kodning i ASCII med Aspose.BarCode för .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Hur man genererar DataMatrix‑streckkoder (ECC 200) med Aspose.BarCode för .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}