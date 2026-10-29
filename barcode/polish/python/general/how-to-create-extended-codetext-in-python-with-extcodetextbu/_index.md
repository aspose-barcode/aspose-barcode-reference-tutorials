---
category: general
date: 2026-10-28
description: Dowiedz się, jak tworzyć rozszerzony kodtekst w Pythonie przy użyciu
  ExtCodetextBuilder. Zawiera dane w formacie plain i zakodowane ECI, kod krok po
  kroku oraz wskazówki najlepszych praktyk.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create extended codetext
- ExtCodetextBuilder Python
- add plain codetext
- add eci codetext
- extended‑codetext example
language: pl
lastmod: 2026-10-28
og_description: Utwórz rozszerzony kod tekstowy w Pythonie przy użyciu ExtCodetextBuilder.
  Ten samouczek pokazuje obsługę danych zwykłych i kodowanych ECI, kompletny działający
  kod oraz typowe pułapki.
og_image_alt: Diagram showing how to create extended codetext using ExtCodetextBuilder
  in Python
og_title: Tworzenie rozszerzonego kodu w Pythonie – kompletny przewodnik
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
title: Jak utworzyć rozszerzony kodtekst w Pythonie za pomocą ExtCodetextBuilder
url: /pl/python/general/how-to-create-extended-codetext-in-python-with-extcodetextbu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak tworzyć rozszerzony kodtekst w Pythonie przy użyciu ExtCodetextBuilder

Jeśli potrzebujesz **tworzyć rozszerzony kodtekst** dla aplikacji kodów kreskowych lub data‑matrix, ten przewodnik pokaże Ci dokładnie, jak to zrobić w Pythonie. Zobaczysz, jak łączyć zwykły tekst, dodawać sekcje ECI (Extended Channel Interpretation) dla znaków Unicode oraz uzyskać pojedynczy, prawidłowo sformatowany ciąg gotowy do kodowania.

Samouczek obejmuje wszystko, od instalacji wymaganego pakietu po obsługę przypadków brzegowych, takich jak nieobsługiwane wartości ECI. Po zakończeniu będziesz mieć wzorzec, który możesz wstawić do dowolnego projektu potrzebującego **tworzyć rozszerzony kodtekst**.

## Czego się nauczysz

* Rola `ExtCodetextBuilder` przy budowaniu ciągów o mieszanym kodowaniu.  
* Jak **dodawać zwykły kodtekst** i **dodawać kodtekst ECI** w jednej instancji buildera.  
* Jak zweryfikować ostateczny wynik i rozwiązywać typowe problemy.  
* Warianty dla innych zestawów znaków (np. ISO‑8859‑1, Shift‑JIS).  

### Wymagania wstępne

* Python 3.8 lub nowszy.  
* Pakiet `extcodetext` (lub podobna biblioteka dostarczająca `ExtCodetextBuilder`). Zainstaluj go przy pomocy:

```bash
pip install extcodetext
```

* Podstawowa znajomość Unicode i wartości ECI – ECI 3 odpowiada UTF‑8, ECI 4 ISO‑8859‑1, itp.

> **Wskazówka:** Miej pod ręką tabelę referencyjną numerów ECI. Zapobiega to przypadkowym niezgodnościom między zadeklarowanym kodowaniem a rzeczywistą sekwencją bajtów.

## Understanding ExtCodetextBuilder

`ExtCodetextBuilder` jest małym narzędziem, które konkatenatuje wiele fragmentów tekstu, automatycznie wstawiając wymagane znaczniki ECI. Znacznik ECI informuje downstreamowy enkoder kodów kreskowych, jaki zestaw znaków ma użyć dla kolejnych bajtów. Bez znacznika znaki nie‑ASCII byłyby źle interpretowane.

Builder działa w trzech prostych fazach:

1. **Create** the builder instance.  
2. **Append** plain or ECI‑encoded fragments.  
3. **Retrieve** the combined extended‑codetext string.

Poniżej przechodzimy przez każdą fazę z konkretnym kodem.

## Step 1: Create an ExtCodetextBuilder instance

Pierwsza linia konstruuje obiekt, który będzie przechowywał wszystkie fragmenty. W tym momencie nie jest wymagana żadna konfiguracja.

```python
from extcodetext import ExtCodetextBuilder

# Step 1: Create an ExtCodetextBuilder instance
codetext_builder = ExtCodetextBuilder()
```

*Dlaczego to ważne*: Inicjalizacja buildera alokuje wewnętrzny bufor. Wszystkie późniejsze wywołania `add_*` działają na tym buforze, zapewniając kolejność, którą określasz.

## Step 2: Append plain (un‑encoded) data

Zwykłe dane składają się z znaków należących do domyślnego zestawu znaków (zazwyczaj ASCII). Użyj `add_plain_codetext` dla takich fragmentów.

```python
# Step 2: Append plain (un‑encoded) data to the builder
codetext_builder.add_plain_codetext("ABC123")
```

*Explanation*: The string `"ABC123"` contains only ASCII characters, so no ECI marker is needed. The method simply appends the raw bytes to the internal buffer.

## Step 3: Append data that must be preceded by an ECI

When you need to embed Unicode characters—like Cyrillic, Japanese, or emoji—you must tell the encoder which charset to use. This is done with `add_eci_codetext(eci, text)`. The first argument is the numeric ECI value; the second is the actual text.

```python
# Step 3: Append data that must be preceded by an ECI (e.g., 3 for UTF‑8)
# This ensures the text "Привет" is correctly interpreted as UTF‑8
codetext_builder.add_eci_codetext(3, "Привет")
```

*Why ECI 3*: According to the ISO/IEC 18004 specification, ECI 3 maps to UTF‑8. By inserting this marker, the barcode reader knows to decode the following bytes as UTF‑8, preserving the Cyrillic characters.

### Handling other encodings

If you need ISO‑8859‑1 (Western European) you would use `add_eci_codetext(4, "¡Hola!")`. For Shift‑JIS (Japanese) the ECI value is 20:

```python
codetext_builder.add_eci_codetext(20, "こんにちは")
```

Always verify that the target barcode library supports the chosen ECI value; unsupported ECIs will cause encoding failures.

## Step 4: Retrieve the combined extended‑codetext string

After all fragments are added, call `get_extended_codetext()` to obtain the final string. This string includes any necessary ECI escape sequences.

```python
# Step 4: Retrieve the combined extended‑codetext string
extended_codetext = codetext_builder.get_extended_codetext()

print("Extended codetext:", extended_codetext)
```

**Expected output** (displayed as a Python `repr` for clarity):

```
Extended codetext: 'ABC123\x1B\x1D\x03Привет'
```

*Breakdown*:

* `ABC123` – plain ASCII segment.  
* `\x1B\x1D\x03` – the ECI escape sequence for UTF‑8 (ESC GS 0x03).  
* `Привет` – the UTF‑8 encoded Cyrillic word.

The exact escape bytes may differ depending on the library implementation, but the logical order will always be *plain → ECI marker → Unicode text*.

## Full runnable example

Putting everything together, here’s a self‑contained script you can copy‑paste into a file named `create_extended_codetext.py` and run immediately.

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

Running the script prints the combined string, ready for any barcode encoder that accepts extended‑codetext input.

## Common pitfalls and how to avoid them

| Objaw | Prawdopodobna przyczyna | Rozwiązanie |
|---|---|---|
| `UnicodeEncodeError` przy wywoływaniu `add_eci_codetext` | Podanie ciągu zawierającego znaki nieodpowiadające wybranemu ECI | Sprawdź, czy ECI odpowiada rzeczywistemu kodowaniu ciągu (np. użyj ECI 3 dla dowolnego tekstu UTF‑8). |
| Brak znacznika ECI w ostatecznym wyniku | Przypadkowe użycie `add_plain_codetext` dla danych nie‑ASCII | Użyj `add_eci_codetext` dla każdego znaku spoza zakresu ASCII. |
| Skaner kodów kreskowych wyświetla zniekształcone znaki | Skaner nie obsługuje wybranej wartości ECI | Wybierz powszechnie obsługiwany ECI (UTF‑8 jest szeroko wspierany) lub użyj ISO‑8859‑1, jeśli docelowy język na to pozwala. |
| `get_extended_codetext` zwraca pusty ciąg | Nie dodano żadnych fragmentów przed wywołaniem metody | Upewnij się, że wykonano przynajmniej jedno wywołanie `add_*`. |

### Edge case: Empty strings

Calling `add_plain_codetext("")` or `add_eci_codetext(3, "")` is harmless; the builder simply ignores the empty fragment. However, repeated empty calls can lead to unnecessary ECI markers. Guard against this by checking string length before adding.

```python
text = "data"
if text:
    builder.add_plain_codetext(text)
```

## Extending the pattern for dynamic data

In real‑world applications you often build the extended codetext from user input or a database record. The following snippet shows a loop that processes a list of `(type, value)` tuples, where `type` is either `"plain"` or `"eci"`.

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

This approach scales nicely: you can read the fragment definitions from JSON, CSV, or an API without changing the core building logic.

## Testing the output

A quick unit test ensures the builder behaves as expected. Using `pytest`:

```python
def test_extended_codetext():
    b = ExtCodetextBuilder()
    b.add_plain_codetext("X")
    b.add_eci_codetext(3, "✓")   # Check mark in UTF‑8
    result = b.get_extended_codetext()
    assert result.startswith("X")
    assert "\x1B\x1D\x03".encode() in result.encode()
```

Running `pytest` should pass, confirming that the ECI marker appears exactly where it should.

## Related concepts you might explore next

* **Biblioteki kodowania kodów kreskowych** – np. `python-barcode`, powiązania `zxing`, które przyjmują bezpośrednio ciąg rozszerzonego kodtekstu.  
* **Referencja tabeli ECI** – pełna lista numerycznych wartości ECI jest publikowana przez ISO/IEC 18004 i może być przechowywana jako słownik Pythona do wyszukiwania.  
* **Poziomy korekcji błędów** – przy generowaniu kodów QR, łącz rozszerzony kodtekst z odpowiednią korekcją błędów (L, M, Q, H) dla niezawodnego skanowania.

## Conclusion

You now know how to **create extended codetext** in Python using `ExtCodetextBuilder`. The process is straightforward:

1. Zainicjalizuj builder.  
2. Dodawaj zwykłe i zakodowane ECI fragmenty w razie potrzeby.  
3. Pobierz ostateczny ciąg i przekaż go do generatora kodów kreskowych.

By following the pattern above you can handle any mix of ASCII and Unicode data, avoid common encoding errors, and produce barcode‑ready strings that work across a wide range of scanners. Experiment with different ECIs, integrate the builder into your data‑pipeline, and you’ll have a solid foundation for all your extended‑codetext needs.

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}