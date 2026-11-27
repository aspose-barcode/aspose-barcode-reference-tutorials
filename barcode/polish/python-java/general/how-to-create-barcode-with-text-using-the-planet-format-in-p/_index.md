---
category: general
date: 2026-11-27
description: Dowiedz się, jak tworzyć kod kreskowy z tekstem i generować kod kreskowy
  planety w Pythonie — przewodnik krok po kroku do uzyskania obrazu PNG w wysokiej
  rozdzielczości.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode with text
- how to generate barcode
- generate planet barcode
- Python barcode generation
- high‑resolution barcode PNG
language: pl
lastmod: 2026-11-27
og_description: Utwórz kod kreskowy z tekstem i wygeneruj kod planetarny w Pythonie.
  Skorzystaj z tego kompletnego przewodnika, aby uzyskać wysokiej rozdzielczości PNG.
og_image_alt: Screenshot showing how to create barcode with text using the Planet
  barcode generator
og_title: Utwórz kod kreskowy z tekstem w Pythonie – łatwo generuj kod kreskowy Planet
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
title: Jak stworzyć kod kreskowy z tekstem używając formatu Planet w Pythonie
url: /pl/python-java/general/how-to-create-barcode-with-text-using-the-planet-format-in-p/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć kod kreskowy z tekstem przy użyciu formatu Planet w Pythonie

Jeśli potrzebujesz **utworzyć kod kreskowy z tekstem** dla systemu pocztowego, ten tutorial pokaże Ci dokładnie, jak to zrobić. Zobaczysz zwięzły, kompleksowy przykład, który generuje kod kreskowy Planet, dostosowuje rozdzielczość i zapisuje wynik jako obraz PNG.

Generowanie kodów kreskowych jest powszechnym wymogiem w logistyce, zarządzaniu zapasami i aplikacjach biletowych. W tym przewodniku nauczysz się nie tylko **jak generować pliki kodów kreskowych**, ale także dlaczego każdy krok konfiguracji ma znaczenie i jak unikać typowych pułapek.

## Czego się nauczysz

* Skonfiguruj generator kodu kreskowego Planet z własnym tekstem.  
* Dostosuj wymiar X, aby zwiększyć ostrość obrazu.  
* Zapisz kod kreskowy jako plik PNG, który można wydrukować lub wyświetlić w sieci.  
* Rozszerz przykład na inne typy kodów kreskowych lub formaty wyjściowe.  

## Wymagania wstępne

* Python 3.8 lub nowszy.  
* Pakiet `aspose-barcode` (lub dowolna kompatybilna biblioteka, która udostępnia `BarcodeGenerator`, `EncodeTypes` i `BarCodeImageFormat`).  
* Podstawowa znajomość skryptów w Pythonie.  

Możesz zainstalować wymagany pakiet za pomocą:

```bash
pip install aspose-barcode
```

---

## Krok 1: Utwórz kod kreskowy z tekstem – zainicjalizuj generator

Pierwszą rzeczą, którą musisz zrobić, jest stworzenie instancji `BarcodeGenerator`, która wie, jaką symbologię użyć i jaki tekst zakodować. Dla kodu kreskowego Planet wartość wyliczeniowa `EncodeTypes.Planet` informuje bibliotekę, aby zastosowała specyfikację USPS Planet.

```python
# Import the necessary classes from the Aspose.BarCode library
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1: Initialize the generator with the desired text
# The text "123456" will appear beneath the Planet barcode pattern.
gen = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**Dlaczego to jest ważne:**  
Obiekt `BarcodeGenerator` kapsułkuje wszystkie ustawienia kodu kreskowego. Przekazanie tekstu w momencie konstrukcji gwarantuje, że zakodowana wartość pozostaje niezmienna przez cały proces, co eliminuje przypadkowe niezgodności później.

---

## Krok 2: Dostosuj ustawienia – jak wygenerować kod kreskowy o wyższej rozdzielczości

Kod kreskowy o niskiej rozdzielczości może wyglądać rozmycie po wydrukowaniu na drukarce etykiet. Wymiar X (szerokość modułu) kontroluje rozmiar każdego pojedynczego paska. Ustawienie go na 4 piksele daje wyraźny, wysokiej rozdzielczości obraz odpowiedni dla większości nowoczesnych drukarek.

```python
# Step 2: Increase the X‑dimension to 4 pixels for better clarity
gen.parameters.barcode.x_dimension.pixels = 4
```

**Wyjaśnienie:**  
* `gen.parameters.barcode.x_dimension.pixels` bezpośrednio odpowiada fizycznej szerokości pojedynczego modułu.  
* Wartość **4** oznacza, że każdy pasek ma cztery piksele szerokości, co w przybliżeniu odpowiada 0,127 mm przy 300 dpi — mieści się w zalecanym zakresie dla kodów kreskowych USPS Planet.  

**Wskazówka:** Jeśli potrzebujesz innej rozdzielczości DPI, oblicz odpowiednią szerokość w pikselach (np. 2 piksele dla 150 dpi, 8 pikseli dla 600 dpi).

---

## Krok 3: Zapisz obraz – wygeneruj kod kreskowy Planet jako PNG

Teraz, gdy generator jest skonfigurowany, możesz wyrenderować kod kreskowy do pliku obrazu. PNG jest bezstratny, co zapewnia zachowanie dokładnego wzoru modułów.

```python
# Step 3: Save the generated barcode as a PNG image
output_path = "output/PostalPlanetBarHeightNone.png"
gen.save(output_path, BarCodeImageFormat.Png)
print(f"Barcode saved to {output_path}")
```

**Wynik:**  
Uruchomienie skryptu tworzy plik o nazwie `PostalPlanetBarHeightNone.png`, który zawiera kod kreskowy Planet kodujący ciąg “123456”. Wymiary obrazu będą wynosić około 200 × 100 pikseli, w zależności od wybranego wymiaru X.

---

## Opcjonalnie: Zweryfikuj kod kreskowy wizualnie

Możesz szybko otworzyć wygenerowany PNG w dowolnej przeglądarce obrazów, aby potwierdzić, że kod kreskowy jest ostry, a tekst czytelny dla człowieka znajduje się pod wzorem.

```python
from PIL import Image

img = Image.open(output_path)
img.show()
```

Jeśli obraz wydaje się rozmyty, wróć do **Krok 2** i zwiększ wymiar X, aż paski będą wyraźnie zdefiniowane.

---

## Typowe warianty i przypadki brzegowe

| Sytuacja | Dostosowanie |
|-----------|------------|
| **Inna długość tekstu** | Kody kreskowe Planet obsługują do 12 znaków numerycznych. Jeśli przekroczysz tę liczbę, biblioteka zgłosi wyjątek. |
| **Alternatywny format wyjściowy** | Zastąp `BarCodeImageFormat.Png` przez `BarCodeImageFormat.Jpeg` lub `BarCodeImageFormat.Bmp` dla innych zastosowań. |
| **Niestandardowe kolory pierwszego planu/tła** | Użyj `gen.parameters.barcode.barcode_color = Color.Blue` oraz `gen.parameters.barcode.back_color = Color.White`. |
| **Brak tekstu czytelnego dla człowieka** | Ustaw `gen.parameters.barcode.hide_code_text = True`, aby wygenerować kod kreskowy bez dolnego podpisu. |
| **Generowanie wsadowe** | Iteruj po liście ciągów, utwórz nowy `BarcodeGenerator` dla każdego i zapisz je do unikalnie nazwanych plików. |

Te warianty pozwalają Ci **generować pliki kodu kreskowego Planet**, które spełniają szeroki zakres wymagań biznesowych.

---

## Pełny skrypt – gotowy do uruchomienia

Poniżej znajduje się kompletny, samodzielny skrypt, który możesz skopiować, wkleić i uruchomić. Zawiera wszystkie importy, obsługę błędów i komentarze.

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

**Wyjaśnienie skryptu**

* Funkcja `create_planet_barcode` kapsułkuje trzy podstawowe kroki, co czyni kod wielokrotnego użytku.  
* Walidacja wejścia zapewnia, że spełniasz specyfikację Planet (tylko cyfry, maksymalnie 12 znaków).  
* Funkcja automatycznie tworzy folder wyjściowy, więc nie musisz ręcznie zarządzać katalogami.  
* Po wygenerowaniu skrypt otwiera obraz przy użyciu Pillow (`PIL`) w celu natychmiastowej weryfikacji.

---

## Zakończenie

Teraz wiesz, jak **utworzyć kod kreskowy z tekstem** i **generować pliki kodu kreskowego Planet** w Pythonie. Przewodnik obejmował inicjalizację, dostrajanie rozdzielczości i zapis do pliku, wraz z opcjonalnymi dostosowaniami i typowymi przypadkami brzegowymi.  

Od tego momentu możesz:

* Zastąp `EncodeTypes.Planet` innymi symbolami (np. `EncodeTypes.Code128`), aby ponownie użyć tego samego wzorca.  
* Zintegruj funkcję z usługą webową, która zwraca obrazy kodów kreskowych na żądanie.  
* Eksperymentuj z przetwarzaniem wsadowym, aby wygenerować tysiące kodów kreskowych do masowej wysyłki.  

Śmiało dostosuj skrypt do potrzeb swojego projektu i podziel się wynikami w komentarzach. Szczęśliwego kodowania!

## Co powinieneś się nauczyć dalej?

Następujące tutoriale obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak generować kod kreskowy w Pythonie – kompletny przewodnik krok po kroku](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Utwórz kod kreskowy PNG w Pythonie – przewodnik krok po kroku](/barcode/english/python-java/general/create-barcode-png-in-python-step-by-step-guide/)
- [Jak utworzyć kod kreskowy Planet PNG w Pythonie](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}