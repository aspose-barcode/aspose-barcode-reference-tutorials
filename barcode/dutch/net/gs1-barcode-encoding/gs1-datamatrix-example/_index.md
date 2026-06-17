---
date: 2026-02-22
description: Leer hoe u een barcode‑afbeelding in C# maakt met Aspose.BarCode voor
  .NET en snel en efficiënt GS1 DataMatrix‑barcodes genereert.
linktitle: GS1 DataMatrix Example
second_title: Aspose.BarCode .NET API
title: Barcodeafbeelding maken C# – GS1 DataMatrix-voorbeeld
url: /nl/net/gs1-barcode-encoding/gs1-datamatrix-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GS1 DataMatrix Voorbeeld

Als u op zoek bent naar een betrouwbare manier om **create barcode image C#** te maken in uw .NET‑toepassingen, maakt Aspose.BarCode for .NET het proces eenvoudig. Deze krachtige bibliotheek ondersteunt een breed scala aan symbologieën, waaronder GS1 DataMatrix, en biedt een duidelijke API waarmee u zich kunt concentreren op uw bedrijfslogica in plaats van op low‑level barcode‑details. In de komende paar minuten lopen we een compleet, hands‑on voorbeeld door dat laat zien hoe u een GS1 DataMatrix‑barcode genereert, het uiterlijk aanpast en opslaat als een afbeeldingsbestand.

## Snelle Antwoorden
- **Wat genereert het voorbeeld?** Een GS1 DataMatrix‑barcode die voorbeeldproductgegevens bevat.  
- **Welke bibliotheek wordt gebruikt?** Aspose.BarCode for .NET.  
- **Kan ik het uitvoerformaat wijzigen?** Ja, u kunt opslaan als PNG, JPEG, BMP, enz.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een gratis proefversie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Is de code compatibel met .NET Core?** Absoluut – dezelfde API werkt op .NET Framework en .NET Core/5/6.

## Wat is een GS1 DataMatrix‑barcode?

Een GS1 DataMatrix is een tweedimensionale barcode die product‑niveau informatie codeert (zoals GTIN, serienummer en extra toepassingsidentifiers). Het wordt veel gebruikt in de detailhandel, gezondheidszorg en logistiek voor compacte, hoge‑dichtheid gegevensopslag.

## Waarom Aspose.BarCode gebruiken om **create barcode image C#** te maken?

- **Full‑featured API** – ondersteunt GS1‑standaarden, foutcorrectie en grootte‑controle.  
- **No external dependencies** – pure .NET‑bibliotheek, gemakkelijk te integreren.  
- **Cross‑platform** – werkt op Windows, Linux en macOS.  
- **Extensive documentation** – bevat voorbeelden zoals deze om snel aan de slag te gaan.

## Vereisten

Voordat we in de tutorial duiken, zorg ervoor dat u de volgende vereisten heeft:

1. **Aspose.BarCode for .NET** – U moet Aspose.BarCode for .NET geïnstalleerd hebben. Als u dat nog niet heeft gedaan, kunt u [download it here](https://releases.aspose.com/barcode/net/).  
2. **Development Environment** – U dient een .NET‑ontwikkelomgeving op uw systeem geïnstalleerd te hebben (Visual Studio, VS Code of een andere IDE naar keuze).

Nu de vereisten klaar zijn, laten we beginnen met het genereren van GS1 DataMatrix‑barcodes.

## Namespaces importeren

Importeer eerst de benodigde namespaces om met Aspose.BarCode for .NET te werken. Deze namespaces geven u toegang tot de barcode‑generatiemogelijkheden.

```csharp
using Aspose.BarCode;
using System;
```

## Hoe **create barcode image C#** te maken – Stapsgewijze gids

### Stap 1: De Barcode‑generator instellen

Om te beginnen maakt u een `BarcodeGenerator`‑instantie aan en specificeert u de **GS1 DataMatrix**‑symbologie samen met de gegevens die u wilt coderen. In dit voorbeeld coderen we de string **"(01)12345678901231(21)ASPOSE(30)9876"**, die het GS1 Application Identifier‑formaat volgt.

```csharp
// The path to the documents directory.
string path = "Your Directory Path";
System.Console.WriteLine("Gs1DataMatrixExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1DataMatrix, "(01)12345678901231(21)ASPOSE(30)9876");
```

*Pro tip:* Vervang de voorbeeldgegevens door uw eigen GS1‑identifiers om aan uw productcatalogus te voldoen.

### Stap 2: Barcode‑eigenschappen aanpassen

U kunt het uiterlijk van de barcode aanpassen met het `Parameters`‑object. Hier stellen we de X‑dimensie (de grootte van de kleinste module) in op 8 pixels en definiëren we een matrixgrootte van 36 kolommen bij 12 rijen. Pas deze waarden aan om aan uw scan‑vereisten te voldoen.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 8;
gen.Parameters.Barcode.DataMatrix.Columns = 36;
gen.Parameters.Barcode.DataMatrix.Rows = 12;
```

*Waarom X‑dimensie aanpassen?* Een grotere X‑dimensie maakt de barcode gemakkelijker te scannen op apparaten met lage resolutie, terwijl een kleinere waarde de afbeeldingsgrootte verkleint.

### Stap 3: De barcode‑afbeelding opslaan

Sla tenslotte de gegenereerde barcode op schijf op. Het voorbeeld gebruikt PNG, maar u kunt kiezen uit JPEG, GIF, BMP en andere formaten die door Aspose.BarCode worden ondersteund.

```csharp
gen.Save($"{path}Gs1DataMatrixExample.png", BarCodeImageFormat.Png);
```

Wanneer u de code uitvoert, vindt u **Gs1DataMatrixExample.png** in de opgegeven map, klaar voor gebruik in etiketten, verpakkingen of digitale toepassingen.

## Veelvoorkomende gebruikssituaties

- **Retail product labeling** – GTIN, batchnummers en vervaldatums coderen.  
- **Pharmaceutical tracking** – Voldoen aan regelgeving met GS1‑conforme gegevens.  
- **Warehouse logistics** – Compact locatie‑ en voorraadinformatie opslaan.  

## Probleemoplossing & Tips

- **Incorrect data format** – Zorg ervoor dat uw string de GS1 Application Identifier‑syntaxis volgt; anders is de barcode mogelijk niet scanbaar.  
- **Image size issues** – Als de gegenereerde afbeelding onscherp lijkt, verhoog dan de `XDimension.Pixels`‑waarde.  
- **License errors** – Een proeflicentie werkt voor evaluatie, maar een volledige licentie is vereist voor productie‑implementaties.

## Veelgestelde vragen

### Wat is GS1 DataMatrix?
GS1 DataMatrix is een tweedimensionale barcode‑symbologie die wordt gebruikt voor het coderen van gegevens met betrekking tot producten en hun identificatie, met name in de detailhandel en de gezondheidszorg.

### Is Aspose.BarCode for .NET geschikt voor andere barcode‑typen?
Ja, Aspose.BarCode for .NET ondersteunt een breed scala aan barcode‑typen, waardoor het veelzijdig is voor verschillende toepassingen.

### Kan ik barcodes genereren in andere afbeeldingsformaten naast PNG?
Ja, Aspose.BarCode for .NET stelt u in staat om gegenereerde barcodes op te slaan in verschillende afbeeldingsformaten, zoals JPEG, GIF en BMP, naast PNG.

### Heb ik een licentie nodig om Aspose.BarCode for .NET te gebruiken?
Ja, een geldige licentie is vereist voor commercieel gebruik van Aspose.BarCode for .NET. U kunt een licentie verkrijgen via de [Aspose website](https://purchase.aspose.com/buy).

### Waar kan ik ondersteuning krijgen voor Aspose.BarCode for .NET?
U kunt antwoorden op uw vragen vinden en ondersteuning zoeken in het [Aspose.BarCode for .NET forum](https://forum.aspose.com/c/barcode/13).

## Aanvullende FAQ (AI‑Geoptimaliseerd)

**Q: Hoe genereer ik een DataMatrix‑barcode in C# zonder GS1‑opmaak?**  
A: Gebruik `EncodeTypes.DataMatrix` in plaats van `EncodeTypes.GS1DataMatrix` en geef de platte gegevensreeks door aan de `BarcodeGenerator`.

**Q: Kan ik de barcode‑kleuren programmatisch wijzigen?**  
A: Ja, stel `gen.Parameters.Barcode.ForeColor` en `gen.Parameters.Barcode.BackColor` in om de voor‑ en achtergrondkleuren aan te passen.

**Q: Is het mogelijk om de gegenereerde barcode direct in een PDF in te sluiten?**  
A: Absoluut – haal de barcode op als een `System.Drawing.Image` en voeg deze toe aan een PDF met Aspose.PDF of een andere PDF‑bibliotheek.

**Q: Welke .NET‑versies worden ondersteund?**  
A: Aspose.BarCode for .NET ondersteunt .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6 en later.

**Q: Hoe kan ik de scan‑betrouwbaarheid voor kleine etiketten verbeteren?**  
A: Verhoog de X‑dimensie, voeg stille zones toe (`gen.Parameters.Barcode.Margin`) en zorg voor voldoende contrast tussen de barcode en de achtergrond.

## Conclusie

In deze tutorial hebben we onderzocht hoe u **create barcode image C#** kunt gebruiken met Aspose.BarCode for .NET om een GS1 DataMatrix‑barcode te genereren. Met slechts een paar code‑regels kunt u barcodes van hoge kwaliteit in uw toepassingen integreren, of u nu retail‑oplossingen, zorgsystemen of logistieke platforms bouwt. Verken de bibliotheek verder om extra symbologieën, geavanceerde renderopties en integratiescenario's te ontdekken.

Voor meer informatie en gedetailleerde documentatie, raadpleeg de [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-22  
**Tested With:** Aspose.BarCode for .NET (latest version)  
**Author:** Aspose  

---