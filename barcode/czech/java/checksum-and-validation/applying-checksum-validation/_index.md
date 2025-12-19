---
date: 2025-12-19
description: Naučte se, jak zakázat ověřování kontrolního součtu v Javě s Aspose.BarCode.
  Tento krok‑za‑krokem průvodce vám ukáže, jak číst čárové kódy, vypnout kontrolní
  součet a zajistit spolehlivé zpracování dat.
linktitle: How to Disable Checksum Validation
second_title: Aspose.BarCode Java API
title: Jak zakázat ověřování kontrolního součtu v Javě
url: /cs/java/checksum-and-validation/applying-checksum-validation/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak zakázat ověřování kontrolního součtu v Javě

V moderních aplikacích pro inventarizaci a logistiku může být **jak zakázat kontrolní součet** klíčem k čtení starých čárových kódů, které neobsahují kontrolní číslici. Aspose.BarCode pro Java umožňuje snadno vypnout ověřování kontrolního součtu a přitom stále získávat zakódovaná data. Tento tutoriál vás provede celým procesem – od nastavení projektu až po čtení ONE‑CODE čárového kódu bez ověření kontrolního součtu.

## Rychlé odpovědi
- **Co dělá zakázání kontrolního součtu?** Říká čtečce, aby ignorovala pole kontrolního součtu, což umožňuje zpracovat čárové kódy bez platného kontrolního součtu.  
- **Kdy byste měli zakázat kontrolní součet?** Když pracujete se starými systémy nebo nestandardními čárovými kódy, které kontrolní součet vynechávají nebo poškozují.  
- **Která třída řídí ověřování kontrolního součtu?** `BarCodeReader.setChecksumValidation(ChecksumValidation)`  
- **Je zakázání kontrolního součtu bezpečné?** Pouze pokud důvěřujete zdroji čárového kódu; jinak pomáhá ověření zachytit chyby.  
- **Ovlivňuje to jiné typy čárových kódů?** Nastavení se vztahuje pouze na aktuální instanci `BarCodeReader`.

## Co je ověřování kontrolního součtu?
Ověřování kontrolního součtu je kontrola integrity dat, která vypočítá malou hodnotu z obsahu čárového kódu a porovná ji s vloženým kontrolním součtem. Pokud se neshodují, čárový kód je považován za nečitelný. Zakázání této kontroly říká Aspose.BarCode, aby přeskočil porovnání.

## Proč zakázat kontrolní součet s Aspose.BarCode?
- **Podpora starých systémů:** Starší skenery často generovaly čárové kódy bez kontrolních součtů.  
- **Výkon:** Přeskočení výpočtu může urychlit hromadné čtení.  
- **Flexibilita:** Můžete se rozhodnout pro každou instanci čtečky, zda má vynucovat ověření.

## Předpoklady
- **Java Development Kit (JDK):** Ujistěte se, že máte nainstalovanou nejnovější verzi JDK.  
- **Aspose.BarCode knihovna:** Stáhněte knihovnu z oficiálního webu [here](https://releases.aspose.com/barcode/java/).  

## Import balíčků
Ve svém Java projektu importujte potřebné třídy Aspose.BarCode pro práci s rozpoznáváním čárových kódů.

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.ChecksumValidation;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## Průvodce krok za krokem

### Krok 1: Nastavte svůj projekt
Vytvořte nový Java projekt (IDE dle vašeho výběru) a přidejte soubor Aspose.BarCode JAR do classpath projektu.

### Krok 2: Inicializujte `BarCodeReader`
Načtěte obrázek, který obsahuje ONE‑CODE čárový kód, který chcete přečíst.

```java
String dataDir = "Your Document Directory";
BarCodeReader reader = new BarCodeReader(dataDir + "onecode.png", DecodeType.ONE_CODE);
```

### Krok 3: Jak zakázat kontrolní součet
Řekněte čtečce, aby ignorovala ověřování kontrolního součtu nastavením vlastnosti na `OFF`.

```java
reader.setChecksumValidation(ChecksumValidation.OFF);
```

### Krok 4: Čtěte čárové kódy
Iterujte přes výsledky a vypište dekódovaný text a typ symbologie.

```java
for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());
}
```

**Výsledek:** Text čárového kódu je zobrazen i když původní obrázek postrádá platný kontrolní součet.

## Časté problémy a tipy
- **Nesprávná cesta k souboru:** Ověřte, že `dataDir` ukazuje na správnou složku; pro testování používejte absolutní cesty.  
- **Nepodporovaný typ čárového kódu:** Ujistěte se, že `DecodeType` odpovídá čárovému kódu, který čtete.  
- **Výkon:** Zakázání kontrolního součtu u velkých dávek může zlepšit propustnost, ale pro kritická data jej vždy znovu povolte.

## Často kladené otázky

### Je Aspose.BarCode kompatibilní s různými typy čárových kódů?
Ano, Aspose.BarCode podporuje širokou škálu symbologií čárových kódů, od QR a DataMatrix po tradiční lineární kódy.

### Mohu používat Aspose.BarCode pro komerční účely?
Rozhodně. Komerční licence jsou k dispozici pro firmy, které potřebují funkce připravené pro produkci.

### Jak mohu získat podporu pro Aspose.BarCode?
Navštivte [Aspose.BarCode fórum](https://forum.aspose.com/c/barcode/13), kde se můžete spojit s komunitou a získat pomoc od týmu produktu.

### Je k dispozici bezplatná zkušební verze?
Ano, můžete prozkoumat kompletní sadu funkcí stažením [free trial](https://releases.aspose.com/).

### Kde najdu podrobnou dokumentaci?
Odkazujte se na komplexní [documentation](https://reference.aspose.com/barcode/java/) pro podrobnosti o API, ukázky kódu a osvědčené postupy.

**Poslední aktualizace:** 2025-12-19  
**Testováno s:** Aspose.BarCode for Java (nejnovější verze)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}