---
date: 2026-09-28
description: Lär dig hur du skapar barcode custom space för GS1‑kuponger med Aspose.BarCode
  för .NET och öka barcode‑läsbarheten. Följ vår steg‑för‑steg‑guide.
keywords:
- create barcode custom space
- GS1 coupon supplement
- Aspose.BarCode .NET
- increase barcode readability
lastmod: 2026-09-28
linktitle: GS1 Coupon Supplement Space Konfiguration
og_description: Lär dig hur du skapar barcode custom space för GS1‑kuponger med Aspose.BarCode
  för .NET och öka barcode‑läsbarheten. Steg‑för‑steg‑kod och tips ingår.
og_image_alt: Screenshot of a GS1 coupon barcode generated with custom supplement
  space using Aspose.BarCode for .NET
og_title: Skapa barcode custom space för GS1 coupon supplement – Aspose.BarCode .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  headline: How to create barcode custom space for GS1 coupon supplement
  type: TechArticle
- description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  name: How to create barcode custom space for GS1 coupon supplement
  steps:
  - name: '**Visual Studio** – The primary IDE for .NET development.'
    text: '**Visual Studio** – The primary IDE for .NET development.'
  - name: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
  - name: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
    text: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
  - name: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
    text: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
  - name: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
    text: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
  - name: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
    text: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
  type: HowTo
- questions:
  - answer: It adds a mandatory blank margin around the supplemental data, improving
      scanner reliability and meeting retailer‑specified minimum widths.
    question: What is the purpose of the GS1 Coupon Supplement Space in barcodes?
  - answer: Yes, set `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` to any
      integer value; the library instantly applies the change to the generated image.
    question: Can I customize the width of the GS1 Coupon Supplement Space with Aspose.BarCode
      for .NET?
  - answer: Refer to the [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)
      and visit the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)
      for community assistance.
    question: Where can I find additional documentation and support for Aspose.BarCode
      for .NET?
  - answer: Absolutely. The API offers straightforward methods for quick tasks and
      advanced options for fine‑tuned barcode generation.
    question: Is Aspose.BarCode for .NET suitable for both beginners and experienced
      developers?
  - answer: Yes, request a trial license from the [Aspose temporary license website](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for Aspose.BarCode for .NET to evaluate
      its features?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- barcode configuration
- GS1 standards
- Aspose.BarCode
- .NET barcode generation
title: Hur man skapar barcode custom space för GS1 coupon supplement
url: /sv/net/gs1-barcode-encoding/gs1-coupon-supplement-space-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GS1 kupongtilläggsrymd konfiguration

I den här handledningen kommer du att **skapa anpassat utrymme för streckkoden** för GS1 kupongtilläggsrymd med Aspose.BarCode för .NET. Att justera tilläggsutrymmet är avgörande när du behöver **öka streckkodsläsbarheten** på lågupplösta skannrar eller följa återförsäljares föreskrivna marginaler. I slutet av den här guiden kommer du att förstå varför tilläggsutrymmet är viktigt, hur du ställer in det programatiskt och hur du genererar bilder med olika pixelvärden.

## Snabba svar
- **Vad styr tilläggsutrymmet?** Det definierar det tomma området (i pixlar) mellan kupongdata och resten av streckkoden.  
- **Vilken streckkodstyp används?** `EncodeTypes.UpcaGs1DatabarCoupon`.  
- **Kan jag ändra storleken på utrymmet?** Ja – sätt `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` till ett heltal.  
- **Behöver jag en licens för den här funktionen?** En tillfällig licens fungerar för utvärdering; en full licens krävs för produktion.  
- **Vilka utdataformat stöds?** PNG, JPEG, BMP, GIF, TIFF, och mer via `BarCodeImageFormat`.

## Vad är GS1 kupongtilläggsrymd?
GS1 kupongtilläggsrymd är ett definierat tomt område som visas i GS1‑Databar kupongstreckkoder. Återförsäljningssystem använder detta utrymme för att förbättra skanningspålitligheten och för att följa branschspecifikationer som kräver en minsta marginal runt den kompletterande datan.

## Varför konfigurera tilläggsutrymmet?
Tilläggsutrymmet ökar direkt **streckkodsläsbarheten** och hjälper dig att uppfylla strikta återförsäljarriktlinjer. Genom att lägga till extra pixlar minskar du sannolikheten för felavläsningar på lågupplösta skannrar, säkerställer konsekvent skanning över olika etikettstorlekar och ger dig visuell flexibilitet att balansera streckkoden i en tryckt layout.

## Förutsättningar

Innan vi går in på att konfigurera GS1 kupongtilläggsrymd med Aspose.BarCode för .NET, se till att du har följande:

1. **Visual Studio** – Den primära IDE:n för .NET‑utveckling.  
2. **Aspose.BarCode for .NET** – Ladda ner biblioteket från [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).  
3. **.NET Framework or .NET 5+** – Kunskap om C# och .NET‑runtime krävs.

Nu när miljön är klar, låt oss gå vidare till implementeringen.

## Importera namnrymder

`Aspose.BarCode.Generation`‑namnrymden innehåller `BarcodeGenerator`‑klassen och relaterade inställningar.

```csharp
using Aspose.BarCode;
```

## Steg 1: definiera sökvägen

Välj en mapp där de genererade bilderna ska sparas. Sökvägen måste avslutas med rätt katalogseparator för ditt operativsystem.

```csharp
string path = "Your Directory Path";
```

## Steg 2: generera konfiguration för GS1 kupongtilläggsrymd

Följande kodsnutt skapar en streckkod, sätter X‑dimensionen och justerar tilläggsutrymmet.

```csharp
System.Console.WriteLine("Gs1CouponSupplementSpace:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.UpcaGs1DatabarCoupon, "123456789012(8110)ASPOSE");
gen.Parameters.Barcode.XDimension.Pixels = 2;

// Set coupon supplement space to 30 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 30;
gen.Save($"{path}Gs1CouponSpace30Pixels.png", BarCodeImageFormat.Png);

// Set coupon supplement space to 50 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 50;
gen.Save($"{path}Gs1CouponSpace50Pixels.png", BarCodeImageFormat.Png);
```

I det här exemplet gör vi:

1. **Skapa** en `BarcodeGenerator`‑instans för typen `UpcaGs1DatabarCoupon`.  
2. **Ställ in** X‑dimensionen till 2 pixlar, vilket bestämmer den smalaste stapelbredden.  
3. **Justera** `SupplementSpace.Pixels`‑egenskapen till 30 px, generera en bild, och upprepa sedan med 50 px.  

Känn dig fri att experimentera med andra pixelvärden för att passa ditt utskriftsflöde.

## Vanliga problem & tips

- **Ogiltig sökväg** – Se till att variabeln `path` avslutas med ett bakåtsnedstreck (`\`) eller snedstreck (`/`) som är lämpligt för ditt OS.  
- **Otillräckliga behörigheter** – Kör Visual Studio som administratör eller välj en mapp där applikationen har skrivbehörighet.  
- **Felaktigt dataformat** – Datatsträngen måste följa GS1‑syntaxen (`(8110)` anger tilläggsidentifieraren).  

## Varför detta är viktigt för ditt företag

Aspose.BarCode stöder **över 60 streckkodssymboler** och kan rendera bilder upp till **10 000 × 10 000 pixlar** utan att tömma minnet. För storskaliga återförsäljningsimplementationer betyder detta att du kan generera högupplösta GS1‑kuponger i batch‑läge samtidigt som bearbetningstiden hålls under en sekund per bild på vanlig serverhårdvara.

## Vanliga frågor

**Q: Vad är syftet med GS1 kupongtilläggsrymd i streckkoder?**  
A: Det lägger till en obligatorisk tom marginal runt den kompletterande datan, vilket förbättrar skanningspålitligheten och uppfyller återförsäljares specificerade minsta bredder.

**Q: Kan jag anpassa bredden på GS1 kupongtilläggsrymd med Aspose.BarCode för .NET?**  
A: Ja, sätt `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` till ett heltal; biblioteket tillämpar omedelbart ändringen på den genererade bilden.

**Q: Var kan jag hitta ytterligare dokumentation och support för Aspose.BarCode för .NET?**  
A: Se [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) och besök [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) för gemenskapsstöd.

**Q: Är Aspose.BarCode för .NET lämplig för både nybörjare och erfarna utvecklare?**  
A: Absolut. API‑et erbjuder enkla metoder för snabba uppgifter och avancerade alternativ för finjusterad streckkodsgenerering.

**Q: Kan jag få en tillfällig licens för Aspose.BarCode för .NET för att utvärdera dess funktioner?**  
A: Ja, begär en provlicens från [Aspose temporary license website](https://purchase.aspose.com/temporary-license/).

## Slutsats

Genom att följa stegen ovan vet du nu hur du **skapar anpassat utrymme för streckkoden** för GS1 kupongtilläggsrymd, en nyckelteknik för att **öka streckkodsläsbarheten** och uppfylla återförsäljningsstandarder. Integrera koden i dina befintliga skanningslösningar, experimentera med olika pixelvärden och utforska andra streckkodstyper som erbjuds av Aspose.BarCode för .NET.

---

**Senast uppdaterad:** 2026-09-28  
**Testat med:** Aspose.BarCode 24.12 for .NET  
**Författare:** Aspose

## Relaterade handledningar

- [Generera Aspose.BarCode Databar streckkod med .NET API – Rad‑ och kolumnkonfiguration](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Hur man genererar DataMatrix‑streckkoder med Aspose.BarCode för .NET – Steg‑för‑steg‑guide](/barcode/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}