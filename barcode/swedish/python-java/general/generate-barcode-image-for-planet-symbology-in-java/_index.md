---
category: general
date: 2026-10-18
description: Generera streckkodsbild för Planet‑symbologi med Java. Lär dig att skapa
  planetstreckkod med anpassade streckkodsdimensioner och tomma staplar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- create planet barcode
- custom barcode dimensions
language: sv
lastmod: 2026-10-18
og_description: Generera streckkodbild för Planet‑symbologi i Java. Denna handledning
  visar hur man skapar en planetstreckkod med anpassade streckkodsdimensioner och
  konturstaplar.
og_image_alt: Generated barcode image showing a Planet barcode with empty outline
  bars
og_title: Skapa streckkodsbild för Planet‑symbologi – Java‑guide
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
title: Generera streckkodsbild för Planet‑symbologi i Java
url: /sv/python-java/general/generate-barcode-image-for-planet-symbology-in-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera streckkodbild för Planet‑symbolik i Java

Om du behöver **generera streckkodbild** för Planet‑symboliken, guidar den här handledningen dig genom hela processen. Oavsett om du bygger ett postautomatiseringssystem eller en anpassad spårningslösning, kommer du att lära dig hur du **skapar planet‑streckkod** med **anpassade streckkodsdimensioner** och kontur‑ (tomma) staplar.

Exemplet använder Aspose.BarCode för Java‑biblioteket, som erbjuder ett flytande API för varje större streckkodstandard. Inga extra bildbehandlingsverktyg behövs, och koden körs på vilken Java 8+‑runtime som helst.

## Förutsättningar

Innan du börjar, se till att du har:

* Java 8 eller nyare installerat (handledningen testades med JDK 17).
* Maven eller Gradle för att hantera beroenden.
* Grundläggande kunskap om Java‑syntax och konceptet streckkod.

Om du är ny på Maven kan du skapa ett enkelt projekt med `mvn archetype:generate` och lägga till Aspose.BarCode‑beroendet som visas nedan.

## Lägg till Aspose.BarCode‑beroendet

```xml
<!-- pom.xml -->
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-barcode</artifactId>
    <version>23.12</version> <!-- Use the latest version available -->
</dependency>
```

> **Proffstips:** Lås versionsnumret för att undvika oväntade brytande förändringar när biblioteket uppdateras.

## Steg 1: Initiera streckkodsgeneratorn för Planet‑symbolik

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

**Varför detta steg är viktigt:**  
`EncodeTypes.PLANET` talar om för biblioteket att använda Planet‑streckkodsspecifikationen, som ofta används av posttjänster. Sträng‑data `"123456"` är den nyttolast som kommer att visas i den genererade bilden.

## Steg 2: Ange anpassade streckkodsdimensioner (X‑dimension)

```java
        // Step 2 – adjust the X dimension (module width) to 4 pixels.
        // This controls the thickness of each bar.
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .getXDimension()
                        .setPixels(4);
```

**Varför detta steg är viktigt:**  
*X‑dimensionen* definierar hur bred varje enskild stapel är. Genom att sätta den till **4 pixlar** får du en streckkod som är lättläst för de flesta skannrar samtidigt som den passar på en standardetikett. Att ändra detta värde är det primära sättet att uppnå **anpassade streckkodsdimensioner**.

## Steg 3: Använd tomma (kontur) staplar istället för solida staplar

```java
        // Step 3 – configure the generator to draw empty bars (outline only)
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .setFilledBars(false);
```

**Varför detta steg är viktigt:**  
`setFilledBars(false)` instruerar renderaren att bara rita stapelkonturerna och lämna insidan transparent. Denna stil krävs ofta för poststreckkoder där bakgrunden kan innehålla annan tryckt information.

## Steg 4: Spara streckkodsbilder som PNG

```java
        // Step 4 – save the generated barcode as a PNG file
        String outputPath = "output/PlanetEmptyBars.png";
        barcodeGenerator.save(outputPath, BarCodeImageFormat.Png);

        System.out.println("Barcode image generated at: " + outputPath);
    }
}
```

**Varför detta steg är viktigt:**  
Att välja `BarCodeImageFormat.Png` ger dig en förlustfri bild som bevarar de skarpa kanterna på konturstaplarna. Filsökvägen kan vara vilken katalog du har skrivbehörighet till; exemplet använder en `output`‑mapp relativt projektroten.

### Förväntad utdata

När programmet körs skapas en fil som liknar bilden nedan:

![Genererad streckkodbild för Planet‑symbolik](/images/planet-barcode.png){.align-center alt="Genererad streckkodbild som visar en Planet‑streckkod med tomma konturstaplar"}

Bilden visar en **Planet‑streckkod** med tunna, tomma staplar, exakt enligt de anpassade dimensioner du angav.

## Vanliga variationer och kantfall

| Situation | Anpassning |
|-----------|------------|
| **Olika datalängd** | Planet‑streckkoder stödjer upp till 12 numeriska tecken. Ändra det andra konstruktörsargumentet därefter. |
| **Högre upplösning** | Öka X‑dimensionen (`setPixels`) eller sätt `YDimension` för att kontrollera stapelhöjden. |
| **Färgad streckkod** | Använd `barcodeGenerator.getParameters().getImageOptions().setForeColor(Color.BLUE);` för att ändra stapelfärgen. |
| **Spara som SVG** | Byt ut `BarCodeImageFormat.Png` mot `BarCodeImageFormat.Svg` för en vektorutdata. |
| **Kör på Android** | Använd den Android‑kompatibla Aspose.BarCode för Android och ersätt filsökvägar med `Context.getFilesDir()`. |

> **Se upp för:** Att sätta X‑dimensionen för lågt (t.ex. 1 pixel) kan göra streckkoden oläslig på lågupplösta skrivare. Testa alltid med en riktig skanner efter att du ändrat dimensioner.

## Fullständig källkod för snabb kopiering

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

Kopiera koden till en fil med namnet `PlanetBarcodeDemo.java`, placera den under `src/main/java/com/example/barcode/`, kör `mvn compile exec:java`, och du kommer att se **generera streckkodbild**‑resultatet i `output`‑mappen.

## Slutsats

Du vet nu hur du **genererar streckkodbild** för Planet‑symboliken i Java, hur du **skapar planet‑streckkod** med **anpassade streckkodsdimensioner**, och hur du byter från solida till tomma staplar för en renare visuell stil. Det kompletta exemplet demonstrerar varje nödvändigt API‑anrop, från initiering av generatorn till sparande av en PNG‑fil.

**Nästa steg** – utforska andra streckkodstyper (`EncodeTypes.CODE_128`, `EncodeTypes.QR`) och experimentera med ytterligare bildalternativ såsom bakgrundsfärg, marginaler och DPI‑inställningar. Om du behöver bädda in streckkoden i en PDF, kombinera denna kod med Aspose.PDF för Java för en sömlös end‑to‑end‑lösning.

Lycka till med kodandet!


## Vad bör du lära dig härnäst?


Följande handledningar täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to create planet barcode with filled and empty bars](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [create planet barcode image – Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-image-step-by-step-guide/)
- [How to generate barcode java: Create an Exact Barcode Image](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}