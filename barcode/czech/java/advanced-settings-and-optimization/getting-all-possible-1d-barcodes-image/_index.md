---
date: 2025-11-29
description: Naučte se číst 1D čárové kódy v Javě s Aspose.BarCode – rychle dekódujte
  čárové kódy z obrázku pomocí robustní knihovny čárových kódů pro Javu.
language: cs
linktitle: read 1d barcodes java
second_title: Aspose.BarCode Java API
title: Jak číst 1D čárové kódy v Javě pomocí Aspose.BarCode
url: /java/advanced-settings-and-optimization/getting-all-possible-1d-barcodes-image/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# čtení 1D čárových kódů v Javě s Aspose.BarCode

## Úvod

V tomto praktickém průvodci se dozvíte, jak **číst 1D čárové kódy v Javě** pomocí výkonné knihovny **Aspose.BarCode**. Ať už potřebujete skenovat štítky produktů, inventární značky nebo jakýkoli lineární čárový kód vložený do obrázku, tento tutoriál vás provede všemi kroky – od nastavení prostředí až po extrakci všech možných čárových kódů, které obrázek obsahuje. Na konci budete schopni **dekódovat čárové kódy z obrázku** pomocí několika řádků Java kódu.

## Rychlé odpovědi
- **Co dělá Aspose.BarCode?** Poskytuje plnohodnotnou knihovnu čárových kódů pro Javu, která dokáže generovat i dekódovat 1D/2D čárové kódy.  
- **Mohu načíst více čárových kódů z jednoho obrázku?** Ano – metoda `BarCodeReader.readBarCodes()` vrací všechny detekované symboly.  
- **Potřebuji licenci pro vývoj?** Dočasná licence funguje pro testování; pro produkci je vyžadována komerční licence.  
- **Jaké verze Javy jsou podporovány?** Java 8 + (doporučeno JDK 11).  
- **Je tato knihovna dostatečně rychlá pro skenování v reálném čase?** Rozhodně – je optimalizována pro vysokovýkonné dávkové zpracování.

## Co je „čtení 1d čárových kódů v Javě“?

Čtení 1D čárových kódů v Javě znamená použití **knihovny čárových kódů pro Javu** k analýze obrázku, vyhledání lineárních vzorů čárových kódů a vrácení zakódovaného textu spolu s metadaty, jako je typ symbologie a orientace. Aspose.BarCode abstrahuje náročnou práci se zpracováním obrazu, takže se můžete soustředit na obchodní logiku.

## Proč zvolit Aspose.BarCode pro dekódování čárových kódů z obrázku?

- **Široká podpora symbologií** – více než 50 typů 1D a 2D.  
- **Přesná detekce** – funguje i u nízkokontrastních nebo otočených čárových kódů.  
- **Jednoduché API** – několik volání metod vám poskytne všechny výsledky.  
- **Žádné externí závislosti** – čistá Java, snadno vložitelná do jakéhokoli projektu.  

## Předpoklady

Než se ponoříme do kódu, ujistěte se, že máte následující:

- **Java Development Kit (JDK)** – verze 8 nebo novější. Stáhněte jej z oficiální [stránky Oracle JDK](https://www.oracle.com/java/technologies/javase-downloads.html).  
- **Aspose.BarCode pro Java** – stáhněte nejnovější JAR ze [stránky vydání Aspose](https://releases.aspose.com/barcode/java/).  

Nyní, když je vaše prostředí připravené, pojďme začít programovat.

## Import Namespaces

Přidejte požadované `import` příkazy, aby kompilátor mohl najít třídy Aspose.

```java
import java.awt.Point;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## Krok 1: Inicializace objektu BarCodeReader

Vytvořte instanci `BarCodeReader`, která ukazuje na váš soubor s obrázkem. Parametr `DecodeType` říká enginu, jaké symbologie má hledat; použití `CODE_128` jako příkladu funguje pro mnoho běžných 1D kódů.

```java
BarCodeReader reader = new BarCodeReader("path/to/your/image.png", DecodeType.CODE_128);
```

> **Tip:** Pokud chcete skenovat *všechny* podporované 1D typy, předávejte `DecodeType.ALL_1D` místo jedné symbologie.

## Krok 2: Načtení všech možných čárových kódů

Procházejte kolekci vrácenou metodou `readBarCodes()`. Pro každý `BarCodeResult` vypíšeme dekódovaný text, název symbologie, úhel detekce a čtyři souřadnice rohů oblasti čárového kódu.

```java
int iCount = 0;
for (BarCodeResult result : reader.readBarCodes()) {
    // Display code text, symbology, detected angle, recognition percentage of the barcode
    System.out.println("Code Text: " + result.getCodeText() + " Symbology: " + result.getCodeTypeName()
            + " Recognition percentage: " + result.getRegion().getAngle());

    // Display x and y coordinates of barcode detected
    Point[] point = result.getRegion().getPoints();

    System.out.println("Top left coordinates: X = " + point[0].getX() + ", Y = " + point[0].getY());
    System.out.println("Bottom left coordinates: X = " + point[1].getX() + ", Y = " + point[1].getY());
    System.out.println("Bottom right coordinates: X = " + point[2].getX() + ", Y = " + point[2].getY());
    System.out.println("Top right coordinates: X = " + point[3].getX() + ", Y = " + point[3].getY());

    iCount = iCount + 1;
}
```

Smyčka automaticky zpracuje každý nalezený čárový kód, takže není potřeba čtečku volat opakovaně. Po dokončení smyčky obsahuje `iCount` celkový počet detekovaných čárových kódů.

## Časté problémy a jak je vyřešit

| Příznak | Pravděpodobná příčina | Řešení |
|---------|-----------------------|--------|
| Žádné čárové kódy nebyly vráceny | Obrázek je příliš rozmazaný nebo má nízký kontrast | Před předáním čtečce předzpracujte obrázek (zvyšte kontrast, binarizujte). |
| Nesprávná symbologie | Použita nesprávná `DecodeType` | Použijte `DecodeType.ALL_1D`, aby engine automaticky detekoval jakýkoli 1D typ. |
| Úhly jsou nesprávné | Obrázek je otočen | API již vrací úhel rotace; můžete obrázek případně otočit zpět. |

## Často kladené otázky

**Q: Je Aspose.BarCode pro Java vhodný pro komerční projekty?**  
A: Ano. Komerční licence odstraňuje všechna omezení hodnocení a poskytuje plná práva na redistribuci.

**Q: Mohu knihovnu testovat bez zakoupení licence?**  
A: Rozhodně. Získejte dočasnou licenci na [stránce dočasné licence Aspose](https://purchase.aspose.com/temporary-license/) pro vývoj a testování.

**Q: Kde najdu úplnou referenci API?**  
A: Kompletní dokumentace je k dispozici [zde](https://reference.aspose.com/barcode/java/).

**Q: Jak získat pomoc, pokud narazím na problém?**  
A: Položte svůj dotaz na [fóru Aspose.BarCode](https://forum.aspose.com/c/barcode/13), kde vám pomůže komunita i inženýři Aspose.

**Q: Existuje bezplatná zkušební verze ke stažení?**  
A: Ano – můžete stáhnout zkušební verzi ze [stránky vydání Aspose](https://releases.aspose.com/).

## Závěr

Nyní jste se naučili, jak **číst 1D čárové kódy v Javě** pomocí Aspose.BarCode, robustní **knihovny čárových kódů pro Javu**, která usnadňuje a spolehlivě provádí dekódování čárových kódů z obrazových souborů. Začleňte tento úryvek do svých aplikací pro automatizaci skenování zásob, ověřování vstupenek nebo jakéhokoli scénáře, kde se v obrázcích objevují lineární čárové kódy.

---

**Poslední aktualizace:** 2025-11-29  
**Testováno s:** Aspose.BarCode 24.11 for Java  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}