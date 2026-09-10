---
category: general
date: 2026-09-10
description: Zakoduj znaki nie‑ASCII w kodzie QR i zapisz obraz kodu QR przy użyciu
  prostego kreatora w Pythonie. Postępuj zgodnie z przewodnikiem krok po kroku, korzystając
  z ExtCodetextBuilder i BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- encode non ascii characters
- save qr code image
- extended codetext builder
- eci encoding python
- barcode generation python
language: pl
lastmod: 2026-09-10
og_description: Zakoduj znaki nie‑ASCII w kodzie QR i zapisz obraz kodu QR przy użyciu
  Pythona. Ten tutorial pokazuje, jak zbudować rozszerzony tekst kodu, wygenerować
  kod QR i zapisać obraz.
og_image_alt: Diagram showing encode non ASCII characters in QR code and save QR code
  image workflow
og_title: Kodowanie znaków nie‑ASCII w kodzie QR i zapisywanie obrazu kodu QR – krok
  po kroku przewodnik w Pythonie
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Encode non ASCII characters in a QR code and save QR code image with
    a simple Python builder. Follow a step‑by‑step guide using ExtCodetextBuilder
    and BarcodeGenerator.
  headline: Encode non ASCII characters in QR code and save QR code image
  type: TechArticle
tags:
- barcode
- QR code
- Python
title: Zakoduj znaki nie‑ASCII w kodzie QR i zapisz obraz kodu QR
url: /pl/python/general/encode-non-ascii-characters-in-qr-code-and-save-qr-code-imag/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kodowanie znaków nie‑ASCII w kodzie QR i zapisywanie obrazu kodu QR

Jeśli potrzebujesz **zakodować znaki nie‑ASCII** w kodzie QR, ten przewodnik pokaże Ci dokładnie, jak to zrobić, a następnie **zapisać obraz kodu QR** na dysku. Niezależnie od tego, czy obsługujesz rosyjskie, chińskie czy emoji, ExtCodetextBuilder pozwala mieszać zwykły tekst i segmenty zakodowane ECI bez ręcznego manipulowania bajtami.

Nauczysz się, jak stworzyć rozszerzony ciąg kodowego tekstu, wygenerować kod QR rozumiejący ten ciąg oraz w końcu zapisać obraz kodu kreskowego do pliku. Tutorial zakłada podstawową znajomość Pythona oraz zainstalowany pakiet `barcode` SDK.

## Prerequisites

Zanim rozpoczniesz, upewnij się, że masz:

* Python 3.8+ zainstalowany.
* Pakiet Python `barcode` (lub odpowiedni SDK), który udostępnia `ExtCodetextBuilder`, `CodetextEncodingType` i `BarcodeGenerator`.
* Uprawnienia do zapisu w katalogu, w którym chcesz **zapisać obraz kodu QR**.

Możesz zainstalować SDK przy pomocy pip (zamień `barcode-sdk` na rzeczywistą nazwę pakietu):

```bash
pip install barcode-sdk
```

## Krok 1: Utwórz builder rozszerzonego kodowego tekstu

Pierwszym krokiem jest utworzenie instancji `ExtCodetextBuilder`. Obiekt ten zbiera wiele segmentów tekstowych i tworzy pojedynczy ciąg, który specyfikacja kodu QR potrafi zinterpretować.

```python
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Initialize the builder that will hold all text parts
ext_builder = ExtCodetextBuilder()
```

*Dlaczego to ważne*: Kody QR obsługują **rozszerzony kodowy tekst**, co oznacza, że możesz osadzić kilka trybów kodowania (plain, ECI, itp.) w jednym kodzie kreskowym. Builder ukrywa niskopoziomowe formatowanie wymagane przez specyfikację QR.

## Krok 2: Dodaj segment zwykłego tekstu

Zwykły tekst jest trybem domyślnym i działa dla znaków ASCII. Dodanie go jako pierwszego zapewnia czytelny fallback dla skanerów, które ignorują ECI.

```python
# Add simple ASCII text
ext_builder.add_plain_codetext("HelloWorld")
```

Jeśli pominiesz ten krok, kod QR będzie zawierał tylko segment ECI, który niektóre starsze czytniki mogą nie odczytać poprawnie.

## Krok 3: Dodaj segment zakodowany ECI dla znaków nie‑ASCII

Aby uwzględnić znaki spoza zakresu ASCII — takie jak cyrylica, chiński czy emoji — musisz określić kodowanie ECI (Extended Channel Interpretation). Tutaj używamy UTF‑8 dla rosyjskiego słowa „Привет”.

```python
# Add a UTF‑8 encoded segment containing non‑ASCII characters
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")  # Russian “Hi”
```

*Dlaczego to działa*: Specyfikacja QR definiuje wartości ECI, które informują skaner, jaki zestaw znaków zastosować. Bez znacznika ECI surowe bajty byłyby interpretowane jako ISO‑8859‑1, co skutkowałoby zniekształconym wynikiem.

## Krok 4: Pobierz połączony ciąg rozszerzonego kodowego tekstu

Po dodaniu wszystkich pożądanych segmentów wywołaj `get_extended_codetext()`, aby uzyskać ostateczny ciąg, którego oczekuje generator kodów kreskowych.

```python
# Combine all parts into one extended codetext string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

Wydrukowana wartość wygląda jak seria znaków kontrolnych, po których następuje właściwy tekst, ale nie musisz jej ręcznie parsować.

## Krok 5: Wygeneruj kod QR używając rozszerzonego kodowego tekstu

Teraz utwórz `BarcodeGenerator`, ustaw symbologię na QR (jedyną powszechną symbologię 2‑D obsługującą rozszerzony kodowy tekst) i przekaż połączony ciąg.

```python
# Initialize the QR generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)          # QR supports extended codetext
qr_generator.set_code_text(extended_codetext)
```

*Wskazówka*: Jeśli spróbujesz tego samego procesu z Code‑128 lub DataMatrix, SDK zgłosi wyjątek, ponieważ te formaty nie potrafią interpretować znaczników ECI.

## Krok 6: Zapisz obraz kodu QR

Na koniec zapisz kod kreskowy do pliku PNG. To właśnie tutaj **zapisujesz obraz kodu QR** do późniejszego użycia.

```python
output_path = "output/qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Upewnij się, że folder `output` istnieje lub utwórz go poleceniem `os.makedirs('output', exist_ok=True)` przed wywołaniem `save`.

### Pełny, gotowy do uruchomienia przykład

Połączenie wszystkich kroków daje samodzielny skrypt, który możesz od razu uruchomić:

```python
import os
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Ensure the output directory exists
os.makedirs("output", exist_ok=True)

# 1️⃣ Create the builder
ext_builder = ExtCodetextBuilder()

# 2️⃣ Add plain ASCII text
ext_builder.add_plain_codetext("HelloWorld")

# 3️⃣ Add UTF‑8 encoded non‑ASCII text (Russian)
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")

# 4️⃣ Retrieve the combined string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 5️⃣ Generate QR code
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)
qr_generator.set_code_text(extended_codetext)

# 6️⃣ Save the image
output_file = "output/qr_extended.png"
qr_generator.save(output_file)
print(f"QR code saved to {output_file}")
```

**Oczekiwany wynik** (konsola):

```
Extended codetext: <binary representation showing ECI markers>
QR code saved to output/qr_extended.png
```

Otwarcie `qr_extended.png` dowolnym skanerem QR wyświetli `HelloWorldПривет`. Skanery rozumiejące ECI pokażą znaki cyrylicy poprawnie; inne wyświetlą tylko część ASCII.

## Częste pytania i przypadki brzegowe

| Question | Answer |
|----------|--------|
| *Can I use other encodings like Shift‑JIS?* | Yes. Replace `CodetextEncodingType.UTF_8` with `CodetextEncodingType.SHIFT_JIS` and provide the appropriate text. |
| *What if the combined data exceeds QR capacity?* | QR codes have version limits (up to 177 × 177 modules). If the builder throws a size exception, either increase the error‑correction level or split data across multiple QR codes. |
| *Do I need to set a specific QR version?* | The SDK automatically selects the smallest version that fits the data. You can force a version with `qr_generator.set_qr_version(10)` if required. |
| *Will the image be transparent?* | By default the SDK writes a PNG with a white background. Use `qr_generator.set_background_color(Color.Transparent)` before `save` if you need transparency. |

## Conclusion

W tym tutorialu nauczyłeś się, jak **zakodować znaki nie‑ASCII** w kodzie QR przy użyciu `ExtCodetextBuilder`, a następnie **zapisać obraz kodu QR** za pomocą `BarcodeGenerator`. Proces obejmuje budowanie rozszerzonego ciągu kodowego tekstu, dodawanie segmentów zwykłego tekstu i segmentów zakodowanych ECI, generowanie symbologii QR oraz ostateczne zapisanie pliku obrazu.

Od tego momentu możesz eksplorować:

* Dodawanie kolejnych segmentów ECI (różne języki lub emoji).
* Dostosowywanie poziomów korekcji błędów QR dla większej niezawodności.
* Osadzanie wygenerowanego PNG w plikach PDF lub stronach internetowych.

Miłego kodowania i twórz wielojęzyczne kody QR!

## What Should You Learn Next?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Generate Code128 Barcode with Aspose.Barcode Python – Full Guide](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [display product name using Python barcode library – step‑by‑step guide](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}