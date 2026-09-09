---
date: 2026-04-12
description: Leer hoe je een Code128‑barcode met lege balken maakt in Java met Aspose.BarCode.
  Deze gids laat zien hoe je snel barcode‑Java‑afbeeldingen genereert.
keywords:
- create code128 barcode
- generate barcode java
- barcode generator java example
- java generate barcode image
linktitle: Barcode genereren met lege staven
second_title: Aspose.BarCode Java API
title: Hoe maak je een Code128-barcode met lege balken in Java
url: /nl/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een Code128-barcode met lege staven te maken in Java

## Introductie

Het integreren van barcode‑generatie in Java‑toepassingen is een veelvoorkomende eis, of je nu inventoriesystemen, ticketplatforms of point‑of‑sale‑oplossingen bouwt. Met **Aspose.BarCode for Java** kun je **Code128‑barcode**‑afbeeldingen maken in slechts een paar regels code. In deze tutorial lopen we de stappen door om **barcode‑Java**‑afbeeldingen te genereren met lege (niet‑gevulde) staven, waardoor je volledige controle krijgt over de visuele stijl van de barcode.

## Snelle antwoorden
- **Welke bibliotheek?** Aspose.BarCode for Java  
- **Primaire gebruikssituatie?** Code128‑barcodes met lege staven maken voor aangepaste UI‑ontwerpen  
- **Voorvereisten?** Java JDK 8+, Aspose.BarCode JAR, schrijfrechten op een map voor de uitvoerafbeelding  
- **Typische implementatietijd?** 5‑10 minuten voor een basisvoorbeeld  
- **Kan ik kleuren aanpassen?** Ja – de API biedt uitgebreide stijlopties  

## Wat is een Code128-barcode?

Code128 is een hoogdichte lineaire barcode‑symbool die de volledige ASCII‑karakterset codeert. Het wordt veel gebruikt in logistiek, verzending en detailhandel omdat het alfanumerieke gegevens compact kan weergeven. Standaard rendert Aspose.BarCode Code128‑staven als solide rechthoeken; door de **FilledBars**‑eigenschap op `false` te zetten, worden ze lege (omtrek‑)staven, wat nuttig is voor stilistische branding.

## Waarom Aspose.BarCode voor Java gebruiken?

- **Rijke functieverzameling** – ondersteunt meer dan 50 barcode‑typen, inclusief QR, DataMatrix en PDF417.  
- **Geen externe afhankelijkheden** – één enkele JAR werkt op elke Java‑runtime.  
- **Fijne controle** – je kunt de staafbreedte, kleuren, lettertypen en de `FilledBars`‑eigenschap aanpassen.  
- **Cross‑platform** – werkt op Windows, Linux en macOS zonder native bibliotheken.

## Voorvereisten

Voordat je begint, zorg ervoor dat je het volgende hebt:

1. **Java-ontwikkelomgeving** – JDK 8 of hoger geïnstalleerd en `JAVA_HOME` geconfigureerd.  
2. **Aspose.BarCode for Java** – download de nieuwste JAR van de [download page](https://releases.aspose.com/barcode/java/).  
3. **Documentdirectory** – een map op je computer waar de gegenereerde barcode‑afbeelding wordt opgeslagen.

## Pakketten importeren

In je Java‑project importeer je de klassen die je nodig hebt om met Aspose.BarCode te werken:

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

Deze imports geven je toegang tot de barcode‑generator, de enumeratie voor afbeeldingsformaten en foutafhandeling.

## Stap 1: De resource‑directory instellen

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Vervang `"Your Document Directory"` door het absolute pad naar de map die je in de voorvereisten hebt aangemaakt. Hier wordt het PNG‑bestand geschreven.

## Stap 2: Code128‑barcode‑generator‑instantie maken

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

Hier maken we een instantie van `BarcodeGenerator` met de **CODE_128**‑symbologie en de voorbeeldtekst `"TEXT"`. Dit is een **barcode‑generator Java‑voorbeeld** dat je kunt aanpassen aan elke string die je wilt coderen.

## Stap 3: Eigenschap FilledBars op false zetten

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

Door `FilledBars` op `false` te zetten, zal de gegenereerde barcode lege staven weergeven in plaats van solide, waardoor het gewenste visuele effect ontstaat.

## Stap 4: De barcode‑afbeelding opslaan

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

De `save`‑methode schrijft de barcode naar de opgegeven directory in PNG‑formaat. Je kunt `BarCodeImageFormat.PNG` wijzigen naar `JPG`, `BMP` of `TIFF` als een ander afbeeldingstype vereist is.

## Veelvoorkomende gebruikssituaties

- **Aangepaste branding** – lege staven kunnen worden overlegd met achtergrondpatronen of kleuren.  
- **Print‑klare assets** – genereer hoge‑resolutie PNG's voor opname in facturen of verzendetiketten.  
- **Dynamische generatie** – maak barcodes on‑the‑fly in webservices of desktop‑applicaties.

## Probleemoplossingstips

- **Ongeldig pad** – zorg ervoor dat `dataDir` eindigt met een bestandsscheidingsteken (`/` of `\\`) of concateneer met `File.separator`.  
- **Licentie vereist** – een proefversie werkt voor evaluatie, maar een volledige licentie is nodig voor productie.  
- **Niet‑ondersteunde tekens** – Code128 ondersteunt de volledige ASCII‑set; vermijd Unicode‑tekens tenzij je overschakelt naar een andere symbologie.

## Conclusie

Je hebt nu geleerd hoe je **Code128‑barcode**‑afbeeldingen met lege staven kunt maken met Aspose.BarCode voor Java. Deze eenvoudige aanpak stelt je in staat om snel aanpasbare barcode‑graphics te genereren, of je nu een desktop‑inventarisatietool of een cloud‑gebaseerde API bouwt.

## Veelgestelde vragen

### Is Aspose.BarCode compatibel met alle Java‑ontwikkelomgevingen?
Ja, Aspose.BarCode is ontworpen om naadloos te integreren met elke Java‑IDE of build‑systeem, inclusief Maven, Gradle en gewone JAR‑projecten.

### Kan ik het uiterlijk van de gegenereerde barcode aanpassen?
Absoluut! Naast `FilledBars` kun je kleuren, staafbreedte, marges aanpassen en zelfs menselijk leesbare tekst toevoegen via de uitgebreide API.

### Is er een proefversie beschikbaar voor Aspose.BarCode?
Ja, je kunt de mogelijkheden van Aspose.BarCode verkennen door een gratis proefversie te verkrijgen [hier](https://releases.aspose.com/).

### Hoe kan ik ondersteuning krijgen voor Aspose.BarCode?
Voor vragen of hulp, bezoek het [Aspose.BarCode‑forum](https://forum.aspose.com/c/barcode/13).

### Waar kan ik gedetailleerde documentatie voor Aspose.BarCode vinden?
De uitgebreide documentatie is beschikbaar [hier](https://reference.aspose.com/barcode/java/).

**Aanvullende vragen**

**Q: Hoe genereer ik een barcode‑afbeelding in een ander formaat, zoals JPEG?**  
A: Verander het tweede argument van `save` naar `BarCodeImageFormat.JPEG`.

**Q: Kan ik meerdere barcodes in een lus genereren?**  
A: Ja – maak een nieuwe `BarcodeGenerator` aan binnen je lus of hergebruik dezelfde instantie met een nieuwe `CodeText`.

---

**Laatst bijgewerkt:** 2026-04-12  
**Getest met:** Aspose.BarCode for Java 24.11  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}