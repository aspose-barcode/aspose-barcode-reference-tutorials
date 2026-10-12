---
category: general
date: 2026-09-23
description: Naučte se, jak generovat čárový kód Code 128 a uložit jeho obrázek pomocí
  Aspose.BarCode v Pythonu – krok za krokem průvodce.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate code 128 barcode
- save barcode image
- Aspose.BarCode Python
- extended codetext builder
- barcode PNG export
language: cs
lastmod: 2026-09-23
og_description: Vygenerujte čárový kód Code 128 a uložte jeho obrázek pomocí Aspose.BarCode
  v Pythonu. Postupujte podle tohoto kompletního příkladu, abyste vytvořili, přizpůsobili
  a exportovali čárový kód jako soubor PNG.
og_image_alt: Python-generated Code 128 barcode saved as PNG image
og_title: Vytvořte čárový kód Code 128 a uložte obrázek čárového kódu – průvodce Pythonem
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to generate Code 128 barcode and save barcode image using
    Aspose.BarCode in Python – step‑by‑step guide.
  headline: How to generate Code 128 barcode and save barcode image with Aspose.BarCode
  type: TechArticle
tags:
- barcode
- Code 128
- Python
- Aspose
title: Jak vygenerovat čárový kód Code 128 a uložit obrázek čárového kódu pomocí Aspose.BarCode
url: /cs/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vygenerovat čárový kód Code 128 a uložit obrázek čárového kódu pomocí Aspose.BarCode

Pokud potřebujete **vygenerovat čárový kód Code 128** a **uložit obrázek čárového kódu** v projektu Python, tento tutoriál ukazuje přesné kroky. Pomocí `ExtCodetextBuilder` z Aspose.BarCode můžete vložit obyčejný text a segmenty Unicode do jednoho payloadu a poté výsledek vykreslit jako soubor PNG.

Uvidíte kompletní, spustitelný skript, vysvětlení každého řádku a tipy pro běžné úskalí, jako je práce s ECI kódováním nebo výběr správné výstupní složky. Žádná externí dokumentace není potřeba – stačí zkopírovat, vložit a spustit.

## Požadavky

Než začnete, ujistěte se, že máte:

* Python 3.8+ nainstalovaný.
* Balíček `aspose.barcode` (nainstalujte pomocí `pip install aspose-barcode`).
* Oprávnění k zápisu do adresáře, kam bude PNG uloženo.

Kód funguje s libovolnou symbologií podporovanou Aspose.BarCode, ale příklad se zaměřuje na **Code 128**, protože efektivně kóduje alfanumerická data a podporuje rozšířené znakové sady.

## Krok 1: Naimportujte požadované třídy

```python
import barcode                     # Core Aspose.BarCode namespace
from barcode import BarCodeWriter, BarCodeEncodeMode, BarCodeImageFormat
from barcode import ExtCodetextBuilder, BuildVersionInfo
```

*Proč tento krok?* Naimportování tříd vám poskytne přístup k builderu pro rozšířený text kódu, zapisovači, který vytváří obrázek, a pomocníkovi pro verzi, který může být užitečný při ladění aktualizací knihovny.

## Krok 2: Vytvořte rozšířený text kódu

```python
# Create a builder for extended codetext
builder = ExtCodetextBuilder()

# Add plain text (no ECI) – this part is simple ASCII
builder.add_plain_codetext("ABC123")

# Add a Unicode segment with ECI 0x03 (UTF‑8). The word “Пример” means “Example” in Russian.
builder.add_eci_codetext(0x03, "Пример")

# Retrieve the full extended codetext string
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

`ExtCodetextBuilder` vám umožní smíchat obyčejný ASCII a Unicode data v jednom payloadu čárového kódu. ECI (Extended Channel Interpretation) bajt `0x03` říká skeneru, že následující bajty jsou kódovány v UTF‑8, což je nezbytné pro jazyky jako ruština, čínština nebo arabština.

## Krok 3: Nakonfigurujte zapisovač čárových kódů pro Code 128

```python
writer = BarCodeWriter()
writer.encode_type = BarCodeEncodeMode.CODE_128   # Choose Code 128 symbology
writer.code_text = extended_codetext
```

Nastavení `encode_type` na `CODE_128` instruuje zapisovač, aby vykreslil **čárový kód Code 128**. Vlastnost `code_text` přijímá rozšířený řetězec vytvořený v předchozím kroku.

## Krok 4: Uložte obrázek čárového kódu jako PNG

```python
output_path = "YOUR_DIRECTORY/extended_codetext.png"
writer.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode image saved to {output_path}")
```

Metoda `save` zapíše čárový kód do souboru. Použití `BarCodeImageFormat.PNG` zajišťuje bezztrátovou kompresi a širokou kompatibilitu s webovými i mobilními aplikacemi.

## Krok 5 (volitelně): Ověřte verzi knihovny Aspose.BarCode

```python
version_info = BuildVersionInfo()
print("Assembly version :", version_info.ASSEMBLY_VERSION)
print("Product version   :", f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR}")
print("Release date      :", version_info.RELEASE_DATE)
```

Znalost přesné verze knihovny pomáhá, když potřebujete hlásit chyby nebo porovnávat chování mezi vydáními.

## Očekávaný výstup

Spuštění skriptu vytvoří výstup v konzoli podobný:

```
Extended codetext: ABC123[ECI=03]Пример
Assembly version : 23.12.0.0
Product version   : 23.12
Release date      : 2023-12-01
Barcode image saved to YOUR_DIRECTORY/extended_codetext.png
```

Vygenerovaný PNG (`extended_codetext.png`) vypadá takto:

![Python-generated Code 128 barcode saved as PNG image](images/code128_extended.png)

*Obrázek zobrazuje čárový kód Code 128, který kóduje jak ASCII řetězec `ABC123`, tak ruské slovo „Пример“. *

## Časté otázky a řešení okrajových případů

| Otázka | Odpověď |
|----------|--------|
| **Mohu použít jinou symbologii?** | Ano. Nahraďte `BarCodeEncodeMode.CODE_128` libovolným jiným podporovaným režimem, například `QR`, `EAN_13` nebo `PDF_417`. |
| **Co když můj Unicode text obsahuje emoji?** | Emoji jsou také znaky UTF‑8, takže stejný volání `add_eci_codetext` funguje. Ujistěte se, že cílový skener podporuje použité ECI. |
| **Jak změním velikost obrázku?** | Nastavte `writer.x_dimension` a `writer.bar_height` před voláním `save`. |
| **Jaký adresář mám použít pro `output_path`?** | Jakýkoli adresář, do kterého může proces Pythonu zapisovat. Použijte `os.makedirs` s `exist_ok=True` pro automatické vytvoření. |

## Profesionální tipy

* **Vyhněte se pevně zakódovaným cestám.** Používejte `os.path.join` a `Path` z modulu `pathlib` pro multiplatformní kompatibilitu.
* **Validujte čárový kód.** Po uložení můžete obrázek načíst zpět pomocí `barcode.BarCodeReader` a potvrdit, že kódovaný text odpovídá `extended_codetext`.
* **Tip pro výkon.** Pokud generujete mnoho čárových kódů ve smyčce, znovu použijte jedinou instanci `BarCodeWriter` a pouze aktualizujte `code_text` v každé iteraci.

## Závěr

Nyní víte, jak **vygenerovat čárový kód Code 128** s kombinací ASCII a Unicode dat a **uložit obrázek čárového kódu** jako PNG pomocí Aspose.BarCode v Pythonu. Kompletní skript zahrnuje vytváření rozšířeného textu kódu, konfiguraci zapisovače, export obrázku a kontrolu verzí knihovny.

Odtud můžete zkoumat:

* Přidání barev popředí/pozadí (`writer.back_color`, `writer.fore_color`).
* Vložení čárového kódu do PDF pomocí `Aspose.PDF`.
* Použití třídy `BarCodeReader` k dekódování uloženého obrázku a automatickému ověření obsahu.

Šťastné programování a nebojte se experimentovat s dalšími symbologiemi a formáty obrázků!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vlastních projektech.

- [Generování čárového kódu Code128 s Aspose.Barcode v Pythonu – Kompletní průvodce](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [Jak generovat čárový kód v Pythonu – kompletní průvodce krok za krokem](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Jak vygenerovat QR kód v Pythonu s Aspose.Barcode – Kompletní průvodce](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}