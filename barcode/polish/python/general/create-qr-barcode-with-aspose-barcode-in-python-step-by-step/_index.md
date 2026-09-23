---
category: general
date: 2026-08-09
description: Utwórz kod QR w Pythonie przy użyciu Aspose.BarCode. Dowiedz się, jak
  zbudować rozszerzony tekst kodu, dostosować wygląd i zapisać obraz — wszystko w
  jednym samouczku.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create QR barcode
- Aspose.BarCode Python
- extended codetext QR
- QR code generation Python
- barcode visual customization
language: pl
lastmod: 2026-08-09
og_description: Utwórz kod QR w Pythonie z Aspose.BarCode. Ten przewodnik pokazuje,
  jak zbudować rozszerzony tekst kodu, ustawić parametry wizualne i wyeksportować
  obraz.
og_image_alt: Screenshot of a generated QR barcode created with Aspose.BarCode in
  Python
og_title: Utwórz kod QR przy użyciu Aspose.BarCode w Pythonie – pełny przykład kodu
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  headline: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  type: TechArticle
- description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  name: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  steps:
  - name: Common variations
    text: '- **Multiple ECI segments:** Call `add_eci_codetext` multiple times to
      mix several languages. - **Different ECI identifiers:** Use `27` for ISO‑8859‑1,
      `28` for ISO‑8859‑2, etc., depending on your target encoding.'
  - name: Edge case handling
    text: '- **High‑density data:** If the encoded data is large, you may need to
      increase `x_dimension` or choose a higher error‑correction level (via `qr_generator.parameters.qr.error_correction_level`).
      - **Transparent background:** Set `qr_generator.parameters.barcode.bg_color
      = Color.Transparent` for PNGs'
  - name: Verifying the result
    text: 'Open the saved file in any image viewer. You should see a QR code that,
      when scanned, returns the combined string:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Tworzenie kodu QR przy użyciu Aspose.BarCode w Pythonie – przewodnik krok po
  kroku
url: /pl/python/general/create-qr-barcode-with-aspose-barcode-in-python-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz kod QR przy użyciu Aspose.BarCode w Pythonie – przewodnik krok po kroku

Jeśli potrzebujesz **utworzyć kod QR** w Pythonie, ten samouczek przeprowadzi Cię przez cały proces przy użyciu biblioteki Aspose.BarCode. Niezależnie od tego, czy kodujesz identyfikatory produktów, tekst wielojęzyczny, czy własne dane, zobaczysz, jak zbudować rozszerzony codetext, dostosować ustawienia wizualne i zapisać końcowy obraz w jednym, uruchamialnym skrypcie.

Przykład pokazuje również, jak wyświetlić wersję biblioteki, co pomaga zweryfikować, że używasz kompatybilnej wersji. Po zakończeniu tego przewodnika będziesz mieć gotowy do użycia obraz kodu QR oraz jasne zrozumienie każdej opcji konfiguracji.

## Wymagania wstępne

- Zainstalowany Python 3.8+.
- Pakiet `aspose-barcode` (zainstaluj za pomocą `pip install aspose-barcode`).
- Podstawowa znajomość składni Pythona.
- Uprawnienia zapisu do katalogu wyjściowego, w którym zostanie zapisany plik PNG.

> **Wskazówka:** Używaj wirtualnego środowiska, aby uniknąć konfliktów wersji z innymi projektami.

## Krok 1: Zweryfikuj wersję biblioteki Aspose.BarCode

Wyświetlenie wersji biblioteki zapewnia, że używasz wydania obsługującego rozszerzony codetext i kodowanie QR.

```python
from asposebarcode import BuildVersionInfo

# Show the current Aspose.BarCode version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)
```

**Dlaczego to ważne:**  
Starsze wydania mogą nie zawierać klasy `ExtCodetextBuilder` wymaganej do mieszania segmentów zwykłych i ECI. Potwierdzenie wersji zapobiega błędom w czasie wykonywania w dalszej części przepływu.

## Krok 2: Zbuduj rozszerzony ciąg codetext

Rozszerzony codetext pozwala połączyć zwykłe dane ASCII z segmentami Unicode (ECI), co jest niezbędne dla wielojęzycznych kodów QR.

```python
from asposebarcode import ExtCodetextBuilder

# Initialize the builder
ext_builder = ExtCodetextBuilder()

# Add a plain segment – typically a product ID or numeric code
ext_builder.add_plain_codetext("ABC12345")

# Add an ECI segment – here we embed Japanese greeting "こんにちは"
# 26 is the ECI identifier for UTF‑8 encoding
ext_builder.add_eci_codetext(26, "こんにちは")

# Retrieve the full extended codetext that the QR generator will use
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")
```

**Dlaczego to ważne:**  
Metoda `add_plain_codetext` zapisuje dane jako standardowy ASCII, natomiast `add_eci_codetext` poprzedza blok Unicode odpowiednim identyfikatorem ECI. Takie podejście zapewnia, że skanery QR prawidłowo interpretują japoński tekst, unikając zniekształconych znaków.

### Typowe warianty

- **Wiele segmentów ECI:** Wywołaj `add_eci_codetext` wielokrotnie, aby połączyć kilka języków.
- **Różne identyfikatory ECI:** Użyj `27` dla ISO‑8859‑1, `28` dla ISO‑8859‑2 itd., w zależności od docelowego kodowania.

## Krok 3: Wygeneruj kod QR przy użyciu rozszerzonego codetext

Teraz, gdy mamy prawidłowo sformatowany ciąg, możemy utworzyć kod QR.

```python
from asposebarcode import BarCodeGenerator, EncodeTypes, BarCodeImageFormat

# Create the QR generator with the extended codetext
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)
```

**Dlaczego to ważne:**  
`EncodeTypes.QR` informuje Aspose.BarCode, aby użył symbologii QR. Przekazanie `extended_codetext` bezpośrednio łączy mieszane dane z macierzą QR, zachowując zarówno część zwykłą, jak i Unicode.

## Krok 4: Dostosuj wygląd wizualny (opcjonalnie, ale zalecane)

Dostrajanie parametrów wizualnych kodu kreskowego poprawia niezawodność skanowania i dopasowuje się do wytycznych brandingowych.

```python
# Set module (pixel) size – larger values increase overall image size
qr_generator.parameters.barcode.x_dimension = 4      # each module = 4 pixels

# Set border thickness – a thin white border helps scanners isolate the QR code
qr_generator.parameters.barcode.border_width = 2    # 2-pixel border
```

**Dlaczego to ważne:**  
- **`x_dimension`** kontroluje rozmiar każdego modułu QR; zbyt mały może powodować błędy odczytu na urządzeniach o niskiej rozdzielczości.  
- **`border_width`** dodaje strefę ciszy. Niektóre skanery wymagają co najmniej 4‑modułowej strefy ciszy; biblioteka dodaje ją automatycznie, ale możesz zwiększyć ją dla dodatkowego bezpieczeństwa.

### Obsługa przypadków brzegowych

- **Dane o wysokiej gęstości:** Jeśli zakodowane dane są duże, może być konieczne zwiększenie `x_dimension` lub wybranie wyższego poziomu korekcji błędów (poprzez `qr_generator.parameters.qr.error_correction_level`).  
- **Przezroczyste tło:** Ustaw `qr_generator.parameters.barcode.bg_color = Color.Transparent` dla PNG z kanałami alfa.

## Krok 5: Zapisz obraz kodu QR

Na koniec zapisz obraz na dysku w wybranym formacie.

```python
# Define output path – replace YOUR_DIRECTORY with an actual folder
output_file = "YOUR_DIRECTORY/extended_qr.png"

# Save as PNG; other formats include JPEG, BMP, GIF, TIFF
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

**Dlaczego to ważne:**  
Zapis jako PNG zachowuje jakość bezstratną, co jest idealne dla kodów QR wymagających wyraźnych krawędzi. Jeśli potrzebujesz innego formatu dla aplikacji internetowej, po prostu zmień wyliczenie `BarCodeImageFormat`.

### Weryfikacja wyniku

Otwórz zapisany plik w dowolnym przeglądarce obrazów. Powinieneś zobaczyć kod QR, który po zeskanowaniu zwraca połączony ciąg:

```
ABC12345
こんにちは
```

Większość nowoczesnych aplikacji skanujących QR wyświetla najpierw segment zwykły, a następnie prawidłowo renderuje japońskie powitanie.

---

## Pełny skrypt do uruchomienia

Skopiuj cały blok poniżej do pliku o nazwie `create_qr_barcode.py` i uruchom go poleceniem `python create_qr_barcode.py`. Dostosuj `YOUR_DIRECTORY` do zapisywalnego folderu na swoim komputerze.

```python
# create_qr_barcode.py
from asposebarcode import (
    BuildVersionInfo,
    ExtCodetextBuilder,
    BarCodeGenerator,
    EncodeTypes,
    BarCodeImageFormat,
)

# 1️⃣ Display library version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)

# 2️⃣ Build extended codetext (plain + Japanese Unicode)
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC12345")
ext_builder.add_eci_codetext(26, "こんにちは")
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")

# 3️⃣ Create QR generator
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)

# 4️⃣ Optional visual tweaks
qr_generator.parameters.barcode.x_dimension = 4
qr_generator.parameters.barcode.border_width = 2

# 5️⃣ Save image
output_file = "YOUR_DIRECTORY/extended_qr.png"
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

Uruchomienie tego skryptu wypisuje wersję, rozszerzony codetext oraz potwierdzenie, że plik PNG został utworzony.

---

## Zakończenie

Teraz wiesz, jak **utworzyć obrazy kodu QR** w Pythonie przy użyciu Aspose.BarCode. Samouczek obejmował:

1. Weryfikację wersji biblioteki.
2. Budowanie rozszerzonego codetextu z segmentami zwykłymi i ECI (Unicode).
3. Generowanie kodu QR.
4. Dostosowywanie parametrów wizualnych, takich jak rozmiar modułu i szerokość obramowania.
5. Zapis końcowego obrazu w formacie PNG.

Od tego miejsca możesz eksplorować:

- Zmianę poziomów korekcji błędów (`qr_generator.parameters.qr.error_correction_level`).
- Dodawanie logo lub obrazu tła (`qr_generator.parameters.qr.logo`).
- Eksport do innych formatów, takich jak SVG, dla skalowalnej grafiki internetowej.
- Integrację generatora z endpointem Flask lub Django w celu tworzenia kodów QR w locie.

Eksperymentuj z różnymi ładunkami danych i ustawieniami wizualnymi, aby dopasować je do brandingu i wymagań skanowania Twojej aplikacji. Szczęśliwego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak utworzyć rozszerzony codetext dotcode przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Utwórz kod kreskowy Aspose .NET – konfigurowanie tekstu DataMatrix](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Jak utworzyć strefę ciszy kodu kreskowego dla ITF-14 przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}