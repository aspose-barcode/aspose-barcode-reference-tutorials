---
category: general
date: 2026-10-28
description: Genereer postbarcode in C# met het Planet‑formaat. Dit Planet‑barcodevoorbeeld
  laat zien hoe je de barcodebreedte instelt en zowel gevulde als lege staven opslaat.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- set barcode width
- planet barcode example
language: nl
lastmod: 2026-10-28
og_description: Genereer postbarcode in C# met een volledig planet‑barcode‑voorbeeld.
  Leer de barcodebreedte instellen, gevulde strepen maken en lege‑streep‑afbeeldingen
  creëren.
og_image_alt: Screenshot of a generated Planet postal barcode saved as PNG
og_title: Genereer postbarcode in C# – stap‑voor‑stap gids
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  headline: How to generate postal barcode in C# – planet example
  type: TechArticle
- description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  name: How to generate postal barcode in C# – planet example
  steps:
  - name: Build the project (`dotnet build`).
    text: Build the project (`dotnet build`).
  - name: Run the executable (`dotnet run`).
    text: Run the executable (`dotnet run`).
  - name: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
    text: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
  - name: Open each image; you should see a series of vertical bars representing the
      numeric string
    text: Open each image; you should see a series of vertical bars representing the
      numeric string
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Hoe een postbarcode te genereren in C# – planet-voorbeeld
url: /nl/python-java/general/how-to-generate-postal-barcode-in-c-planet-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een postbarcode genereren in C# – Planet voorbeeld

Als je een postbarcode moet genereren in C#, leidt deze gids je door een volledige oplossing. Je ziet een praktisch Planet‑barcode‑voorbeeld dat een numerieke string codeert, je de barcode‑breedte laat instellen, en zowel gevulde als lege balkafbeeldingen opslaat.

Het maken van een postbarcode vereist geen complexe build‑pipeline. Aan het einde van deze tutorial kun je barcode‑generatie integreren in elke .NET‑applicatie, de X‑dimensie aanpassen, en kiezen of de balken gevuld of leeg worden weergegeven.

## Vereisten

* .NET 6.0 SDK of later geïnstalleerd  
* Een C# ontwikkelomgeving (Visual Studio, VS Code, of Rider)  
* Het **Aspose.BarCode for .NET** NuGet‑pakket (versie 23.10 of nieuwer)  

U kunt het pakket toevoegen met de volgende opdracht:

```bash
dotnet add package Aspose.BarCode
```

De code‑fragmenten hieronder gaan ervan uit dat je `using Aspose.BarCode.Generation;` aan het begin van je bestand hebt toegevoegd.

## Genereer een postbarcode met Planet‑symbologie

De eerste stap is het maken van een `BarcodeGenerator`‑instantie die de Planet‑symbologie gebruikt. Planet is een postbarcode‑formaat dat door verschillende nationale postdiensten wordt gebruikt.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a Planet barcode generator with the data to encode
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Additional configuration will be applied here (see next steps)

        // Save the filled‑bars image
        barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // Switch to empty bars and save the second image
        barcodeGenerator.Parameters.Barcode.FilledBars = false;
        barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**Waarom dit belangrijk is:**  
`EncodeTypes.Planet` vertelt de bibliotheek om de Planet‑barcode‑standaard te gebruiken, die numerieke gegevens codeert in een reeks balken en spaties. De constructor ontvangt de gegevensreeks (`"123456"` in dit geval) die je wilt coderen.

Het uitvoeren van het programma genereert twee PNG‑bestanden in de werkmap van het uitvoerbare bestand:

* **PostalPlanetFilledBars.png** – balken worden weergegeven als solide zwarte rechthoeken.  
* **PostalPlanetEmptyBars.png** – balken worden weergegeven als witte rechthoeken met een zwarte omtrek, handig voor afdrukken op donkere achtergronden.

## Stel de barcode‑breedte (X‑dimensie) in pixels in

De visuele grootte van een barcode wordt bepaald door de X‑dimensie, die de breedte van een enkele balk definieert. Het aanpassen van deze waarde zorgt ervoor dat de barcode correct wordt gescand bij de beoogde afdrukresolutie.

```csharp
// Define the width of each bar (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

**Waarom je dit moet instellen:**  
Een grotere X‑dimensie maakt de barcode gemakkelijker te scannen met scanners met lage resolutie, terwijl een kleinere waarde de totale afbeeldingsgrootte verkleint voor hoge‑dichtheid afdrukken. De standaardbreedte is 2 pixels; 4 pixels is een veelvoorkomend compromis voor de meeste desktop‑printers.

Je kunt experimenteren met verschillende waarden:

| Pixels | Typisch gebruiksscenario |
|--------|--------------------------|
| 2      | Labels met hoge dichtheid |
| 4      | Standaard kantoorafdrukken |
| 6‑8    | Signage in groot formaat |

**Tip:** Altijd de gegenereerde barcode testen met je doel‑scanner na het wijzigen van de X‑dimensie.

## Planet‑barcode‑voorbeeld – gevulde vs lege balken

Een Planet‑barcode kan worden gerenderd met ofwel solide (gevulde) balken of omrande (lege) balken. De eigenschap `FilledBars` schakelt dit gedrag.

```csharp
// Save the barcode with the default filled bars
barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// Configure the generator to produce empty (unfilled) bars
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the barcode with empty bars
barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Waarom je lege balken zou kunnen kiezen:**  
Lege balken verbeteren het contrast op donker getinte verpakkingen, omdat het witte interieur van elke balk opvalt tegen een donkere achtergrond. Gevulde balken zijn de standaard en werken goed op lichtgekleurde media.

**Verwachte output:**  

*Beide afbeeldingen tonen dezelfde gecodeerde gegevens (`123456`).* Het enige visuele verschil is de balkstijl. Hieronder staat een tekstuele beschrijving van wat je zult zien:

* **Afbeelding met gevulde balken:** Solide zwarte verticale balken op een witte achtergrond.  
* **Afbeelding met lege balken:** Zwarte omtrekken die hetzelfde patroon vormen, met witte interieurs.

Je kunt de PNG‑bestanden openen in elke afbeeldingsviewer om te verifiëren dat het patroon overeenkomt met de Planet‑specificatie.

## Pas extra barcode‑eigenschappen aan (optioneel)

Hoewel de bovenstaande kernstappen de meeste scenario's dekken, wil je mogelijk andere instellingen fijn afstemmen:

| Eigenschap | Beschrijving | Typische waarde |
|------------|--------------|-----------------|
| `Barcode.Color` | Voorgrondkleur van de balken | `System.Drawing.Color.Black` |
| `Barcode.BackgroundColor` | Achtergrondvulkleur | `System.Drawing.Color.White` |
| `Barcode.CodeText` | Menselijk leesbare tekst onder de barcode | Zelfde als gecodeerde data of een aangepast label |
| `Barcode.ImageFormat` | Uitvoerformaat (PNG, JPEG, BMP, etc.) | `BarCodeImageFormat.Png` |

Voorbeeld van het instellen van een aangepaste voorgrondkleur:

```csharp
barcodeGenerator.Parameters.Barcode.Color = System.Drawing.Color.DarkBlue;
```

Deze optionele aanpassingen helpen je om de huisstijl van het bedrijf te matchen of te voldoen aan specifieke afdrukvereisten.

## Veelvoorkomende valkuilen en hoe ze te vermijden

| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| Barcode is niet leesbaar | X‑dimensie te klein voor de DPI van de printer | Verhoog `XDimension.Pixels` naar 4 of hoger |
| Afbeeldingsbestand is beschadigd | Ontbrekende schrijfrechten in de doelmap | Gebruik een absoluut pad of zorg dat de map bestaat |
| Verkeerde symbologie gebruikt | `EncodeTypes.Code128` doorgeven in plaats van `EncodeTypes.Planet` | Controleer of het `EncodeTypes`‑argument overeenkomt met het postformaat |

**Pro‑tip:** Genereer altijd een test‑barcode en scan deze met de beoogde hardware voordat je naar productie gaat.

## Volledig, uitvoerbaar voorbeeld

Hieronder staat een zelfstandige console‑applicatie die alle besproken stappen bevat. Kopieer de code naar een nieuw .NET‑console‑project en voer het uit om de twee PNG‑bestanden in de uitvoermap te zien verschijnen.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a Planet barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Set the width of each bar (X‑dimension) to 4 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the barcode with the default filled bars
            generator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved filled‑bars barcode as PostalPlanetFilledBars.png");

            // 4️⃣ Configure the generator to produce empty (unfilled) bars
            generator.Parameters.Barcode.FilledBars = false;

            // 5️⃣ Save the barcode with empty bars
            generator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved empty‑bars barcode as PostalPlanetEmptyBars.png");
        }
    }
}
```

**Verificatiestappen:**  

1. Bouw het project (`dotnet build`).  
2. Voer het uitvoerbare bestand uit (`dotnet run`).  
3. Zoek `PostalPlanetFilledBars.png` en `PostalPlanetEmptyBars.png` in de map `bin/Debug/net6.0`.  
4. Open elke afbeelding; je zou een reeks verticale balken moeten zien die de numerieke string weergeven


## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe een planet‑barcode te maken met gevulde en lege balken](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [Hoe de breedte in te stellen en een Planet‑barcode te genereren in C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Maak een postbarcode in C# – volledig generator‑voorbeeld](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}