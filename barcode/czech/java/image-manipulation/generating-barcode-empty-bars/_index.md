---
date: 2025-12-22
description: Naučte se, jak vytvořit obrázek čárového kódu s prázdnými pruhy pomocí
  Aspose.BarCode pro Javu. Tento krok‑za‑krokem příklad generování čárových kódů vám
  pomůže rychle vytvořit čárový kód v Javě.
linktitle: Generating Barcode with Empty Bars
second_title: Aspose.BarCode Java API
title: Jak vytvořit obrázek čárového kódu s prázdnými pruhy v Javě
url: /cs/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit obrázek čárového kódu s prázdnými pruhy v Javě

## Úvod

V moderních Java aplikacích je schopnost **create barcode image** souborů za běhu cennou funkcí pro řízení zásob, systémy vstupenek a mnoho dalších obchodních scénářů. Aspose.BarCode pro Java poskytuje výkonné, snadno použitelné API, které vám umožní generovat vysoce kvalitní čárové kódy během několika řádků kódu. V tomto tutoriálu vás provedeme **step‑by‑step barcode** procesem tvorby, který vytváří čárový kód s prázdnými (nevyplněnými) pruhy, ideální pro designy vyžadující dutý vzhled.

## Rychlé odpovědi
- **Co znamená “empty bars”?** Pruhy jsou vykresleny bez výchozího plného výplně, což dává dutý vzhled.  
- **Jaký typ čárového kódu se používá?** Code 128 (rozšířená lineární symbologie).  
- **Potřebuji licenci pro vyzkoušení?** Je k dispozici bezplatná zkušební verze; licence je vyžadována pro produkční použití.  
- **Jaké výstupní formáty jsou podporovány?** PNG, JPEG, BMP, GIF, TIFF a další.  
- **Je to kompatibilní se všemi verzemi Javy?** Ano, knihovna funguje s Java 8 a novějšími.

## Co je create barcode image?
Vytvoření obrázku čárového kódu znamená převod řetězce dat na vizuální reprezentaci, kterou skenery mohou číst. Výsledný obrázek lze uložit jako PNG, JPEG nebo jiné běžné formáty a vložit do PDF, vytisknout na štítky nebo zobrazit v uživatelském rozhraní.

## Proč používat knihovnu Aspose.BarCode pro Java?
- **Bohatá sada funkcí** – podporuje více než 50 symbologií čárových kódů, včetně Code , QR, DataMatrix a dalších.  
- **Detailní kontrola** – vlastnosti jako `FilledBars`, barvy, okraje a velikost obrázku jsou snadno konfigurovatelné.  
- **Žádné externí závislosti** – jediný soubor JAR řeší vše, což usnadňuje nasazení.  
- **Komplexní dokumentace** – příklady, reference API a fóra vám pomohou rychle se zorientovat.

## Předpoklady

Než se pustíme do generování čárových kódů, ujistěte se, že máte následující předpoklady:

1. **Java vývojové prostředí** – Ujistěte se, že máte nainstalovanou Javu 8+ a kompatibilní IDE nebo nástroj pro sestavení.  
2. **Knihovna Aspose.BarCode pro Java** – Stáhněte a nainstalujte knihovnu Aspose.BarCode pro Java ze [stránky ke stažení](https://releases.aspose.com/barcode/java/).  
3. **Adresář dokumentů** – Vytvořte adresář ve vašem systému pro uložení vygenerovaného obrázku čárového kódu.

## Import balíčků

Ve vašem Java projektu importujte potřebné balíčky pro práci s Aspose.BarCode:

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Jak vytvořit obrázek čárového kódu s prázdnými pruhy

### Krok 1: Nastavte adresář zdrojů

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Nahraďte `"Your Document Directory"` skutečnou cestou, kam chcete uložit výstupní soubor.

### Krok 2: Vytvořte instanci Barcode Generator (Code128 Barcode Java)

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

Zde používáme symbologii **Code 128**—jednu z nejoblíbenějších lineárních čárových kódů—což dělá z tohoto klasického příkladu **code128 barcode java**.

### Krok 3: Nastavte vlastnost FilledBars na False

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

Nastavení `FilledBars` na `false` říká Aspose.BarCode, aby vykreslil pruhy jako prázdné (duté) tvary místo plných bloků.

### Krok 4: Uložte obrázek čárového kódu

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

Obrázek je uložen ve formátu PNG, ale můžete změnit výčet `BarCodeImageFormat` pro vytvoření JPEG, BMP nebo jiných podporovaných typů.

Opakujte tyto kroky ve vaší Java aplikaci, abyste snadno **create barcode image** soubory s prázdnými pruhy pomocí Aspose.BarCode pro Java.

## Závěr

Na závěr, tento tutoriál vás provedl procesem **step‑by‑step barcode** tvorby, který ukazuje, jak **create barcode image** soubory s prázdnými pruhy v Javě. Díky intuitivnímu API a rozsáhlým možnostem přizpůsobení Aspose.BarCode zjednodušuje integraci čárových kódů, což z něj činí cenný nástroj pro vývojáře, kteří potřebují spolehlivou **java barcode library**.

## Často kladené otázky

### Je Aspose.BarCode kompatibilní se všemi vývojovými prostředími Java?
Ano, Aspose.BarCode je navržen tak, aby se bez problémů integroval s různými vývojovými prostředími Java.

### Mohu přizpůsobit vzhled vygenerovaného čárového kódu?
Rozhodně! Aspose.BarCode poskytuje řadu možností přizpůsobení, které vám umožní upravit čárový kód podle vašich konkrétních potřeb.

### Je k dispozici zkušební verze pro Aspose.BarCode?
Ano, můžete prozkoumat možnosti Aspose.BarCode získáním bezplatné zkušební verze [zde](https://releases.aspose.com/).

### Jak mohu získat podporu pro Aspose.BarCode?
Pro jakékoli dotazy nebo pomoc navštivte [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

### Kde najdu podrobnou dokumentaci pro Aspose.BarCode?
Komplexní dokumentace je k dispozici [zde](https://reference.aspose.com/barcode/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-22  
**Tested With:** Aspose.BarCode Java 24.11 (latest)  
**Author:** Aspose