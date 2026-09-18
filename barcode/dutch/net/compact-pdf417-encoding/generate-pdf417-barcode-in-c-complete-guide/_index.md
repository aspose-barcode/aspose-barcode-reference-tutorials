---
category: general
date: 2026-09-18
description: Leer hoe je snel een PDF417 barcode-afbeelding in C# kunt maken en kolommen
  instelt voor een compacte barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode image
- compact pdf417 barcode
- Aspose.BarCode PDF417
- C# barcode generation
- set barcode columns
lastmod: 2026-09-18
og_description: Leer hoe je snel een PDF417 barcode-afbeelding in C# kunt maken en
  kolommen instelt voor een compacte barcode. Aspose.BarCode maakt het eenvoudig.
og_image_alt: Developer guide showing a compact PDF417 barcode PNG generated with
  Aspose.BarCode
og_title: Maak PDF417 barcode-afbeelding – stap‑voor‑stap C# gids
schemas:
- author: Aspose
  dateModified: '2026-09-18'
  description: Learn how to create PDF417 barcode image in C# quickly and set columns
    for a compact barcode.
  headline: Create PDF417 barcode image – complete guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- Aspose.BarCode
title: Hoe een PDF417 barcode-afbeelding te maken in C# – volledige gids
url: /nl/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417-barcodeafbeelding te maken in C# – volledige gids

Als je een **PDF417 barcode‑afbeelding** moet maken in een .NET‑applicatie, ben je hier op de juiste plek. Of je nu boarding‑pass‑tags afdrukt, voorraadgegevens codeert, of een mobiel‑ticketingsysteem bouwt, PDF417 levert hoge‑capaciteit, tweedimensionale barcodes. Deze gids laat zien hoe je de afbeelding genereert met Aspose.BarCode en hoe je kolommen instelt zodat de barcode zo compact mogelijk blijft.

## Snelle antwoorden
- **Welke bibliotheek maakt PDF417‑barcodes?** Aspose.BarCode for .NET.
- **Hoeveel regels code zijn nodig?** Ongeveer 10 regels in een console‑app.
- **Kan ik de breedte van de barcode regelen?** Ja, door de `Columns`‑eigenschap in te stellen.
- **Welk afbeeldingsformaat wordt aanbevolen?** PNG voor verlies‑loze kwaliteit.
- **Wordt .NET 6 ondersteund?** Volledig – de bibliotheek werkt met .NET 6, .NET 7 en later.

## Wat is een PDF417‑barcode‑afbeelding?
De PDF417‑barcode‑afbeelding is een tweedimensionale matrix die tot 1 700 tekens per rij opslaat, waarbij rijen en kolommen worden gebruikt om gegevens dicht te verpakken. Aspose.BarCode rendert deze matrix naar standaard afbeeldingsformaten zoals PNG, JPEG of BMP. Het kan in verschillende formaten worden opgeslagen en is geschikt voor afdrukken op labels, tickets of mobiele schermen.

## Waarom kolommen instellen voor een compacte PDF417‑barcode‑afbeelding?
Kolommen instellen laat je de breedte van de barcode verkleinen, wat essentieel is voor smalle labels of UI‑elementen met beperkte ruimte. Aspose.BarCode ondersteunt 1‑30 kolommen, en het kiezen van een lager aantal vermindert de totale afbeeldingsbreedte tot wel 40 % terwijl de gegevensintegriteit behouden blijft. Deze aanpassing helpt barcodes op kleine tags te passen zonder leesbaarheid op te offeren.

## Hoe PDF417‑barcode‑afbeelding te maken in C#?
Laad de `Aspose.BarCode`‑bibliotheek, configureer een `BarcodeGenerator` met `EncodeTypes.Pdf417`, stel `Columns` en `Truncate` in, en sla vervolgens het resultaat op als PNG. Het volledige proces vereist twee methode‑aanroepen en levert een kant‑klaar afbeeldingsbestand op. Je kunt ook afmetingen, kleuren aanpassen en menselijk leesbare tekst toevoegen om aan de eisen van je applicatie te voldoen.

### Vereisten
- .NET 6+ SDK (of nieuwer)
- Visual Studio 2022 of een C#‑editor
- NuGet‑pakket `Aspose.BarCode`

### Stapsgewijze implementatie

## Stap 1: Installeer het Aspose.BarCode NuGet‑pakket
`Aspose.BarCode` is een .NET‑bibliotheek voor het genereren en lezen van verschillende barcode‑symbologieën.

```bash
dotnet add package Aspose.BarCode
```

Die enkele regel haalt alle types op die je nodig hebt, inclusief `BarcodeGenerator`, `EncodeTypes` en de `BarCodeImageFormat`‑enum.

> **Pro tip:** Als je .NET Framework target in plaats van .NET 6, gebruik dan de klassieke PowerShell‑opdracht `Install-Package Aspose.BarCode` in de Package Manager Console.

## Stap 2: Maak een minimale console‑applicatie
`BarcodeGenerator` maakt barcode‑afbeeldingen op basis van opgegeven instellingen. `EncodeTypes` somt de ondersteunde barcode‑symbologieën op. `BarCodeImageFormat` somt afbeeldingsformaten op.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Define the data you want to encode.
            string data = "SampleBarcode©";

            // 2️⃣ Instantiate the generator for PDF417.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // 3️⃣ Set the size of a single barcode module (pixel dimension).
            //    This is the “X‑Dimension” – smaller values yield a finer image.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ **How to set columns** – configure the matrix layout.
            //    Fewer columns = taller barcode; more columns = wider barcode.
            generator.Parameters.Barcode.Pdf417.Columns = 3;   // 👈 primary levers
            generator.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

            // 5️⃣ Choose where the PNG will be saved.
            string outputPath = @"./CompactPdf417.png";

            // 6️⃣ Save the generated barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode saved to {outputPath}");
        }
    }
}
```

**Waarom dit belangrijk is:**  
- `EncodeTypes.Pdf417` geeft aan dat we een PDF417‑barcode willen, niet QR of Code128.  
- `XDimension.Pixels` regelt de resolutie van elke kleine zwarte of witte module.  
- Het **how to set columns**‑blok beïnvloedt direct de vorm van de **PDF417‑barcode‑afbeelding**.  
- `Truncate = true` verwijdert onnodige lege rijen, waardoor je die “compacte” uitstraling krijgt die veel scanners waarderen.

## Stap 3: Dieper duiken – kolommen en truncatie begrijpen

### Hoe kolommen in te stellen
PDF417 rangschikt gegevens in een matrix van *rijen* × *kolommen*. De bibliotheek gebruikt standaard 5 kolommen, wat voor de meeste gevallen werkt. Echter, je hebt mogelijk een smallere barcode nodig om op een label te passen of een bredere om de scan‑betrouwbaarheid te verbeteren. De eigenschap:

```csharp
generator.Parameters.Barcode.Pdf417.Columns = <desiredColumnCount>;
```

accepteert waarden van **1** tot **30** (de exacte limiet hangt af van de gegevenslengte). Hier is een snelle cheat‑sheet:

| Kolommen | Approx. breedte (mm) | Wanneer te gebruiken |
|----------|----------------------|-----------------------|
| 1‑3      | Zeer smal            | Klein label, beperkte ruimte |
| 4‑6      | Standaard            | De meeste bonnen, tickets |
| 7‑10     | Breder               | Hoge‑dichtheid gegevens, betere leesbaarheid |

### Truncate (compacte modus)
Het instellen van `Truncate = true` vertelt de encoder om onnodige lege rijen onderaan af te knippen. Het resultaat is een **compacte PDF417‑barcode‑afbeelding** die zo klein mogelijk is, terwijl alle gegevens behouden blijven. Als je ooit “barcode te groot voor label” fouten krijgt, schakel dan deze vlag.

## Stap 4: Voer de app uit en controleer de output
Compile and execute:

```bash
dotnet run
```

Je zou het console‑bericht moeten zien dat de opslaglocatie bevestigt. Navigeer naar de map en open `CompactPdf417.png`. De afbeelding zal er ongeveer zo uitzien:

![Gegenereerde PDF417 barcode‑afbeelding](./CompactPdf417.png "Gegenereerde PDF417 barcode‑afbeelding – compacte PNG gemaakt door Aspose.BarCode")

[Gegenereerde PDF417 barcode‑afbeelding](./CompactPdf417.png "Gegenereerde PDF417 barcode‑afbeelding – compacte PNG gemaakt door Aspose.BarCode")

*Afbeeldings‑alt‑tekst:* **Gegenereerde PDF417 barcode‑afbeelding** – een compacte PNG‑bestand geproduceerd door de tutorial‑code.

Als je scanner het kan lezen, gefeliciteerd—je hebt met succes een **PDF417‑barcode** gegenereerd en beheerst **hoe kolommen in te stellen** voor een nette **PDF417‑barcode‑afbeelding**.

## Stap 5: Veelvoorkomende valkuilen & hoe ze op te lossen

| Symptoom | Waarschijnlijke oorzaak | Snelle oplossing |
|----------|--------------------------|-------------------|
| Barcode ziet er wazig uit | `XDimension.Pixels` te laag (bijv. 1) | Verhoog naar 2‑3 pixels voor een duidelijkere afbeelding. |
| Scanner kan niet lezen | Te veel kolommen voor de gegeven data | Verminder `Columns` of schakel `Truncate` in. |
| Verkeerd bestandsformaat | Per ongeluk opgeslagen met `BarCodeImageFormat.Jpeg` | Gebruik `BarCodeImageFormat.Png` voor verliesvrije resultaten. |
| Uitzondering `ArgumentOutOfRangeException` | Kolomtelling overschrijdt het toegestane bereik | Houd kolommen tussen 1‑30 en zorg dat de data past. |

## Stap 6: Verder gaan – kleuren aanpassen en tekst toevoegen
Als je de barcode wilt laten overeenkomen met een merk‑palet, kun je de voor‑ en achtergrondkleuren aanpassen:

```csharp
generator.Parameters.Barcode.BarcodeColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

Of plaats menselijk leesbare tekst onder de barcode:

```csharp
generator.Parameters.Barcode.CodeText = data; // shows the raw string
generator.Parameters.Barcode.CodeLocation = CodeLocation.Below;
```

Deze toevoegingen zijn optioneel, maar ze illustreren hoe flexibel de **generate PDF417 barcode**‑workflow kan zijn.

## Conclusie
We hebben een compleet, end‑to‑end voorbeeld doorlopen dat een **PDF417‑barcode** genereert met Aspose.BarCode, uitgelegd **hoe kolommen in te stellen** om de afmetingen van de barcode te beheersen, en het resultaat opgeslagen als een scherpe **PDF417‑barcode‑afbeelding** in PNG‑formaat. De code is zelf‑voorzienend, werkt met .NET 6+, en kan in elk bestaand project worden geïntegreerd met minimale moeite.

Wat nu? Probeer grotere payloads te coderen (bijv. JSON‑strings), experimenteer met verschillende afbeeldingsformaten, of integreer de generator in een web‑API die barcodes on‑demand levert. De mogelijkheden zijn eindeloos, en je hebt nu een solide basis om op voort te bouwen.

Veel plezier met coderen, en moge je barcodes altijd bij de eerste poging scannen!

## Wat je hierna moet leren
De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies te beheersen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe een barcode te maken – Compacte PDF417 met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hoe barcode‑afbeelding te genereren in Java met Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Barcode genereren Java – Afbeeldingsresolutie instellen met Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)

## Veelgestelde vragen

**Q: Kan ik de gegenereerde PNG gebruiken op een webpagina zonder extra conversie?**  
A: Ja, PNG wordt natively ondersteund door alle moderne browsers, dus je kunt het bestand direct insluiten met een `<img>`‑tag.

**Q: Hoeveel tekens kan een PDF417‑barcode bevatten?**  
A: Tot 1 700 tekens per rij en tot 30 rijen, wat een theoretisch maximum van ongeveer 51 000 tekens oplevert, hoewel praktische limieten afhangen van de scanner‑mogelijkheden.

**Q: Vereist Aspose.BarCode een licentie voor ontwikkeling?**  
A: Een gratis evaluatielicentie is beschikbaar voor testen; een commerciële licentie is vereist voor productie‑implementaties.

**Q: Is het mogelijk om PDF417‑barcodes te genereren in een achtergrondservice?**  
A: Absoluut. De bibliotheek is thread‑safe voor alleen‑lezen‑operaties, zodat je barcodes kunt genereren in ASP.NET Core of Windows‑services zonder UI‑interactie.

**Q: Welke afbeeldingsformaten naast PNG worden ondersteund?**  
A: BMP, JPEG, GIF, TIFF en SVG worden allemaal ondersteund via de `BarCodeImageFormat`‑enumeratie.

---

**Laatst bijgewerkt:** 2026-09-18  
**Getest met:** Aspose.BarCode 24.11 for .NET  
**Auteur:** Aspose  

```bash
dotnet add package Aspose.BarCode
```

## Gerelateerde tutorials

- [PDF417‑barcode maken met Aspose – volledige gids](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-complete-guide/)
- [Hoe PDF417‑barcode‑afbeelding te genereren in C met Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [PDF417‑barcode maken in C – stapsgewijze gids](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}