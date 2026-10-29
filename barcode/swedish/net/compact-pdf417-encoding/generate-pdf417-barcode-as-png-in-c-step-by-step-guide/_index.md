---
category: general
date: 2026-10-28
description: Generera PDF417‑streckkod i C# och exportera den som en PNG‑bild. Lär
  dig hur du konfigurerar layout, ställer in kolumner och rader samt sparar filen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- barcode generator PNG
- how to set PDF417
- how to generate PNG barcode
- how to configure PDF417 barcode
language: sv
lastmod: 2026-10-28
og_description: Generera PDF417‑streckkod i C# och spara den som en PNG‑bild. Följ
  den här kompletta guiden för att konfigurera layout, ställa in kolumner och rader
  samt skapa en högkvalitativ streckkodsfil.
og_image_alt: Screenshot of a generated PDF417 barcode saved as a PNG file
og_title: Skapa PDF417‑streckkod som PNG – C#‑handledning
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Generate PDF417 barcode in C# and export it as a PNG image. Learn how
    to configure layout, set columns and rows, and save the file.
  headline: Generate PDF417 barcode as PNG in C# – step‑by‑step guide
  type: TechArticle
tags:
- C#
- PDF417
- barcode
- image generation
title: Generera PDF417-streckkod som PNG i C# – steg‑för‑steg‑guide
url: /sv/net/compact-pdf417-encoding/generate-pdf417-barcode-as-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera PDF417-streckkod som PNG i C# – steg‑för‑steg‑guide

Om du behöver **generera PDF417-streckkod** i en .NET-applikation visar den här guiden exakt hur du skapar streckkoden och sparar den som en PNG‑bild. Du kommer att lära dig hur du konfigurerar streckkodens layout, anger antalet kolumner och rader, och producerar en fil som kan användas i lagerhantering, biljettförsäljning eller mobila skanningsscenarier.

Tutorialen täcker allt från att installera det nödvändiga biblioteket till att hantera kantfall som ogiltiga layoutvärden. Ingen extern dokumentation krävs—kopiera bara koden, kör den, så har du en färdigstreckkodbild.

## Förutsättningar

* .NET 6.0 SDK eller senare installerat  
* En C#‑utvecklingsmiljö (Visual Studio, VS Code eller Rider)  
* Internetåtkomst för att ladda ner **Aspose.BarCode for .NET** NuGet‑paketet (biblioteket som används i exemplen)

Dessa krav säkerställer att koden kompileras och körs utan ytterligare konfiguration.

## Steg 1: Installera streckkodsbiblioteket

Det enklaste sättet att få **barcode generator PNG**‑funktionalitet är att använda det officiella Aspose.BarCode‑paketet. Öppna en terminal i din projektmapp och kör:

```bash
dotnet add package Aspose.BarCode
```

Kommandot lägger till biblioteket och dess beroenden i din projektfil. När installationen lyckas kan du referera till klasserna i dina C#‑källfiler.

## Steg 2: Skapa en PDF417‑streckkodsgenerator

Att skapa streckkodobjektet är grunden för processen. Följande kodsnutt bygger en generator som kodar texten "Sample" med PDF417‑symbologin.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for PDF417
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");
```

*Varför detta steg är viktigt* – `BarcodeGenerator`‑klassen kapslar in alla inställningar som krävs för rendering. Genom att ange `EncodeTypes.Pdf417` talar du om för biblioteket att producera en **PDF417‑streckkod**, vilket är en staplad linjär kod idealisk för att lagra stora mängder data.

## Steg 3: Hur du ställer in PDF417‑kolumner och -rader

En PDF417‑streckkod kan anpassas genom att justera dess matris. De två vanligaste parametrarna är **columns** (horisontella moduler) och **rows** (vertikala moduler). Att styra dessa värden påverkar streckkodens storlek och läsbarhet.

```csharp
        // Step 3: Configure a custom layout – set columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // allowed range: 2‑30
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // allowed range: 1‑90
```

### Hur du konfigurerar PDF417‑streckkod för specifika dimensioner

* Använd värden inom de dokumenterade intervallen; tal utanför intervallet utlöser ett undantag.  
* Ett högre antal kolumner komprimerar streckkoden horisontellt, medan fler rader ökar den vertikala höjden.  
* Justera layouten för att matcha den avsedda utskriftsytan eller skanningsavståndet.

Om du behöver en annan form, ändra siffrorna därefter. Biblioteket beräknar automatiskt om modulstorleken för att hålla streckkoden skannbar.

## Steg 4: Hur du genererar PNG‑streckkod

Att spara streckkoden som en PNG‑fil är en endaste‑rad‑operation när generatorn är fullt konfigurerad. PNG ger förlustfri komprimering, vilket gör den idealisk för skarpa streckkodsbilder.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        generator.Save("CustomLayout.png", BarCodeImageFormat.Png);
    }
}
```

*Varför PNG* – `BarCodeImageFormat.Png`‑enumet talar om för biblioteket att rendera streckkoden med PNG‑formatet. Detta format bevarar skarpa kanter, vilket är avgörande för streckkodsläsare som förlitar sig på högkontrastkanter.

### Förväntad utdata

När programmet körs skapas en fil med namnet **CustomLayout.png** i applikationens arbetskatalog. När du öppnar filen visas en rektangulär PDF417‑streckkod med fyra kolumner och nio rader, som kodar strängen "Sample".

![Generera PDF417-streckkod som PNG](https://example.com/images/pdf417-custom.png "Generera PDF417-streckkod som PNG")

*Bildens alt‑text*: **Generera PDF417-streckkod som PNG** – en streckkodsbild som producerats av tutorial‑koden.

## Steg 5: Verifiera streckkoden och felsök vanliga problem

Efter att bilden har genererats bör du verifiera att en scanner eller ett valideringsverktyg kan läsa den. Här är några snabba kontroller:

| Problem | Orsak | Lösning |
|-------|-------|-----|
| Streckkoden är suddig | Bilden har ändrats storlek efter generering | Behåll original PNG‑storlek; undvik skalning i UI‑kontroller |
| Scannern rapporterar “ogiltig data” | Kolumner/rader utanför intervallet eller data för lång för vald layout | Minska mängden kodad text eller öka rader/kolumner |
| PNG‑filen är tom | `generator.Save`‑sökvägen pekar på en icke‑existerande katalog | Säkerställ att katalogen finns eller använd en absolut sökväg |

**Pro‑tips:** När du behöver en transparent bakgrund (t.ex. överlagra streckkoden på ett UI‑element), sätt `generator.Parameters.Image.TransparentBackground = true;` innan du anropar `Save`.

## Fullt fungerande exempel

Nedan är det kompletta programmet som du kan kopiera, klistra in och köra utan ändringar (förutom eventuell justering av utsökvägen).

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the generator for PDF417 with sample data
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");

        // Configure custom layout – set columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // 2‑30
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // 1‑90

        // Optional: make background transparent
        generator.Parameters.Image.TransparentBackground = true;

        // Save the barcode as a PNG file
        string outputPath = "CustomLayout.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to {outputPath}");
    }
}
```

När programmet körs skrivs ett bekräftelsemeddelande ut och `CustomLayout.png` skapas i samma mapp som den körbara filen.

## Slutsats

Du vet nu hur du **genererar PDF417‑streckkod** i C#, konfigurerar dess layout med specifika kolumner och rader, och exporterar resultatet som en **PNG‑streckkod**‑bild. Stegen omfattade installation av Aspose.BarCode‑biblioteket, initiering av generatorn, tillämpning av anpassade dimensioner, sparande av filen och verifiering av utdata.

Härifrån kan du utforska ytterligare inställningar såsom felkorrigeringsnivå, streckkodsmarginaler eller inbäddning av bilden direkt i en PDF‑rapport. Varje av dessa ämnen bygger på det grundmönster som demonstrerats i denna guide, så du är redo att anpassa lösningen till alla .NET‑streckkodsgenereringsscenarier.

---

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig behärska ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)
- [How to generate PDF417 barcode in C# and set barcode size](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)
- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}