---
category: general
date: 2026-10-18
description: Genereer barcode‑afbeelding voor Planet‑symbologie met Java. Leer hoe
  je een planet‑barcode maakt met aangepaste barcode‑afmetingen en lege staven.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- create planet barcode
- custom barcode dimensions
language: nl
lastmod: 2026-10-18
og_description: Genereer een barcode‑afbeelding voor Planet‑symbologie in Java. Deze
  tutorial laat zien hoe je een planet‑barcode maakt met aangepaste barcode‑afmetingen
  en omtrekstrepen.
og_image_alt: Generated barcode image showing a Planet barcode with empty outline
  bars
og_title: Genereer barcode‑afbeelding voor Planet‑symbologie – Java‑gids
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Generate barcode image for Planet symbology using Java. Learn to create
    planet barcode with custom barcode dimensions and empty bars.
  headline: Generate barcode image for Planet symbology in Java
  type: TechArticle
tags:
- barcode
- Java
- imaging
title: Genereer barcode‑afbeelding voor Planet‑symbologie in Java
url: /nl/python-java/general/generate-barcode-image-for-planet-symbology-in-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode‑afbeelding genereren voor Planet‑symbologie in Java

Als je een **barcode‑afbeelding** voor de Planet‑symbologie moet **genereren**, leidt deze gids je door het volledige proces. Of je nu een postautomatiseringssysteem of een aangepaste traceeroplossing bouwt, je leert hoe je een **planet‑barcode** maakt met **aangepaste barcode‑afmetingen** en omtrek‑ (lege) strepen.

Het voorbeeld maakt gebruik van de Aspose.BarCode for Java‑bibliotheek, die een vloeiende API biedt voor elke belangrijke barcode‑standaard. Er zijn geen extra beeldverwerkingstools nodig, en de code draait op elke Java 8+ runtime.

## Voorvereisten

* Java 8 of nieuwer geïnstalleerd (de tutorial is getest met JDK 17).
* Maven of Gradle om afhankelijkheden te beheren.
* Basiskennis van Java‑syntaxis en het concept van een barcode.

Als je nieuw bent met Maven, kun je een eenvoudig project maken met `mvn archetype:generate` en de Aspose.BarCode‑afhankelijkheid toevoegen zoals hieronder weergegeven.

## Voeg de Aspose.BarCode‑afhankelijkheid toe

```xml
<!-- pom.xml -->
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-barcode</artifactId>
    <version>23.12</version> <!-- Use the latest version available -->
</dependency>
```

> **Pro tip:** Vergrendel het versienummer om onverwachte brekende wijzigingen te voorkomen wanneer de bibliotheek wordt bijgewerkt.

## Stap 1: Initialiseert de barcode‑generator voor Planet‑symbologie

```java
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generator.BarcodeGenerator;

public class PlanetBarcodeDemo {
    public static void main(String[] args) {
        // Step 1 – create a generator that encodes data using the Planet symbology
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.PLANET,          // Planet is the barcode type
                "123456");                   // Data to encode
```

**Waarom deze stap belangrijk is:**  
`EncodeTypes.PLANET` vertelt de bibliotheek om de Planet‑barcode‑specificatie te gebruiken, die vaak wordt toegepast in postdiensten. De gegevensreeks `"123456"` is de payload die in de gegenereerde afbeelding zal verschijnen.

## Stap 2: Stel aangepaste barcode‑afmetingen in (X‑dimensie)

```java
        // Step 2 – adjust the X dimension (module width) to 4 pixels.
        // This controls the thickness of each bar.
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .getXDimension()
                        .setPixels(4);
```

**Waarom deze stap belangrijk is:**  
De *X‑dimensie* bepaalt hoe breed elke individuele staaf is. Door deze in te stellen op **4 pixels**, krijg je een barcode die gemakkelijk leesbaar is voor de meeste scanners en toch op een standaard label past. Het wijzigen van deze waarde is de belangrijkste manier om **aangepaste barcode‑afmetingen** te realiseren.

## Stap 3: Gebruik lege (omtrek‑) strepen in plaats van massieve strepen

```java
        // Step 3 – configure the generator to draw empty bars (outline only)
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .setFilledBars(false);
```

**Waarom deze stap belangrijk is:**  
`setFilledBars(false)` vertelt de renderer om alleen de omtrek van de strepen te tekenen, waarbij het binnenste transparant blijft. Deze stijl is vaak vereist voor post‑barcodes waarbij de achtergrond andere gedrukte informatie kan bevatten.

## Stap 4: Sla de barcode‑afbeelding op als PNG

```java
        // Step 4 – save the generated barcode as a PNG file
        String outputPath = "output/PlanetEmptyBars.png";
        barcodeGenerator.save(outputPath, BarCodeImageFormat.Png);

        System.out.println("Barcode image generated at: " + outputPath);
    }
}
```

**Waarom deze stap belangrijk is:**  
Het kiezen van `BarCodeImageFormat.Png` levert een verliesvrije afbeelding op die de scherpe randen van de omtrekstrepen behoudt. Het bestandspad kan elke map zijn waar je schrijfrechten voor hebt; het voorbeeld gebruikt een `output`‑map relatief ten opzichte van de project‑root.

### Verwachte output

Het uitvoeren van het programma maakt een bestand aan dat lijkt op de afbeelding hieronder:

![Gegenereerde barcode‑afbeelding voor Planet‑symbologie](/images/planet-barcode.png){.align-center alt="Gegenereerde barcode‑afbeelding die een Planet‑barcode met lege omtrekstrepen toont"}

De afbeelding toont een **Planet‑barcode** met dunne, lege strepen, die precies overeenkomen met de aangepaste afmetingen die je hebt ingesteld.

## Veelvoorkomende variaties en randgevallen

| Situatie | Aanpassing |
|-----------|------------|
| **Verschillende datalengte** | Planet‑barcodes ondersteunen tot 12 numerieke tekens. Pas het tweede constructor‑argument dienovereenkomstig aan. |
| **Hogere resolutie** | Verhoog de X‑dimensie (`setPixels`) of stel de `YDimension` in om de balkhoogte te regelen. |
| **Kleur‑barcode** | Gebruik `barcodeGenerator.getParameters().getImageOptions().setForeColor(Color.BLUE);` om de kleur van de streep te wijzigen. |
| **Opslaan als SVG** | Vervang `BarCodeImageFormat.Png` door `BarCodeImageFormat.Svg` voor een vector‑output. |
| **Uitvoeren op Android** | Gebruik de Android‑compatibele Aspose.BarCode voor Android en vervang bestandssysteempaden door `Context.getFilesDir()`. |

> **Let op:** Het instellen van de X‑dimensie te laag (bijv. 1 pixel) kan de barcode onleesbaar maken op printers met lage resolutie. Test altijd met een echte scanner na het wijzigen van de afmetingen.

## Volledige broncode voor snelle copy‑paste

```java
package com.example.barcode;

import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generator.BarcodeGenerator;

public class PlanetBarcodeDemo {
    public static void main(String[] args) {
        // Create the generator for Planet barcode with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.PLANET,
                "123456");

        // Custom X dimension – 4 pixels per module
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .getXDimension()
                        .setPixels(4);

        // Use outline (empty) bars
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .setFilledBars(false);

        // Save as PNG
        String outputPath = "output/PlanetEmptyBars.png";
        barcodeGenerator.save(outputPath, BarCodeImageFormat.Png);

        System.out.println("Barcode image generated at: " + outputPath);
    }
}
```

Kopieer de code naar een bestand genaamd `PlanetBarcodeDemo.java`, plaats het onder `src/main/java/com/example/barcode/`, voer `mvn compile exec:java` uit, en je ziet het resultaat van het **genereren van een barcode‑afbeelding** in de `output`‑map.

## Conclusie

Je weet nu hoe je een **barcode‑afbeelding** voor de Planet‑symbologie in Java kunt **genereren**, hoe je een **planet‑barcode** maakt met **aangepaste barcode‑afmetingen**, en hoe je van massieve naar lege strepen kunt schakelen voor een nettere visuele stijl. Het volledige voorbeeld toont elke benodigde API‑aanroep, van het initialiseren van de generator tot het opslaan van een PNG‑bestand.

**Volgende stappen** – verken andere barcode‑typen (`EncodeTypes.CODE_128`, `EncodeTypes.QR`) en experimenteer met extra afbeelding‑opties zoals achtergrondkleur, marges en DPI‑instellingen. Als je de barcode in een PDF moet insluiten, combineer deze code dan met Aspose.PDF for Java voor een naadloze end‑to‑end‑oplossing.

Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe maak je een planet‑barcode met gevulde en lege strepen](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [planet‑barcode afbeelding maken – Stapsgewijze gids](/barcode/english/python-java/general/create-planet-barcode-image-step-by-step-guide/)
- [Hoe barcode genereren in Java: Een exacte barcode‑afbeelding maken](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}