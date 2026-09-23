---
date: 2026-05-04
description: Leer hoe u een Data Matrix‑barcode maakt met een Java‑barcodebibliotheek
  en de tekstlocatie van de barcode boven het symbool instelt met Aspose.BarCode.
  Volg ons stapsgewijze voorbeeld voor barcode‑generatie.
keywords:
- java barcode library
- barcode generation example
- barcode text above
- customize barcode text
linktitle: Instelling code‑tekstlocatie
second_title: Aspose.BarCode Java API
title: Maak Data Matrix-barcode met Java Barcode Library en stel de locatie van de
  code‑tekst in
url: /nl/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak Data Matrix barcode met Java Barcode Library en stel code‑tekstlocatie in

## Inleiding

Als je een voorraad‑, verzend‑ of volgsysteem in Java bouwt, ontdek je al snel dat een betrouwbare **java barcode library** essentieel is. Met **Aspose.BarCode for Java** kun je een **Data Matrix barcode** genereren in slechts een paar regels code en de visuele lay‑out volledig beheersen, inclusief waar de mens‑leesbare tekst verschijnt. In deze tutorial lopen we een volledig **barcode‑generatie‑voorbeeld** door, laten we zien hoe je de **barcode‑tekst** kunt aanpassen en leggen we uit waarom het plaatsen van de tekst boven het symbool de bruikbaarheid kan verbeteren.

## Snelle antwoorden
- **Welke bibliotheek wordt gebruikt?** Aspose.BarCode for Java  
- **Welk barcode‑type wordt gedemonstreerd?** Data Matrix  
- **Hoe positioneer je de code‑tekst?** Met `CodeLocation.ABOVE` (je kunt ook `BELOW` gebruiken)  
- **Heb je een licentie nodig voor productie?** Ja, een commerciële licentie is vereist  
- **Kan de code draaien op Java 8+?** Absoluut, het ondersteunt Java 8 en later  

## Wat is een Java barcode library?
Een **java barcode library** biedt ontwikkelaars kant‑klaar API’s om 1‑D‑ en 2‑D‑barcodes direct vanuit Java‑applicaties te maken, lezen en op te maken. Het abstraheert de complexe coderingsregels en laat je focussen op de bedrijfslogica in plaats van op low‑level beeldverwerking.

## Waarom een Java barcode library gebruiken voor barcode‑generatie‑voorbeeld?
- **Snelheid:** Genereer barcodes van hoge kwaliteit in milliseconden.  
- **Betrouwbaarheid:** Ingebouwde naleving van ISO/IEC‑normen.  
- **Flexibiliteit:** Volledige controle over grootte, kleur, marges en **barcode‑tekst**‑plaatsing.  
- **Cross‑platform:** Werkt in elke JVM‑gebaseerde omgeving, van desktop‑apps tot cloud‑services.

## Wat is een Data Matrix barcode?
Een Data Matrix barcode is een tweedimensionaal (2‑D) symbool dat **grote hoeveelheden data** opslaat in een compact vierkant of rechthoekig patroon. Het wordt veel gebruikt voor het markeren van kleine items, elektronica en medische apparaten omdat het tot 2.335 alfanumerieke tekens kan coderen.

## Waarom de barcode‑tekstlocatie instellen?
Het plaatsen van de mens‑leesbare tekst **boven**, **onder** of **naast** de barcode helpt gebruikers snel de gecodeerde data te verifiëren zonder te scannen. Het aanpassen van de tekstlocatie verbetert de UI‑consistentie, voldoet aan merkrichtlijnen en kan fouten bij handmatige gegevensinvoer verminderen.

## Voorvereisten

- Basiskennis van Java‑programmeren.  
- Java Development Kit (JDK) geïnstalleerd.  
- Een IDE zoals Eclipse of IntelliJ IDEA.  
- Aspose.BarCode for Java library (download deze van [here](https://releases.aspose.com/barcode/java/)).  

## Pakketten importeren

Importeer eerst de essentiële Aspose.BarCode‑klassen in je project:

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

Deze imports geven je toegang tot de barcode‑generator en de enumeratie die de tekstplaatsing regelt.

## Stapsgewijze handleiding

### Stap 1: Definieer directory‑paden
Geef aan waar je bestanden wilt lezen/schrijven. Vervang de placeholders door de daadwerkelijke paden op jouw machine.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### Stap 2: Maak een BarcodeGenerator‑instantie
Instantieer `BarcodeGenerator` met het **Data Matrix**‑type en geef de code‑tekst op die je wilt coderen.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### Stap 3: Stel barcode‑tekstlocatie in (pas barcode‑tekst aan)
Gebruik de `CodeLocation`‑enumeratie om de mens‑leesbare tekst te verplaatsen. In dit voorbeeld plaatsen we deze **boven** de barcode.

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

> **Pro tip:** Om de tekst **onder** het symbool te plaatsen, wijzig je simpelweg `CodeLocation.ABOVE` in `CodeLocation.BELOW`.

### Stap 4: Sla de gegenereerde barcode‑afbeelding op
Schrijf tenslotte de barcode‑afbeelding naar schijf. Het bestand bevat het Data Matrix‑symbool met de tekst boven het symbool gepositioneerd.

```java
generator.save(dataDir + "codetextAbove.png");
```

## Veelvoorkomende problemen en oplossingen
- **Tekst verschijnt niet:** Zorg ervoor dat je een versie van Aspose.BarCode gebruikt die `CodeLocation` ondersteunt.  
- **Bestandspad‑fouten:** Controleer of `dataDir` eindigt op een bestandsscheidingsteken (`/` of `\\`) dat geschikt is voor jouw OS.  
- **Niet‑ondersteunde tekens:** Data Matrix kan slechts een beperkt aantal tekens coderen; vermijd speciale symbolen die niet in de ISO/IEC 16022‑standaard staan.  

## Veelgestelde vragen (FAQ)

### Q: Kan ik het uiterlijk van de gegenereerde barcode aanpassen?
A: Ja, Aspose.BarCode biedt uitgebreide aanpassingsopties, zodat je kleuren, marges en lettertype‑stijlen kunt regelen.

### Q: Is Aspose.BarCode compatibel met Java 8 en latere versies?
A: Absoluut, de bibliotheek werkt met Java 8 en alle daaropvolgende releases.

### Q: Hoe kan ik Aspose.BarCode integreren in mijn bestaande Java‑project?
A: Voeg de Aspose.BarCode‑JAR‑bestanden toe aan de classpath van je project, importeer de benodigde pakketten, en je bent klaar om barcodes te genereren.

### Q: Is er een proefversie beschikbaar voor Aspose.BarCode?
A: Ja, je kunt de mogelijkheden van Aspose.BarCode verkennen door een gratis proefversie te verkrijgen [here](https://releases.aspose.com/).

### Q: Waar kan ik hulp of ondersteuning krijgen voor Aspose.BarCode?
A: Bezoek het [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) voor community‑ondersteuning en officiële hulp.

## Aanvullende veelgestelde vragen

**Q: Kan ik een barcode genereren met tekst onder het symbool?**  
A: Ja, stel `CodeLocation.BELOW` in in dezelfde `setLocation`‑methode.

**Q: Ondersteunt de bibliotheek andere 2‑D‑barcodes zoals QR‑Code?**  
A: Absoluut, wijzig simpelweg `EncodeTypes.DATA_MATRIX` in `EncodeTypes.QR`.

**Q: Hoe wijzig ik de lettergrootte van de barcode‑tekst?**  
A: Gebruik `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)`.

## Conclusie

Je hebt nu geleerd hoe je een **Data Matrix barcode** kunt **maken** in Java met een **java barcode library** en nauwkeurig de **barcode‑tekstlocatie** kunt instellen met Aspose.BarCode. Experimenteer met andere `CodeLocation`‑waarden, lettertype‑instellingen en kleuropties om te voldoen aan de ontwerpvereisten van jouw applicatie.

---

**Last Updated:** 2026-05-04  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}