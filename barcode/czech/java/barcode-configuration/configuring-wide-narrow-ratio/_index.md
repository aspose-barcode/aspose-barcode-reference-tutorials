---
date: 2025-12-10
description: Naučte se, jak v Javě pomocí Aspose.BarCode generovat čárový kód s vlastním
  poměrem široké‑úzké a efektivně vytvořit obrázek čárového kódu. Postupujte podle
  našeho krok‑za‑krokem průvodce.
linktitle: Configuring Wide-Narrow Ratio
second_title: Aspose.BarCode Java API
title: Jak vygenerovat čárový kód s poměrem široký‑úzký v Javě
url: /cs/java/barcode-configuration/configuring-wide-narrow-ratio/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vygenerovat čárový kód s poměrem široko-úzký v Javě

## Úvod

Pokud potřebujete **jak vygenerovat čárový kód** s přesnými vizuálními proporcemi, klíčovým prvkem je nastavení poměru široko‑úzký. V tomto tutoriálu vás provedeme **krok za krokem tvorbou čárového kódu** pomocí Aspose.BarCode pro Java, ukážeme, jak nastavit poměr, vygenerovat obrázek čárového kódu a **uložit čárový kód png** na disk. Ať už vytváříte štítky zásob, přepravní značky nebo jakoukoli aplikaci vyžadující vlastní styl CODE_128, najdete zde vše, co potřebujete.

## Rychlé odpovědi
- **Co je poměr široko‑úzký?** Řídí relativní šířku širokých pruhů oproti úzkým pruhům v čárovém kódu.  
- **Které symboly podporují úpravu poměru?** Většina 1‑D symbolů, včetně CODE_128, umožňuje nastavit vlastní poměr.  
- **Potřebuji licenci?** K dispozici je bezplatná zkušební verze, ale pro produkční použití je vyžadována komerční licence.  
- **Mohu vygenerovat obrázek čárového kódu ve formátu PNG?** Ano – použijte `generator.save(...)` k vytvoření obrázku čárového kódu jako PNG.  
- **Je kód kompatibilní s Java 8+?** Rozhodně; Aspose.BarCode funguje se všemi moderními verzemi Javy.

## Předpoklady

Než se pustíme do kódu, ujistěte se, že máte následující:

- Java Development Kit (JDK) nainstalovaný na vašem počítači.  
- Knihovnu Aspose.BarCode pro Java. Stáhněte ji z [download link](https://releases.aspose.com/barcode/java/).

## Import balíčků

Pro začátek importujte základní třídu Aspose.BarCode do svého projektu.

```java
// Import Aspose.BarCode library
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Co je poměr široko‑úzký a proč jej upravovat?

Poměr široko‑úzký určuje, jak silné se jeví „široké“ pruhy ve srovnání s „úzkými“. Úprava tohoto poměru může zlepšit čitelnost skenerem, splnit specifické tiskové standardy nebo jednoduše ladit vizuální styl značky.

## Jak vygenerovat čárový kód s poměrem široko‑úzký v Javě

Níže je **krok za krokem průvodce čárovým kódem**, který vás provede každým úsekem procesu.

### Krok 1: Nastavte adresář dokumentu

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Ujistěte se, že adresář existuje a máte oprávnění k zápisu; sem bude umístěn soubor **save barcode png**.

### Krok 2: Vytvořte objekt Barcode

```java
// Instantiate barcode object
// Create an instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

Zde **vytvoříme code_128 barcode** předáním `EncodeTypes.CODE_128` do konstruktoru.

### Krok 3: Nastavte poměr široko‑úzký

```java
// Set the wide to narrow ratio for the barcode
generator.getParameters().getBarcode().setWideNarrowRatio(3.0f);
```

Metoda `setWideNarrowRatio` vám umožní jemně doladit vizuální rozestupy. Hodnota `3.0f` znamená, že široký pruh je třikrát širší než úzký pruh.

### Krok 4: Uložte obrázek na disk

```java
// Save the image to disk in PNG format
generator.save(dataDir + "wideNarrowRatio.png");
```

Volání `save` **vygeneruje obrázek čárového kódu** a uloží jej jako soubor PNG, čímž dokončí krok **save barcode png**.

## Časté problémy a řešení

| Problém | Důvod | Řešení |
|---------|-------|--------|
| Čárový kód vypadá deformovaně | Poměr je příliš vysoký nebo nízký pro tiskárnu | Upravte hodnotu předanou do `setWideNarrowRatio` (např. 2.0‑2.5). |
| Soubor nebyl vytvořen | Neplatná cesta `dataDir` nebo nedostatečná oprávnění | Ověřte cestu k adresáři a zajistěte, aby aplikace měla právo zapisovat. |
| Skener nedokáže čárový kód přečíst | Poměr mimo doporučený rozsah pro daný symbol | Použijte standardní poměry (2.0‑3.0) nebo testujte s cílovým skenerem. |

## Často kladené otázky

**Q: Mohu použít Aspose.BarCode s jinými Java frameworky?**  
A: Ano, Aspose.BarCode je navržen tak, aby bez problémů fungoval se Spring, Java EE, Android a dalšími Java prostředími.

**Q: Jak mohu generovat čárové kódy s různými symboly?**  
A: Stačí změnit typ symbolu v konstruktoru `BarcodeGenerator`, například `EncodeTypes.QR` pro QR kódy.

**Q: Je k dispozici zkušební verze Aspose.BarCode?**  
A: Ano, bezplatnou zkušební verzi získáte [zde](https://releases.aspose.com/).

**Q: Kde najdu podrobnou dokumentaci k Aspose.BarCode?**  
A: Dokumentaci najdete [zde](https://reference.aspose.com/barcode/java/).

**Q: Jak získat podporu pro Aspose.BarCode?**  
A: Navštivte fórum Aspose.BarCode [zde](https://forum.aspose.com/c/barcode/13) pro podporu a komunitní diskuze.

---

**Poslední aktualizace:** 2025-12-10  
**Testováno s:** Aspose.BarCode pro Java 24.11 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}