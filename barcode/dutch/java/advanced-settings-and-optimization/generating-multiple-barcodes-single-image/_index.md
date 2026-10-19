---
date: 2026-10-19
description: Leer hoe u QR code java maakt en meerdere barcodes op één afbeelding
  genereert met Aspose.BarCode for Java. Inclusief installatie, code en probleemoplossing.
keywords:
- create qr code java
- how to create qr
- java barcode library
- generate multiple barcodes
- aspose trial license
lastmod: 2026-10-19
linktitle: Meerdere barcodes genereren op één afbeelding
og_description: Maak QR code java en combineer verschillende barcode‑typen tot één
  afbeelding met Aspose.BarCode for Java. Volg de stapsgewijze handleiding, bekijk
  code‑fragmenten en leer tips voor probleemoplossing.
og_image_alt: Screenshot of a Java application generating a QR code and other barcodes
  on one combined image
og_title: QR code java maken – genereer meerdere barcodes op één afbeelding
schemas:
- author: Aspose
  dateModified: '2026-10-19'
  description: Learn how to create QR code java and generate multiple barcodes on
    a single image using Aspose.BarCode for Java. Includes setup, code, and troubleshooting.
  headline: Create QR code java – generate multiple barcodes on one image
  type: TechArticle
- questions:
  - answer: Yes. Use the `BarcodeGenerator` properties such as `setBarColor`, `setBackgroundColor`,
      and `setXDimension` to style each barcode independently before adding it to
      the canvas.
    question: Can I customize the appearance of individual barcodes in the generated
      image?
  - answer: Absolutely. The library supports 50+ symbologies, including CODE_39, DATA_MATRIX,
      QR, CODE_128, EAN_13, and AZTEC, as demonstrated in this tutorial.
    question: Is Aspose.BarCode compatible with different barcode symbologies?
  - answer: Download the JAR from the Aspose.BarCode for Java library download page,
      add it to your project’s classpath, and import the required namespaces as shown
      in the “Import namespaces” section.
    question: How do I integrate Aspose.BarCode into my Java project?
  - answer: Yes. Purchase a license from the Aspose.BarCode license purchase page
      to remove trial limitations and obtain full production support.
    question: Can I use Aspose.BarCode for commercial applications?
  - answer: Certainly. A free trial license is available from the Aspose.BarCode free
      trial download page, giving you full API access for evaluation.
    question: Are there trial options available for Aspose.BarCode?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- create qr code
- aspose barcode
- java barcode generation
- multiple barcodes image
title: QR code java maken – genereer meerdere barcodes op één afbeelding
url: /nl/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# QR-code java maken – meerdere barcodes op één afbeelding genereren

## Inleiding

In deze tutorial leer je **how to create QR code java** en combineer je verschillende barcode‑typen op één canvas met behulp van **Aspose.BarCode for Java**. Of je nu een compact QR‑label, een productbarcode of een mix van 2‑D‑ en lineaire symbologieën nodig hebt, deze gids leidt je stap voor stap—van projectconfiguratie tot het opslaan van de uiteindelijke gecombineerde afbeelding—zodat je direct barcode‑generatie in je Java‑applicaties kunt integreren.

## Snelle antwoorden
- **Welke bibliotheek moet ik gebruiken?** Aspose.BarCode for Java provides the most complete set of symbologies.  
- **Kan ik verschillende barcode‑typen samen genereren?** Yes, you can mix CODE_39, QR, AZTEC, and more on a single canvas.  
- **Heb ik een licentie nodig voor ontwikkeling?** A free trial works for testing; a commercial license is required for production.  
- **Welke Java‑versie wordt ondersteund?** Java 8 and newer are fully compatible.  
- **Is het uitvoerformaat configureerbaar?** You can export the combined image as PNG, JPEG, BMP, or TIFF.

## Wat is create QR code java?

`create QR code java` verwijst naar het proces waarbij een tekststring wordt omgezet in een tweedimensionale matrix die kan worden gescand door smartphones of barcode‑lezers. Aspose.BarCode for Java voert de codering en weergave uit, zodat je je kunt concentreren op de businesslogica in plaats van op pixel‑niveau beeldverwerking.

## Waarom Aspose.BarCode Java gebruiken voor generate barcodes java?

Aspose.BarCode ondersteunt **meer dan 50 barcode‑symbologieën**—inclusief QR, Data Matrix, Code 128, AZTEC en traditionele lineaire codes—waardoor het de meest veelzijdige Java‑barcode‑bibliotheek is. Het rendert **anti‑aliased afbeeldingen tot 1200 dpi**, wat zorgt voor scherpe scans op scherm en print. De API vereist alleen de JVM en biedt een vloeiend configuratiemodel om grootte, kleur, marges en foutcorrectie aan te passen in slechts een paar regels code.

## Vereisten

- Een solide begrip van de Java‑basisprincipes.  
- JDK 8 of nieuwer geïnstalleerd en geconfigureerd in je PATH.  
- De Aspose.BarCode for Java JAR (download van de officiële Aspose.BarCode for Java downloadpagina).  
- Een IDE zoals IntelliJ IDEA of Eclipse voor het bewerken en uitvoeren van het voorbeeld.  

## Importeren van namespaces

Import‑statements brengen Aspose.BarCode‑klassen zoals `BarcodeGenerator`, `EncodeTypes` en `BarCodeImageFormat` in scope, zodat je ze kunt refereren zonder volledig gekwalificeerde namen.  
`BarcodeGenerator` is de hoofdklasse die wordt gebruikt om barcode‑afbeeldingen te configureren en te genereren.  
`EncodeTypes` is een enum in Aspose.BarCode die de te genereren barcode‑symbologie specificeert.  
`BarCodeImageFormat` definieert het uitvoer‑afbeeldingsformaat voor de gegenereerde barcode.

## Stap 1: stel de resource‑directory in

De **resource‑directory** is de map op je bestandssysteem waarin alle gegenereerde barcode‑afbeeldingen worden weggeschreven. Het één keer definiëren houdt je project georganiseerd en maakt het eenvoudig om oude bestanden op te ruimen.

```java
import java.awt.Color;
import java.awt.Graphics;
import java.awt.image.BufferedImage;
import java.io.File;
import java.util.ArrayList;
import java.util.HashMap;

import javax.imageio.ImageIO;

import com.aspose.barcode.BaseEncodeType;
import com.aspose.barcode.EncodeTypes;


import com.aspose.barcode.generation.BarcodeGenerator;
```

## Stap 2: maak een collectie van barcodes

Een `HashMap<String, EncodeTypes>` slaat de gegevensstring van elke barcode op samen met de symbologie die je wilt gebruiken. `HashMap` is een Java‑collectie die sleutels aan waarden koppelt. Deze collectie stuurt de daaropvolgende generatie‑lus aan. `EncodeTypes` is een enum die aangeeft welk barcode‑type moet worden gegenereerd.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Stap 3: genereer barcode‑afbeeldingen

De generatie‑lus iterereert over de `HashMap`, maakt voor elke invoer een `BarcodeGenerator` aan en roept `generateBarCodeImage()` aan om een `BufferedImage` te verkrijgen. `generateBarCodeImage()` creëert een `BufferedImage` met de gerenderde barcode. `BufferedImage` is een Java‑klasse die een afbeelding in het geheugen vertegenwoordigt. Alle afbeeldingen worden toegevoegd aan een `ArrayList<BufferedImage>` voor later samenvoegen. `ArrayList` is een dynamische lijstimplementatie in Java.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Stap 4: maak een gecombineerde afbeelding

Eerst berekent het algoritme de **maximale breedte** van alle barcode‑afbeeldingen en de **totale hoogte** die nodig is om ze verticaal te stapelen met optionele tussenruimte. Vervolgens maakt het een `BufferedImage` van die grootte en tekent elke barcode op het canvas met behulp van een `Graphics2D`‑object. `Graphics2D` is een Java‑klasse die 2D‑renderingsmogelijkheden biedt voor het tekenen van vormen en afbeeldingen.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Stap 5: sla het resultaat op

Tenslotte wordt de samengestelde afbeelding naar schijf geschreven met `ImageIO.write`, met het door jou opgegeven formaat (PNG, JPEG, BMP of TIFF). `ImageIO.write` schrijft een `BufferedImage` naar een bestand in het gespecificeerde formaat. Het bestandspad is relatief ten opzichte van de eerder gedefinieerde resource‑directory.

```java
int maxWidth = 0;
int sumHeight = 0;
for (BufferedImage bmp : images) {
    sumHeight += bmp.getHeight();
    if (maxWidth < bmp.getWidth())
        maxWidth = bmp.getWidth();
}

int offset = 10;
BufferedImage resultBitmap = new BufferedImage(maxWidth + offset * 2, sumHeight + offset * images.size(),
        BufferedImage.TYPE_INT_ARGB);
Graphics g = resultBitmap.getGraphics();
g.setColor(Color.white);
g.fillRect(0, 0, resultBitmap.getWidth(), resultBitmap.getHeight());

int yPosition = offset;
for (int i = 0; i < images.size(); ++i) {
    BufferedImage currentBitmap = images.get(i);
    g.drawImage(currentBitmap, offset, yPosition, null);
    yPosition += currentBitmap.getHeight() + offset;
}
```

## Veelvoorkomende gebruikssituaties voor het genereren van meerdere barcodes

- **Verpakkingslabels** – combineer product-, batch- en verzendcodes op één label om de printkosten te verlagen.  
- **Evenementtickets** – voeg QR, Data Matrix en Code 128‑identifiers toe voor verschillende scanstations op een locatie.  
- **Voorraadbeheer** – toon SKU, RFID‑taggegevens en serienummers samen voor snelle audit en traceerbaarheid.

## Probleemoplossing & tips

- **Problemen met afbeeldingsgrootte** – pas de `offset`‑variabele aan om de tussenruimte tussen barcodes te vergroten of te verkleinen.  
- **Niet‑ondersteunde symbologie** – controleer of jouw Aspose.BarCode‑versie het gewenste barcode‑type ondersteunt; nieuwere releases voegen extra 2‑D‑codes toe.  
- **Prestaties** – hergebruik één `Graphics2D`‑object bij het genereren van veel afbeeldingen in een lus om de overhead van objectallocatie te minimaliseren.

## Veelgestelde vragen

**Q: Kan ik het uiterlijk van individuele barcodes in de gegenereerde afbeelding aanpassen?**  
A: Ja. Gebruik de `BarcodeGenerator`‑eigenschappen zoals `setBarColor`, `setBackgroundColor` en `setXDimension` om elke barcode afzonderlijk te stylen voordat je deze aan het canvas toevoegt.

**Q: Is Aspose.BarCode compatibel met verschillende barcode‑symbologieën?**  
A: Absoluut. De bibliotheek ondersteunt meer dan 50 symbologieën, waaronder CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 en AZTEC, zoals in deze tutorial wordt getoond.

**Q: Hoe integreer ik Aspose.BarCode in mijn Java‑project?**  
A: Download de JAR van de Aspose.BarCode for Java bibliotheek‑downloadpagina, voeg deze toe aan de classpath van je project, en importeer de benodigde namespaces zoals weergegeven in de sectie “Import namespaces”.

**Q: Mag ik Aspose.BarCode gebruiken voor commerciële toepassingen?**  
A: Ja. Schaf een licentie aan via de Aspose.BarCode licentie‑aankooppagina om proefbeperkingen te verwijderen en volledige productie‑ondersteuning te krijgen.

**Q: Zijn er proefopties beschikbaar voor Aspose.BarCode?**  
A: Zeker. Een gratis proeflicentie is beschikbaar via de Aspose.BarCode gratis‑proef‑downloadpagina, die volledige API‑toegang biedt voor evaluatie.

**Q: Hoe genereer ik een hoge‑resolutie QR‑code voor afdrukken?**  
A: Stel de `setResolutionDpi`‑eigenschap in op de `BarcodeGenerator` voordat je `generateBarCodeImage()` aanroept, en sla vervolgens het resultaat op in een verliesvrij formaat zoals PNG.

**Q: Wat moet ik doen als de gecombineerde afbeelding afgekapt lijkt?**  
A: Controleer of de `offset`‑ en canvas‑grootte‑berekeningen correct rekening houden met alle barcode‑hoogtes; het verhogen van de canvas‑hoogte of het verkleinen van individuele barcode‑groottes lost de meeste afkappingsproblemen op.

---

**Laatst bijgewerkt:** 2026-10-19  
**Getest met:** Aspose.BarCode for Java 24.11  
**Auteur:** Aspose  

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Gerelateerde tutorials

- [Hoe barcode‑afbeelding maken Java – Rand toevoegen met Aspose](/barcode/java/image-manipulation/adding-borders-barcode-image/)
- [Hoe barcode genereren Java: opslaan naar streams met Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/saving-barcode-image-streams/)
- [Hoe barcode genereren Java en barcode afdrukken met Aspose](/barcode/java/barcode-rendering-techniques/rendering-barcode-printer/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}