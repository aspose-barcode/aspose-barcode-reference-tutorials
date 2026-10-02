---
category: general
date: 2026-09-07
description: Genereer PDF417‑barcode in C# en leer hoe je de afmetingen van de barcode
  kunt instellen voor precieze controle. Volg deze stap‑voor‑stap‑gids om een PNG‑afbeelding
  te maken.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- how to set barcode dimensions
language: nl
lastmod: 2026-09-07
og_description: Genereer PDF417-barcode in C# en leer hoe je de afmetingen van de
  barcode instelt. Deze tutorial toont een volledig, uitvoerbaar voorbeeld.
og_image_alt: Generated PDF417 barcode image with custom dimensions
og_title: Genereer PDF417-barcode in C# – volledige gids met afmetingen
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  headline: How to generate PDF417 barcode in C# with custom dimensions
  type: TechArticle
- description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  name: How to generate PDF417 barcode in C# with custom dimensions
  steps:
  - name: Expected output
    text: '- **File:** `Pdf417Layout.png` (PNG, lossless) - **Dimensions:** Determined
      by `XDimension` (2 px) × (columns × rows) matrix - **Content:** A scannable
      PDF417 barcode encoding the Unicode string `Åspóse.Barcóde©`'
  - name: What if I need a larger image for printing?
    text: Increase `XDimension.Pixels` to 4 or 5. Larger values produce a higher‑resolution
      barcode but also increase file size.
  - name: Can I encode more data than the example string?
    text: Yes. PDF417 can hold up to 1,850 characters. Just replace the text argument
      in the `BarcodeGenerator` constructor. If the data exceeds the matrix capacity,
      the library automatically adds extra rows.
  - name: How does error correction work?
    text: 'PDF417 includes built‑in error correction. You can adjust its level via:'
  - name: What if the barcode appears blurry on screen?
    text: 'Make sure the output image’s DPI matches the display environment. You can
      set DPI when saving:'
  - name: Next steps
    text: '- Explore **how to generate PDF417 barcode** with different image formats
      (JPEG, BMP). - Learn **how to set barcode dimensions** dynamically based on
      user input or device DPI. - Integrate the barcode generation into an ASP.NET
      Core API to serve barcodes on demand.'
  type: HowTo
tags:
- barcode generation
- PDF417
- C#
title: Hoe PDF417-barcode te genereren in C# met aangepaste afmetingen
url: /nl/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417 barcode te genereren in C# met aangepaste afmetingen

Als je een **PDF417 barcode wilt genereren** in een .NET‑applicatie, laat deze gids je precies zien hoe je dat doet. Je ziet een volledig, uitvoerbaar voorbeeld dat een PNG‑afbeelding maakt terwijl je de afmetingen van de barcode kunt bepalen.

Het genereren van een PDF417 barcode is een veelvoorkomende eis voor voorraad‑systemen, instapkaarten en beveiligde documenten. In deze tutorial leer je ook **hoe je barcode‑afmetingen instelt** zodat de output overeenkomt met je lay‑outbehoeften.

## Vereisten

Voordat je begint, zorg dat je het volgende hebt:

- .NET 6.0 SDK of later geïnstalleerd  
- Visual Studio 2022 (of een andere C#‑compatibele IDE)  
- Het **Aspose.BarCode for .NET** NuGet‑pakket (of een andere compatibele bibliotheek die PDF417 ondersteunt)  

Je kunt het pakket toevoegen met de volgende opdracht:

```bash
dotnet add package Aspose.BarCode
```

## Stap 1: Maak een PDF417 barcode‑generator

De eerste stap is het instantieren van een `BarcodeGenerator` met het type `EncodeTypes.Pdf417` en de tekst die je wilt coderen. Het generator‑object bevat alle instellingen voor de barcode.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");
```

**Waarom dit belangrijk is:** De `EncodeTypes.Pdf417`‑enum vertelt de bibliotheek om de PDF417‑symbologie te gebruiken, die grote gegevens‑payloads en foutcorrectie ondersteunt. De tekst‑string kan Unicode‑tekens bevatten, zodat je internationale symbolen kunt coderen zonder extra moeite.

## Stap 2: Hoe barcode‑afmetingen in te stellen

Het bepalen van de grootte van elk module (het kleinste zwart/witte vierkant) bepaalt de algehele beeldresolutie. De eigenschap `XDimension.Pixels` stelt de pixelbreedte van één module in.

```csharp
        // Step 2: Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Waarom dit belangrijk is:** Een grotere `XDimension` levert een hoger‑resolutie‑beeld op, wat nuttig is voor afdrukken of scannen van een afstand. Een kleinere waarde verkleint de bestandsgrootte voor webgebruik.

## Stap 3: Definieer de PDF417‑lay‑out (kolommen en rijen)

PDF417 stelt je in staat de matrixvorm te beïnvloeden door het aantal kolommen en rijen op te geven. Dit kan de leesbaarheid en de fysieke grootte van de barcode beïnvloeden.

```csharp
        // Step 3: Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

**Waarom dit belangrijk is:** Het aanpassen van kolommen en rijen laat je de barcode in een specifieke ruimte passen of voldoen aan de aspect‑ratio‑vereisten van een scanner. De bibliotheek voegt automatisch opvulling toe als de gegevens de matrix niet volledig vullen.

## Stap 4: Sla de barcode op als PNG‑afbeelding

Schrijf tenslotte de gegenereerde barcode naar een bestand. PNG behoudt verliesvrije kwaliteit, waardoor het ideaal is voor verdere verwerking.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

Wanneer je het programma uitvoert, verschijnt `Pdf417Layout.png` in de output‑map van het project. Het beeld ziet er als volgt uit:

![Generated PDF417 barcode image with custom dimensions](og_image_placeholder.png)

*Afbeeldingsalt‑tekst: Gegenereerde PDF417 barcode‑afbeelding met aangepaste afmetingen*  

**Waarom dit belangrijk is:** Opslaan als PNG zorgt ervoor dat de exacte module‑afmetingen die je hebt ingesteld behouden blijven, wat cruciaal is voor downstream‑scan‑toepassingen.

## Volledig voorbeeld in één blok

Hieronder staat het volledige programma dat je kunt kopiëren, plakken en uitvoeren zonder aanpassingen (behalve het output‑pad indien gewenst).

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

### Verwachte output

- **Bestand:** `Pdf417Layout.png` (PNG, verliesvrij)  
- **Afmetingen:** Bepaald door `XDimension` (2 px) × (kolommen × rijen) matrix  
- **Inhoud:** Een scanbare PDF417 barcode die de Unicode‑string `Åspóse.Barcóde©` codeert

## Veelgestelde vragen en randgevallen

### Wat als ik een groter beeld nodig heb voor afdrukken?

Verhoog `XDimension.Pixels` naar 4 of 5. Grotere waarden produceren een hogere resolutie barcode, maar vergroten ook de bestandsgrootte.

### Kan ik meer data coderen dan de voorbeeld‑string?

Ja. PDF417 kan tot 1.850 tekens bevatten. Vervang gewoon het tekstargument in de `BarcodeGenerator`‑constructor. Als de data de matrixcapaciteit overschrijdt, voegt de bibliotheek automatisch extra rijen toe.

### Hoe werkt foutcorrectie?

PDF417 bevat ingebouwde foutcorrectie. Je kunt het niveau aanpassen via:

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // 0‑8, higher = more correction
```

Hogere niveaus verhogen de robuustheid ten koste van grotere barcodes.

### Wat als de barcode wazig lijkt op het scherm?

Zorg ervoor dat de DPI van de output‑afbeelding overeenkomt met de weergave‑omgeving. Je kunt DPI instellen bij het opslaan:

```csharp
barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png, 300);
```

## Pro‑tips

- **Pro‑tip:** Test de gegenereerde barcode altijd met de daadwerkelijke scanner die je wilt gebruiken. Verschillende apparaten hebben verschillende toleranties voor module‑grootte en stille zones.  
- **Let op:** Zeer kleine `XDimension`‑waarden (< 1 px) kunnen op high‑DPI‑schermen als onzichtbare lijnen renderen.  
- **Tip voor web‑apps:** Serveer de PNG met `Cache-Control: public, max-age=86400` om herhaalde generatie‑overhead te verminderen.

## Conclusie

Je weet nu hoe je een **PDF417 barcode kunt genereren** in C# en precies **barcode‑afmetingen kunt instellen** om aan elke eis te voldoen. Het volledige, uitvoerbare voorbeeld toont hoe je een PNG‑afbeelding maakt met aangepaste kolom/rij‑lay‑out en module‑grootte, klaar voor afdrukken of digitale distributie.

### Volgende stappen

- Verken **hoe PDF417 barcode te genereren** met verschillende beeldformaten (JPEG, BMP).  
- Leer **hoe barcode‑afmetingen dynamisch in te stellen** op basis van gebruikersinvoer of apparaat‑DPI.  
- Integreer de barcode‑generatie in een ASP.NET Core API om barcodes on‑demand te leveren.

Voel je vrij om te experimenteren met andere PDF417‑instellingen zoals foutcorrectie, marges en kleur. Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Generate PDF417 Barcode in C# – Complete Guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}