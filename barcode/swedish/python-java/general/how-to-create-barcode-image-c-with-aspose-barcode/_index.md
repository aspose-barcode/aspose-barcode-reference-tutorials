---
category: general
date: 2026-10-12
description: Skapa streckkodbild i C# med Aspose.BarCode på några minuter. Detta steg‑för‑steg-exempel
  på streckkodsgenerator i C# visar hur man ställer in bildförhållanden och sparar
  PNG‑filer.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image c#
- barcode generator example c#
language: sv
lastmod: 2026-10-12
og_description: Skapa streckkodbild i C# omedelbart. Följ detta exempel på streckkodsgenerator
  i C# för att producera högkvalitativa PNG‑streckkoder med anpassade bildförhållanden.
og_image_alt: Sample barcode image created with C# using Aspose.BarCode
og_title: Skapa streckkodbild i C# – snabbguide med Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Create barcode image c# using Aspose.BarCode in minutes. This step‑by‑step
    barcode generator example c# shows how to set aspect ratios and save PNG files.
  headline: How to create barcode image c# with Aspose.BarCode
  type: TechArticle
- description: Create barcode image c# using Aspose.BarCode in minutes. This step‑by‑step
    barcode generator example c# shows how to set aspect ratios and save PNG files.
  name: How to create barcode image c# with Aspose.BarCode
  steps:
  - name: – Initialise the barcode generator
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: – Set the module (X‑dimension) size
    text: '```csharp // Adjust visual parameters – set the module size (X‑dimension)
      in pixels. barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2; ```'
  - name: – Save the first image with aspect ratio 15
    text: '```csharp // Set the first aspect ratio (15) and save the image. barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio
      = 15; barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
      ```'
  - name: – Change the aspect ratio to 30 and save a second image
    text: '```csharp // Change the aspect ratio to 30 and save the second image. barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio
      = 30; barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
      ```'
  - name: Expected output
    text: 'Running the program creates two PNG files:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Hur man skapar en streckkodsbild i C# med Aspose.BarCode
url: /sv/python-java/general/how-to-create-barcode-image-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så skapar du streckkodsbild c# med Aspose.BarCode

Om du snabbt behöver **skapa streckkodsbild c#** så guidar den här artikeln dig genom ett komplett, körbart exempel. Oavsett om du bygger ett fraktsedelssystem eller en lageravläsare visar stegen nedan exakt hur du konfigurerar en DataBar Stacked Omnidirectional‑streckkod, justerar dess visuella parametrar och sparar resultatet som en PNG‑fil.

Du får också se ett **barcode generator example c#** som demonstrerar hur du ändrar bildförhållandet i farten, så att du kan producera flera varianter utan att skriva om koden. Ingen extern dokumentation behövs – bara kopiera, klistra in och kör.

## Vad du behöver

Innan du börjar, se till att du har:

* .NET 6.0 eller senare (koden fungerar också med .NET Framework 4.7+)
* **Aspose.BarCode for .NET**‑paketet via NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* En mapp där de genererade PNG‑filerna ska skrivas (byt ut `YOUR_DIRECTORY` i koden)

Dessa förutsättningar säkerställer att **barcode generator example c#** körs på vilken modern Windows-, Linux‑ eller macOS‑utvecklingsmaskin som helst.

## Så skapar du streckkodsbild c# med Aspose.BarCode

Processen består av fyra korta steg: skapa generatorn, ange modulstorlek, konfigurera bildförhållandet och slutligen spara bilden. Varje steg förklaras så att du förstår *varför* det är viktigt, inte bara *vad* du ska skriva.

### Steg 1 – Initiera streckkodsgeneratorn

```csharp
using Aspose.BarCode.Generation;

// Create a DataBar Stacked Omnidirectional barcode generator with the desired data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

**Varför detta är viktigt:** `BarcodeGenerator`‑konstruktorn tar två argument: streckkodssymbologin (`EncodeTypes.DatabarStackedOmniDirectional`) och den råa datasträngen. Prefixet `(01)` talar om för läsaren att de följande 14 siffrorna representerar en GTIN‑14‑identifierare, vilket är ett vanligt krav inom detaljhandel och logistik.

### Steg 2 – Ange modul‑ (X‑dimension)‑storlek

```csharp
// Adjust visual parameters – set the module size (X‑dimension) in pixels.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Varför detta är viktigt:** X‑dimensionen styr bredden på den minsta stapeln (”modulen”). Ett värde på `2` pixlar ger en skarp, högupplöst streckkod som förblir läsbar efter skalning. Om du behöver en större streckkod för en affisch, öka detta värde proportionellt.

### Steg 3 – Spara den första bilden med bildförhållande 15

```csharp
// Set the first aspect ratio (15) and save the image.
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Varför detta är viktigt:** DataBar‑symboler stödjer ett *bildförhållande* som påverkar förhållandet mellan höjd och bredd. Ett bildförhållande på `15` är standard för många detaljhandelsapplikationer och ger en kompakt, nästan kvadratisk streckkod som enkelt får plats på små etiketter.

### Steg 4 – Ändra bildförhållandet till 30 och spara en andra bild

```csharp
// Change the aspect ratio to 30 and save the second image.
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

**Varför detta är viktigt:** Att öka bildförhållandet till `30` sträcker streckkoden vertikalt, vilket förbättrar läsbarheten på lågupplösta läsare eller på etiketter som är högre än de är breda. Eftersom samma `BarcodeGenerator`‑instans återanvänds undviker du att allokera ett nytt objekt för varje variant – ett effektivt mönster för batch‑bearbetning.

## Fullt, körbart exempel

Nedan är hela programmet som du kan kopiera in i en konsolapplikation. Det innehåller nödvändiga `using`‑direktiv, felhantering och kommentarer som förklarar varje rad.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // Initialise the generator with DataBar Stacked Omnidirectional symbology.
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.DatabarStackedOmniDirectional,
                    "(01)12345678901231");

                // Set the module (X‑dimension) size – 2 pixels gives a clear image.
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // -----------------------------------------------------------------
                // First image – aspect ratio 15 (default for most retail use cases)
                // -----------------------------------------------------------------
                generator.Parameters.Barcode.DataBar.AspectRatio = 15;
                string path15 = "YOUR_DIRECTORY/DatabarAspectRatio15.png";
                generator.Save(path15, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved barcode with aspect ratio 15 to {path15}");

                // -----------------------------------------------------------------
                // Second image – aspect ratio 30 (taller barcode for special scanners)
                // -----------------------------------------------------------------
                generator.Parameters.Barcode.DataBar.AspectRatio = 30;
                string path30 = "YOUR_DIRECTORY/DatabarAspectRatio30.png";
                generator.Save(path30, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved barcode with aspect ratio 30 to {path30}");
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error generating barcode: {ex.Message}");
            }
        }
    }
}
```

### Förväntad utdata

När programmet körs skapas två PNG‑filer:

| Filnamn | Bildförhållande | Typisk användning |
|-----------|------------------|-------------------|
| `DatabarAspectRatio15.png` | 15 | Standard detaljhandelsetikett |
| `DatabarAspectRatio30.png` | 30 | Hög etikett eller lågupplöst läsare |

Båda bilderna innehåller en skarp DataBar Stacked Omnidirectional‑streckkod som kodar GTIN‑14‑värdet `12345678901231`. Du kan öppna PNG‑filerna i vilken bildvisare som helst för att verifiera den visuella kvaliteten.

![Exempel på streckkodbild skapad med C# med Aspose.BarCode](https://example.com/placeholder.png){.align-center width=400 alt="Exempel på streckkodbild skapad med C# med Aspose.BarCode"}

*Alt‑texten ovan innehåller huvudnyckelordet, vilket hjälper både sökmotorer och skärmläsare.*

## Ytterligare överväganden och bästa praxis‑tips

* **Stödda format** – `BarCodeImageFormat` stödjer PNG, JPEG, BMP, GIF och TIFF. PNG är förlustfritt och därmed det säkraste valet för efterföljande skanning.
* **Färg‑anpassning** – Du kan ändra förgrunds‑/bakgrundsfärger via `generator.Parameters.Barcode.ForegroundColor` och `BackgroundColor`. Detta är användbart när du skriver ut på färgad media.
* **Batch‑generering** – För stora lager, omslut spara‑logiken i en `foreach`‑loop som läser produktdata från en CSV‑fil. Återanvändning av samma `BarcodeGenerator`‑instans minskar minnesbelastningen.
* **Felhantering** – `try/catch`‑blocket i hela exemplet fångar problem som ogiltiga datasträngar eller skriv‑behörighetsfel, vilket är vanligt när målmappen saknas.
* **Prestanda** – Att sätta `XDimension.Pixels` innan det första `Save`‑anropet säkerställer att renderaren beräknar bitmap‑storleken bara en gång per bildförhållande‑ändring.

## Slutsats

Du vet nu hur du **skapar streckkodsbild c#** med Aspose.BarCode, justerar X‑dimensionen, byter bildförhållande och sparar PNG‑filer i ett enda återanvändbart kodblock. Detta **barcode generator example c#** täcker de vanligaste varianterna du kommer att stöta på när du genererar DataBar Stacked Omnidirectional‑symboler för detaljhandel eller logistik.

## Vad blir nästa steg?

* Utforska andra symbologier såsom `EncodeTypes.Code128` eller `EncodeTypes.QR` för att bredda din lösning.
* Experimentera med `generator.Parameters.Barcode.ImageMargin` för att lägga till vitt utrymme runt streckkoden.
* Integrera de genererade PNG‑filerna i PDF‑fakturor med Aspose.PDF, eller bädda in dem direkt i HTML‑rapporter.

Känn dig fri att anpassa koden för ditt specifika arbetsflöde – oavsett om du behöver en enda bild per produkt eller en massexport av tusentals streckkoder, skalar mönstret som visas här effektivt.

---


## Vad bör du lära dig härnäst?


Följande handledningar täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to create barcode image with Aspose.Barcode in C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [How to create postal barcode image in C# using Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}