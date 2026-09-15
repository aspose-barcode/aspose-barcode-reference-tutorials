---
date: 2026-04-05
description: Naučte se, jak vytvořit obrázek čárového kódu Codabar v Javě s kontrolním
  součtem, a podívejte se na příklad čtečky čárových kódů v Javě pomocí Aspose.BarCode.
  Postupujte podle tohoto průvodce krok po kroku pro generování a rozpoznávání čárových
  kódů.
keywords:
- create codabar barcode java
- java barcode reader example
- codabar checksum
- aspose barcode java
linktitle: Použití kontrolního součtu pro CodaBar
second_title: Aspose.BarCode Java API
title: Jak vytvořit obrázek čárového kódu Codabar v Javě s kontrolním součtem
url: /cs/java/checksum-and-validation/applying-checksum-codabar/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit obrázek čárového kódu codabar v Javě s kontrolním součtem

## Úvod

V tomto tutoriálu **vytvoříte codabar barcode java** obrázky s kontrolním součtem Mod 10 pomocí Aspose.BarCode for Java. Provedeme vás generováním CodaBar čárového kódu, povolením kontrolního součtu a následnou validací pomocí **java barcode reader example**. Na konci budete mít připravený úryvek kódu, který můžete vložit do jakéhokoli Java projektu, ať už budujete knihovní systém, tiskárnu štítků pro lékařské laboratoře nebo řešení pokladny v maloobchodě.

## Rychlé odpovědi
- **Co dělá kontrolní součet?** Ověřuje integritu dat čárového kódu během skenování.  
- **Která knihovna je vyžadována?** Aspose.BarCode for Java.  
- **Potřebuji licenci pro vývoj?** Dočasná licence funguje pro testování; plná licence je vyžadována pro produkci.  
- **Mohu přizpůsobit vzhled čárového kódu?** Ano – barvu, velikost a písmo lze změnit pomocí parametrů generátoru.  
- **Je to kompatibilní se všemi verzemi Javy?** Knihovna podporuje Java 8 a novější.

## Jak vytvořit codabar barcode java

Níže najdete stručný, krok‑za‑krokem průvodce, který vysvětluje **proč je každý řádek důležitý**, takže můžete s jistotou přizpůsobit kód svým projektům.

### Co je CodaBar čárový kód?

CodaBar je lineární (1‑dimenzionální) symbologie široce používaná v knihovnách, krevních bankách a maloobchodě. Kóduje číselná data a několik speciálních znaků, což z ní činí ideální řešení pro jednoduché, strojově čitelné štítky. Přidání kontrolního součtu (Mod 10) zvyšuje přesnost čtení, zejména u tisků nízké kvality.

### Proč používat Aspose.BarCode pro Java?

Aspose.BarCode nabízí **java barcode reader example**, který abstrahuje nízkoúrovňové detaily generování a rozpoznávání čárových kódů. Poskytuje:
* Úplnou kontrolu nad režimy kontrolního součtu.  
* Bezproblémovou integraci s Java IDE.  
* Rozsáhlou dokumentaci a rychlou podporu.  

### Předpoklady

Než začneme, ujistěte se, že máte:
- Nainstalovaný Java Development Kit (JDK) 8 nebo novější.  
- Knihovnu Aspose.BarCode for Java. Můžete si ji stáhnout [zde](https://releases.aspose.com/barcode/java/).  
- Základní znalost konceptů programování v Javě.  

### Import balíčků

Ve vašem Java projektu importujte potřebné třídy pro práci s Aspose.BarCode:

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

### Průvodce krok za krokem

#### Krok 1: Nastavení prostředí

Vytvořte nový Java projekt a přidejte JAR soubor Aspose.BarCode do cesty sestavení. Definujte složku, kam budou ukládány vygenerované obrázky.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

#### Krok 2: Vygenerujte obrázek CodaBar čárového kódu s kontrolním součtem

Vytvořte instanci `BarcodeGenerator`, povolte kontrolní součet, zvolte režim Mod 10 a uložte obrázek.

```java
// Instantiate BarcodeGenerator object
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "1234567890");

// Set the EnableChecksum property to yes
generator.getParameters().getBarcode().setChecksumEnabled(EnableChecksum.YES);

// Set the CodabarChecksumMode
generator.getParameters().getBarcode().getCodabar().setCodabarChecksumMode(CodabarChecksumMode.MOD_10);

// Save the image on the system
generator.save(dataDir + "Codabar_Mod10.png");
```

#### Krok 3: Java barcode reader example – Rozpoznání čárového kódu

Nyní načtěte čárový kód zpět, zapněte validaci kontrolního součtu, aby byla data správná.

```java
// Initialize reader object
BarCodeReader reader = new BarCodeReader(dataDir + "Codabar_Mod10.png", DecodeType.CODABAR);

// Set ChecksumValidation property of the reader to On
reader.setChecksumValidation(ChecksumValidation.ON);

for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());

    // Get checksum value
    System.out.println("Checksum:" + result.getExtended().getOneD().getCheckSum());
}
```

Spuštěním kódu se vypíše dekódovaný text, typ symbologie a vypočtený kontrolní součet, což potvrzuje, že čárový kód byl správně vygenerován a ověřen.

### Běžné případy použití

- **Správa knihovny:** Kódujte ID knih pro rychlé skenování při výpůjčce.  
- **Štítky krevních bank:** Zajistěte přesnou identifikaci pacienta s ochranou kontrolního součtu.  
- **Štítky regálů v maloobchodě:** Tiskněte levné, vysokorychlostní čárové kódy pro sledování zásob.  

### Běžné problémy a řešení

| Problém | Řešení |
|-------|----------|
| **Selhání validace kontrolního součtu** | Ověřte, že `EnableChecksum` je nastaven na `YES` a že `CodabarChecksumMode` odpovídá režimu použitému při generování (Mod 10). |
| **Chyba souboru nenalezen** | Ujistěte se, že `dataDir` ukazuje na existující složku a že vygenerovaný obrázek (`Codabar_Mod10.png`) je v ní uložen před čtením. |
| **Nesprávná verze Javy** | Použijte Java 8 nebo novější; starší verze mohou postrádat potřebná API. |

## Často kladené otázky

**Q: Je Aspose.BarCode kompatibilní se všemi verzemi Javy?**  
A: Aspose.BarCode je navržena tak, aby fungovala s Java 8 a novějšími. Zkontrolujte oficiální dokumentaci pro podrobnou kompatibilitu.

**Q: Mohu přizpůsobit vzhled vygenerovaného čárového kódu?**  
A: Ano, můžete měnit barvy, písma a formát obrázku pomocí API parametrů generátoru.

**Q: Jsou k dispozici dočasné licence pro testovací účely?**  
A: Ano, můžete získat dočasnou licenci pro Aspose.BarCode [zde](https://purchase.aspose.com/temporary-license/).

**Q: Kde najdu další podporu a zdroje?**  
A: Navštivte [Aspose.BarCode fórum](https://forum.aspose.com/c/barcode/13) pro komunitní podporu a diskuse.

**Q: Je k dispozici bezplatná zkušební verze?**  
A: Ano, můžete prozkoumat funkce Aspose.BarCode stažením bezplatné zkušební verze [zde](https://releases.aspose.com/).

---

**Last Updated:** 2026-04-05  
**Tested With:** Aspose.BarCode for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}