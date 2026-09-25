---
category: general
date: 2026-08-12
description: Exempel på streckkodsgenerator som visar hur man genererar streckkod
  med exakt pixelförstorlek. Lär dig att ställa in modulbredd, stapelhöjd och skapa
  Planet‑streckkoder.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to generate barcode
- barcode pixel size
- generate planet barcode
- barcode height setting
language: sv
lastmod: 2026-08-12
og_description: Exemplet på streckkodsgenerator visar hur man genererar en streckkod
  med exakta pixeldimensioner. Följ den här guiden för att kontrollera modulbredd
  och stapelhöjd för Planet‑ och RM4SCC‑koder.
og_image_alt: Screenshot of a barcode generator example showing a Planet barcode with
  custom pixel size
og_title: exempel på streckkodsgenerator – anpassa pixelstorlek i C#
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: barcode generator example that shows how to generate barcode with precise
    pixel size. Learn to set module width, bar height and create Planet barcodes.
  headline: barcode generator example – step‑by‑step guide for custom pixel sizes
  type: TechArticle
- description: barcode generator example that shows how to generate barcode with precise
    pixel size. Learn to set module width, bar height and create Planet barcodes.
  name: barcode generator example – step‑by‑step guide for custom pixel sizes
  steps:
  - name: Install the Aspose.BarCode package
    text: 'Open a terminal in your project folder and run:'
  - name: Add the necessary `using` directives
    text: '```csharp using Aspose.BarCode.Generation; using Aspose.BarCode.BarCodeImageFormat;
      ```'
  - name: – generate a Planet barcode with automatically calculated height
    text: '```csharp // Step 1: Generate a Planet barcode with automatically calculated
      height BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet,
      "123456");'
  - name: – generate a Planet barcode with an explicit 100‑pixel height
    text: '```csharp // Step 2: Generate a Planet barcode with an explicit 100‑pixel
      height BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet,
      "123456");'
  - name: – generate an RM4SCC barcode with the same explicit height
    text: '```csharp // Step 3: Generate an RM4SCC barcode with the same explicit
      height BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC,
      "123456");'
  - name: What is **barcode pixel size**?
    text: '*Pixel size* refers to the physical number of screen or printer pixels
      that represent a single module (`XDimension`). A larger pixel size yields a
      bigger barcode, which can be easier for low‑resolution scanners but consumes
      more label real‑estate.'
  - name: How does `BarHeight` affect readability?
    text: The `BarHeight` property controls the vertical length of the bars. Standards
      for most 1‑D barcodes (including Planet and RM4SCC) recommend a minimum height
      of 10 mm when printed at 300 dpi, which translates to roughly 118 pixels. Setting
      a height below that can cause read errors, especially on mobil
  - name: When should you let the library calculate height automatically?
    text: If you’re generating barcodes for on‑screen display only, the automatic
      calculation keeps the aspect ratio consistent and reduces the amount of manual
      tweaking needed. For printed labels that must meet strict ISO specifications,
      you should **explicitly set the bar height**.
  - name: Pro tip on performance
    text: When generating thousands of barcodes in a batch job, reuse a single `BarcodeGenerator`
      instance and only change the `CodeText` and size parameters between saves. This
      avoids repeated allocation of internal rendering objects and can cut execution
      time by up to 30 %.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Exempel på streckkodsgenerator – steg‑för‑steg‑guide för anpassade pixelstorlekar
url: /sv/python-java/general/barcode-generator-example-step-by-step-guide-for-custom-pixe/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# barcode generator example – steg‑för‑steg guide för anpassade pixelformater

Om du behöver ett **barcode generator example** som låter dig kontrollera varje pixel, visar den här guiden exakt hur du gör det. Du kommer att lära dig att ställa in modulbredden, definiera en fast stapelhöjd och generera både Planet‑ och RM4SCC‑streckkoder med förutsägbara dimensioner.

De flesta utvecklare har problem med “hur man genererar streckkod”‑bilder som ser likadana ut på varje skärm eller skrivare. Kodsnuttarna nedan löser problemet genom att exponera pixel‑nivå‑parametrarna i Aspose.BarCode för .NET‑biblioteket, så att du kan producera konsekvent output utan gissningar.

## Vad du kommer att lära dig

* Hur du installerar det nödvändiga NuGet‑paketet.  
* Hur du genererar en Planet‑streckkod med automatiskt beräknad höjd.  
* Hur du genererar en Planet‑streckkod med en explicit 100‑pixel‑höjd.  
* Hur du genererar en RM4SCC‑streckkod med samma explicita höjd.  
* Varför **barcode pixel size** är viktigt för skannings‑tillförlitlighet.  
* Tips för felsökning av vanliga problem när du genererar Planet‑streckkodsbilder.  

Du behöver bara .NET 6 eller senare, en grundläggande C#‑utvecklingsmiljö och en internetanslutning för att hämta NuGet‑paketet.

---

## barcode generator example – konfigurera utvecklingsmiljön

Innan du skriver någon kod, se till att Aspose.BarCode‑biblioteket är tillgängligt för ditt projekt.

### Install the Aspose.BarCode package

Öppna en terminal i din projektmapp och kör:

```bash
dotnet add package Aspose.BarCode
```

Kommandot lägger till den senaste stabila versionen av **Aspose.BarCode** i ditt `csproj`. När återställningen är klar kan du börja använda klassen `BarcodeGenerator`.

> **Pro tip:** Sikta på .NET 6 eller .NET 7 för att dra nytta av de senaste prestandaförbättringarna och standard‑UTF‑8‑hantering.

### Add the necessary `using` directives

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;
```

Dessa namnrymder exponerar `BarcodeGenerator`‑klassen och `BarCodeImageFormat`‑enum som används senare i handledningen.

---

## Hur du genererar streckkod med anpassad pixelform

De följande tre stegen illustrerar det kompletta **barcode generator example**. Varje steg bygger på det föregående, så du kan kopiera‑klistra in hela blocket i en konsolapp och köra det utan ändringar.

### Steg 1 – generera en Planet‑streckkod med automatiskt beräknad höjd

```csharp
// Step 1: Generate a Planet barcode with automatically calculated height
BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set module width (x‑dimension) to 4 pixels
planetAuto.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG
planetAuto.Save("PlanetAuto.png", BarCodeImageFormat.Png);
```

**Why this works:**  
*`XDimension`‑egenskapen definierar bredden på en enskild streckkodmodul (det minsta svarta eller vita elementet). När du utelämnar `BarHeight` beräknar biblioteket en höjd som behåller standard‑aspektförhållandet för Planet‑koder.*

**Expected output:** En PNG‑fil med namnet `PlanetAuto.png` som innehåller en ren Planet‑streckkod. Dess höjd anpassas till 4‑pixel‑modulbredden, vanligtvis omkring 60 pixel för en sex‑tecken‑payload.

### Steg 2 – generera en Planet‑streckkod med en explicit 100‑pixel‑höjd

```csharp
// Step 2: Generate a Planet barcode with an explicit 100‑pixel height
BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same module width
planetFixed.Parameters.Barcode.XDimension.Pixels = 4;

// Force the bar height to 100 pixels
planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the image
planetFixed.Save("PlanetHeight100.png", BarCodeImageFormat.Png);
```

**Why you might need this:**  
Ibland förväntar sig skanningsutrustningen en minsta stapelhöjd för pålitlig detektering. Genom att sätta `BarHeight.Pixels` garanterar du att varje genererad bild uppfyller detta krav, oavsett den kodade datalängden.

**Expected output:** `PlanetHeight100.png` visar samma data som tidigare, men staplarna är exakt 100 pixel höga, vilket ger dig full kontroll över den visuella storleken.

### Steg 3 – generera en RM4SCC‑streckkod med samma explicita höjd

```csharp
// Step 3: Generate an RM4SCC barcode with the same explicit height
BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Use the same module width for consistency
rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;

// Apply the 100‑pixel bar height
rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the image
rm4sccFixed.Save("RM4SCCHeight100.png", BarCodeImageFormat.Png);
```

**Why this matters:**  
`EncodeTypes.RM4SCC` är en staplad linjär streckkod som används inom logistik. Att matcha dess stapelhöjd med Planet‑streckkoden förenklar batch‑bearbetning när båda symbolerna förekommer på samma etikett.

**Expected output:** `RM4SCCHeight100.png` visar en perfekt dimensionerad RM4SCC‑streckkod, med samma 100‑pixel‑höjd som du satte för Planet‑koden.

> **Result verification:** Öppna varje PNG i en bildvisare och bekräfta att de svarta staplarna är exakt 4 pixel breda och, där du specificerat, 100 pixel höga. Du kan också mata in filerna i en streckkodsläsarapp för att säkerställa att de avkodas till “123456”.

---

## Förstå streckkodens pixelform och stapelhöjd

### Vad är **barcode pixel size**?

*Pixel size* avser det fysiska antalet skärm‑ eller skrivarpixlar som representerar en enskild modul (`XDimension`). En större pixelform ger en större streckkod, vilket kan vara lättare för lågupplösta skannrar men tar upp mer etikettutrymme.

### Hur påverkar `BarHeight` läsbarheten?

`BarHeight`‑egenskapen styr staplarnas vertikala längd. Standarder för de flesta 1‑D‑streckkoder (inklusive Planet och RM4SCC) rekommenderar en minsta höjd på 10 mm vid 300 dpi, vilket motsvarar ungefär 118 pixel. Att sätta en höjd under detta kan orsaka läsfel, särskilt med mobila kameror.

### När bör du låta biblioteket beräkna höjden automatiskt?

Om du bara genererar streckkoder för visning på skärm håller den automatiska beräkningen aspektförhållandet konsekvent och minskar behovet av manuell finjustering. För tryckta etiketter som måste uppfylla strikta ISO‑specifikationer bör du **explicit sätta stapelhöjden**.

---

## Vanliga fallgropar och bästa praxis när du genererar Planet‑streckkod

| Pitfall | Why it happens | Fix |
|---------|----------------|-----|
| Bars appear too thin or thick | `XDimension` left at default (1 pixel) on high‑resolution displays | Set `XDimension.Pixels` to at least 3‑4 for visual clarity |
| Scanner cannot read the code | `BarHeight` is too small for the scanner’s focal length | Use `BarHeight.Pixels` ≥ 100 for most mobile scanners |
| Image is blurry after scaling | Saving as JPEG introduces compression artifacts | Save as PNG (`BarCodeImageFormat.Png`) for lossless output |
| Unexpected barcode type | Wrong `EncodeTypes` enum value | Double‑check you’re using `EncodeTypes.Planet` for Planet symbology |

### Pro tip on performance

När du genererar tusentals streckkoder i ett batch‑jobb, återanvänd en enda `BarcodeGenerator`‑instans och ändra bara `CodeText` och storleksparametrarna mellan sparningar. Detta undviker upprepade allokeringar av interna renderingsobjekt och kan minska körningstiden med upp till 30 %.

---

## Fullt fungerande exempel – sätt ihop allt

Skapa ett nytt konsolprojekt (`dotnet new console -n BarcodeDemo`) och ersätt innehållet i `Program.cs` med följande:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Directory where PNG files will be saved
            string outputDir = Environment.CurrentDirectory;

            // ---------- Planet barcode – automatic height ----------
            var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
            planetAuto.Save($"{outputDir}/PlanetAuto.png", BarCodeImageFormat.Png);
            Console.WriteLine("PlanetAuto.png generated.");

            // ---------- Planet barcode – fixed 100‑pixel height ----------
            var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            planetFixed.Save($"{outputDir}/PlanetHeight100.png", BarCodeImageFormat.Png);
            Console.WriteLine("PlanetHeight100.png generated.");

            // ---------- RM4SCC barcode – same fixed height ----------
            var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            rm4sccFixed.Save($"{outputDir}/RM4SCCHeight100.png", BarCodeImageFormat.Png);
            Console.WriteLine("RM4SCCHeight100.png generated.");

            Console.WriteLine("All barcodes created successfully.");
        }
    }
}
```

Kör programmet med `dotnet run`. Efter körning hittar du tre PNG‑filer i projektmappen, var och en illustrerar ett annat **barcode generator example**‑scenario.

---

## Nästa steg och relaterade ämnen

* **How to generate barcode in other formats** – utforska `EncodeTypes.Code128`, `EncodeTypes.QR` och `EncodeTypes.DataMatrix` för 2‑D‑behov.  
* **Embedding barcodes in PDFs** – kombinera Aspose.BarCode med Aspose.PDF för att placera streckkoder direkt på fakturamallar.  
* **Dynamic barcode size based on user input** – calculate  

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to generate barcode java: Create an Exact Barcode Image](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)
- [How to Generate Barcode in Java Create and Set Size for Whole Picture](/barcode/english/java/barcode-basics/creating-setting-size-whole-picture-barcode/)
- [How to create code128 barcode Java and set bar height](/barcode/english/java/barcode-configuration/setting-bars-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}