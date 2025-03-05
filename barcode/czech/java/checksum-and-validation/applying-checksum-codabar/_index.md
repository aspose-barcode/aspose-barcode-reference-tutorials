---
title: Použití kontrolního součtu pro CodaBar v Javě
linktitle: Použití kontrolního součtu pro CodaBar
second_title: Aspose.BarCode Java API
description: Naučte se, jak použít kontrolní součet pro CodaBar v Javě pomocí Aspose.BarCode. Vytvářejte a rozpoznávejte čárové kódy bez námahy pomocí tohoto podrobného průvodce.
type: docs
weight: 11
url: /cs/java/checksum-and-validation/applying-checksum-codabar/
---

## Úvod

Vítejte v tomto podrobném návodu na použití kontrolního součtu pro CodaBar v Javě pomocí Aspose.BarCode. Aspose.BarCode for Java je výkonná knihovna, která umožňuje vývojářům bezproblémově generovat a rozpoznávat čárové kódy v aplikacích Java. V tomto tutoriálu se zaměříme na konkrétní úlohu použití kontrolního součtu pro čárové kódy CodaBar.

## Předpoklady

Než se pustíme do výukového programu, ujistěte se, že máte následující předpoklady:

- Java Development Kit (JDK) nainstalovaný na vašem počítači.
-  Aspose.BarCode pro knihovnu Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/barcode/java/).
- Základní znalost programování v Javě.

## Importujte balíčky

Ve svém projektu Java se ujistěte, že importujete potřebné balíčky pro práci s Aspose.BarCode:

```java
import java.io.IOException;

import com.aspose.barcode.CodabarChecksumMode;
import com.aspose.barcode.EnableChecksum;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.ChecksumValidation;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Krok 1: Nastavte prostředí

Začněte vytvořením nového projektu Java a zahrnutím knihovny Aspose.BarCode do závislostí vašeho projektu. Nastavte své vývojové prostředí s požadovanými prostředky.

```java
// Cesta k adresáři prostředků.
String dataDir = "Your Document Directory";
```

## Krok 2: Generování čárového kódu CodaBar

Nyní vygenerujme čárový kód CodaBar s povoleným kontrolním součtem.

```java
// Vytvořte objekt BarcodeGenerator
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "1234567890");

// Nastavte vlastnost EnableChecksum na yes
generator.getParameters().getBarcode().setChecksumEnabled(EnableChecksum.YES);

// Nastavte CodabarChecksumMode
generator.getParameters().getBarcode().getCodabar().setCodabarChecksumMode(CodabarChecksumMode.MOD_10);

// Uložte obrázek do systému
generator.save(dataDir + "Codabar_Mod10.png");
```

## Krok 3: Rozpoznání čárového kódu CodaBar

Nyní implementujme rozpoznávací část čárového kódu CodaBar s kontrolním součtem.

```java
// Inicializujte objekt čtečky
BarCodeReader reader = new BarCodeReader(dataDir + "Codabar_Mod10.png", DecodeType.CODABAR);

// Nastavte vlastnost ChecksumValidation čtečky na On
reader.setChecksumValidation(ChecksumValidation.ON);

for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());

    // Získejte hodnotu kontrolního součtu
    System.out.println("Checksum:" + result.getExtended().getOneD().getCheckSum());
}
```

Chcete-li použít kontrolní součet pro CodaBar v Javě bez námahy pomocí Aspose.BarCode, postupujte podle těchto kroků.

## Závěr

V tomto tutoriálu jsme prozkoumali, jak použít kontrolní součet pro čárové kódy CodaBar v Javě pomocí Aspose.BarCode. Tato knihovna poskytuje přímý způsob generování a rozpoznávání čárových kódů s různými možnostmi přizpůsobení.

---

## Nejčastější dotazy

### Je Aspose.BarCode kompatibilní se všemi verzemi Java?
Aspose.BarCode je navržen pro práci s různými verzemi Java. Podrobnosti o kompatibilitě zkontrolujte v dokumentaci.

### Mohu upravit vzhled vygenerovaného čárového kódu?
Ano, Aspose.BarCode nabízí rozsáhlé možnosti přizpůsobení, které vám umožní ovládat vzhled generovaných čárových kódů.

### Jsou dočasné licence dostupné pro testovací účely?
 Ano, můžete získat dočasnou licenci pro Aspose.BarCode od[tady](https://purchase.aspose.com/temporary-license/).

### Kde najdu další podporu a zdroje?
 Navštivte[Fórum Aspose.BarCode](https://forum.aspose.com/c/barcode/13) za podporu komunity a diskuze.

### Je k dispozici bezplatná zkušební verze?
 Ano, funkce Aspose.BarCode můžete prozkoumat stažením bezplatné zkušební verze z[tady](https://releases.aspose.com/).