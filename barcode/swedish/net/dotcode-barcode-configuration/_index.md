---
date: 2026-06-14
description: Lär dig hur du genererar DotCode-streckkoder med Aspose.BarCode för .NET,
  inklusive bildförhållande, kodningslägen, utökad text och läsarinitialisering.
keywords:
- how to generate dotcode
- dotcode barcode configuration
- aspose barcode .net
linktitle: Hur man genererar DotCode-streckkoder – Konfigurationsguide
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to generate DotCode barcodes with Aspose.BarCode for .NET,
    covering aspect ratio, encoding modes, extended text, and reader initialization.
  headline: How to Generate DotCode Barcodes – Configuration Guide
  type: TechArticle
- questions:
  - answer: Yes, set `BarCodeImageFormat = BarCodeImageFormat.Svg` on the generator
      to receive a scalable vector output.
    question: Can I generate DotCode barcodes in SVG format?
  - answer: Aspose.BarCode does not support direct logo embedding for DotCode, but
      you can overlay an image after generation using standard graphics libraries.
    question: Is it possible to embed a logo inside a DotCode symbol?
  - answer: The symbology includes built‑in Reed‑Solomon error correction; increasing
      rows/columns automatically raises the correction level.
    question: How does error correction work for DotCode?
  - answer: No, the same `BarCodeReader` can extract DotCode from PDF pages, images,
      or streams without additional tools.
    question: Do I need a separate library to read DotCode from a PDF?
  - answer: Up to **1 200** numeric or **800** alphanumeric characters, depending
      on the chosen rows/columns configuration.
    question: What is the maximum data size for a single DotCode symbol?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Hur man genererar DotCode-streckkoder – Konfigurationsguide
url: /sv/net/dotcode-barcode-configuration/
weight: 32
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar DotCode-streckkoder – Konfigurationsguide

## Introduktion
**Hur man genererar DotCode** streckkoder snabbt och pålitligt är ett vanligt krav för utvecklare som bygger lager-, spårnings- eller mobila skanningslösningar. I den här handledningen går vi igenom varje konfigurationsalternativ som Aspose.BarCode för .NET erbjuder för DotCode-symboler—justeringar av bildförhållande, Auto- och Bytes‑kodningslägen, hantering av utökad kodtext, läsarininitiering, rader/kolumner‑layout och Structured‑Append‑läge. När du är klar kan du producera perfekt storleksanpassade, högdensitets‑DotCode‑bilder som uppfyller branschstandarder och integreras sömlöst i vilken .NET‑applikation som helst.

## Snabba svar
- **Vad är den primära klassen för att skapa en DotCode‑streckkod?** `BarcodeGenerator` med `EncodeTypes.DotCode`.
- **Vilken egenskap styr bildförhållandet?** `BarCodeImageAspectRatio`.
- **Kan jag växla mellan Auto‑ och Bytes‑kodning?** Ja, via egenskapen `EncodeMode`.
- **Behövs en separat läsare för DotCode?** Nej, samma `BarcodeGenerator` kan avkoda när `ReadBarcode` anropas.
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Hur man genererar DotCode‑streckkoder med Aspose.BarCode för .NET?
`BarcodeGenerator` är den primära klassen i Aspose.BarCode för att skapa streckkodsbilder. Ladda `BarcodeGenerator` med `EncodeTypes.DotCode`, sätt önskade egenskaper (bildförhållande, kodningsläge, rader/kolumner osv.) och anropa `GenerateBarCodeImage()`—biblioteket returnerar en färdig‑att‑använda `System.Drawing.Image` eller en byte‑array. Detta endaste steg‑arbetsflöde hanterar alla låg‑nivå‑kodningsdetaljer, stödjer utdataformat som PNG, JPEG och SVG, och kan rendera bilder upp till 10 000 × 10 000 px utan att förbruka onödig minne.

## Vad är en DotCode‑streckkod?
En DotCode‑streckkod är en högdensitets, kvadratisk 2D‑symbologi som lagrar upp till 1 200 numeriska eller 800 alfanumeriska tecken i en kompakt matris av prickar. Den är optimerad för märkning av små paket och mobil skanning, och erbjuder snabba läshastigheter även på lågupplösta kameror.

## Varför använda DotCode med Aspose.BarCode?
Aspose.BarCode stödjer **20+** 2D‑streckkodstyper, inklusive DotCode, och kan bearbeta filer större än **200 MB** utan att ladda hela bilden i minnet. Biblioteket garanterar **99,9 %** skanningsnoggrannhet på vanliga smarttelefonkameror och erbjuder inbyggda felkorrigeringsnivåer för att minimera läsfel.

## Förutsättningar
- .NET Framework 4.5 eller högre, eller .NET Core 3.1 / .NET 5+.
- Aspose.BarCode för .NET (senaste versionen rekommenderas).
- En tillfällig eller fullständig licensnyckel (prövversion fungerar för utveckling).

## Anpassning av DotCode‑aspektförhållande
**aspect‑ratio** bestämmer hur utdragen eller komprimerad DotCode‑matrisen visas. Använd egenskapen `BarCodeImageAspectRatio` för att ange ett värde mellan **0.5** (tätare) och **2.0** (bredare). Ett förhållande på **1.0** ger en perfekt kvadratisk symbol, vilket är standard och fungerar bäst för de flesta skannrar.

> **Tips:** Vid utskrift på smala etiketter förbättrar ett förhållande på **0.75** ofta läsbarheten utan att minska datakapaciteten.

## DotCode kodningsläge (Auto)
I **Auto**‑läge analyserar biblioteket inmatningssträngen och väljer automatiskt den mest effektiva kodningen (numerisk, alfanumerisk eller byte). Detta maximerar datadensiteten och minskar symbolens totala storlek.

> **Direkt svar:** Sätt `EncodeMode = EncodeModes.Auto` på `BarcodeGenerator` för att låta Aspose.BarCode bestämma optimal kodning för dina data, vilket säkerställer den minsta möjliga DotCode‑storleken samtidigt som alla tecken bevaras.

## DotCode kodningsläge (Bytes)
När du behöver lagra binär data eller för‑kodade byte‑arrayer, välj **Bytes**‑läge. Detta tvingar generatorn att behandla indata som råa byte, och kringgår automatisk teckenuppsättningsdetektering.

> **Direkt svar:** Använd `EncodeMode = EncodeModes.Bytes` och tillhandahåll en `byte[]`‑payload för att bädda in binär information såsom krypterade identifierare eller komprimerade filer direkt i DotCode‑symbolen.

## Konfiguration av DotCode utökad kodtext
Utökad kodtext låter dig bifoga kompletterande information som inte är en del av huvuddatapayloaden men som kan visas tillsammans med streckkoden i rapporter eller GUI. Sätt egenskapen `ExtendedCodeText` till en valfri sträng (upp till **256** tecken) och välj ett teckensnitt via `ExtendedCodeTextFont`.

> **Pro‑tips:** Kombinera utökad text med en mindre teckenstorlek (t.ex. 8 pt) för att hålla den visuella fotavtrycket lågt samtidigt som du ger mänskligt läsbar kontext.

## Initiering av DotCode‑läsare
`BarCodeReader` är klassen som används för att avkoda streckkoder från bilder eller strömmar. Att läsa en DotCode‑bild är lika enkelt som att generera den. Skapa en `BarCodeReader` med bildströmmen och specificera `EncodeTypes.DotCode`. Anropa `ReadBarCode()` för att hämta den avkodade strängen.

> **Direkt svar:** `using (var reader = new BarCodeReader(imageStream, DecodeType.DotCode)) { if (reader.ReadBarCode()) { string data = reader.GetCodeText(); } }` – detta enkla block avkodar symbolen utan externa beroenden.

## Konfiguration av DotCode rader och kolumner
DotCode tillåter explicit kontroll över antalet rader och kolumner, vilket påverkar symbolstorlek och felkorrigeringskapacitet. Använd egenskaperna `Rows` och `Columns` för att ange värden mellan **10** och **144**. Större matriser ökar datakapaciteten och robustheten.

> **Bästa praxis:** För inventarie‑etiketter som måste klara hårdhänt hantering, konfigurera **Rows = 64** och **Columns = 64** för att lägga till extra redundans.

## Konfiguration av DotCode Structured Append‑läge
Structured Append möjliggör uppdelning av en stor payload över flera DotCode‑symboler som kan läsas sekventiellt. Sätt `StructuredAppend = true` och definiera `StructuredAppendCount` samt `StructuredAppendIndex` för varje del.

> **Direkt svar:** Aktivera `StructuredAppend` på varje `BarcodeGenerator`, tilldela ett unikt index (börjar på 1) och ange det totala antalet; biblioteket kommer automatiskt att bädda in den nödvändiga länkinformationen.

## Vanliga problem och lösningar
- **Oläslig streckkod på lågupplösta skärmar:** Öka egenskapen `Resolution` till minst **300 dpi** före generering.
- **Varningar om datatrunkering:** Verifiera att indata‑längden inte överskrider maxgränsen för de valda raderna/kolumnerna; justera storleken eller byt till Bytes‑läge om det behövs.
- **Licensutgång under utveckling:** Använd en tillfällig licens hämtad från Aspose‑portalen; ersätt den med en permanent nyckel innan produktionsdistribution.

## Vanliga frågor

**Q: Kan jag generera DotCode‑streckkoder i SVG‑format?**  
A: Ja, sätt `BarCodeImageFormat = BarCodeImageFormat.Svg` på generatorn för att få en skalbar vektorutdata.

**Q: Är det möjligt att bädda in en logotyp i en DotCode‑symbol?**  
A: Aspose.BarCode stödjer inte direkt logotypinbäddning för DotCode, men du kan överlagra en bild efter generering med vanliga grafikbibliotek.

**Q: Hur fungerar felkorrigering för DotCode?**  
A: Symbolen innehåller inbyggd Reed‑Solomon‑felkorrigering; ökning av rader/kolumner höjer automatiskt korrigeringsnivån.

**Q: Behöver jag ett separat bibliotek för att läsa DotCode från en PDF?**  
A: Nej, samma `BarCodeReader` kan extrahera DotCode från PDF‑sidor, bilder eller strömmar utan extra verktyg.

**Q: Vad är den maximala datastorleken för en enskild DotCode‑symbol?**  
A: Upp till **1 200** numeriska eller **800** alfanumeriska tecken, beroende på den valda rader/kolumner‑konfigurationen.

**Senast uppdaterad:** 2026-06-14  
**Testat med:** Aspose.BarCode 24.11 för .NET  
**Författare:** Aspose  

## DotCode streckkodskonfigurationshandledningar
### [Anpassa DotCode bildförhållande](./dotcode-aspect-ratio-customization/)
Lär dig anpassa DotCode‑streckkodens bildförhållande med Aspose.BarCode för .NET. Skapa skräddarsydda streckkoder för dina applikationer utan ansträngning.
### [DotCode kodningsläge (Auto)](./dotcode-encoding-mode-auto/)
Utforska DotCode kodningsläge (Auto) i Aspose.BarCode för .NET, ett kraftfullt verktyg för streckkodsgenerering. Lär dig steg för steg hur du genererar DotCode‑streckkoder. Se dokumentationen, ladda ner biblioteket och få tillfälliga licenser.
### [DotCode kodningsläge (Bytes)](./dotcode-encoding-mode-bytes/)
Lär dig DotCode‑kodning med Aspose.BarCode för .NET: En steg‑för‑steg‑guide för att generera streckkoder.
### [DotCode konfiguration av utökad kodtext](./dotcode-extended-code-text-configuration/)
Generera DotCode‑utökad kodtext med lätthet med Aspose.BarCode för .NET. Följ vår steg‑för‑steg‑guide för effektiv streckkodsskapning.
### [Initiering av DotCode‑läsare](./dotcode-reader-initialization/)
Lär dig hur du initierar DotCode‑läsare med Aspose.BarCode för .NET. Skapa DotCode‑streckkoder enkelt för olika tillämpningar.
### [Konfiguration av DotCode rader och kolumner](./dotcode-rows-columns-configuration/)
Lär dig konfigurera DotCode‑rader och -kolumner med Aspose.BarCode för .NET. Generera precisa och anpassningsbara 2D‑streckkoder utan ansträngning.
### [Konfiguration av DotCode Structured Append‑läge](./dotcode-structured-append-mode-configuration/)
Lär dig konfigurera DotCode Structured Append‑läge med Aspose.BarCode för .NET och skapa effektiva streckkoder.

## Relaterade handledningar

- [Anpassa DotCode bildförhållande med Aspose.BarCode för .NET](/barcode/net/dotcode-barcode-configuration/dotcode-aspect-ratio-customization/)
- [DotCode konfiguration av utökad kodtext med Aspose.BarCode för .NET](/barcode/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [DotCode kodningsläge (Auto) i Aspose.BarCode för .NET](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}