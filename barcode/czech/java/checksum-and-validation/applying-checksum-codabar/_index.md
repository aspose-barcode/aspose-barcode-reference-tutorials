---
date: 2025-12-18
description: Naučte se, jak vytvořit obrázek čárového kódu Codabar, a podívejte se
  na příklad čtečky čárových kódů v Javě pomocí Aspose.BarCode. Generujte a rozpoznávejte
  čárové kódy bez námahy s tímto krok‑za‑krokem průvodcem.
linktitle: Applying Checksum for CodaBar
second_title: Aspose.BarCode Java API
title: Jak vytvořit obrázek čárového kódu Codabar s kontrolním součtem v Javě
url: /cs/java/checksum-and-validation/applying-checksum-codabar/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit obrázek čárového kódu Codabar s kontrolním součtem v Javě

## Úvod

V tomto tutoriálu se naučíte, jak **vytvořit obrázek čárového kódu Codabar** s kontrolním součtem v Javě pomocí Aspose.BarCode. Provedeme vás generováním čárového kódu CodaBar, povolením kontrolního součtu a následným načtením pomocí **příkladu čtečky čárových kódů v Javě**. Na konci budete mít připravený úryvek kódu, který můžete vložit do libovolného Java projektu.

## Rychlé odpovědi
- **Co dělá kontrolní součet?** Ověřuje integritu dat čárového kódu během skenování.  
- **Která knihovna je vyžadována?** Aspose.BarCode pro Java.  
- **Potřebuji licenci pro vývoj?** Dočasná licence funguje pro testování; pro produkci je vyžadována plná licence.  
- **Mohu přizpůsobit vzhled čárového kódu?** Ano – barvu, velikost a písmo lze změnit pomocí parametrů generátoru.  
- **Je to kompatibilní se všemi verzemi Javy?** Knihovna podporuje Java 8 a novější.

## Co je čárový kód CodaBar?

CodaBar je lineární (1‑dimenzionální) symbologie široce používaná v knihovnách, krevních bankách a maloobchodu. Kóduje číselná data a několik speciálních znaků, což něj činí ideální řešení pro jednoduché, strojově čitelné štítky. Přidání kontrolního součtu (Mod 10) zvyšuje přesnost čtení, zejména u nízkokvalitních výtisků.

## Proč použít Aspose.BarCode pro Java?

Aspose.BarCode nabízí **příklad čtečky čárových kódů v Javě**, který abstrahuje nízkoúrovňové detaily generování a rozpoznávání čárových kódů. Poskytuje:

* Plnou kontrolu nad režimy kontrolního součtu.  
* Bezproblémovou integraci s Java IDE.  
* Rozsáhlou dokumentaci a podporu.  

## Požadavky

- Java Development Kit (JDK) nainstalovaný na vašem počítači.  
- Knihovnu Aspose.BarCode pro Java. Můžete si ji stáhnout [zde](https://releases.aspose.com/barcode/java/).  
- Základní znalost programování v Javě.  

## Import balíčků

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

## Postupný návod

### Krok 1: Nastavení prostředí

Vytvořte nový Java projekt a přidejte JAR Aspose.BarCode do cesty sestavení. Definujte složku, kam budou ukládány vygenerované obrázky.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

### Krok 2: Vygenerujte obrázek čárového kódu CodaBar s kontrolním součtem

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

### Krok 3: Příklad čtečky čárových kódů v Javě – Rozpoznání čárového kódu

Nyní načtěte čárový kód zpět, zapněte ověření kontrolního součtu, aby byla data správná.

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

## Časté problémy a řešení

| Problém | Řešení |
|-------|----------|
| **Ověření kontrolního součtu selhalo** | Ověřte, že `EnableChecksum` je nastaven na `YES` a že `CodabarChecksumMode` odpovídá režimu použitému při generování (Mod 10). |
| **Chyba souboru nenalezen** | Ujistěte se, že `dataDir` ukazuje na existující složku a že vygenerovaný obrázek (`Codabar_Mod10.png`) je v ní uložen před čtením. |
| **Není podporovaná verze Javy** | Použijte Java 8 nebo novější; starší verze mohou postrádat potřebná API. |

## Často kladené otázky

**Q: Je Aspose.BarCode kompatibilní se všemi verzemi Javy?**  
A: Aspose.BarCode je navržen tak, aby fungoval s Java 8 a novějšími. Podívejte se do oficiální dokumentace pro podrobnosti o kompatibilitě.

**Q: Mohu přizpůsobit vzhled vygenerovaného čárového kódu?**  
A: Ano, můžete měnit barvy, písma a formát obrázku pomocí API parametrů generátoru.

**Q: Jsou k dispozici dočasné licence pro testovací účely?**  
A: Ano, dočasnou licenci pro Aspose.BarCode můžete získat [zde](https://purchase.aspose.com/temporary-license/).

**Q: Kde mohu najít další podporu a zdroje?**  
A: Navštivte [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13) pro komunitní podporu a diskuze.

**Q: Je k dispozici bezplatná zkušební verze?**  
A: Ano, můžete si vyzkoušet funkce Aspose.BarCode stažením bezplatné zkušební verze [zde](https://releases.aspose.com/).

---

**Last Updated:** 2025-12-18  
**Tested With:** Aspose.BarCode for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}