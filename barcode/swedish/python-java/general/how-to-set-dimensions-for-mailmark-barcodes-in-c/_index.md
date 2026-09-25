---
category: general
date: 2026-08-22
description: Lär dig hur du ställer in dimensioner för Mailmark‑streckkoder i C# och
  sparar dem som PNG‑bilder. Inkluderar fullständig kod, förklaringar och tips.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set dimensions
- Mailmark barcode C# example
- BarcodeGenerator dimensions
- set barcode size in C#
- save barcode as PNG
language: sv
lastmod: 2026-08-22
og_description: Hur man ställer in dimensioner för Mailmark‑streckkoder i C# och exporterar
  dem som PNG‑filer. Följ det kompletta exemplet och undvik vanliga fallgropar.
og_image_alt: Screenshot of two generated Mailmark barcode PNG files showing different
  dimensions
og_title: Hur man ställer in dimensioner för Mailmark‑streckkoder i C# – steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to set dimensions for Mailmark barcodes in C# and save them
    as PNG images. Includes full code, explanations, and tips.
  headline: How to set dimensions for Mailmark barcodes in C#
  type: TechArticle
tags:
- C#
- barcode
- Mailmark
- image generation
title: Hur man anger dimensioner för Mailmark‑streckkoder i C#
url: /sv/python-java/general/how-to-set-dimensions-for-mailmark-barcodes-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man anger dimensioner för Mailmark‑streckkoder i C#

Om du behöver **hur man ställer in dimensioner** för en Mailmark‑streckkod i C#, visar den här guiden de exakta stegen. Du kommer att se hur du konfigurerar X‑dimensionen och stapelhöjden, och sedan sparar streckkoden som en PNG‑bild utan extra verktyg.

Att generera poststreckkoder är en rutinuppgift när man bygger programvara för postetiketter, men standardstorleken matchar ofta inte skrivaren eller layoutkraven. I slutet av den här handledningen kommer du att kunna kontrollera streckkodens storlek exakt och producera två giltiga Mailmark‑typer (C‑type och L‑type) som är redo för utskrift.

**Vad du kommer att lära dig**

* Hur du anger X‑dimensionen (modulbredd) och stapelhöjden för en `BarcodeGenerator`.
* Hur du sparar den genererade streckkoden som en PNG‑fil med `BarCodeImageFormat`.
* Vanliga fallgropar såsom ogiltiga mappvägar eller icke‑stödda dimensionsvärden.
* Tips för att återanvända samma konfiguration för flera streckkoder.

## Förutsättningar

* .NET 6.0 eller senare (koden fungerar också med .NET Framework 4.6+).
* **Aspose.BarCode for .NET** NuGet‑paketet (eller ett kompatibelt bibliotek som tillhandahåller `BarcodeGenerator`, `EncodeTypes` och `BarCodeImageFormat`).
* Grundläggande kunskap om C#‑syntax och fil‑I/O.

> **Pro tip:** Installera paketet med CLI‑kommandot  
> `dotnet add package Aspose.BarCode` för att hålla ditt projekt prydligt.

## Steg 1: Definiera utdatamappen

Innan du skapar någon streckkod måste du bestämma var PNG‑filerna ska skrivas. Att använda en absolut sökväg undviker överraskningar på olika maskiner.

```csharp
// Step 1: Define the folder where the barcode images will be saved
string outputFolder = @"C:\Temp\Barcodes\";

// Ensure the directory exists; create it if necessary
if (!Directory.Exists(outputFolder))
{
    Directory.CreateDirectory(outputFolder);
}
```

*Varför detta är viktigt*: Om mappen inte finns kastar `Save` ett `IOException`. Anropet `Directory.CreateDirectory` är idempotent – det gör ingenting om mappen redan finns.

## Steg 2: Skapa en Mailmark C‑type streckkod och **ange dimensioner**

Mailmark C‑type kodar en 20‑tecken alfanumerisk sträng. Efter att ha initierat generatorn kan du **ange dimensioner** via `Parameters.Barcode`‑objektet.

```csharp
// Step 2: Create a Mailmark C‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkC = new BarcodeGenerator(EncodeTypes.Mailmark, "21B2254800659JW5O9QA6Y");

// Set the width of a single module (X‑dimension) to 4 pixels
mailmarkC.Parameters.Barcode.XDimension.Pixels = 4;

// Set the overall bar height to 50 pixels
mailmarkC.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the image; the second argument specifies PNG format
mailmarkC.Save($"{outputFolder}PostalMailmarkCType.png", BarCodeImageFormat.Png);
```

### Varför välja dessa värden?

* **X‑dimension** styr bredden på den minsta stapeln (en “modul”). Ett värde på `4` pixlar ger en streckkod som är lätt läsbar av de flesta laserskrivare samtidigt som filstorleken hålls måttlig.
* **BarHeight** bestämmer den vertikala storleken på staplarna. `50` pixlar är en vanlig höjd för standardpostetiketter, men du kan öka den för större format.

> **Edge case:** Vissa skrivare kräver en minsta stapelhöjd på 30 px. Att sätta höjden lägre än skrivarnas kapacitet kan leda till oläsliga streckkoder.

## Steg 3: Skapa en Mailmark L‑type streckkod och **ange dimensioner**

L‑type använder en längre datasträng (upp till 30 tecken). Samma metod för att ange dimensioner gäller.

```csharp
// Step 3: Create a Mailmark L‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkL = new BarcodeGenerator(EncodeTypes.Mailmark, "41038422416563762EF61AH8T");

// Reuse the same dimension settings for consistency
mailmarkL.Parameters.Barcode.XDimension.Pixels = 4;
mailmarkL.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the L‑type barcode image
mailmarkL.Save($"{outputFolder}PostalMailmarkLType.png", BarCodeImageFormat.Png);
```

### Återanvända konfiguration

Om du genererar många streckkoder med identiska dimensioner, överväg att extrahera konfigurationen till en hjälpfunktion:

```csharp
void ApplyStandardDimensions(BarcodeGenerator generator)
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.BarHeight.Pixels = 50;
}
```

Att anropa `ApplyStandardDimensions(mailmarkC)` och `ApplyStandardDimensions(mailmarkL)` minskar duplicering och gör framtida ändringar (t.ex. byte till 5‑pixel‑moduler) till en endradsredigering.

## Steg 4: Verifiera de genererade PNG‑filerna

Efter att programmet har körts, öppna de två PNG‑filerna i någon bildvisare. Du bör se två distinkta Mailmark‑streckkoder, var och en 4 px per modul och 50 px hög.

*Förväntat resultat*

| Filnamn                     | Ungefärliga dimensioner (px) |
|-----------------------------|------------------------------|
| `PostalMailmarkCType.png`   | 4 px × module × N modules |
| `PostalMailmarkLType.png`   | 4 px × module × N modules |

Den exakta bredden beror på den kodade datalängden, men höjden kommer konsekvent att vara **50 px** eftersom vi har satt `BarHeight.Pixels`.

## Vanliga fallgropar och hur man undviker dem

| Problem                         | Symptom                                            | Lösning |
|---------------------------------|----------------------------------------------------|---------|
| Ogiltig mappväg                 | `IOException: Could not find a part of the path`  | Använd `Path.Combine` med `Environment.SpecialFolder` eller verifiera sökvägssträngen. |
| X‑dimension satt till 0 eller negativ | Barcode appears as a solid block                | Säkerställ att `XDimension.Pixels` är ett positivt heltal (minimum 1). |
| Ej stödd `EncodeTypes.Mailmark` | `ArgumentException` at generator construction      | Bekräfta att du har en aktuell version av Aspose.BarCode‑biblioteket som inkluderar stöd för Mailmark. |
| Spara med fel bildformat        | Corrupted PNG file                                 | Använd `BarCodeImageFormat.Png` (eller `Jpeg` om du behöver ett annat format). |

## Utöka exemplet

* **Olika storlekar** – Ändra `XDimension.Pixels` till 3 för en mer kompakt streckkod, eller öka `BarHeight.Pixels` till 70 för större etiketter.
* **Batch‑generering** – Loopa igenom en samling datasträngar och applicera samma dimensionsinställningar för varje iteration.
* **Andra bildformat** – Byt ut `BarCodeImageFormat.Png` mot `BarCodeImageFormat.Jpeg` eller `BarCodeImageFormat.Bmp` om ditt arbetsflöde kräver det.

## Slutsats

Du vet nu **hur man anger dimensioner** för Mailmark‑streckkoder i C# och exporterar dem som PNG‑filer. Genom att konfigurera `XDimension.Pixels` och `BarHeight.Pixels` styr du den visuella storleken på både C‑type och L‑type streckkoder, så att de uppfyller skrivarspecifikationer och layoutkrav.  

Härifrån kan du experimentera med olika dimensionsvärden, integrera koden i ett större postetikett‑system, eller generera batcher av streckkoder för massutskick.

---

*Nästa steg*: utforska **BarcodeGenerator dimensions** för QR‑koder, eller läs Aspose.BarCode‑dokumentationen om **setting DPI** för högupplösta utskrifter. Om du behöver bädda in streckkoden i en PDF, kombinera detta tillvägagångssätt med **Aspose.PDF**‑biblioteket för en komplett end‑to‑end‑lösning.

## Vad bör du lära dig härnäst?

De följande handledningarna täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man ställer in kantlinje för ITF-14‑streckkodsanpassning](/barcode/english/net/itf-14-barcode-customization/)
- [Hur man konfigurerar Patch Code‑streckkoder med Aspose.BarCode för .NET](/barcode/english/net/patch-code-configuration/)
- [Hur man genererar DataMatrix‑streckkoder med Aspose.BarCode för .NET – Steg‑för‑steg‑guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}