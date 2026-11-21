---
category: general
date: 2026-11-20
description: Skapa poststreckkodsbild i C# snabbt. Lär dig hur du genererar planet‑streckkod
  och RM4SCC‑streckkoder med anpassningsbara streckstilar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- postal barcode C#
- Aspose.BarCode example
- barcode image generation
language: sv
lastmod: 2026-11-20
og_description: Skapa poststreckkodbild i C# med Aspose.BarCode. Denna handledning
  visar hur du genererar planet‑streckkod, anpassar stapelstilar och producerar RM4SCC‑bilder.
og_image_alt: Create postal barcode image example showing filled and empty bars
og_title: Skapa poststreckkodbild i C# – steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create postal barcode image in C# quickly. Learn how to generate planet
    barcode and RM4SCC barcodes with customizable bar styles.
  headline: Create postal barcode image and generate planet barcode
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Skapa poststreckkodsbild och generera planetstreckkod
url: /sv/python-java/general/create-postal-barcode-image-and-generate-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa poststreckkodbild och generera planet‑streckkod

Skapa en poststreckkodbild i C# med hjälp av Aspose.BarCode-biblioteket. Om du behöver generera planet‑streckkod eller RM4SCC‑streckkoder för postapplikationer, ger den här handledningen en komplett, färdig‑att‑köra lösning.

Att generera streckkoder för posttjänster kräver ofta exakta dimensioner och möjligheten att växla mellan fyllda och tomma stapelstilar. Denna guide visar hur du ställer in utdata‑mappen, skapar både fyllda och tomma Planet‑streckkoder samt producerar en RM4SCC‑streckkod med samma visuella inställningar. I slutet har du fyra PNG‑filer som du kan använda direkt i ditt postflöde.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 eller senare installerat  
* Visual Studio 2022 (eller någon C#‑IDE du föredrar)  
* **Aspose.BarCode** NuGet‑paketet (`Install-Package Aspose.BarCode`)  

Ingen ytterligare konfiguration krävs; koden använder endast standardtypsnittet och PNG‑kodaren.

## Skapa poststreckkodbild – översikt

Kärnan i processen är klassen `BarcodeGenerator`. Den accepterar ett `EncodeTypes`‑värde som bestämmer streckkodssymbologin (t.ex. `EncodeTypes.Planet` för en Planet‑streckkod). Efter att generatorn har konfigurerats anropar du `Save` för att skriva bildfilen.

![Exempel på poststreckkodbild](/images/postal_barcode_example.png)

*Alt text: Exempel på poststreckkodbild som visar fyllda och tomma staplar.*

## Steg 1: Ställ in utdata‑mappen

Definiera först en mapp där PNG‑filerna ska sparas. Att använda en absolut eller relativ sökväg fungerar på samma sätt; se bara till att mappen finns eller låt koden skapa den.

```csharp
using System.IO;
using Aspose.BarCode.Generation;

// Define the output folder (change to your own path)
string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

Att skapa mappen programatiskt förhindrar `DirectoryNotFoundException` när handledningen körs på en ny maskin.

## Steg 2: Generera planet‑streckkod med fyllda staplar

En fylld‑stapels Planet‑streckkod är standardvisuell stil. Följande kod skapar streckkoden, sätter X‑dimensionen till 4 pixlar (en vanlig storlek för postapplikationer) och sparar bilden.

```csharp
// Step 2: Generate a Planet barcode with filled bars
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG
string planetFilledPath = Path.Combine(outputFolder, "PostalPlanetFilledBars.png");
planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
```

**Varför detta fungerar:**  
* `EncodeTypes.Planet` talar om för generatorn att använda Planet‑symbologin, vilket krävs för många posttjänster.  
* `XDimension.Pixels` styr bredden på varje stapel; 4 px ger en klar, läsbar bild utan onödig filstorlek.  
* Metoden `Save` väljer automatiskt PNG‑kodaren baserat på `BarCodeImageFormat`‑enum.

## Steg 3: Generera planet‑streckkod med tomma staplar

Vissa postspecifikationer föredrar tomma (vita) staplar på en mörk bakgrund. Detta kan uppnås genom att sätta `FilledBars` till `false`.

```csharp
// Step 3: Generate a Planet barcode with empty bars
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for consistency
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars – the bars become transparent (empty)
planetEmpty.Parameters.Barcode.FilledBars = false;

// Save the result
string planetEmptyPath = Path.Combine(outputFolder, "PostalPlanetEmptyBars.png");
planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
```

**Tips:** När `FilledBars` är `false` målar generatorn staplarna i bakgrundsfärgen (vit som standard) och mellanrummen i förgrundsfärgen (svart). Om du behöver ett annat färgschema, justera `Parameters.Barcode.ForeColor` och `BackColor`.

## Steg 4: Generera RM4SCC‑streckkod med fyllda staplar

RM4SCC är en annan postsymbologi som används i Storbritannien. Skapandet följer samma steg som Planet‑exemplet; endast `EncodeTypes`‑värdet ändras.

```csharp
// Step 4: Generate an RM4SCC barcode with filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Reuse the same X‑dimension for a uniform look
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save the PNG file
string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png");
rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
```

**Vad du kan förvänta dig:** Den resulterande PNG‑filen visar en kompakt RM4SCC‑streckkod som följer brittiska postriktlinjer. Bildstorleken blir liknande Planet‑streckkoderna eftersom X‑dimensionen är identisk.

## Steg 5: Verifiera de genererade bilderna

Efter att programmet har körts, öppna de fyra filerna i `Barcodes`‑mappen. Du bör se:

* `PostalPlanetFilledBars.png` – mörka staplar på en ljus bakgrund  
* `PostalPlanetEmptyBars.png` – ljusa staplar på en mörk bakgrund (inverterad)  
* `PostalRM4SCCFilledBars.png` – standard RM4SCC‑mönster  

Om någon bild ser förvrängd ut, kontrollera följande:

* **X‑dimension** – för liten (< 2 px) kan orsaka suddighet; för stor (> 10 px) kan överskrida etikettstorleksgränser.  
* **Datat sträng** – värdet `"123456"` måste uppfylla längdkraven för den valda symbologin (Planet förväntar 6 siffror, RM4SCC förväntar också 6 siffror).  
* **Mappbehörigheter** – säkerställ att applikationen har skrivbehörighet till utdata‑katalogen.

## Vanliga variationer och kantfall

| Scenario | Justering |
|----------|------------|
| **Olika streckkodsdata** | Ersätt `"123456"` med någon giltig numerisk sträng. För Planet måste längden vara exakt 6 siffror; RM4SCC kräver också 6 siffror. |
| **Anpassade färger** | Sätt `planetFilled.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;` och `BackColor = System.Drawing.Color.LightYellow;`. |
| **Högre upplösning** | Öka `XDimension.Pixels` till 6 eller 8 för större utskrifter. |
| **Andra bildformat** | Använd `BarCodeImageFormat.Jpeg` eller `BarCodeImageFormat.Bmp` i `Save`‑anropet. |
| **Batch‑generering** | Loopa över en samling strängar och anropa samma generatorlogik inuti loopen, återanvänd `outputFolder`‑sökvägen. |

## Fullt, körbart exempel

Kopiera koden nedan till ett nytt C#‑konsolprojekt. Den kompileras med .NET 6.0 och producerar automatiskt alla fyra streckkods‑bilder.



## Vad bör du lära dig härnäst?

De följande handledningarna täcker närliggande ämnen som bygger på teknikerna som demonstreras i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Hur man skapar poststreckkodbild med anpassade höjder i C#](/barcode/english/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/)
- [Hur man skapar RM4SCC‑streckkod och genererar planet‑streckkod i C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [Skapa poststreckkodbild i C# – steg‑för‑steg‑guide](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}