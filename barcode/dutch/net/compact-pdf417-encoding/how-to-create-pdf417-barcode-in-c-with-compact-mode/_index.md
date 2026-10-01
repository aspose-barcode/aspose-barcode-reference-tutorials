---
category: general
date: 2026-09-10
description: Maak snel een PDF417‑barcode in C#. Leer hoe je compacte modus inschakelt,
  kolommen instelt en een PNG genereert met BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- enable compact mode
- barcode generator C#
- how to generate barcode
- how to set columns
language: nl
lastmod: 2026-09-10
og_description: Maak PDF417‑barcode in C# door compacte modus in te schakelen, kolommen
  in te stellen en op te slaan als PNG. Volg de volledige stap‑voor‑stap‑handleiding.
og_image_alt: Screenshot of a compact PDF417 barcode generated with C#
og_title: PDF417-barcode maken in C# – compacte modus tutorial
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create PDF417 barcode in C# quickly. Learn how to enable compact mode,
    set columns, and generate a PNG with BarcodeGenerator.
  headline: How to create PDF417 barcode in C# with compact mode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Hoe maak je een PDF417‑barcode in C# met compacte modus
url: /nl/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417 barcode te maken in C# met compacte modus

Als je een **PDF417 barcode wilt maken** in een .NET‑applicatie, laat deze gids je precies zien hoe je dat doet. Je ziet hoe je **compacte modus inschakelt**, het aantal kolommen instelt, en het resultaat opslaat als een PNG‑afbeelding met behulp van de BarcodeGenerator C#‑bibliotheek.

Het genereren van een barcode is een veelvoorkomende eis voor voorraadbeheer, ticketsystemen en mobiele scan‑apps. Aan het einde van deze tutorial heb je een zelfstandige, uitvoerbare voorbeeldcode die een compacte PDF417 barcode produceert, klaar voor productie.

## Vereisten

* .NET 6.0 of later geïnstalleerd (de code werkt ook met .NET Framework 4.7+)
* Een recente versie van de **BarcodeGenerator**‑bibliotheek (bijv. Aspose.BarCode voor .NET)
* Een IDE of editor zoals Visual Studio 2022 of VS Code
* Schrijfrechten voor een map waarin de PNG wordt opgeslagen

Er zijn geen extra NuGet‑pakketten nodig naast de barcode‑bibliotheek zelf.

## Stap 1: Maak een PDF417 barcode‑generator

De eerste stap is het instantieren van een `BarcodeGenerator`‑object met de `EncodeTypes.Pdf417`‑enum en de tekst die je wilt coderen. Dit object stuurt het volledige generatieproces aan.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

*Waarom dit belangrijk is*: De waarde `EncodeTypes.Pdf417` vertelt de bibliotheek om de PDF417‑symbologie te gebruiken, terwijl het tweede argument de payload levert. Je kunt `"Compact mode"` vervangen door elke alfanumerieke string die je wilt coderen.

## Stap 2: Stel de X‑dimensie in (modulebreedte)

De X‑dimensie bepaalt de breedte van elk klein vierkant (module) in de barcode. Kleinere waarden geven een compactere afbeelding, wat handig is wanneer de ruimte beperkt is.

```csharp
// Step 2: Set the X dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Een waarde van `2` pixels is een goede balans tussen leesbaarheid en compactheid voor de meeste scherm‑gebaseerde scanners.

## Stap 3: Definieer het aantal kolommen

PDF417 kan gegevens rangschikken in een raster van rijen en kolommen. Het aanpassen van het aantal kolommen verandert de beeldverhouding van de barcode.

```csharp
// Step 3: Define the number of columns for the PDF417 barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

Het instellen van **hoe kolommen in te stellen** op `3` levert een korte, brede barcode op die goed op een label past. Je kunt experimenteren met waarden van `1` tot `30`, afhankelijk van de hoeveelheid data en de doelscanner.

## Stap 4: Schakel compacte modus in

Compacte modus verwijdert onnodige opvulrijen, waardoor de barcode kleiner wordt zonder verlies van gegevensintegriteit. Dit is de cruciale stap voor een **compacte PDF417**.

```csharp
// Step 4: Enable compact mode by truncating the barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

Wanneer `Truncate` `true` is, berekent de bibliotheek automatisch het minimale aantal rijen dat nodig is om de gegevens op te slaan, waardoor de uiteindelijke afbeelding “compact” lijkt.

## Stap 5: Sla de gegenereerde barcode op als een PNG‑afbeelding

Schrijf tenslotte de barcode naar een bestand. PNG behoudt de scherpe randen die nodig zijn voor betrouwbare scanning.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Vervang `YOUR_DIRECTORY` door een absoluut of relatief pad waar je applicatie naar kan schrijven. Na uitvoering vind je een `CompactPdf417.png`‑bestand dat de barcode bevat.

### Volledige broncode

Alle stappen samenvoegen geeft je een enkel, kant‑klaar programma:

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

        // Set the X dimension (module width) in pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the number of columns for the PDF417 barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;

        // Enable compact mode by truncating the barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("CompactPdf417.png", BarCodeImageFormat.Png);

        Console.WriteLine("PDF417 barcode created successfully.");
    }
}
```

Het uitvoeren van dit programma maakt `CompactPdf417.png` aan in dezelfde map als het uitvoerbare bestand. Open de afbeelding met een viewer; je zou een dichte, hoog‑contrast PDF417 barcode moeten zien, klaar om te scannen.

## Hoe compacte modus in andere scenario's in te schakelen

* **Batchgeneratie** – Bij het maken van veel barcodes, stel `Truncate` één keer in op de generator en hergebruik deze voor elke nieuwe payload.
* **Verschillende afbeeldingsformaten** – Dezelfde `Save`‑methode werkt met `BarCodeImageFormat.Jpeg` of `BarCodeImageFormat.Bmp` als je een ander bestandstype nodig hebt.
* **Dynamisch aantal kolommen** – Als de lengte van de gecodeerde string varieert, bereken dan een optimaal aantal kolommen op basis van de stringlengte en de resolutie van de scanner.

## Hoe kolommen in te stellen voor specifieke gebruikssituaties

* **Labelprinten** – Gebruik een laag aantal kolommen (bijv. `2`‑`5`) om de barcode kort genoeg te houden om op smalle labels te passen.
* **Mobiel scannen** – Hogere kolom aantallen (`10`‑`15`) produceren hogere barcodes die makkelijker door telefooncamera's te focussen zijn.
* **Fout‑correctie afweging** – Meer kolommen verminderen het aantal rijen, wat de ingebouwde foutcorrectie van de barcode kan beïnvloeden. Test met je doelscanner om de optimale balans te vinden.

## Veelvoorkomende valkuilen en pro‑tips

| Issue | Why it happens | Fix |
|-------|----------------|-----|
| Barcode is onleesbaar | X‑dimensie te laag (bijv. `1` pixel) | Verhoog `XDimension.Pixels` tot minimaal `2` |
| Afbeelding is te groot | Kolommen te hoog ingesteld voor een korte payload | Verlaag `Pdf417.Columns` of schakel `Truncate` in |
| PNG‑bestand is leeg | Uitvoermap bestaat niet of heeft geen schrijfrechten | Zorg dat de map bestaat en het proces schrijfrechten heeft |
| Scanner meldt “data corrupt” | Truncate uitgeschakeld terwijl er veel kolommen worden gebruikt | Schakel `Truncate` in of verlaag het aantal kolommen |

## Het resultaat verifiëren

Je kunt de barcode verifiëren met elke PDF417‑scanner‑app (er bestaan veel gratis Android/iOS‑apps). Open `CompactPdf417.png` in de app en bevestig dat de gedecodeerde tekst overeenkomt met de oorspronkelijke payload (“Compact mode”). Als de tekst afwijkt, controleer dan opnieuw de `Truncate`‑vlag en kolominstellingen.

## Volgende stappen

* **Integreren met ASP.NET Core** – Retourneer de PNG direct vanuit een controller‑actie in plaats van op schijf op te slaan.
* **Voeg mens‑leesbare tekst toe** – Gebruik `barcodeGenerator.Parameters.Barcode.CodeTextParameters` om de gecodeerde string onder de barcode weer te geven.
* **Verken andere symbologieën** – Dezelfde `BarcodeGenerator`‑klasse ondersteunt QR, Code128, DataMatrix en meer. Wissel `EncodeTypes` om ze uit te proberen.

---

### Conclusie

Je weet nu hoe je een **PDF417 barcode kunt maken** in C# terwijl je **compacte modus inschakelt**, **hoe kolommen in te stellen** beheert, en de **barcode generator C#**‑API gebruikt om een **barcode te genereren** die voldoet aan real‑world grootte‑beperkingen. Pas deze stappen toe in elk .NET‑project dat compacte, hoge‑dichtheid barcodes nodig heeft, en breid het patroon uit naar andere barcode‑formaten indien nodig. Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Maak PDF417 Barcode in C# – Complete Stapsgewijze Gids](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Hoe foutniveau in PDF417 Barcode in te stellen – Complete Gids](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Hoe Barcode op te slaan in C# – PDF417 Barcodes genereren](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}