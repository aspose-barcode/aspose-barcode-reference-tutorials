---
category: general
date: 2026-10-18
description: Vygenerujte obrázek čárového kódu pro planetární symboliku pomocí Javy.
  Naučte se vytvořit planetární čárový kód s vlastními rozměry čárového kódu a prázdnými
  pruhy.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- create planet barcode
- custom barcode dimensions
language: cs
lastmod: 2026-10-18
og_description: Vygenerujte obrázek čárového kódu pro symbologii Planet v Javě. Tento
  tutoriál ukazuje, jak vytvořit planetární čárový kód s vlastními rozměry čárového
  kódu a obrysovými pruhy.
og_image_alt: Generated barcode image showing a Planet barcode with empty outline
  bars
og_title: Vygenerujte obrázek čárového kódu pro planetární symboliku – Java průvodce
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
title: Generovat obrázek čárového kódu pro planetární symboliku v Javě
url: /cs/python-java/general/generate-barcode-image-for-planet-symbology-in-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření obrázku čárového kódu pro Planet symbologii v Javě

Pokud potřebujete **vytvořit obrázek čárového kódu** pro Planet symbologii, tento návod vás provede celým procesem. Ať už budujete poštovní automatizační systém nebo vlastní sledovací řešení, naučíte se **vytvořit Planet čárový kód** s **vlastními rozměry čárového kódu** a obrysy (prázdnými) pruhy.

Příklad používá knihovnu Aspose.BarCode pro Java, která poskytuje fluent API pro každý hlavní standard čárových kódů. Nepotřebujete žádné další nástroje pro zpracování obrázků a kód běží na libovolném runtime Java 8+.

## Požadavky

Než začnete, ujistěte se, že máte:

* Java 8 nebo novější nainstalovanou (návod byl testován s JDK 17).
* Maven nebo Gradle pro správu závislostí.
* Základní znalost syntaxe Javy a konceptu čárového kódu.

Pokud jste nováčkem v Maven, můžete vytvořit jednoduchý projekt pomocí `mvn archetype:generate` a přidat závislost Aspose.BarCode uvedenou níže.

## Přidejte závislost Aspose.BarCode

```xml
<!-- pom.xml -->
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-barcode</artifactId>
    <version>23.12</version> <!-- Use the latest version available -->
</dependency>
```

> **Tip:** Uzamkněte číslo verze, aby nedošlo k neočekávaným breaking changes při aktualizaci knihovny.

## Krok 1: Inicializace generátoru čárových kódů pro Planet symbologii

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

**Proč je tento krok důležitý:**  
`EncodeTypes.PLANET` říká knihovně, aby použila specifikaci Planet čárového kódu, která je běžně používána pro poštovní služby. Řetězec dat `"123456"` je náklad, který se objeví v generovaném obrázku.

## Krok 2: Nastavení vlastních rozměrů čárového kódu (X rozměr)

```java
        // Step 2 – adjust the X dimension (module width) to 4 pixels.
        // This controls the thickness of each bar.
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .getXDimension()
                        .setPixels(4);
```

**Proč je tento krok důležitý:**  
*X rozměr* určuje, jak široký je každý jednotlivý pruh. Nastavením na **4 pixely** získáte čárový kód, který je snadno čitelný většinou skenerů a zároveň se vejde na standardní štítek. Změna této hodnoty je hlavním způsobem, jak dosáhnout **vlastních rozměrů čárového kódu**.

## Krok 3: Použití prázdných (obrysových) pruhů místo plných pruhů

```java
        // Step 3 – configure the generator to draw empty bars (outline only)
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .setFilledBars(false);
```

**Proč je tento krok důležitý:**  
`setFilledBars(false)` říká rendereru, aby kreslil pouze obrysy pruhů a zanechal vnitřek průhledný. Tento styl je často vyžadován u poštovních čárových kódů, kde pozadí může obsahovat další tištěné informace.

## Krok 4: Uložení obrázku čárového kódu jako PNG

```java
        // Step 4 – save the generated barcode as a PNG file
        String outputPath = "output/PlanetEmptyBars.png";
        barcodeGenerator.save(outputPath, BarCodeImageFormat.Png);

        System.out.println("Barcode image generated at: " + outputPath);
    }
}
```

**Proč je tento krok důležitý:**  
Volba `BarCodeImageFormat.Png` vám poskytne bezztrátový obrázek, který zachovává ostré hrany obrysových pruhů. Cesta k souboru může být libovolný adresář, do kterého máte právo zapisovat; v příkladu je použita složka `output` relativně k kořeni projektu.

### Očekávaný výstup

Spuštěním programu se vytvoří soubor podobný obrázku níže:

![Vygenerovaný obrázek čárového kódu pro Planet symbologii](/images/planet-barcode.png){.align-center alt="Vygenerovaný obrázek čárového kódu zobrazující Planet čárový kód s prázdnými obrysy"}

Obrázek zobrazuje **Planet čárový kód** s tenkými, prázdnými pruhy, přesně odpovídající nastaveným vlastním rozměrům.

## Běžné varianty a okrajové případy

| Situace | Úprava |
|-----------|------------|
| **Různá délka dat** | Planet čárové kódy podporují až 12 číselných znaků. Podle toho změňte druhý argument konstruktoru. |
| **Vyšší rozlišení** | Zvyšte X rozměr (`setPixels`) nebo nastavte `YDimension` pro kontrolu výšky pruhů. |
| **Barevný čárový kód** | Použijte `barcodeGenerator.getParameters().getImageOptions().setForeColor(Color.BLUE);` pro změnu barvy pruhů. |
| **Ukládání jako SVG** | Nahraďte `BarCodeImageFormat.Png` za `BarCodeImageFormat.Svg` pro vektorový výstup. |
| **Spuštění na Androidu** | Použijte Android‑kompatibilní Aspose.BarCode pro Android a nahraďte cesty k souborovému systému za `Context.getFilesDir()`. |

> **Dejte pozor:** Nastavení X rozměru příliš nízko (např. 1 pixel) může způsobit, že čárový kód bude nečitelný na nízkorizolucních tiskárnách. Vždy testujte s reálným skenerem po změně rozměrů.

## Kompletní zdrojový kód pro rychlé zkopírování

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

Zkopírujte kód do souboru pojmenovaného `PlanetBarcodeDemo.java`, umístěte jej pod `src/main/java/com/example/barcode/`, spusťte `mvn compile exec:java` a uvidíte výsledek **vytvoření obrázku čárového kódu** ve složce `output`.

## Závěr

Nyní víte, jak **vytvořit obrázek čárového kódu** pro Planet symbologii v Javě, jak **vytvořit Planet čárový kód** s **vlastními rozměry čárového kódu** a jak přepnout z plných na prázdné pruhy pro čistší vizuální styl. Kompletní příklad demonstruje každé potřebné volání API, od inicializace generátoru až po uložení PNG souboru.

**Další kroky** – prozkoumejte další typy čárových kódů (`EncodeTypes.CODE_128`, `EncodeTypes.QR`) a experimentujte s dalšími možnostmi obrázku, jako je barva pozadí, okraje a nastavení DPI. Pokud potřebujete vložit čárový kód do PDF, zkombinujte tento kód s Aspose.PDF pro Java pro bezproblémové end‑to‑end řešení.

Šťastné programování!


## Co byste se měli naučit dál?


Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy ve vlastních projektech.

- [How to create planet barcode with filled and empty bars](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [create planet barcode image – Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-image-step-by-step-guide/)
- [How to generate barcode java: Create an Exact Barcode Image](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}