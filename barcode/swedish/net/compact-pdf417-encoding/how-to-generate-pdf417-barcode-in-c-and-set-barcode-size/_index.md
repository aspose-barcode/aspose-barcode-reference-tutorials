---
category: general
date: 2026-08-22
description: Lär dig hur du genererar PDF417‑streckkod i C# med Aspose.BarCode, ställer
  in streckkodens storlek, justerar kolumner och aktiverar kompakt läge.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- set barcode size
language: sv
lastmod: 2026-08-22
og_description: Generera PDF417‑streckkod i C# med Aspose.BarCode. Denna guide visar
  hur du ställer in streckkodens storlek, kontrollerar kolumner och aktiverar kompakt
  läge för en mindre bild.
og_image_alt: Screenshot of a generated PDF417 barcode in C# showing compact mode
og_title: Generera PDF417-streckkod i C# – ställ in storlek, kolumner och kompakt
  läge
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate PDF417 barcode in C# with Aspose.BarCode, set
    barcode size, adjust columns, and enable compact mode.
  headline: How to generate PDF417 barcode in C# and set barcode size
  type: TechArticle
tags:
- pdf417
- barcode
- csharp
title: Hur man genererar PDF417‑streckkod i C# och ställer in streckkodens storlek
url: /sv/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar PDF417‑streckkod i C# och ställer in streckkodsstorlek

Om du behöver **generera PDF417‑streckkod** i en .NET‑applikation, guidar den här artikeln dig genom hela processen. Du får se exakt **hur man genererar PDF417** med Aspose.BarCode, justerar **set barcode size**, och skapar en kompakt PNG som kan bäddas in i rapporter eller mobilappar.

Att skapa en streckkod kräver ingen separat grafikredigerare. I slutet av den här tutorialen har du en fullt fungerande C#‑metod som producerar en PDF417‑bild med exakt de dimensioner du behöver, klar för vidare bearbetning.

## Vad du kommer att lära dig

* Installera och referera Aspose.BarCode‑biblioteket.  
* Skapa en PDF417‑streckkodsgenerator och ange den kodade texten.  
* **Set barcode size** genom att konfigurera X‑dimension och kolumnantal.  
* Aktivera kompakt (trunkerad) läge för att minska symbolen.  
* Spara resultatet som en PNG‑fil.  
* Felsök vanliga problem som oläsliga koder och för stora bilder.

### Förutsättningar

* .NET 6.0 eller senare (API‑et fungerar även med .NET Framework 4.6+).  
* Grundläggande kunskap om C# och Visual Studio (eller någon annan C#‑IDE).  
* En giltig Aspose.BarCode‑licens (den fria utvärderingsversionen fungerar för testning).

> **Pro tip:** Om du planerar att generera många streckkoder i en loop, återanvänd en enda `BarcodeGenerator`‑instans och ändra bara `CodeText`‑egenskapen. Detta minskar minnesallokeringar.

## Generera PDF417‑streckkod med Aspose.BarCode

Det första steget är att instansiera `BarcodeGenerator` för PDF417‑symbologi. Detta objekt är ingångspunkten för alla streckkodsåtgärder.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,          // Symbology
    "Sample text for PDF417");   // Data to encode
```

*Varför detta är viktigt*: `EncodeTypes.Pdf417` talar om för biblioteket att använda PDF417‑standarden, som stödjer stora datamängder och felkorrigering. Konstruktorn accepterar också den data du vill koda, vilket eliminerar behovet av en separat `CodeText`‑tilldelning senare.

## Ställ in streckkodsstorlek och kolumnantal

PDF417‑symboler består av rader och kolumner av små rektangulära moduler. Genom att kontrollera modulbredden (X‑dimension) och antalet kolumner kan du finjustera de totala dimensionerna.

```csharp
// Step 2: Adjust the module size (X‑dimension) – 2 pixels per module
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Define the number of columns for the PDF417 code
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

*Förklaring*:  
* **X‑dimension** (`Pixels`) bestämmer hur bred varje modul är. Mindre värden ger en tätare streckkod, medan större värden ökar läsbarheten på lågupplösta skannrar.  
* **Columns** styr den horisontella layouten. Färre kolumner gör streckkoden högre; fler kolumner gör den bredare. Justera dessa två inställningar tillsammans för att uppnå exakt **set barcode size** som du behöver.

## Aktivera kompakt läge för en mindre streckkod

PDF417 innehåller ett “compact” (eller trunkerat) läge som tar bort onödig utfyllnad och minskar den totala fotavtrycket. Detta är särskilt användbart när du har begränsat skärmutrymme.

```csharp
// Step 4: Enable compact mode to truncate the barcode data
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

*Varför aktivera trunkering?*  
När `Truncate` är `true` utelämnar generatorn stoppmönstret och vissa felkorrigeringskodord som inte krävs för de flesta skanningsscenario. Den resulterande bilden blir ungefär 15‑20 % mindre utan att offra dataintegriteten för typiska användningsfall.

## Spara streckkoden som en PNG‑bild

Efter att ha konfigurerat storlek och läge, skriv streckkoden till disk. PNG är förlustfri, vilket säkerställer att modulernas kanter förblir skarpa.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save(
    "YOUR_DIRECTORY/CompactPdf417.png",
    BarCodeImageFormat.Png);
```

Filen `CompactPdf417.png` kommer att innehålla en skarp PDF417‑symbol som matchar de dimensioner du angav i föregående steg.

### Förväntat resultat

När du öppnar den sparade PNG‑filen bör du se en vertikalt orienterad PDF417‑streckkod bestående av tre kolumner, varje modul 2 px bred, och en total storlek på ungefär **120 × 240 px** (bredd × höjd). Att skanna bilden med någon standard‑PDF417‑läsare returnerar den ursprungliga texten “Sample text for PDF417”.

## Vanliga fallgropar och hur du undviker dem

| Symptom | Trolig orsak | Åtgärd |
|---------|--------------|-------|
| Streckkoden är oläslig | X‑dimension för liten för skannern | Öka `XDimension.Pixels` till 3 eller 4 |
| Bilden är för bred för UI | För många kolumner angivna | Minska `Pdf417.Columns` eller aktivera `Truncate` |
| Undantag `ArgumentOutOfRangeException` | Negativt eller noll kolumnantal | Säkerställ att `Columns` är ett positivt heltal (minst 1) |
| PNG‑filen är tom | Utskriftsvägen finns inte eller saknar skrivbehörighet | Verifiera att katalogen finns och att appen har skrivrättigheter |

> **Pro tip:** Använd `barcodeGenerator.ValidateParameters()` innan du anropar `Save()` för att fånga konfigurationsfel tidigt.

## Fullt körbart exempel

Nedan finns ett självständigt konsolprogram som innehåller alla stegen ovan. Kopiera det till ett nytt C#‑projekt, återställ Aspose.BarCode‑NuGet‑paketet, och kör det för att se resultatet.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with the data to encode
            var generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample text for PDF417");

            // Set module width (X‑dimension) – 2 px per module
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Choose a small number of columns to keep the barcode compact
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable truncation for a smaller image
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Optional: validate parameters before saving
            generator.ValidateParameters();

            // Save as PNG
            const string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

**När programmet körs** skapas `CompactPdf417.png` i programmets arbetskatalog. Skanna bilden med en mobilapp (t.ex. “Barcode Scanner”) för att verifiera att den kodade texten matchar källsträngen.

## Nästa steg och relaterade ämnen

* **Öka felkorrigeringsnivån** – justera `Pdf417.ErrorLevel` för miljöer med brusiga skanningar.  
* **Ändra orientering** – sätt `Pdf417.Rotate` till `RotationAngle.Rotate90` om du behöver en horisontell layout.  
* **Bädda in streckkoden i en PDF** – kombinera Aspose.PDF med Aspose.BarCode för att placera bilden direkt i ett dokument.  
* **Generera andra 2‑D‑streckkoder** – samma `BarcodeGenerator`‑klass stödjer DataMatrix, QR och Aztec; byt bara `EncodeTypes.Pdf417` mot önskad symbologi.

Genom att behärska **generate PDF417 barcode**‑tekniker kan du automatisera biljetthantering, lageretikettering och säker datatransmission i ett brett spektrum av .NET‑applikationer.

## Slutsats

Du vet nu hur du **genererar PDF417‑streckkod** i C#, exakt **set barcode size**, konfigurerar kolumner, aktiverar kompakt läge och sparar resultatet som en PNG. Använd dessa inställningar för att passa alla UI‑begränsningar eller skanningskrav, och utvidga metoden till andra streckkodformat vid behov. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

De följande tutorialerna behandlar närliggande ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [How to Generate PDF417 Barcode – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}