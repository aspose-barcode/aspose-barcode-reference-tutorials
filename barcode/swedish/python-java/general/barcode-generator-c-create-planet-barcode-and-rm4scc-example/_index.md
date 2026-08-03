---
category: general
date: 2026-08-03
description: Barcode‑generator C#‑handledning som visar hur man skapar Planet‑streckkod
  med Aspose.BarCode, ställer in X‑dimension och sparar som PNG‑bilder.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- create planet barcode
language: sv
lastmod: 2026-08-03
og_description: Barcode‑generator C#‑handledning guidar dig genom att skapa en Planet‑streckkod,
  justera X‑dimensionen och spara som PNG med Aspose.BarCode.
og_image_alt: Screenshot of generated Planet and RM4SCC barcodes in PNG format
og_title: Streckkodsgenerator C# – skapa Planet‑streckkod steg för steg
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial showing how to create Planet barcode
    with Aspose.BarCode, set X‑dimension, and save as PNG images.
  headline: Barcode generator C# – create Planet barcode and RM4SCC example
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Barcodegenerator C# – skapa Planet-streckkod och RM4SCC‑exempel
url: /sv/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generator C# – skapa Planet‑streckkod och RM4SCC‑exempel

Om du behöver en **barcode generator C#** som kan producera post‑specifika symboler, visar den här guiden exakt hur du **skapar Planet‑streckkod**‑bilder med Aspose.BarCode. Du får se hur du konfigurerar X‑dimensionen, genererar en matchande RM4SCC‑streckkod och sparar båda som PNG‑filer – allt i några koncisa steg.

Tutorialen täcker allt du behöver för att köra koden på .NET 6 eller senare, förklarar varför varje inställning är viktig och pekar på vanliga fallgropar såsom fel modulbredd eller saknade katalogbehörigheter. I slutet har du två färdiga streckkods‑bilder som kan skrivas ut och som följer Planet‑ och RM4SCC‑standarderna.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6 SDK (eller någon .NET‑version som stöds av Aspose.BarCode)
* Visual Studio 2022 eller någon C#‑IDE du föredrar
* Ett NuGet‑referens till **Aspose.BarCode** (`Install-Package Aspose.BarCode`)
* Skrivbehörighet till den mapp där du planerar att lagra PNG‑filerna

Inga ytterligare externa tjänster krävs; biblioteket hanterar all kodning lokalt.

## Steg 1: Initiera barcode generator C#‑objektet

Den första uppgiften är att skapa en instans av `BarcodeGenerator`. Konstruktorn tar streckkodssymbologin (`EncodeTypes.Planet`) och data som ska kodas.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*Varför detta steg?*  
`BarcodeGenerator` är startpunkten för varje streckkod du genererar. Genom att välja `EncodeTypes.Planet` talar du om för biblioteket att följa ISO/IEC 24723‑specifikationen som används av många posttjänster.

## Steg 2: Ställ in X‑dimensionen (modulbredd) för Planet‑streckkoden

X‑dimensionen definierar bredden på en enskild streckkodmodul (det minsta strecket eller mellanslaget). Ett värde på **4 pixlar** fungerar bra för de flesta etikett‑skrivare.

```csharp
// Step 2: Define the X‑dimension (module width) in pixels
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Varför detta är viktigt*  
Om modulen är för smal kan streckkoden bli oläslig; om den är för bred växer etikettens storlek onödigt. Genom att justera `Pixels` kan du finjustera streckkoden för just din skrivarupplösning.

## Steg 3: Spara Planet‑streckkoden som en PNG‑bild

Aspose.BarCode beräknar automatiskt streckkodshöjden baserat på den valda symbologin, så du behöver bara ange filsökvägen och formatet.

```csharp
// Step 3: Save the Planet barcode as a PNG image (height is calculated automatically)
planetGenerator.Save("YOUR_DIRECTORY/PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*Tips*  
Byt ut `YOUR_DIRECTORY` mot en absolut eller relativ sökväg som finns på din maskin. Om katalogen inte finns kastar `Save`‑metoden ett `DirectoryNotFoundException`.

**Förväntad output** – en PNG‑fil som liknar illustrationen nedan (den faktiska bilden visas inte här, men du kommer att se en klassisk Planet‑streckkod med en numerisk payload på `123456`).

## Steg 4: Initiera en andra generator för RM4SCC‑streckkoden

Många postsystem kräver både Planet‑ och RM4SCC‑symboler på samma brev. Skapa en ny `BarcodeGenerator`‑instans för RM4SCC‑symbologin.

```csharp
// Step 4: Create an RM4SCC barcode generator with the same data
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
```

*Varför en separat instans?*  
Varje symbologi har sin egen uppsättning parametrar. Att återanvända samma generator kan oavsiktligt föra över inställningar (som X‑dimension) som inte är optimala för den andra streckkoden.

## Steg 5: Konfigurera X‑dimensionen för RM4SCC‑streckkoden

RM4SCC respekterar också X‑dimensionen, så vi använder samma pixelbredd för visuell konsistens.

```csharp
// Step 5: Set the X‑dimension for the RM4SCC barcode
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Pro‑tips*  
Om du behöver en högre streckkod (t.ex. för större etiketter) kan du också sätta `Height.Pixels`. Att låta den vara odefinierad låter biblioteket beräkna den ideala höjden automatiskt.

## Steg 6: Spara RM4SCC‑streckkoden som en PNG‑bild

Till sist sparar du RM4SCC‑streckkoden till disk.

```csharp
// Step 6: Save the RM4SCC barcode as a PNG image (height is calculated automatically)
rm4sccGenerator.Save("YOUR_DIRECTORY/PostalRM4SCCBarHeightNone.png", BarCodeImageFormat.Png);
```

Du har nu två PNG‑filer – `PostalPlanetBarHeightNone.png` och `PostalRM4SCCBarHeightNone.png` – som du kan bädda in i postetiketter, skriva ut på kuvert eller skicka till en tredjeparts‑trycktjänst.

## Valfritt: Justera höjd eller använda andra bildformat

Om ditt arbetsflöde kräver en specifik streckkodshöjd eller ett annat bildformat (t.ex. JPEG eller BMP) kan du ändra parametrarna innan du anropar `Save`:

```csharp
// Example: set a fixed height of 100 pixels and save as JPEG
planetGenerator.Parameters.Barcode.Height.Pixels = 100;
planetGenerator.Save("PostalPlanet.jpg", BarCodeImageFormat.Jpeg);
```

**Edge case** – När du sätter en anpassad höjd, se till att värdet uppfyller den minsta höjd som ISO‑standarden kräver; annars kan streckkoden misslyckas med valideringen.

## Vanliga fallgropar och hur du undviker dem

| Fallgrop | Varför det händer | Lösning |
|----------|-------------------|---------|
| `DirectoryNotFoundException` | Målkatalogen finns inte eller är felstavad. | Skapa katalogen först eller använd `Path.Combine` med `Environment.CurrentDirectory`. |
| Streckkod oläslig på lågupplösta skrivare | X‑dimension för liten för skrivarens DPI. | Öka `XDimension.Pixels` till 5 – 6 för 203 dpi‑skrivare, eller testa med en provetikett. |
| Fel symbologi använd | `EncodeTypes.Code128` skickas istället för `EncodeTypes.Planet`. | Dubbelkolla att `EncodeTypes`‑enum‑värdet matchar den krävs poststandard. |
| Null‑referens på `Parameters` | En äldre version av Aspose.BarCode där API:t skiljer sig. | Uppgradera till den senaste NuGet‑paketet (v23.12 eller senare). |

## Fullt körbart exempel

Nedan är hela programmet som du kan kopiera, klistra in och köra. Det inkluderar `using`‑satser, felhantering och kommentarer som förklarar varje rad.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define the output directory (change as needed)
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // -------- Planet barcode ----------
        var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string planetPath = Path.Combine(outputDir, "PostalPlanetBarHeightNone.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Planet barcode saved to: {planetPath}");

        // -------- RM4SCC barcode ----------
        var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string rm4sccPath = Path.Combine(outputDir, "PostalRM4SCCBarHeightNone.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);
        Console.WriteLine($"RM4SCC barcode saved to: {rm4sccPath}");
    }
}
```

När du kör programmet skapas en `Barcodes`‑mapp bredvid den körbara filen och de två PNG‑filerna placeras där. Öppna dem med någon bildvisare för att verifiera resultatet.

## Slutsats

Du har nu en **barcode generator C#**‑lösning som kan **skapa Planet‑streckkod**‑bilder, justera X‑dimensionen för optimal utskrift och producera en matchande RM4SCC‑streckkod – allt med några få kodrader. Metoden fungerar med .NET 6+, kräver bara Aspose.BarCode‑NuGet‑paketet och kan utökas till andra symbologier som Code128, QR eller DataMatrix genom att byta `EncodeTypes`‑värdet.

### Vad blir nästa steg?

* Experimentera med olika `XDimension.Pixels`‑värden för att matcha din skrivar‑DPI.  
* Generera streckkoder i andra format (PDF, SVG) genom att ändra `BarCodeImageFormat`‑enum.  
* Kombinera de två PNG‑filerna till en enda etikett med ett grafikbibliotek som **SkiaSharp**.  
* Utforska hela Aspose.BarCode‑API:t för avancerade funktioner som kontrollsiffra‑validering eller anpassade typsnitt.

Känn dig fri att anpassa koden för batch‑bearbetning eller integrera den i en ASP.NET Core‑webbtjänst som returnerar streckkods‑bilder på begäran. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

De följande handledningarna täcker närbesläktade ämnen som bygger vidare på teknikerna i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationssätt i dina egna projekt.

- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [How to Save PNG using DataMatrix C40 with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [barcode generator tutorial c# – Customize Code 16K Barcode Aspect Ratios with Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}