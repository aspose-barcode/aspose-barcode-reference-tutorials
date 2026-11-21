---
category: general
date: 2026-11-20
description: Dowiedz się, jak używać ECI, generować kod QR z tekstu, wyczyścić builder
  oraz zapisać obraz QR przy użyciu biblioteki Python barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use eci
- generate qr from text
- how to clear builder
- save qr image
- clear qr builder
language: pl
lastmod: 2026-11-20
og_description: Jak używać ECI do generowania kodu QR z tekstu, wyczyścić kreator
  QR i zapisać obraz QR – kompletny przewodnik krok po kroku.
og_image_alt: Diagram illustrating how to use ECI to generate a QR code and save the
  QR image
og_title: Jak używać ECI w generowaniu kodów QR w Pythonie
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to use ECI, generate QR from text, clear the builder, and
    save QR image using the Python barcode library.
  headline: How to use ECI in QR code generation with Python
  type: TechArticle
tags:
- QR code
- Python
- barcode
- ECI
title: Jak używać ECI przy generowaniu kodów QR w Pythonie
url: /pl/python/general/how-to-use-eci-in-qr-code-generation-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak używać ECI przy generowaniu kodów QR w Pythonie

Jeśli potrzebujesz **how to use eci** przy tworzeniu kodów QR, ten przewodnik pokazuje dokładne kroki. Zobaczysz, jak generować QR z tekstu, wyczyścić builder i ostatecznie zapisać obraz QR — wszystko przy użyciu kilku linii Pythona.

Kody QR zawierające dane wielojęzyczne często wymagają segmentu Extended Channel Interpretation (ECI), aby skanery wiedziały, którego zestawu znaków użyć. Ten tutorial przeprowadzi Cię przez budowanie rozszerzonego kodetextu, czyszczenie buildera przy ponownym użyciu oraz zapisywanie wyniku jako pliku PNG.

## Prerequisites

- Zainstalowany Python 3.8+.
- Pakiet Aspose.BarCode for Python via .NET (lub dowolna kompatybilna biblioteka `barcode`, która udostępnia `ExtCodetextBuilder` i `BarcodeGenerator`).
- Podstawowa znajomość koncepcji kodów QR.

Install the library with pip:

```bash
pip install aspose-barcode
```

> **Wskazówka:** Używaj wirtualnego środowiska, aby uniknąć konfliktów wersji.

## Krok 1: Importuj wymagane klasy

Podstawowe klasy, z którymi będziesz pracować, to `ExtCodetextBuilder` do konstruowania rozszerzonego kodu tekstowego oraz `BarcodeGenerator` do renderowania kodu QR.

```python
from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
```

Te importy dają dostęp do metod buildera (`add_plain_codetext`, `add_eci_codetext` itp.) oraz funkcji generatora `set_code_text`, `set_symbology` i `save`.

## Krok 2: Utwórz i skonfiguruj ExtCodetextBuilder

Utworzenie nowej instancji buildera jest pierwszym konkretnym przykładem **how to use eci**. Możesz także wyczyścić builder później, jeśli potrzebujesz go ponownie użyć.

```python
# Create an ExtCodetextBuilder instance
extended_text_builder = ExtCodetextBuilder()

# Optional: clear any previous items (useful when reusing the same builder)
extended_text_builder.clear()   # this demonstrates how to clear builder
```

Wywołanie `clear()` zapewnia, że builder zaczyna od czystego stanu, co jest niezbędne przy generowaniu wielu kodów QR w pętli.

## Krok 3: Dodaj zwykły (nie‑ECI) kod tekstowy

Zwykły tekst nie wymaga segmentu ECI. Użyj `add_plain_codetext` dla ciągów kompatybilnych z ASCII.

```python
# Add plain codetext (e.g., an English phrase)
extended_text_builder.add_plain_codetext("HelloWorld")
```

Builder teraz zawiera zwykły segment `"HelloWorld"`.

## Krok 4: Dodaj segment zakodowany ECI

Oto sedno **how to use eci**: określasz wartość ECI (26 dla UTF‑8) i podajesz ciąg Unicode, który chcesz zakodować. Dzięki temu kod QR może zawierać rosyjski, chiński lub dowolny inny język, który nie jest objęty domyślnym zestawem ISO‑8859‑1.

```python
# Add ECI‑encoded codetext (ECI value 26 = UTF‑8, Russian “Hello”)
extended_text_builder.add_eci_codetext(26, "Привет")
```

> **Dlaczego to ważne:** Bez wskaźnika ECI skaner zinterpretowałby bajty przy użyciu domyślnego zestawu znaków i wyświetliłby zniekształcone znaki dla tekstu nie‑ASCII.

## Krok 5: Pobierz połączony rozszerzony ciąg kodu tekstowego

Po dodaniu wszystkich wymaganych segmentów pobierz ostateczny ciąg, który zostanie przekazany do generatora QR.

```python
combined_extended_text = extended_text_builder.get_extended_codetext()
print("Extended codetext:", combined_extended_text)
```

Wydrukowana wartość wygląda mniej więcej tak:

```
Extended codetext: [ECI26]ПриветHelloWorld
```

Dokładny format zależy od biblioteki, ale istotne jest, że znacznik ECI (`[ECI26]`) poprzedza ładunek UTF‑8.

## Krok 6: Wygeneruj kod QR używając połączonego tekstu

Teraz możesz **generate QR from text** przekazując rozszerzony kod tekstowy do `BarcodeGenerator`.

```python
# Initialize the QR generator
qr_generator = barcode.generation.BarcodeGenerator()

# Assign the combined extended codetext
qr_generator.set_code_text(combined_extended_text)

# Choose QR symbology (the library supports many, QR is the most common)
qr_generator.set_symbology(barcode.Symbology.QR)

# Save the QR image to disk – this demonstrates how to save QR image
output_path = "qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Kiedy otworzysz `qr_extended.png`, pojawi się kod QR, który koduje zarówno zwykły angielski ciąg, jak i rosyjskie powitanie. Zeskanowanie go nowoczesnym skanerem QR poprawnie wyświetli „HelloWorld” i „Привет”.

### Dlaczego powinieneś wywołać `clear()` przed ponownym użyciem buildera

Jeśli generujesz wiele kodów QR w pętli, zapomnienie o wyczyszczeniu buildera spowoduje połączenie starych segmentów z nowymi, co doprowadzi do nieprawidłowego kodu. Oto szybki wzorzec:

```python
for text, eci, unicode_str in data_set:
    extended_text_builder.clear()                       # ensures a fresh start
    extended_text_builder.add_plain_codetext(text)
    extended_text_builder.add_eci_codetext(eci, unicode_str)
    qr_generator.set_code_text(extended_text_builder.get_extended_codetext())
    qr_generator.save(f"qr_{text}.png")
```

Ten fragment ilustruje **how to clear builder** i **how to generate QR from text** wielokrotnie.

## Przypadki brzegowe i typowe pułapki

| Sytuacja | Na co zwrócić uwagę | Jak postąpić |
|-----------|-------------------|---------------|
| **Nieobsługiwana wartość ECI** | Biblioteka rzuca `InvalidArgumentException`. | Używaj tylko wartości ECI wymienionych w specyfikacji (np. 26 dla UTF‑8, 20 dla Shift‑JIS). |
| **Bardzo długi połączony tekst** | Wersja QR może przekroczyć maksymalną pojemność. | Zwiększ wersję QR automatycznie (`qr_generator.set_qr_version(QRVersion.AUTO)`) lub podziel dane na wiele kodów QR. |
| **Błędy uprawnień systemu plików** | `save` kończy się niepowodzeniem z `IOError`. | Upewnij się, że docelowy katalog istnieje i proces ma uprawnienia do zapisu. |
| **Niepoprawne wyświetlanie zestawu znaków** | Skaner pokazuje zniekształcone znaki. | Zweryfikuj, czy prawidłowa wartość ECI odpowiada rzeczywistemu kodowaniu ciągu. |

## Pełny działający przykład

Poniżej znajduje się samodzielny skrypt, który możesz skopiować, wkleić i uruchomić. Zawiera wszystkie importy, obsługę błędów i komentarze dla przejrzystości.

```python
# qr_eci_example.py
# Demonstrates how to use ECI, generate QR from text, clear the builder,
# and save QR image using Aspose.BarCode for Python.

from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
import os

def generate_qr(plain_text: str, eci_value: int, unicode_text: str, out_file: str):
    """
    Creates a QR code that contains both plain and ECI‑encoded text.
    Parameters:
        plain_text – ASCII‑compatible string.
        eci_value  – Numeric ECI identifier (e.g., 26 for UTF‑8).
        unicode_text – Text that requires the specified ECI.
        out_file – Destination file path for the PNG image.
    """
    # Step 1: instantiate and clear the builder
    builder = ExtCodetextBuilder()
    builder.clear()                       # how to clear builder

    # Step 2: add segments
    builder.add_plain_codetext(plain_text)
    builder.add_eci_codetext(eci_value, unicode_text)

    # Step 3: retrieve combined text
    combined = builder.get_extended_codetext()
    print("Combined extended codetext:", combined)

    # Step 4: generate QR code
    generator = barcode.generation.BarcodeGenerator()
    generator.set_code_text(combined)
    generator.set_symbology(barcode.Symbology.QR)

    # Ensure output directory exists
    os.makedirs(os.path.dirname(out_file), exist_ok=True)

    # Step 5: save QR image – how to save QR image
    generator.save(out_file)
    print(f"QR code saved as {out_file}")

if __name__ == "__main__":
    # Example usage
    generate_qr(
        plain_text="HelloWorld",
        eci_value=26,               # UTF‑8
        unicode_text="Привет",      # Russian "Hello"
        out_file="output/qr_extended.png"
    )
```

Uruchomienie tego skryptu tworzy `output/qr_extended.png`, kod QR, który poprawnie koduje zarówno angielski, jak i rosyjski tekst.

## Zakończenie

Teraz wiesz **how to use eci** przy budowaniu kodów QR, jak **clear the QR builder** przed ponownym użyciem, jak **generate QR from text**, oraz dokładne kroki, aby **save QR image** przy użyciu Pythona. Stosując powyższy wzorzec, możesz osadzić dowolny ciąg Unicode w kodzie QR, zachowując przewidywalny stan buildera.

### Co dalej?

- Zbadaj inne wartości ECI dla języków takich jak chiński (ECI 20) lub ISO‑8859‑5.
- Dostosuj poziomy korekcji błędów (`qr_generator.set_error_correction_level`), aby zwiększyć niezawodność skanowania.
- Połącz wiele segmentów ECI w jednym kodzie QR dla wiadomości wielojęzycznych.

Miłego kodowania i przyjemnego tworzenia wielojęzycznych kodów QR!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak generować kod kreskowy z ECI przy użyciu Aspose.Barcode Python](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)
- [Jak wygenerować obraz kodu QR w Pythonie z Aspose.Barcode – Pełny przewodnik](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Jak generować kod kreskowy w Pythonie – kompletny przewodnik krok po kroku](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}