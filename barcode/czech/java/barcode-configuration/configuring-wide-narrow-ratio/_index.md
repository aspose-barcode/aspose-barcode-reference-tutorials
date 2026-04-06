---
date: 2026-02-12
description: Naučte se, jak vytvořit čárový kód code128 s vlastním poměrem široko‑úzkých
  pruhů v Javě pomocí Aspose.BarCode a efektivně generovat PNG obrázky čárových kódů.
  Postupujte podle našeho průvodce krok za krokem.
linktitle: Configuring Wide-Narrow Ratio
second_title: Aspose.BarCode Java API
title: Jak vytvořit čárový kód CODE_128 s poměrem široko‑úzký v Javě
url: /cs/java/barcode-configuration/configuring-wide-narrow-ratio/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit čárový kód CODE_128 s poměrem široké‑úzké v Javě

## Úvod

Pokud potřebujete **vytvořit čárový kód code128** s přesnými vizuálními proporcemi, klíčem je nastavení poměru široké‑úzké. V tomto tutoriálu vás provedeme **krok‑za‑krokem procesem tvorby čárového kódu** pomocí Aspose.BarCode pro Java, ukážeme vám, jak nakonfigurovat poměr, **vytvořit PNG** obrázky čárového kódu a **uložit obrázek čárového kódu** na disk. Ať už vytváříte štítky zásob, přepravní štítky nebo jakoukoli aplikaci, která vyžaduje vlastní stylizovaný čárový kód CODE_128, najdete zde vše, co potřebujete.

## Rychlé odpovědi
- **Co je poměr široké‑úzké?** Řídí relativní šířku širokých pruhů oproti úzkým pruhům v čárovém kódu.  
- **Která symbologie podporuje úpravu poměru?** Většina 1‑D symbologií, včetně CODE_128, umožňuje nastavit vlastní poměr.  
- **Potřebuji licenci?** K dispozici je bezplatná zkušební verze, ale pro produkční použití je vyžadována komerční licence.  
- **Mohu vygenerovat obrázek čárového kódu ve formátu PNG?** Ano — použijte `generator.save(...)` k vytvoření PNG obrázků čárového kódu.  
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

## Co je poměr široké‑úzké a proč jej upravovat?

Poměr široké‑úzké určuje, jak silně „široké“ pruhy vypadají ve srovnání s „úzkými“. Úprava tohoto poměru může zlepšit čitelnost skenerem, splnit specifické tiskové standardy nebo jednoduše odpovídat vizuálnímu stylu značky.

## Jak vytvořit čárový kód code128 s poměrem široké‑úzké v Javě

Níže je **krok‑za‑krokem průvodce čárovým kódem**, který vás provede každým krokem procesu.

### Krok 1: Nastavte adresář dokumentu

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Ujistěte se, že adresář existuje a máte oprávnění k zápisu; sem bude umístěn soubor **uložit obrázek čárového kódu**.

### Krok 2: Vytvořte objekt Barcode

```java
// Instantiate barcode object
// Create an instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

Zde **vytvoříme code128 čárový kód** předáním `EncodeTypes.CODE_128` do konstruktoru.

### Krok 3: Nastavte poměr široké‑úzké

```java
// Set the wide to narrow ratio for the barcode
generator.getParameters().getBarcode().setWideNarrowRatio(3.0f);
```

Metoda `setWideNarrowRatio` vám umožní jemně doladit vizuální rozestupy. Hodnota `3.0f` znamená, že široký pruh je třikrát širší než úzký pruh.

### Krok 4: Uložte obrázek na disk

```java
// Save the image to disk in PNG format
generator.save(dataDir + "wideNarrowRatio.png");
```

Volání `save` **vygeneruje obrázek čárového kódu** a uloží jej jako PNG soubor, čímž dokončí krok **uložit obrázek čárového kódu**.

## Proč upravovat poměr široké‑úzké?

- **Kompatibilita se skenery:** Některé skenery upřednostňují poměr mezi 2.0 a 3.0 pro optimální četnost.  
- **Kvalita tisku:** Úprava poměru může kompenzovat omezení DPI tiskárny a zabránit deformaci pruhů.  
- **Konzistence značky:** Některé společnosti chtějí čárové kódy, které vizuálně ladí s firemními barvami nebo designovými směrnicemi.

## Časté problémy a řešení

| Problém | Důvod | Řešení |
|---------|-------|--------|
| Čárový kód vypadá deformovaně | Poměr je příliš vysoký/nízký pro tiskárnu | Upravit hodnotu předanou metodě `setWideNarrowRatio` (např. 2.0‑2.5). |
| Soubor nebyl vytvořen | Neplatná cesta `dataDir` nebo nedostatečná oprávnění | Ověřit cestu k adresáři a zajistit, aby aplikace měla právo zápisu. |
| Skener nedokáže čárový kód přečíst | Poměr mimo doporučený rozsah pro symbologii | Použít standardní poměry (2.0‑3.0) nebo testovat s cílovým skenerem. |

## Často kladené otázky

**Q: Mohu použít Aspose.BarCode s jinými Java frameworky?**  
A: Ano, Aspose.BarCode je navržen tak, aby bez problémů fungoval se Spring, Java EE, Android a dalšími Java prostředími.

**Q: Jak mohu generovat čárové kódy s různými symbologiemi?**  
A: Jednoduše změňte typ symbologie v konstruktoru `BarcodeGenerator`, například `EncodeTypes.QR` pro QR kódy.

**Q: Je k dispozici zkušební verze Aspose.BarCode?**  
A: Ano, bezplatnou zkušební verzi získáte [zde](https://releases.aspose.com/).

**Q: Kde najdu podrobnou dokumentaci k Aspose.BarCode?**  
A: Dokumentaci najdete [zde](https://reference.aspose.com/barcode/java/).

**Q: Jak získat podporu pro Aspose.BarCode?**  
A: Navštivte fórum Aspose.BarCode [zde](https://forum.aspose.com/c/barcode/13) pro podporu a komunitní diskuse.

---

**Poslední aktualizace:** 2026-02-12  
**Testováno s:** Aspose.BarCode pro Java 24.11 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}