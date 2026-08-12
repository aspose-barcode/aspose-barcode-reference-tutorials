---
category: general
date: 2026-08-12
description: Rychle nakonfigurujte rozložení čárového kódu Databar v Pythonu. Naučte
  se nastavit sloupce, řádky a ukládat obrázky pomocí knihovny generátoru čárových
  kódů.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- configure databar barcode layout
- Databar Expanded Stacked
- barcode generator Python
- set barcode columns
- set barcode rows
language: cs
lastmod: 2026-08-12
og_description: Nakonfigurujte rozložení čárových kódů Databar v Pythonu, abyste ovládali
  sloupce, řádky a výstup obrázku. Postupujte podle tohoto návodu pro připravené řešení
  připravené k okamžitému spuštění.
og_image_alt: Screenshot of a Databar Expanded Stacked barcode with custom column
  layout
og_title: Konfigurace rozložení čárového kódu Databar v Pythonu – kompletní tutoriál
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  headline: Configure Databar barcode layout in Python – step‑by‑step guide
  type: TechArticle
- description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  name: Configure Databar barcode layout in Python – step‑by‑step guide
  steps:
  - name: Import the required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: Create a barcode generator for Databar Expanded Stacked
    text: '```python # Initialize the generator with the desired symbology and value
      barcode_generator = BarcodeGenerator( EncodeTypes.DatabarExpandedStacked, "Databar
      Expanded Stacked long" ) ```'
  - name: Set the number of columns (horizontal layout)
    text: '```python # Configure the layout to use 4 columns barcode_generator.parameters.barcode.data_bar.columns
      = 4 ```'
  - name: Save the barcode image with the column layout
    text: '```python # Save the image as a PNG file barcode_generator.save("output/ExpandedCols4.png",
      BarCodeImageFormat.Png) ```'
  - name: Create a second generator for the same barcode type (row layout)
    text: If you prefer a vertical stack, you work with rows instead of columns. The
      code below re‑uses the same value but creates a fresh `BarcodeGenerator` instance
      to avoid mixing column and row settings.
  - name: Set the number of rows (vertical layout)
    text: '```python # Configure the layout to use 3 rows barcode_generator.parameters.barcode.data_bar.rows
      = 3 ```'
  - name: Save the barcode image with the row layout
    text: '```python # Save the vertically stacked barcode barcode_generator.save("output/ExpandedRows3.png",
      BarCodeImageFormat.Png) ```'
  type: HowTo
tags:
- barcode
- Python
- Databar
- image generation
title: Nastavte rozložení čárového kódu Databar v Pythonu – krok za krokem
url: /cs/python-java/general/configure-databar-barcode-layout-in-python-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení rozložení čárového kódu Databar v Pythonu – krok za krokem

Pokud potřebujete **nastavit rozložení čárového kódu Databar v Pythonu**, tento průvodce vás provede celým procesem. Uvidíte, jak nastavit počet sloupců nebo řádků pro čárový kód Databar Expanded Stacked a jak uložit výsledný obrázek jediným voláním knihovny pro generování čárových kódů.

Řízení rozložení je nezbytné, když vkládáte čárové kódy na úzké obaly, účtenky nebo mobilní obrazovky. V následujících sekcích pokryjeme potřebné importy, dvě možnosti rozložení (sloupce a řádky) a osvědčené postupy pro uložení čistého PNG obrázku.

## Co budete potřebovat

* Python 3.8 nebo novější
* `aspose.barcode` (nebo jakýkoli kompatibilní balíček pro generování čárových kódů) nainstalovaný  
  ```bash
  pip install aspose-barcode
  ```
* Oprávnění k zápisu do složky, kde budou PNG soubory uloženy

Žádné další externí nástroje nejsou vyžadovány – knihovna interně zajišťuje vykreslování, škálování a kódování obrázku.

## Jak nastavit rozložení čárového kódu Databar v Pythonu

Jádrem řešení je třída `BarcodeGenerator`. Přijímá výčtový typ `EncodeTypes`, který určuje symbologii čárového kódu – v tomto případě `EncodeTypes.DatabarExpandedStacked`. Po vytvoření generátoru můžete upravit rozložení nastavením vlastností `columns` nebo `rows` na objektu parametru `data_bar`.

### Krok 1: Importujte požadované třídy

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

Tyto importy vám poskytují přístup k generátoru, výčtu pro typy Databar a konstantě formátu obrázku PNG.

### Krok 2: Vytvořte generátor čárového kódu pro Databar Expanded Stacked

```python
# Initialize the generator with the desired symbology and value
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

*Proč tento krok?*  
`EncodeTypes.DatabarExpandedStacked` říká knihovně, aby vytvořila symbologii **Databar Expanded Stacked**, která podporuje delší číselné řetězce při zachování kompaktního rozměru. Druhý argument jsou data k zakódování; může to být jakýkoli řetězec splňující specifikaci Databar.

### Krok 3: Nastavte počet sloupců (horizontální rozložení)

```python
# Configure the layout to use 4 columns
barcode_generator.parameters.barcode.data_bar.columns = 4
```

**set barcode columns** je klíčová fráze pro tuto operaci. Když zvýšíte počet sloupců, čárový kód se rozprostře horizontálně, což může být užitečné pro široké štítky. Knihovna automaticky přepočítá šířku modulu, aby zachovala celkovou velikost konzistentní.

#### Tip
Maximální počet sloupců pro Databar Expanded Stacked je 8. Nastavení hodnoty vyšší než limit ji ořízne na maximum, ale je lepší vstup předem ověřit.

### Krok 4: Uložte obrázek čárového kódu s rozložením sloupců

```python
# Save the image as a PNG file
barcode_generator.save("output/ExpandedCols4.png", BarCodeImageFormat.Png)
```

**save barcode image** je akce, která zapíše vykreslený čárový kód na disk. PNG je bezztrátový formát, který zachovává ostré hrany potřebné pro spolehlivé skenování.

### Krok 5: Vytvořte druhý generátor pro stejný typ čárového kódu (rozložení řádků)

Pokud dáváte přednost vertikálnímu uspořádání, pracujete s řádky místo sloupců. Níže uvedený kód znovu použije stejnou hodnotu, ale vytvoří novou instanci `BarcodeGenerator`, aby nedocházelo k míchání nastavení sloupců a řádků.

```python
# New generator instance for row configuration
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

### Krok 6: Nastavte počet řádků (vertikální rozložení)

```python
# Configure the layout to use 3 rows
barcode_generator.parameters.barcode.data_bar.rows = 3
```

**set barcode rows** uspořádá moduly čárového kódu vertikálně. Rozložení se třemi řádky snižuje výšku každého jednotlivého stacku, což činí čárový kód vhodným pro úzké účtenky nebo mobilní obrazovky.

#### Okrajový případ
Pokud nastavíte `rows` na 1, knihovna vygeneruje jednoradý Databar (ekvivalent standardního Databar). Hodnoty pod 1 jsou ignorovány a resetovány na výchozí (1 řádek).

### Krok 7: Uložte obrázek čárového kódu s rozložením řádků

```python
# Save the vertically stacked barcode
barcode_generator.save("output/ExpandedRows3.png", BarCodeImageFormat.Png)
```

Opět **save barcode image** pomocí PNG, aby výstup zůstal ostrý.

## Kompletní spustitelný příklad

Sestavením všech částí dohromady získáte samostatný skript, který můžete vložit do libovolného Python projektu.

```python
# ------------------------------------------------------------
# configure_databar_layout.py
# Demonstrates how to configure Databar barcode layout in Python
# ------------------------------------------------------------

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# -----------------------------------------------------------------
# 1️⃣ Column layout – 4 columns
# -----------------------------------------------------------------
col_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
col_generator.parameters.barcode.data_bar.columns = 4   # set barcode columns
col_path = os.path.join(output_dir, "ExpandedCols4.png")
col_generator.save(col_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Column layout saved to {col_path}")

# -----------------------------------------------------------------
# 2️⃣ Row layout – 3 rows
# -----------------------------------------------------------------
row_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
row_generator.parameters.barcode.data_bar.rows = 3      # set barcode rows
row_path = os.path.join(output_dir, "ExpandedRows3.png")
row_generator.save(row_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Row layout saved to {row_path}")
```

**Očekávaný výstup**

Spuštěním skriptu se vytvoří dva PNG soubory:

* `output/ExpandedCols4.png` – čárový kód roztažený přes čtyři sloupce
* `output/ExpandedRows3.png` – čárový kód komprimovaný do tří řádků

Oba obrázky lze otevřít v libovolném prohlížeči obrázků nebo je přímo importovat do PDF faktur, šablon štítků či webových stránek.

## Časté otázky a řešení problémů

| Question | Answer |
|----------|--------|
| *Co když čárový kód vypadá rozmazaně?* | Zvyšte rozlišení obrázku nastavením `barcode_generator.parameters.image_width` a `image_height` před voláním `save`. |
| *Mohu použít jiné formáty obrázků?* | Ano. Nahraďte `BarCodeImageFormat.Png` za `Jpeg`, `Bmp` nebo `Gif` podle potřeby. |
| *Existuje limit délky dat?* | Databar Expanded Stacked podporuje až 74 číselných znaků. Překročení limitu vyvolá `ArgumentException`. |
| *Jak změním barvu popředí?* | Použijte `barcode_generator.parameters.barcode.color = Color.Blue` (importujte `System.Drawing.Color`). |
| *Mohu kombinovat sloupce a řádky?* | Ne. API považuje sloupce a řádky za vzájemně se vylučující režimy rozložení. Vyberte jeden pro každou instanci čárového kódu. |

## Další kroky

Nyní, když můžete **nastavit rozložení čárového kódu Databar**, zvažte prozkoumání těchto souvisejících témat:

* **Přidat textové popisky** – použijte `barcode_generator.parameters.barcode.code_text` k zobrazení zakódované hodnoty pod obrázkem.
* **Vložit čárový kód do PDF** – kombinujte vygenerovaný PNG s `aspose.pdf` pro vytvoření tisknutelných dokumentů.
* **Dynamické velikosti** – vypočítejte optimální počet sloupců nebo řádků na základě rozměrů štítku za běhu.
* **Dávkové zpracování** – projděte CSV soubor s kódy produktů a automaticky vygenerujte knihovnu obrázků čárových kódů.

Experimentujte s různými hodnotami sloupců a řádků, abyste viděli, jak ovlivňují spolehlivost skenování na vašich cílových zařízeních. Čím více testujete, tím lépe pochopíte kompromisy mezi velikostí čárového kódu, čitelností a prostorovými omezeními.

*Šťastné kódování! Pokud se vám tento tutoriál hodil, sdílejte ho se spolupracovníky nebo zanechte komentář o výzvách s rozložením, se kterými jste se setkali.*

## Co byste se měli učit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vlastních projektech.

- [Vytvořit obrázek čárového kódu DotCode – řádky a sloupce (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Vytvořit obrázek čárového kódu c# – nastavit řádky a sloupce Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Jednorozměrné nastavení výšky čárového kódu Databar](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}