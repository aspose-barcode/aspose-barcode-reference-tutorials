---
date: 2025-12-25
description: Leer hoe je tekst uit barcode‑afbeeldingen kunt extraheren, specifiek
  PDF417 met Chinese tekens, met Aspose.BarCode voor Java. Volg onze stapsgewijze
  handleiding om barcode‑gegevens efficiënt te lezen.
linktitle: 'Extract Text from Barcode: PDF417 Chinese Characters'
second_title: Aspose.BarCode Java API
title: 'Tekst extraheren uit barcode: PDF417 Chinese karakters in Java'
url: /nl/java/multilingual-support/recognizing-pdf417-chinese-characters/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tekst extraheren uit barcode: PDF417 Chinese tekens in Java

## Introductie

Het integreren van barcode‑herkenning in Java‑toepassingen is een waardevolle vaardigheid, vooral wanneer je **tekst uit een barcode** moet extraheren uit afbeeldingen met meertalige gegevens. In deze tutorial laten we je zien hoe je Aspose.BarCode for Java gebruikt om PDF417‑barcodes met Chinese tekens te herkennen. Aan het einde weet je precies hoe je barcode‑gegevens kunt lezen en decoderen naar leesbare tekst.

## Snelle antwoorden
- **Welke bibliotheek ondersteunt PDF417 met Chinese tekens?** Aspose.BarCode for Java.  
- **Welke tekenset is nodig voor Chinese decodering?** MS936 (GBK).  
- **Heb ik een licentie nodig voor productiegebruik?** Ja, een commerciële licentie is vereist.  
- **Kan ik dit op elke Java‑versie draaien?** Het werkt met Java 8 en nieuwer.  
- **Is er een gratis proefversie beschikbaar?** Absoluut – download deze van de site van Aspose.

## Wat is “tekst extraheren uit barcode”?

Tekst extraheren uit een barcode betekent het omzetten van de gecodeerde gegevens terug naar de oorspronkelijke menselijk leesbare vorm. Voor PDF417‑barcodes die Chinese tekens opslaan, houdt dit ook in dat je de juiste tekencodering moet selecteren zodat de bytes naar de juiste glyphs worden gemapt.

## Waarom Aspose.BarCode for Java gebruiken?

Aspose.BarCode biedt robuuste ondersteuning voor een breed scala aan barcode‑symbologieën, inclusief PDF417, en verwerkt complexe tekensets direct. Het abstraheert beeldverwerking op laag niveau, zodat je je kunt concentreren op de bedrijfslogica in plaats van op decodeerintriciteiten.

## Vereisten

1. **Java Development Kit (JDK)** – de nieuwste versie wordt aanbevolen.  
2. **Aspose.BarCode for Java** – download deze van [hier](https://releases.aspose.com/barcode/java/).  
3. **Een PDF417‑barcode‑afbeelding** die Chinese tekens bevat (bijv. `barcode.png`).

## Pakketten importeren

Importeer in je Java‑project de benodigde klassen om met Aspose.BarCode te werken:

```java
import java.nio.ByteBuffer;
import java.nio.charset.Charset;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## Stap 1: Stel de documentmap in

Geef de map op waar je barcode‑afbeelding zich bevindt:

```java
String dataDir = "Your Document Directory";
```

Vervang `"Your Document Directory"` door het daadwerkelijke pad op jouw machine.

## Stap 2: Laad de barcode‑afbeelding

Maak een `BarCodeReader`‑instance die naar het PNG‑bestand wijst en de lezer instrueert om te zoeken naar PDF417‑symbologie:

```java
BarCodeReader reader = new BarCodeReader(dataDir + "barcode.png", DecodeType.PDF_417);
```

## Stap 3: Lees de barcode

Itereer door de detectieresultaten, haal de ruwe byte‑array op en decodeer deze met de GBK (MS936) tekenset:

```java
for (BarCodeResult result : reader.readBarCodes()) {
    byte[] bytes = result.getCodeBytes();
    ByteBuffer bytebuf = ByteBuffer.wrap(bytes);
    System.out.println(Charset.forName("MS936").decode(bytebuf).toString());
}
```

Deze lus **extrahert tekst uit de barcode** en print de gedecodeerde Chinese tekens naar de console.

## Hoe lees je een barcode met PDF417?

De bovenstaande code demonstreert stap voor stap **hoe je barcode‑gegevens** leest:

1. **Initialiseer** de lezer met het juiste `DecodeType`.  
2. **Itereer** over elk teruggegeven `BarCodeResult`.  
3. **Converteer** de ruwe bytes met de juiste charset (`MS936` voor Chinees).  

Als je barcode andere talen bevat, schakel dan eenvoudig de charset naar die van je gegevens.

## Veelvoorkomende problemen & oplossingen

| Probleem | Oplossing |
|----------|-----------|
| Vervormde tekens na decodering | Controleer of je de juiste charset gebruikt (`MS936` voor GBK). |
| Geen barcode gedetecteerd | Zorg dat de beeldkwaliteit hoog is en de barcode niet gedraaid is; je kunt het beeld indien nodig voorbewerken. |
| Meerdere resultaten geretourneerd | PDF417 kan meerdere segmenten opslaan; itereer door alle resultaten zoals getoond. |

## Veelgestelde vragen (FAQ's)

### Kan ik Aspose.BarCode for Java gebruiken in commerciële projecten?
Ja, je kunt Aspose.BarCode for Java gebruiken in commerciële projecten. Voor licentie‑details, bezoek [hier](https://purchase.aspose.com/buy).

### Is er een gratis proefversie beschikbaar?
Ja, je kunt een gratis proefversie van Aspose.BarCode for Java krijgen [hier](https://releases.aspose.com/).

### Hoe kan ik ondersteuning krijgen voor Aspose.BarCode?
Bezoek het Aspose.BarCode‑forum [hier](https://forum.aspose.com/c/barcode/13) voor ondersteuning of vragen.

### Kan ik een tijdelijke licentie verkrijgen voor testdoeleinden?
Ja, je kunt een tijdelijke licentie krijgen [hier](https://purchase.aspose.com/temporary-license/).

### Waar kan ik de documentatie vinden?
De documentatie is beschikbaar [hier](https://reference.aspose.com/barcode/java/).

**Aanvullende Vragen & Antwoorden**

**V: Wat als mijn barcode‑afbeelding in JPEG‑formaat is?**  
**A:** De `BarCodeReader` werkt met JPEG, PNG, BMP en andere gangbare beeldformaten — wijzig gewoon de bestandsextensie overeenkomstig.

**V: Kan ik barcodes decoderen vanuit een stream in plaats van een bestand?**  
**A:** Ja, je kunt een `InputStream` doorgeven aan de `BarCodeReader`‑constructor voor decodering on‑the‑fly.

**V: Ondersteunt Aspose.BarCode andere tekensets?**  
**A:** Absoluut. Gebruik `Charset.forName("<your‑charset>")` om bytes te decoderen voor UTF‑8, ISO‑8859‑1, enz.

## Conclusie

Je hebt nu geleerd hoe je **tekst uit barcode‑afbeeldingen** kunt extraheren, specifiek PDF417‑barcodes met Chinese tekens, met behulp van Aspose.BarCode for Java. Deze mogelijkheid opent de deur naar meertalige voorraadsystemen, documentautomatisering en meer. Voel je vrij om met andere symbologieën en tekensets te experimenteren om het bereik van je applicatie te vergroten.

---

**Last Updated:** 2025-12-25  
**Tested With:** Aspose.BarCode for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}