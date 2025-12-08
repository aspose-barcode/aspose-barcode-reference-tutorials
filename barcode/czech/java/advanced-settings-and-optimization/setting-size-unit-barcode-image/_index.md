---
date: 2025-12-08
description: Naučte se, jak vytvořit čárový kód code128 v Javě a vygenerovat obrázek
  čárového kódu v Javě pomocí Aspose.BarCode. Nastavte přesné jednotky velikosti pro
  obrázky čárových kódů pomocí jednoduchého, znovupoužitelného kódu.
language: cs
linktitle: Setting Size Unit for Barcode Image
second_title: Aspose.BarCode Java API
title: Vytvořte čárový kód code128 v Javě s Aspose.BarCode
url: /java/advanced-settings-and-optimization/setting-size-unit-barcode-image/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořte code128 barcode java a nastavte jednotku velikosti pomocí Aspose.BarCode

## Úvod

V tomto průvodci krok za krokem **vytvoříte code128 barcode java** kód, který generuje obrázek čárového kódu a umožňuje vám řídit jednotku velikosti výstupu. Ať už budujete inventární systém, generátor přepravních štítků nebo jakoukoli Java aplikaci, která potřebuje spolehlivý čárový kód, Aspose.BarCode pro Java proces zjednodušuje a nabízí vysokou míru přizpůsobení.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.BarCode for Java.
- **Jaký typ čárového kódu je pokryt?** CODE_128 (create code128 barcode java).
- **Jak nastavit jednotku velikosti?** Use the `BarHeight` property with `.setPoint()`.
- **Mohu generovat obrázek čárového kódu v Javě v jiných formátech?** Yes – PNG, JPEG, BMP, etc.
- **Jaké jsou předpoklady?** JDK installed, Aspose.BarCode library, and a Java IDE.

## Co je **create code128 barcode java**?

Vytvoření CODE_128 čárového kódu v Javě znamená vytvořit instanci třídy `BarcodeGenerator` s výčtem `EncodeTypes.CODE128` a poskytnout řetězec dat, který chcete zakódovat. Tato symbologie je široce používána v logistice, protože podporuje celý ASCII znakový soubor a nabízí vysokou datovou hustotu.

## Proč použít Aspose.BarCode k **generate barcode image java**?

- **Plná kontrola nad rozměry** – můžete nastavit výšku čáry, velikost modulu a rozlišení obrázku.  
- **Žádné externí závislosti** – čistá Java, funguje na jakékoli platformě podporující JDK.  
- **Bohaté přizpůsobení** – podporovány barvy, písma, okraje a dokonce i QR kódy.  
- **Vysoký výkon** – generuje obrázky během milisekund, vhodné pro dávkové zpracování.

## Předpoklady

1. **Java Development Kit (JDK)** – verze 8 nebo novější nainstalovaná na vašem počítači.  
2. **Aspose.BarCode pro Java knihovna** – stáhněte nejnovější JAR z webu Aspose (zkušební nebo licencovaná).  
3. **Java IDE** – např. IntelliJ IDEA, Eclipse nebo VS Code s rozšířeními pro Javu.  

## Importování jmenných prostorů

Add the required imports at the top of your Java class so you can access Aspose.BarCode’s API:

```java
import java.io.IOException;

import com.aspose.barcode.*;

import com.aspose.barcode.generation.BarcodeGenerator;
```

## Jak **generate barcode image java** s Aspose.BarCode?

Below is the complete workflow. Each step is explained in plain language, and the original code blocks are kept exactly as they were.

### Krok 1: Definujte adresář zdrojů

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Nahraďte `"Your Document Directory"` absolutní cestou, kam chcete uložit obrázek čárového kódu.

### Krok 2: Vytvořte objekt čárového kódu

```java
// Instantiate barcode object, Set the symbology type to code128 and Set the
// Code text for the barcode
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "1234567");
```

Zde **vytvoříme code128 barcode java** předáním `EncodeTypes.CODE_128` a řetězce dat `"1234567"`.

### Krok 3: Nastavte výšku čáry (jednotka velikosti)

```java
// Set the bar height to 3 points
bb.getParameters().getBarcode().getBarHeight().setPoint(3.0f);
```

`setPoint()` metoda určuje výšku v bodech (1 bod = 1/72 palce). Upravit tuto hodnotu podle požadavků rozvržení.

### Krok 4: Uložte obrázek

```java
// Save the image
bb.save(dataDir + "barcode-size-unit.jpg");
```

Volání `save()` zapíše vygenerovaný čárový kód do zadané složky. Formát obrázku je odvozen z přípony souboru (v tomto případě JPEG).

## Časté problémy a řešení

| Problém | Důvod | Řešení |
|-------|--------|-----|
| **Obrázek nebyl vytvořen** | cesta `dataDir` je nesprávná nebo chybí oprávnění k zápisu. | Ověřte, že složka existuje a aplikace má právo zapisovat. |
| **Čárový kód je příliš malý** | Výška čáry nastavená v bodech je pro zvolenou DPI příliš nízká. | Zvyšte hodnotu předanou `setPoint()` nebo upravte DPI obrázku pomocí `bb.getParameters().getImage().setResolution()`. |
| **Nepodporované znaky** | CODE_128 podporuje pouze ASCII; předali jste Unicode. | Použijte jinou symbologii (např. QR_CODE) pro data mimo ASCII. |

## Často kladené otázky

**Q: Je Aspose.BarCode pro Java vhodný jak pro generování čárových kódů, tak pro jejich rozpoznávání?**  
A: Ano, knihovna podporuje jak generování, tak rozpoznávání široké škály symbologií.

**Q: Mohu přizpůsobit vzhled vygenerovaných obrázků čárových kódů?**  
A: Rozhodně. Můžete měnit barvy, přidávat popisky, upravovat okraje a dokonce vkládat loga pomocí rozsáhlého API `Parameters`.

**Q: Jak mohu získat dočasnou licenci pro Aspose.BarCode pro Java?**  
A: Navštivte [zde](https://purchase.aspose.com/temporary-license/) a požádejte o dočasnou licenci pro vyhodnocení.

**Q: Kde mohu najít podporu pro Aspose.BarCode pro Java?**  
A: Komunitní fórum Aspose.BarCode je nejlepší místo pro pomoc. Podívejte se na [forum](https://forum.aspose.com/c/barcode/13) pro odpovědi a položte nové otázky.

**Q: Jaké symbologie čárových kódů jsou podporovány v Aspose.BarCode pro Java?**  
A: Knihovna podporuje desítky symbologií, včetně CODE_128, QR_CODE, UPC_A, DataMatrix, PDF417 a mnoha dalších.

---

**Poslední aktualizace:** 2025-12-08  
**Testováno s:** Aspose.BarCode for Java 24.12 (latest at time of writing)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}