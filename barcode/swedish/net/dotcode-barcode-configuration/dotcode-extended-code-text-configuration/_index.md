---
date: 2026-09-28
description: Lär dig hur du skapar 2d matrix barcode med Aspose.BarCode för .NET –
  en steg‑för‑steg‑guide för att generera DotCode‑streckkoder med extended code text.
keywords:
- create 2d matrix barcode
- how to generate dotcode
- dotcode extended codetext
lastmod: 2026-09-28
linktitle: DotCode Extended Code Text‑konfiguration
og_description: Lär dig att skapa 2d matrix barcode med Aspose.BarCode för .NET. Denna
  guide visar steg‑för‑steg hur man genererar DotCode‑streckkoder med extended code
  text.
og_image_alt: Guide showing how to create a 2d matrix DotCode barcode with extended
  codetext in .NET
og_title: Skapa 2d matrix barcode med Aspose.BarCode för .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create 2d matrix barcode with Aspose.BarCode for .NET
    – a step‑by‑step guide for generating DotCode barcodes with extended code text.
  headline: How to create 2d matrix barcode via Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. The PNG image produced by the generator can be embedded in iOS, Android,
      or any cross‑platform mobile application.
    question: Can I use the generated barcode in a mobile app?
  - answer: Use the `AddECICodetext` method with the appropriate `ECIEncodings` (e.g.,
      `ECIEncodings.Base64`) to embed binary payloads.
    question: What if I need to encode binary data instead of text?
  - answer: Adjust the `XDimension.Pixels` property; higher values increase module
      size, while lower values make the barcode more compact.
    question: How do I change the barcode size without affecting readability?
  - answer: Yes. Set `gen.Parameters.Barcode.Margin` to define the desired quiet zone
      in pixels.
    question: Is there a way to add a quiet zone around the barcode?
  - answer: The latest Aspose.BarCode releases are compatible with .NET 8; just reference
      the appropriate NuGet package version.
    question: Does the library support .NET 8?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- dotcode
- Aspose.BarCode
- .NET barcode generation
- 2d matrix barcode
title: Hur du skapar 2d matrix barcode via Aspose.BarCode för .NET
url: /sv/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så skapar du 2d-matrisstreckkod via Aspose.BarCode för .NET

## Introduktion

I området för streckkodsgenerering och -hantering sticker Aspose.BarCode för .NET ut som en mångsidig lösning som stöder **50+ in- och utdataformat** och kan bearbeta dokument på flera hundra sidor utan att ladda hela filen i minnet. Oavsett om du behöver streckkoder för produktspårning, lagerkontroll eller datarika applikationer, gör skapandet av en **2d-matrisstreckkod** såsom DotCode med utökad kodtext det möjligt att bädda in både textuella och binära data i en kompakt fyrkantig symbol. Denna handledning guidar dig genom att bygga den utökade kodtexten steg för steg och rendera den slutliga bilden.

## Snabba svar
- **Vad betyder “create dotcode extended codetext”?** Det betyder att bygga en DotCode-streckkod som inkluderar FNC1, ECICodetext, vanlig text och symbolseparatorer i en enda utökad nyttolast.  
- **Vilket bibliotek krävs?** Aspose.BarCode för .NET.  
- **Behöver jag en licens?** En tillfällig licens fungerar för utvärdering; en full licens krävs för produktion.  
- **Vilka .NET-versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Hur lång tid tar implementeringen?** Ungefär 10‑15 minuter för ett grundexempel.

## Så skapar du dotcode utökad kodtext

Läs in ditt projekt, ange katalogen, bygg den utökade kodtexten och generera bilden – allt på mindre än ett dussin kodrader. Följande direkta svar sammanfattar hela processen:

Läs in `BarcodeGenerator` med `EncodeTypes.DotCode`, bygg den utökade kodtexten med `DotCodeExtendedCodetextBuilder` (lägger till FNC1, ECICodetext, vanlig text och FNC3-separatorer), och anropa sedan `Save` för att skriva en PNG‑fil. Denna sekvens skapar en fullt kompatibel 2d-matrisstreckkod i ett enda anrop.

## Vad är dotcode utökad kodtext?

**dotcode extended codetext** är en sammansatt sträng som kombinerar flera datasegment—såsom FNC1‑identifierare, ECICodetext, vanlig text och FNC3‑separatorer—till en enda nyttolast som DotCode kan avkoda. Den möjliggör kodning av flerspråkig text, binära blobbar och strukturerad data i en enda 2d-matrisstreckkod, vilket gör den idealisk för leveranskedjor, sjukvård och IoT‑scenarier.

## Varför använda Aspose.BarCode för denna uppgift?

Aspose.BarCode bearbetar **upp till 500 sidor per sekund** på vanlig serverhårdvara och stöder **över 30 streckkodssymboler**, inklusive DotCode. Dess `GetExtendedCodetext`‑API garanterar korrekt placering av kontrolltecken, eliminerar manuella strängkonkateneringsfel och säkerställer efterlevnad av ISO/IEC 24724. Dessutom erbjuder den inbyggd felkorrigering och automatisk hantering av tyst zon, vilket minskar behovet av manuell justering.

## Förutsättningar

- **Aspose.BarCode for .NET** – ladda ner från [Aspose.BarCode for .NET-dokumentationen](https://reference.aspose.com/barcode/net/).  
- En .NET‑utvecklingsmiljö (Visual Studio 2022 eller senare rekommenderas).  
- Valfritt: en tillfällig licensfil för utvärdering.

## Importera namnrymder

`using Aspose.BarCode.Generation;`  
`using Aspose.BarCode.ComplexBarcodes;`  

Dessa namnrymder exponerar klassen `BarcodeGenerator` och hjälparklassen `DotCodeExtendedCodetextBuilder` som behövs för exemplet.

```csharp
using Aspose.BarCode.Generation;
```

Nu när vi har täckt förutsättningarna, låt oss bryta ner processen för att generera DotCode Extended Code Text i en steg‑för‑steg‑guide.

## Steg 1: definiera katalogsökvägen

Ange var den genererade PNG‑filen ska sparas. Använd en absolut eller relativ sökväg som din applikation kan skriva till.

```csharp
string path = "Your Directory Path";
```

Ersätt `"Your Directory Path"` med den faktiska sökvägen på ditt system.

## Steg 2: skapa dotcode utökad kodtext

`DotCodeExtendedCodetextBuilder`‑klassen samlar de olika segmenten till en enda utökad kodtextsträng.

För att skapa DotCode Extended Code Text, följ dessa delsteg:

### 2.1 lägg till fnc1 formatidentifierare

FNC1‑formatidentifieraren markerar början på ett nytt datafält. Den krävs för GS1‑kompatibla DotCode‑symboler.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 lägg till ecicodetext

ECICodetext kodar specialtecken och internationell text. I detta exempel kodar vi `"犬Right狗"` med UTF‑8.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 lägg till vanlig kodtext

Du kan också lägga till vanlig text till DotCode Extended Code Text. Här lägger vi till `"Plain text"`.

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 lägg till fnc3 symbolseparator

FNC3‑symbolseparatorn separerar olika sektioner av koden, vilket förbättrar läsbarheten för skannrar.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 lägg till fnc3 läsarinitalisering

Detta steg lägger till FNC3 Reader Initialization‑informationen, som talar om för skannern hur den ska tolka följande data.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 generera kodtext

Generera nu DotCode Extended Codetext genom att anropa `GetExtendedCodetext`‑metoden på `textBuilder`‑objektet.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## Steg 3: generera dotcode‑bild

Rendera streckkodsbilden från den utökade kodtexten.

#### 3.1 initiera streckkodsgenerator

`BarcodeGenerator`‑klassen är Aspose.BarCode:s kärnobjekt för att skapa vilken streckkod som helst. Du instansierar den med önskad symbolik (`EncodeTypes.DotCode`) och den utökade kodtext du just byggt.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Slutligen anropar du `Save` för att skriva PNG‑filen till disk. Bilden är klar för inbäddning i rapporter, mobilappar eller tryckta etiketter.

## Vanliga problem och lösningar

- **Fel kodning** – Se till att du använder `ECIEncodings.UTF8` när du lägger till flerspråkig text; annars kan tecken bli förvrängda.  
- **Fil‑åtkomstfel** – Verifiera att applikationen har skrivrättigheter till mål katalogen.  
- **Tyst zon saknas** – Ställ in `gen.Parameters.Barcode.Margin` om skannrar kräver extra vitt utrymme runt symbolen.

## Vanliga frågor

**Q: Kan jag använda den genererade streckkoden i en mobilapp?**  
A: Ja. PNG‑bilden som genereras av generatorn kan bäddas in i iOS, Android eller någon cross‑platform‑mobilapplikation.

**Q: Vad händer om jag behöver koda binär data istället för text?**  
A: Använd `AddECICodetext`‑metoden med lämplig `ECIEncodings` (t.ex. `ECIEncodings.Base64`) för att bädda in binära nyttolaster.

**Q: Hur ändrar jag streckkodens storlek utan att påverka läsbarheten?**  
A: Justera egenskapen `XDimension.Pixels`; högre värden ökar modulstorleken, medan lägre värden gör streckkoden mer kompakt.

**Q: Finns det ett sätt att lägga till en tyst zon runt streckkoden?**  
A: Ja. Ställ in `gen.Parameters.Barcode.Margin` för att definiera önskad tyst zon i pixlar.

**Q: Stöder biblioteket .NET 8?**  
A: De senaste Aspose.BarCode‑utgåvorna är kompatibla med .NET 8; referera bara till rätt NuGet‑paketversion.

Om du behöver ytterligare vägledning eller har frågor, tveka inte att besöka [Aspose.BarCode för .NET-dokumentationen](https://reference.aspose.com/barcode/net/) eller delta i gemenskapen på [Aspose.BarCode supportforum](https://forum.aspose.com/c/barcode/13).

---

**Senast uppdaterad:** 2026-09-28  
**Testat med:** Aspose.BarCode 24.12 för .NET  
**Författare:** Aspose

## Relaterade handledningar

- [Skapa DotCode-streckkod .NET (Auto‑läge) med Aspose.BarCode](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)
- [Hur man genererar DataMatrix‑streckkoder med Aspose.BarCode för .NET – Steg‑för‑steg‑guide](/barcode/net/datamatrix-barcode-configuration/)
- [Hur man skapar Aztec‑streckkod med Aspose.BarCode för .NET](/barcode/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}