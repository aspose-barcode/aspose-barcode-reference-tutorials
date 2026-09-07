---
category: general
date: 2026-09-07
description: barcodegenerator C#‑tutorial die laat zien hoe je barcode‑PNG‑bestanden
  genereert en DataBar‑barcodes maakt met aanpasbare rijen en kolommen
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- generate barcode PNG
- create DataBar barcode
language: nl
lastmod: 2026-09-07
og_description: 'barcode generator C# tutorial: leer hoe je barcode PNG‑bestanden
  genereert en DataBar‑barcodes maakt met aangepaste rijen en kolommen in slechts
  enkele minuten'
og_image_alt: Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator
  C#
og_title: barcodegenerator C# – maak DataBar-barcodes en PNG-afbeeldingen
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: barcode generator C# tutorial that shows you how to generate barcode
    PNG files and create DataBar barcodes with customizable rows and columns
  headline: How to use a barcode generator C# to create DataBar barcodes
  type: TechArticle
tags:
- barcode
- C#
- DataBar
title: Hoe een barcodegenerator in C# te gebruiken om DataBar-barcodes te maken
url: /nl/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een barcode‑generator C# te gebruiken om DataBar‑barcodes te maken

Als je een **barcode generator C#** nodig hebt voor het maken van barcodes van hoge kwaliteit, laat deze gids je zien hoe je **barcode PNG**‑bestanden kunt **genereren** en **DataBar‑barcodes** kunt maken met aangepaste rijen en kolommen. Of je nu een retail‑inventarisatiesysteem of een ticketingsplatform bouwt, de onderstaande stappen laten je een DataBar Expanded Stacked‑barcode produceren in één zelf‑containend voorbeeld.

In deze tutorial leer je:

* Hoe je de `BarcodeGenerator` instantiate voor de DataBar Expanded Stacked‑symbologie.  
* Hoe je kolom‑ en rij‑instellingen aanpast om te voldoen aan de ISO / GS1‑specificaties.  
* Hoe je de output opslaat als een PNG‑afbeelding die in webpagina’s kan worden ingebed of op etiketten kan worden afgedrukt.  

Er zijn geen externe services nodig—alleen de Aspose.BarCode for .NET‑bibliotheek (of een compatibele bibliotheek die dezelfde API volgt). De code draait op .NET 6+ en werkt in Visual Studio, Rider of elke IDE die C# ondersteunt.

## Vereisten

Voordat je begint, zorg dat je het volgende hebt:

* .NET 6 SDK of later geïnstalleerd.  
* Een referentie naar het `Aspose.BarCode` NuGet‑pakket (of een equivalente bibliotheek die `BarcodeGenerator`, `EncodeTypes` en `BarCodeImageFormat` levert).  
* Basiskennis van C#‑syntaxis en projectstructuur.  

Je kunt het pakket toevoegen via de opdrachtregel:

```bash
dotnet add package Aspose.BarCode
```

## Stap 1: Initialiseert de barcode‑generator C# voor DataBar Expanded Stacked

De eerste stap is het aanmaken van een `BarcodeGenerator`‑instantie die zich richt op de **DataBar Expanded Stacked**‑symbologie. Dit object bevat alle render‑parameters, inclusief de te coderen tekst.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,          // Symbology
    "Databar Expanded Stacked long");            // Data to encode
```

**Waarom dit belangrijk is:** De enum‑waarde `EncodeTypes.DatabarExpandedStacked` vertelt de bibliotheek welke barcode‑standaard moet worden toegepast. Het gebruik van de juiste enum zorgt ervoor dat de gegenereerde afbeelding voldoet aan de GS1 DataBar‑specificaties.

## Stap 2: Configureer het aantal kolommen (standaard rijen worden gebruikt)

DataBar Expanded Stacked kan worden opgesplitst in meerdere kolommen. Het aanpassen van het kolomaantal verandert de visuele dichtheid en kan helpen langere gegevensreeksen in beperkte ruimte te passen.

```csharp
// Step 2: Set the number of columns (default rows are used)
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

**Pro tip:** Het standaard kolomaantal is 1. Instellen op 4 creëert vier gestapelde kolommen, wat ideaal is voor langere numerieke reeksen terwijl de barcode‑hoogte beheersbaar blijft.

## Stap 3: Genereer barcode PNG met de kolominstelling toegepast

Sla nu de barcode op als een PNG‑afbeelding. PNG behoudt de scherpe randen die scanners nodig hebben en werkt goed zowel op web als in printmedia.

```csharp
// Step 3: Save the barcode image with the column setting applied
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

Het bestand `DatabarCols4.png` bevat een **barcode PNG** die je direct in HTML kunt embedden:

```html
<img src="DatabarCols4.png" alt="Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#">
```

## Stap 4: Maak een aparte generator‑instantie voor rij‑configuratie

Als je het aantal rijen in plaats van kolommen wilt regelen, instantiateer je een nieuwe `BarcodeGenerator`. Het hergebruiken van dezelfde instantie na het wijzigen van een dimensie kan onverwachte lay‑out‑artefacten veroorzaken, dus een nieuw object is de veiligste aanpak.

```csharp
// Step 4: Create a new generator instance for the same barcode type
BarcodeGenerator rowBarcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## Stap 5: Stel het aantal rijen in (standaard kolommen worden gebruikt)

Rijen beïnvloeden de verticale stapeling van de barcode‑modules. Het verhogen van het aantal rijen kan de barcode hoger maken, wat nodig kan zijn voor bepaalde etiketgroottes.

```csharp
// Step 5: Set the number of rows (default columns are used)
rowBarcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

**Waarom rijen vs. kolommen:** Kolommen splitsen de barcode horizontaal, terwijl rijen deze verticaal uitbreiden. Kies de oriëntatie die het beste past bij je etiketlay‑out.

## Stap 6: Genereer barcode PNG met de rij‑instelling toegepast

Sla tenslotte de rij‑aangepaste barcode op als een PNG‑bestand.

```csharp
// Step 6: Save the barcode image with the row setting applied
rowBarcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

Je hebt nu twee aparte PNG‑bestanden:

* `DatabarCols4.png` – 4 kolommen, 1 rij.  
* `DatabarRows3.png` – 1 kolom, 3 rijen.

Beide afbeeldingen zijn direct klaar voor gebruik in applicaties, rapporten of afgedrukte etiketten.

## Hoe barcode PNG‑bestanden te genereren in C# met aangepaste afmetingen

Het patroon hierboven kan worden hergebruikt voor elke DataBar‑variant of andere symbologieën die door de bibliotheek worden ondersteund. Hier is een compacte template die je kunt kopiëren‑plakken in een hulpprogrammaklasse:

```csharp
public static void GenerateDatabar(string data, int columns = 1, int rows = 1, string outputPath = "output.png")
{
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, data);
    generator.Parameters.Barcode.DataBar.Columns = columns;
    generator.Parameters.Barcode.DataBar.Rows = rows;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Roep de methode als volgt aan:

```csharp
GenerateDatabar("1234567890123", columns: 4, outputPath: "DatabarCols4.png");
GenerateDatabar("1234567890123", rows: 3, outputPath: "DatabarRows3.png");
```

**Randgevallen om te overwegen**

* **Gegevenslengte** – DataBar Expanded Stacked kan tot 74 numerieke tekens coderen. Het overschrijden van deze limiet veroorzaakt een uitzondering. Valideer de invoerlengte vóór het aanroepen van de generator.  
* **Ongeldige afmetingen** – De bibliotheek beperkt kolommen tot 1‑4 en rijen tot 1‑3 voor deze symbologie. Waarden buiten deze bereiken worden genegeerd of veroorzaken een fout.  
* **Afbeeldings‑DPI** – Als je een hogere resolutie voor afdrukken nodig hebt, stel dan `generator.Parameters.ImageResolution` in vóór het opslaan.

## Verwachte output

Wanneer je `DatabarCols4.png` of `DatabarRows3.png` opent, zie je een duidelijke, hoog‑contrast DataBar‑barcode. Het scannen van de afbeelding met een GS1‑compatibele scanner geeft de oorspronkelijke tekst `"Databar Expanded Stacked long"` terug.

![Voorbeeld DataBar Expanded Stacked barcode opgeslagen als PNG met barcode generator C#](image.png)

*Alt‑tekst: Voorbeeld DataBar Expanded Stacked barcode opgeslagen als PNG met barcode generator C#*

## Conclusie

Deze tutorial heeft laten zien hoe een **barcode generator C#** kan worden gebruikt om **DataBar‑barcodes** te **maken** en **barcode PNG**‑bestanden te **genereren** met aangepaste rij‑ en kolominstellingen. Door de zes stappen te volgen—de generator initialiseren, kolommen of rijen configureren, en opslaan als PNG—verkrijg je productie‑klare afbeeldingen die geschikt zijn voor inventarisatiesystemen, ticketing of elke situatie die betrouwbare barcode‑rendering vereist.

Vervolgens kun je verkennen:

* Het toevoegen van kleur of achtergrondafbeeldingen aan de PNG (nog steeds compatibel met de meeste scanners).  
* Het gebruik van andere symbologieën zoals QR, Code 128 of PDF417 via dezelfde `BarcodeGenerator`‑API.  
* Het direct embedden van de gegenereerde PNG in ASP.NET Core MVC‑views of Blazor‑componenten.

Voel je vrij om te experimenteren met verschillende gegevensreeksen, afmetingen en afbeeldingsformaten (bijv. JPEG, BMP). Hetzelfde patroon geldt, waardoor de **barcode generator C#** een veelzijdig hulpmiddel is in de toolbox van elke .NET‑ontwikkelaar. Veel plezier met coderen!


## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids zijn gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Generate barcode C# – Create DataBar barcode](/barcode/english/python-java/general/generate-barcode-c-create-databar-barcode/)
- [Barcode Generator Example – Build DataBar Image in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}