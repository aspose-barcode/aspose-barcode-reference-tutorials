---
category: general
date: 2026-09-07
description: Generera PDF417‑streckkod i C# och lär dig hur du ställer in streckkodens
  dimensioner för exakt kontroll. Följ den här steg‑för‑steg‑guiden för att skapa
  en PNG‑bild.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- how to set barcode dimensions
language: sv
lastmod: 2026-09-07
og_description: Generera PDF417‑streckkod i C# och lär dig hur du ställer in streckkodens
  dimensioner. Denna handledning visar ett komplett, körbart exempel.
og_image_alt: Generated PDF417 barcode image with custom dimensions
og_title: Generera PDF417-streckkod i C# – fullständig guide med dimensioner
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  headline: How to generate PDF417 barcode in C# with custom dimensions
  type: TechArticle
- description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  name: How to generate PDF417 barcode in C# with custom dimensions
  steps:
  - name: Expected output
    text: '- **File:** `Pdf417Layout.png` (PNG, lossless) - **Dimensions:** Determined
      by `XDimension` (2 px) × (columns × rows) matrix - **Content:** A scannable
      PDF417 barcode encoding the Unicode string `Åspóse.Barcóde©`'
  - name: What if I need a larger image for printing?
    text: Increase `XDimension.Pixels` to 4 or 5. Larger values produce a higher‑resolution
      barcode but also increase file size.
  - name: Can I encode more data than the example string?
    text: Yes. PDF417 can hold up to 1,850 characters. Just replace the text argument
      in the `BarcodeGenerator` constructor. If the data exceeds the matrix capacity,
      the library automatically adds extra rows.
  - name: How does error correction work?
    text: 'PDF417 includes built‑in error correction. You can adjust its level via:'
  - name: What if the barcode appears blurry on screen?
    text: 'Make sure the output image’s DPI matches the display environment. You can
      set DPI when saving:'
  - name: Next steps
    text: '- Explore **how to generate PDF417 barcode** with different image formats
      (JPEG, BMP). - Learn **how to set barcode dimensions** dynamically based on
      user input or device DPI. - Integrate the barcode generation into an ASP.NET
      Core API to serve barcodes on demand.'
  type: HowTo
tags:
- barcode generation
- PDF417
- C#
title: Hur man genererar PDF417-streckkod i C# med anpassade dimensioner
url: /sv/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar PDF417‑streckkod i C# med anpassade dimensioner

Om du behöver **generera PDF417‑streckkod** i en .NET‑applikation visar den här guiden exakt hur du gör det. Du får se ett komplett, körbart exempel som skapar en PNG‑bild samtidigt som du kan kontrollera streckkodens dimensioner.

Att generera en PDF417‑streckkod är ett vanligt krav för lagersystem, boardingkort och säkra dokument. I den här handledningen lär du dig också **hur du ställer in streckkodens dimensioner** så att resultatet matchar dina layoutbehov.

## Förutsättningar

Innan du börjar, se till att du har:

- .NET 6.0 SDK eller senare installerat  
- Visual Studio 2022 (eller någon C#‑kompatibel IDE)  
- NuGet‑paketet **Aspose.BarCode for .NET** (eller något kompatibelt bibliotek som stödjer PDF417)  

Du kan lägga till paketet med följande kommando:

```bash
dotnet add package Aspose.BarCode
```

## Steg 1: Skapa en PDF417‑streckkodsgenerator

Det första steget är att instansiera en `BarcodeGenerator` med typen `EncodeTypes.Pdf417` och den text du vill koda. Generatorobjektet innehåller alla inställningar för streckkoden.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");
```

**Varför detta är viktigt:** `EncodeTypes.Pdf417`‑enumet talar om för biblioteket att använda PDF417‑symbologi, som stödjer stora datamängder och felkorrigering. Textsträngen kan innehålla Unicode‑tecken, så du kan koda internationella symboler utan extra arbete.

## Steg 2: Hur du ställer in streckkodens dimensioner

Att kontrollera storleken på varje modul (den minsta svarta/vita kvadraten) bestämmer den totala bildupplösningen. `XDimension.Pixels`‑egenskapen sätter pixelbredden för en modul.

```csharp
        // Step 2: Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Varför detta är viktigt:** En större `XDimension` ger en högre upplösning, vilket är användbart för utskrift eller skanning på avstånd. Omvänt minskar ett mindre värde filstorleken för webbbruk.

## Steg 3: Definiera PDF417‑layouten (kolumner och rader)

PDF417 låter dig påverka matrisens form genom att ange antalet kolumner och rader. Detta kan påverka läsbarheten och den fysiska storleken på streckkoden.

```csharp
        // Step 3: Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

**Varför detta är viktigt:** Att justera kolumner och rader låter dig passa streckkoden i ett specifikt utrymme eller uppfylla en scanners bildförhållandekrav. Biblioteket lägger automatiskt till utfyllnad om data inte fyller matrisen helt.

## Steg 4: Spara streckkoden som en PNG‑bild

Slutligen skriver du den genererade streckkoden till en fil. PNG bevarar förlustfri kvalitet, vilket gör den idealisk för vidare bearbetning.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

När du kör programmet visas `Pdf417Layout.png` i projektets output‑mapp. Bilden ser ut så här:

![Generated PDF417 barcode image with custom dimensions](og_image_placeholder.png)

*Bild alt text: Genererad PDF417‑streckkod med anpassade dimensioner*  

**Varför detta är viktigt:** Att spara som PNG säkerställer att de exakta modul‑dimensionerna du ställt in behålls, vilket är avgörande för efterföljande skanningsapplikationer.

## Komplett exempel i ett block

Nedan är hela programmet som du kan kopiera, klistra in och köra utan ändringar (förutom om du vill ändra sökvägen för output).

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

### Förväntat resultat

- **Fil:** `Pdf417Layout.png` (PNG, förlustfri)  
- **Dimensioner:** Bestäms av `XDimension` (2 px) × (kolumner × rader) matris  
- **Innehåll:** En skannbar PDF417‑streckkod som kodar Unicode‑strängen `Åspóse.Barcóde©`

## Vanliga frågor och specialfall

### Vad händer om jag behöver en större bild för utskrift?

Öka `XDimension.Pixels` till 4 eller 5. Större värden ger en högre upplösning men ökar också filstorleken.

### Kan jag koda mer data än exempelsträngen?

Ja. PDF417 kan hålla upp till 1 850 tecken. Byt bara ut textargumentet i `BarcodeGenerator`‑konstruktorn. Om data överskrider matrisens kapacitet lägger biblioteket automatiskt till extra rader.

### Hur fungerar felkorrigering?

PDF417 innehåller inbyggd felkorrigering. Du kan justera nivån via:

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // 0‑8, higher = more correction
```

Högre nivåer ökar robustheten men ger större streckkoder.

### Vad händer om streckkoden blir suddig på skärmen?

Se till att bildens DPI matchar displaymiljön. Du kan sätta DPI vid sparande:

```csharp
barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png, 300);
```

## Proffstips

- **Proffstips:** Testa alltid den genererade streckkoden med den faktiska scanner du planerar att använda. Olika enheter har olika tolerans för modulstorlek och tysta zoner.  
- **Se upp för:** Mycket små `XDimension`‑värden (< 1 px) kan renderas som osynliga linjer på hög‑DPI‑skärmar.  
- **Tips för webbappar:** Servera PNG:n med `Cache-Control: public, max-age=86400` för att minska upprepade genereringskostnader.

## Slutsats

Du vet nu hur du **genererar PDF417‑streckkod** i C# och exakt **ställer in streckkodens dimensioner** för att passa alla krav. Det kompletta, körbara exemplet visar hur man skapar en PNG‑bild med anpassad kolumn/rad‑layout och modulstorlek, redo för utskrift eller digital distribution.

### Nästa steg

- Utforska **hur man genererar PDF417‑streckkod** med olika bildformat (JPEG, BMP).  
- Lär dig **hur du ställer in streckkodens dimensioner** dynamiskt baserat på användarinput eller enhetens DPI.  
- Integrera streckkodsgenereringen i ett ASP.NET Core‑API för att leverera streckkoder på begäran.

Känn dig fri att experimentera med andra PDF417‑inställningar som felkorrigering, marginaler och färg. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Generate PDF417 Barcode in C# – Complete Guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}