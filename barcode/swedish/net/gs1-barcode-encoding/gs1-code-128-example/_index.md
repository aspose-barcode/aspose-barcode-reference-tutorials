---
date: 2026-09-08
description: Lär dig hur du skapar code 128‑streckkod och genererar GS1‑streckkoder
  i C# med Aspose.BarCode för .NET. Steg‑för‑steg‑guide, förutsättningar och kod‑fri
  anpassning.
keywords:
- create code 128 barcode
- generate gs1 barcode
- how to generate barcode
- create barcode from data
- step by step barcode
lastmod: 2026-09-08
linktitle: GS1 Code 128‑exempel
og_description: Lär dig hur du skapar code 128‑streckkod och genererar GS1‑streckkoder
  i C# med Aspose.BarCode för .NET. Följ en steg‑för‑steg‑guide för att snabbt generera
  och spara barcode images.
og_image_alt: 'Developer guide: create code 128 barcode with Aspose.BarCode .NET'
og_title: Så skapar du code 128‑streckkod med GS1 med Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-08'
  description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  headline: How to create code 128 barcode with GS1 using Aspose.BarCode
  type: TechArticle
- description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  name: How to create code 128 barcode with GS1 using Aspose.BarCode
  steps:
  - name: set your directory path
    text: Define the folder where the generated image will be stored. Keeping the
      path configurable makes the code reusable across environments. Replace `"Your
      Directory Path"` with an absolute or relative path that your application can
      write to, such as `@"C:\Barcodes"` or `Path.Combine(Environment.CurrentDi
  - name: create a GS1 Code 128 barcode
    text: Create the barcode generator, specify the symbology, and provide GS1‑formatted
      data. The data string must include Application Identifiers wrapped in parentheses.
      The example uses the GTIN `(01)12345678901231`, a serial number `(21)ASPOSE`,
      and an additional custom AI `(30)9876`. Aspose.BarCode autom
  - name: customize barcode parameters
    text: Adjust visual parameters such as `XDimension` (the width of the narrow bar)
      to control the barcode’s density. You can also modify height, colors, and margins.
      Setting `XDimension = 2` yields a barcode that is easily scannable by most handheld
      readers while keeping the image size modest.
  - name: save the barcode image
    text: Persist the generated barcode to disk. You may choose PNG for lossless quality,
      JPEG for smaller files, or TIFF for printing workflows. The `Save` method writes
      the image file in the format indicated by the file extension. Replace `GS1Code128Example.png`
      with any valid filename and extension that ma
  - name: verify the barcode (optional)
    text: After saving, you can load the image back into your application or use a
      barcode scanner to confirm that the encoded data matches the original string.
      This step is useful during development and automated testing.
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode works with .NET Core and .NET 5/6, so you can expose
      a lightweight REST endpoint that returns barcode images on demand.
    question: Can I generate barcodes in a web API without installing the full .NET
      Framework?
  - answer: Absolutely. Loop through a collection of data strings, instantiate a `BarcodeGenerator`
      for each, and call `Save` inside the loop. The library is thread‑safe for parallel
      processing.
    question: Does the library support batch generation of multiple barcodes?
  - answer: Use Aspose.PDF to create a PDF document, then call `PdfPage.AddImage`
      with the barcode image stream. This avoids writing intermediate files to disk.
    question: Is there a way to embed the barcode directly into a PDF?
  - answer: Set `BarcodeGenerator.Options.Barcode.XDimension` to at least 0.33 mm
      and enable `BarHeight` according to the label size. Aspose.BarCode validates
      the AI format and throws an exception for invalid data.
    question: How can I ensure the barcode meets ISO/GS1 quality standards?
  - answer: Aspose offers perpetual, subscription, and cloud‑based licensing models.
      A trial license works for evaluation, but a paid license removes the evaluation
      watermark and unlocks all features.
    question: What licensing options are available for production use?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- create code 128 barcode
- Aspose.BarCode
- .NET barcode generation
title: Så skapar du code 128‑streckkod med GS1 med Aspose.BarCode
url: /sv/net/gs1-barcode-encoding/gs1-code-128-example/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar code 128 streckkod med GS1 med Aspose.BarCode

I den här handledningen kommer du att lära dig hur du **skapar code 128 streckkod** som följer GS1‑standarden med hjälp av Aspose.BarCode‑biblioteket för .NET. Oavsett om du behöver en streckkod för lager, frakt eller kassa, guidar den dig genom varje steg—från att sätta upp utvecklingsmiljön till att spara den slutliga bilden—så att du kan börja generera pålitliga streckkoder på några minuter.

## Snabba svar
- **Vad är den primära klassen för att generera en streckkod?** `BarcodeGenerator` skapar och konfigurerar streckkodsbilden.  
- **Vilken symbologi använder GS1 Code 128?** Den använder typen `EncodeTypes.Code128` med GS1‑specifik dataformatering.  
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för utvärdering; en kommersiell licens krävs för produktion.  
- **Kan jag ändra bildformatet?** Ja—spara som PNG, JPEG, BMP eller TIFF genom att ändra filändelsen.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ och .NET 6+.

## Vad är create code 128 barcode?
`create code 128 barcode` avser att generera en linjär streckkod som kodar alfanumerisk data med Code 128‑symbologi, vilket är allmänt använt inom logistik eftersom det stödjer hela ASCII‑uppsättningen och kan bädda in GS1‑applikationsidentifierare. Streckkoden kan lagra produktidentifierare, serienummer och annan anpassad data, vilket gör den lämplig för ett brett spektrum av affärsscenarier.

## Varför använda Aspose.BarCode för GS1 Code 128?
Aspose.BarCode stödjer **30+ streckkodssymbologier** och kan rendera bilder upp till **10 000 × 10 000 px** utan kvalitetsförlust, vilket gör den lämplig för högupplöst etikettutskrift. Biblioteket validerar också automatiskt GS1‑datastrukturer, vilket minskar risken för felaktiga streckkoder i produktionslinjer. Dessutom erbjuder det omfattande anpassningsalternativ för storlek, färg och layout, vilket hjälper till att uppfylla strikta branschstandarder.

## Förutsättningar
Innan du börjar, se till att du har följande:

1. **.NET‑utvecklingsmiljö** – Visual Studio 2022, Rider eller någon IDE som stödjer .NET 6+.  
2. **Aspose.BarCode för .NET** – ladda ner det från **Aspose.BarCode för .NET nedladdningssida** på [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/) och lägg till NuGet‑paketet `Aspose.BarCode` i ditt projekt.  
3. **Grundläggande C#‑kunskaper** – du bör vara bekväm med att skapa konsol‑ eller Windows‑applikationer.  
4. **Förståelse för GS1 Code 128** – valfritt men hjälpsamt; GS1 använder applikationsidentifierare (AI) som `(01)` för GTIN och `(21)` för serienummer.

## Så skapar du code 128 streckkod steg för steg

Läs in biblioteket, konfigurera streckkodstypen, ange GS1‑data, anpassa dimensioner och spara slutligen bilden. Det direkta svaret på frågan “hur skapar man code 128 streckkod?” är: **instansiera `BarcodeGenerator` med `EncodeTypes.Code128` och GS1‑formaterad data, justera `XDimension` om behövs, och sedan anropa `Save` med önskat filnamn och format**. Följande avsnitt bryter ner varje steg.

### Steg 1: ange din katalogsökväg
Definiera mappen där den genererade bilden ska lagras. Att hålla sökvägen konfigurerbar gör koden återanvändbar i olika miljöer.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Byt ut `"Your Directory Path"` mot en absolut eller relativ sökväg som din applikation kan skriva till, till exempel `@"C:\\Barcodes"` eller `Path.Combine(Environment.CurrentDirectory, "Output")`.

### Steg 2: skapa en GS1 Code 128 streckkod
Skapa streckkodsgeneratorn, specificera symbologin och ange GS1‑formaterad data. Datasträngen måste innehålla applikationsidentifierare omslutna av parenteser.

```csharp
string path = "Your Directory Path";
```

Exemplet använder GTIN `(01)12345678901231`, ett serienummer `(21)ASPOSE` och en ytterligare anpassad AI `(30)9876`. Aspose.BarCode infogar automatiskt det nödvändiga FNC1‑tecknet för GS1‑efterlevnad.

### Steg 3: anpassa streckkodens parametrar
Justera visuella parametrar såsom `XDimension` (bredden på den smala stapeln) för att kontrollera streckkodens täthet. Du kan också ändra höjd, färger och marginaler.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1Code128, "(01)12345678901231(21)ASPOSE(30)9876");
```

Att sätta `XDimension = 2` ger en streckkod som enkelt kan skannas av de flesta handhållna läsare samtidigt som bildstorleken hålls måttlig.

### Steg 4: spara streckkodsbilden
Spara den genererade streckkoden till disk. Du kan välja PNG för förlustfri kvalitet, JPEG för mindre filer eller TIFF för utskriftsflöden. Metoden `Save` skriver bildfilen i det format som anges av filändelsen.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

Byt ut `GS1Code128Example.png` mot ett giltigt filnamn och en filändelse som matchar ditt önskade utdataformat.

### Steg 5: verifiera streckkoden (valfritt)
Efter sparandet kan du läsa in bilden tillbaka i din applikation eller använda en streckkodsläsare för att bekräfta att den kodade datan matchar den ursprungliga strängen. Detta steg är användbart under utveckling och automatiserade tester.

```csharp
gen.Save($"{path}GS1Code128Example.png", BarCodeImageFormat.Png);
```

## Vanliga problem och felsökningstips
- **FNC1 upptäcks inte** – Se till att datasträngen börjar med en öppningsparentes och innehåller giltiga GS1‑AI:n; biblioteket infogar FNC1 automatiskt endast för igenkända mönster.  
- **Bild sparas inte** – Verifiera att mål katalogen finns och att applikationen har skrivrättigheter. Använd `Directory.CreateDirectory(path)` för att skapa den vid behov.  
- **Streckkoden för tät** – Minska `XDimension` eller öka bildhöjden för att ge läsare mer utrymme att läsa smala staplar.  
- **Ej stödjade tecken** – Code 128 kan endast koda hela ASCII‑uppsättningen; undvik Unicode‑tecken utanför detta intervall.

## Vanliga frågor

**Q: Kan jag generera streckkoder i ett web‑API utan att installera hela .NET‑Frameworket?**  
A: Ja, Aspose.BarCode fungerar med .NET Core och .NET 5/6, så du kan exponera en lättviktig REST‑endpoint som returnerar streckkodsbilder på begäran.

**Q: Stöder biblioteket batch‑generering av flera streckkoder?**  
A: Absolut. Loop igenom en samling av datasträngar, instansiera en `BarcodeGenerator` för varje och anropa `Save` inom loopen. Biblioteket är trådsäkert för parallell bearbetning.

**Q: Finns det ett sätt att bädda in streckkoden direkt i en PDF?**  
A: Använd Aspose.PDF för att skapa ett PDF‑dokument, och anropa sedan `PdfPage.AddImage` med streckkodsbildens ström. Detta undviker att skriva mellanfiler till disk.

**Q: Hur kan jag säkerställa att streckkoden uppfyller ISO/GS1‑kvalitetsstandarder?**  
A: Ställ in `BarcodeGenerator.Options.Barcode.XDimension` till minst 0,33 mm och aktivera `BarHeight` enligt etikettens storlek. Aspose.BarCode validerar AI‑formatet och kastar ett undantag för ogiltig data.

**Q: Vilka licensalternativ finns tillgängliga för produktionsanvändning?**  
A: Aspose erbjuder eviga, prenumerations‑ och molnbaserade licensmodeller. En provlicens fungerar för utvärdering, men en betald licens tar bort vattenstämpeln för utvärdering och låser upp alla funktioner.

## Ytterligare resurser

- **Dokumentation** – Tillgång till fullständig API‑referens på [https://reference.aspose.com/barcode/net/](https://reference.aspose.com/barcode/net/).  
- **Nedladdning** – Hämta den senaste biblioteksversionen från [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/).  
- **Gratis prov** – Starta en 30‑dagars provperiod på [https://releases.aspose.com/](https://releases.aspose.com/).  
- **Köp** – Köp en kommersiell licens på [https://purchase.aspose.com/buy](https://purchase.aspose.com/buy).  
- **Support** – Gå med i community‑forumet på [https://forum.aspose.com/c/barcode/13](https://forum.aspose.com/c/barcode/13) för hjälp med felsökning.

---

**Senast uppdaterad:** 2026-09-08  
**Testad med:** Aspose.BarCode 24.11 för .NET  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man skapar ITF-14 streckkod .NET – Omfattande Aspose.BarCode-handledningar](/barcode/net/)
- [Generera endimensionella Databar 2D streckkoder med Aspose.BarCode .NET API](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}