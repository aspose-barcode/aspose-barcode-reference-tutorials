---
category: general
date: 2026-09-16
description: Leer hoe je barcodekolommen instelt in C# met BarcodeGenerator en ook
  barcode‑rijen instelt voor DataBar Expanded Stacked‑barcodes.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- set barcode columns
- set barcode rows
- DataBar Expanded Stacked
- BarcodeGenerator C#
- barcode image format
- configure barcode dimensions
language: nl
lastmod: 2026-09-16
og_description: Stel barcodekolommen in C# snel in. Deze gids laat zien hoe je kolommen,
  rijen en beeldformaat configureert met BarcodeGenerator.
og_image_alt: DataBar Expanded Stacked barcode showing custom columns and rows
og_title: Stel barcodekolommen en -rijen in C# – volledige BarcodeGenerator-gids
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set barcode columns in C# using BarcodeGenerator and also
    set barcode rows for DataBar Expanded Stacked barcodes.
  headline: How to set barcode columns and rows with C# BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Hoe barcodekolommen en -rijen instellen met C# BarcodeGenerator
url: /nl/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe barcodekolommen en -rijen in te stellen met C# BarcodeGenerator

Als je barcodekolommen in een C#‑applicatie moet instellen, laat deze tutorial de exacte stappen zien die nodig zijn. Je ziet hoe je zowel kolommen als rijen voor een DataBar Expanded Stacked‑barcode configureert en vervolgens het resultaat opslaat als een PNG‑afbeelding.

Barcodes programmatically genereren bespaart je handmatig ontwerpproces en garandeert consistentie in rapporten, facturen en productetiketten. Het voorbeeld hieronder behandelt de volledige workflow, van het installeren van de bibliotheek tot het produceren van twee afbeeldingen — een met een aangepast aantal kolommen en een met een aangepast aantal rijen.

## Vereisten

Voordat je begint, zorg dat je het volgende hebt:

* .NET 6.0 of hoger geïnstalleerd.
* Een referentie naar het **Aspose.BarCode for .NET** NuGet‑pakket. Installeer het met:

```bash
dotnet add package Aspose.BarCode
```

* Schrijfrechten in een map waar de gegenereerde PNG‑bestanden worden opgeslagen.

Deze vereisten zorgen ervoor dat de code compileert en draait zonder extra configuratie.

## Hoe barcodekolommen in C# in te stellen

De eerste belangrijke stap is het aanmaken van een `BarcodeGenerator`‑instantie voor de **DataBar Expanded Stacked**‑symbologie en het toewijzen van het gewenste aantal kolommen.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize a DataBar Expanded Stacked barcode generator with the target text.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the number of columns. The DataBar object exposes a Columns property.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image using the PNG format.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**Waarom dit werkt:**  
`EncodeTypes.DatabarExpandedStacked` vertelt de bibliotheek welke symbologie moet worden gerenderd. Het instellen van `Parameters.Barcode.DataBar.Columns` wijzigt de interne module‑lay-out, wat direct invloed heeft op de visuele breedte van de barcode. De `Save`‑methode schrijft de afbeelding naar schijf in het opgegeven `BarCodeImageFormat`.

### Verwacht resultaat
Open `C:\Barcodes\DatabarCols4.png` in een willekeurige afbeeldingsviewer. Je zou een DataBar Expanded Stacked‑barcode moeten zien die breder is dan de standaard, omdat er vier kolommen worden gebruikt.

## Hoe barcode‑rijen in C# in te stellen

Nadat je de kolom‑gebaseerde afbeelding hebt opgeslagen, wil je misschien een barcode die in hoogte varieert door rijen aan te passen. Het proces spiegelt de kolomconfiguratie, maar gebruikt de eigenschap `Rows` in plaats daarvan.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 4️⃣ Re‑initialize the generator for a fresh configuration.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 5️⃣ Set the number of rows. This property controls the vertical module count.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6️⃣ Save the barcode image with the row configuration.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Waarom dit werkt:**  
Het opnieuw initialiseren van de generator zorgt ervoor dat de vorige kolominstelling de rijconfiguratie niet beïnvloedt. Het wijzigen van `Parameters.Barcode.DataBar.Rows` past de hoogte van de barcode aan, waardoor een hogere afbeelding ontstaat wanneer het aantal rijen hoger is dan de standaard.

### Verwacht resultaat
Open `C:\Barcodes\DatabarRows3.png`. De barcode zal hoger verschijnen, passend bij de drie‑rij‑configuratie.

## Volledig end‑to‑end‑voorbeeld

Hieronder staat één enkel programma dat beide afbeeldingen in één uitvoering maakt. Het behouden van de code in één bestand laat zien hoe je kunt schakelen tussen kolom‑ en rij‑configuraties zonder de applicatie opnieuw te starten.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Common text for both barcodes.
        const string barcodeText = "Databar Expanded Stacked long";

        // ---------- Column configuration ----------
        var colGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        colGenerator.Parameters.Barcode.DataBar.Columns = 4;
        colGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Row configuration ----------
        var rowGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;
        rowGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

Het uitvoeren van het programma levert twee PNG‑bestanden op:

* **DatabarCols4.png** – barcode met vier kolommen.  
* **DatabarRows3.png** – barcode met drie rijen.

Beide bestanden gebruiken het **barcode‑afbeeldingsformaat** PNG, dat scherpe randen behoudt en lossless compressie ondersteunt — ideaal voor afdrukken en digitale weergave.

## Veelgestelde vragen en tips

| Vraag | Antwoord |
|----------|--------|
| *Kan ik JPEG in plaats van PNG gebruiken?* | Ja. Vervang `BarCodeImageFormat.Png` door `BarCodeImageFormat.Jpeg`. JPEG is kleiner, maar introduceert compressie‑artefacten die de scannerbetrouwbaarheid kunnen beïnvloeden. |
| *Wat is het maximale aantal kolommen of rijen?* | De bibliotheek valideert de waarden volgens de DataBar‑specificatie. Waarden buiten het toegestane bereik veroorzaken een `ArgumentException`. Raadpleeg de Aspose.BarCode‑documentatie voor de exacte limieten. |
| *Moet ik de `BarcodeGenerator` vrijgeven?* | De klasse implementeert `IDisposable`. Plaats de generator in een `using`‑blok als je veel instanties in een lus maakt, zodat onbeheerste resources tijdig worden vrijgegeven. |
| *Hoe wijzig ik de barcode‑grootte zonder kolommen/rijen aan te passen?* | Gebruik `barcodeGenerator.Parameters.Image.Width` en `Height` om de uitvoerafbeelding te schalen terwijl de module‑lay-out ongewijzigd blijft. |

**Pro tip:** Wanneer je barcodes genereert voor hoge‑resolutie‑afdrukken, vergroot dan de afmetingen van de uitvoerafbeelding (`Width`/`Height`) in plaats van het aantal kolommen of rijen. Deze aanpak behoudt de standaard module‑grootte die door de symbologie is gedefinieerd, terwijl je een scherpere afbeelding krijgt.

## Conclusie

Je weet nu hoe je barcodekolommen en -rijen in C# instelt met de **BarcodeGenerator**‑klasse. De gids besprak het initialiseren van de generator, het configureren van kolom‑ en rij‑aantallen, het opslaan van de barcode in PNG‑formaat, en het omgaan met veelvoorkomende variaties zoals wijziging van het afbeeldingsformaat en resource‑vrijgave.

Ga vervolgens aan de slag met gerelateerde onderwerpen zoals **barcode‑kleuren aanpassen**, **menselijk leesbare tekst toevoegen**, en **barcodes in PDF‑documenten insluiten**. Al deze uitbreidingen bouwen voort op hetzelfde configuratie‑patroon dat hier is gedemonstreerd, zodat je volledig uitgeruste barcode‑oplossingen kunt maken voor elke .NET‑applicatie.

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids zijn getoond. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Barcode Generator-voorbeeld in C# – Kolommen, rijen instellen & afbeelding exporteren](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [databar expanded stacked barcode guide – hoe te genereren en te dimensioneren in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Barcode generator-voorbeeld in C# – breedte en hoogte instellen](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}