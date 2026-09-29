---
category: general
date: 2026-09-29
description: Skapa planetstreckkod i C# med både fyllda och tomma staplar – steg‑för‑steg‑guide
  med Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode XDimension
- filled bars
- empty bars
- Aspose.Barcode C#
language: sv
lastmod: 2026-09-29
og_description: Skapa planetstreckkod i C# snabbt. Lär dig hur du renderar fyllda
  staplar, växlar till tomma staplar och justerar X‑dimensionen med Aspose.Barcode.
og_image_alt: 'Screenshot of two Planet barcodes: one with filled bars, one with empty
  bars'
og_title: Skapa planetstreckkod med fyllda och tomma staplar – C#‑handledning
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  headline: How to create planet barcode with filled and empty bars
  type: TechArticle
- description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  name: How to create planet barcode with filled and empty bars
  steps:
  - name: Changing the bar width
    text: If your label printer expects a different bar width, modify the `XDimension.Pixels`
      value. For high‑resolution printers, a value of **2** or **3** pixels may be
      preferable; for low‑resolution printers, **5** or **6** pixels can improve scan
      reliability.
  - name: Using a different image format
    text: Aspose.Barcode supports PNG, JPEG, BMP, GIF, and TIFF. Swap `BarCodeImageFormat.Png`
      with another enum value to match your downstream workflow.
  - name: Generating multiple barcodes in a loop
    text: When you need a batch of Planet barcodes (e.g., for a mailing list), wrap
      the generator logic in a `foreach` loop and change the data string each iteration.
  - name: Handling invalid input
    text: The Planet symbology accepts only numeric strings of **5‑8** digits. Supplying
      an invalid value throws an `ArgumentException`. Guard against this with a simple
      validation method.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Hur man skapar planetstreckkod med fyllda och tomma staplar
url: /sv/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar planet barcode med fyllda och tomma staplar

Om du behöver **skapa planet barcode**-bilder i C#, visar den här guiden exakt hur du genererar både versioner med fyllda staplar och tomma staplar. Du får se hur du ställer in stapelbredden (X‑dimension), växlar `FilledBars`‑egenskapen och sparar resultaten som PNG‑filer – allt med Aspose.Barcode‑biblioteket.

Att generera poststreckkoder är ett vanligt krav för fraktssystem, utskickslistor och logistik‑instrumentpaneler. I slutet av den här handledningen har du två färdiga PNG‑filer som du kan bädda in i rapporter, e‑post eller utskrifter.

## Förutsättningar

| Krav | Varför det är viktigt |
|-------------|----------------|
| .NET 6.0 eller senare | Tillhandahåller runtime för C#‑exemplet. |
| Visual Studio 2022 (eller någon C#‑IDE) | Gör att du kan kompilera och köra koden. |
| **Aspose.Barcode for .NET** NuGet‑paket | Tillhandahåller `BarcodeGenerator`‑klassen och `EncodeTypes.Planet`. Installera det med `dotnet add package Aspose.Barcode`. |
| Skrivbehörighet till en mapp på disken | `Save`‑metoden skriver PNG‑filer till den angivna sökvägen. |

## Steg 1: Ställ in projektet och importera namnrymder

Skapa ett nytt konsolprojekt (eller lägg till koden i ett befintligt) och referera till Aspose.Barcode‑namnrymden.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;
```

Dessa `using`‑direktiv ger dig åtkomst till `BarcodeGenerator`, `EncodeTypes` och bildformat‑enum‑värden som behövs för handledningen.

## Steg 2: Skapa en Planet‑streckkod med standard (fyllda) staplar

Den första streckkoden använder bibliotekets standardrendering, som fyller staplarna.

```csharp
// Initialise a generator for the Planet (postal) barcode with sample data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Optional: adjust the bar width (X dimension) to 4 pixels for clearer printing.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image with filled bars.
string filledPath = @"C:\Barcodes\PlanetFilledBars.png";
barcodeGenerator.Save(filledPath, BarCodeImageFormat.Png);

Console.WriteLine($"Filled Planet barcode saved to: {filledPath}");
```

**Varför detta fungerar:**  
`EncodeTypes.Planet` instruerar Aspose.Barcode att använda **Planet**‑symbologi, som är en poststreckkod som används av United States Postal Service. `XDimension`‑egenskapen styr bredden på varje stapel; att sätta den till 4 pixlar ger en streckkod som skrivs bra på vanliga etikett‑skrivare. Som standard är `FilledBars` `true`, så staplarna visas som solida.

## Steg 3: Skapa en Planet‑streckkod med tomma staplar

För att generera samma data med *tomma* staplar behöver du bara växla `FilledBars`‑flaggan medan de andra inställningarna förblir identiska.

```csharp
// Re‑use the same variable for clarity.
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for visual consistency.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Render empty bars instead of filled ones.
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the image with empty bars.
string emptyPath = @"C:\Barcodes\PlanetEmptyBars.png";
barcodeGenerator.Save(emptyPath, BarCodeImageFormat.Png);

Console.WriteLine($"Empty Planet barcode saved to: {emptyPath}");
```

**Varför detta är viktigt:**  
Vissa utskickssystem kräver **tomma‑staplar**‑stilen för att förbättra läsbarheten när streckkoden skrivs på mörka bakgrunder eller när ett kontrasterande färgschema används. Genom att sätta `FilledBars = false` ritar generatorn bara konturerna av staplarna, medan insidan blir transparent.

## Förväntat resultat

Efter att ha kört programmet innehåller mappen `C:\Barcodes` (eller den sökväg du valde) två PNG‑filer:

| Fil | Visuell beskrivning |
|------|---------------------|
| `PlanetFilledBars.png` | Staplarna är solida svarta rektanglar på en vit bakgrund. |
| `PlanetEmptyBars.png`  | Staplarna är svarta konturer; insidan av varje stapel är transparent (visar bakgrunden). |

Båda bilderna kodar samma numeriska sträng `"123456"` och har en stapelbredd på 4 pixlar, vilket säkerställer att de ser likadana ut förutom fyllningsstilen.

## Vanliga variationer och kantfall

### Ändra stapelbredden

Om din etikettskrivare förväntar sig en annan stapelbredd, ändra värdet på `XDimension.Pixels`. För högupplösta skrivare kan ett värde på **2** eller **3** pixlar vara att föredra; för lågupplösta skrivare kan **5** eller **6** pixlar förbättra skanningspålitligheten.

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 5; // example for coarse printers
```

### Använd ett annat bildformat

Aspose.Barcode stödjer PNG, JPEG, BMP, GIF och TIFF. Byt ut `BarCodeImageFormat.Png` mot ett annat enum‑värde för att matcha ditt efterföljande arbetsflöde.

```csharp
barcodeGenerator.Save("Planet.tiff", BarCodeImageFormat.Tiff);
```

### Generera flera streckkoder i en loop

När du behöver en batch av Planet‑streckkoder (t.ex. för en utskickslista), omslut generatorlogiken i en `foreach`‑loop och ändra datasträngen för varje iteration.

```csharp
string[] postalCodes = { "123456", "654321", "112233" };
int index = 1;
foreach (var code in postalCodes)
{
    var gen = new BarcodeGenerator(EncodeTypes.Planet, code);
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    gen.Save($@"C:\Barcodes\Planet_{index}_filled.png", BarCodeImageFormat.Png);
    gen.Parameters.Barcode.FilledBars = false;
    gen.Save($@"C:\Barcodes\Planet_{index}_empty.png", BarCodeImageFormat.Png);
    index++;
}
```

### Hantera ogiltig inmatning

Planet‑symbologin accepterar endast numeriska strängar med **5‑8** siffror. Att ange ett ogiltigt värde kastar ett `ArgumentException`. Skydda mot detta med en enkel valideringsmetod.

```csharp
bool IsValidPlanet(string value) => System.Text.RegularExpressions.Regex.IsMatch(value, @"^\d{5,8}$");

string data = "ABC123";
if (!IsValidPlanet(data))
{
    Console.WriteLine("Invalid Planet data – must be 5 to 8 digits.");
    return;
}
```

## Proffstips: Verifiera streckkoden med en skanner‑emulator

Aspose.Barcode innehåller en `BarcodeReader`‑klass som du kan använda för att bekräfta att den genererade bilden avkodas tillbaka till originaldata.

```csharp
using Aspose.Barcode.Reader;

// Verify filled barcode
using (BarCodeReader reader = new BarCodeReader(filledPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from filled image: {reader.GetCodeText()}");
}

// Verify empty barcode
using (BarCodeReader reader = new BarCodeReader(emptyPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from empty image: {reader.GetCodeText()}");
}
```

Om utskriften visar `"123456"` för båda filerna, har streckkoden genererats korrekt.

## Slutsats

Du vet nu hur du **skapar planet barcode**‑bilder i C# med både fyllda och tomma stapelstilar, styr **Planet barcode XDimension**, och sparar resultaten i PNG‑format med **Aspose.Barcode**‑biblioteket. Justera stapelbredden, byt bildformat eller loopa över en samling värden för att passa vilket postkod‑arbetsflöde som helst.

Nästa steg kan vara att utforska:

* **Lägga till mänskligt läsbar text** under streckkoden (`barcodeGenerator.Parameters.Caption.Show = true`).
* **Bädda in streckkoder i PDF‑dokument** med Aspose.PDF.
* **Generera andra post‑symbologier** såsom **USPS POSTNET** eller **Intelligent Mail**.

Känn dig fri att experimentera med parametrarna och integrera koden i ditt frakt‑ eller utskickssystem. Lycka till med kodandet!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Create planet barcode in C# – complete programming guide](/barcode/english/python-java/general/create-planet-barcode-in-c-complete-programming-guide/)
- [Barcode generator C# – create Planet barcode and RM4SCC example](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}