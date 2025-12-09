---
date: 2025-11-29
description: Leer hoe u 1D‑barcodes in Java kunt lezen met Aspose.BarCode – decodeer
  barcodes van afbeeldingen snel met een robuuste barcodebibliotheek voor Java.
linktitle: read 1d barcodes java
second_title: Aspose.BarCode Java API
title: Hoe 1D-barcodes lezen in Java met Aspose.BarCode
url: /nl/java/advanced-settings-and-optimization/getting-all-possible-1d-barcodes-image/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 1D-barcodes lezen in Java met Aspose.BarCode

## Inleiding

In deze praktische gids ontdek je hoe je **1D-barcodes in Java** kunt **lezen** met de krachtige **Aspose.BarCode**‑bibliotheek. Of je nu productetiketten, voorraadlabels of een andere lineaire barcode in een afbeelding moet scannen, deze tutorial leidt je stap voor stap – van het opzetten van de omgeving tot het extraheren van elke mogelijke barcode die de afbeelding bevat. Aan het einde kun je **barcodes decoderen uit afbeeldingsbestanden** met slechts een paar regels Java‑code.

## Snelle antwoorden
- **Wat doet Aspose.BarCode?** Het biedt een volledige barcode‑bibliotheek voor Java die 1D/2D‑barcodes kan genereren en decoderen.  
- **Kan ik meerdere barcodes uit één afbeelding lezen?** Ja – de methode `BarCodeReader.readBarCodes()` retourneert alle gedetecteerde symbolen.  
- **Heb ik een licentie nodig voor ontwikkeling?** Een tijdelijke licentie werkt voor testen; een commerciële licentie is vereist voor productie.  
- **Welke Java‑versies worden ondersteund?** Java 8 + (JDK 11 aanbevolen).  
- **Is deze bibliotheek snel genoeg voor realtime scannen?** Absoluut – hij is geoptimaliseerd voor hoge‑prestaties batchverwerking.

## Wat is “read 1d barcodes java”?

Het lezen van 1D-barcodes in Java betekent dat je een **barcode‑bibliotheek voor Java** gebruikt om een afbeelding te analyseren, lineaire barcode‑patronen te lokaliseren en de gecodeerde tekst terug te geven, samen met metadata zoals het symbooltype en de oriëntatie. Aspose.BarCode abstraheert het zware beeldverwerkingswerk, zodat jij je kunt concentreren op de bedrijfslogica.

## Waarom Aspose.BarCode kiezen voor het decoderen van barcodes uit afbeelding?

- **Brede symboolondersteuning** – meer dan 50 1D‑ en 2D‑typen.  
- **Nauwkeurige detectie** – werkt zelfs bij lage contrasten of geroteerde barcodes.  
- **Eenvoudige API** – een paar methode‑aanroepen leveren alle resultaten.  
- **Geen externe afhankelijkheden** – pure Java, eenvoudig in te sluiten in elk project.  

## Voorvereisten

Voordat we in de code duiken, zorg dat je het volgende hebt:

- **Java Development Kit (JDK)** – versie 8 of nieuwer. Download deze van de officiële [Oracle JDK‑pagina](https://www.oracle.com/java/technologies/javase-downloads.html).  
- **Aspose.BarCode for Java** – haal de nieuwste JAR op van de [Aspose‑release‑pagina](https://releases.aspose.com/barcode/java/).  

Nu je omgeving klaar is, laten we beginnen met coderen.

## Import Namespaces

Voeg de benodigde `import`‑statements toe zodat de compiler de klassen van Aspose kan vinden.

```java
import java.awt.Point;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## Stap 1: Initialiseer het BarCodeReader‑object

Maak een `BarCodeReader`‑instantie die naar je afbeeldingsbestand wijst. De parameter `DecodeType` vertelt de engine welke symbologieën gezocht moeten worden; het gebruik van `CODE_128` als voorbeeld werkt voor veel voorkomende 1D‑codes.

```java
BarCodeReader reader = new BarCodeReader("path/to/your/image.png", DecodeType.CODE_128);
```

> **Pro tip:** Als je *alle* ondersteunde 1D‑typen wilt scannen, geef dan `DecodeType.ALL_1D` door in plaats van een enkele symbologie.

## Stap 2: Lees alle mogelijke barcodes

Itereer door de collectie die wordt geretourneerd door `readBarCodes()`. Voor elke `BarCodeResult` printen we de gedecodeerde tekst, de symbologie‑naam, de detectie‑hoek en de vier hoekcoördinaten van het barcode‑gebied.

```java
int iCount = 0;
for (BarCodeResult result : reader.readBarCodes()) {
    // Display code text, symbology, detected angle, recognition percentage of the barcode
    System.out.println("Code Text: " + result.getCodeText() + " Symbology: " + result.getCodeTypeName()
            + " Recognition percentage: " + result.getRegion().getAngle());

    // Display x and y coordinates of barcode detected
    Point[] point = result.getRegion().getPoints();

    System.out.println("Top left coordinates: X = " + point[0].getX() + ", Y = " + point[0].getY());
    System.out.println("Bottom left coordinates: X = " + point[1].getX() + ", Y = " + point[1].getY());
    System.out.println("Bottom right coordinates: X = " + point[2].getX() + ", Y = " + point[2].getY());
    System.out.println("Top right coordinates: X = " + point[3].getX() + ", Y = " + point[3].getY());

    iCount = iCount + 1;
}
```

De lus verwerkt automatisch elke gevonden barcode, dus je hoeft de reader niet herhaaldelijk aan te roepen. Na afloop van de lus bevat `iCount` het totale aantal gedetecteerde barcodes.

## Veelvoorkomende problemen & oplossingen

| Symptoom | Waarschijnlijke oorzaak | Oplossing |
|----------|--------------------------|-----------|
| Geen barcodes geretourneerd | Afbeelding te onscherp of laag contrast | Pre‑process de afbeelding (verhoog contrast, binariseer) voordat je deze aan de reader geeft. |
| Verkeerde symbologie gerapporteerd | Onjuiste `DecodeType` gebruikt | Gebruik `DecodeType.ALL_1D` zodat de engine elke 1D‑type automatisch detecteert. |
| Hoekwaarden onjuist | Afbeelding geroteerd | De API retourneert al de rotatie‑hoek; je kunt de afbeelding indien nodig terugdraaien. |

## Veelgestelde vragen

**V: Is Aspose.BarCode for Java geschikt voor commerciële projecten?**  
A: Ja. Een commerciële licentie verwijdert alle evaluatiebeperkingen en geeft je volledige distributierechten.

**V: Kan ik de bibliotheek testen zonder een licentie aan te schaffen?**  
A: Absoluut. Verkrijg een tijdelijke licentie via de [Aspose‑tijdelijke‑licentie‑pagina](https://purchase.aspose.com/temporary-license/) voor ontwikkeling en testen.

**V: Waar vind ik de volledige API‑referentie?**  
A: De uitgebreide documentatie is beschikbaar [hier](https://reference.aspose.com/barcode/java/).

**V: Hoe krijg ik hulp als ik tegen een probleem aanloop?**  
A: Plaats je vraag op het [Aspose.BarCode‑forum](https://forum.aspose.com/c/barcode/13) waar de community en Aspose‑engineers je kunnen assisteren.

**V: Is er een gratis proefversie beschikbaar?**  
A: Ja – je kunt een proefversie downloaden vanaf de [Aspose‑releases‑pagina](https://releases.aspose.com/).

## Conclusie

Je hebt nu geleerd hoe je **1D-barcodes in Java** kunt **lezen** met Aspose.BarCode, een robuuste **barcode‑bibliotheek voor Java** die het decoderen van barcodes uit afbeeldingsbestanden eenvoudig en betrouwbaar maakt. Integreer dit fragment in je eigen toepassingen om voorraad‑scans, ticketvalidatie of elke situatie waarbij lineaire barcodes in afbeeldingen voorkomen te automatiseren.

---

**Laatst bijgewerkt:** 2025-11-29  
**Getest met:** Aspose.BarCode 24.11 for Java  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}