---
category: general
date: 2026-10-15
description: Vytvořte čárový kód ze řetězce v Pythonu pomocí Aspose.BarCode, naučte
  se generovat čárový kód Code 128 a uložit jej jako PNG během několika řádků.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from string
- generate code 128 barcode
- how to save barcode
- generate barcode png
- encode data into barcode
language: cs
lastmod: 2026-10-15
og_description: Vytvořte čárový kód ze řetězce v Pythonu, který zakóduje data do čárového
  kódu Code 128, a uložte jej jako soubor PNG pomocí Aspose.BarCode.
og_image_alt: Screenshot of a generated Code 128 barcode saved as a PNG image
og_title: Vytvořte čárový kód ze řetězce v Pythonu – krok za krokem
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode from string in Python using Aspose.BarCode, learn how
    to generate Code 128 barcode and save barcode PNG in just a few lines.
  headline: Create barcode from string in Python with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Replace `EncodeTypes.CODE_128` with another enum value such as `EncodeTypes.QR`,
      `EncodeTypes.EAN_13`, or `EncodeTypes.PDF_417`. The rest of the code remains
      the same.
    question: What if I need a different symbology?
  - answer: Code 128 supports the full 128‑character ASCII set. For Unicode data,
      consider using QR Code (`EncodeTypes.QR`) which handles UTF‑8 natively.
    question: Can I generate a barcode from non‑ASCII characters?
  - answer: Pass a different member of `BarCodeImageFormat` to `save`, e.g., `BarCodeImageFormat.JPEG`
      or `BarCodeImageFormat.BMP`.
    question: How do I change the image format?
  - answer: Wrap the `save` call in a try/except block and handle `PermissionError`
      gracefully, perhaps by prompting the user for an alternative path.
    question: What if the output directory is read‑only?
  type: FAQPage
tags:
- barcode
- Python
- Aspose
- Code128
title: Vytvořte čárový kód ze řetězce v Pythonu pomocí Aspose.BarCode
url: /cs/python-java/general/create-barcode-from-string-in-python-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření čárového kódu ze řetězce v Pythonu s Aspose.BarCode

Pokud potřebujete **vytvořit čárový kód ze řetězce** v Pythonu, tento průvodce vám ukáže přesné kroky s Aspose.BarCode. Naučíte se, jak **vygenerovat Code 128 čárový kód**, upravit jeho vzhled a **uložit čárový kód PNG** na disk. Řešení funguje na jakékoli platformě, která podporuje Python 3.9+, a vyžaduje jen několik řádků kódu.

Programatické generování čárových kódů eliminuje chyby při ručním zadávání a zjednodušuje pracovní postupy, jako je sledování zásob, vydávání vstupenek a tisk štítků. Na konci tohoto tutoriálu budete schopni **zakódovat data do čárového kódu**, přizpůsobit rozměry a uložit obrázek kamkoli potřebujete.

## Požadavky

- Nainstalovaný Python 3.9 nebo novější  
- Přístup k internetu pro stažení balíčku Aspose.BarCode  
- Oprávnění k zápisu do adresáře, kam budete ukládat soubor PNG  

Pokud používáte virtuální prostředí (vysoce doporučeno), aktivujte jej nyní.

## Instalace Python balíčku Aspose.BarCode

Aspose poskytuje čistě Python knihovnu, která zpracovává všechny běžné symbologie čárových kódů, včetně Code 128. Nainstalujte ji pomocí pip:

```bash
pip install aspose-barcode
```

*Tip:* Připněte (pin) verzi (např. `aspose-barcode==23.9`), abyste se vyhnuli neočekávaným breaking changes v produkci.

## Vytvoření čárového kódu ze řetězce v Pythonu

Prvním funkčním krokem je importovat požadované třídy a vytvořit generátor pro požadovanou symbologii. Tento příklad používá **Code 128**, který je ideální pro alfanumerická data.

```python
# Step 1: Import the Aspose.BarCode classes
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Create a generator for Code 128 and provide the data string
barcode_generator = BarcodeGenerator(EncodeTypes.CODE_128, "1234567890")
```

**Proč je to důležité:** `EncodeTypes.CODE_128` říká knihovně, který standard čárového kódu použít, zatímco druhý argument (`"1234567890"`) je **řetězec, který chcete zakódovat do čárového kódu**. Můžete jej nahradit libovolným ASCII řetězcem až do 80 znaků pro Code 128.

## Generování Code 128 čárového kódu

Jakmile je generátor připraven, můžete vytvořit obrázek čárového kódu v paměti. Knihovna automaticky vykreslí čárový kód na základě poskytnutých dat.

```python
# Step 3: Render the barcode to an image object (in memory)
barcode_image = barcode_generator.generate_barcode_image()
```

V tomto okamžiku je `barcode_image` instancí `System.Drawing.Image` (na Windows) nebo kompatibilním objektem obrázku na jiných platformách. Můžete jej zobrazit přímo v GUI, vložit do PDF nebo pokračovat v jeho úpravách.

## Úprava vzhledu čárového kódu

Doladění vizuálních vlastností zajišťuje spolehlivé načítání čárového kódu ve vašem konkrétním prostředí. Běžné úpravy zahrnují X‑dimenzi (šířku nejtenčího pruhu) a celkovou výšku pruhu.

```python
# Step 4: Adjust appearance – X dimension and bar height
barcode_generator.parameters.barcode.x_dimension.pixels = 2   # width of the smallest bar
barcode_generator.parameters.barcode.bar_height.pixels = 100  # height of the bars (optional)
```

*Proč upravovat tyto hodnoty?*  
- **X dimenze** ovlivňuje hustotu čárového kódu; menší hodnota vede k kompaktnějšímu kódu, který se vejde na malé štítky.  
- **Výška pruhu** ovlivňuje čitelnost; vyšší pruhy jsou snazší pro skenery detekovat z větší vzdálenosti.

Můžete také změnit barvy, přidat okraje nebo vložit lidsky čitelný text pomocí objektu `parameters`. Kompletní seznam možností najdete v dokumentaci Aspose.BarCode.

## Jak uložit čárový kód jako PNG

Uložení vygenerovaného obrázku je posledním krokem v pracovním postupu **vytvořit čárový kód ze řetězce**. Knihovna podporuje několik formátů; PNG je bezztrátový a široce podporovaný.

```python
# Step 5: Save the barcode image to a PNG file
output_path = "output/barcode.png"
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

Metoda `save` zapíše obrázek do souborového systému pomocí formátu, který specifikujete. Pokud cílový adresář (`output/` v tomto příkladu) neexistuje, Python vyvolá `FileNotFoundError`. Vytvořte adresář předem nebo ošetřete výjimku:

```python
import os

output_dir = os.path.dirname(output_path)
os.makedirs(output_dir, exist_ok=True)   # ensures the directory exists
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

**Očekávaný výsledek:** Po spuštění skriptu `output/barcode.png` obsahuje čistý Code 128 čárový kód, který zakóduje `"1234567890"`. Otevřením souboru v libovolném prohlížeči obrázků uvidíte černobílý čárový kód připravený ke skenování.

## Kompletní, spustitelný příklad

Spojením všech částí dohromady zde máte samostatný skript, který můžete zkopírovat, vložit a spustit:

```python
"""
Complete example: create barcode from string, generate Code 128 barcode,
customize appearance, and save barcode PNG using Aspose.BarCode.
"""

import os
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1. Define input data and output location
data_to_encode = "1234567890"
output_path = "output/barcode.png"

# 2. Ensure the output directory exists
os.makedirs(os.path.dirname(output_path), exist_ok=True)

# 3. Initialise the generator for Code 128
generator = BarcodeGenerator(EncodeTypes.CODE_128, data_to_encode)

# 4. Optional: tweak visual parameters
generator.parameters.barcode.x_dimension.pixels = 2
generator.parameters.barcode.bar_height.pixels = 100

# 5. Save as PNG
generator.save(output_path, BarCodeImageFormat.PNG)

print(f"Barcode saved to {output_path}")
```

Spusťte skript pomocí `python create_barcode.py`. Pokud je vše správně nainstalováno, uvidíte:

```
Barcode saved to output/barcode.png
```

Otevřete soubor PNG a ověřte, že čárový kód odpovídá původnímu řetězci pomocí libovolné aplikace pro skenování čárových kódů.

## Časté otázky a okrajové případy

- **Co když potřebuji jinou symbologii?**  
  Nahraďte `EncodeTypes.CODE_128` jinou hodnotou enumu, například `EncodeTypes.QR`, `EncodeTypes.EAN_13` nebo `EncodeTypes.PDF_417`. Zbytek kódu zůstane stejný.

- **Mohu generovat čárový kód z ne‑ASCII znaků?**  
  Code 128 podporuje kompletní 128‑znakovou ASCII sadu. Pro Unicode data zvažte použití QR Code (`EncodeTypes.QR`), který nativně pracuje s UTF‑8.

- **Jak změním formát obrázku?**  
  Předávejte jiný člen `BarCodeImageFormat` metodě `save`, např. `BarCodeImageFormat.JPEG` nebo `BarCodeImageFormat.BMP`.

- **Co když je výstupní adresář jen pro čtení?**  
  Zabalte volání `save` do bloku try/except a ošetřete `PermissionError` elegantně, například vyzváním uživatele k zadání alternativní cesty.

- **Tip pro výkon:**  
  Generování tisíců čárových kódů v cyklu může být náročné na CPU. Znovu použijte jedinou instanci `BarcodeGenerator` a pouze aktualizujte `generator.parameters.barcode.code_text` mezi iteracemi.

## Závěr

Nyní víte, jak **vytvořit čárový kód ze řetězce** v Pythonu pomocí Aspose.BarCode, **vygenerovat Code 128 čárový kód**, přizpůsobit jeho velikost a **uložit čárový kód PNG** na disk. Toto end‑to‑end řešení vám umožní **zakódovat data do čárového kódu** rychle a spolehlivě, což usnadňuje integraci čárových kódů do inventárních systémů, platform pro vstupenky nebo jakékoli aplikace vyžadující strojově čitelné identifikátory.

**Další kroky**

- Prozkoumejte další symbologie (`generate code 128 barcode` alternativy) jako QR nebo DataMatrix.  
- Přidejte logiku ošetření chyb, aby byl skript odolný pro produkční použití (`how to save barcode` selhání).  
- Vložte vygenerovaný PNG do PDF nebo HTML reportů (`generate barcode png` pro web).  

Šťastné kódování a užívejte si jednoduchost programového generování čárových kódů!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vygenerovat Code 128 čárový kód a uložit obrázek čárového kódu pomocí Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [Jak vygenerovat QR Code obrázek v Pythonu s Aspose.Barcode – Kompletní průvodce](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Vytvořit barcode png v Pythonu – Kompletní Aspose.Barcode průvodce](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}