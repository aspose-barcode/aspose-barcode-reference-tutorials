---
category: general
date: 2026-11-17
description: Maak een barcode‑afbeelding in C# met behulp van de Barcode Generator‑bibliotheek.
  Volg deze gids om stap voor stap te leren hoe je DataBar stacked omnidirectionele
  codes genereert.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to generate databar
language: nl
lastmod: 2026-11-17
og_description: Maak een barcode‑afbeelding in C# met een beknopt voorbeeld. Leer
  hoe je gestapelde omnidirectionele DataBar‑barcodes genereert met de Barcode Generator‑bibliotheek.
og_image_alt: Screenshot showing a generated barcode image created with C# code
og_title: Maak barcode‑afbeelding in C# – volledige gids voor DataBar‑codes
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Create barcode image in C# using the Barcode Generator library. Follow
    this guide to learn how to generate DataBar stacked omnidirectional codes step‑by‑step.
  headline: How to create barcode image in C# with DataBar stacked omnidirectional
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Hoe maak je een barcode‑afbeelding in C# met DataBar stacked omnidirectional
url: /nl/python-java/general/how-to-create-barcode-image-in-c-with-databar-stacked-omnidi/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een barcode‑afbeelding te maken in C# met DataBar gestapeld omnidirectioneel

Als je een **barcode‑afbeelding** moet maken in een .NET‑applicatie, laat deze tutorial je een complete, kant‑klaar oplossing zien. Je ziet precies hoe je de **Barcode Generator C#** API gebruikt om een gestapelde omnidirectionele DataBar te produceren, het formaat dat wordt behandeld in de *how to generate databar* query.

De gids doorloopt elke vereiste stap — van het installeren van de bibliotheek tot het fijn afstellen van de beeldverhouding — zodat je de code kunt kopiëren, uitvoeren en direct een PNG‑bestand krijgt. Het is niet nodig om externe documentatie te raadplegen.

## Vereisten

* .NET 6.0 SDK of later geïnstalleerd (het voorbeeld werkt ook met .NET Framework 4.7+)
* Een ontwikkelomgeving zoals Visual Studio 2022 of VS Code
* Het **Aspose.BarCode for .NET** NuGet‑pakket (de bibliotheek die `BarcodeGenerator` levert)

Je kunt het pakket toevoegen met de volgende opdracht:

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Gebruik de `--version`‑vlag om het pakket vast te zetten op de nieuwste stabiele release, bijv. `dotnet add package Aspose.BarCode --version 23.9`.

## Stap 1: Het project instellen en namespaces importeren

Maak een nieuw console‑project aan en verwijs naar de benodigde namespaces. Deze stap bereidt de omgeving voor de **barcode generator c#**‑code die volgt.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // All barcode generation logic lives here
```

De namespace `Aspose.BarCode.Generation` bevat de klasse `BarcodeGenerator`, die de kern vormt van de **barcode‑afbeelding maken**‑workflow.

## Stap 2: Initialiseer de BarcodeGenerator voor een gestapelde omnidirectionele DataBar

De generator heeft twee gegevens nodig: het type barcode en de te coderen data. De enum‑waarde `EncodeTypes.DatabarStackedOmniDirectional` selecteert de exacte DataBar‑variant die vereist is voor *how to generate databar* scenario's.

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // Example GTIN-14 payload
```

*Waarom dit belangrijk is:* Het selecteren van de juiste `EncodeTypes`‑waarde zorgt ervoor dat de resulterende afbeelding voldoet aan de industriespecificaties voor retail‑scanning.

## Stap 3: Definieer de module‑grootte (X‑dimensie) in pixels

De visuele dichtheid van een barcode wordt geregeld door de X‑dimensie. Het instellen op een redelijk pixel‑waarde garandeert dat de afbeelding zowel op scherm als op papier leesbaar is.

```csharp
            // Step 3: Define the module size (X‑dimension) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Als je een grotere barcode nodig hebt voor low‑resolution afdrukken, verhoog dan de pixel‑waarde dienovereenkomstig.

## Stap 4: Pas de DataBar‑beeldverhouding aan om rijen hoger te maken

De gestapelde omnidirectionele DataBar bestaat uit twee rijen. Het aanpassen van `AspectRatio` stelt je in staat de hoogte van elke rij te regelen, wat handig kan zijn wanneer de standaardgrootte krap lijkt.

```csharp
            // Step 4: Adjust the DataBar aspect ratio to make rows taller
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

Een beeldverhouding van `15` is een veelgebruikte keuze voor retail‑labels; je kunt experimenteren met waarden tussen `10` en `20` om aan specifieke lay‑out eisen te voldoen.

## Stap 5: Sla de gegenereerde barcode op als PNG‑afbeelding

Schrijf tenslotte de afbeelding naar schijf. PNG is verliesvrij, waardoor het ideaal is voor latere verwerking of inbedding in PDF‑bestanden.

```csharp
            // Step 5: Save the generated barcode as a PNG image
            string outputPath = "DatabarAspectRatio15.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to {outputPath}");
        }
    }
}
```

Het uitvoeren van het programma genereert een bestand met de naam **DatabarAspectRatio15.png** in de output‑directory van het project. Het openen van het bestand toont een schone, hoog‑contrast barcode klaar om te scannen.

### Verwachte output

De opgeslagen afbeelding ziet er vergelijkbaar uit met de illustratie hieronder (de daadwerkelijke weergave is weggelaten voor beknoptheid).

*Alt‑tekst voor de voorbeeldafbeelding:* **barcode‑afbeelding maken** – een PNG‑bestand dat een gestapelde omnidirectionele DataBar met een beeldverhouding van 15 weergeeft.

## Veelvoorkomende variaties en randgevallen

| Situatie | Aanpassing |
|-----------|------------|
| **Verschillende payload‑lengte** | Vervang de GTIN‑string door elke geldige DataBar‑inhoud (bijv. `(01)01234567890123`). |
| **Hogere resolutie voor grote afdrukken** | Verhoog `XDimension.Pixels` naar 4 of 5 en stel eventueel `Resolution` in `Parameters.Image` in. |
| **Andere DataBar‑formaten** | Gebruik `EncodeTypes.DatabarStacked` voor een twee‑rij gestapelde variant zonder omnidirectionele mogelijkheid. |
| **Opslaan als JPEG** | Verander `BarCodeImageFormat.Png` naar `BarCodeImageFormat.Jpeg` en stel eventueel `Quality` in. |

Deze variaties beantwoorden de bredere *how to generate databar*‑vraag door te laten zien dat dezelfde generator kan worden geherconfigureerd voor meerdere DataBar‑families.

## Volledige broncode‑overzicht

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // Define the module size (X‑dimension) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Adjust the DataBar aspect ratio to make rows taller
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;

            // Save the generated barcode as a PNG image
            string outputPath = "DatabarAspectRatio15.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to {outputPath}");
        }
    }
}
```

Kopieer de code naar `Program.cs`, herstel de NuGet‑pakketten en voer `dotnet run` uit. De console bevestigt de locatie van de afbeelding, en je kunt de PNG openen om het **barcode‑afbeelding maken**‑resultaat te verifiëren.

## Conclusie

Je weet nu hoe je een **barcode‑afbeelding kunt maken** in C# met behulp van de Barcode Generator‑bibliotheek en hoe je **DataBar**‑codes kunt genereren met precieze controle over grootte en beeldverhouding. Het volledige voorbeeld toont elke benodigde instelling — van het initialiseren van `BarcodeGenerator` tot het exporteren van een PNG‑bestand — zodat je barcode‑creatie kunt integreren in elke .NET‑applicatie zonder verder onderzoek.

### Wat is het volgende?

* Verken andere barcode‑symbologieën met `EncodeTypes` (bijv. QR, Code128) – een natuurlijke uitbreiding van de **barcode generator c#**‑workflow.
* Combineer de gegenereerde afbeelding met PDF‑ of Excel‑rapporten met behulp van Aspose.PDF of Aspose.Cells.
* Pas de kleur aan, voeg marges toe, of embed de barcode in een web‑API voor on‑demand generatie.

Voel je vrij om met de parameters te experimenteren, en laat de code dienen als een betrouwbare basis voor al je toekomstige barcode‑gerelateerde projecten. Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe een barcode‑generator C# te gebruiken om DataBar‑barcodes te maken](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)
- [Hoe een barcode‑generator C# te gebruiken om DataBar Omni‑directionele barcodes te maken](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [Hoe een gestapelde databar‑barcode te maken in C# – stap‑voor‑stap gids](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}