---
date: 2026-01-04
description: Leer hoe u een Codabar-barcode met start‑ en stoptekens kunt genereren
  met Aspose.BarCode voor .NET. Een stapsgewijze tutorial voor barcodegeneratie voor
  ontwikkelaars.
linktitle: Codabar Start/Stop Characters
second_title: Aspose.BarCode .NET API
title: Genereer Codabar-barcode met start-/stoptekens in Aspose.BarCode voor .NET
url: /nl/net/codabar-encoding-and-checksum/codabar-start-stop-characters/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Genereer Codabar-barcode met start/stop‑tekens in Aspose.BarCode voor .NET

## Inleiding

Welkom bij deze uitgebreide gids over hoe je **codabar‑barcode**‑afbeeldingen genereert met start/stop‑tekens met behulp van Aspose.BarCode voor .NET. Of je nu een retail‑inventarisatiesysteem, een laboratorium‑sample‑tracker of een medische‑record‑oplossing bouwt, Codabar is een betrouwbare numerieke symbologie die expliciete start‑ en stop‑symbolen vereist voor nauwkeurige scanning. In de komende minuten lopen we alles door wat je nodig hebt — van de vereisten tot het opslaan van de uiteindelijke PNG‑bestanden — zodat je meteen Codabar‑barcodes kunt maken.

## Snelle antwoorden
- **Welke bibliotheek heb ik nodig?** Aspose.BarCode voor .NET  
- **In welk formaat kan ik de barcode opslaan?** PNG (BarCodeImageFormat.Png)  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Kan ik de start/stop‑symbolen wijzigen?** Ja – gebruik CodabarSymbol.A, B, C of D.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Voorvereisten

Voordat we beginnen, zorgen we ervoor dat je alles hebt om deze tutorial te volgen:

1. **Omgevingsconfiguratie** – Zorg dat je een werkende .NET‑ontwikkelomgeving op je machine hebt. Als je begeleiding nodig hebt, raadpleeg dan de [documentatie](https://reference.aspose.com/barcode/net/).  
2. **Aspose.BarCode voor .NET Bibliotheek** – Download en installeer de bibliotheek van de officiële [bron](https://releases.aspose.com/barcode/net/).  
3. **Basis .NET‑kennis** – Vertrouwdheid met C# en Visual Studio (of een andere favoriete IDE) maakt de stappen soepeler.  
4. **IDE** – Visual Studio, Rider of Visual Studio Code zijn allemaal geschikt.

Nu we de voorvereisten hebben behandeld, duiken we in de daadwerkelijke code.

## Namespaces importeren

Om te beginnen met Aspose.BarCode voor .NET, zorg ervoor dat je de benodigde namespace importeert:

```csharp
using Aspose.BarCode.Generation;
```

## Hoe een Codabar‑barcode te genereren – Stapsgewijze handleiding

### Stap 1: Initialiseer de Barcode‑generator

Maak een `BarcodeGenerator`‑instantie, specificeer **Codabar** als het coderings‑type en geef de gegevensreeks op die al de start/stop‑tekens bevat (bijv. “-12345-”).

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarStartStop:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

> **Pro‑tip:** Het streepje (`-`) is een van de geldige start/stop‑symbolen voor Codabar. Je kunt ook A, B, C of D gebruiken, afhankelijk van de eisen van je toepassing.

### Stap 2: Stel de X‑dimensie in (breedte van barcode‑element)

De X‑dimensie bepaalt de breedte van de smalste balk. Pas deze aan op basis van je scan‑omgeving.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Waarom het belangrijk is:** Een grotere X‑dimensie verbetert de leesbaarheid op laag‑resolutie‑printers, terwijl een kleinere waarde ruimte bespaart op hoge‑dichtheidslabels.

### Stap 3: Definieer start‑ en stop‑tekens

Codabar ondersteunt vier start/stop‑symbolen (A, B, C, D). Hieronder vind je voorbeelden voor elke optie. Kies degene die overeenkomt met de specificatie van het systeem waarmee je integreert.

#### Instellen van Start A en Stop A

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.A;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.A;
```

#### Instellen van Start B en Stop B

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.B;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.B;
```

#### Instellen van Start C en Stop C

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.C;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.C;
```

#### Instellen van Start D en Stop D

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.D;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.D;
```

Je kunt de configuratie herhalen voor elk symbool dat je moet genereren; het voorbeeld hieronder slaat vier afzonderlijke afbeeldingen op — één voor elk start/stop‑paar.

### Stap 4: Sla de gegenereerde barcode‑afbeeldingen op (PNG)

Schrijf tenslotte de barcode naar PNG‑bestanden. Dit demonstreert het **save barcode png**‑gebruiksscenario en levert kant‑klaar‑te‑gebruiken assets voor testen.

```csharp
gen.Save($"{path}CodabarStartAStopA.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartBStopB.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartCStopC.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartDStopD.png", BarCodeImageFormat.Png);
```

Elke file bevat nu een **codabar‑barcode‑voorbeeld** met de bijbehorende start/stop‑symbolen.

## Veelvoorkomende problemen & foutopsporing

| Symptoom | Waarschijnlijke oorzaak | Oplossing |
|----------|--------------------------|-----------|
| Barcode ziet er vervormd uit | X‑dimensie te laag voor de gekozen printerresolutie | Verhoog `XDimension.Pixels` (bijv. naar 3 of 4) |
| Scanner kan start/stop niet lezen | Verkeerd start/stop‑symbool voor het doelsysteem | Controleer het vereiste symbool (A‑D) en stel het correct in |
| PNG‑bestand is leeg of corrupt | Ongeldig uitvoerpad of onvoldoende schrijfrechten | Zorg dat `path` naar een bestaande map wijst en dat je app schrijfrechten heeft |

## Veelgestelde vragen

### Q1: Wat is Codabar en waarom zijn start‑ en stop‑tekens belangrijk?

A1: Codabar is een numerieke barcode‑symbologie die veel wordt gebruikt in voorraadbeheer, bibliotheken en de gezondheidszorg. Start‑ en stop‑tekens definiëren de grenzen van de barcode, zodat scanners weten waar de gegevens beginnen en eindigen.

### Q2: Kan ik het uiterlijk van Codabar‑barcodes aanpassen met Aspose.BarCode voor .NET?

A2: Ja. Naast de X‑dimensie kun je kleuren wijzigen, marges toevoegen en de barcode zelfs in PDF‑ of SVG‑formaten insluiten met dezelfde API.

### Q3: Zijn er beperkingen voor Codabar‑barcodes qua gegevenscodering?

A3: Codabar ondersteunt voornamelijk numerieke gegevens (0‑9) en enkele speciale tekens. Het is niet geschikt voor volledige alfanumerieke strings.

### Q4: Is Aspose.BarCode voor .NET geschikt voor commercieel gebruik, en hoe kan ik een licentie verkrijgen?

A4: Ja, het is productie‑klaar. Koop een licentie op de [aankooppagina van Aspose](https://purchase.aspose.com/buy).

### Q5: Waar kan ik hulp zoeken of discussiëren over problemen met Aspose.BarCode voor .NET?

A5: Word lid van de community op het [Aspose.BarCode voor .NET supportforum](https://forum.aspose.com/c/barcode/13) voor assistentie van zowel Aspose‑engineers als mede‑ontwikkelaars.

---

**Last Updated:** 2026-01-04  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}