---
date: 2026-03-07
description: Leer hoe u één-dimensionale databar GS1‑gecodeerde barcodes in .NET kunt
  maken met Aspose.BarCode. Deze gids laat zien hoe u GS1 instelt, de barcodegenerator
  configureert en snel barcodes genereert.
linktitle: One-Dimensional Databar GS1 Encoding
second_title: Aspose.BarCode .NET API
title: Maak een één-dimensionale Databar GS1-codering met Aspose.BarCode
url: /nl/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak één-dimensionale Databar GS1-codering met Aspose.BarCode

In deze tutorial **maak je één-dimensionale databar** barcodes die voldoen aan de GS1-standaard, met behulp van de Aspose.BarCode bibliotheek voor .NET. Of je nu strikte GS1-validatie nodig hebt of een flexibelere barcode, we lopen elke stap door—van het installeren van de bibliotheek tot het afhandelen van coderingsuitzonderingen—zodat je betrouwbare barcodes kunt genereren in je eigen toepassingen.

## Snelle antwoorden
- **Wat betekent “create one-dimensional databar”?** Het betekent het genereren van een lineaire (1‑D) barcode van de Databar-familie, vaak gebruikt voor detailhandel en logistiek.  
- **Hoe stel ik GS1-validatie in?** Stel `IsAllowOnlyGS1Encoding` in op `true` op de `DataBar`-parameters.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Welke .NET-versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Waar kan ik de bibliotheek downloaden?** Van de officiële Aspose-releasepagina (zie vereisten).

## Wat is “create one-dimensional databar”?
Een één-dimensionale Databar (ook bekend als RSS) is een compacte lineaire barcode die numerieke gegevens, datums of AI‑strings (Application Identifier) kan coderen. Wanneer deze wordt gecombineerd met GS1-codering, volgt de barcode een wereldwijd erkende datastructuur, waardoor hij ideaal is voor detailhandel, gezondheidszorg en supply‑chain scenario's.

## Waarom Aspose.BarCode voor .NET gebruiken?
Aspose.BarCode biedt een vloeiende API, volledige GS1-ondersteuning en de mogelijkheid om elk visueel aspect van de barcode fijn af te stemmen. Het verwijdert het giswerk van low‑level codering en laat je je concentreren op de bedrijfslogica.

## Vereisten

1. **Aspose.BarCode for .NET** – download en installeer het vanaf [here](https://releases.aspose.com/barcode/net/).  
2. **Your Directory Path** – vervang `"Your Directory Path"` in de voorbeelden door een map waarin je schrijfrechten hebt.

## Namespaces importeren

Voeg de benodigde `using`-statements toe aan de bovenkant van je C#-bestand:

```csharp
using Aspose.BarCode;
using System;
```

## Stap 1: Initialiseer de Barcode Generator

Maak een `BarcodeGenerator`-instantie aan en specificeer de Databar Expanded-symbologie:

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## Stap 2: Hoe GS1 in te stellen – Genereer een barcode met strikte GS1-validatie

Schakel GS1‑alleen codering in, wijs een GS1‑conforme codetext toe, en sla de afbeelding op:

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## Stap 3: Barcodegeneratie met Aspose – Variabele codering (geen GS1-controle)

Als je een barcode nodig hebt die **niet** de GS1-regels afdwingt, schakel dan de controle uit:

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## Stap 4: Barcodegenerator GS1-controle – Een uitzondering afhandelen

Wanneer `IsAllowOnlyGS1Encoding` `true` is maar de codetext niet GS1‑conform is, gooit Aspose een uitzondering. Het volgende patroon laat zien hoe je deze kunt opvangen en loggen:

```csharp
try
{
    gen.CodeText = "ASPOSE";
    gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### Veelvoorkomende valkuilen & tips
- **Valkuil:** Het leveren van een niet‑GS1‑string terwijl de GS1-controle is ingeschakeld, zal de barcodegeneratie afbreken.  
- **Pro tip:** Valideer je AI‑strings voordat je ze toewijst aan `CodeText` om runtime‑fouten te voorkomen.  
- **Tip:** Gebruik absolute paden of `Path.Combine` om bestandsnamen veilig op te bouwen over verschillende platformen.

## Conclusie

Je weet nu hoe je **one-dimensional databar** barcodes met GS1-codering kunt maken, hoe je de GS1-controle kunt in- of uitschakelen, en hoe je gerelateerde uitzonderingen kunt afhandelen—alles met Aspose.BarCode voor .NET. Voel je vrij om extra stijlopties te verkennen, zoals barcodegrootte, kleur en marges via het `Parameters.Barcode`-object.

Als je tegen problemen aanloopt, zijn de officiële documentatie en het community‑forum uitstekende bronnen:

- [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/)  
- [Aspose.BarCode support forum](https://forum.aspose.com/c/barcode/13)

## Veelgestelde vragen

### 1. Wat is GS1-codering in barcodes?
GS1-codering is een gestandaardiseerde manier om gegevens (bijv. productidentifiers) binnen een barcode te structureren, waardoor interoperabiliteit tussen detailhandelaren, fabrikanten en logistieke dienstverleners wordt gegarandeerd.

### 2. Kan ik het uiterlijk van de gegenereerde barcodes aanpassen?
Ja. Aspose.BarCode stelt je in staat om grootte, kleuren, marges aan te passen, en zelfs mens‑leesbare tekst toe te voegen via de `Parameters.Barcode`-instellingen.

### 3. Waar kan ik extra bronnen en documentatie voor Aspose.BarCode vinden?
Je kunt uitgebreide documentatie en voorbeelden vinden op [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/). Het is een waardevolle bron voor leren en probleemoplossing.

### 4. Is er een proefversie beschikbaar voor Aspose.BarCode?
Ja, je kunt een gratis proefversie van Aspose.BarCode voor .NET krijgen via [here](https://releases.aspose.com/).

### 5. Hoe kan ik een licentie voor Aspose.BarCode voor .NET aanschaffen?
Om een licentie voor Aspose.BarCode voor .NET aan te schaffen, bezoek je de [purchase page](https://purchase.aspose.com/buy) op de Aspose-website.

---

**Laatst bijgewerkt:** 2026-03-07  
**Getest met:** Aspose.BarCode 24.11 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}