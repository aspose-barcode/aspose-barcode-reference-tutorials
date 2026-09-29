---
category: general
date: 2026-09-29
description: Zobrazte název produktu v Pythonu při výpisu data vydání a získávání
  podrobností o verzi z knihovny barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- display product name
- print release date
- how to get version
- how to print product
- show minor version
language: cs
lastmod: 2026-09-29
og_description: Zobrazte název produktu v Pythonu a naučte se, jak vytisknout datum
  vydání, získat verzi a zobrazit podverzi pomocí několika řádků kódu.
og_image_alt: Screenshot of terminal output showing product name, version, and release
  date
og_title: Zobrazit název produktu a informace o verzi v Pythonu
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Display product name in Python while printing release date and retrieving
    version details from the barcode library.
  headline: Display product name and version info in Python
  type: TechArticle
tags:
- Python
- barcode library
- version information
title: Zobrazit název produktu a informace o verzi v Pythonu
url: /cs/python/general/display-product-name-and-version-info-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zobrazte název produktu a informace o verzi v Pythonu

Pokud potřebujete **zobrazit název produktu** z knihovny, tento průvodce vám ukáže přesně jak. Také se naučíte **vytisknout datum vydání**, **získat verzi** a **zobrazit minor verzi** pomocí stručného Python kódu.

Mnoho vývojářů integruje funkce skenování nebo generování čárových kódů a musí uživatelům nebo logům zpřístupnit metadata knihovny. Tento tutoriál pokrývá vše potřebné pro spolehlivé získání a prezentaci těchto informací.

## Co se naučíte

* Získat informace o verzi z knihovny `barcode`.  
* **Zobrazit název produktu** spolu s hlavní a minor verzí.  
* **Vytisknout datum vydání** v lidsky čitelném formátu.  
* Elegantně ošetřit chybějící atributy.  

**Předpoklady**  
* Python 3.8 nebo novější.  
* Přístup k balíčku `barcode` (nainstalujte pomocí `pip install python-barcode` nebo knihovny, která poskytuje `BuildVersionInfo`).  

---

## Jak zobrazit název produktu a informace o verzi v Pythonu

Prvním krokem je importovat knihovnu a zavolat metodu, která vrací objekt s informacemi o verzi. Objekt obsahuje atributy jako `PRODUCT`, `PRODUCT_MAJOR`, `PRODUCT_MINOR` a `RELEASE_DATE`.

```python
import barcode

def main():
    # Step 1: Retrieve version information from the barcode library
    info = barcode.BuildVersionInfo()

    # Step 2: Display product name
    print(f"Product: {info.PRODUCT}")

    # Step 3: Show major and minor version numbers
    print(f"Version: {info.PRODUCT_MAJOR}.{info.PRODUCT_MINOR}")

    # Step 4: Print release date
    print(f"Release date: {info.RELEASE_DATE}")

if __name__ == "__main__":
    main()
```

**Proč to funguje**  
`BuildVersionInfo()` vrací lehký objekt, jehož atributy jsou naplněny při importu. Přímý přístup k atributům eliminuje další I/O a zaručuje, že zobrazená data odpovídají verzi knihovny, kterou váš kód skutečně používá.

### Očekávaný výstup

```
Product: BarcodeLib
Version: 2.5
Release date: 2024-03-15
```

Přesné hodnoty závisí na nainstalované verzi knihovny barcode.

---

## Jak získat verzi z knihovny barcode

Pokud potřebujete jen čísla verze, můžete vynechat tisk názvu produktu a soustředit se na číselné pole.

```python
import barcode

info = barcode.BuildVersionInfo()
major = info.PRODUCT_MAJOR
minor = info.PRODUCT_MINOR

print(f"Current version: {major}.{minor}")
```

*Attribúty `PRODUCT_MAJOR` a `PRODUCT_MINOR` následují semantické verzování, což vám umožní programově porovnávat verze.*

---

## Jak vytisknout datum vydání

Datum vydání je uloženo jako řetězec ve formátu `YYYY‑MM‑DD`. Pro zobrazení v jiném locale jej nejprve převeďte na objekt `datetime`.

```python
import barcode
from datetime import datetime

info = barcode.BuildVersionInfo()
raw_date = info.RELEASE_DATE          # e.g., "2024-03-15"
date_obj = datetime.strptime(raw_date, "%Y-%m-%d")
formatted = date_obj.strftime("%B %d, %Y")  # "March 15, 2024"

print(f"Release date: {formatted}")
```

**Tip:** Vždy před parsováním ověřte řetězec data, abyste předešli `ValueError`, pokud knihovna změní svůj formát.

---

## Zobrazte minor verzi vedle hlavní verze

Někdy potřebujete minor verzi zobrazit samostatně, například při logování varování o kompatibilitě.

```python
import barcode

info = barcode.BuildVersionInfo()
print(f"Major version: {info.PRODUCT_MAJOR}")
print(f"Minor version: {info.PRODUCT_MINOR}")
```

**Pro tip:** Použijte minor verzi k aktivaci feature flagů:

```python
if info.PRODUCT_MINOR >= 5:
    enable_new_feature()
```

---

## Ošetření chybějících atributů (edge cases)

Starší verze knihovny barcode nemusí všechny atributy poskytovat. Zabalte přístup k atributům do `getattr` s rozumnými výchozími hodnotami.

```python
import barcode

info = barcode.BuildVersionInfo()

product = getattr(info, "PRODUCT", "Unknown Product")
major = getattr(info, "PRODUCT_MAJOR", 0)
minor = getattr(info, "PRODUCT_MINOR", 0)
release = getattr(info, "RELEASE_DATE", "N/A")

print(f"Product: {product}")
print(f"Version: {major}.{minor}")
print(f"Release date: {release}")
```

Tento vzor zajišťuje, že váš skript nikdy nezhavolí kvůli chybějícímu poli, což ho činí odolným pro CI pipeline, které mohou běžet proti různým verzím knihovny.

---

## Kompletní spustitelný příklad

Níže je kompletní skript, který kombinuje všechny osvědčené postupy: validaci atributů, formátování data a přehledný výstup.

```python
import barcode
from datetime import datetime

def fetch_info():
    """Retrieve version info safely, providing defaults for missing attributes."""
    raw = barcode.BuildVersionInfo()
    return {
        "product": getattr(raw, "PRODUCT", "Unknown Product"),
        "major": getattr(raw, "PRODUCT_MAJOR", 0),
        "minor": getattr(raw, "PRODUCT_MINOR", 0),
        "release_raw": getattr(raw, "RELEASE_DATE", "N/A")
    }

def format_release(date_str):
    """Convert YYYY‑MM‑DD to a friendly format; fall back to the original string."""
    try:
        dt = datetime.strptime(date_str, "%Y-%m-%d")
        return dt.strftime("%B %d, %Y")
    except (ValueError, TypeError):
        return date_str

def main():
    info = fetch_info()

    # Display product name
    print(f"Product: {info['product']}")

    # Show major and minor version numbers
    print(f"Version: {info['major']}.{info['minor']}")

    # Print release date in a readable form
    print(f"Release date: {format_release(info['release_raw'])}")

if __name__ == "__main__":
    main()
```

Spuštěním tohoto skriptu na systému s nainstalovanou knihovnou barcode získáte výstup podobný předchozímu příkladu, ale nyní je chráněn proti chybějícím polím a datum je hezky naformátováno.

---

## Závěr

Nyní víte, jak **zobrazit název produktu**, **vytisknout datum vydání**, **získat verzi**, **vytisknout produkt** a **zobrazit minor verzi** pomocí jednoduchého Python workflow. Kompletní příklad demonstruje spolehlivý přístup k atributům, práci s daty a porovnávání verzí – dovednosti, které můžete znovu použít pro jakoukoli třetí knihovnu, která poskytuje metadata objekty.

**Další kroky**

* Prozkoumejte další metody metadat knihovny barcode, jako je `BuildCommitInfo()`.  
* Integrovat výstup do logovacího frameworku (např. `logging.info`).  
* Programově porovnávat verze, abyste v aplikaci vynutili minimální požadovanou verzi.

Neváhejte experimentovat s různými formáty výstupu nebo rozšířit skript o zápis informací do souboru pro auditní účely. Šťastné programování!  

![Terminal output showing product name and version details](image.png "Terminal output")


## Co byste se měli naučit dál?


Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobným krok‑za‑krokem vysvětlením, které vám pomohou zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [display product name using Python barcode library – step‑by‑step guide](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)
- [How to Print Version of Aspose.Barcode (Python)](/barcode/english/python/general/how-to-print-version-of-aspose-barcode-python/)
- [How to generate barcode with Aspose.BarCode in Python](/barcode/english/python-java/general/how-to-generate-barcode-with-aspose-barcode-in-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}