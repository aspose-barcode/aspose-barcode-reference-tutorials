---
category: general
date: 2026-10-24
description: Příklad generátoru čárových kódů, který ukazuje, jak vytvořit čárový
  kód Planet a jak nastavit výšku čárového kódu pomocí Pythonu. Postupujte podle průvodce
  krok za krokem.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to create planet barcode
- how to set barcode height
language: cs
lastmod: 2026-10-24
og_description: Příklad generátoru čárových kódů, který demonstruje, jak vytvořit
  čárový kód Planet a jak nastavit výšku čárového kódu v Pythonu. Získejte kompletní,
  spustitelné řešení.
og_image_alt: Barcode generator example showing Planet and RM4SCC barcodes with different
  heights
og_title: Příklad generátoru čárových kódů – vytvořte čárové kódy Planet a RM4SCC
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  headline: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  type: TechArticle
- description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  name: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  steps:
  - name: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
    text: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
  - name: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
    text: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
  - name: '**Save** the image to disk in PNG format.'
    text: '**Save** the image to disk in PNG format.'
  type: HowTo
tags:
- barcode
- Python
- image generation
title: Příklad generátoru čárových kódů – vytvořte čárové kódy Planet a RM4SCC s vlastní
  výškou
url: /cs/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Příklad generátoru čárových kódů – vytvořte čárové kódy Planet a RM4SCC s vlastní výškou

Pokud hledáte **příklad generátoru čárových kódů**, tento průvodce vám poskytne kompletní, připravené řešení. Uvidíte **jak vytvořit obrázky planet čárových kódů**, naučíte se **jak nastavit výšku čárového kódu** a pochopíte malé rozdíly mezi automatickým a ručním nastavením velikosti.

Tutoriál prochází dvě realistické situace: Planet čárový kód, který používá výchozí (automatickou) výšku, a RM4SCC čárový kód, kde je výška vynucena na 100 px. Na konci budete schopni generovat PNG soubory pro jakýkoli podporovaný typ čárového kódu pomocí jediné, konzistentní API.

## Požadavky

* Nainstalovaný Python 3.8 nebo novější.
* Balíček `aspose-barcode` (nebo jakákoli knihovna, která poskytuje `BarcodeGenerator`, `EncodeTypes` a `BarCodeImageFormat`). Nainstalujte jej pomocí  

  ```bash
  pip install aspose-barcode
  ```
* Oprávnění k zápisu do složky, kam budou PNG soubory ukládány.

Žádné další systémové závislosti nejsou vyžadovány.

## Přehled řešení

Jádro **příkladu generátoru čárových kódů** se skládá ze tří znovupoužitelných kroků:

1. **Instancujte** `BarcodeGenerator` s požadovanou hodnotou `EncodeTypes` a datovým řetězcem.
2. **Nakonfigurujte** X‑dimenzi (šířku modulu) a v případě potřeby výšku čárového kódu.
3. **Uložte** obrázek na disk ve formátu PNG.

Oba příklady sdílejí kroky 1 a 3; pouze krok 2 se liší, protože Planet čárový kód spoléhá na automatický výpočet výšky knihovny, zatímco RM4SCC čárový kód ukazuje **jak nastavit výšku čárového kódu** ručně.

Níže je diagram na vysoké úrovni, který ilustruje tok:

![Příklad generátoru čárových kódů zobrazující čárové kódy Planet a RM4SCC](barcode-example.png)

*Alt text: Příklad generátoru čárových kódů zobrazující čárové kódy Planet a RM4SCC s různými výškami.*

## Jak vytvořit planet čárový kód – automatická výška

Planet čárový kód je součástí poštovní rodiny používané mnoha národními poštovními službami. Ve většině případů necháte SDK rozhodnout o výšce, což zachovává správné vizuální proporce pro různé délky dat.

```python
# Step 1: Create a generator for the Planet barcode with the data "123456"
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

planet_gen = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Define the X‑dimension (module width) as 4 pixels
planet_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Save the barcode image as a PNG file
planet_gen.save("PostalPlanetBarHeightAuto.png", BarCodeImageFormat.Png)
```

**Proč to funguje**

* `EncodeTypes.Planet` říká knihovně, aby použila symbologii Planet.
* Nastavení `x_dimension.pixels` na 4 dává každému modulu šířku 4 px, což je běžná výchozí hodnota pro tištěné štítky.
* Výška není explicitně nastavena; SDK vypočítá optimální výšku na základě dat a X‑dimenze, což je důvod, proč je to nejjednodušší **příklad generátoru čárových kódů** pro poštovní kódy.

**Očekávaný výsledek**

2‑D PNG soubor pojmenovaný `PostalPlanetBarHeightAuto.png`, který obsahuje ostrý Planet čárový kód. Výška bude přibližně 30 px (v závislosti na verzi knihovny) a šířka bude 4 px × počet modulů.

## Jak nastavit výšku čárového kódu – vlastní příklad RM4SCC

RM4SCC je další poštovní čárový kód, který často vyžaduje pevnou výšku, aby odpovídal šablonám štítků. Tato část tutoriálu ukazuje **jak nastavit výšku čárového kódu** na přesný počet pixelů.

```python
# Step 1: Create a generator for the RM4SCC barcode with the data "123456"
rm4scc_gen = BarcodeGenerator(EncodeTypes.RM4SCC, "123456")

# Step 2: Set the X‑dimension to 4 pixels (same as the Planet example)
rm4scc_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Specify the barcode height as 100 pixels
rm4scc_gen.parameters.barcode.bar_height.pixels = 100

# Step 4: Save the barcode image as a PNG file
rm4scc_gen.save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png)
```

**Proč to funguje**

* `EncodeTypes.RM4SCC` vybírá symbologii RM4SCC.
* X‑dimenze zůstává na 4 px, aby velikost modulu byla konzistentní u obou čárových kódů.
* `bar_height.pixels = 100` vynutí, aby čárový kód byl přesně 100 px vysoký, čímž přepíše automatický výpočet. Toto je doporučený způsob **jak nastavit výšku čárového kódu**, když vaše rozvržení vyžaduje konkrétní velikost.

**Očekávaný výsledek**

PNG soubor pojmenovaný `PostalRM4SCCBarHeight100Pixels.png`, který zobrazuje vysoký RM4SCC čárový kód. Šířka je stále určena X‑dimenzí, zatímco výška je pevně nastavena na 100 px, což ho činí vhodným pro vysoce rozlišené tiskárny štítků.

## Kompletní skript – kombinace obou příkladů

Pokud dáváte přednost jedinému skriptu, který generuje oba obrázky, zkopírujte následující kód do `generate_barcodes.py` a spusťte jej.

```python
"""
Full barcode generator example that creates:
* a Planet barcode with automatic height
* an RM4SCC barcode with a custom 100 px height
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_planet_barcode(data: str, x_dim: int, out_path: str):
    """Generate a Planet barcode using the default height."""
    gen = BarcodeGenerator(EncodeTypes.Planet, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.save(out_path, BarCodeImageFormat.Png)

def create_rm4scc_barcode(data: str, x_dim: int, height_px: int, out_path: str):
    """Generate an RM4SCC barcode with a fixed height."""
    gen = BarcodeGenerator(EncodeTypes.RM4SCC, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.parameters.barcode.bar_height.pixels = height_px
    gen.save(out_path, BarCodeImageFormat.Png)

if __name__ == "__main__":
    # Planet barcode – auto height
    create_planet_barcode(
        data="123456",
        x_dim=4,
        out_path="PostalPlanetBarHeightAuto.png"
    )

    # RM4SCC barcode – custom 100 px height
    create_rm4scc_barcode(
        data="123456",
        x_dim=4,
        height_px=100,
        out_path="PostalRM4SCCBarHeight100Pixels.png"
    )
```

**Vysvětlení skriptu**

* Dvě pomocné funkce udržují kód DRY (Don’t Repeat Yourself) a usnadňují rozšíření skriptu pro další symbologie.
* Ochrana `if __name__ == "__main__":` umožňuje soubor importovat jako modul bez spuštění generovací logiky, což je užitečné pro jednotkové testování.
* Všechny parametry (datový řetězec, X‑dimenze, výška) jsou explicitní, takže skript slouží jako referenční **příklad generátoru čárových kódů** pro budoucí projekty.

## Časté otázky a okrajové případy

| Question | Answer |
|----------|--------|
| *Co když potřebuji jinou X‑dimenzi?* | Změňte `x_dimension.pixels` na požadovanou šířku modulu. Větší hodnoty proporčně zvětší celkovou velikost čárového kódu. |
| *Mohu generovat jiné formáty obrázků?* | Ano. Nahraďte `BarCodeImageFormat.Png` za `Jpg`, `Bmp` nebo `Gif` podle enumu knihovny. |
| *Co se stane, pokud datový řetězec obsahuje neplatné znaky?* | Generátor vyhodí `ArgumentException`. Ověřte data vůči znakové sadě symbologie před voláním konstruktoru. |
| *Je možné nastavit minimální výšku při zachování automatického škálování?* | Použijte `gen.parameters.barcode.bar_height.min_pixels = <value>` (pokud SDK poskytuje vlastnost `min_pixels`). Tím se zabrání zmenšení čárového kódu pod čitelnou velikost. |
| *Musím generátor uvolnit?* | `BarcodeGenerator` třída implementuje `IDisposable` v .NET; v Pythonu se o to postará garbage collector, ale můžete zavolat `gen.dispose()`, pokud vytváříte mnoho instancí v cyklu. |

## Tipy pro produkční použití

* **Pro tip:** Uložte hodnoty X‑dimenze a výšky do konfiguračního souboru, abyste je mohli upravovat bez překladu.
* **Pozor na:** Použití výšky, která je pro vybranou symbologii příliš malá; skenery mohou mít potíže číst čárový kód.
* **Poznámka k výkonu:** Generování velké dávky čárových kódů je rychlejší, když znovu použijete jedinou instanci `BarcodeGenerator` a mezi ukládáními měníte pouze její vlastnost `code_text`.

## Závěr

Tento **příklad generátoru čárových kódů** demonstruje jak **vytvořit obrázky planet čárových kódů** s automatickým nastavením velikosti, tak **jak nastavit výšku čárového kódu** ručně pro kódy RM4SCC. Dodržením krok‑za‑krokem průvodce můžete integrovat tvorbu čárových kódů do jakékoli Python aplikace, přizpůsobit rozměry a vytvořit PNG soubory připravené k tisku nebo digitálnímu zobrazení.

### Další kroky

* Prozkoumejte další symbologie jako `EncodeTypes.Postnet` nebo `EncodeTypes.Code128` – stejný vzor platí.
* Experimentujte s **jak nastavit výšku čárového kódu** pro QR kódy nebo symboly DataMatrix; většina knihoven poskytuje podobnou vlastnost `bar_height`.
* Kombinujte generátor s PDF knihovnou pro vložení čárových kódů přímo do faktur nebo přepravních štítků.

Neváhejte skript upravit, sdílet své výsledky a dejte nám vědět, které typy čárových kódů přidáte dál!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak uložit PNG z příkladu generátoru čárových kódů v Pythonu](/barcode/english/python-java/general/how-to-save-png-from-a-barcode-generator-example-in-python/)
- [Jak vytvořit PNG planet čárového kódu v Pythonu](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [Jak použít C# generátor čárových kódů k vytvoření Planet čárového kódu](/barcode/english/python-java/general/how-to-use-a-c-barcode-generator-to-create-a-planet-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}