---
category: general
date: 2026-08-22
description: Naučte se generovat DataMatrix čárový kód v Pythonu a kódovat ruský text
  pomocí Aspose.BarCode – krok za krokem průvodce.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate DataMatrix barcode
- encode Russian text
language: cs
lastmod: 2026-08-22
og_description: Vygenerujte DataMatrix čárový kód v Pythonu a zakódujte ruský text
  pomocí Aspose.BarCode. Postupujte podle kompletního příkladu a spusťte jej okamžitě.
og_image_alt: Python script that generate DataMatrix barcode with encoded Russian
  text
og_title: Generování čárového kódu DataMatrix v Pythonu – kompletní tutoriál Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  headline: How to generate DataMatrix barcode in Python with Aspose.BarCode
  type: TechArticle
- description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  name: How to generate DataMatrix barcode in Python with Aspose.BarCode
  steps:
  - name: '**ABC123** – the plain identifier.'
    text: '**ABC123** – the plain identifier.'
  - name: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
    text: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
  - name: Open the PNG file in an image viewer.
    text: Open the PNG file in an image viewer.
  - name: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
    text: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
  - name: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
    text: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
  type: HowTo
tags:
- Aspose.BarCode
- Python
- barcode generation
title: Jak v Pythonu generovat DataMatrix čárový kód pomocí Aspose.BarCode
url: /cs/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vygenerovat DataMatrix čárový kód v Pythonu s Aspose.BarCode

Pokud potřebujete **vygenerovat DataMatrix čárový kód** v Pythonu a **zakódovat ruský text**, tento návod vám ukáže přesné kroky. Uvidíte kompletní, spustitelný příklad, který vytvoří rozšířený kódový text, nakonfiguruje čárový kód a uloží obrázek v jediném skriptu.

Vytváření čárových kódů obsahujících ne‑ASCII znaky často vyvolává otázky ohledně znakových sad a kódování dat. Pomocí `ExtCodetextBuilder` z Aspose.BarCode můžete bezpečně vložit UTF‑8 text, například cyrilické znaky, do symbolu DataMatrix. Výsledek funguje s jakýmkoli skenerem, který podporuje standard DataMatrix.

V tomto tutoriálu se naučíte:

* Nainstalovat požadovaný balíček Aspose.BarCode.
* Vytvořit rozšířený kódový text, který kombinuje prostá data a ruský text.
* **Vygenerovat DataMatrix čárový kód** s rozšířeným řetězcem.
* Upravit parametry čárového kódu, jako je velikost modulu.
* Uložit čárový kód jako PNG soubor.

Žádné externí služby nejsou potřeba; vše běží lokálně na vašem počítači.

## Požadavky

Než začnete, ujistěte se, že máte:

* Python 3.8 nebo novější nainstalovaný.
* Aktivní licenci Aspose.BarCode pro Python (bezplatná zkušební verze stačí pro vývoj).
* Základní znalosti skriptování v Pythonu.

Knihovnu Aspose.BarCode můžete nainstalovat pomocí pip:

```bash
pip install aspose-barcode
```

## Krok 1: Vytvořit rozšířený řetězec kódového textu

Prvním úkolem je vytvořit jeden řetězec, který obsahuje jak prostý identifikátor produktu, tak ruskou frázi. `ExtCodetextBuilder` vám umožní spojit různé části kódového textu a zachovat informace o jejich kódování.

```python
# Import required Aspose.BarCode classes
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

# Initialize the extended codetext builder
builder = ExtCodetextBuilder()

# Add a plain ASCII identifier – this could be a SKU, part number, etc.
builder.add_plain_codetext("ABC123")

# Add Russian text using ECI (Extended Channel Interpretation) encoding.
# The eci_encoding value 3 corresponds to UTF‑8.
builder.add_eci_codetext(eci_encoding=3, codetext="Привет")

# Retrieve the combined string that Aspose.BarCode will use.
extended_text = builder.get_extended_codetext()
print("Generated extended codetext:", extended_text)
```

**Proč je tento krok důležitý** – Symboly DataMatrix ukládají surové bajty. Když potřebujete kombinovat různé abecedy, musíte kodéru říct, která znaková sada platí pro každý segment. Metoda `add_eci_codetext` vloží před ruský text indikátor ECI, což zajistí, že skenery interpretují bajty jako UTF‑8. Bez ECI by se cyrilické znaky zobrazily jako poškozená data.

## Krok 2: Vytvořit generátor DataMatrix čárového kódu

Jakmile máte rozšířený kódový text připravený, vytvořte instanci `BarcodeGenerator` a specifikujte typ `EncodeTypes.DATA_MATRIX`.

```python
# Create a DataMatrix barcode generator using the extended codetext
generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)
```

**Proč DataMatrix?** – DataMatrix je dvourozměrný čárový kód, který může uložit až 2 335 alfanumerických znaků nebo 1 556 bajtů. Je ideální pro malé položky, průmyslové součásti a situace, kde potřebujete vložit vícejazyčný text.

## Krok 3: (Volitelné) Konfigurace parametrů čárového kódu

Aspose.BarCode nabízí mnoho parametrů. Pro většinu případů výchozí nastavení vytvoří čitelný symbol. Přesto můžete chtít ovládat velikost každého modulu (nejmenší čtvereček v mřížce), aby odpovídala požadavkům tisku.

```python
# Set the module (pixel) size to 2.5 points – adjust as needed for your printer DPI
generator.parameters.barcode.x_dimension = 2.5
```

Další užitečné parametry zahrnují úroveň korekce chyb, okraj a barvu pozadí. Upravujte je jen tehdy, když vaše cílové skenovací prostředí vyžaduje konkrétní tolerance.

## Krok 4: Uložit obrázek čárového kódu

Nakonec zapište čárový kód do souboru. Metoda `save` podporuje PNG, JPEG, BMP a několik vektorových formátů.

```python
# Save the barcode image to the desired folder
output_path = "YOUR_DIRECTORY/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

Když otevřete `extended_codetext.png`, uvidíte ostrý DataMatrix symbol. Skenováním standardním čtečkou DataMatrix získáte dvě části:

1. **ABC123** – prostý identifikátor.
2. **Привет** – ruský pozdrav, správně dekódovaný jako UTF‑8.

## Kompletní, spustitelný příklad

Níže je celý skript, který můžete zkopírovat do souboru pojmenovaného `generate_datamatrix.py`. Nahraďte `YOUR_DIRECTORY` existujícím adresářem ve vašem systému.

```python
# generate_datamatrix.py
# -------------------------------------------------
# Complete example: generate DataMatrix barcode and encode Russian text
# -------------------------------------------------

import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

def main():
    # Step 1: Build extended codetext
    builder = ExtCodetextBuilder()
    builder.add_plain_codetext("ABC123")
    builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_text = builder.get_extended_codetext()
    print("Generated extended codetext:", extended_text)

    # Step 2: Create DataMatrix generator
    generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)

    # Step 3: Optional parameters (adjust module size if needed)
    generator.parameters.barcode.x_dimension = 2.5

    # Step 4: Save the image
    output_path = "YOUR_DIRECTORY/extended_codetext.png"
    generator.save(output_path)
    print(f"Barcode saved as {output_path}")

if __name__ == "__main__":
    main()
```

Spusťte skript z příkazové řádky:

```bash
python generate_datamatrix.py
```

Měli byste vidět výstup v konzoli podobný tomuto:

```
Generated extended codetext: (ECI:3)ПриветABC123
Barcode saved as YOUR_DIRECTORY/extended_codetext.png
```

## Ověření výsledku

Pro potvrzení, že čárový kód správně kóduje ruskou frázi:

1. Otevřete PNG soubor v prohlížeči obrázků.
2. Použijte libovolnou aplikaci pro skenování DataMatrix (mnoho mobilních aplikací to podporuje) nebo hardwarový skener.
3. Dekódovaný řetězec by měl zobrazit `ABC123Привет` (nebo dvě části oddělené podle UI skeneru).

Pokud se ruské znaky zobrazí jako nesmyslné, zkontrolujte, že skener podporuje ECI UTF‑8. Většina moderních čteček to podporuje, ale starší zařízení mohou vyžadovat explicitní nastavení.

## Časté problémy a jak se jim vyhnout

| Problém | Příčina | Řešení |
|-------|-------|-----|
| Zkreslený cyrilický výstup | Chybějící indikátor ECI | Použijte `add_eci_codetext` s `eci_encoding=3`. |
| Čárový kód příliš malý pro tiskárnu | Výchozí velikost modulu příliš jemná pro nízké DPI | Zvyšte `x_dimension` (např. `3.0` nebo `4.0`). |
| Soubor se neuložil | Neplatná cesta adresáře | Ujistěte se, že `YOUR_DIRECTORY` existuje a je zapisovatelný. |
| Skener nedokáže přečíst | Přehnaná hustota dat | Snižte množství kódovaných dat nebo zvyšte úroveň korekce chyb (`generator.parameters.barcode.error_correction_level`). |

## Rozšíření příkladu

Můžete tento vzor přizpůsobit pro jiné jazyky nebo typy dat:

* **Kódovat japonský nebo arabský text** – změňte `eci_encoding` na odpovídající hodnotu (např. 5 pro ISO‑8859‑5, 6 pro ISO‑8859‑7).  
* **Přidat více ECI segmentů** – zavolejte `add_eci_codetext` vícekrát, každý s vlastní znakovou sadou.  
* **Vytvořit QR kód místo toho** – nahraďte `EncodeTypes.DATA_MATRIX` za `EncodeTypes.QR`.  

Všechny ostatní kroky zůstávají stejné, protože `ExtCodetextBuilder` abstrahuje nízkoúrovňové zpracování bajtů.

## Závěr

Nyní víte, jak **vygenerovat DataMatrix čárový kód** v Pythonu a **zakódovat ruský text** pomocí rozšířené funkce kódového textu v Aspose.BarCode. Kompletní skript řeší vyjednávání znakových sad, tvorbu čárového kódu a výstup obrázku během několika řádků kódu.

Dále můžete prozkoumat další symbologie čárových kódů (PDF417, Aztec) nebo integrovat generátor do webové služby, která na vyžádání vrací PNG obrázky. Stejné principy – tvorba rozšířeného kódového textu a výběr vhodného `EncodeTypes` – platí napříč celým portfoliem Aspose.BarCode.

Šťastné programování a užijte si sílu vícejazyčného generování čárových kódů!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční příklady kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [Generate a DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET (C#)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}