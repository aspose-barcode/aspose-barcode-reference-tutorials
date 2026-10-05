---
category: general
date: 2026-08-22
description: Hur man ändrar streckkodsstorlek i C# med DataBar Stacked Omni‑Directional‑generatorn.
  Lär dig att ställa in X‑dimension och bildförhållande för PNG‑utdata.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to change barcode size
- DataBar Stacked Omni‑Directional barcode
- C# barcode generator
- barcode aspect ratio
- X‑dimension pixels
- BarCodeImageFormat PNG
language: sv
lastmod: 2026-08-22
og_description: Hur man ändrar streckkodsstorlek i C# med DataBar Stacked Omni‑Directional‑generatorn.
  Följ den steg‑för‑steg‑guiden för att justera X‑dimensionen och bildförhållandet.
og_image_alt: Screenshot showing how to change barcode size in C#
og_title: Hur man ändrar streckkodens storlek i C# – komplett guide
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  headline: How to change barcode size in C# with DataBar Stacked
  type: TechArticle
- description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  name: How to change barcode size in C# with DataBar Stacked
  steps:
  - name: Create a DataBar Stacked Omni‑Directional barcode generator
    text: The generator object holds all barcode settings. By passing `EncodeTypes.DatabarStackedOmniDirectional`
      and sample data, you create a valid barcode ready for further customization.
  - name: Set the basic module size (X‑dimension) in pixels
    text: The X‑dimension defines the width of a single barcode module. Adjusting
      it changes the overall width and height proportionally.
  - name: Change the barcode aspect ratio to 15 and save the image
    text: The **barcode aspect ratio** controls the height‑to‑width relationship.
      An aspect ratio of 15 yields a relatively tall barcode.
  - name: Change the barcode aspect ratio to 30 and save the new image
    text: Increasing the aspect ratio to 30 makes the barcode even taller, illustrating
      the flexibility of size adjustments.
  - name: Verify the generated images
    text: Open the PNG files in any image viewer. You should see two barcodes with
      identical width (controlled by the X‑dimension) but different heights (controlled
      by the aspect ratio). If the images appear blurry, increase the X‑dimension
      pixels; if they are too tall, lower the aspect ratio.
  - name: What to explore next
    text: '* **Custom colors** – experiment with `barcodeGenerator.Parameters.Barcode.ForeColor`
      and `BackColor` to match brand guidelines. * **Different barcode types** – replace
      `EncodeTypes.DatabarStackedOmniDirectional` with `EncodeTypes.QR` or `EncodeTypes.Code128`
      to see how size parameters differ across'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Hur man ändrar streckkodens storlek i C# med DataBar Stacked
url: /sv/python-java/general/how-to-change-barcode-size-in-c-with-databar-stacked/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så ändrar du streckkodsstorlek i C# med DataBar Stacked

Om du behöver **hur du ändrar streckkodsstorlek** i en .NET‑applikation, visar den här guiden de exakta stegen med DataBar Stacked Omni‑Directional‑streckkodsgeneratorn. Du kommer att se hur du styr X‑dimensionen i pixlar, justerar streckkodens bildförhållande och sparar resultatet som en PNG‑fil.

Att ändra streckkodsstorlek är ofta nödvändigt när det tryckta etikettutrymmet är begränsat eller när en bild med högre upplösning behövs för digitala kanaler. Denna handledning täcker allt du behöver, från att initiera generatorn till att producera två bilder med olika storlekar.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare installerad  
* En referens till NuGet‑paketet **Aspose.BarCode for .NET**  
* Grundläggande kunskap om C#‑syntax  

Ingen ytterligare konfiguration krävs; koden körs på Windows, Linux eller macOS.

## Så ändrar du streckkodsstorlek i C# – steg för steg

Följande avsnitt delar upp processen i diskreta, återanvändbara steg. Varje steg förklarar **varför** koden behövs, inte bara **vad** den gör.

### Steg 1: Skapa en DataBar Stacked Omni‑Directional‑streckkodsgenerator

Generator‑objektet innehåller alla streckkodinställningar. Genom att skicka `EncodeTypes.DatabarStackedOmniDirectional` och exempeldata skapar du en giltig streckkod som är redo för vidare anpassning.

```csharp
// Step 1: Create a DataBar Stacked Omni‑Directional barcode generator with sample data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

*Varför detta är viktigt* – **C# barcode generator**‑klassen kapslar in kodningsalgoritmen. Att börja med en giltig generator säkerställer att efterföljande storleksändringar påverkar rätt streckkodstyp.

### Steg 2: Ställ in grundmodulens storlek (X‑dimension) i pixlar

X‑dimensionen definierar bredden på en enskild streckkodmodul. Att justera den förändrar den totala bredden och höjden proportionellt.

```csharp
// Step 2: Define the basic module size (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Varför detta är viktigt* – En större X‑dimension ger en större streckkod, vilket är användbart för skrivare med låg upplösning. Omvänt skapar ett mindre värde en kompakt streckkod som passar för små etiketter.

### Steg 3: Ändra streckkodens bildförhållande till 15 och spara bilden

**Barcode aspect ratio** styr förhållandet mellan höjd och bredd. Ett bildförhållande på 15 ger en relativt hög streckkod.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

*Varför detta är viktigt* – Olika skanningsenheter har optimala bildförhållandekrav. Att sätta förhållandet till 15 demonstrerar hur du **hur du ändrar streckkodsstorlek** genom att modifiera höjden medan bredden bestäms av X‑dimensionen.

#### Expected output

Filen `DatabarAspectRatio15.png` visar en DataBar Stacked Omni‑Directional‑streckkod som är högre än standard. Streckkodens bredd speglar 2‑pixel X‑dimensionen, och höjden följer 15‑förhållandet.

### Steg 4: Ändra streckkodens bildförhållande till 30 och spara den nya bilden

Att öka bildförhållandet till 30 gör streckkoden ännu högre, vilket illustrerar flexibiliteten i storleksjusteringar.

```csharp
// Step 4: Change the DataBar aspect ratio to 30 and save the new image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

*Varför detta är viktigt* – Genom att byta **barcode aspect ratio**‑värde ser du omedelbart hur **hur du ändrar streckkodsstorlek** utan att återskapa generatorn. Detta sparar behandlingstid i batch‑scenarier.

#### Expected output

Filen `DatabarAspectRatio30.png` är tydligt högre än den föregående bilden, vilket bekräftar att bildförhållandet direkt påverkar streckkodens höjd.

### Steg 5: Verifiera de genererade bilderna

Öppna PNG‑filerna i någon bildvisare. Du bör se två streckkoder med identisk bredd (styrd av X‑dimensionen) men olika höjder (styrda av bildförhållandet). Om bilderna är suddiga, öka X‑dimensionens pixlar; om de är för höga, sänk bildförhållandet.

```csharp
// Optional verification code – load images and print dimensions
using (var img15 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio15.png"))
using (var img30 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio30.png"))
{
    Console.WriteLine($"15‑ratio size: {img15.Width}×{img15.Height}");
    Console.WriteLine($"30‑ratio size: {img30.Width}×{img30.Height}");
}
```

*Varför detta är viktigt* – Programmatisk verifiering säkerställer att storleksändringarna har tillämpats korrekt, vilket är avgörande för automatiserade byggpipelines.

## Vanliga variationer och kantfall

| Situation | Justering | Orsak |
|-----------|------------|--------|
| **Mycket små etiketter** | Ställ in `XDimension.Pixels = 1` och `AspectRatio = 10` | Minskar det totala fotavtrycket samtidigt som läsbarheten behålls |
| **Utskrift med hög upplösning** | Ställ in `XDimension.Pixels = 4` och `AspectRatio = 20` | Ökar pixeltätheten för skarp utskrift |
| **Annat bildformat** | Byt ut `BarCodeImageFormat.Png` mot `BarCodeImageFormat.Jpeg` | Användbart när PNG‑stöd är begränsat |
| **Dynamisk data** | Skicka en variabel sträng till `BarcodeGenerator`‑konstruktorn | Genererar streckkoder för varje produkt automatiskt |

När du behöver generera många streckkoder med varierande storlekar, slå in stegen i en metod:

```csharp
void GenerateDatabar(string data, int xDim, int aspectRatio, string filePath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
    generator.Parameters.Barcode.XDimension.Pixels = xDim;
    generator.Parameters.Barcode.DataBar.AspectRatio = aspectRatio;
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

Att anropa `GenerateDatabar("(01)98765432109876", 3, 25, "output.png")` producerar en streckkod med anpassad storlek i ett enda kodrader.

## Pro‑tips för pålitliga storleksändringar

* **Ställ alltid in X‑dimensionen före bildförhållandet.** Att ändra bildförhållandet först kan leda till oväntad skalning om X‑dimensionen har ett icke‑optimalt standardvärde.  
* **Använd en konsekvent utdatamapp.** Att hårdkoda `"YOUR_DIRECTORY"` fungerar för demonstrationer, men i produktion föredras `Path.Combine(Environment.CurrentDirectory, "Barcodes")`.  
* **Validera den genererade bildens storlek.** Små förändringar i X‑dimensionen kanske inte märks på skärmen; att kontrollera pixelmåtten garanterar att förändringen trätt i kraft.  

## Slutsats

Du vet nu **hur du ändrar streckkodsstorlek** i C# med DataBar Stacked Omni‑Directional‑streckkodsgeneratorn. Genom att justera **X‑dimension pixels** och **barcode aspect ratio** kan du producera PNG‑bilder som passar alla etikettstorlekar eller upplösningskrav. Det kompletta, körbara exemplet ovan demonstrerar hela arbetsflödet från generator‑skapande till storleksverifiering.

### Vad du kan utforska härnäst

* **Anpassade färger** – experimentera med `barcodeGenerator.Parameters.Barcode.ForeColor` och `BackColor` för att matcha varumärkesriktlinjer.  
* **Olika streckkodstyper** – ersätt `EncodeTypes.DatabarStackedOmniDirectional` med `EncodeTypes.QR` eller `EncodeTypes.Code128` för att se hur storleksparametrar skiljer sig mellan symbologier.  
* **Batch‑behandling** – kombinera `GenerateDatabar`‑metoden med en CSV‑import för att automatiskt skapa tusentals streckkoder.

Anpassa gärna kodsnuttarna till ditt projekts arkitektur, och låt streckkodsstorleksjusteringarna förbättra både skanningspålitlighet och visuell design. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

De följande handledningarna täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}