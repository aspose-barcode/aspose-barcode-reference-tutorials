---
date: 2026-06-09
description: Lär dig hur du genererar datamatrix-streckkod med Aspose.BarCode för
  .NET, anpassar bildförhållanden, ECC-lägen och datamatrix c40-kodning för effektiv
  streckkodsskapning.
keywords:
- generate datamatrix barcode
- datamatrix c40 encoding
- aspose barcode .net
- datamatrix ecc modes
- barcode aspect ratio
linktitle: DataMatrix-streckkodskonfiguration
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  headline: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  name: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  steps:
  - name: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
    text: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
  - name: '**Adjust** `AspectRatio` to your desired value.'
    text: '**Adjust** `AspectRatio` to your desired value.'
  - name: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
    text: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
  type: HowTo
- questions:
  - answer: Choose ECC 000‑140 for small data sets with limited error correction,
      or ECC 200 for larger data and higher reliability. Macro mode adds an extra
      data layer for linking.
    question: How do I decide which ECC mode to use?
  - answer: Yes, set the `CodeText` property to your custom string, then select the
      appropriate encoding mode (ASCII, C40, etc.) to control size.
    question: Can I embed custom text in a DataMatrix barcode?
  - answer: Set `EncodeMode` to `Auto`; Aspose.BarCode evaluates the payload and picks
      the most space‑efficient mode automatically.
    question: Is there a way to automatically select the best encoding mode?
  - answer: Reuse a single `BarCodeGenerator` instance, enable multi‑threading, and
      generate PNG images for lossless quality or JPEG for smaller file size. Processing
      10 000 symbols typically completes in under 30 seconds on a standard 8‑core
      server.
    question: What are the performance considerations for large barcode batches?
  - answer: Absolutely – the library is fully compatible with .NET Framework, .NET
      Core, and the latest .NET releases, offering the same feature set across all
      platforms.
    question: Does Aspose.BarCode support .NET Core and .NET 5/6?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Generera DataMatrix-streckkod – Proguide med Aspose.BarCode
url: /sv/net/datamatrix-barcode-configuration/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera DataMatrix-streckkod – Proguide med Aspose.BarCode

Välkommen till vår omfattande handledningsserie om **generate datamatrix barcode** med Aspose.BarCode för .NET. Oavsett om du är en erfaren utvecklare som finjusterar streckkodens utdata eller en nybörjare som är ivrig att förstå grunderna, guidar den här guiden dig genom varje steg—från grundläggande konfiguration till avancerade kodningstekniker—så att du kan leverera pålitliga, skanningsklara streckkoder i vilken .NET-applikation som helst.

## Snabba svar
- **Vad är det primära syftet?** Att programatiskt skapa och anpassa DataMatrix-streckkoder.  
- **Vilket bibliotek används?** Aspose.BarCode for .NET.  
- **Behöver jag en licens?** En gratis provversion finns tillgänglig; en kommersiell licens krävs för produktion.  
- **Stödda .NET-versioner?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Kan jag anpassa bildförhållandet?** Ja – se avsnittet “How to customize DataMatrix aspect ratio”.

## Vad är generate datamatrix barcode?
En DataMatrix-streckkod är en tvådimensionell matris av svarta och vita celler som kan lagra upp till 2 300 alfanumeriska tecken. Med Aspose.BarCode kan du **generate datamatrix barcode** bilder, PDF‑filer eller SVG‑filer direkt från din .NET‑kod, och kontrollera storlek, felkorrigeringsnivå och kodningsläge för att uppfylla alla branschstandarder.

## Varför använda Aspose.BarCode för DataMatrix?
Aspose.BarCode renderar DataMatrix‑symboler med upp till **600 dpi** utan pixling, vilket garanterar skarpa skanningar på högupplösta skrivare. Det stödjer **alla 50+ ECC‑ och makrolägen**—inklusive ECC 000‑140, ECC 200 och Macro 05/06—så att du kan välja den optimala felkorrigeringsnivån för din datamängd. API‑et erbjuder kodningsalternativen **ASCII, C40, Text, X12 och Bytes**, vilket låter dig packa data effektivt. Integration kräver bara ett enda NuGet‑paket och inga externa inhemska bibliotek.

## Hur du anpassar DataMatrix bildförhållande
Egenskapen `AspectRatio` i `BarCodeGenerator` styr bredd‑till‑höjd‑förhållandet för den genererade DataMatrix‑symbolen. `BarCodeGenerator` är huvudklassen i Aspose.BarCode som används för att skapa streckkodsbilder.  

**Direkt svar:** Sätt `generator.Parameters.Barcode.DataMatrix.AspectRatio = 1.2` (eller något värde mellan 0.5 och 2.0) innan du anropar `GenerateBarCodeImage()`. Biblioteket beräknar automatiskt om modulstorleken för att bevara skanningspålitlighet samtidigt som det respekterar det begärda förhållandet.

### Steg‑för‑steg
1. **Instansiera** `BarCodeGenerator` med `EncodeTypes.DataMatrix`.  
2. **Justera** `AspectRatio` till önskat värde.  
3. **Generera** bilden och verifiera med en scanner eller Aspose:s inbyggda läsare.

## Hur du genererar DataMatrix ECC 000‑140 streckkoder
ECC 000‑140 är idealisk för korta datasträngar där en kompakt symbol krävs, och erbjuder upp till 140 felkorrigeringskodord. `DataMatrixEccMode.Ecc000140` väljer ECC 000‑140 felkorrigeringsschema för DataMatrix.  

**Direkt svar:** Använd `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc000140` innan rendering. Detta byter kodaren till ECC 000‑140‑algoritmen, vilket producerar den minsta möjliga matrisen för given data samtidigt som den ger robust felkorrigering.  

**Praktiskt tips**  
När du kodar numerisk data under 20 tecken ger ECC 000‑140 ofta en 10 × 10‑matris, vilket sparar värdefull etikettutrymme.

## Hur du genererar DataMatrix ECC 200 streckkoder
ECC 200 är det mest använda DataMatrix‑läget, stödjer upp till 2 335 alfanumeriska tecken och erbjuder överlägsen felkorrigering. `DataMatrixEccMode.Ecc200` väljer ECC 200 felkorrigeringsschema för DataMatrix.  

**Direkt svar:** Sätt `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc200` och ange ditt innehåll via `CodeText`. Biblioteket väljer då automatiskt optimal matrisstorlek.  

**När du bör föredra ECC 200**  
Använd ECC 200 för längre strängar, blandad data eller när du behöver högsta motståndskraft mot skador—upp till **30 %** av symbolen kan återställas.

## Så behärskar du DataMatrix‑kodning i ASCII
ASCII‑läge kodar tecken med en byte per tecken, vilket gör det mest utrymmeseffektiva för vanlig text. `DataMatrixEncodeMode.Ascii` talar om för generatorn att använda ASCII‑kodning för DataMatrix‑symbolen.  

**Direkt svar:** Tilldela `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Ascii` och sätt `CodeText` till din ASCII‑sträng. Motorn packar data utan extra overhead, vilket ger den minsta möjliga matrisen för ren ASCII‑innehåll.  

**Exempelscenario**  
Ett lager‑SKU bestående av stora bokstäver och siffror (t.ex. “AB1234”) passar perfekt i ASCII‑läge, vilket ofta resulterar i en 12 × 12‑matris.

## Hur du genererar DataMatrix‑läge (Auto)
Auto‑läge låter Aspose.BarCode analysera indata och automatiskt välja den mest effektiva kodningen (ASCII, C40, Text, X12 eller Bytes). `DataMatrixEncodeMode.Auto` aktiverar denna automatiska urvalsfunktion.  

**Direkt svar:** Sätt `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Auto`. Biblioteket utvärderar payloaden, väljer optimal läge och renderar streckkoden i ett steg.  

**Fördelar**  
Auto‑läge minskar utvecklingsarbete och garanterar den minsta möjliga symbolen för blandad data, vilket förbättrar skanningshastigheten.

## Hur du använder DataMatrix‑kodningsläge (Bytes)
Bytes‑läge är designat för binär data, såsom krypterade payloads eller komprimerade filer. `DataMatrixEncodeMode.Bytes` instruerar generatorn att behandla varje byte som rådata.  

**Direkt svar:** Använd `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Bytes` och ange en Base64‑kodad sträng som `CodeText`. Kodaren behandlar varje byte som rådata, vilket bevarar den exakta binära representationen.  

**Användningsfall**  
Inbäddning av ett 128‑bit GUID eller en liten krypterad token direkt i en DataMatrix‑symbol.

## Så behärskar du DataMatrix‑kodningsläge (C40)
C40‑läge komprimerar stora bokstäver och alfanumerisk data, vilket ger upp till **40 %** minskning jämfört med ASCII. `DataMatrixEncodeMode.C40` aktiverar detta komprimeringsalgoritm.  

**Direkt svar:** Sätt `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.C40` och ange en sträng med stora bokstäver (t.ex. “HELLO WORLD”). Motorn packar tre tecken i två kodord, vilket minskar den slutliga matrisen.  

**Pro‑tips**  
C40 fungerar bäst när payloaden mestadels består av stora bokstäver, siffror och mellanslag. För blandade fall, överväg Auto‑läge.

## Så konfigurerar du DataMatrix‑kodtext
`CodeText`‑egenskapen definierar exakt data som lagras i streckkoden. Den kan innehålla vanlig text, numeriska strängar eller till och med XML‑payloads. `CodeText` är den primära strängegenskapen i `BarCodeGenerator` som håller streckkodens payload.  

**Direkt svar:** Tilldela `generator.Parameters.Barcode.CodeText = "YourDataHere"` innan rendering. Egenskapen accepterar vilken UTF‑8‑sträng som helst upp till maximal längd som stöds av vald ECC‑läge.  

**Avancerat tips**  
Kombinera `CodeText` med `ExtendedDataMatrix` för att bädda in ytterligare metadata utan att öka den synliga matrisstorleken.

## Så behärskar du DataMatrix‑makrokonfiguration
Makrolägen (Macro 05 och Macro 06) låter dig bädda in en sekundär DataMatrix‑symbol i den primära, användbart för att länka till externa datakällor. `DataMatrixMacroMode.Macro05` och `DataMatrixMacroMode.Macro06` aktiverar dessa makrofunktioner.  

**Direkt svar:** Aktivera makroläge med `generator.Parameters.Barcode.DataMatrix.MacroMode = DataMatrixMacroMode.Macro05` (eller `Macro06`) och sätt `MacroPdf417`‑egenskaper för den sekundära payloaden. Generatorn skapar en sammansatt symbol som skannrar kan tolka som två länkade koder.  

**Exempel från verkligheten**  
Inbäddning av en URL i makrodelen medan produktidentifierare hålls i den primära matrisen, vilket möjliggör sömlös web‑till‑streckkod‑integration.

*Användning av Aspose.BarCode för .NET‑handledningar*

## DataMatrix‑streckkodskonfigurationshandledningar
### [Anpassa DataMatrix bildförhållande](./datamatrix-aspect-ratio-customization/)
Lär dig hur du anpassar DataMatrix‑streckkodens bildförhållanden med Aspose.BarCode för .NET. Steg‑för‑steg‑guide för streckkodsgenerering.
### [Generera DataMatrix ECC 000-140 streckkoder](./datamatrix-ecc-000-140-configuration/)
Skapa DataMatrix ECC 000-140 streckkoder enkelt med Aspose.BarCode för .NET. Öka effektiviteten i lagerhantering och mer.
### [Generera DataMatrix ECC 200 streckkoder](./datamatrix-ecc-200-configuration/)
Lär dig hur du genererar DataMatrix ECC 200 streckkoder i .NET med Aspose.BarCode. Effektivisera verksamheten med effektiv streckkodsskapning.
### [Behärska DataMatrix‑kodning i ASCII](./datamatrix-encoding-mode-ascii/)
Lär dig skapa DataMatrix‑streckkoder i ASCII‑läge med Aspose.BarCode för .NET. Steg‑för‑steg‑guide för utvecklare.
### [Generera DataMatrix‑läge (Auto)](./datamatrix-encoding-mode-auto/)
Lär dig hur du genererar DataMatrix‑läge (Auto) med Aspose.BarCode för .NET. Denna steg‑för‑steg‑guide täcker allt från förutsättningar till läsning av streckkoder.
### [DataMatrix‑kodningsläge (Bytes)](./datamatrix-encoding-mode-bytes/)
Lär dig hur du kodar data i DataMatrix‑format med Bytes‑läge med Aspose.BarCode för .NET. Följ vår steg‑för‑steg‑guide för streckkodsgenerering och -igenkänning.
### [Behärska DataMatrix‑kodningsläge (C40)](./datamatrix-encoding-mode-c40/)
Lär dig DataMatrix‑kodningsläge (C40) med Aspose.BarCode för .NET. Skapa anpassade streckkoder effektivt. Utforska steg‑för‑steg‑guiden.
### [Konfigurera DataMatrix‑kodtext](./datamatrix-extended-code-text-configuration/)
Lär dig konfigurera DataMatrix utökad kodtext med Aspose.BarCode för .NET. Generera, identifiera och integrera streckkoder i dina .NET‑applikationer.
### [Behärska DataMatrix‑makrokonfiguration](./datamatrix-macro-configuration/)
Lär dig hur du konfigurerar DataMatrix‑makrostreckkoder med Aspose.BarCode för .NET. Generera, anpassa och identifiera DataMatrix‑streckkoder i dina .NET‑applikationer.

## Vanliga frågor

**Q: Hur bestämmer jag vilken ECC‑mode jag ska använda?**  
A: Välj ECC 000‑140 för små datamängder med begränsad felkorrigering, eller ECC 200 för större data och högre pålitlighet. Makroläge lägger till ett extra datalager för länkar.

**Q: Kan jag bädda in anpassad text i en DataMatrix‑streckkod?**  
A: Ja, sätt `CodeText`‑egenskapen till din anpassade sträng, och välj sedan lämpligt kodningsläge (ASCII, C40 osv.) för att kontrollera storleken.

**Q: Finns det ett sätt att automatiskt välja det bästa kodningsläget?**  
A: Sätt `EncodeMode` till `Auto`; Aspose.BarCode utvärderar payloaden och väljer automatiskt det mest utrymmeseffektiva läget.

**Q: Vilka prestandaöverväganden finns för stora streckkodsbatcher?**  
A: Återanvänd en enda `BarCodeGenerator`‑instans, aktivera flertrådad körning och generera PNG‑bilder för förlustfri kvalitet eller JPEG för mindre filstorlek. Bearbetning av 10 000 symboler slutförs vanligtvis på under 30 sekunder på en standard 8‑kärnig server.

**Q: Stöder Aspose.BarCode .NET Core och .NET 5/6?**  
A: Absolut – biblioteket är fullt kompatibelt med .NET Framework, .NET Core och de senaste .NET‑utgåvorna, och erbjuder samma funktionsuppsättning på alla plattformar.

**Senast uppdaterad:** 2026-06-09  
**Testad med:** Aspose.BarCode 24.12 for .NET  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man genererar DataMatrix‑streckkoder (ECC 200) med Aspose.BarCode för .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Behärska DataMatrix‑kodning i ASCII med Aspose.BarCode för .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Skapa streckkod PNG – DataMatrix bildförhållande – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}