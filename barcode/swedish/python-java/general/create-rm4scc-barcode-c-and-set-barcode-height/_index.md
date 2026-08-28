---
category: general
date: 2026-08-25
description: Skapa RM4SCC‑streckkod i C# med steg‑för‑steg‑kod och lär dig hur du
  ställer in streckkodens höjd för exakt dimensionering.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create rm4scc barcode c#
- how to set barcode height
language: sv
lastmod: 2026-08-25
og_description: Skapa RM4SCC-streckkod i C# med Aspose.BarCode och lär dig hur du
  ställer in streckkodens höjd för exakt kontroll i dina .NET-applikationer.
og_image_alt: Screenshot of an RM4SCC barcode generated with C#
og_title: Skapa RM4SCC-streckkod i C# – guide för att ställa in streckkodens höjd
schemas:
- author: Aspose
  dateModified: '2026-08-25'
  description: Create RM4SCC barcode C# with step‑by‑step code and learn how to set
    barcode height for precise sizing.
  headline: Create RM4SCC barcode C# and set barcode height
  type: TechArticle
tags:
- barcode
- C#
- RM4SCC
- Aspose.BarCode
title: Skapa RM4SCC‑streckkod i C# och ange streckkodshöjd
url: /sv/python-java/general/create-rm4scc-barcode-c-and-set-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa RM4SCC streckkod C# och ange streckkodshöjd

Skapa RM4SCC streckkod C# snabbt med Aspose.BarCode-biblioteket. Denna handledning visar **hur man anger streckkodshöjd** och anpassar andra visuella egenskaper så att streckkoden passar exakt i din layout.

Du kommer att se ett komplett, färdigt‑att‑köra konsolprogram som genererar tre PNG‑filer:

* en Planet‑streckkod med standardhöjd (för jämförelse)  
* en RM4SCC‑streckkod med manuell höjd på 100 px  
* en Planet‑streckkod med tomma (oifyllda) staplar  

Exemplet förutsätter att du har Visual Studio 2022 (eller någon .NET 6+ IDE) och en giltig Aspose.BarCode för .NET‑licens eller utvärderingskopi.

## Förutsättningar

| Krav | Orsak |
|------|-------|
| .NET 6 SDK (eller senare) | Tillhandahåller runtime för konsolappen |
| Aspose.BarCode för .NET NuGet‑paket | Tillhandahåller `BarcodeGenerator`, `EncodeTypes` och API:er för bildexport |
| Grundläggande C#‑kunskaper | Behövs för att förstå kodflödet |

Installera NuGet‑paketet med:

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Om du kör koden utan licens kommer de genererade bilderna att innehålla ett litet Aspose‑vattenstämpel.

## Steg 1: Ställ in projektstrukturen

Skapa ett nytt konsolprojekt och lägg till de nödvändiga `using`‑direktiven:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat; // optional, you can use the enum directly
```

`using`‑satserna ger dig åtkomst till klasserna för streckkodsgeneratorn och PNG‑format‑enumen.

## Steg 2: Definiera utdatamappen

Välj en mapp där PNG‑filerna ska sparas. Mappen måste finnas innan du anropar `Save`.

```csharp
// Step 1: Define the output folder
string outputFolder = "GeneratedBarcodes/";

// Ensure the directory exists
System.IO.Directory.CreateDirectory(outputFolder);
```

Att skapa katalogen programatiskt undviker ett *FileNotFoundException* när koden körs på en ny maskin.

## Steg 3: Generera en Planet‑streckkod med standardhöjd (baslinje)

Planet‑streckkoden är inte huvudfokus i den här guiden, men den ger en visuell baslinje för jämförelse med den manuellt dimensionerade RM4SCC‑streckkoden.

```csharp
// Step 2: Generate a Planet barcode with the default (auto) height
BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // controls bar width
planetAuto.Save($"{outputFolder}PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*Varför detta är viktigt:*  
`XDimension` bestämmer bredden på en enskild stapel. Genom att hålla den konstant medan `BarHeight` ändras isoleras höjdens effekt.

## Steg 4: **Skapa RM4SCC streckkod C#** – ange en manuell höjd

Nu tar vi itu med huvuduppgiften: **skapa RM4SCC streckkod C#** och explicit kontrollera dess höjd.

```csharp
// Step 3: Generate an RM4SCC barcode with a manual height of 100 px
BarcodeGenerator rm4sccManual = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccManual.Parameters.Barcode.XDimension.Pixels = 4;           // same bar width as Planet example
rm4sccManual.Parameters.Barcode.BarHeight.Pixels = 100;          // <-- how to set barcode height
rm4sccManual.Save($"{outputFolder}PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

### Så här anger du streckkodshöjd

`BarHeight`‑egenskapen finns under `Parameters.Barcode`. Den accepterar ett `float`‑värde uttryckt i **pixlar**, **punkter** eller **millimeter** beroende på vilken `Unit` du väljer (`Pixels`, `Points`, `Millimeters`). I exemplet använder vi `Pixels` eftersom utdataformatet är PNG.

Om du behöver en höjd i millimeter, byt enhet först:

```csharp
rm4sccManual.Parameters.Barcode.BarHeight.Unit = BarHeightUnit.Millimeters;
rm4sccManual.Parameters.Barcode.BarHeight.Value = 25; // 25 mm tall
```

## Steg 5: Generera en Planet‑streckkod med tomma (oifyllda) staplar

Detta steg demonstrerar en annan användbar egenskap—`FilledBars`. Att sätta den till `false` skapar en “hålig” streckkod, vilket kan vara praktiskt för designändamål.

```csharp
// Step 4: Generate a Planet barcode with empty (unfilled) bars
BarcodeGenerator planetEmptyBars = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetEmptyBars.Parameters.Barcode.XDimension.Pixels = 4;
planetEmptyBars.Parameters.Barcode.FilledBars = false; // makes bars transparent
planetEmptyBars.Save($"{outputFolder}PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

## Fullt, körbart program

Kopiera följande kod till `Program.cs`. Bygg och kör projektet; tre PNG‑filer kommer att dyka upp i mappen `GeneratedBarcodes`.



## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar code128 streckkod Java och anger stapelhöjd](/barcode/english/java/barcode-configuration/setting-bars-height/)
- [Hur man skapar tyst zon för streckkod .NET för Code 16K med Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Hur man skapar Aztec‑streckkod med Aspose.BarCode för .NET](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}