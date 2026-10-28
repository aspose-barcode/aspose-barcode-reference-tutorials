---
category: general
date: 2026-10-28
description: Naučte se, jak vytvořit rozšířený kódový text v Pythonu pomocí ExtCodetextBuilder.
  Obsahuje prostá i ECI‑kódovaná data, krok‑za‑krokem kód a tipy na nejlepší postupy.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create extended codetext
- ExtCodetextBuilder Python
- add plain codetext
- add eci codetext
- extended‑codetext example
language: cs
lastmod: 2026-10-28
og_description: Vytvořte rozšířený kódový text v Pythonu pomocí ExtCodetextBuilder.
  Tento tutoriál ukazuje zpracování prostých i ECI‑kódovaných dat, kompletní spustitelný
  kód a běžné úskalí.
og_image_alt: Diagram showing how to create extended codetext using ExtCodetextBuilder
  in Python
og_title: Vytvořte rozšířený kódový text v Pythonu – kompletní průvodce
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  headline: How to create extended codetext in Python with ExtCodetextBuilder
  type: TechArticle
- description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  name: How to create extended codetext in Python with ExtCodetextBuilder
  steps:
  - name: Prerequisites
    text: '* Python 3.8 or newer. * The `extcodetext` package (or a similar library
      that provides `ExtCodetextBuilder`). Install it with:'
  - name: Handling other encodings
    text: 'If you need ISO‑8859‑1 (Western European) you would use `add_eci_codetext(4,
      "¡Hola!")`. For Shift‑JIS (Japanese) the ECI value is 20:'
  - name: 'Edge case: Empty strings'
    text: Calling `add_plain_codetext("")` or `add_eci_codetext(3, "")` is harmless;
      the builder simply ignores the empty fragment. However, repeated empty calls
      can lead to unnecessary ECI markers. Guard against this by checking string length
      before adding.
  type: HowTo
tags:
- Python
- encoding
- data‑serialization
title: Jak vytvořit rozšířený kódový text v Pythonu pomocí ExtCodetextBuilder
url: /cs/python/general/how-to-create-extended-codetext-in-python-with-extcodetextbu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit rozšířený kódový text v Pythonu pomocí ExtCodetextBuilder

Pokud potřebujete **vytvořit rozšířený kódový text** pro aplikace čárových kódů nebo datových matic, tento návod vám přesně ukáže, jak to provést v Pythonu. Uvidíte, jak kombinovat prostý text, přidávat sekce ECI (Extended Channel Interpretation) pro Unicode znaky a získat jediný, správně formátovaný řetězec připravený k zakódování.

Návod pokrývá vše od instalace požadované knihovny až po zpracování okrajových případů, jako jsou nepodporované hodnoty ECI. Na konci budete mít znovupoužitelný vzor, který můžete vložit do libovolného projektu, který potřebuje **vytvořit rozšířený kódový text**.

## Co se naučíte

* Úloha `ExtCodetextBuilder` při vytváření řetězců s kombinovaným kódováním.  
* Jak **přidat prostý kódový text** a **přidat ECI kódový text** v jedné instanci builderu.  
* Jak ověřit finální výstup a řešit běžné problémy.  
* Variace pro jiné znakové sady (např. ISO‑8859‑1, Shift‑JIS).  

### Předpoklady

* Python 3.8 nebo novější.  
* Balíček `extcodetext` (nebo podobná knihovna, která poskytuje `ExtCodetextBuilder`). Nainstalujte jej pomocí:

```bash
pip install extcodetext
```

* Základní znalost Unicode a hodnot ECI – ECI 3 odpovídá UTF‑8, ECI 4 ISO‑8859‑1 atd.

> **Tip:** Mějte po ruce referenční tabulku čísel ECI. Zabraňuje to neúmyslným nesouladům mezi deklarovaným kódováním a skutečnou bajtovou sekvencí.

## Porozumění ExtCodetextBuilder

`ExtCodetextBuilder` je malý nástroj, který spojuje více textových fragmentů a automaticky vkládá požadované ECI značky. Značka ECI říká následnému enkodéru čárových kódů, jakou znakovou sadu použít pro následující bajty. Bez značky by ne‑ASCII znaky byly špatně interpretovány.

Builder funguje ve třech jednoduchých fázích:

1. **Vytvořit** instanci builderu.  
2. **Připojit** prosté nebo ECI‑kódované fragmenty.  
3. **Získat** kombinovaný rozšířený‑kódový‑text řetězec.

Níže projdeme každou fázi s konkrétním kódem.

## Krok 1: Vytvořit instanci ExtCodetextBuilder

První řádek vytvoří objekt, který bude držet všechny fragmenty. V tuto chvíli není potřeba žádná konfigurace.

```python
from extcodetext import ExtCodetextBuilder

# Step 1: Create an ExtCodetextBuilder instance
codetext_builder = ExtCodetextBuilder()
```

*Proč je to důležité*: Instanciace builderu alokuje interní buffer. Všechny následné volání `add_*` operují na tomto bufferu, což zaručuje pořadí, které určíte.

## Krok 2: Připojit prostá (nekódovaná) data

Prostá data se skládají ze znaků, které patří do výchozí znakové sady (obvykle ASCII). Pro takové fragmenty použijte `add_plain_codetext`.

```python
# Step 2: Append plain (un‑encoded) data to the builder
codetext_builder.add_plain_codetext("ABC123")
```

*Vysvětlení*: Řetězec `"ABC123"` obsahuje pouze ASCII znaky, takže není potřeba žádná značka ECI. Metoda jednoduše připojí surové bajty do interního bufferu.

## Krok 3: Připojit data, která musí být předcházená ECI

Když potřebujete vložit Unicode znaky – například cyriliku, japonštinu nebo emoji – musíte enkodéru říct, kterou znakovou sadu použít. To se provádí pomocí `add_eci_codetext(eci, text)`. První argument je číselná hodnota ECI; druhý je skutečný text.

```python
# Step 3: Append data that must be preceded by an ECI (e.g., 3 for UTF‑8)
# This ensures the text "Привет" is correctly interpreted as UTF‑8
codetext_builder.add_eci_codetext(3, "Привет")
```

*Proč ECI 3*: Podle specifikace ISO/IEC 18004 ECI 3 odpovídá UTF‑8. Vložení této značky umožní čtečce čárových kódů dekódovat následující bajty jako UTF‑8, čímž zachová cyrilické znaky.

### Zpracování dalších kódování

Pokud potřebujete ISO‑8859‑1 (západoevropské), použijete `add_eci_codetext(4, "¡Hola!")`. Pro Shift‑JIS (japonština) je hodnota ECI 20:

```python
codetext_builder.add_eci_codetext(20, "こんにちは")
```

Vždy ověřte, že cílová knihovna čárových kódů podporuje zvolenou hodnotu ECI; nepodporované ECI způsobí selhání kódování.

## Krok 4: Získat kombinovaný rozšířený‑kódový‑text řetězec

Po přidání všech fragmentů zavolejte `get_extended_codetext()`, abyste získali finální řetězec. Tento řetězec obsahuje všechny potřebné únikové sekvence ECI.

```python
# Step 4: Retrieve the combined extended‑codetext string
extended_codetext = codetext_builder.get_extended_codetext()

print("Extended codetext:", extended_codetext)
```

**Očekávaný výstup** (zobrazený jako Python `repr` pro přehlednost):

```
Extended codetext: 'ABC123\x1B\x1D\x03Привет'
```

*Rozpis*:

- `ABC123` – prostý ASCII segment.  
- `\x1B\x1D\x03` – úniková sekvence ECI pro UTF‑8 (ESC GS 0x03).  
- `Привет` – slovo v cyrilici zakódované v UTF‑8.

Přesné únikové bajty se mohou lišit v závislosti na implementaci knihovny, ale logické pořadí bude vždy *prostý → značka ECI → Unicode text*.

## Kompletní spustitelný příklad

Spojením všeho dohromady získáte samostatný skript, který můžete zkopírovat do souboru pojmenovaného `create_extended_codetext.py` a okamžitě spustit.

```python
#!/usr/bin/env python3
"""
Create extended codetext in Python using ExtCodetextBuilder.
Demonstrates plain text, UTF‑8 ECI, and how to retrieve the final string.
"""

from extcodetext import ExtCodetextBuilder

def main() -> None:
    # 1️⃣ Create the builder
    builder = ExtCodetextBuilder()

    # 2️⃣ Add a plain ASCII segment
    builder.add_plain_codetext("ABC123")

    # 3️⃣ Add a UTF‑8 segment (ECI 3) containing Cyrillic characters
    builder.add_eci_codetext(3, "Привет")

    # 4️⃣ Retrieve and display the extended codetext
    result = builder.get_extended_codetext()
    print("Extended codetext:", result)

if __name__ == "__main__":
    main()
```

Spuštěním skriptu se vytiskne kombinovaný řetězec, připravený pro jakýkoli enkodér čárových kódů, který přijímá vstup rozšířeného‑kódového‑textu.

## Běžné úskalí a jak se jim vyhnout

| Příznak | Pravděpodobná příčina | Řešení |
|---|---|---|
| `UnicodeEncodeError` při volání `add_eci_codetext` | Poskytnutí řetězce, který obsahuje znaky, jež nelze reprezentovat ve zvoleném ECI | Ověřte, že ECI odpovídá skutečnému kódování řetězce (např. použijte ECI 3 pro jakýkoli UTF‑8 text). |
| Chybějící značka ECI ve finálním výstupu | Náhodné použití `add_plain_codetext` pro ne‑ASCII data | Přepněte na `add_eci_codetext` pro jakýkoli znak mimo ASCII rozsah. |
| Čtečka čárových kódů zobrazuje poškozené znaky | Čtečka nepodporuje vybranou hodnotu ECI | Zvolte univerzálně podporovanou hodnotu ECI (UTF‑8 je široce podporováno) nebo se vraťte k ISO‑8859‑1, pokud to cílový jazyk umožňuje. |
| `get_extended_codetext` vrací prázdný řetězec | Nebyl přidán žádný fragment před voláním metody | Ujistěte se, že je vykonáno alespoň jedno volání `add_*`. |

### Okrajový případ: Prázdné řetězce

Volání `add_plain_codetext("")` nebo `add_eci_codetext(3, "")` je neškodné; builder jednoduše ignoruje prázdný fragment. Opakovaná prázdná volání však mohou vést k zbytečným značkám ECI. Chraňte se tím, že před přidáním zkontrolujete délku řetězce.

```python
text = "data"
if text:
    builder.add_plain_codetext(text)
```

## Rozšíření vzoru pro dynamická data

V reálných aplikacích často vytváříte rozšířený kódový text z uživatelského vstupu nebo záznamu v databázi. Následující úryvek ukazuje smyčku, která zpracovává seznam dvojic `(type, value)`, kde `type` je buď `"plain"` nebo `"eci"`.

```python
fragments = [
    ("plain", "Order#"),
    ("plain", "98765"),
    ("eci", (3, "商品")),   # Japanese word "商品" (product) encoded as UTF‑8
]

for kind, payload in fragments:
    if kind == "plain":
        builder.add_plain_codetext(payload)
    elif kind == "eci":
        eci_val, text = payload
        builder.add_eci_codetext(eci_val, text)
    else:
        raise ValueError(f"Unsupported fragment type: {kind}")

print(builder.get_extended_codetext())
```

Tento přístup se dobře škáluje: můžete načíst definice fragmentů z JSON, CSV nebo API, aniž byste měnili základní logiku sestavování.

## Testování výstupu

Rychlý unit test zajistí, že builder se chová podle očekávání. Použití `pytest`:

```python
def test_extended_codetext():
    b = ExtCodetextBuilder()
    b.add_plain_codetext("X")
    b.add_eci_codetext(3, "✓")   # Check mark in UTF‑8
    result = b.get_extended_codetext()
    assert result.startswith("X")
    assert "\x1B\x1D\x03".encode() in result.encode()
```

Spuštění `pytest` by mělo projít, což potvrzuje, že značka ECI se objeví přesně tam, kde má.

## Související koncepty, které můžete dále prozkoumat

* **Knihovny pro kódování čárových kódů** – např. `python-barcode`, `zxing` bindingy, které přijímají řetězec rozšířeného kódového textu přímo.  
* **Referenční tabulka ECI** – úplný seznam číselných hodnot ECI je publikován v ISO/IEC 18004 a může být uložen jako Python slovník pro vyhledávání.  
* **Úrovně opravy chyb** – při generování QR kódů kombinujte rozšířený kódový text s vhodnou úrovní opravy chyb (L, M, Q, H) pro spolehlivé skenování.

## Závěr

Nyní víte, jak **vytvořit rozšířený kódový text** v Pythonu pomocí `ExtCodetextBuilder`. Proces je přímočarý:

1. Instanciujte builder.  
2. Připojte prosté a ECI‑kódované fragmenty podle potřeby.  
3. Získejte finální řetězec a předávejte jej svému generátoru čárových kódů.

Podle výše uvedeného vzoru můžete zvládnout libovolnou kombinaci ASCII a Unicode dat, vyhnout se běžným chybám kódování a vytvořit řetězce připravené pro čárové kódy, které fungují napříč širokou škálou skenerů. Experimentujte s různými ECI, integrujte builder do svého datového potrubí a získáte pevný základ pro všechny své potřeby rozšířeného kódového textu.

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}