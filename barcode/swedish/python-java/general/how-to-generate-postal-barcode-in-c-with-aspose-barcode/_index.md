---
category: general
date: 2026-08-19
description: Lär dig hur du genererar poststreckkod i C# med Aspere.BarCode. Denna
  steg‑för‑steg‑guide visar hur du genererar streckkod för Planet‑ och RM4SCC‑format.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- how to generate barcode
language: sv
lastmod: 2026-08-19
og_description: Generera poststreckkod i C# med Aspose.BarCode. Följ den här guiden
  för att lära dig hur du genererar streckkod för Planet och RM4SCC med anpassade
  dimensioner.
og_image_alt: Generated postal barcode image using Aspose.BarCode
og_title: Generera poststreckkod i C# – komplett Aspose.BarCode‑guide
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Learn how to generate postal barcode in C# using Aspere.BarCode. This
    step‑by‑step guide shows how to generate barcode for Planet and RM4SCC formats.
  headline: How to generate postal barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate postal barcode in C# using Aspere.BarCode. This
    step‑by‑step guide shows how to generate barcode for Planet and RM4SCC formats.
  name: How to generate postal barcode in C# with Aspose.BarCode
  steps:
  - name: Create a Planet barcode (automatic height)
    text: Planet is a postal barcode used in many countries for mail sorting. When
      you create a Planet barcode, the library automatically determines the optimal
      bar height based on the encoded data.
  - name: Create an RM4SCC barcode with explicit height
    text: RM4SCC is another postal symbology that often requires a specific bar height
      for scanner compatibility. The following code shows how to set that height manually.
  - name: Verify the output
    text: 'After running the program, open the two PNG files located in `YOUR_DIRECTORY`.
      You should see two distinct barcodes:'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- C#
title: Hur man genererar poststreckkod i C# med Aspose.BarCode
url: /sv/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar poststreckkod i C# med Aspose.BarCode

Om du behöver **generera poststreckkod** för postapplikationer visar den här guiden exakt hur du skapar streckkod med Aspose.BarCode‑biblioteket. Du får ett komplett, körbart exempel som skapar både en Planet‑streckkod (höjden beräknas automatiskt) och en RM4SCC‑streckkod med en explicit stapelhöjd.

Att generera poststreckkod är ett vanligt krav för logistikprogram, automatiska etikett‑skrivare och massutskickssystem. I slutet av den här handledningen kan du integrera streckkodsgenerering i vilket .NET‑projekt som helst, anpassa X‑dimensionen och styra stapelhöjden när standardformatet tillåter det.

**Vad du kommer att lära dig**

* Hur du sätter upp Aspose.BarCode i ett C#‑projekt.  
* Hur du genererar Planet‑ och RM4SCC‑poststreckkoder.  
* Hur du justerar X‑dimensionen (modulbredd) och stapelhöjden.  
* Hur du sparar resultatet som en PNG‑bild.  

Inga externa tjänster krävs – allt körs lokalt efter att du har refererat Aspose.BarCode‑NuGet‑paketet.

## Förutsättningar

* .NET 6.0 SDK eller senare (koden fungerar även med .NET Framework 4.7+).  
* Visual Studio 2022, Visual Studio Code eller någon annan C#‑IDE du föredrar.  
* Aspose.BarCode for .NET‑paket – installera det via NuGet:

```bash
dotnet add package Aspose.BarCode
```

## Generera poststreckkod med Aspose.BarCode

Följande avsnitt guidar dig genom varje steg, från att skapa generatorobjekten till att spara de slutgiltiga PNG‑filerna.

### Steg 1: Skapa en Planet‑streckkod (automatisk höjd)

Planet är en poststreckkod som används i många länder för postsortering. När du skapar en Planet‑streckkod bestämmer biblioteket automatiskt den optimala stapelhöjden baserat på den kodade datan.

```csharp
using Aspose.BarCode.Generation;

// Create a Planet barcode generator with the data you want to encode.
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Define the X‑dimension (module width) in pixels. A value of 4 pixels is a good default.
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the barcode as a PNG image. The height is calculated automatically.
planetGenerator.Save("YOUR_DIRECTORY/PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

**Varför detta fungerar** – `EncodeTypes.Planet` talar om för Aspose.BarCode att använda Planet‑symbologi. `XDimension`‑egenskapen styr bredden på den minsta stapeln (modulen). Eftersom Planet inte kräver en fast stapelhöjd beräknar biblioteket en lämplig höjd automatiskt, vilket förenklar koden.

### Steg 2: Skapa en RM4SCC‑streckkod med explicit höjd

RM4SCC är en annan post‑symbologi som ofta kräver en specifik stapelhöjd för scanner‑kompatibilitet. Följande kod visar hur du ställer in den höjden manuellt.

```csharp
// Create an RM4SCC barcode generator.
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Set the X‑dimension (module width) and the desired bar height in pixels.
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the barcode as a PNG image.
rm4sccGenerator.Save("YOUR_DIRECTORY/PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

**Varför du anger höjden** – Vissa post‑scanners förväntar sig en minsta stapelhöjd. Genom att tilldela `BarHeight.Pixels = 100` garanterar du att den genererade bilden uppfyller dessa krav. X‑dimensionen förblir konsekvent med Planet‑streckkoden så att båda bilderna har samma visuella densitet.

### Steg 3: Verifiera resultatet

Efter att du har kört programmet, öppna de två PNG‑filerna i `YOUR_DIRECTORY`. Du bör se två distinkta streckkoder:

* `PostalPlanetBarHeightNone.png` – en Planet‑streckkod med automatiskt beräknad höjd.  
* `PostalRM4SCCBarHeight100Pixels.png` – en RM4SCC‑streckkod med 100‑pixel stapelhöjd.

Båda bilderna kan matas direkt in i etikett‑skrivare eller visas i en webbapplikation.

![Generated postal barcode image using Aspose.BarCode](generated-postal-barcode.png)

*Bildtext:* **Genererad poststreckkod** bild med Aspose.BarCode (visar hur man genererar poststreckkod).

## Hur man genererar streckkod med anpassade dimensioner (avancerat)

Om du behöver finjustera andra parametrar – såsom marginaler, textplacering eller färg – erbjuder Aspose.BarCode ett rikt `Parameters`‑objekt. Nedan är ett snabbt exempel som lägger till en vit bakgrund och inaktiverar den mänskligt läsbara texten.

```csharp
planetGenerator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
planetGenerator.Parameters.Barcode.CodeTextVisible = false;
planetGenerator.Save("YOUR_DIRECTORY/PostalPlanetNoText.png", BarCodeImageFormat.Png);
```

**När du använder detta** – Att inaktivera den mänskligt läsbara texten är vanligt för automatiserad sortering där endast maskinläsbart mönster är relevant. Att sätta en bakgrundsfärg säkerställer att streckkoden skrivs korrekt på transparent media.

## Vanliga fallgropar och pro‑tips

| Problem | Varför det händer | Lösning |
|---------|-------------------|---------|
| Streckkoden ser utdragen ut | X‑dimensionen är för stor i förhållande till bildstorleken | Håll `XDimension.Pixels` mellan 2 och 5 för de flesta poststreckkoder |
| Scanner avvisar bilden | Stapelhöjden är under det minimum som posttjänsten kräver | Använd `BarHeight.Pixels` ≥ 80 för RM4SCC om inte specifikationen anger annat |
| PNG‑filen är stor | Bildens upplösning är högre än nödvändigt | Spara som PNG‑8 (`BarCodeImageFormat.Png8`) eller minska pixel‑dimensionerna |

**Pro‑tips:** Testa alltid den genererade streckkoden med en riktig scanner innan du går i produktion. Små visuella skillnader kan påverka läsbarheten.

## Fullständig källkod

Kopiera hela blocket nedan till ett nytt konsolprogram (`Program.cs`). Anpassa utgångssökvägarna till en mapp som ditt program har skrivbehörighet till.

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // ------------------------------
        // Generate Planet barcode (auto height)
        // ------------------------------
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        planetGenerator.Save("PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);

        // ------------------------------
        // Generate RM4SCC barcode (explicit height)
        // ------------------------------
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4sccGenerator.Save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);

        Console.WriteLine("Barcodes generated successfully.");
    }
}
```

När du kör programmet skrivs *“Barcodes generated successfully.”* och de två PNG‑filerna skapas i programmets arbetskatalog.

## Slutsats

Du vet nu hur du **genererar poststreckkod** i C# med Aspose.BarCode, både för automatiskt höjd‑Planet‑streckkoder och fasta‑höjd‑RM4SCC‑streckkoder. Guiden visade också **hur man genererar streckkod** med anpassad X‑dimension, stapelhöjd och visuella alternativ, vilket ger en solid grund för alla post‑automatiseringsprojekt.

Nästa steg du kan utforska:

* Integrera de genererade PNG‑filerna i en PDF‑faktura med Aspose.PDF.  
* Byt ut utdataformatet till SVG för skalbara vektorgrafik.  
* Använd `BarcodeReader`‑klassen för att programatiskt verifiera den kodade datan.

Känn dig fri att experimentera med olika symbologier (t.ex. `EncodeTypes.Postnet`) och dela dina resultat med communityn. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

De följande handledningarna täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to Generate Barcode Image with Supplemental Space Customization using Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}