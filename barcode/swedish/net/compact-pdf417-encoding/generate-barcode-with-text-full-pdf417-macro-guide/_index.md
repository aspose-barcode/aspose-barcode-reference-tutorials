---
category: general
date: 2026-07-18
description: Generera streckkod med text med Aspose.BarCode för .NET. Lär dig hur
  du genererar PDF417‑streckkoder, ställer in makroalternativ och exporterar PNG‑bilder.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode with text
- how to generate pdf417
language: sv
lastmod: 2026-07-18
og_description: Generera streckkod med text i C# snabbt. Denna steg‑för‑steg‑handledning
  visar hur man genererar PDF417‑streckkoder, konfigurerar makroinställningar och
  sparar som PNG.
og_image_alt: Screenshot of a generated barcode with text using Aspose.BarCode
og_title: Generera streckkod med text – Master PDF417 Makro Skapande
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate barcode with text using Aspose.BarCode for .NET. Learn how
    to generate PDF417 barcodes, set macro options, and export PNG images.
  headline: Generate barcode with text – Full PDF417 Macro Guide
  type: TechArticle
tags:
- barcode generation
- PDF417
- Aspose.BarCode
title: Generera streckkod med text – Fullständig PDF417 Macro-guide
url: /sv/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera streckkod med text – Fullständig PDF417 Macro-guide

Har du någonsin undrat **hur man genererar PDF417**-streckkoder som också inbäddar anpassad text? I den här handledningen kommer du att se exakt hur du **genererar streckkod med text** med Aspose.BarCode för .NET, och vi går igenom alla inställningar du behöver för en Macro PDF417-symbol. Inga onödigheter, bara ett komplett, körbart exempel som du kan lägga in i ditt projekt idag.

Vi kommer att gå igenom:

* Det nödvändiga NuGet‑paketet och using‑direktiven.  
* Hur man skapar en streckkodsgenerator som inkluderar Unicode‑tecken.  
* Inställning av modulstorlek, kolumnantal och macro‑specifika ID:n.  
* Spara resultatet som en PNG‑fil och verifiera utdata.  

Genom att följa guiden får du en färdig‑att‑använda PNG‑bild av en Macro PDF417‑streckkod som du kan bädda in i fakturor, biljetter eller vilket dokument som helst som behöver ett maskinläsbart segment.

---

## Förutsättningar

Innan vi dyker ner, se till att du har:

| Krav | Orsak |
|------|-------|
| **.NET 6.0** or later | Aspose.BarCode stödjer .NET Standard 2.0+, så .NET 6 ger dig den senaste runtime‑miljön. |
| **Visual Studio 2022** (or any C# IDE) | För enkel redigering och felsökning. |
| **Aspose.BarCode for .NET** NuGet package | Biblioteket som faktiskt skapar streckkoden. Installera det med `dotnet add package Aspose.BarCode`. |
| **Write permission** to the output folder | `Save`‑metoden måste skriva PNG‑filen. |

Om någon av dessa är okänd, pausa och fixa dem – annars kommer koden att kasta uppenbara undantag.

---

## Steg 1 – Installera och importera biblioteket

Först, lägg till NuGet‑paketet i ditt projekt:

```bash
dotnet add package Aspose.BarCode
```

Sedan, importera de nödvändiga namnutrymmena:

```csharp
using Aspose.BarCode.Generation;   // Core generation classes
using Aspose.BarCode;               // General utilities (optional)
```

> **Proffstips:** Om du använder Visual Studio, högerklicka på projektet → *Manage NuGet Packages* → sök efter *Aspose.BarCode* och installera den senaste stabila versionen.

---

## Steg 2 – Skapa streckkodsgeneratorn med din anpassade text

Den *primära* uppgiften är att **generera streckkod med text** som innehåller specialtecken som “Å” och “©”. Konstruktorn tar kodningstypen och den råa datatexten:

```csharp
// Step 2: Initialise a Macro PDF417 generator with Unicode text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417,            // Macro PDF417 type
    "Åspóse.Barcóde©");                 // Text to encode (Unicode supported)
```

Varför detta är viktigt: `EncodeTypes.MacroPdf417` talar om för Aspose att vi vill ha macro‑versionen, vilket låter oss dela upp ett stort meddelande över flera symboler. Textsträngen kan vara vilken UTF‑8‑sekvens som helst; Aspose hanterar konverteringen internt.

---

## Steg 3 – Justera grundläggande utseende (modulstorlek)

En streckkods “modul” är den minsta svarta‑eller‑vita fyrkanten. Att sätta dess pixelförstorning styr bildens totala dimensioner utan att ändra datadensiteten:

```csharp
// Step 3: Set module (X‑dimension) size to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Om du behöver en större bild för utskrift, öka värdet till 4 eller 6. Kom bara ihåg att större moduler ökar den slutliga PNG‑filens storlek.

---

## Steg 4 – Konfigurera Macro PDF417‑specifika alternativ

Macro PDF417 lägger till två identifierare som låter en scanner sätta ihop flera symboler. Du kommer vanligtvis att ställa in:

| Egenskap | Vad den gör |
|----------|--------------|
| `Columns` | Antal datakolumner per symbol (påverkar bredden). |
| `MacroPdf417FileID` | Unikt ID för hela macro‑filen (måste vara ≤ 2³¹‑1). |
| `MacroPdf417SegmentID` | Index för det aktuella segmentet (0‑254). |

Här är koden:

```csharp
// Step 4: Define macro‑specific settings
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;                     // Narrower barcode
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Consistent across all segments
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // This is segment #12
```

**Edge‑case note:** `MacroPdf417FileID` måste vara samma för varje segment i samma logiska fil. Om du genererar flera segment, återanvänd samma ID eller så får du orelaterade symboler som inte kan kombineras.

---

## Steg 5 – Spara streckkoden som en PNG‑bild

Nu när allt är konfigurerat, skriv bilden till disk:

```csharp
// Step 5: Export the barcode to PNG
string outputPath = @"C:\Barcodes\MacroPdf417Main.png";
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
```

`Save`‑metoden skapar automatiskt PNG‑filen och hanterar DPI samt färgdjup åt dig. Efter körning, öppna filen för att se något liknande detta:

![Exempel på generera streckkod med text](/images/barcode-example.png){.center alt="Exempel på generera streckkod med text"}

Om du inte ser någon streckkod, dubbelkolla att mappen finns och att din applikation har skrivrättigheter.

---

## Fullt, körklart exempel

Kopiera hela kodsnutten nedan till en ny konsolapp (`dotnet new console`) och kör den. Den kommer att skapa PNG‑filen i mappen `C:\Barcodes` (skapa mappen först).

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise generator with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MacroPdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size (pixel density)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Macro‑PDF417 specific settings
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
        generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

        // 4️⃣ Export to PNG
        string path = @"C:\Barcodes\MacroPdf417Main.png";
        generator.Save(path, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {path}");
    }
}
```

**Förväntad output** (konsol):

```
Barcode saved to C:\Barcodes\MacroPdf417Main.png
```

Och PNG‑filen kommer att visa en kompakt Macro PDF417‑symbol som innehåller texten “Åspóse.Barcóde©”.

---

## Vanliga frågor & fallgropar

| Fråga | Svar |
|-------|------|
| *Kan jag använda ett annat bildformat?* | Absolut—byt ut `BarCodeImageFormat.Png` mot `Jpeg`, `Bmp` eller `Gif`. PNG är förlustfritt, vilket är anledningen till att vi använder det som standard. |
| *Vad händer om jag behöver mer än ett segment?* | Skapa en ny `BarcodeGenerator` för varje segment, håll `MacroPdf417FileID` identisk och öka `MacroPdf417SegmentID` (0‑254). |
| *Min text innehåller emojis—kommer de att fungera?* | Aspose.BarCode stödjer UTF‑8, så de flesta emojis fungerar. Se bara till att den avsedda skannern kan avkoda dem; många industriella skannrar hanterar bara alfanumerisk data. |
| *Streckkoden är för bred för min etikett.* | Minska `Columns` eller öka modulstorleken. Färre kolumner ger en smalare symbol, men kan kräva en skrivare med högre DPI. |
| *Behöver jag en licens?* | En gratis utvärderingslicens fungerar för testning, men den lägger till ett litet vattenmärke. För produktion, köp en licens för att ta bort vattenmärket och låsa upp alla funktioner. |

---

## Nästa steg

Nu när du vet **hur man genererar PDF417**-streckkoder med anpassad text, kanske du vill:

* **Dekoda** streckkoden i en mobilapp med Aspose.BarCode:s `BarCodeReader`.  
* **Kombinera** flera macro‑segment till ett enda PDF‑dokument för batch‑utskrift.  
* **Utforska andra symbologier** (QR, DataMatrix) med liknande parameter‑mönster.  
* **Justera felkorrigeringsnivå** via `Pdf417.ErrorCorrectionLevel` för tuffare miljöer.  

Varje ämne bygger på samma grundkoncept du just lärt dig, så övergången blir smidig.

---

## Slutsats

Vi har gått igenom en komplett, end‑to‑end‑lösning som låter dig **generera streckkod med text** och, specifikt, **hur man genererar PDF417**‑macrosymboler med Aspose.BarCode för .NET. Genom att sätta X‑dimension, kolumnantal och macro‑ID:n får du full kontroll över storlek, layout och hantering av flera segment. Den resulterande PNG‑filen kan skrivas ut, bäddas in i PDF‑dokument eller skickas till en scanner utan ytterligare konvertering.

Prova, justera parametrarna och låt streckkoden arbeta för ditt affärsfall. Om du stöter på problem är Aspose‑dokumentationen och community‑forumen utmärkta resurser för vidare stöd. Lycka till med kodandet!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna i den här guiden. Varje resurs innehåller kompletta kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Hur man genererar PDF417‑streckkoder – Kompakt PDF417‑kodning](/barcode/english/net/compact-pdf417-encoding/)
- [Hur man genererar DataMatrix‑streckkod med Aspose.BarCode för .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Hur man genererar streckkod – En-dimensionella streckkodstyper](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}