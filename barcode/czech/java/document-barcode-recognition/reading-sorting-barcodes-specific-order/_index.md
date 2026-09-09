---
date: 2026-04-08
description: Naučte se číst čárové kódy a řadit je v konkrétním pořadí pomocí Aspose.BarCode
  pro Javu. Tento průvodce krok za krokem ukazuje, jak používat Aspose, Java čtečku
  čárových kódů a dekódovat čárový kód Code128.
keywords:
- how to read barcodes
- java barcode reader
- aspose barcode java
linktitle: Čtení a řazení čárových kódů ve specifickém pořadí
second_title: Aspose.BarCode Java API
title: Jak číst čárové kódy v konkrétním pořadí pomocí Javy
url: /cs/java/document-barcode-recognition/reading-sorting-barcodes-specific-order/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak číst čárové kódy v konkrétním pořadí pomocí Javy


## Úvod

Pokud potřebujete **jak číst čárové kódy** a poté je uspořádat v konkrétním pořadí, Aspose.BarCode pro Javu vám poskytuje čistý, výkonný způsob, jak to provést. V mnoha Java aplikacích—systémech inventarizace, přepravních řešeních nebo pokladních terminálech—je čtení více čárových kódů a jejich řazení podle textové hodnoty častým požadavkem. Tento tutoriál vás provede celým procesem, od nastavení prostředí až po zobrazení seřazených výsledků, takže můžete rychle a jistě integrovat práci s čárovými kódy.

## Rychlé odpovědi
- **Jaká knihovna zpracovává čtení čárových kódů?** Aspose.BarCode for Java  
- **Jaký typ čárového kódu je použit v příkladu?** CODE_128  
- **Potřebuji licenci pro vývoj?** Dočasná licence funguje pro testování; plná licence je vyžadována pro produkci.  
- **Mohu řadit podle jiných kritérií?** Ano — upravit komparátor pro řazení podle umístění, důvěryhodnosti atd.  
- **Jaká verze Javy je vyžadována?** Java 8 nebo novější (jakýkoli JDK, který podporuje knihovnu Aspose).

## Co znamená „jak číst čárové kódy“ v Javě?

Čtení čárových kódů znamená dekódování vizuálního vzoru do původního datového řetězce. Aspose.BarCode poskytuje třídu `BarCodeReader`, která abstrahuje nízkoúrovňové zpracování obrazu, takže se můžete soustředit na obchodní logiku, jako je řazení nebo validace.

## Proč používat Aspose.BarCode pro Javu?

- **Robustní dekódování** – podporuje více než 50 symbologií, včetně Code 128, QR, DataMatrix a dalších.  
- **Vysoká přesnost** – optimalizované algoritmy snižují chybné čtení i u nízkokvalitních obrázků.  
- **Jednoduché API** – několik řádků kódu vás provede od obrázku k textu.  
- **Cross‑platform** – funguje na jakémkoli Java runtime, od desktopu po serverová prostředí.

## Předpoklady

Předtím, než se ponoříte do kódu, ujistěte se, že máte následující předpoklady:

- Java Development Kit (JDK): Aspose.BarCode for Java vyžaduje funkční JDK. Nejnovější verzi můžete stáhnout [zde](https://www.oracle.com/java/technologies/javase-downloads.html).

- Aspose.BarCode Library: Ujistěte se, že máte knihovnu Aspose.BarCode. Získáte ji z [odkazu ke stažení](https://releases.aspose.com/barcode/java/).

## Importování balíčků

Začněte importováním potřebných balíčků do vašeho Java projektu. Tyto balíčky poskytují základní třídy a metody pro práci s čárovými kódy.

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;

import java.awt.Point;
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;
```

Nyní si rozebráme kód krok za krokem:

## Krok 1: Nastavení adresáře zdrojů

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Nahraďte `"Your Document Directory"` skutečnou cestou k vašemu adresáři dokumentů.

## Krok 2: Zadejte cestu k obrázku čárového kódu a inicializujte čtečku

```java
String path = dataDir + "barcode.png";
List<FoundBarCodes> found = new ArrayList<FoundBarCodes>();

// Initialize BarCodeReader with the specified path and decode type
BarCodeReader reader = new BarCodeReader(path, DecodeType.CODE_128);
```

## Krok 3: Čtení čárových kódů a uložení výsledků

```java
// Iterate through barcodes and store results
for (BarCodeResult result : reader.readBarCodes()) {
    found.add(new FoundBarCodes(result.getCodeText(), result.getRegion()));
}
```

## Krok 4: Definice komparátoru pro řazení

```java
// Define a comparator for sorting barcodes based on code text
Comparator<FoundBarCodes> foundComparator = new Comparator<FoundBarCodes>() {
    @Override
    public int compare(FoundBarCodes e1, FoundBarCodes e2) {
        return e1.getCodeText().compareTo(e2.getCodeText());
    }
};
```

## Krok 5: Řazení čárových kódů

```java
// Sort the list of barcodes using the defined comparator
found.sort(foundComparator);
```

## Krok 6: Zobrazení seřazených čárových kódů

```java
// Display sorted barcodes with their coordinates
int i = 1;
for (FoundBarCodes barcode : found) {
    Point[] point = barcode.BarCodeRegion.getPoints();
    System.out.println("Codetext ( " + i + " ): " + barcode.CodeText);
    System.out.println("Top left coordinates: X = " + point[0].getX() + ", Y = " + point[0].getY());
    System.out.println("Bottom left coordinates: X = " + point[1].getX() + ", Y = " + point[1].getY());
    System.out.println("Bottom right coordinates: X = " + point[2].getX() + ", Y = " + point[2].getY());
    System.out.println("Top right coordinates: X = " + point[3].getX() + ", Y = " + point[3].getY());
    System.out.println();
    i++;
}
```

## Časté úskalí a tipy

- **Nesprávná cesta k obrázku** – zkontrolujte, že `dataDir` končí oddělovačem souborů (`/` nebo `\\`), aby se celá cesta správně vyřešila.  
- **Není podporovaný typ čárového kódu** – pokud potřebujete dekódovat jinou symbologii, změňte `DecodeType.CODE_128` na odpovídající hodnotu enumu (např. `DecodeType.QR`).  
- **Řazení podle číselné hodnoty** – výchozí komparátor řadí lexikograficky. Pro číselné řazení převádějte `CodeText` na celé číslo uvnitř komparátoru.  
- **Uvolnění zdrojů** – `BarCodeReader` implementuje `Closeable`. V produkčním kódu jej obalte do bloku try‑with‑resources, aby byl podkladový stream uvolněn.

## Často kladené otázky

### Otázka: Kde najdu dokumentaci k Aspose.BarCode pro Javu?
Dokumentace je k dispozici [zde](https://reference.aspose.com/barcode/java/).

### Otázka: Jak si mohu stáhnout Aspose.BarCode pro Javu?
Můžete si jej stáhnout z [odkazu ke stažení](https://releases.aspose.com/barcode/java/).

### Otázka: Je k dispozici bezplatná zkušební verze?
Ano, můžete vyzkoušet bezplatnou verzi [zde](https://releases.aspose.com/).

### Otázka: Jak získám informace o dočasné licenci?
Dočasné licence lze získat [zde](https://purchase.aspose.com/temporary-license/).

### Otázka: Kde mohu získat podporu nebo položit otázky?
Navštivte fórum podpory [zde](https://forum.aspose.com/c/barcode/13).

---

**Last Updated:** 2026-04-08  
**Tested With:** Aspose.BarCode 24.10 for Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}