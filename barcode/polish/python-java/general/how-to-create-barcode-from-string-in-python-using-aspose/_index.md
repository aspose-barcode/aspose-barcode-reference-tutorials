---
category: general
date: 2026-10-15
description: Utwórz kod kreskowy z ciągu znaków przy użyciu Aspose.Barcode dla Pythona.
  Dowiedz się, jak wygenerować kod kreskowy, ustawić wymiary i zapisać jako PNG w
  kilka minut.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from string
- how to generate barcode
- barcode generator example
- generate postal barcode
- aspose barcode python
language: pl
lastmod: 2026-10-15
og_description: Utwórz kod kreskowy z ciągu znaków przy użyciu Aspose.Barcode dla
  Pythona. Ten samouczek pokazuje krok po kroku, jak wygenerować kod kreskowy pocztowy
  i zapisać go jako PNG.
og_image_alt: Screenshot of a generated postal barcode saved as PNG
og_title: Utwórz kod kreskowy z ciągu znaków w Pythonie – przewodnik Aspose
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode from string with Aspose.Barcode for Python. Learn how
    to generate barcode, set dimensions, and save as PNG in minutes.
  headline: How to create barcode from string in Python using Aspose
  type: TechArticle
tags:
- barcode
- python
- Aspose
title: Jak utworzyć kod kreskowy z ciągu znaków w Pythonie przy użyciu Aspose
url: /pl/python-java/general/how-to-create-barcode-from-string-in-python-using-aspose/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć kod kreskowy z ciągu znaków w Pythonie przy użyciu Aspose

Jeśli potrzebujesz szybko **create barcode from string**, Aspose.Barcode for Python ułatwia to. W tym przewodniku zobaczysz dokładnie **how to generate barcode** obrazy, dostosujesz wymiar X‑dimension i zapiszesz wynik jako plik PNG — wszystko w kilku linijkach kodu.

Otrzymasz także kompletny **barcode generator example**, który możesz skopiować i wkleić do własnego projektu. Nie są wymagane zewnętrzne skrypty ani skomplikowana konfiguracja, a tutorial działa z bieżącą wersją Aspose.Barcode 23.10 release.

## Wymagania wstępne

- Zainstalowany Python 3.8+ na twoim komputerze  
- Aktywna licencja Aspose.Barcode for Python (bezpłatna wersja próbna działa w ocenie)  
- `pip install aspose-barcode` wykonane w twoim środowisku wirtualnym  

Te elementy zapewniają, że kod uruchomi się bez błędów importu.

## Utwórz kod kreskowy z ciągu znaków przy użyciu Aspose.Barcode (Python)

Pierwszym krokiem jest utworzenie instancji `BarcodeGenerator` z wybraną symbologią — w tym przypadku **Planet** kod pocztowy — oraz ciągiem, który chcesz zakodować.

```python
# Step 1: Import the required classes
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Create a barcode generator for the Planet symbology with data "123456"
# This is the core of the "create barcode from string" operation.
generator = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**Dlaczego to ważne:**  
`EncodeTypes.Planet` informuje Aspose, że ma używać symbologii pocztowej Planet, przeznaczonej do sortowania poczty w wielu krajach. Drugi argument (`"123456"`) to surowy ciąg, który zostanie zakodowany w kodzie kreskowym. Zmiana tej wartości pozwala **create barcode from string** dla dowolnego kodu pocztowego lub numeru śledzenia, którego potrzebujesz.

## Jak wygenerować kod kreskowy z niestandardowymi wymiarami

Szerokość modułu kodu pocztowego (X‑dimension) często musi odpowiadać specyfikacjom druku. Aspose pozwala ustawić szerokość w pikselach, automatycznie obliczając wysokość.

```python
# Step 3: Set the X dimension (module width) in pixels; height is calculated automatically
generator.parameters.barcode.x_dimension.pixels = 4
```

**Dlaczego możesz to dostosować:**  
Większy X‑dimension sprawia, że paski są grubsze, co może poprawić niezawodność skanowania na drukarkach o niskiej rozdzielczości. Odwrotnie, mniejsza wartość zmniejsza rozmiar obrazu do użytku w sieci. Ten wiersz demonstruje **how to generate barcode** obrazy spełniające dokładne wymagania rozmiarowe.

## Zapisz obraz kodu kreskowego

Po skonfigurowaniu generatora po prostu wywołujesz `save`. Metoda przyjmuje ścieżkę wyjściową oraz żądany format obrazu.

```python
# Step 4: Save the generated barcode as a PNG image
output_path = "YOUR_DIRECTORY/PostalPlanetAuto.png"
generator.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_path}")
```

**Co otrzymujesz:**  
Plik PNG o nazwie `PostalPlanetAuto.png` zawierający kod Planet, który koduje `"123456"`. Możesz otworzyć plik w dowolnej przeglądarce obrazów, aby zweryfikować wynik.

![Screenshot of a generated postal barcode saved as PNG](barcode_example.png){.align-center alt="Zrzut ekranu wygenerowanego kodu pocztowego zapisanego jako PNG"}

## Pełny przykład generatora kodu kreskowego

Poniżej znajduje się kompletny, gotowy do uruchomienia skrypt, który zawiera wszystkie powyższe kroki. Skopiuj go do pliku o nazwie `generate_postal_barcode.py` i uruchom `python generate_postal_barcode.py`.

```python
# generate_postal_barcode.py
# -------------------------------------------------
# Complete example that shows how to create barcode from string,
# set custom dimensions, and save the result as PNG using Aspose.Barcode for Python.
# -------------------------------------------------

from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_postal_barcode(data: str, output_file: str, x_dim_pixels: int = 4):
    """
    Generates a Planet postal barcode from the supplied string.

    Args:
        data: The raw string to encode (e.g., "123456").
        output_file: Full path where the PNG image will be saved.
        x_dim_pixels: Desired X dimension in pixels (default = 4).

    Returns:
        None. The PNG file is written to disk.
    """
    # Validate data length for Planet symbology (6‑digit numeric is standard)
    if not data.isdigit() or len(data) != 6:
        raise ValueError("Planet barcode requires a 6‑digit numeric string.")

    # Create the generator (this is the core of create barcode from string)
    generator = BarcodeGenerator(EncodeTypes.Planet, data)

    # Adjust module width; height is calculated automatically
    generator.parameters.barcode.x_dimension.pixels = x_dim_pixels

    # Save as PNG
    generator.save(output_file, BarCodeImageFormat.PNG)
    print(f"Barcode saved to {output_file}")

if __name__ == "__main__":
    # Example usage – you can change the values to test other strings
    try:
        create_postal_barcode(
            data="123456",
            output_file="PostalPlanetAuto.png",
            x_dim_pixels=4
        )
    except Exception as e:
        print(f"Error generating barcode: {e}")
```

### Oczekiwany wynik

Uruchomienie skryptu generuje:

```
Barcode saved to PostalPlanetAuto.png
```

…i tworzy plik `PostalPlanetAuto.png`, który wygląda tak:

![Generated Planet barcode](barcode_example.png){.align-center alt="Wygenerowany kod Planet zapisany jako PNG"}

## Typowe warianty i przypadki brzegowe

| Situation | What to change | Why |
|-----------|----------------|-----|
| **Inna symbologia** (np. Code128) | Zamień `EncodeTypes.Planet` na `EncodeTypes.Code128` | Umożliwia **generate barcode** dla etykiet inwentaryzacyjnych, nie tylko kodów pocztowych. |
| **Dłuższe ciągi danych** | Upewnij się, że wybrana symbologia obsługuje tę długość; dla Planet musisz zachować 6 cyfr. | Zapobiega wystąpieniu `ValueError` w czasie wykonywania. |
| **Wyższa rozdzielczość** | Zwiększ `x_dimension.pixels` do 6 lub 8. | Tworzy grubsze paski dla druku w wysokiej rozdzielczości DPI. |
| **Inne formaty obrazu** | Użyj `BarCodeImageFormat.JPEG` lub `BarCodeImageFormat.GIF`. | Przydatne, gdy PNG nie jest odpowiedni dla twojego przepływu pracy. |
| **Uruchamianie w usłudze webowej** | Zamień wywołanie `save` na system plików na strumień `BytesIO` i zwróć bajty. | Umożliwia generowanie kodu kreskowego w locie w Flask lub Django. |

**Pro tip:** Zawsze waliduj ciąg wejściowy przed wywołaniem `BarcodeGenerator`. Nieprawidłowe dane (zła długość, nienumeryczne znaki dla Planet) spowodują wyjątek i przerwą działanie aplikacji.

## Jak wygenerować kod kreskowy w endpointzie Flask (opcjonalny kolejny krok)

Jeśli chcesz udostępnić **barcode generator example** jako API REST, możesz opakować funkcję `create_postal_barcode`:

```python
from flask import Flask, send_file, request, abort
import io

app = Flask(__name__)

@app.route("/barcode", methods=["GET"])
def barcode_endpoint():
    data = request.args.get("data", "123456")
    try:
        # Generate barcode into an in‑memory stream
        stream = io.BytesIO()
        generator = BarcodeGenerator(EncodeTypes.Planet, data)
        generator.parameters.barcode.x_dimension.pixels = 4
        generator.save(stream, BarCodeImageFormat.PNG)
        stream.seek(0)
        return send_file(stream, mimetype="image/png", as_attachment=False)
    except Exception as exc:
        abort(400, str(exc))

if __name__ == "__main__":
    app.run(debug=True)
```

Ten fragment pokazuje, jak **generate barcode** na żądanie bez zapisywania na dysku, co jest przydatne w mikro‑serwisach.

## Podsumowanie

Teraz wiesz, jak **create barcode from string** w Pythonie przy użyciu Aspose.Barcode, jak **generate barcode** z niestandardowymi wymiarami oraz jak **save** wynik jako plik PNG. Pełny **barcode generator example** zawiera walidację wejścia, obsługę błędów i wielokrotnego użytku funkcję, którą możesz zintegrować z większymi aplikacjami.

Następnie, eksploruj inne symbologie (`EncodeTypes.Code128`, `EncodeTypes.QR`) lub osadź generator w frameworku webowym takim jak Flask lub Django. Oba kroki pogłębią twoją znajomość biblioteki **aspose barcode python** i rozszerzą możliwości **generate postal barcode** obrazów w projektach rzeczywistych.

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak wygenerować kod kreskowy w Pythonie – kompletny przewodnik krok po kroku](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Utwórz kod kreskowy PNG w Pythonie – pełny przewodnik Aspose.Barcode](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)
- [Jak wygenerować kod kreskowy z ECI używając Aspose.Barcode Python](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}