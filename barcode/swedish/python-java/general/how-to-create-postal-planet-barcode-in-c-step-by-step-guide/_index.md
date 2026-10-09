---
category: general
date: 2026-09-23
description: Lär dig hur du skapar postal planet‑streckkodsbilder i C# med fyllda
  och tomma staplar. Följ detta kompletta exempel med BarcodeGenerator och X‑dimension‑inställningar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal planet barcode
- Planet barcode generator C#
- barcode X‑dimension pixels
- filled bars vs empty bars
- BarCodeImageFormat PNG
language: sv
lastmod: 2026-09-23
og_description: Skapa postal planet-streckkod i C# med den här detaljerade handledningen.
  Generera både fyllda och tomma stapelstilar med BarcodeGenerator och X‑dimension‑inställningar.
og_image_alt: Screenshot showing a created postal planet barcode with filled bars
og_title: Skapa Postal Planet-streckkod i C# – komplett programmeringsguide
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to create postal planet barcode images in C# with filled
    and empty bars. Follow this complete example using BarcodeGenerator and X‑dimension
    settings.
  headline: How to create postal planet barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: Hur man skapar Postal Planet-streckkod i C# – steg‑för‑steg‑guide
url: /sv/python-java/general/how-to-create-postal-planet-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur du skapar postal planet‑streckkod i C# – steg‑för‑steg‑guide

Om du behöver **skapa postal planet‑streckkod**‑bilder i en .NET‑applikation, visar den här handledningen en färdig‑till‑körning‑lösning. Oavsett om du bygger ett system för postetiketter eller ett verktyg för adressverifiering, kommer du att se exakt hur du genererar både fyllda‑staplar och tomma‑staplar‑varianter med Aspose.Barcode‑klassen `BarcodeGenerator`.

Du kommer att lära dig hur du konfigurerar **Planet‑streckkodsgeneratorn**, ställer in **X‑dimensionen** (bredden på varje stapel) i pixlar och sparar resultatet som en PNG‑fil. Handledningen förklarar också varför du kan välja fyllda staplar kontra tomma staplar och hur du växlar mellan de två med en enda kodrad.

## Vad du behöver

* .NET 6.0 SDK eller senare (koden fungerar även med .NET Core och .NET Framework)
* Visual Studio 2022 (eller någon IDE som stödjer C#)
* Aspose.Barcode för .NET NuGet‑paketet (`Aspose.Barcode`) installerat i ditt projekt
* Skrivbehörighet till en mapp där de genererade PNG‑filerna ska sparas

Dessa förutsättningar säkerställer att exemplet kompileras utan ytterligare konfiguration.

## Steg 1: Ställ in utdatamappen

Det första steget är att definiera var streckkods‑bilderna ska skrivas. Att använda en absolut eller relativ sökväg fungerar; se bara till att mappen finns eller skapa den programatiskt.

```csharp
// Step 1: Define the output folder
string outputFolder = "C:/Barcodes/";

// Ensure the folder exists
if (!Directory.Exists(outputFolder))
{
    Directory.CreateDirectory(outputFolder);
}
```

*Varför detta är viktigt*: Om mappen inte finns, kastar `BarcodeGenerator.Save` ett undantag. Att skapa mappen i förväg gör koden robust för distributionsmiljöer.

## Steg 2: Initiera en Planet‑streckkodsgenerator

**Planet‑streckkodsgeneratorn** (EncodeTypes.Planet) är den specifika symbologin som används av många posttjänster. Du initierar den med den data du vill koda – i detta fall den numeriska strängen `"123456"`.

```csharp
// Step 2: Create a Planet barcode generator with the data "123456"
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*Varför detta är viktigt*: `EncodeTypes.Planet` talar om för Aspose.Barcode att använda Planet‑symbologin, som har ett fast mönster av staplar och mellanslag som är lämpligt för postruttning.

## Steg 3: Konfigurera streckkodens X‑dimension

**Streckkodens X‑dimension** styr bredden på varje enskild stapel. Att sätta den till 4 pixlar ger en tydlig, läsbar streckkod som skrivs ut bra på vanliga etikett‑skrivare.

```csharp
// Step 3: Set the X‑dimension (width of each bar) to 4 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Varför detta är viktigt*: En för liten X‑dimension kan göra streckkoden oläslig, medan ett för stort värde slösar etikettutrymme. Fyra pixlar är en vanlig optimal storlek för 300 dpi‑skrivare.

## Steg 4: Generera en Planet‑streckkod med fyllda staplar

Standardrenderingsläget använder **fyllda staplar** (svarta staplar på vit bakgrund). Spara bilden som PNG för att bevara förlustfri kvalitet.

```csharp
// Step 4: Save the barcode using the default setting (filled bars)
barcodeGenerator.Save($"{outputFolder}PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

**Förväntat resultat**: `PostalPlanetFilledBars.png` visar en klassisk Planet‑streckkod där varje stapel är fylld.  

![Exempel på en skapad postal planet‑streckkod med fyllda staplar](https://example.com/filled-bars.png "Exempel på en skapad postal planet‑streckkod med fyllda staplar")

*Varför detta är viktigt*: Fyllda staplar är industristandardutseendet för de flesta postskannrar. Att använda PNG säkerställer att bilden förblir skarp när den skrivs ut.

## Steg 5: Skapa en andra generator för tomma staplar

För att illustrera jämförelsen **fyllda staplar vs tomma staplar**, skapar vi en annan `BarcodeGenerator`‑instans med samma data. Återanvändning av samma data garanterar att båda bilderna är visuellt jämförbara.

```csharp
// Step 5: Create another Planet barcode generator for the same data
BarcodeGenerator emptyBarGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

## Steg 6: Använd samma X‑dimension och växla till tomma staplar

`FilledBars`‑egenskapen växlar renderingsläget. Att sätta den till `false` producerar **tomma staplar** (vita staplar på svart bakgrund). X‑dimensionen förblir identisk för att hålla storleken konsekvent.

```csharp
// Step 6: Apply the same X‑dimension and configure the barcode to use empty bars
emptyBarGenerator.Parameters.Barcode.XDimension.Pixels = 4;
emptyBarGenerator.Parameters.Barcode.FilledBars = false;
```

*Varför detta är viktigt*: Vissa posttjänster eller anpassade arbetsflöden kräver det omvända färgschemat för bättre kontrast på mörkt material. `FilledBars`‑flaggan ger dig den flexibiliteten med en enda kodrad.

## Steg 7: Generera Planet‑streckkoden med tomma staplar

Spara slutligen tomma‑staplar‑versionen till samma utdatamapp.

```csharp
// Step 7: Save the barcode with empty bars
emptyBarGenerator.Save($"{outputFolder}PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Förväntat resultat**: `PostalPlanetEmptyBars.png` visar samma Planet‑mönster, men staplarna är tomma (vita) medan bakgrunden är svart.

![Exempel på en skapad postal planet‑streckkod med tomma staplar](https://example.com/empty-bars.png "Exempel på en skapad postal planet‑streckkod med tomma staplar")

## Verifiera resultaten

Öppna de två PNG‑filerna i någon bildvisare. Du bör se två visuellt identiska streckkoder, som bara skiljer sig åt i färg‑inversion. För att bekräfta att streckkoderna kan skannas kan du använda en smartphone‑app för streckkodsläsning som stödjer Planet‑symbologin.

Om bilderna ser förvrängda ut, dubbelkolla **X‑dimension**‑värdet och se till att sökvägen till utdatamappen inte innehåller otillåtna tecken.

## Vanliga fallgropar och bästa‑praxis‑tips

| Problem | Varför det händer | Lösning |
|-------|----------------|-----|
| **Mapp ej hittad** | `Save` kastar `DirectoryNotFoundException` när sökvägen saknas. | Skapa mappen med `Directory.CreateDirectory` innan du sparar. |
| **Felaktig streckkodsstorlek** | Att använda en icke‑heltal X‑dimension eller ett värde < 2 pixlar ger oläsliga koder. | Håll X‑dimensionen ≥ 2 pixlar; 4 pixlar fungerar för de flesta skrivare. |
| **Färg‑inversion ej tillämpad** | Glömmer att sätta `FilledBars = false`. | Ange explicit `FilledBars` efter att X‑dimensionen har konfigurerats. |
| **Fel bildformat** | Att spara som JPEG kan introducera komprimeringsartefakter. | Använd `BarCodeImageFormat.Png` för förlustfri output. |

## Utöka exemplet

* **Ändra data** – Ersätt `"123456"` med någon numerisk sträng upp till 12 tecken (Planet stödjer upp till 12 siffror).  
* **Justera bildstorlek** – Ändra `XDimension.Pixels` eller sätt `Height`/`Width` via `barcodeGenerator.Parameters.Image`.  
* **Lägg till en ram** – Använd `barcodeGenerator.Parameters.Barcode.BorderWidth` för att rita en tunn kontur runt streckkoden.  
* **Exportera till andra format** – Ändra `BarCodeImageFormat.Png` till `Jpeg`, `Bmp` eller `Tiff` om ditt arbetsflöde kräver det.  

## Slutsats

Du vet nu hur du **skapar postal planet‑streckkod**‑bilder i C# med Aspose.Barcode `BarcodeGenerator`. Handledningen täckte initiering av **Planet‑streckkodsgeneratorn**, inställning av **streckkodens X‑dimension**, och generering av både **fyllda staplar** och **tomma staplar** PNG‑filer. Med dessa grunder kan du integrera generering av poststreckkoder i vilken .NET‑applikation som helst, anpassa utseendet och säkerställa pålitlig skanning i verkliga postningssystem.

Redo att utforska mer? Prova att generera andra post‑symbologier (t.ex. **Postnet** eller **Intelligent Mail**) eller kombinera streckkoden med en PDF‑etikett med hjälp av Aspose.PDF. Lycka till med kodandet!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Skapa Planet‑streckkodbild i C# – Hur man genererar post‑streckkod](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Barcode‑generator C# – skapa Planet‑streckkod och RM4SCC‑exempel](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [Skapa Planet‑streckkod i C# – Full steg‑för‑steg‑guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}