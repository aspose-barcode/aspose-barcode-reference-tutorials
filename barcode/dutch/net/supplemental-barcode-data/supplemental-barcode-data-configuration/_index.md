---
date: 2026-03-07
description: Leer hoe je een EAN‑13‑barcode met aanvullende gegevens maakt in C# met
  Aspose.BarCode voor .NET – genereer snel een barcode‑PNG.
linktitle: Supplemental Barcode Data Configuration
second_title: Aspose.BarCode .NET API
title: EAN-13 barcode maken met aanvullende gegevens – Aspose.BarCode
url: /nl/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak EAN-13 Barcode met Aanvullende Gegevens – Aspose.BarCode voor .NET

In deze praktische tutorial zult u **een EAN-13 barcode** maken die aanvullende EAN‑2- of EAN‑5-gegevens bevat, en u zult zien hoe u **barcode PNG**-bestanden kunt genereren met slechts een paar regels C#. Of u nu een kassasysteem voor detailhandel bouwt, een logistieke applicatie, of een eenvoudig voorraadtool, de mogelijkheid om aanvullende informatie toe te voegen maakt uw barcodes veel bruikbaarder.

## Snelle Antwoorden
- **Wat betekent “aanvullende gegevens”?** Extra cijfers (EAN‑2/EAN‑5) die naast de hoofdbarcode worden afgedrukt, vaak gebruikt voor prijs- of uitgave‑nummers.  
- **Welke barcode‑type wordt gebruikt?** EAN‑13 als het primaire symbool, met optionele EAN‑2- of EAN‑5‑aanvullingen.  
- **Kan ik PNG‑afbeeldingen exporteren?** Ja – de `Save`‑methode laat u direct naar PNG exporteren.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Is dit compatibel met .NET Core / .NET 6?** Absoluut – Aspose.BarCode ondersteunt alle moderne .NET‑runtime‑omgevingen.

## Voorvereisten

- Visual Studio (of een andere .NET‑compatibele IDE).  
- Een kopie van Aspose.BarCode voor .NET – download deze **[hier](https://releases.aspose.com/barcode/net/)**.  
- Basiskennis van C#.  
- Een beschrijfbare map waar de gegenereerde PNG‑bestanden worden opgeslagen.

## Namespaces Importeren

Voeg eerst de Aspose.BarCode‑namespace toe zodat u toegang heeft tot de generator‑klassen:

```csharp
using Aspose.BarCode.Generation;
```

> **Pro tip:** Als u .NET Core gebruikt, voeg dan het NuGet‑pakket `Aspose.BarCode` toe aan uw project in plaats van de DLL handmatig te refereren.

## Wat is een Aanvullende Barcode?

Een aanvullende barcode is een extra numerieke reeks die naast de hoofdbarcode wordt afgedrukt.  
- **EAN‑2** – twee‑cijferige aanvulling, vaak gebruikt voor uitgave‑nummers op tijdschriften.  
- **EAN‑5** – vijf‑cijferige aanvulling, algemeen gebruikt voor prijsuitbreidingen op detailhandelsartikelen.

Het toevoegen van deze aanvullingen wijzigt de primaire EAN‑13‑gegevens niet; het levert simpelweg extra context die scanners kunnen lezen.

## Waarom Aspose.BarCode gebruiken voor Aanvullende Gegevens?

- **One‑line API** – configureer zowel de hoofdbarcode als de aanvulling in één enkel object.  
- **Volledige controle over afmetingen** – pas X‑dimensie, aanvulling‑spatiëring en afbeeldingsformaat aan.  
- **Cross‑platform** – werkt op .NET Framework, .NET Core en .NET 5/6+.  

## Stapsgewijze Gids

### Stap 1: Stel de Uitvoermap in

Definieer waar de PNG‑bestanden worden opgeslagen. Vervang de tijdelijke aanduiding door een echt pad op uw machine.

```csharp
string path = "Your Directory Path";
```

### Stap 2: Initialiseer de Barcode Generator (Barcode Generator C#)

Maak een `BarcodeGenerator`‑instantie aan, waarbij u **EAN‑13** als hoofdtype opgeeft en de 13‑cijferige payload levert.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

### Stap 3: Pas de Barcode‑Afmetingen Aan

Stel de visuele grootte van de barcode en de gereserveerde ruimte voor de aanvulling nauwkeurig af.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

### Stap 4: Voeg een EAN‑2‑Aanvulling toe

Stel de aanvullende gegevens in op een twee‑cijferige waarde (bijv. “12”). Deze verschijnt rechts van de hoofdbarcode.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

### Stap 5: Sla de EAN‑2‑Barcode op als PNG

Exporteer de afbeelding. Het argument `BarCodeImageFormat.Png` zorgt voor een PNG‑bestand van hoge kwaliteit.

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

### Stap 6: Schakel over naar een EAN‑5‑Aanvulling

Verander de `SupplementData` naar een vijf‑cijferige tekenreeks voor prijsuitbreidingen.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

### Stap 7: Sla de EAN‑5‑Barcode op als PNG

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

> **Waarom dit werkt:** Dezelfde `BarcodeGenerator`‑instantie wordt hergebruikt, dus u hoeft alleen de `SupplementData`‑eigenschap aan te passen vóór elke `Save`‑aanroep. Dit houdt de code beknopt en voorkomt onnodige objectcreatie.

## Veelvoorkomende Problemen & Tips

- **Ongeldig mappad** – zorg ervoor dat de map bestaat en dat de applicatie schrijfrechten heeft.  
- **Onjuiste aanvullinglengte** – EAN‑2 verwacht exact 2 cijfers, EAN‑5 verwacht 5; anders wordt een uitzondering gegooid.  
- **Afbeelding niet zichtbaar** – controleer of `BarCodeImageFormat.Png` wordt gebruikt; andere formaten (bijv. JPEG) kunnen compressie‑artefacten introduceren die de leesbaarheid voor scanners beïnvloeden.  

## Veelgestelde Vragen

### Kan ik Aspose.BarCode voor .NET gebruiken in mijn .NET Core‑project?
Ja, Aspose.BarCode voor .NET is volledig compatibel met .NET Core, .NET 5 en .NET 6.

### Is er een gratis proefversie beschikbaar voor Aspose.BarCode voor .NET?
Ja, u kunt het gratis uitproberen door **[deze link](https://releases.aspose.com/)** te bezoeken.

### Waar kan ik een tijdelijke licentie krijgen voor Aspose.BarCode voor .NET?
U kunt een tijdelijke licentie verkrijgen via **[deze link](https://purchase.aspose.com/temporary-license/)**.

### Ondersteunt Aspose.BarCode een breed scala aan barcode‑typen?
Absoluut – het ondersteunt EAN‑13, QR Code, Code 128, DataMatrix, PDF‑417 en nog veel meer.

### Kan ik het uiterlijk van de gegenereerde barcodes aanpassen?
Ja, u kunt kleuren, lettertypen, marges aanpassen en zelfs achtergrondafbeeldingen toevoegen via de uitgebreide `Parameters`‑API.

## Conclusie

U weet nu hoe u **een EAN-13 barcode** kunt maken met aanvullende EAN‑2‑ of EAN‑5‑gegevens en **barcode PNG**‑bestanden kunt genereren met Aspose.BarCode voor .NET. Deze aanpak geeft u volledige controle over barcode‑afmetingen, aanvulling‑spatiëring en uitvoerformaat, waardoor het ideaal is voor detailhandel, logistiek en elke situatie waarin extra numerieke informatie vereist is.

Voor een diepere verkenning, bekijk de volledige referentiegids: **[Aspose.BarCode for .NET documentatie](https://reference.aspose.com/barcode/net/)**.

---

**Last Updated:** 2026-03-07  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}