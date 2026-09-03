---
date: 2026-09-03
description: Lär dig hur du genererar streckkod från en sträng med Aspose.BarCode
  för .NET. Detta streckkodsgenereringsexempel i C# visar steg‑för‑steg‑skapandet
  av en GS1 Coupon UPC‑A Code 128.
keywords:
- generate barcode from string
- how to generate barcode
- convert text to barcode
- generate code 128 barcode
- barcode generation tutorial c#
lastmod: 2026-09-03
linktitle: Generera streckkod från sträng – GS1 Coupon UPC-A Code 128
og_description: Generera streckkod från en sträng med Aspose.BarCode för .NET. Denna
  guide visar ett steg‑för‑steg C#‑exempel för att snabbt skapa en GS1 Coupon UPC‑A
  Code 128 streckkod.
og_image_alt: Tutorial showing how to generate a GS1 Coupon UPC‑A Code 128 barcode
  from a string in C# using Aspose.BarCode
og_title: Generera streckkod från sträng – GS1 Coupon UPC-A Code 128
schemas:
- author: Aspose
  dateModified: '2026-09-03'
  description: Learn how to generate barcode from string using Aspose.BarCode for
    .NET. This barcode generation tutorial C# example shows step‑by‑step creation
    of a GS1 Coupon UPC‑A Code 128.
  headline: Generate barcode from string – GS1 Coupon UPC-A Code 128
  type: TechArticle
- description: Learn how to generate barcode from string using Aspose.BarCode for
    .NET. This barcode generation tutorial C# example shows step‑by‑step creation
    of a GS1 Coupon UPC‑A Code 128.
  name: Generate barcode from string – GS1 Coupon UPC-A Code 128
  steps:
  - name: set the directory path
    text: Begin by defining the directory path where you want to save the generated
      barcode image. Replace `"Your Directory Path"` with the actual path on your
      system.
  - name: create a barcode generator
    text: '`BarcodeGenerator` is Aspose.BarCode''s core class that creates barcode
      images from supplied data. Initialize a `BarcodeGenerator` object with the desired
      encoding type and data to encode. You can replace the data with your own if
      needed.'
  - name: customize barcode parameters
    text: You can fine‑tune various parameters for your barcode, such as the X‑Dimension
      (size of the smallest bar), image format, and more. In this example, we set
      the X‑Dimension to 2 pixels. Feel free to adjust these parameters according
      to your project requirements.
  - name: save the barcode image
    text: Now, save the generated barcode as an image in your specified directory.
      We are saving it in PNG format. You can change the filename and image format
      as needed. By following these four simple steps, you've successfully generated
      a GS1 Coupon UPC‑A Code 128 barcode using Aspose.BarCode for .NET.
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode for .NET fully supports .NET Core 3.1 and later, as
      well as .NET 5/6.
    question: Does the library support .NET Core?
  - answer: Absolutely. Use `BarCodeImageFormat.Svg` or `Pdf` when calling `gen.Save()`.
    question: Can I generate barcodes in vector formats?
  - answer: Set `gen.Parameters.Barcode.CodeTextParameters.ShowCodeText = true;` and
      adjust font settings via `CodeTextParameters`.
    question: How do I add a human‑readable caption below the barcode?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- barcode generation
- Aspose.BarCode
- .NET barcode
title: Generera streckkod från sträng – GS1 Coupon UPC-A Code 128
url: /sv/net/gs1-barcode-encoding/gs1-coupon-upc-a-code-128-encoding/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GS1 Coupon UPC-A Code 128 kodning

## Introduktion

Streckkoder är de tysta arbetskraftarna bakom butikshyllor, lager och till och med mobila kuponger. Om du någonsin har behövt **generera streckkod från sträng**‑data i en .NET‑applikation, ger Aspose.BarCode för .NET dig ett rent och pålitligt sätt att göra det. I den här **barcode generation tutorial C#** kommer du att se ett komplett **barcode generator C# example** som skapar en GS1 Coupon UPC‑A Code 128‑streckkod från en enkel textsträng. När du är klar med den här guiden kan du bädda in streckkoder direkt i dina egna projekt utan att kämpa med låg‑nivå kodningslogik.

## Snabba svar
- **Vad gör huvud‑API‑et?** Det konverterar en vanlig sträng till en fullt kompatibel GS1 Coupon UPC‑A Code 128‑streckkod.  
- **Vilket bibliotek krävs?** Aspose.BarCode för .NET (tillgängligt som en gratis provversion).  
- **Behöver jag en licens för utveckling?** Nej, provversionen fungerar för utveckling och testning.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Hur lång tid tar implementeringen?** Ungefär 5‑10 minuter för att få en fungerande bild.

## Förutsättningar

Innan du dyker in i streckkodsgenerering med Aspose.BarCode för .NET är det viktigt att du har de nödvändiga verktygen och kunskapen tillgänglig.

1. En utvecklingsmiljö: Se till att du har en fungerande utvecklingsmiljö installerad. Detta inkluderar Visual Studio eller någon annan IDE du föredrar för att skriva och kompilera din .NET‑kod.

2. Aspose.BarCode för .NET‑biblioteket: Du måste ha Aspose.BarCode för .NET installerat på ditt system. Om du inte redan har gjort det kan du ladda ner det från [Aspose.BarCode för .NET nedladdningssida](https://releases.aspose.com/barcode/net/).

3. Grundläggande C#‑kunskaper: Bekantskap med programmeringsspråket C# är ett måste eftersom du kommer att skriva kod för att generera streckkoder.

## Importera namnrymder

Nu när du har gått igenom förutsättningarna är det dags att förstå vilka namnrymder som behövs för att arbeta med Aspose.BarCode för .NET.

1. Inkludera Aspose.BarCode‑namnrymden: Börja med att inkludera Aspose.BarCode‑namnrymden i ditt projekt. Här finns all funktionalitet för streckkodsgenerering.

   ```csharp
   using Aspose.BarCode;
   ```

2. Ytterligare namnrymder: Beroende på dina specifika krav kan du behöva inkludera andra namnrymder för bildmanipulation eller filhantering. Till exempel:

   ```csharp
   using System;
   using System.IO;
   ```

Med dessa namnrymder tillagda i ditt projekt är du nu redo att skapa och anpassa streckkoder.

## Vad är en GS1 Coupon UPC‑A Code 128?

En GS1 Coupon UPC‑A Code 128‑streckkod kodar den standardiserade 12‑siffriga UPC‑A‑numeriska datan tillsammans med GS1‑applikationsidentifierare som bär kupongspecifik information såsom rabattvärde eller utgångsdatum. Formatet följer GS1‑specifikationerna och använder Code 128‑symbolik för att representera både den numeriska produktkoden och AI‑prefixad data i en enda linjär streckkod.

## Varför använda Aspose.BarCode för detta?

Eftersom Aspose.BarCode implementerar hela GS1‑specifikationen, hanterar automatiskt kontrollsiffror, AI‑formatering och högupplöst rendering, så att du kan generera kompatibla UPC‑A Code 128‑kuponger med ett enda API‑anrop. Biblioteket stödjer också över 50 utdataformat, batch‑bearbetning och fin‑granulär visuell anpassning utan externa beroenden.

## Steg‑för‑steg‑guide för att generera streckkod från sträng – GS1 Coupon UPC‑A Code 128

Låt oss gå igenom steg‑för‑steg‑processen för att generera en GS1 Coupon UPC‑A Code 128‑streckkod med Aspose.BarCode för .NET. I detta exempel delar vi upp koden i hanterbara steg för tydlig förståelse.

### Steg 1: ange katalogsökvägen

Börja med att definiera katalogsökvägen där du vill spara den genererade streckkodsbilden.

```csharp
string path = "Your Directory Path";
```

Byt ut `"Your Directory Path"` mot den faktiska sökvägen på ditt system.

### Steg 2: skapa en streckkodsgenerator

`BarcodeGenerator` är Aspose.BarCode:s kärnklass som skapar streckkods‑bilder från angivna data. Initiera ett `BarcodeGenerator`‑objekt med önskad kodningstyp och data att kodas.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.UpcaGs1Code128Coupon, "123456789012(8110)ASPOSE");
```

Du kan ersätta datan med din egen om så önskas.

### Steg 3: anpassa streckkodens parametrar

Du kan finjustera olika parametrar för din streckkod, såsom X‑Dimension (storleken på den minsta stapeln), bildformat och mer. I detta exempel sätter vi X‑Dimension till 2 pixlar.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

Känn dig fri att justera dessa parametrar enligt dina projektkrav.

### Steg 4: spara streckkodsbilden

Spara nu den genererade streckkoden som en bild i den angivna katalogen. Vi sparar den i PNG‑format.

```csharp
gen.Save($"{path}Gs1CouponUpcaCode128.png", BarCodeImageFormat.Png);
```

Du kan ändra filnamnet och bildformatet efter behov.

Genom att följa dessa fyra enkla steg har du framgångsrikt genererat en GS1 Coupon UPC‑A Code 128‑streckkod med Aspose.BarCode för .NET.

## Vanliga användningsområden

- **Butikskuponger** – bädda in rabattinformation direkt på produktförpackningen.  
- **Lageretikettering** – kombinera produkt‑ID:n med batch‑ eller utgångsdata.  
- **Mobila kampanjer** – generera utskrivbara streckkoder för kuponginlösen utan QR‑kod.  

## Felsökning och tips

- **Sökvägsproblem** – säkerställ att katalogen finns och att applikationen har skrivbehörighet.  
- **Ogiltigt dataformat** – strängen måste följa GS1‑syntaxen (`(AI)Data`).  
- **Bildkvalitet** – öka `XDimension` för högre upplösning vid utskrift.  

## Slutsats

I den här handledningen har vi gjort en djupdykning i streckkodsgenerering med Aspose.BarCode för .NET. Vi har gått igenom förutsättningar, importerat nödvändiga namnrymder och steg för steg gått igenom ett praktiskt **barcode generator C# example**. Med denna kunskap kan du nu **generera streckkod från sträng**‑data för alla GS1‑kompatibla scenarier, oavsett om det är en kupong, lageretikett eller anpassad kampanj.

Aspose.BarCode för .NET erbjuder en mångsidig och användarvänlig lösning för alla dina behov av streckkodsgenerering. Oavsett om du hanterar lager, spårar produkter eller kodar data förenklar detta bibliotek processen.

Om du har frågor eller behöver ytterligare hjälp, tveka inte att besöka [Aspose.BarCode‑dokumentationen](https://reference.aspose.com/barcode/net/) eller söka stöd i [Aspose.BarCode‑forumet](https://forum.aspose.com/c/barcode/13).

## Vanliga frågor (FAQ)

### Q: Kan jag använda Aspose.BarCode för .NET i kommersiella projekt?
A: Ja, Aspose.BarCode för .NET är lämpligt för både personliga och kommersiella projekt. Du kan köpa en licens på [Aspose.BarCode‑licensköpssida](https://purchase.aspose.com/buy).

### Q: Finns det en gratis provversion av Aspose.BarCode för .NET?
A: Ja, du kan ladda ner en gratis provversion på [Aspose.BarCode‑gratis provnedladdning](https://releases.aspose.com/). Den låter dig testa bibliotekets funktioner innan du köper.

### Q: Hur kan jag få en tillfällig licens för Aspose.BarCode för .NET?
A: Om du behöver en tillfällig licens för utvärdering eller testning kan du begära en på [tillfällig licens‑förfrågningssida](https://purchase.aspose.com/temporary-license/).

### Q: Kan jag anpassa utseendet på genererade streckkoder ytterligare?
A: Absolut. Aspose.BarCode för .NET erbjuder olika parametrar och inställningar för att anpassa både utseende och beteende för dina streckkoder. Du kan utforska dokumentationen för fler detaljer.

### Q: Finns det andra kodningstyper som stöds av Aspose.BarCode för .NET?
A: Ja, Aspose.BarCode för .NET stödjer ett brett spektrum av kodningstyper, inklusive UPC‑A, Code 128, QR‑koder och många fler. Den kompletta listan finns i dokumentationen.

## Ytterligare vanliga frågor

**Q: Stöder biblioteket .NET Core?**  
A: Ja, Aspose.BarCode för .NET har full support för .NET Core 3.1 och senare, samt .NET 5/6.

**Q: Kan jag generera streckkoder i vektorformat?**  
A: Absolut. Använd `BarCodeImageFormat.Svg` eller `Pdf` när du anropar `gen.Save()`.

**Q: Hur lägger jag till en människoläsbar bildtext under streckkoden?**  
A: Sätt `gen.Parameters.Barcode.CodeTextParameters.ShowCodeText = true;` och justera teckensnittsinställningarna via `CodeTextParameters`.

---

**Senast uppdaterad:** 2026-09-03  
**Testat med:** Aspose.BarCode för .NET 24.11  
**Författare:** Aspose

## Relaterade handledningar

- [Generera Aztec‑streckkod med textkodning med Aspose.BarCode för .NET](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)
- [Hur man genererar DataMatrix‑streckkoder med Aspose.BarCode för .NET – steg‑för‑steg‑guide](/barcode/net/datamatrix-barcode-configuration/)
- [Generera endimensionella Databar 2D‑streckkoder med Aspose.BarCode .NET‑API](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}