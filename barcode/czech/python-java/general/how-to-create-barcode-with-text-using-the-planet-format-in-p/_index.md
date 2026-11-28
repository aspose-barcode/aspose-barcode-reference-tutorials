---
category: general
date: 2026-11-27
description: Naučte se, jak vytvořit čárový kód s textem a generovat planetový čárový
  kód v Pythonu – krok za krokem průvodce pro výstup ve vysokém rozlišení PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode with text
- how to generate barcode
- generate planet barcode
- Python barcode generation
- high‑resolution barcode PNG
language: cs
lastmod: 2026-11-27
og_description: Vytvořte čárový kód s textem a vygenerujte planetový čárový kód v
  Pythonu. Postupujte podle tohoto kompletního návodu pro výstup ve vysokém rozlišení
  PNG.
og_image_alt: Screenshot showing how to create barcode with text using the Planet
  barcode generator
og_title: Vytvořte čárový kód s textem v Pythonu – snadno generujte Planet čárový
  kód
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to create barcode with text and generate planet barcode in
    Python—step‑by‑step guide for high‑resolution PNG output.
  headline: How to create barcode with text using the Planet format in Python
  type: TechArticle
tags:
- barcode
- Python
- Planet format
- image generation
title: Jak vytvořit čárový kód s textem pomocí formátu Planet v Pythonu
url: /cs/python-java/general/how-to-create-barcode-with-text-using-the-planet-format-in-p/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit čárový kód s textem pomocí formátu Planet v Pythonu

Pokud potřebujete **vytvořit čárový kód s textem** pro poštovní systém, tento tutoriál vám přesně ukáže, jak na to. Uvidíte stručný, kompletní příklad, který generuje Planet čárový kód, upravuje rozlišení a uloží výsledek jako PNG obrázek.

Generování čárových kódů je běžnou potřebou pro logistiku, inventarizaci a aplikace pro vstupenky. V tomto průvodci se naučíte nejen **jak generovat soubory s čárovým kódem**, ale také proč je každý konfigurační krok důležitý a jak se vyhnout typickým úskalím.

## Co se naučíte

* Nastavit generátor Planet čárového kódu s vlastním textem.
* Upravit X‑dimenzi pro zvýšení ostrosti obrázku.
* Uložit čárový kód jako PNG soubor, který lze vytisknout nebo zobrazit na webu.
* Rozšířit příklad na jiné typy čárových kódů nebo výstupní formáty.

**Požadavky**

* Python 3.8 nebo novější.
* Balíček `aspose-barcode` (nebo jakákoli kompatibilní knihovna, která poskytuje `BarcodeGenerator`, `EncodeTypes` a `BarCodeImageFormat`).
* Základní znalost skriptování v Pythonu.

You can install the required package with:

```bash
pip install aspose-barcode
```

---

## Krok 1: Vytvořit čárový kód s textem – inicializace generátoru

Prvním krokem je vytvořit instanci `BarcodeGenerator`, která ví, jakou symbologii použít a jaký text kódovat. Pro Planet čárový kód hodnota výčtu `EncodeTypes.Planet` říká knihovně, aby se řídila specifikací USPS Planet.

```python
# Import the necessary classes from the Aspose.BarCode library
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1: Initialize the generator with the desired text
# The text "123456" will appear beneath the Planet barcode pattern.
gen = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**Proč je to důležité:**  
Objekt `BarcodeGenerator` zapouzdřuje všechna nastavení čárového kódu. Poskytnutí textu při konstrukci zaručuje, že kódovaná hodnota zůstane během celého procesu neměnná, což eliminuje náhodné nesoulady později.

---

## Krok 2: Úprava nastavení – jak generovat čárový kód s vyšším rozlišením

Čárový kód s nízkým rozlišením může vypadat rozmazaně při tisku na štítkový tiskárně. X‑dimenze (šířka modulu) řídí velikost každého jednotlivého pruhu. Nastavením na 4 pixely získáte ostrý, vysoké rozlišení obrázek vhodný pro většinu moderních tiskáren.

```python
# Step 2: Increase the X‑dimension to 4 pixels for better clarity
gen.parameters.barcode.x_dimension.pixels = 4
```

**Vysvětlení:**  
* `gen.parameters.barcode.x_dimension.pixels` přímo odpovídá fyzické šířce jednoho modulu.  
* Hodnota **4** znamená, že každý pruh je široký čtyři pixely, což zhruba odpovídá 0,127 mm při 300 dpi — v rámci doporučeného rozsahu pro USPS Planet čárové kódy.  

**Tip:** Pokud potřebujete jiné DPI, vypočítejte šířku v pixelech odpovídajícím způsobem (např. 2 pixely pro 150 dpi, 8 pixely pro 600 dpi).

---

## Krok 3: Uložení obrázku – generovat Planet čárový kód jako PNG

Nyní, když je generátor nastaven, můžete vykreslit čárový kód do souboru s obrázkem. PNG je bezztrátový formát, který zajišťuje zachování přesného vzoru modulů.

```python
# Step 3: Save the generated barcode as a PNG image
output_path = "output/PostalPlanetBarHeightNone.png"
gen.save(output_path, BarCodeImageFormat.Png)
print(f"Barcode saved to {output_path}")
```

**Výsledek:**  
Spuštěním skriptu se vytvoří soubor pojmenovaný `PostalPlanetBarHeightNone.png`, který obsahuje Planet čárový kód kódující řetězec “123456”. Rozměry obrázku budou přibližně 200 × 100 pixelů, v závislosti na zvolené X‑dimenzi.

---

## Volitelné: Ověření čárového kódu vizuálně

Můžete rychle otevřít vygenerovaný PNG v libovolném prohlížeči obrázků a potvrdit, že čárový kód vypadá ostře a lidsky čitelný text je přítomen pod vzorem.

```python
from PIL import Image

img = Image.open(output_path)
img.show()
```

Pokud se obrázek jeví jako rozmazaný, vraťte se k **kroku 2** a zvyšte X‑dimenzi, dokud nebudou pruhy jasně definované.

---

## Běžné varianty a okrajové případy

| Situace | Úprava |
|-----------|------------|
| **Různá délka textu** | Planet čárové kódy podporují až 12 číselných znaků. Pokud tuto limit překročíte, knihovna vyvolá výjimku. |
| **Alternativní výstupní formát** | Nahraďte `BarCodeImageFormat.Png` za `BarCodeImageFormat.Jpeg` nebo `BarCodeImageFormat.Bmp` pro jiné případy použití. |
| **Vlastní barvy popředí/pozadí** | Použijte `gen.parameters.barcode.barcode_color = Color.Blue` a `gen.parameters.barcode.back_color = Color.White`. |
| **Bez lidsky čitelného textu** | Nastavte `gen.parameters.barcode.hide_code_text = True` pro generování čárového kódu bez dolního popisku. |
| **Dávkové generování** | Projděte seznam řetězců, vytvořte pro každý nový `BarcodeGenerator` a uložte je do jedinečně pojmenovaných souborů. |

Tyto varianty vám umožní **generovat planet čárové kódy** soubory, které vyhovují širokému spektru obchodních požadavků.

---

## Kompletní skript – připravený ke spuštění

Níže je kompletní, samostatný skript, který můžete zkopírovat, vložit a spustit. Obsahuje všechny importy, ošetření chyb a komentáře.

```python
"""
Complete example: create barcode with text and generate a Planet barcode PNG.
Author: Your Name
Date: 2026-11-27
"""

import os
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from aspose.barcode import Color  # optional, for color customization
from PIL import Image

def create_planet_barcode(text: str, output_dir: str, x_dim_pixels: int = 4) -> str:
    """
    Generates a Planet barcode with the given text and saves it as a PNG.
    
    Args:
        text: Numeric string to encode (max 12 characters for Planet).
        output_dir: Directory where the PNG will be stored.
        x_dim_pixels: Width of a single module in pixels (default 4 for high resolution).
    
    Returns:
        Full path to the saved PNG file.
    """
    if not text.isdigit():
        raise ValueError("Planet barcode requires numeric text only.")
    if len(text) > 12:
        raise ValueError("Planet barcode supports up to 12 digits.")
    
    # Ensure the output directory exists
    os.makedirs(output_dir, exist_ok=True)
    
    # Initialize the generator with the desired text
    gen = BarcodeGenerator(EncodeTypes.Planet, text)
    
    # Adjust resolution via X‑dimension
    gen.parameters.barcode.x_dimension.pixels = x_dim_pixels
    
    # Build the output file path
    file_name = f"Planet_{text}.png"
    full_path = os.path.join(output_dir, file_name)
    
    # Save as PNG
    gen.save(full_path, BarCodeImageFormat.Png)
    
    return full_path

if __name__ == "__main__":
    try:
        result_path = create_planet_barcode("123456", "output")
        print(f"Barcode successfully generated: {result_path}")
        
        # Open the image for a quick visual check
        Image.open(result_path).show()
    except Exception as e:
        print(f"Error: {e}")
```

**Vysvětlení skriptu**

* Funkce `create_planet_barcode` zapouzdřuje tři hlavní kroky, což činí kód znovupoužitelným.
* Ověření vstupu zajišťuje, že dodržujete specifikaci Planet (pouze číselné, max 12 číslic).
* Funkce automaticky vytvoří výstupní složku, takže nemusíte ručně spravovat adresáře.
* Po generování skript otevře obrázek pomocí Pillow (`PIL`) pro okamžité ověření.

---

## Závěr

Nyní víte, jak **vytvořit čárový kód s textem** a **generovat planet čárové kódy** soubory v Pythonu. Průvodce pokryl inicializaci, ladění rozlišení a výstup souboru, spolu s volitelnými úpravami a běžnými okrajovými případy.  

Odtud můžete:

* Nahradit `EncodeTypes.Planet` jinými symbologiemi (např. `EncodeTypes.Code128`) a znovu použít stejný vzor.
* Integrovat funkci do webové služby, která na požádání vrací obrázky čárových kódů.
* Experimentovat s dávkovým zpracováním pro vytvoření tisíců čárových kódů pro hromadnou poštu.

Neváhejte přizpůsobit skript potřebám vašeho projektu a sdílet své výsledky v komentářích. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak generovat čárový kód v Pythonu – kompletní krok‑za‑krokem průvodce](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Vytvořit čárový kód PNG v Pythonu – krok‑za‑krokem průvodce](/barcode/english/python-java/general/create-barcode-png-in-python-step-by-step-guide/)
- [Jak vytvořit Planet čárový kód PNG pomocí Pythonu](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}