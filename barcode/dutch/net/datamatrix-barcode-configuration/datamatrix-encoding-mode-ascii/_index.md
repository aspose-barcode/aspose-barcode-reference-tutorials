---
date: 2026-06-09
description: Leer hoe u DataMatrix barcode in ASCII-modus kunt maken met Aspose.BarCode
  voor .NET. Deze gids laat zien hoe u snel een barcode in C# kunt genereren.
keywords:
- create datamatrix barcode
- generate barcode c#
- how to encode barcode
- barcode generator example
linktitle: DataMatrix-coderingmodus (ASCII)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  headline: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  name: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  steps:
  - name: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
    text: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
  - name: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
    text: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
  - name: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
    text: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
  type: HowTo
- questions:
  - answer: Yes, a valid Aspose license is required for production use; a free trial
      is available for evaluation.
    question: Can I use this in a commercial application?
  - answer: Absolutely – Aspose.BarCode fully supports .NET Core 3.1+, .NET 5, .NET
      6, and later versions.
    question: Does the library work with .NET Core?
  - answer: Up to 2,335 alphanumeric characters fit in a single DataMatrix symbol
      when using ASCII encoding.
    question: How many characters can I encode in ASCII mode?
  - answer: Yes, adjust `generator.Parameters.Image.ForeColor` and `BackColor` to
      any `System.Drawing.Color` value.
    question: Can I change the barcode’s foreground or background color?
  - answer: The official documentation contains dozens of samples covering custom
      sizes, colors, and error‑correction levels.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Maak DataMatrix barcode in ASCII-modus met Aspose.BarCode voor .NET
url: /nl/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak DataMatrix barcode in ASCII-modus met Aspose.BarCode voor .NET

## Introductie

Klaar om **maak DataMatrix barcode** afbeeldingen te maken die de efficiënte ASCII-codering gebruiken? In deze tutorial leer je hoe je een DataMatrix barcode in ASCII-modus genereert met Aspose.BarCode voor .NET. We lopen elke stap door — van het opzetten van het project tot het opslaan van de uiteindelijke afbeelding — zodat je barcodegeneratie aan je C#-toepassingen kunt toevoegen in enkele minuten.

## Snelle antwoorden
- **Welke bibliotheek is het beste voor DataMatrix in .NET?** Aspose.BarCode for .NET  
- **Hoeveel regels code zijn nodig?** About 5‑7 lines for a basic ASCII barcode  
- **Heb ik een licentie nodig?** A free trial works for development; a license is required for production  
- **Ondersteunde platforms?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Kan ik grootte of kleuren wijzigen?** Yes, Aspose.BarCode exposes properties for dimensions and foreground/background colors  

## Wat is DataMatrix barcode?
DataMatrix is een tweedimensionale barcode die tekst en binaire gegevens opslaat in een compact vierkant patroon.  
Een DataMatrix barcode codeert informatie in een raster van zwarte en witte modules, waardoor tot 2.335 alfanumerieke tekens in één symbool passen. Het wordt veel gebruikt in de productie, logistiek en gezondheidszorg omdat het op zeer kleine formaten kan worden afgedrukt en toch zeer goed scanbaar blijft.

## Hoe maak je DataMatrix barcode in ASCII-modus?
Laad de Aspose.BarCode namespace, maak een `BarcodeGenerator` instantie, stel de `EncodeMode` in op **EncodeMode.ASCII**, wijs je gegevensreeks toe, en roep `Save` aan om het afbeeldingsbestand te schrijven. Deze aanpak produceert een volledig conforme DataMatrix barcode met alleen ASCII-codering in slechts een paar regels C#-code.

## Waarom ASCII-codering gebruiken voor DataMatrix?
ASCII-modus is de standaard- en meest efficiënte codering voor platte‑tekstgegevens, en levert de kleinste mogelijke symboolgrootte voor alfanumerieke tekenreeksen. Het ondersteunt alle 128 ASCII‑tekens, verwerkt gegevens sneller dan uitgebreide modi, en garandeert maximale compatibiliteit met legacy‑scanners die standaard ASCII‑symbolen verwachten.

## Voorvereisten

1. **Ontwikkelomgeving** – Visual Studio, Rider, of elke C#‑compatibele IDE.  
2. **Aspose.BarCode for .NET** – Download het nieuwste pakket van [hier](https://releases.aspose.com/barcode/net/).  
   - Documentatie: [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)  
   - Community‑hulp: [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)  
3. **Basis C#-kennis** – Vertrouwdheid met de .NET-projectstructuur helpt je de stappen snel te volgen.  
4. **Andere Aspose-producten** zijn te vinden op [hier](https://releases.aspose.com/).

## Namespaces importeren

Om te beginnen, voeg de vereiste `using`-directieven toe aan de bovenkant van je C#-bestand:

```csharp
using Aspose.BarCode.Generation;
using System.Drawing;
```

Deze namespaces geven je toegang tot de `BarcodeGenerator`-klasse en de afbeeldinggerelateerde types die nodig zijn om de output op te slaan.

## Stap 1: Een map maken

Kies een map waarin de gegenereerde barcode‑afbeeldingen worden opgeslagen. Vervang `"Your Directory Path"` door een absoluut of relatief pad dat bestaat op je machine.

```csharp
string outputDir = @"C:\Barcodes";
if (!System.IO.Directory.Exists(outputDir))
{
    System.IO.Directory.CreateDirectory(outputDir);
}
```

De code zorgt ervoor dat de map bestaat voordat er bestanden worden weggeschreven, waardoor runtime‑fouten worden voorkomen.

## Stap 2: Gegevens coderen in ASCII-modus

De `BarcodeGenerator`-klasse maakt en configureert barcode‑afbeeldingen. De `DataMatrixEncodeMode`-enumeratie selecteert het coderingsalgoritme voor DataMatrix‑symbolen.

```csharp
// Initialise the generator with the data you want to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "1234567890");

// Set the encoding mode to ASCII for optimal size
generator.Parameters.Barcode.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;

// Optional: adjust image dimensions or colors here
generator.Parameters.Image.Width = 200;
generator.Parameters.Image.Height = 200;

// Save the barcode as a PNG file
string filePath = System.IO.Path.Combine(outputDir, "datamatrix_ascii.png");
generator.Save(filePath, BarCodeImageFormat.Png);
```

Na het uitvoeren van de code vind je `datamatrix_ascii.png` in de map die je hebt opgegeven. De afbeelding bevat een DataMatrix barcode die de tekenreeks `"1234567890"` codeert met de compacte ASCII-modus.

## Veelvoorkomende problemen en oplossingen

- **Bestands‑toegangs fouten** – Zorg ervoor dat de applicatie schrijfrechten heeft voor de doelmap. Visual Studio als Administrator uitvoeren kan machtigingsproblemen op Windows oplossen.  
- **Onjuiste symboolgrootte** – Als de barcode te groot of te klein lijkt, pas `generator.Parameters.Image.Width` en `Height` aan of laat Aspose de optimale grootte automatisch berekenen door die eigenschappen weg te laten.  
- **Niet‑ondersteunde tekens** – ASCII-modus accepteert alleen tekens in het bereik 0‑127. Voor Unicode‑gegevens, schakel over naar `DataMatrixEncodeMode.Base256` of een andere geschikte modus.

## Veelgestelde vragen

**V: Kan ik dit gebruiken in een commerciële applicatie?**  
A: Ja, een geldige Aspose‑licentie is vereist voor productiegebruik; een gratis proefversie is beschikbaar voor evaluatie.

**V: Werkt de bibliotheek met .NET Core?**  
A: Absoluut – Aspose.BarCode ondersteunt volledig .NET Core 3.1+, .NET 5, .NET 6 en latere versies.

**V: Hoeveel tekens kan ik coderen in ASCII-modus?**  
A: Tot 2.335 alfanumerieke tekens passen in één DataMatrix‑symbool bij gebruik van ASCII‑codering.

**V: Kan ik de voor‑ of achtergrondkleur van de barcode wijzigen?**  
A: Ja, pas `generator.Parameters.Image.ForeColor` en `BackColor` aan naar elke `System.Drawing.Color`‑waarde.

**V: Waar kan ik meer geavanceerde voorbeelden vinden?**  
A: De officiële documentatie bevat tientallen voorbeelden die aangepaste groottes, kleuren en foutcorrectieniveaus behandelen.

## Veelgestelde vragen

### V1: Kan ik Aspose.BarCode for .NET gebruiken met andere programmeertalen naast C#?
A1: Aspose.BarCode ondersteunt meerdere programmeertalen, maar deze tutorial richt zich op C#.

### V2: Wat zijn de verschillende coderingsmodi beschikbaar in DataMatrix barcodes?
A2: DataMatrix barcodes ondersteunen verschillende coderingsmodi, waaronder ASCII, C40, Text en Base256. Elke modus is geschikt voor verschillende soorten gegevens.

### V3: Kan ik het uiterlijk van de gegenereerde barcode aanpassen, zoals de grootte en kleur?
A3: Ja, Aspose.BarCode biedt een breed scala aan parameters om het uiterlijk van de barcode aan te passen, inclusief grootte, kleur en meer.

### V4: Is er een gratis proefversie van Aspose.BarCode for .NET beschikbaar?
A4: Ja, je kunt Aspose.BarCode for .NET verkennen met een gratis proefversie via [hier](https://releases.aspose.com/).

### V5: Waar kan ik een licentie voor Aspose.BarCode for .NET kopen?
A5: Je kunt een licentie kopen op de Aspose-website [hier](https://purchase.aspose.com/buy).

---

**Laatst bijgewerkt:** 2026-06-09  
**Getest met:** Aspose.BarCode 24.11 for .NET  
**Auteur:** Aspose

## Gerelateerde tutorials

- [DataMatrix-codering in Bytes met Aspose.BarCode voor .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [DataMatrix barcode lezen C# – DataMatrix-modus genereren (Auto)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Hoe DataMatrix barcodes (ECC 200) te genereren met Aspose.BarCode voor .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
```

```csharp
System.Console.WriteLine("DataMatrixEncodeModeASCII:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    // Set the X-dimension (size) of the barcode in pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set the encoding mode to ASCII
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;
    
    // Save the barcode as a PNG image
    gen.Save($"{path}DataMatrixEncodeModeASCII.png", BarCodeImageFormat.Png);
}
```

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}