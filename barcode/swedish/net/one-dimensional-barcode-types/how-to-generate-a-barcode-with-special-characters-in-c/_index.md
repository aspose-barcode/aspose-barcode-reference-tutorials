---
category: general
date: 2026-10-02
description: streckkod med specialtecken i C# – lär dig hur du genererar en streckkod
  med specialtecken med Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode with special characters
- how to generate barcode c#
language: sv
lastmod: 2026-10-02
og_description: streckkod med specialtecken i C# – den här handledningen visar hur
  man genererar streckkod i C# som inkluderar accentuerade och varumärkessymboler,
  komplett med kod och förklaringar.
og_image_alt: barcode with special characters example output
og_title: Generera en streckkod med specialtecken i C# – steg‑för‑steg guide
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: barcode with special characters in C# – learn how to generate a barcode
    with special characters using Aspose.BarCode.
  headline: How to generate a barcode with special characters in C#
  type: TechArticle
- description: barcode with special characters in C# – learn how to generate a barcode
    with special characters using Aspose.BarCode.
  name: How to generate a barcode with special characters in C#
  steps:
  - name: Why this works
    text: '* **Unicode support** – `BarcodeGenerator` accepts a `string` containing
      any Unicode glyph, so characters like **Å**, **ó**, and **©** are encoded without
      extra steps. * **MacroPdf417** – This format allows you to attach file‑level
      metadata (file ID, segment ID, checksum, etc.) that many enterprise '
  - name: Pro tip
    text: If you target a high‑density label printer, increase `XDimension.Pixels`
      to `3` or `4` to avoid pixel‑level distortion.
  - name: Edge case handling
    text: '* **Large file IDs** – The `FileID` property accepts a 32‑bit integer.
      If your system uses GUIDs, hash the GUID into a 32‑bit value before assignment.
      * **Timestamp precision** – The property stores a `DateTime`. If you need sub‑second
      precision, include it in the filename instead, as the standard d'
  - name: Expected output
    text: '* A PNG file approximately 300 × 150 pixels (size varies with column count).
      * When scanned with a PDF417‑compatible reader, the decoded text displays exactly
      **Åspóse.Barcóde©** and the scanner can reconstruct the original file using
      the macro fields.'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Hur man genererar en streckkod med specialtecken i C#
url: /sv/net/one-dimensional-barcode-types/how-to-generate-a-barcode-with-special-characters-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så genererar du en streckkod med specialtecken i C#

Om du behöver generera en streckkod med specialtecken i C#, visar den här guiden en komplett, färdig‑att‑köra lösning. Oavsett om du kodar accentuerade bokstäver som **Å** eller symboler som **©**, låter stegen nedan dig skapa en MacroPdf417‑streckkod som bevarar varje tecken exakt som du skrev det.

Du kommer att lära dig hur du genererar barcode c# med Aspose.BarCode‑biblioteket, konfigurerar MacroPdf417‑specifik metadata och sparar resultatet som en PNG‑bild. Inga externa verktyg krävs—bara en .NET‑utvecklingsmiljö och Aspose.BarCode‑NuGet‑paketet.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare installerat  
* Visual Studio 2022 (eller någon IDE som stödjer C#)  
* Aspose.BarCode för .NET tillagt i ditt projekt (`dotnet add package Aspose.BarCode`)  

Dessa krav säkerställer att koden kompileras utan ytterligare beroenden.

## Generera en streckkod med specialtecken i C#

Kärnan i lösningen är att skapa en `BarcodeGenerator`‑instans som använder formatet `EncodeTypes.MacroPdf417`. Generatorn accepterar vilken Unicode‑sträng som helst, så du kan bädda in specialtecken direkt.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for MacroPdf417 with special characters
        using (BarcodeGenerator barcodeGenerator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // Step 2: Set basic barcode appearance
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Step 3: Configure MacroPdf417 specific metadata
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 checksum
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Step 4: Save the generated barcode as a PNG image
            barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Barcode with special characters generated successfully.");
    }
}
```

### Varför detta fungerar

* **Unicode‑stöd** – `BarcodeGenerator` accepterar en `string` som innehåller vilket Unicode‑tecken som helst, så tecken som **Å**, **ó** och **©** kodas utan extra steg.  
* **MacroPdf417** – Detta format låter dig bifoga metadata på filnivå (fil‑ID, segment‑ID, kontrollsumma osv.) som många företags‑scanningssystem förväntar sig.  
* **Pixel‑nivå‑kontroll** – Att sätta `XDimension.Pixels` styr modulbredden, vilket påverkar läsbarheten på lågrelösningsskrivare.  

## Ställ in grundläggande streckkodutseende

Justering av `XDimension` och antalet kolumner påverkar både den visuella storleken och mängden data som får plats på en rad. Ett värde på `2` pixlar ger en kompakt men läsbar streckkod, medan `Columns = 5` håller symbolen tillräckligt smal för de flesta etiketter.

### Proffstips

Om du riktar dig mot en högdensitetsetikett‑skrivare, öka `XDimension.Pixels` till `3` eller `4` för att undvika pixel‑nivå‑distortion.

## Konfigurera MacroPdf417‑metadata

MacroPdf417 utökar den standard PDF417‑specifikationen med fält som beskriver hur en flerdelad fil ska rekonstrueras. Egenskaperna du sätter i exemplet motsvarar ett typiskt användningsfall:

| Property | Purpose |
|----------|---------|
| `MacroPdf417FileID` | Unik identifierare för hela filen |
| `MacroPdf417SegmentID` | Index för det aktuella segmentet (börjar på 1) |
| `MacroPdf417SegmentsCount` | Totalt antal segment i filen |
| `MacroPdf417FileName` | Logiskt namn på filen (används av vissa skannrar) |
| `MacroPdf417Checksum` | CCITT‑16‑kontrollsumma för dataintegritet |
| `MacroPdf417FileSize` | Förväntad storlek i byte – hjälper skannrar att validera fullständighet |
| `MacroPdf417TimeStamp` | Skapelsestämpel för revisionsspår |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Valfri routningsinformation |
| `MacroPdf417Terminator` | Anger om detta är det sista segmentet (`Set`) eller ett mellansteg (`Unset`) |

### Hantering av kantfall

* **Stora fil‑ID:n** – `FileID`‑egenskapen accepterar ett 32‑bit heltal. Om ditt system använder GUID:s, hash GUID‑en till ett 32‑bit‑värde innan tilldelning.  
* **Tidsstämpel‑precision** – Egenskapen lagrar ett `DateTime`. Om du behöver subsekundprecision, inkludera den i filnamnet istället, eftersom standarden inte stödjer millisekunder.  

## Spara streckkodsbilden

`Save`‑metoden skriver den renderade streckkoden till filsystemet. Du kan välja andra format (`Jpeg`, `Bmp`, `Svg`) genom att byta `BarCodeImageFormat.Png`. PNG är förlustfri, vilket gör den idealisk för vidare bearbetning eller inbäddning i PDF‑filer.

```csharp
barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
```

Efter att ha kört programmet hittar du `ExtPDF417Meta.png` i utmatningskatalogen. När du öppnar bilden visas en tät, flerradig streckkod som innehåller texten **Åspóse.Barcóde©** tillsammans med den macro‑metadata du konfigurerade.

### Förväntad output

* En PNG‑fil på ungefär 300 × 150 pixlar (storleken varierar med kolumnantalet).  
* När den skannas med en PDF417‑kompatibel läsare visar den avkodade texten exakt **Åspóse.Barcóde©** och skannern kan rekonstruera originalfilen med hjälp av macro‑fälten.

## Så genererar du barcode c# – vanliga fallgropar

Även om koden är enkel, stöter utvecklare ofta på följande problem:

1. **Saknat NuGet‑paket** – Att glömma att installera `Aspose.BarCode` leder till kompileringsfel. Verifiera paketreferensen i din `.csproj`.  
2. **Ogiltiga tecken för den valda symbolen** – Vissa streckkodstyper (t.ex. Code 128) avvisar vissa Unicode‑intervall. MacroPdf417 accepterar hela Unicode‑uppsättningen, vilket gör den till det säkraste valet för specialtecken.  
3. **Felaktig filsökväg** – Att använda en relativ sökväg utan rätt behörigheter kan orsaka ett körnings‑`UnauthorizedAccessException`. Ange en absolut sökväg eller säkerställ att applikationen har skrivbehörighet till målmappen.  

Genom att åtgärda dessa punkter säkerställer du att hur man genererar barcode c# förblir en smidig upplevelse.

## Fullt fungerande exempel

Kopiera hela programmet nedan till ett nytt konsolprojekt och kör det. Ingen ytterligare konfiguration krävs utöver NuGet‑paketet.



## Vad du bör lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Streckkod med specialtecken – Komplett guide för att generera PDF417](/barcode/english/net/compact-pdf417-encoding/barcode-with-special-characters-complete-guide-to-generating/)
- [Hur man genererar streckkodsbild med Aspose.BarCode i C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)
- [Hur man genererar PDF417‑streckkodsbild i C# med Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}