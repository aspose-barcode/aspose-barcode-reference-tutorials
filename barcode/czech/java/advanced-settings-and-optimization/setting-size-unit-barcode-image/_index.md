---
date: 2026-02-07
description: Naučte se, jak použít Aspose Barcode pro Javu k vytvoření čárového kódu
  CODE_128, generování obrázku čárového kódu v Javě a nastavení přesných jednotek
  velikosti – ideální pro čárový kód v inventárním systému nebo při tvorbě přepravních
  štítků.
linktitle: Setting Size Unit for Barcode Image
second_title: Aspose.BarCode Java API
title: 'aspose barcode java: Vytvořit čárový kód CODE_128 s jednotkou velikosti'
url: /cs/java/advanced-settings-and-optimization/setting-size-unit-barcode-image/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose barcode java: Vytvoření čárového kódu CODE_128 s jednotkou velikosti

## Úvod

V tomto krok‑za‑krokem tutoriálu **použijete aspose barcode java** k vytvoření čárového kódu CODE_128, vygenerování obrázku čárového kódu java a přesnému řízení jednotky velikosti výstupu. Ať už vytváříte čárový kód pro inventurní systém, generátor přepravních štítků nebo jakoukoli Java‑aplikaci, která potřebuje spolehlivé čárové kódy, Aspose.BarCode for Java vám poskytne plnou flexibilitu během několika řádků kódu.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.BarCode for Java (aspose barcode java).  
- **Jaký typ čárového kódu je pokryt?** CODE_128 (create code128 barcode java).  
- **Jak nastavit jednotku velikosti?** Použijte vlastnost `BarHeight` s `.setPoint()`.  
- **Mohu generovat barcode image java v jiných formátech?** Ano – PNG, JPEG, BMP, atd.  
- **Jaké jsou předpoklady?** Nainstalovaný JDK, knihovna Aspose.BarCode a Java IDE.

## Co je **create code128 barcode java**?

Vytvoření čárového kódu CODE_128 v Javě znamená vytvořit instanci třídy `BarcodeGenerator` s výčtem `EncodeTypes.CODE_128` a předat řetězec dat, který chcete zakódovat. Tato symbologie je široce používána v logistice, protože podporuje celý ASCII znakový soubor a nabízí vysokou datovou hustotu — což ji činí ideální pro scénáře inventurních systémů.

## Proč použít Aspose.BarCode k **generate barcode image java**?

- **Plná kontrola nad rozměry** — můžete nastavit výšku čáry, velikost modulu a rozlišení obrázku.  
- **Žádné externí závislosti** — čistá Java, funguje na jakékoli platformě podporující JDK.  
- **Bohatá přizpůsobitelnost** — barvy, písma, okraje a dokonce i QR kódy jsou podporovány.  
- **Vysoký výkon** — generuje obrázky během milisekund, vhodné pro dávkové zpracování a workflow generování štítků s čárovými kódy.

## Předpoklady

Před zahájením se ujistěte, že máte:

1. **Java Development Kit (JDK)** — verze 8 nebo novější nainstalovaná na vašem počítači.  
2. **Aspose.BarCode for Java knihovna** — stáhněte nejnovější JAR z webu Aspose (zkušební nebo licencovaná verze).  
3. **Java IDE** — např. IntelliJ IDEA, Eclipse nebo VS Code s rozšířeními pro Javu.  

## Import Namespaces

Přidejte požadované importy na začátek vaší Java třídy, aby byl přístupný API Aspose.BarCode:

```java
import java.io.IOException;

import com.aspose.barcode.*;

import com.aspose.barcode.generation.BarcodeGenerator;
```

## Jak **generate barcode image java** s Aspose.BarCode?

Níže je kompletní workflow. Každý krok je vysvětlen srozumitelně a původní bloky kódu jsou zachovány přesně tak, jak byly.

### Krok 1: Definujte adresář zdrojů

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Nahraďte `"Your Document Directory"` absolutní cestou, kam chcete uložit obrázek čárového kódu. Tento adresář bude obsahovat vygenerované soubory PNG/JPEG, které můžete později vložit do faktur, balicích listů nebo inventurních reportů.

### Krok 2: Vytvořte objekt čárového kódu

```java
// Instantiate barcode object, Set the symbology type to code128 and Set the
// Code text for the barcode
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "1234567");
```

Zde **create code128 barcode java** předáním `EncodeTypes.CODE_128` a řetězce dat `"1234567"`.

### Krok 3: Nastavte výšku čáry (jednotka velikosti)

```java
// Set the bar height to 3 points
bb.getParameters().getBarcode().getBarHeight().setPoint(3.0f);
```

Metoda `setPoint()` určuje výšku v bodech (1 bod = 1/72 palce). Upravením této hodnoty přizpůsobíte požadavkům na rozvržení — větší hodnoty vytvoří vyšší čáry, což je často potřeba u vysoce rozlišených přepravních štítků.

### Krok 4: Uložte obrázek

```java
// Save the image
bb.save(dataDir + "barcode-size-unit.jpg");
```

Volání `save()` zapíše vygenerovaný čárový kód do dříve určeného adresáře. Formát obrázku je odvozen od přípony souboru (v tomto případě JPEG). Přepnutím přípony můžete snadno použít PNG, BMP nebo TIFF.

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|-------|--------|-----|
| **Obrázek nebyl vytvořen** | `dataDir` cesta je nesprávná nebo chybí oprávnění k zápisu. | Ověřte, že složka existuje a aplikace má oprávnění k zápisu. |
| **Čárový kód je příliš malý** | Výška čáry nastavená v bodech je pro zvolenou DPI příliš nízká. | Zvyšte hodnotu předanou do `setPoint()` nebo upravte DPI obrázku pomocí `bb.getParameters().getImage().setResolution()`. |
| **Nesprávné znaky** | CODE_128 podporuje pouze ASCII; předali jste Unicode. | Použijte jinou symbologii (např. QR_CODE) pro data mimo ASCII. |

## Často kladené otázky

**Q: Je Aspose.BarCode for Java vhodný jak pro generování, tak pro rozpoznávání čárových kódů?**  
A: Ano, knihovna podporuje jak generování, tak rozpoznávání široké škály symbologií.

**Q: Mohu přizpůsobit vzhled vygenerovaných obrázků čárových kódů?**  
A: Rozhodně. Můžete měnit barvy, přidávat popisky, upravovat okraje a dokonce vkládat loga pomocí rozsáhlého API `Parameters`.

**Q: Jak získat dočasnou licenci pro Aspose.BarCode for Java?**  
A: Navštivte [zde](https://purchase.aspose.com/temporary-license/) a požádejte o dočasnou licenci pro vyhodnocení.

**Q: Kde najdu podporu pro Aspose.BarCode for Java?**  
A: Komunitní fórum Aspose.BarCode je nejlepší místo pro pomoc. Podívejte se na [forum](https://forum.aspose.com/c/barcode/13) pro odpovědi a položte nové otázky.

**Q: Jaké symbologie čárových kódů jsou v Aspose.BarCode for Java podporovány?**  
A: Knihovna podporuje desítky symbologií, včetně CODE_128, QR_CODE, UPC_A, DataMatrix, PDF417 a mnoha dalších.

### Další tipy (Pro tip)

- **Dávkové zpracování:** Zabalte výše uvedené kroky do smyčky a vygenerujte stovky čárových kódů pro hromadné nahrávání inventáře.  
- **Řízení rozlišení:** Použijte `bb.getParameters().getImage().setResolution(300)` k vytvoření 300 dpi obrázků, ideálních pro vysoce kvalitní tiskové štítky.  

**Poslední aktualizace:** 2026-02-07  
**Testováno s:** Aspose.BarCode for Java 24.12 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}