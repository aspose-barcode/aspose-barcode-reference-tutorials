---
category: general
date: 2026-07-30
description: Vytvořte Databar Stacked Omnidirectional čárový kód v Pythonu. Postupujte
  podle tohoto krok‑za‑krokem průvodce a nastavte poměr stran, XDimension a exportujte
  PNG pomocí generátoru čárových kódů v Pythonu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked omnidirectional
- python barcode generator
- databar aspect ratio
- xdimension pixel size
- barcodeimageformat png
language: cs
lastmod: 2026-07-30
og_description: Vytvořte Databar Stacked Omnidirectional čárový kód v Pythonu. Tento
  tutoriál ukazuje, jak nastavit XDimension, upravit poměr stran DataBar a uložit
  jako PNG pomocí BarCodeImageFormat.
og_image_alt: Screenshot of a Databar Stacked Omnidirectional barcode saved as a PNG
  file
og_title: Vytvořte vrstvený omnidirekční čárový kód Databar – Python tutoriál
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Create Databar Stacked Omnidirectional barcode in Python. Follow this
    step‑by‑step guide to configure aspect ratio, XDimension, and export PNG using
    a python barcode generator.
  headline: Create Databar Stacked Omnidirectional Barcode in Python
  type: TechArticle
tags:
- barcode
- python
- databar
title: Vytvořte Databar Stacked Omnidirectional čárový kód v Pythonu
url: /cs/python-java/general/create-databar-stacked-omnidirectional-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořte Databar Stacked Omnidirectional Barcode v Pythonu

Už jste někdy potřebovali **create databar stacked omnidirectional** čárový kód v Pythonu, ale nebyli jste si jisti, kde začít? Nejste sami – mnoho vývojářů narazí na tuto překážku, když poprvé pracují s třídou `BarcodeGenerator`. Dobrou zprávou je, že celý proces je poměrně jednoduchý, jakmile pochopíte klíčové vlastnosti.

V tomto průvodci projdeme kompletním, spustitelným příkladem, který používá **python barcode generator** k nastavení XDimension, úpravě poměru stran DataBar a nakonec exportuje dva PNG soubory. Na konci budete mít pevné pochopení, jak generovat vysoce kvalitní stacked omnidirectional symboly pro jakýkoli inventární nebo logistický projekt.

## Co se naučíte

- Jak vytvořit instanci **databar stacked omnidirectional** generátoru s GTIN‑14 payload.  
- Proč **XDimension pixel size** má význam pro spolehlivost skenování.  
- Jaký dopad má **DataBar aspect ratio** na šířku řádku oproti výšce.  
- Jak uložit výsledek jako soubor **BarCodeImageFormat PNG**.  
- Tipy pro opětovné použití stejného objektu generátoru k vytvoření více variant bez extra paměťové zátěže.

### Požadavky

- Python 3.8+ (knihovna, kterou používáme, je čistě Python, není potřeba kompilované wheel).  
- `barcode-generator` balíček (nainstalujte pomocí `pip install barcode-generator`).  
- Složka, do které můžete zapisovat – skript tam uloží dva PNG obrázky.

Pokud jste pohodlní se základními importy v Pythonu a objektově orientovaným kódem, jste připraveni začít.

## Vytvoření Databar Stacked Omnidirectional Barcode – Přehled kroků

Níže rozdělíme pracovní postup do šesti malých kroků. Každý krok je samostatný úsek kódu, který můžete zkopírovat a vložit do REPL nebo skriptového souboru. Klidně experimentujte – změna poměru stran nebo XDimension okamžitě poskytne jiný vizuální styl.

---

## Krok 1: Vytvořte Databar Stacked Omnidirectional Generátor

Prvním krokem je **create databar stacked omnidirectional** vytvořit instanci generátoru, předáním odpovídajícího enumu `EncodeTypes` a datového řetězce.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1 – initialize the generator with a GTIN‑14 payload
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)
```

> **Proč je to důležité:** Příznak `EncodeTypes.DatabarStackedOmniDirectional` říká knihovně, aby vytvořila stacked omnidirectional symbol, což je jediná varianta DataBar, která může kódovat až 14 číslic a přitom je čitelná z jakéhokoli úhlu.

---

## Nastavte XDimension Pixel Size

Velikost **XDimension pixel size** řídí nejmenší modul (nejtenčí černý pruh). Hodnota `2` pixely funguje dobře pro většinu scénářů zobrazení na obrazovce.

```python
# Step 2 – set the smallest module to 2 pixels
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2
```

> **Tip:** Pokud plánujete tisknout čárový kód při vysokém DPI, zvyšte tuto hodnotu na 3 nebo 4, aby nedošlo k rozmazaným hranám.

---

## Upravit DataBar Aspect Ratio (15)

**DataBar aspect ratio** určuje, jak široký je každý řádek ve srovnání s jeho výškou. Poměr stran `15` dává širší řádky, které mnoho skenerů preferuje pro rychlé zachycení pohybu.

```python
# Step 3 – make rows wider (aspect ratio = 15)
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
```

> **Proč 15?** Oficiální specifikace GS1 doporučuje poměr mezi 10 a 20 pro stacked omnidirectional symboly. Zvolili jsme `15` jako vyvážený výchozí.

---

## Exportujte čárový kód jako PNG pomocí BarCodeImageFormat

Nyní, když je generátor nastaven, uložíme obrázek. Enum `BarCodeImageFormat.Png` zajišťuje bezztrátový výstup, ideální pro následné zpracování.

```python
# Step 4 – save the first PNG with the 15 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR15.png",
    BarCodeImageFormat.Png
)
```

> **Co uvidíte:** Otevřete výsledný PNG; měli byste zaznamenat čistý, vysoce kontrastní čárový kód s relativně širokými řádky.

---

## Změňte DataBar Aspect Ratio na 30

Někdy potřebujete vyšší řádky místo širších – třeba pro úzký štítek. Přepnutím **DataBar aspect ratio** na `30` se každý řádek prodlouží.

```python
# Step 5 – increase the aspect ratio to make rows taller
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
```

> **Hraniční případ:** Velmi vysoké poměry (např. >40) mohou způsobit, že čárový kód přesáhne typické výšky štítků, proto to otestujte na skutečném tiskárně před nasazením.

---

## Exportujte čárový kód znovu s novým poměrem stran

Nakonec znovu použijeme stejný objekt `barcode_generator` k zápisu druhého PNG. Není potřeba generátor znovu vytvářet – stačí změnit vlastnost a znovu zavolat `Save`.

```python
# Step 6 – save the second PNG with the 30 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR30.png",
    BarCodeImageFormat.Png
)
```

> **Výsledek:** Nyní máte dva PNG soubory – jeden se širokými řádky (`AR15`) a druhý s vysokými řádky (`AR30`). Porovnejte je vedle sebe, abyste rozhodli, který nejlépe funguje s vaším nastavením skeneru.

---

## Kompletní funkční příklad

Spojením všech částí zde máte kompletní skript, který můžete spustit okamžitě. Nahraďte `YOUR_DIRECTORY` absolutní cestou na vašem počítači.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1️⃣ Initialize generator
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)

# 2️⃣ Set smallest module (XDimension)
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2

# 3️⃣ First aspect ratio – wider rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR15.png", BarCodeImageFormat.Png)

# 4️⃣ Second aspect ratio – taller rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR30.png", BarCodeImageFormat.Png)

print("✅ Two PNG files created – AR15 and AR30")
```

**Očekávaný výstup** (ve vaší konzoli):

```
✅ Two PNG files created – AR15 and AR30
```

A dva soubory obrázků se objeví v cílové složce, připravené pro testování skenování.

---

## Závěr

Právě jsme **created databar stacked omnidirectional** čárové kódy v Pythonu, upravili **XDimension pixel size**, experimentovali se dvěma různými nastaveními **DataBar aspect ratio** a exportovali výsledky jako soubory **BarCodeImageFormat PNG**. Celý pracovní postup se vejde do několika řádků, přičemž vám poskytuje plnou kontrolu nad vizuálními charakteristikami, které jsou pro skenery nejdůležitější.

Co dál? Zkuste vyměnit payload za jiný GTIN, pohrát si s barvami převodem PNG na obrázek s paletou, nebo vygenerovat PDF zprávu, která vloží oba PNG vedle sebe. Třída `BarcodeGenerator` je dostatečně flexibilní, aby zvládla všechny tyto scénáře, takže klidně experimentujte.

Máte otázky ohledně konkrétního použití nebo narazili na chybu? Zanechte komentář níže a rád pomohu. Šťastné kódování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Generovat obrázek čárového kódu – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}