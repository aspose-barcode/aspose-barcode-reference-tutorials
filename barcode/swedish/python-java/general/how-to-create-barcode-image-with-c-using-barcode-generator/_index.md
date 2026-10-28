---
category: general
date: 2026-10-28
description: Skapa streckkodbild i C# snabbt. Lär dig hur du använder barcode‑generatorn
  i C#, hur du ställer in pixelförstorlek och hur du ändrar bildförhållandet för DataBar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to set pixel size
- how to change aspect ratio
- how to generate databar
language: sv
lastmod: 2026-10-28
og_description: Skapa streckkodbild i C# med en streckkodsgenerator. Följ den här
  guiden för att ställa in pixelstorlek, ändra bildförhållande och generera DataBar‑streckkoder.
og_image_alt: Screenshot of a generated barcode image created with C#
og_title: Skapa streckkodbild i C# – steg‑för‑steg‑guide
schemas:
- author: GroupDocs
  dateModified: '2026-10-28'
  description: Create barcode image in C# quickly. Learn barcode generator c# usage,
    how to set pixel size, and how to change aspect ratio for DataBar.
  headline: How to create barcode image with C# using Barcode Generator
  type: TechArticle
tags:
- barcode
- C#
- imaging
title: Hur man skapar en streckkodbild med C# med Barcode Generator
url: /sv/python-java/general/how-to-create-barcode-image-with-c-using-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så skapar du streckkodbild med C# med Barcode Generator

Om du behöver **skapa streckkodbild** i en .NET‑applikation visar den här guiden exakt hur du gör. Du får ett komplett, körbart exempel som använder Barcode Generator‑biblioteket för C# för att generera en DataBar stacked omnidirectional‑streckkod, ställa in pixelförstoringen och ändra bildförhållandet.

Att generera streckkoder programatiskt eliminerar behovet av externa verktyg och låter dig bädda in bilden direkt i PDF‑filer, rapporter eller UI‑kontroller. I stegen nedan går vi också igenom **hur du ställer in pixelförstoringen** och **hur du ändrar bildförhållandet**, två vanliga krav när du behöver en skarp, korrekt skalad streckkod.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare installerat  
* En C#‑kompatibel IDE (Visual Studio, Rider eller VS Code)  
* NuGet‑paketet `BarcodeGenerator` (t.ex. `GroupDocs.Barcode` eller `Aspose.Barcode`) installerat i ditt projekt  

Du kan lägga till paketet med följande kommando:

```bash
dotnet add package GroupDocs.Barcode
```

> **Pro tip:** Verifiera att paketversionen matchar ditt mål‑framework för att undvika körnings‑inkompatibiliteter.

## Skapa streckkodbild med Barcode Generator C#

Det första steget är att instansiera generatorn med önskad streckkodstyp och data. Exemplet nedan skapar en **DataBar stacked omnidirectional**‑streckkod, vilket är idealiskt för detaljhandels‑scanningsscenario.

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // Step 1: Create a BarcodeGenerator for DataBar stacked omnidirectional
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example data

        // Step 2: Set the pixel size of the X‑dimension (how to set pixel size)
        barcode.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 3: Save an image with the first aspect ratio (how to generate databar)
        barcode.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcode.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // Step 4: Change the aspect ratio (how to change aspect ratio) and save a second image
        barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcode.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### Varför varje rad är viktig

* **Instansiera `BarcodeGenerator`** – Konstruktorn tar en streckkodssymbologi (`EncodeTypes.DatabarStackedOmniDirectional`) och den råa datasträngen. Att välja rätt symbologi säkerställer att scannern kan läsa koden.  
* **Ställ in `XDimension.Pixels`** – Denna egenskap styr bredden på det minsta stapel‑elementet. Ett värde på `2` ger en finfördelad bild som förblir läsbar på de flesta skärmar. Höj värdet om du behöver en större streckkod för lågupplösta skrivare.  
* **Konfigurera `AspectRatio`** – DataBar‑familjen stödjer flera bildförhållanden som påverkar förhållandet mellan höjd och bredd. Värdena `15` och `30` är vanliga; `15` ger en kortare streckkod, medan `30` ger en högre.  
* **`Save`‑metod** – Sparar den genererade streckkoden till en PNG‑fil. Du kan ersätta `BarCodeImageFormat.Png` med `Jpeg` eller `Bmp` om ditt downstream‑system kräver ett annat format.

## Hur du ställer in pixelförstoringen för olika renderingssammanhang

Pixelförstoringen bestämmer den visuella densiteten i streckkoden. Om en streckkod ska visas på en hög‑DPI‑monitor kan du öka pixelförstoringen till `3` eller `4`. Omvänt, för lågupplösta termiska skrivare, minskar en mindre pixelförstorning (t.ex. `1`) bläckförbrukningen.

```csharp
// Example: increase pixel size for a high‑resolution display
barcode.Parameters.Barcode.XDimension.Pixels = 4;
```

**Edge case:** Att sätta pixelförstoringen för lågt (< 1) kastar ett `ArgumentOutOfRangeException`. Validera alltid värdet innan du tilldelar det.

## Hur du ändrar bildförhållandet utan att återskapa generatorn

Att ändra bildförhållandet är en enkel egenskapsuppdatering; du behöver **inte** återskapa `BarcodeGenerator`‑instansen. Detta sparar minne och förbättrar prestanda när du behöver flera bilder med olika former.

```csharp
// Switch from a short to a tall barcode
barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
barcode.Save("TallDatabar.png", BarCodeImageFormat.Png);
```

Om du behöver fler än två förhållanden kan du loopa igenom en array:

```csharp
int[] ratios = { 15, 20, 25, 30 };
foreach (int ratio in ratios)
{
    barcode.Parameters.Barcode.DataBar.AspectRatio = ratio;
    string fileName = $"DatabarAspectRatio{ratio}.png";
    barcode.Save(fileName, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {fileName}");
}
```

## Förväntad output

När programmet körs skapas två PNG‑filer (eller fler om du använder loopen). Öppna dem i en bildvisare; du bör se en ren DataBar‑streckkod:

* **DatabarAspectRatio15.png** – kort, bred streckkod som passar smala etikettutrymmen.  
* **DatabarAspectRatio30.png** – högre streckkod som förbättrar skannings‑tillförlitlighet på vinklade scannrar.

Båda bilderna har samma pixelförstorning (2 px per modul) men skiljer sig endast i höjd, vilket demonstrerar **hur du ändrar bildförhållandet** samtidigt som övriga parametrar förblir oförändrade.

## Vanliga fallgropar och hur du undviker dem

| Symptom | Orsak | Lösning |
|---------|-------|--------|
| Streckkoden blir suddig | `XDimension.Pixels` är för lågt för den aktuella utskrifts‑/skärmupplösningen | Öka pixelförstoringen till minst `2` för skärmvisning, `3` för utskrift |
| Scannern kan inte läsa koden | Fel `EncodeTypes` för dataformatet | Verifiera att GTIN‑14‑data matchar den valda symbologin |
| `ArgumentOutOfRangeException` på bildförhållande | Förhållandsvärdet stöds inte av biblioteket (giltigt intervall: 15‑30) | Använd endast värden som dokumenteras av biblioteket, eller fånga undantaget och falla tillbaka på ett standardvärde |
| Filen hittas inte efter `Save` | Relativ sökväg pekar på en icke‑existerande katalog | Använd en absolut sökväg eller se till att `Directory.CreateDirectory` anropas först |

```csharp
// Ensure the output folder exists
string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputDir);
barcode.Save(Path.Combine(outputDir, "DatabarAspectRatio15.png"), BarCodeImageFormat.Png);
```

## Nästa steg – utöka streckkod‑arbetsflödet

Nu när du kan **skapa streckkodbild**, kanske du vill:

* **Bädda in PNG‑filen i en PDF** med ett bibliotek som `PdfSharp` eller `iTextSharp`.  
* **Generera andra symbologier** (QR, Code128, PDF417) genom att ändra `EncodeTypes`‑enum.  
* **Applicera färgtransformeringar** genom att komma åt `barcode.Parameters.Barcode.Image.Color`.  
* **Servera bilden via en ASP.NET Core‑endpoint** för on‑the‑fly‑generering i webbappar.

Varje ämne bygger på samma grundkoncept som behandlas i den här handledningen, såsom **barcode generator c#**‑användning, kontroll av pixelförstoringen och manipulation av bildförhållandet.

## Slutsats

Du vet nu hur du **skapar streckkodbild** i C# med en Barcode Generator, hur du ställer in pixelförstoringen, hur du ändrar bildförhållandet och hur du effektivt genererar DataBar‑streckkoder. Det kompletta, körbara exemplet kan kopieras in i vilket .NET‑projekt som helst, anpassas för andra symbologier och utökas för att passa verkliga arbetsflöden.

Känn dig fri att experimentera med olika `XDimension`‑värden, bildförhållanden och utdataformat. Om du stöter på problem, gå tillbaka till tabellen “Vanliga fallgropar” eller konsultera bibliotekets officiella dokumentation för djupare konfigurationsalternativ. Lycka till med kodandet!

## Vad bör du lära dig härnäst?

De följande handledningarna täcker närliggande ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to create barcode image and adjust its aspect ratio in C#](/barcode/english/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/)
- [How to generate barcode set custom size and save image in C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [How to use a barcode generator C# to create DataBar barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}