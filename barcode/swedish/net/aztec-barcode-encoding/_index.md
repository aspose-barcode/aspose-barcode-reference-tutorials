---
date: 2026-05-19
description: Lär dig hur du skapar Aztec barcode med Aspose.BarCode för .NET, anpassar
  bildförhållanden, kodar bytes eller text och behärskar symbollägen.
keywords:
- create aztec barcode
- aztec barcode encoding
- aspose barcode .net
linktitle: Aztec Barcode kodning
schemas:
- author: Aspose
  dateModified: '2026-05-19'
  description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  headline: How to create Aztec barcode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  name: How to create Aztec barcode with Aspose.BarCode for .NET
  steps:
  - name: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
    text: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
  - name: '**Assign your data** (text, bytes, or numeric string).'
    text: '**Assign your data** (text, bytes, or numeric string).'
  - name: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
    text: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
  - name: '**Generate the image** using `Save` or `GetBarCodeImage`.'
    text: '**Generate the image** using `Save` or `GetBarCodeImage`.'
  - name: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
    text: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
  - name: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
    text: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
  - name: '**Call `EncodeBytes(data)`** to load the binary content.'
    text: '**Call `EncodeBytes(data)`** to load the binary content.'
  - name: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
    text: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
  - name: '**Create the generator** with `EncodeTypes.Aztec`.'
    text: '**Create the generator** with `EncodeTypes.Aztec`.'
  - name: '**Set `CodeText`** to the string you want to encode.'
    text: '**Set `CodeText`** to the string you want to encode.'
  type: HowTo
- questions:
  - answer: The library works with .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET
      6, and later.
    question: Which .NET versions are supported by Aspose.BarCode for Aztec encoding?
  - answer: Yes—set the `Resolution` property (e.g., 300 dpi) before saving the image
      to obtain print‑ready quality.
    question: Can I create a high‑resolution Aztec barcode for printing?
  - answer: Up to 3,000 numeric or 2,300 alphanumeric characters, or roughly 1,800
      bytes of raw data in Compact mode.
    question: How large a data payload can an Aztec barcode hold?
  - answer: Absolutely—Aspose.BarCode’s decoder automatically detects orientation
      and corrects it during the read operation.
    question: Is it possible to read an Aztec barcode that has been rotated?
  - answer: A free evaluation license is available for testing; a commercial license
      is required for production deployments.
    question: Do I need a license for development and testing?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Hur man skapar Aztec barcode med Aspose.BarCode för .NET
url: /sv/net/aztec-barcode-encoding/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aztec streckkodkodning

Är du redo att dyka in i världen av Aztec Barcode Encoding och lära dig hur du **skapar Aztec streckkod**‑bilder med Aspose.BarCode för .NET? Detta bibliotek ger dig full kontroll över storlek, felkorrigering och datarapresentation, vilket gör det idealiskt för allt från mobilt biljettsystem till lagerhantering.

## Snabba svar
- **Vilket bibliotek stödjer Aztec‑streckkoder?** Aspose.BarCode för .NET  
- **Kan jag ändra bildförhållandet?** Ja, via egenskapen `AspectRatio`  
- **Är byte‑nivåkodning möjlig?** Absolut – använd metoden `EncodeBytes`  
- **Vilka felkorrigeringsnivåer finns tillgängliga?** Nivåer 0 till 4 (högre = mer redundans)  
- **Behöver jag en licens för produktion?** Ja, en kommersiell licens tar bort evalueringsgränserna  

## Vad är en Aztec‑streckkod?
En Aztec‑streckkod är en tvådimensionell matris‑kod som kan koda upp till 3 000 numeriska eller 2 300 alfanumeriska tecken. Den har ett centralt sökmönster som möjliggör snabb skanning även när symbolen skrivs ut med låg upplösning. Eftersom mönstret sitter i mitten kan koden läsas från vilken riktning som helst, vilket gör den mycket pålitlig för mobila och industriella tillämpningar.

## Hur anpassar du bildförhållandet för en Aztec‑streckkod?
`BarcodeGenerator` är huvudklassen som används för att skapa streckkoder i Aspose.BarCode. Ställ in `AspectRatio`‑egenskapen på `BarcodeGenerator`‑objektet till önskad bredd‑till‑höjd‑proportion och generera sedan bilden. Att justera bildförhållandet hjälper dig att få streckkoden att passa in i begränsade UI‑ytor eller etikettlayouter utan att offra skanningspålitlighet, och det låter dig även följa varumärkesriktlinjer eller specifika skrivarkrav.

### Steg för att anpassa bildförhållandet
1. **Skapa en `BarcodeGenerator`‑instans** med `EncodeTypes.Aztec`.  
2. **Tilldela dina data** (text, byte eller numerisk sträng).  
3. **Ställ in `AspectRatio`** – exempelvis `1.5` för en bredare stapel.  
4. **Generera bilden** med `Save` eller `GetBarCodeImage`.  

## Hur kan du koda råa byte i en Aztec‑streckkod?
`EncodeBytes` är en metod som accepterar en byte‑array och konverterar den till en Aztec‑matris. Skicka en byte‑array till `EncodeBytes`‑metoden på `BarcodeGenerator`. API‑t konverterar automatiskt de binära data till en kompakt Aztec‑matris och bevarar varje bit. Detta är perfekt för att bädda in krypterade nyttolaster, binära identifierare eller komprimerade filer direkt i en streckkod.

### Steg för att koda byte
1. **Förbered byte‑arrayen** (t.ex. `byte[] data = Encoding.UTF8.GetBytes("Hello")`).  
2. **Instansiera `BarcodeGenerator`** med `EncodeTypes.Aztec`.  
3. **Anropa `EncodeBytes(data)`** för att ladda det binära innehållet.  
4. **Rendera streckkoden** med `Save` eller `GetBarCodeImage`.  

## Hur kodar du text i en Aztec‑streckkod?
`CodeText` är en egenskap som innehåller den rena texten som ska kodas. Använd `CodeText`‑egenskapen på `BarcodeGenerator` för att tillhandahålla textdata. Biblioteket väljer automatiskt den optimala kodningsläget (numeriskt, alfanumeriskt eller byte) och tillämpar rätt felkorrigeringsnivå. Detta gör det enkelt att bädda in URL:er, produkt‑ID:n eller vilken läsbar sträng som helst.

### Steg för att koda text
1. **Skapa generatorn** med `EncodeTypes.Aztec`.  
2. **Ställ in `CodeText`** till den sträng du vill koda.  
3. **Justera eventuellt `ErrorLevel`** för högre motståndskraft.  
4. **Generera bilden** med `Save` eller `GetBarCodeImage`.  

## Hur kan du generera Aztec‑streckkoder med olika felkorrigeringsnivåer?
`ErrorLevel` är en egenskap som styr hur mycket redundant data som läggs till i streckkoden. Justera `ErrorLevel`‑egenskapen (0‑4) innan rendering. Högre nivåer ökar mängden redundant data, vilket gör att streckkoden kan läsas även när upp till 30 % av symbolen är skadad. Detta är avgörande i tuffa miljöer som industriell märkning eller utomhusskyltning.

### Steg för att ställa in felkorrigering
1. **Instansiera `BarcodeGenerator`** för Aztec.  
2. **Tilldela dina data** (text eller byte).  
3. **Ställ in `ErrorLevel`** – t.ex. `generator.Parameters.Barcode.Aztec.ErrorLevel = 3`.  
4. **Rendera streckkoden** med ditt föredragna utdataformat.  

## Vilka är de olika Aztec Symbollägena och hur använder du dem?
`SymbolMode` är en inställning som bestämmer matrisens storlek och datakapacitet för den genererade Aztec‑koden. Biblioteket erbjuder fyra lägen: **Auto**, **FullRange**, **Compact** och **Rune**.  

- **Auto** – generatorn väljer den minsta möjliga storleken.  
- **FullRange** – tillåter maximal matrisstorlek för mycket stora datamängder.  
- **Compact** – skapar en mindre, tätare symbol idealisk för begränsat utrymme.  
- **Rune** – ett specialiserat läge för kodning av Unicode‑runor.  

Välj läge via `Generator.Parameters.Barcode.Aztec.SymbolMode`. Varje läge balanserar storlek, läsbarhet och datakapacitet, så att du kan anpassa streckkoden efter dina applikationskrav.

## Aztec streckkodskodningshandledningar
Nedan följer dedikerade steg‑för‑steg‑guider som går djupare in på varje ämne ovan. Klicka på någon länk för att utforska fullständiga kodexempel, förutsättningar och bästa praxis‑tips.

### [Anpassa Aztec streckkod bildförhållande](./aztec-aspect-ratio-customization/)
Lär dig hur du anpassar bildförhållandet för Aztec‑streckkoder med Aspose.BarCode för .NET. Skapa unika, flexibla streckkoder för dina .NET‑applikationer.

### [Aztec bytekodning](./aztec-bytes-encoding/)
Lär dig hur du utför Aztec Bytes Encoding med Aspose.BarCode för .NET. Steg‑för‑steg‑guide, förutsättningar och kodexempel ingår.

### [Aztec kodtextkodning](./aztec-code-text-encoding/)
Upptäck kraften i Aztec Code Text Encoding med Aspose.BarCode för .NET. Lär dig hur du skapar och läser Aztec‑koder i dina .NET‑applikationer.

### [Generera Aztec felstreckkoder](./aztec-error-level-example/)
Lär dig hur du genererar Aztec‑felkorrigeringsstreckkoder med olika felnivåer med Aspose.BarCode för .NET. Omfattande guide för streckkodsskapande.

### [Behärska Aztec Symbolläge](./aztec-symbol-mode-example/)
Utforska Aztec Symbol Mode i Aspose.BarCode för .NET och lär dig hur du enkelt genererar mångsidiga streckkoder. Praktiska exempel på Auto, FullRange, Compact och Rune‑lägen i denna omfattande handledning.

## Vanliga frågor

**Q: Vilka .NET-versioner stöds av Aspose.BarCode för Aztec‑kodning?**  
A: Biblioteket fungerar med .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6 och senare.

**Q: Kan jag skapa en högupplöst Aztec‑streckkod för utskrift?**  
A: Ja—sätt `Resolution`‑egenskapen (t.ex. 300 dpi) innan du sparar bilden för att få utskriftsklar kvalitet.

**Q: Hur stor datamängd kan en Aztec‑streckkod rymma?**  
A: Upp till 3 000 numeriska eller 2 300 alfanumeriska tecken, eller ungefär 1 800 byte rådata i Compact‑läge.

**Q: Är det möjligt att läsa en Aztec‑streckkod som har roterats?**  
A: Absolut—Aspose.BarCode:s avkodare upptäcker automatiskt orienteringen och korrigerar den vid läsning.

**Q: Behöver jag en licens för utveckling och testning?**  
A: En gratis evalueringslicens finns för testning; en kommersiell licens krävs för produktionsdistribution.

---

**Senast uppdaterad:** 2026-05-19  
**Testad med:** Aspose.BarCode 24.12 för .NET  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Hur man genererar Aztec‑streckkod med anpassat bildförhållande med Aspose.BarCode för .NET](/barcode/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Aztec bytekodning med barcode generator .net](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [Hur man skapar Aztec‑streckkod med felkorrigering i .NET](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}