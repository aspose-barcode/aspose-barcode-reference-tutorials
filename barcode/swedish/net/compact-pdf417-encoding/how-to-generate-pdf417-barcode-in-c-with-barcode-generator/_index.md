---
category: general
date: 2026-08-25
description: Lär dig hur du genererar PDF417‑streckkod i C# med streckkodsgeneratorn
  C# PDF417‑bibliotek – steg‑för‑steg‑kodexempel.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- barcode generator C# PDF417
- PDF417 barcode C#
- barcode resolution C#
- Aspose.BarCode PDF417
language: sv
lastmod: 2026-08-25
og_description: Generera PDF417‑streckkod i C# med streckkodsgeneratorn C# PDF417‑biblioteket.
  Följ den här koncisa handledningen för fullständig kod och bästa praxis.
og_image_alt: Generated PDF417 barcode example
og_title: Generera PDF417-streckkod i C# – komplett guide
schemas:
- author: Aspose
  dateModified: '2026-08-25'
  description: Learn how to generate PDF417 barcode in C# with the barcode generator
    C# PDF417 library – step-by-step code examples.
  headline: How to generate PDF417 barcode in C# with Barcode Generator
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Hur man genererar PDF417‑streckkod i C# med Barcode Generator
url: /sv/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så genererar du PDF417‑streckkod i C# med Barcode Generator

Om du behöver **generera PDF417‑streckkod** i en .NET‑applikation, visar den här guiden en färdig‑att‑köra lösning. Med **barcode generator C# PDF417**‑biblioteket kan du styra dimensioner, kolumner, rader och bildformat med bara några rader kod.

Du kommer att lära dig hur du skapar högupplösta streckkoder, anpassar layouten och sparar resultatet som PNG‑filer — utan att lämna din IDE.

## Vad du behöver

- .NET 6.0 eller senare (koden fungerar också med .NET Framework 4.6+)
- Aspose.BarCode för .NET‑paketet (installera via NuGet: `Install-Package Aspose.BarCode`)
- En mapp där de genererade PNG‑bilderna kommer att sparas
- Grundläggande kunskap om C#‑syntax

## Steg 1: Ställ in projektet och importera namnrymder

Skapa en ny konsolapplikation (eller lägg till koden i ett befintligt projekt) och lägg till de nödvändiga using‑direktiven:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

`Aspose.BarCode.Generation`‑namnrymden tillhandahåller `BarcodeGenerator`, medan `Aspose.BarCode` innehåller `BarCodeImageFormat`‑enum.

## Steg 2: Initiera PDF417‑streckkodsgeneratorn

Instansiera `BarcodeGenerator` med PDF417‑kodningstypen och den text du vill koda. Exemplet använder en sträng med icke‑ASCII‑tecken för att demonstrera Unicode‑stöd.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**Varför detta är viktigt:** `EncodeTypes.Pdf417` talar om för biblioteket att producera en PDF417‑streckkod, vilket är en staplad linjär streckkod idealisk för att lagra stora mängder data. Att ange texten vid konstruktionen säkerställer att generatorn är redo att rendera omedelbart.

## Steg 3: Förbättra upplösning med X‑dimension

X‑dimensionen (modulbredd) styr hur många pixlar varje liten stapel upptar. Ett större värde ger en tydligare bild, särskilt vid utskrift.

```csharp
// Step 3: Define the module (X) dimension in pixels for better resolution
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Att sätta `Pixels = 2` ger en bra balans mellan storlek och läsbarhet. Du kan öka detta värde för hög‑DPI‑utdata, men var medveten om större filstorlekar.

## Steg 4: Generera en streckkod med ett fast kolumnantal

En PDF417‑streckkod kan ordnas i ett specifikt antal kolumner. Här begär vi **2 kolumner** och låter biblioteket bestämma radantalet automatiskt.

```csharp
// Step 4: Generate a barcode with 2 columns and save it as PNG
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 2;   // columns = 2, rows = auto
barcodeGenerator.Save("Pdf417Columns2.png", BarCodeImageFormat.Png);
```

**Resultat:** `Pdf417Columns2.png` innehåller en kompakt streckkod med två vertikala staplar.

## Steg 5: Låt generatorn bestämma kolumner och sätt ett fast radantal

När du behöver ett specifikt antal rader — t.ex. för att passa en etikettshöjd — kan du ange rader medan du låter kolumner vara på *auto*.

```csharp
// Step 5: Generate a barcode with 6 rows (columns set to auto) and save it
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 0;   // columns = auto
barcodeGenerator.Parameters.Barcode.Pdf417.Rows = 6;      // rows = 6
barcodeGenerator.Save("Pdf417Rows6.png", BarCodeImageFormat.Png);
```

Biblioteket beräknar det optimala kolumnantalet för att rymma data inom sex rader.

## Steg 6: Ange både kolumner och rader för en anpassad layout

Ibland har du strikta layoutbegränsningar (t.ex. ett förtryckt formulär). Du kan explicit ange båda dimensionerna:

```csharp
// Step 6: Generate a barcode with 4 columns and 9 rows, then save it
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;   // columns = 4
barcodeGenerator.Parameters.Barcode.Pdf417.Rows = 9;      // rows = 9
barcodeGenerator.Save("Pdf417Rows9Columns4.png", BarCodeImageFormat.Png);
```

Detta skapar en streckkod som exakt matchar ett 4 × 9‑rutnät, användbart för justering med fysiska mallar.

## Fullt körbart exempel

Nedan är ett komplett program som kör alla fem steg i sekvens. Kopiera det till `Program.cs` och kör projektet.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with sample text containing Unicode characters
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // Improve image sharpness
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 1️⃣ Two columns, rows auto
            generator.Parameters.Barcode.Pdf417.Columns = 2;
            generator.Parameters.Barcode.Pdf417.Rows = 0; // explicit auto
            generator.Save("Pdf417Columns2.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: Pdf417Columns2.png");

            // 2️⃣ Six rows, columns auto
            generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
            generator.Parameters.Barcode.Pdf417.Rows = 6;
            generator.Save("Pdf417Rows6.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: Pdf417Rows6.png");

            // 3️⃣ Custom layout: 4 columns × 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows = 9;
            generator.Save("Pdf417Rows9Columns4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: Pdf417Rows9Columns4.png");
        }
    }
}
```

**Förväntat resultat**

När programmet körs skapas tre PNG‑filer i projektets output‑mapp:

- `Pdf417Columns2.png` – en streckkod med två vertikala kolumner.
- `Pdf417Rows6.png` – en streckkod utsträckt till sex rader.
- `Pdf417Rows9Columns4.png` – en streckkod ordnad i ett 4 × 9‑rutnät.

Du kan öppna någon av bilderna med en standardvisare för att verifiera att streckkoden skannas korrekt med en PDF417‑skannerapp.

## Pro‑tips och vanliga fallgropar

- **Unicode‑hantering**: Generatorn kodar automatiskt Unicode‑tecken, men se till att målskannern stödjer den teckenuppsättning du använder.
- **Bildformat**: PNG bevarar förlustfri kvalitet. Om du behöver ett vektorformat (t.ex. SVG) för skalning, ersätt `BarCodeImageFormat.Png` med `BarCodeImageFormat.Svg`.
- **Prestanda**: Återanvändning av samma `BarcodeGenerator`‑instans (som visas) är mer effektivt än att skapa en ny för varje layout.
- **Felhantering**: Omslut `Save`‑anrop med `try/catch` för att fånga I/O‑fel, särskilt när du skriver till skyddade kataloger.
- **Utskriftsaspekter**: För utskrivna etiketter, öka `XDimension.Pixels` till 3 eller 4 för att undvika pixelering vid typisk DPI (300 dpi).

## Slutsats

Du vet nu hur du **genererar PDF417‑streckkod** i C# med hjälp av **barcode generator C# PDF417**‑biblioteket. Handledningen täckte inställning av upplösning, styrning av

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to Generate PDF417 Barcode – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [java barcode library – Add barcode to PDF using Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}