---
category: general
date: 2026-10-18
description: Skapa en databar expanded‑streckkod i Java med Aspose.BarCode. Lär dig
  hur du genererar databar, ställer in rader och exporterar streckkodsbilden som PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar expanded barcode
- how to generate databar
- barcode generator rows
- export barcode image
language: sv
lastmod: 2026-10-18
og_description: Skapa databar expanded‑streckkod i Java. Följ den här guiden för att
  lära dig hur du genererar databar, konfigurerar rader och exporterar streckkodsbild
  som PNG.
og_image_alt: Screenshot of a Databar Expanded barcode saved as PNG
og_title: Skapa databar expanded‑streckkod i Java – steg‑för‑steg‑handledning
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Create databar expanded barcode in Java with Aspose.BarCode. Learn
    how to generate databar, set rows, and export barcode image as PNG.
  headline: Create databar expanded barcode in Java – full guide
  type: TechArticle
tags:
- barcode
- Java
- Aspose
title: Skapa Databar Expanded-streckkod i Java – fullständig guide
url: /sv/python-java/general/create-databar-expanded-barcode-in-java-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa databar expanded barcode i Java – fullständig guide

Om du behöver **skapa databar expanded barcode** i Java, visar den här handledningen exakt **hur du genererar databar**-bilder med hjälp av Aspose.BarCode-biblioteket. Du kommer också att lära dig hur du konfigurerar **barcode generator rows** och **export barcode image**-filer i PNG-format.

I avsnitten nedan hittar du ett komplett, körbart program, steg‑för‑steg‑förklaringar av varje API‑anrop och tips för att hantera vanliga kantfall såsom ej stödda tecken eller anpassade layoutstorlekar. I slutet av den här guiden kommer du att kunna skapa både 4‑kolumns- och 3‑raders Databar Expanded‑streckkoder och spara dem där du behöver.

## Förutsättningar

* Java 17 eller senare (koden kompileras med vilken JDK 11+ som helst)
* Maven eller Gradle för att hantera beroenden
* Aspose.BarCode för Java – lägg till den senaste versionen i din `pom.xml` eller `build.gradle`
* Grundläggande kunskap om Javas `main`‑metod och objekt‑orienterade koncept

```xml
<!-- Maven dependency -->
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-barcode</artifactId>
    <version>23.10</version>
</dependency>
```

> **Proffstips:** Den kostnadsfria evalueringslicensen fungerar för utveckling; ersätt den med en köpt licens innan du distribuerar till produktion.

## Skapa databar expanded barcode – initial konfiguration

Det första steget är att instansiera en `BarcodeGenerator` med typen `EncodeTypes.DatabarExpandedStacked` och en exempel‑payload. Denna payload kan vara vilken alfanumerisk sträng som helst som passar Databar‑specifikationen.

```java
import com.aspose.barcode.*;
import com.aspose.barcode.barcodeimageformat.*;
import com.aspose.barcode.encode.*;

public class DatabarExpandedDemo {

    public static void main(String[] args) throws Exception {
        // Step 1: Create a barcode generator for Databar Expanded Stacked with sample text
        BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
```

*Varför detta är viktigt*: `EncodeTypes.DatabarExpandedStacked` talar om för biblioteket att använda Databar Expanded Stacked‑symbologi, vilket stödjer längre datasträngar än den vanliga Databar.

## Så genererar du databar med anpassade kolumner

Databar Expanded låter dig kontrollera antalet kolumner i den staplade layouten. Att ange kolumner är användbart när du behöver en kompakt streckkod som ändå får plats med den nödvändiga databredden.

```java
        // Step 2: Configure a 4‑column layout for the DataBar
        generator.getParameters().getBarcode().getDataBar().setColumns(4);
```

*Förklaring*: `setColumns(4)` tvingar generatorn att dela streckkoden i fyra vertikala sektioner. Biblioteket justerar automatiskt modulbredden för att hålla den totala storleken rimlig.

## Exportera streckkodbild som PNG – 4‑kolumnsversion

När layouten är definierad kan du exportera streckkoden till en fil. PNG är det rekommenderade förlustfria formatet för de flesta UI‑scenarier.

```java
        // Step 3: Save the 4‑column barcode image
        generator.save("output/DatabarExpandedCols4.png", BarCodeImageFormat.Png);
```

`save`‑metoden skriver bilden till den angivna katalogen. Om katalogen inte finns skapar Java den automatiskt.

## Konfigurera barcode generator rows

Förutom kolumner stödjer Databar Expanded Stacked‑symbologi en rad‑baserad layout. Att byta från kolumner till rader kan förbättra läsbarheten på högupplösta utskrifter.

```java
        // Step 4: Create a new generator for the same data (demonstrates a different layout)
        BarcodeGenerator rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

        // Step 5: Configure a 3‑row layout for the DataBar
        rowGenerator.getParameters().getBarcode().getDataBar().setRows(3);
```

*Varför använda rader?* En 3‑radslayout sprider data vertikalt, vilket kan vara fördelaktigt för smala etiketter där horisontellt utrymme är begränsat.

## Exportera streckkodbild som PNG – 3‑radsversion

Att spara den andra layouten följer samma mönster som tidigare. Att hålla filnamnen olika hjälper dig att jämföra de visuella skillnaderna.

```java
        // Step 6: Save the 3‑row barcode image
        rowGenerator.save("output/DatabarExpandedRows3.png", BarCodeImageFormat.Png);
    }
}
```

### Förväntat resultat

När programmet körs genereras två PNG‑filer:

| Filnamn                     | Layoutbeskrivning                |
|------------------------------|-----------------------------------|
| `DatabarExpandedCols4.png`   | 4‑kolumn staplad streckkod           |
| `DatabarExpandedRows3.png`   | 3‑rad staplad streckkod              |

Båda bilderna visar samma kodade sträng, men den visuella densiteten skiljer sig beroende på kolumn‑/radinställningarna.

## Vanliga fallgropar och hur du undviker dem

| Problem                               | Orsak                                   | Lösning |
|--------------------------------------|------------------------------------------|-----|
| Streckkoden blir suddig               | Sparas med låg DPI                       | Använd `generator.getParameters().setResolution(300)` före `save`. |
| Texten trunkeras                      | Payload överskrider Databar‑kapaciteten  | Minska payloaden eller byt till `EncodeTypes.DatabarExpanded` (icke‑staplad). |
| `NullPointerException` on `setRows`  | Använder en version av Aspose.BarCode före 20.12 | Uppgradera till den senaste biblioteksversionen. |

## Avancerade varianter (valfritt)

* **Ändra förgrunds-/bakgrundsfärger** – anropa `generator.getParameters().getBarcode().setForeColor(Color.BLUE)` och `setBackColor(Color.WHITE)`.
* **Generera SVG istället för PNG** – ersätt `BarCodeImageFormat.Png` med `BarCodeImageFormat.Svg`.
* **Bädda in streckkoden i en PDF** – använd Aspose.PDF för att skapa ett dokument och lägg till PNG‑filen som en bild.

## Slutsats

Du vet nu hur du **skapar databar expanded barcode** i Java, **genererar databar** med både kolumn‑ och radkonfigurationer, och hur du **exporterar streckkodbild**‑filer i PNG‑format. Den kompletta källkoden är klar att kopiera, klistra in och köra i vilket Java‑projekt som helst.

Känn dig fri att experimentera med andra layouter, färger eller utdataformat. Om du fann den här guiden hjälpsam, överväg att utforska Aspose.BarCode-dokumentationen för ämnen som *micro‑PDF417*, *QR‑kod felkorrigering* och *streckkodsskanning*.

Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar streckkod java: Skapa en exakt streckkodbild](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)
- [databar expanded stacked streckkodsguide – hur man genererar och dimensionerar den i C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Hur man skapar omnidirektionell Databar-streckkod i C#](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}