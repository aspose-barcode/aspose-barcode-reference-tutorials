---
category: general
date: 2026-10-08
description: Skapa en tom planetstreckkod med C# och lär dig hur du genererar poststreckkod
  med Aspose.BarCode. Steg‑för‑steg‑kod och tips ingår.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create empty planet barcode
- how to generate postal barcode
- Aspose.BarCode C#
- postal barcode example
- barcode XDimension setting
language: sv
lastmod: 2026-10-08
og_description: Skapa en tom planetstreckkod med Aspose.BarCode i C# och se hur du
  kan generera poststreckkods‑bilder för postapplikationer.
og_image_alt: Screenshot of generated empty Planet barcode and filled RM4SCC barcode
og_title: Skapa tom planetstreckkod – C#‑guide för poststreckkod
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Create empty planet barcode with C# and learn how to generate postal
    barcode using Aspose.BarCode. Step‑by‑step code and tips included.
  headline: Create empty planet barcode, generate postal barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- postal
title: Skapa tom planetstreckkod, generera poststreckkod i C#
url: /sv/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa tom planet‑streckkod, generera poststreckkod i C#

Om du behöver **create empty planet barcode** för ett postningssystem, visar den här guiden exakt hur du gör det med Aspose.BarCode för .NET. Du kommer också att lära dig **how to generate postal barcode** bilder såsom Planet och RM4SCC, anpassa stapelbredd och kontrollera alternativet för fyllda‑staplar.

Att generera poststreckkoder kräver inte ett separat grafikbibliotek. Aspose.BarCode SDK tillhandahåller ett enda API som hanterar kodning, bildrendering och val av bildformat. I slutet av den här tutorialen kommer du att ha tre färdiga PNG‑filer:

* `PostalPlanetEmptyBars.png` – en Planet‑streckkod med tomma staplar  
* `PostalPlanetFilledBars.png` – standard Planet‑streckkod med fyllda staplar  
* `PostalRM4SCCFilledBars.png` – en RM4SCC‑streckkod med fyllda staplar  

Du kan placera dessa filer i någon postetikettmall, skriva ut dem på kuvert eller skicka dem till en tredjepartstjänst.

## Förutsättningar

* .NET 6.0 eller senare (koden fungerar även med .NET Framework 4.7+).  
* Visual Studio 2022 eller någon C#‑IDE.  
* Aspose.BarCode for .NET – install via NuGet:

```bash
dotnet add package Aspose.BarCode
```

Inga ytterligare beroenden krävs.

## Skapa tom planet‑streckkod med Aspose.BarCode

Planet‑symboliken är en del av United States Postal Service (USPS)‑streckkodsfamiljen. Som standard ritar SDK **filled** staplar. För att **create empty planet barcode** inaktiverar du flaggan `FilledBars`.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1 – instantiate a Planet barcode generator with the data to encode.
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Step 2 – set the width of a single bar. XDimension defines the pixel size of one bar.
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Step 3 – disable the FilledBars option to get empty (hollow) bars.
planetEmpty.Parameters.Barcode.FilledBars = false;

// Step 4 – save the image. The PNG format is widely supported by printers and browsers.
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Varför detta fungerar:**  
`EncodeTypes.Planet` talar om för generatorn att använda Planet‑symboliken. `XDimension.Pixels` styr den fysiska bredden på varje stapel, vilket är avgörande för postskannrar som förväntar sig en specifik modulstorlek. Att sätta `FilledBars` till `false` får renderaren att bara rita konturen av varje stapel, vilket ger det *tomma* utseendet som krävs av vissa poststandarder.

### Förväntat resultat

Du hittar `PostalPlanetEmptyBars.png` i målmappen. Bilden visar en Planet‑streckkod där varje stapel är en kontur snarare än en solid rektangel.

![Exempel på tom planet‑streckkod](empty-planet.png){: .align-center alt="Skapa tom planet‑streckkod – exempel på en tom‑staplar Planet‑streckkod"}

## Hur man genererar poststreckkodsbilder (fylld version)

De flesta postarbetsflöden använder standardversionen med fyllda staplar. Samma API kan generera en fylld Planet‑streckkod och en RM4SCC‑streckkod med bara några rader kod.

```csharp
// Filled Planet barcode (default behavior)
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// RM4SCC barcode – another USPS format that always uses filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
```

**Varför du kan behöva RM4SCC:**  
RM4SCC är den nyare USPS‑streckkoden som kodar samma data som Planet men med högre densitet. Vissa transportörer kräver RM4SCC för rabatter vid massutskick. Koden ovan demonstrerar hur man **how to generate postal barcode** för båda standarderna utan att ändra hela arbetsflödet.

### Förväntat resultat

* `PostalPlanetFilledBars.png` – en klassisk Planet‑streckkod med fyllda staplar.  
* `PostalRM4SCCFilledBars.png` – en RM4SCC‑streckkod med fyllda staplar, visuellt liknande men med tätare avstånd.

Båda filerna kan öppnas i någon bildvisare för att verifiera stapelmönstren.

## Justera stapelbredd för olika utskriftsupplösningar

Postskannrar anger ofta en minsta modulbredd (t.ex. 0.013 tum). Om din skrivare arbetar på 300 dpi motsvarar en 4‑pixel modul 0.013 tum. Justera `XDimension.Pixels`‑värdet för att matcha din hårdvara:

| Önskad modul (tum) | DPI | Pixlar behövs (`XDimension`) |
|--------------------------|-----|------------------------------|
| 0.013                    | 300 | 4                            |
| 0.013                    | 600 | 8                            |
| 0.015                    | 300 | 5                            |

**Proffstips:** Alltid testa en

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar planet‑streckkod PNG med C# – steg‑för‑steg‑guide](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/)
- [Generera poststreckkod i C# – komplett guide med Planet‑streckkod](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)
- [Hur man genererar poststreckkod i C# med Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}