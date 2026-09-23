---
date: 2026-08-28
description: Leer hoe u een barcode-afbeelding in Java maakt met Aspose Barcode Java,
  CODABAR start- en stopsymbolen instelt en PNG-bestanden genereert zonder watermerken.
keywords:
- create barcode image java
- barcode generation without watermark
- codabar start stop symbols
lastmod: 2026-08-28
linktitle: Instellen van start- en stopsymbolen
og_description: Maak barcode-afbeelding java met Aspose Barcode Java. Deze gids laat
  zien hoe u CODABAR start-/stopsymbolen instelt en PNG exporteert zonder watermerken.
og_image_alt: 'Aspose Barcode Java tutorial: create barcode image with start/stop
  symbols'
og_title: Maak barcode-afbeelding java – gids voor start-/stopsymbolen
schemas:
- author: Aspose
  dateModified: '2026-08-28'
  description: Learn how to create barcode image java with Aspose Barcode Java, set
    CODABAR start and stop symbols, and generate PNG files without watermarks.
  headline: Aspose Barcode Java – Create barcode image with start/stop symbols
  type: TechArticle
- questions:
  - answer: Aspose.BarCode for Java.
    question: What library creates barcode images in Java?
  - answer: Yes, using `setCodabarStartSymbol` and `setCodabarStopSymbol`.
    question: Can I customize start/stop symbols?
  - answer: CODABAR.
    question: Which barcode type is used in this example?
  - answer: A commercial license is required for non‑trial use.
    question: Do I need a license for production?
  - answer: PNG image saved to disk.
    question: What output format is generated?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- barcode generation
- Aspose.BarCode
- Java barcode tutorial
title: Aspose Barcode Java – Maak een barcode-afbeelding met start-/stopsymbolen
url: /nl/java/barcode-configuration/setting-start-stop-symbols/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Barcode Java – Maak barcode‑afbeelding met start/stop‑symbolen

## Inleiding

In deze uitgebreide tutorial maak je **barcode‑afbeeldingen java** met Aspose Barcode Java en leer je **hoe je start‑ en stopsymbolen** voor CODABAR‑barcodes instelt. Of je nu een point‑of‑sale‑terminal, een magazijnbeheersysteem of een andere applicatie bouwt die betrouwbare barcode‑generatie vereist, het aanpassen van deze symbolen stelt je in staat om te voldoen aan legacy‑specificaties terwijl de code schoon en onderhoudbaar blijft. We lopen elke stap door, leggen uit waarom elke instelling belangrijk is en laten zien hoe je een PNG‑afbeelding produceert zonder proef‑watermerk.

## Snelle antwoorden
- **Welke bibliotheek maakt barcode‑afbeeldingen in Java?** Aspose.BarCode for Java.  
- **Kan ik start/stop‑symbolen aanpassen?** Ja, met `setCodabarStartSymbol` en `setCodabarStopSymbol`.  
- **Welk barcode‑type wordt in dit voorbeeld gebruikt?** CODABAR.  
- **Heb ik een licentie nodig voor productie?** Een commerciële licentie is vereist voor niet‑proefgebruik.  
- **Welk uitvoerformaat wordt gegenereerd?** PNG‑afbeelding opgeslagen op schijf.

## Wat is Aspose Barcode Java?

Aspose Barcode Java is een **dependency‑vrije Java‑bibliotheek die meer dan 70 barcode‑symbologieën** genereert, van klassieke 1D‑codes zoals CODABAR tot moderne 2D‑codes zoals QR en DataMatrix. Het verzorgt alle low‑level‑codering, zodat je je kunt richten op de bedrijfslogica terwijl je voldoet aan de industrienormen.

## Waarom Aspose Barcode Java gebruiken voor barcode‑generatie zonder watermerk?

Laad eerst je licentie, en de bibliotheek produceert schone afbeeldingen—geen “Aspose Evaluation”‑overlay. Het biedt ook **fijne controle** (start/stop‑symbolen, kleuren, groottes) en **cross‑platform‑compatibiliteit** (elke Java‑runtime, inclusief Android). Met ondersteuning voor **50+ uitvoerformaten** en de mogelijkheid om afbeeldingen direct naar HTTP‑responses te streamen, is het de ideale keuze voor high‑throughput, productie‑grade barcode‑creatie.

## Voorvereisten

Zorg ervoor dat je het volgende hebt:

1. **Java Development Kit (JDK)** – Installeer de nieuwste JDK vanaf [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. **Aspose.BarCode for Java‑bibliotheek** – Download deze via de [download link](https://releases.aspose.com/barcode/java/).

Met deze componenten kun je **barcode‑afbeeldingen java** maken zonder ontbrekende onderdelen.

## Pakketten importeren

De volgende imports geven je toegang tot de kernklassen die nodig zijn voor barcode‑generatie:

De `CodabarSymbol`‑enum definieert de toegestane start/stop‑tekens voor CODABAR‑barcodes.  

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.CodabarSymbol;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Stapsgewijze gids

### Hoe definieer je de uitvoermap voor de barcode‑afbeelding?

Geef de map op waar het PNG‑bestand wordt weggeschreven. Het gebruik van `Paths.get` maakt de code draagbaar over Windows, macOS en Linux.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

### Hoe maak je een barcode‑generator voor CODABAR?

De `BarcodeGenerator`‑klasse maakt een barcode‑afbeelding voor een opgegeven symbologie en data.  

Instantieer `BarcodeGenerator` met de CODABAR‑symbologie en de gegevensreeks die je wilt coderen.

```java
// Create instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "12345678");
```

### Hoe stel je het CODABAR‑startsymbool in?

`setCodabarStartSymbol` stelt het teken in dat het begin van een CODABAR‑barcode markeert.  

Roep `setCodabarStartSymbol` aan en geef een van de ondersteunde tekens (`A`, `B`, `C`, `D`) door. In dit voorbeeld gebruiken we `A`.

```java
// Set the Codabar start symbol to A
generator.getParameters().getBarcode().getCodabar().setCodabarStartSymbol(CodabarSymbol.A);
```

### Hoe stel je het CODABAR‑stopsymbool in?

`setCodabarStopSymbol` stelt het teken in dat het einde van een CODABAR‑barcode markeert.  

Gebruik `setCodabarStopSymbol` met het bijbehorende stopsymbool—`D` in dit geval.

```java
// Set the Codabar stop symbol to D
generator.getParameters().getBarcode().getCodabar().setCodabarStopSymbol(CodabarSymbol.D);
```

### Hoe sla je de gegenereerde barcode op als PNG‑bestand?

De `SaveFormat`‑enum specificeert het bestandsformaat voor het opslaan van de barcode‑afbeelding.  

Roep de `save`‑methode aan, geef de volledige bestandsnaam en de `SaveFormat.Png`‑enumwaarde door. De afbeelding wordt zonder watermerk weggeschreven zodra een geldige licentie is toegepast.

```java
// Save the image to disk in PNG format
generator.save(dataDir + "startAndStopSymbols.png");
```

## Veelvoorkomende valkuilen & tips

De `License`‑klasse laadt een Aspose‑licentiebestand om de volledige functionaliteit in te schakelen.

- **Onjuist mappad** – Zorg ervoor dat `dataDir` eindigt met de juiste scheidingsteken of bouw het pad op met `Paths.get`.  
- **Niet‑ondersteunde start/stop‑tekens** – CODABAR accepteert alleen `A`, `B`, `C` of `D`. Een andere waarde veroorzaakt een `IllegalArgumentException`.  
- **Licentie niet toegepast** – In proefmodus bevat de output een watermerk. Laad je licentiebestand met `License license = new License(); license.setLicense("Aspose.Total.Java.lic");` vóór het aanmaken van de generator om dit te voorkomen.  
- **Grote‑schaal generatie** – Bij het genereren van duizenden barcodes, hergebruik een enkele `BarcodeGenerator`‑instantie en wijzig alleen de code‑tekst om overhead van objectcreatie te verminderen.

## Veelgestelde vragen

### Kan ik Aspose.BarCode for Java gebruiken in een commercieel project?

Ja. Koop een commerciële licentie [purchase a commercial license](https://purchase.aspose.com/buy) om het evaluatiewatermerk te verwijderen en volledige technische ondersteuning te krijgen.

### Is er een gratis proefversie beschikbaar?

Absoluut. Download de proefversie [download the trial version](https://releases.aspose.com/) om alle functies te evalueren voordat je koopt.

### Hoe kan ik ondersteuning krijgen voor Aspose.BarCode for Java?

Bezoek het Aspose.BarCode‑forum [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) voor community‑hulp, of open een supportticket via je Aspose‑account‑portaal.

### Hoe verkrijg ik een tijdelijke licentie voor testen?

Je kunt een tijdelijke 30‑daagse licentie aanvragen [request a temporary 30‑day license](https://purchase.aspose.com/temporary-license/). Hiermee kun je productielike tests uitvoeren zonder een volledige aankoop.

### Welke andere barcode‑symbologieën ondersteunt Aspose.BarCode?

De bibliotheek ondersteunt **70+ symbologieën**, waaronder Code128, EAN‑13, QR, DataMatrix, PDF417 en nog veel meer. Zie de volledige lijst in de officiële documentatie.

## Extra Q&A (AI‑vriendelijk)

**V:** Welke afbeeldingsformaten kan ik exporteren naast PNG?  
**A:** Aspose.BarCode ondersteunt PNG, JPEG, BMP, GIF en TIFF. Kies het gewenste formaat door de `SaveFormat`‑enumwaarde in de `save`‑aanroep te wijzigen.

**V:** Kan ik barcode‑afbeeldingen in het geheugen genereren zonder naar schijf te schrijven?  
**A:** Ja. Roep `generator.save(OutputStream)` aan om direct naar een stream te schrijven—ideaal voor web‑API’s die de afbeelding als HTTP‑respons teruggeven.

**V:** Werkt de bibliotheek op Android?  
**A:** De Java‑versie draait op Android, maar je moet handmatig de benodigde afhankelijkheden opnemen (geen Maven Central voor Android). De kern‑API blijft identiek.

## Conclusie

Je hebt nu geleerd hoe je **barcode‑afbeeldingen java** maakt en nauwkeurig **start/stop‑symbolen** voor een CODABAR‑barcode instelt met Aspose Barcode Java. Deze aanpak geeft je de flexibiliteit om legacy‑specificaties te vervullen terwijl je codebase schoon en onderhoudbaar blijft. Verken verdere aanpassingen—zoals het wijzigen van kleuren, het toevoegen van mens‑leesbare tekst, of overschakelen naar andere symbologieën—door de officiële API‑referentie te raadplegen op [documentation](https://reference.aspose.com/barcode/java/).

---

**Laatst bijgewerkt:** 2026-08-28  
**Getest met:** Aspose.BarCode for Java 24.12  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Validate Checksum and Create Codabar Barcode in Java with Aspose.BarCode](/barcode/java/checksum-and-validation/)
- [Create Barcode with Aspose - Set X & Y Dimensions in Java](/barcode/java/barcode-configuration/managing-x-y-dimension-barcode/)
- [How to generate barcode java: Create an Exact Barcode Image](/barcode/java/barcode-basics/creating-image-exact-barcode/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}