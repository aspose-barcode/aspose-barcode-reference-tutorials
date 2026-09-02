---
category: general
date: 2026-07-18
description: Generera PDF417‑streckkod snabbt. Lär dig hur du ställer in länkat läge
  och hur du genererar PDF417‑streckkod med Aspose.BarCode i en tydlig steg‑för‑steg‑handledning.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to set linked mode
- how to generate pdf417 barcode
language: sv
lastmod: 2026-07-18
og_description: Generera PDF417‑streckkod omedelbart. Denna handledning visar hur
  du ställer in länkat läge och hur du genererar PDF417‑streckkod med Aspose.BarCode,
  komplett med körbar kod.
og_image_alt: Screenshot of a generated PDF417 barcode with linked mode enabled
og_title: Generera PDF417‑streckkod i C# – Fullständig steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate PDF417 barcode quickly. Learn how to set linked mode and how
    to generate PDF417 barcode with Aspose.BarCode in a clear step‑by‑step tutorial.
  headline: Generate PDF417 Barcode in C# – Complete Programming Guide
  type: TechArticle
- description: Generate PDF417 barcode quickly. Learn how to set linked mode and how
    to generate PDF417 barcode with Aspose.BarCode in a clear step‑by‑step tutorial.
  name: Generate PDF417 Barcode in C# – Complete Programming Guide
  steps:
  - name: Prerequisites
    text: '- .NET 6.0 or later (the code also works on .NET Framework 4.7+). - Basic
      C# knowledge. - Visual Studio 2022 (or any IDE you prefer). - A free Aspose.BarCode
      trial or licensed copy.'
  - name: Expected Output
    text: Running the program prints a confirmation line, and the folder now contains
      `Pdf417Linked.png`. Opening the PNG shows a three‑column PDF417 barcode that
      may span two rows (thanks to linked mode). Scanning it with a smartphone app
      reveals the text **“Aspose”**.
  - name: 1. *What if the barcode looks blurry?*
    text: Usually this is a DPI issue. Increase `XDimension.Pixels` or save the image
      at a higher resolution using `generator.Save(..., BarCodeImageFormat.Png, 300)`
      where `300` is the DPI.
  - name: 2. *Can I encode longer strings?*
    text: Yes—PDF417 can hold up to ~1,850 characters. If you exceed the capacity
      of the chosen column count, the library automatically adds rows. Adjust `Columns`
      or enable `IsLinked` to keep the barcode compact.
  - name: 3. *Do I need a license for production?*
    text: Aspose.BarCode works in evaluation mode, but the generated barcode will
      have a small watermark. Purchase a license to remove it and unlock advanced
      features like error‑correction level tweaking.
  - name: 4. *How to generate PDF417 barcode in other formats?*
    text: Simply change the second argument of `Save`. For JPEG use `BarCodeImageFormat.Jpeg`;
      for PDF use `BarCodeImageFormat.Pdf`.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspose
title: Generera PDF417-streckkod i C# – Komplett programmeringsguide
url: /sv/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera PDF417-streckkod i C# – Komplett programmeringsguide

Har du någonsin behövt **generera PDF417-streckkod** i en .NET‑app men varit osäker på var du ska börja? Du är inte ensam. Oavsett om du bygger en boarding‑pass‑skrivare, en lager‑scanner eller bara experimenterar med 2‑D‑streckkoder, är det enklare än du tror att få en PDF417 att fungera.

I den här guiden går vi igenom de exakta stegen för att **generera PDF417-streckkod** med Aspose.BarCode, visar **hur man ställer in linked mode** och täcker **hur man genererar PDF417-streckkod** med anpassade parametrar – allt i ett enda, kopiera‑och‑klistra‑klart exempel.

## Vad du kommer att lära dig

- Det minsta NuGet‑paketet du behöver.
- Hur du initierar PDF417‑generatorn med din egen text.
- **Hur man ställer in linked mode** så att streckkoden kan radbrytas.
- Ytterligare justeringar som modulstorlek och kolumnantal.
- Hur du sparar resultatet som PNG, JPEG eller något annat stödformat.
- Vanliga fallgropar och snabba felsökningstips.

### Förutsättningar

- .NET 6.0 eller senare (koden fungerar också på .NET Framework 4.7+).
- Grundläggande kunskaper i C#.
- Visual Studio 2022 (eller någon annan IDE du föredrar).
- En gratis Aspose.BarCode‑utvärderingsversion eller licensierad kopia.

> **Pro tip:** Om du är på en ny maskin, kör `dotnet add package Aspose.BarCode` från terminalen i din projektmapp. Det hämtar allt du behöver.

---

## Steg 1: Installera Aspose.BarCode och lägg till namnrymder

Först och främst – låt oss lägga till biblioteket i projektet.

```csharp
// Using the .NET CLI
dotnet add package Aspose.BarCode
```

Sedan, högst upp i din C#‑fil, inkludera de nödvändiga namnrymderna:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;   // For image format enums
```

> **Varför detta är viktigt:** Utan namnrymden `Aspose.BarCode.Generation` har du ingen åtkomst till `BarcodeGenerator`, och namnrymden `System.Drawing.Imaging` ger dig `ImageFormat`‑enumet för att spara filer.

---

## Steg 2: Initiera PDF417‑streckkodsgeneratorn

Nu skapar vi en generatorinstans och matar in den text vi vill koda. Detta är kärnan i **hur man genererar PDF417-streckkod**.

```csharp
// Step 2: Create a generator for PDF417 with the desired payload
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Aspose");
```

> **Förklaring:** `EncodeTypes.Pdf417` talar om för Aspose att vi arbetar med en PDF417‑symbologi. Det andra argumentet, `"Aspose"`, är den data som visas när streckkoden skannas.

---

## Steg 3: Definiera modulstorlek (X‑dimension)

Modulstorleken styr hur stor varje liten ruta (eller “pixel”) i streckkoden blir. Mindre värden ger en kompakt streckkod; större värden gör den mer läsbar på lågupplösta skrivare.

```csharp
// Step 3: Set the X‑dimension in pixels (module size)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Typiskt intervall:** 1–4 pixlar fungerar för de flesta skärmar. Om du skriver ut på en hög‑DPI‑etikettprinter, öka detta till 3 eller 4.

---

## Steg 4: Konfigurera kolumner och aktivera linked mode

Här svarar vi på **hur man ställer in linked mode**. Linked mode låter en PDF417‑streckkod delas över flera rader, vilket är praktiskt när du har begränsat horisontellt utrymme.

```csharp
// Step 4a: Choose the number of columns (affects data capacity & shape)
generator.Parameters.Barcode.Pdf417.Columns = 3;

// Step 4b: Turn on linked mode so the barcode can wrap
generator.Parameters.Barcode.Pdf417.IsLinked = true;
```

> **Varför linked mode?** Föreställ dig att du behöver att streckkoden ska passa i ett smalt UI‑element. Med `IsLinked = true` delar biblioteket automatiskt symbolen i rader samtidigt som läsbarheten bevaras.

> **Edge case:** Om du sätter `Columns` för lågt samtidigt som du aktiverar linked mode, kan Aspose öka antalet rader kraftigt, vilket kan överskrida en liten bild‑canvas. Håll koll på de slutliga bilddimensionerna.

---

## Steg 5: Spara streckkodsbilden

Till sist skriver du ut streckkoden till en fil. Du kan välja PNG, JPEG, BMP eller till och med PDF. PNG är förlustfri, vilket gör den idealisk för vidare bearbetning.

```csharp
// Step 5: Persist the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417Linked.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

> **Resultat:** Du får en skarp PDF417‑streckkod med tre kolumner, en 2‑pixel modulstorlek och länkade rader om datan överskrider en enskild rads bredd.

---

## Fullt fungerande exempel

Nedan är det kompletta, färdiga programmet. Kopiera‑och‑klistra in det i ett nytt konsolprojekt (`dotnet new console`) och tryck **F5**.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator with PDF417 and payload
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Aspose");

        // 2️⃣ Set module size (X‑dimension) – 2 pixels works well on most screens
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Define columns and enable linked mode
        generator.Parameters.Barcode.Pdf417.Columns = 3;
        generator.Parameters.Barcode.Pdf417.IsLinked = true;   // ← how to set linked mode

        // 4️⃣ Choose output path and save as PNG
        string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417Linked.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ PDF417 barcode generated! Saved at: {outputPath}");
    }
}
```

### Förväntad output

När programmet körs skrivs en bekräftelse‑rad ut, och mappen innehåller nu `Pdf417Linked.png`. När du öppnar PNG‑filen ser du en PDF417‑streckkod med tre kolumner som kan sträcka sig över två rader (tack vare linked mode). Skannar du den med en smartphone‑app visas texten **“Aspose”**.

---

## Vanliga frågor & felsökning

### 1. *Vad händer om streckkoden ser suddig ut?*  
Vanligtvis är det ett DPI‑problem. Öka `XDimension.Pixels` eller spara bilden i högre upplösning med `generator.Save(..., BarCodeImageFormat.Png, 300)` där `300` är DPI.

### 2. *Kan jag koda längre strängar?*  
Ja – PDF417 kan innehålla upp till ~1 850 tecken. Om du överskrider kapaciteten för det valda kolumnantalet lägger biblioteket automatiskt till rader. Justera `Columns` eller aktivera `IsLinked` för att hålla streckkoden kompakt.

### 3. *Behöver jag en licens för produktion?*  
Aspose.BarCode fungerar i utvärderingsläge, men den genererade streckkoden får ett litet vattenmärke. Köp en licens för att ta bort det och låsa upp avancerade funktioner som justering av felkorrigeringsnivå.

### 4. *Hur genererar man PDF417‑streckkod i andra format?*  
Byt helt enkelt ut det andra argumentet i `Save`. För JPEG använd `BarCodeImageFormat.Jpeg`; för PDF använd `BarCodeImageFormat.Pdf`.

---

## Utöka exemplet

Nu när du vet **hur man genererar PDF417‑streckkod** och **hur man ställer in linked mode**, kanske du vill utforska:

- **Felkorrektionnivå** – `generator.Parameters.Barcode.Pdf417.ErrorCorrection = Pdf417ErrorCorrectionLevel.Level3;`
- **Lägga till en ram** – `generator.Parameters.Barcode.BorderWidth = 1;`
- **Anpassade färger** – `generator.Parameters.Barcode.ForeColor = Color.DarkBlue;`
- **Bädda in streckkoden i en PDF‑rapport** – kombinera Aspose.PDF med Aspose.BarCode.

Varje av dessa justeringar följer samma mönster: hitta rätt egenskap under `generator.Parameters.Barcode.Pdf417` (eller det generiska `Barcode`‑objektet) och sätt ett värde.

---

## Slutsats

Vi har gått igenom allt du behöver för att **generera PDF417‑streckkod** i C#, från att installera Aspose.BarCode till att konfigurera linked mode och spara bilden. Genom att följa stegen ovan får du en produktionsklar streckkodsgenerator som kan integreras i vilken .NET‑lösning som helst.

Kom ihåg, de viktigaste slutsatserna är:

1. Initiera med `EncodeTypes.Pdf417`.
2. Justera `XDimension` för visuell tydlighet.
3. Ställ in `Columns` och aktivera `IsLinked` för att kontrollera layouten (**hur man ställer in linked mode**).
4. Spara i önskat format.

Känn dig fri att experimentera med de extra parametrarna, och tveka inte att dela dina resultat eller ställa frågor i kommentarerna. Lycka till med kodningen, och må dina streckkoder alltid skannas på första försöket!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}