---
category: general
date: 2026-10-24
description: Przykład generatora kodów kreskowych, który pokazuje, jak utworzyć kod
  kreskowy Planet i jak ustawić wysokość kodu kreskowego przy użyciu Pythona. Postępuj
  zgodnie z przewodnikiem krok po kroku.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to create planet barcode
- how to set barcode height
language: pl
lastmod: 2026-10-24
og_description: Przykład generatora kodów kreskowych, który demonstruje, jak stworzyć
  kod kreskowy Planet oraz jak ustawić wysokość kodu w Pythonie. Uzyskaj kompletną,
  gotową do uruchomienia wersję.
og_image_alt: Barcode generator example showing Planet and RM4SCC barcodes with different
  heights
og_title: Przykład generatora kodów kreskowych – tworzenie kodów Planet i RM4SCC
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
title: Przykład generatora kodów kreskowych – tworzenie kodów Planet i RM4SCC o niestandardowej
  wysokości
url: /pl/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Przykład generatora kodów kreskowych – tworzenie kodów Planet i RM4SCC o niestandardowej wysokości

Jeśli szukasz **przykładu generatora kodów kreskowych**, ten przewodnik dostarcza kompletne, gotowe do uruchomienia rozwiązanie. Zobaczysz **jak tworzyć obrazy kodu Planet**, dowiesz się **jak ustawić wysokość kodu kreskowego** oraz poznasz małe różnice między automatycznym a ręcznym określaniem rozmiaru.

Tutorial przechodzi przez dwa realistyczne scenariusze: kod Planet używający domyślnej (automatycznej) wysokości oraz kod RM4SCC, w którym wysokość jest wymuszona na 100 px. Po zakończeniu będziesz mógł generować pliki PNG dla dowolnego obsługiwanego typu kodu kreskowego przy użyciu jednej, spójnej API.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz:

* Python 3.8 lub nowszy zainstalowany.
* Pakiet `aspose-barcode` (lub dowolną bibliotekę udostępniającą `BarcodeGenerator`, `EncodeTypes` i `BarCodeImageFormat`). Zainstaluj go za pomocą  

  ```bash
  pip install aspose-barcode
  ```
* Uprawnienia do zapisu w folderze, w którym będą zapisywane pliki PNG.

Nie są wymagane dodatkowe zależności systemowe.

## Przegląd rozwiązania

Rdzeń **przykładu generatora kodów kreskowych** składa się z trzech wielokrotnego użytku kroków:

1. **Instancjonowanie** `BarcodeGenerator` z żądaną wartością `EncodeTypes` oraz ciągiem danych.
2. **Konfigurowanie** wymiaru X (szerokość modułu) i, w razie potrzeby, wysokości kodu kreskowego.
3. **Zapisywanie** obrazu na dysku w formacie PNG.

Oba przykłady dzielą kroki 1 i 3; jedynie krok 2 różni się, ponieważ kod Planet polega na automatycznym obliczaniu wysokości biblioteki, natomiast kod RM4SCC demonstruje **jak ustawić wysokość kodu kreskowego** ręcznie.

Poniżej znajduje się diagram wysokiego poziomu ilustrujący przepływ:

![Przykład generatora kodów kreskowych pokazujący kody Planet i RM4SCC](barcode-example.png)

*Alt text: Przykład generatora kodów kreskowych pokazujący kody Planet i RM4SCC o różnych wysokościach.*

## Jak utworzyć kod Planet – automatyczna wysokość

Kod Planet jest częścią rodziny kodów pocztowych używanych przez wiele krajowych usług pocztowych. W większości przypadków pozwalasz SDK określić wysokość, co utrzymuje prawidłowe proporcje wizualne przy różnych długościach danych.

```python
# Step 1: Create a generator for the Planet barcode with the data "123456"
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

planet_gen = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Define the X‑dimension (module width) as 4 pixels
planet_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Save the barcode image as a PNG file
planet_gen.save("PostalPlanetBarHeightAuto.png", BarCodeImageFormat.Png)
```

**Dlaczego to działa**

* `EncodeTypes.Planet` informuje bibliotekę, że ma użyć symboliki Planet.
* Ustawienie `x_dimension.pixels` na 4 nadaje każdemu modułowi szerokość 4 px, co jest powszechnym domyślnym rozmiarem dla drukowanych etykiet.
* Nie ustawiamy explicite wysokości; SDK oblicza optymalną wysokość na podstawie danych i wymiaru X, dlatego jest to najprostszy **przykład generatora kodów kreskowych** dla kodów pocztowych.

**Oczekiwany rezultat**

Plik PNG 2‑D o nazwie `PostalPlanetBarHeightAuto.png` zawierający wyraźny kod Planet. Wysokość będzie wynosić około 30 px (w zależności od wersji biblioteki), a szerokość będzie równa 4 px × liczba modułów.

## Jak ustawić wysokość kodu kreskowego – przykład RM4SCC z niestandardową wysokością

RM4SCC to kolejny kod pocztowy, który często wymaga stałej wysokości, aby pasował do szablonów etykiet. Ta część tutorialu pokazuje **jak ustawić wysokość kodu kreskowego** na dokładną liczbę pikseli.

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

**Dlaczego to działa**

* `EncodeTypes.RM4SCC` wybiera symbolikę RM4SCC.
* Wymiar X pozostaje na 4 px, aby zachować spójny rozmiar modułu w obu kodach.
* `bar_height.pixels = 100` wymusza dokładną wysokość 100 px, nadpisując automatyczne obliczenia. Jest to zalecany sposób **jak ustawić wysokość kodu kreskowego**, gdy układ wymaga konkretnego rozmiaru.

**Oczekiwany rezultat**

Plik PNG o nazwie `PostalRM4SCCBarHeight100Pixels.png` wyświetlający wysoki kod RM4SCC. Szerokość nadal zależy od wymiaru X, podczas gdy wysokość jest stała – 100 px, co czyni go odpowiednim dla drukarek etykiet o wysokiej rozdzielczości.

## Pełny skrypt – połączenie obu przykładów

Jeśli wolisz pojedynczy skrypt generujący oba obrazy, skopiuj poniższy kod do pliku `generate_barcodes.py` i uruchom go.

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

**Wyjaśnienie skryptu**

* Dwie funkcje pomocnicze utrzymują kod w stylu DRY (Don’t Repeat Yourself) i ułatwiają rozszerzenie skryptu o inne symboliki.
* Warunek `if __name__ == "__main__":` pozwala na importowanie pliku jako modułu bez wykonywania logiki generacji, co jest przydatne przy testach jednostkowych.
* Wszystkie parametry (ciąg danych, wymiar X, wysokość) są jawne, więc skrypt służy jako odniesienie **przykładu generatora kodów kreskowych** dla przyszłych projektów.

## Częste pytania i przypadki brzegowe

| Pytanie | Odpowiedź |
|----------|-----------|
| *Co zrobić, jeśli potrzebuję innego wymiaru X?* | Zmień `x_dimension.pixels` na żądaną szerokość modułu. Większe wartości proporcjonalnie zwiększają całkowity rozmiar kodu. |
| *Czy mogę generować inne formaty obrazu?* | Tak. Zamień `BarCodeImageFormat.Png` na `Jpg`, `Bmp` lub `Gif` w zależności od enumu biblioteki. |
| *Co się stanie, jeśli ciąg danych zawiera nieprawidłowe znaki?* | Generator zgłosi `ArgumentException`. Zweryfikuj dane względem zestawu znaków danej symboliki przed wywołaniem konstruktora. |
| *Czy można ustawić minimalną wysokość przy zachowaniu automatycznego skalowania?* | Użyj `gen.parameters.barcode.bar_height.min_pixels = <wartość>` (jeśli SDK udostępnia właściwość `min_pixels`). Zapobiegnie to zmniejszeniu kodu poniżej czytelnego rozmiaru. |
| *Czy muszę zwalniać generator?* | Klasa `BarcodeGenerator` implementuje `IDisposable` w .NET; w Pythonie garbage collector się tym zajmuje, ale możesz wywołać `gen.dispose()`, jeśli tworzysz wiele instancji w pętli. |

## Wskazówki dla środowiska produkcyjnego

* **Pro tip:** Przechowuj wartości wymiaru X i wysokości w pliku konfiguracyjnym, aby móc je modyfikować bez rekompilacji.
* **Uwaga:** Unikaj wysokości zbyt małej dla wybranej symboliki; skanery mogą mieć problem z odczytem kodu.
* **Nota o wydajności:** Generowanie dużej partii kodów jest szybsze, gdy ponownie używasz jednej instancji `BarcodeGenerator` i zmieniasz jedynie jej właściwość `code_text` pomiędzy zapisami.

## Podsumowanie

Ten **przykład generatora kodów kreskowych** demonstruje zarówno **jak tworzyć obrazy kodu Planet** z automatycznym rozmiarem, jak i **jak ustawić wysokość kodu kreskowego** ręcznie dla kodów RM4SCC. Postępując zgodnie z przewodnikiem krok po kroku, możesz zintegrować tworzenie kodów kreskowych z dowolną aplikacją Python, dostosować wymiary i generować pliki PNG gotowe do druku lub wyświetlania cyfrowego.

### Kolejne kroki

* Poznaj dodatkowe symboliki, takie jak `EncodeTypes.Postnet` lub `EncodeTypes.Code128` – obowiązuje ten sam wzorzec.
* Eksperymentuj z **jak ustawić wysokość kodu kreskowego** dla kodów QR lub DataMatrix; większość bibliotek udostępnia podobną właściwość `bar_height`.
* Połącz generator z biblioteką PDF, aby osadzać kody bezpośrednio w fakturach lub etykietach wysyłkowych.

Śmiało dostosowuj skrypt, dziel się wynikami i daj nam znać, które typy kodów dodasz jako następne!

### Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [How to save PNG from a barcode generator example in Python](/barcode/english/python-java/general/how-to-save-png-from-a-barcode-generator-example-in-python/)
- [How to create planet barcode PNG with Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [How to use a C# barcode generator to create a Planet barcode](/barcode/english/python-java/general/how-to-use-a-c-barcode-generator-to-create-a-planet-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}