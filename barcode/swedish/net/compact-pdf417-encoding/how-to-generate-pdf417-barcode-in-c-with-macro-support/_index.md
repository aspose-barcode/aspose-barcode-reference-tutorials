---
category: general
date: 2026-10-21
description: Lär dig hur du genererar PDF417‑streckkod i C# med Aspose.BarCode. Detaljerade
  steg täcker PDF417‑streckkodinställningar, skapande av macro‑PDF417‑streckkod och
  sparande som PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate PDF417 barcode
- PDF417 barcode settings
- Macro PDF417 barcode
- barcode generator C#
- BarCodeImageFormat PNG
- EncodeTypes.MacroPdf417
language: sv
lastmod: 2026-10-21
og_description: Hur man genererar PDF417‑streckkod i C# med Aspose.BarCode. Följ den
  här steg‑för‑steg‑handledningen för att konfigurera PDF417‑streckkodinställningar,
  skapa en makro‑PDF417‑streckkod och exportera till PNG.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C# code
og_title: Hur man genererar PDF417-streckkod i C# – komplett guide
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Detailed
    steps cover PDF417 barcode settings, macro PDF417 barcode creation, and saving
    as PNG.
  headline: How to generate PDF417 barcode in C# with macro support
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Detailed
    steps cover PDF417 barcode settings, macro PDF417 barcode creation, and saving
    as PNG.
  name: How to generate PDF417 barcode in C# with macro support
  steps:
  - name: '**Create a `BarcodeGenerator` instance** using `EncodeTypes.MacroPdf417`.'
    text: '**Create a `BarcodeGenerator` instance** using `EncodeTypes.MacroPdf417`.'
  - name: '**Adjust basic barcode appearance** (module size, colors, etc.).'
    text: '**Adjust basic barcode appearance** (module size, colors, etc.).'
  - name: '**Configure PDF417‑specific settings**, including macro‑related fields.'
    text: '**Configure PDF417‑specific settings**, including macro‑related fields.'
  - name: '**Save the generated barcode image** with `BarCodeImageFormat PNG`.'
    text: '**Save the generated barcode image** with `BarCodeImageFormat PNG`.'
  type: HowTo
tags:
- PDF417
- barcode
- C#
- Aspose.BarCode
title: Hur man genererar PDF417-streckkod i C# med makrostöd
url: /sv/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-macro-support/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar PDF417‑streckkod i C# med makrostöd

Om du behöver generera PDF417‑streckkod i C# visar den här guiden en komplett, färdig‑att‑köra lösning. Oavsett om du bygger ett logistiskt etikettssystem eller kodar stora datamängder, får du se hur du konfigurerar PDF417‑streckkodinställningar, skapar en makro‑PDF417‑streckkod och sparar resultatet som en PNG‑bild.

Att generera en PDF417‑streckkod kräver ingen låg‑nivå bitmanipulation. Genom att använda **barcode generator C#**‑klassen från Aspose.BarCode kan du fokusera på affärslogiken medan biblioteket hanterar kodning, felkorrigering och bildrendering.

## Vad du behöver

Innan du börjar, se till att du har:

- **.NET 6.0** eller senare (koden fungerar även med .NET Framework 4.6+)
- **Aspose.BarCode for .NET** NuGet‑paket (`Install-Package Aspose.BarCode`)
- En utvecklingsmiljö såsom Visual Studio 2022 eller Visual Studio Code
- Skrivbehörighet till en mapp där PNG‑bilden ska sparas

Dessa förutsättningar säkerställer att exemplet kompileras och körs utan ytterligare konfiguration.

## Så här genererar du PDF417‑streckkod – steg‑för‑steg‑översikt

Nedan är en kortfattad färdplan för processen:

1. **Skapa en `BarcodeGenerator`‑instans** med `EncodeTypes.MacroPdf417`.
2. **Justera grundläggande streckkodutseende** (modulstorlek, färger osv.).
3. **Konfigurera PDF417‑specifika inställningar**, inklusive makro‑relaterade fält.
4. **Spara den genererade streckkodsbilden** med `BarCodeImageFormat PNG`.

Varje steg förklaras i detalj, med kompletta kodsnuttar som du kan kopiera direkt in i en konsolapp.

## Steg 1: Ställ in utvecklingsmiljön

Skapa ett nytt konsolprojekt och lägg till Aspose.BarCode‑referensen:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Öppna `Program.cs` och lägg till de nödvändiga namnutrymmena:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Dessa importeringar ger dig åtkomst till `BarcodeGenerator`, `EncodeTypes` och `BarCodeImageFormat`.

## Steg 2: Skapa makro‑PDF417‑streckkodsgeneratorn

Den första raden i implementationen skapar **Macro PDF417 barcode**‑objektet. Enum‑värdet `EncodeTypes.MacroPdf417` talar om för biblioteket att använda makrovarianten av PDF417.

```csharp
// Step 1: Create a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample Text"))
{
    // Subsequent configuration goes here
}
```

> **Varför detta är viktigt:** Att använda `EncodeTypes.MacroPdf417` aktiverar makrofälten (`FileID`, `SegmentID` osv.) som låter dig dela upp en stor nyttolast över flera streckkods‑bilder samtidigt som ordningen bevaras.

## Steg 3: Justera grundläggande streckkodutseende

Innan du finjusterar PDF417‑specifika parametrar, sätt modul‑ (pixel)‑bredden. Ett värde på `2` ger en tydlig, skannbar bild utan onödig filstorlek.

```csharp
// Step 2: Adjust basic barcode appearance
generator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel width of a single module
```

Du kan också ändra förgrunds‑/bakgrundsfärger här om ditt UI kräver en annan palett.

## Steg 4: Konfigurera PDF417‑specifika inställningar

**PDF417‑streckkodinställningarna** exponeras via `generator.Parameters.Barcode.Pdf417`. De viktigaste makrofälten visas nedan:

```csharp
// Step 3: Configure PDF417‑specific settings
generator.Parameters.Barcode.Pdf417.Columns = 5;                     // number of columns (affects width)
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;     // unique file identifier
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // segment number within the file
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;  // total number of segments
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";  // optional human‑readable name
```

### Förstå varje egenskap

| Property | Purpose | Typical range |
|----------|---------|---------------|
| `Columns` | Styr hur många datakolumner varje rad innehåller. Fler kolumner minskar antalet rader men ökar bredden. | 1 – 30 |
| `MacroPdf417FileID` | En 32‑bit identifierare som grupperar alla segment av samma logiska fil. Måste vara samma för varje segment. | Valfritt positivt heltal |
| `MacroPdf417SegmentID` | Noll‑baserat index för det aktuella segmentet. Öka för varje efterföljande streckkod. | 0 – `SegmentsCount`‑1 |
| `MacroPdf417SegmentsCount` | Totalt antal segment som utgör hela filen. Alla segment måste genereras. | ≥ 1 |
| `MacroPdf417FileName` | Valfritt beskrivande namn (max 255 tecken). Användbart för felsökning. | Alfanumerisk sträng |

> **Proffstips:** Håll `Columns` mellan 3 och 7 för de flesta etikett‑skrivare. Större värden kan överskrida utskriftsbredden på låg‑upplösta enheter.

## Steg 5: Spara streckkoden som en PNG‑bild

Till sist, skriv streckkoden till disk med `BarCodeImageFormat PNG`. PNG bevarar förlustfri kvalitet, vilket är avgörande för pålitlig skanning.

```csharp
// Step 4: Save the generated barcode image
string outputPath = Path.Combine(Environment.CurrentDirectory, "MacroPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
```

När programmet avslutas hittar du `MacroPdf417.png` i projektmappen. Att öppna filen visar en ren Macro PDF417‑streckkod redo för utskrift.

### Förväntat resultat

Den genererade bilden ser ut ungefär som exemplet nedan (endast illustrativt):

![Macro PDF417 barcode example](macro-pdf417-barcode.png "Macro PDF417 barcode generated by C# code")

*Bildens alt‑text är “Macro PDF417 barcode generated with C# code”, vilket uppfyller åtkomst‑ och SEO‑krav.*

## Vanliga fallgropar och felsökning

| Issue | Symptom | Fix |
|-------|---------|-----|
| **Incorrect `EncodeTypes`** | Barcode renders as QR code or plain text. | Ensure you use `EncodeTypes.MacroPdf417` (not `EncodeTypes.Pdf417`). |
| **Mismatched segment IDs** | Scanner reports “missing segment”. | Increment `MacroPdf417SegmentID` sequentially and keep `SegmentsCount` consistent across all files. |
| **Too large module size** | Barcode becomes too wide for the label. | Reduce `XDimension.Pixels` or lower `Columns`. |
| **File path errors** | `UnauthorizedAccessException` when saving. | Write to a folder you own, e.g., `Environment.CurrentDirectory`. |
| **Missing NuGet package** | Compile error: `BarcodeGenerator` not found. | Run `dotnet add package Aspose.BarCode` before building. |

Att åtgärda dessa problem tidigt sparar tid när du integrerar streckkodsgenerering i större arbetsflöden.

## Utöka exemplet

Nu när du kan generera en enskild Macro PDF417‑streckkod, överväg följande nästa steg:

- **Batch‑generering**: Loopa över en samling databit, uppdatera `MacroPdf417SegmentID` för varje iteration.
- **Olika bildformat**: Byt ut `BarCodeImageFormat.Png` mot `Jpeg` eller `Bmp` om ditt downstream‑system föredrar dem.
- **Inbäddning i PDF‑filer**: Använd Aspose.PDF för att placera PNG‑filen i en PDF‑rapport för distribution.
- **Skanningsverifiering**: Testa de genererade streckkoderna med en hårdvaruskanner eller en mobilapp som stödjer Macro PDF417.

Dessa variationer behåller kärnan i **PDF417 barcode settings** intakt samtidigt som de anpassar utdata till ditt projekts behov.

## Slutsats

Du vet nu **hur man genererar PDF417‑streckkod** i C# med Aspose.BarCode, från att skapa en `BarcodeGenerator` med `EncodeTypes.MacroPdf417` till att konfigurera makrofält och spara resultatet som en `BarCodeImageFormat PNG`. Den kompletta, körbara koden demonstrerar den rekommenderade metoden, förklarar varför varje inställning är viktig och belyser vanliga fallgropar du kan stöta på.

Känn dig fri att experimentera med kolumnantal, färger eller utdataformat, och integrera generatorn i dina egna applikationer för pålitlig, högdensitets‑datakodning.


## Vad bör du lära dig härnäst?


Följande handledningar täcker nära besläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [How to generate PDF417 barcodes in C# with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [How to save barcode and generate PDF417 with Aspose in C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}