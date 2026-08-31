---
date: 2026-05-24
description: Lär dig hur du skapar aztec-streckkod .NET med Aspose.BarCode för .NET,
  med fokus på symbol‑lägena Auto, FullRange, Compact och Rune, med steg‑för‑steg‑vägledning.
keywords:
- create aztec barcode .net
- aztec symbol mode
- aspose barcode .net
linktitle: Exempel på Aztec-symbolläge
schemas:
- author: Aspose
  dateModified: '2026-05-24'
  description: Learn how to create aztec barcode .net using Aspose.BarCode for .NET,
    covering Auto, FullRange, Compact, and Rune symbol modes with step‑by‑step guidance.
  headline: Create Aztec Barcode .NET with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Aztec Symbol Mode determines how the library packs data into layers, affecting
      size, capacity, and readability.
    question: What is the purpose of Aztec Symbol Mode in barcode generation?
  - answer: Yes, simply assign a new string to the `CodeText` property before calling
      `Save`.
    question: Can I change the code text for Aztec barcodes in Aspose.BarCode for
      .NET?
  - answer: Yes, you can download a free trial version of Aspose.BarCode for .NET
      [here](https://releases.aspose.com/).
    question: Is there a free trial version of Aspose.BarCode for .NET available?
  - answer: You can refer to the complete documentation for Aspose.BarCode for .NET
      [here](https://reference.aspose.com/barcode/net/).
    question: Where can I find the full documentation for Aspose.BarCode for .NET?
  - answer: You can acquire a temporary license for Aspose.BarCode for .NET by visiting
      [this link](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Skapa Aztec-streckkod .NET med Aspose.BarCode
url: /sv/net/aztec-barcode-encoding/aztec-symbol-mode-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Behärska Aztec Symbolläge med Aspose.BarCode för .NET

Om du vill **create aztec barcode .net** snabbt och pålitligt, ger Aspose.BarCode för .NET dig ett fullständigt API som fungerar på .NET Framework, .NET Core och .NET 5/6+. I den här handledningen kommer vi att utforska de fyra Aztec Symbol Modes—Auto, FullRange, Compact och Rune—och visa exakt hur du växlar mellan dem och sparar resultatet som en bild. I slutet kommer du att kunna bädda in Aztec‑streckkoder i vilken .NET‑applikation som helst med bara några rader kod.

## Snabba svar
- **Vilket bibliotek genererar Aztec‑streckkoder i .NET?** Aspose.BarCode för .NET.  
- **Hur många symbollägen stöder Aztec?** Fyra: Auto, FullRange, Compact och Rune.  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för utvärdering; en kommersiell licens krävs för produktion.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ och .NET 6+.  
- **Kan jag exportera PNG, JPEG eller SVG?** Ja—alla standard bildformat stöds.

## Vad är create aztec barcode .net?
`create aztec barcode .net` avser processen att generera en Aztec tvådimensionell streckkod med hjälp av Aspose.BarCode API i en .NET‑miljö. API:t hanterar kodning, val av symbolläge och bildrendering automatiskt, vilket gör det möjligt för utvecklare att producera högkvalitativa streckkoder utan att behöva hantera lågnivådetaljer som felkorrigeringsberäkningar eller pixelmanipulation.

## Varför använda Aspose.BarCode för Aztec‑streckkoder?
Aspose.BarCode stöder **30+ streckkodssymboler** och kan rendera bilder upp till **10 000 × 10 000 px** utan att ladda hela filen i minnet. Det bearbetar ett 500‑sidigt dokument på under **2 sekunder** på en vanlig server, vilket gör det idealiskt för högkapacitets‑företagsscenarier.

## Förutsättningar

Innan vi börjar, se till att du har följande förutsättningar på plats:

- Grundläggande kunskap om .NET‑utveckling.  
- Visual Studio installerat på din maskin.  
- En kopia av Aspose.BarCode för .NET. Du kan ladda ner den [here](https://releases.aspose.com/barcode/net/). Du kan också utforska andra Aspose‑produkter [here](https://releases.aspose.com/).

Nu när du är redo, låt oss dyka ner i exemplen för Aztec Symbol Mode.

## Importera namnrymder

Först måste du importera de nödvändiga namnrymderna för att arbeta med Aspose.BarCode för .NET. Öppna ditt Visual Studio‑projekt och lägg till följande using‑satser högst upp i din kodfil:

```csharp
using Aspose.BarCode.Generation;
```

Med namnrymderna på plats kan du nu börja använda Aspose.BarCode för .NET.

## Hur ställer jag in Barcode Generator för Aztec‑streckkoder?

`BarcodeGenerator`‑klassen är den centrala komponenten som skapar streckkods‑bilder baserat på den valda symbolen och konfigurationsalternativen. Den erbjuder ett enkelt API för att ange streckkodstyp, data att koda och olika renderingsparametrar innan du sparar resultatet till en bildfil.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

I detta steg har vi konfigurerat generatorn och angett kodtexten för kodning.

## Hur ställer man in Aztec Symbol Mode till Auto?

`AztecSymbolMode`‑enumerationen definierar de fyra möjliga symbollägena för Aztec‑streckkoder, och **Auto**‑alternativet låter biblioteket automatiskt välja den mest kompakta storleken samtidigt som alla data‑ och felkorrigeringskrav bevaras. Detta läge är idealiskt för de flesta scenarier där du vill ha den minsta möjliga streckkoden utan manuell justering.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

Detta steg säkerställer att Aztec Symbol Mode bestäms automatiskt, och den resulterande streckkodsbilden sparas.

## Hur tvingar man FullRange Symbol Mode?

När du behöver maximal datakapacitet kan du välja **FullRange**‑värdet i `AztecSymbolMode`‑enumerationen. Detta läge inaktiverar automatisk storleksreduktion, vilket gör att streckkoden kan lagra hela teckenuppsättningen och uppnå den högsta möjliga informationsdensiteten, vilket är användbart för stora datamängder.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

Detta kommer att skapa en streckkod med FullRange Aztec Symbol Mode.

## Hur genererar man en Compact Aztec‑streckkod?

**Compact**‑värdet i `AztecSymbolMode`‑enumerationen producerar en mindre streckkod genom att minska antalet lager som används i matrisen. Detta resulterar i en mer yteffektiv bild, vilket gör den lämplig för applikationer med begränsat displayutrymme såsom mobila skärmar eller små etiketter.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

Detta steg konfigurerar streckkoden så att den genereras med Compact Aztec Symbol Mode.

## Hur skapar man en Rune Aztec‑streckkod?

**Rune**‑läget är en specialiserad variant av Aztec‑symboliken som kodar numerisk data med en anpassad teckenuppsättning, vilket ger en distinkt visuell stil samtidigt som den behåller samma felkorrigeringsstyrka som andra lägen. Det är användbart när du behöver en streckkod som betonar numerisk information.

```csharp
gen.CodeText = "123"; // Change the code text if needed
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

Detta steg ändrar kodtexten till "123" och genererar en streckkod med Rune Aztec Symbol Mode.

## Vanliga problem och lösningar

- **Bild sparas inte** – Se till att målmappen finns och att applikationen har skrivbehörighet.  
- **Oväntad symbolstorlek** – Verifiera att du inte har åsidosatt `EncodeMode` någon annanstans i din kod.  
- **Licensundantag** – En provversion lägger till ett vattenmärke; tillämpa en giltig licens för att ta bort det.

## Vanliga frågor

**Q: Vad är syftet med Aztec Symbol Mode i streckkodsgenerering?**  
A: Aztec Symbol Mode bestämmer hur biblioteket packar data i lager, vilket påverkar storlek, kapacitet och läsbarhet.

**Q: Kan jag ändra kodtexten för Aztec‑streckkoder i Aspose.BarCode för .NET?**  
A: Ja, tilldela helt enkelt en ny sträng till `CodeText`‑egenskapen innan du anropar `Save`.

**Q: Finns det en gratis provversion av Aspose.BarCode för .NET tillgänglig?**  
A: Ja, du kan ladda ner en gratis provversion av Aspose.BarCode för .NET [here](https://releases.aspose.com/).

**Q: Var kan jag hitta den fullständiga dokumentationen för Aspose.BarCode för .NET?**  
A: Du kan hänvisa till den kompletta dokumentationen för Aspose.BarCode för .NET [here](https://reference.aspose.com/barcode/net/).

**Q: Hur kan jag skaffa en tillfällig licens för Aspose.BarCode för .NET?**  
A: Du kan skaffa en tillfällig licens för Aspose.BarCode för .NET genom att besöka [this link](https://purchase.aspose.com/temporary-license/).

## Slutsats

I den här handledningen har vi utforskat hur man **create aztec barcode .net** med Aspose.BarCode, och täckt symbollägena Auto, FullRange, Compact och Rune. Du har nu en solid grund för att bädda in mångsidiga Aztec‑streckkoder i vilken .NET‑applikation som helst, oavsett om den körs på en desktop, webbserver eller molntjänst.

Om du har några frågor eller behöver ytterligare hjälp, tveka inte att kontakta Aspose.BarCode‑gemenskapen på deras [support forum](https://forum.aspose.com/c/barcode/13).

---

**Senast uppdaterad:** 2026-05-24  
**Testat med:** Aspose.BarCode 24.11 för .NET  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Aztec-kodtextkodning med Aspose.BarCode för .NET](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)
- [Aztec Bytes‑kodning med barcode generator .net](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [Hur man skapar Aztec‑streckkod med felkorrigering i .NET](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}