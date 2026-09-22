---
category: general
date: 2026-07-18
description: Użyj extcodetextbuilder Aspose do tworzenia kodów QR, które łączą zwykły
  ASCII i rosyjski tekst w formacie UTF‑8. Poznaj generowanie kodów QR Aspose.Barcode
  w Pythonie.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- use extcodetextbuilder aspose
- Aspose.Barcode
- ECI encoding
- QR Code generation
- mixed codetext
language: pl
lastmod: 2026-07-18
og_description: Użyj ExtCodeTextBuilder w Aspose, aby połączyć zwykłe i zakodowane
  w UTF‑8 fragmenty w kodzie QR. Postępuj zgodnie z tym przewodnikiem krok po kroku
  dla Aspose.Barcode w Pythonie.
og_image_alt: use extcodetextbuilder aspose QR code example showing mixed ECI text
og_title: Użyj ExtCodeTextBuilder Aspose – twórz kody QR z mieszanym tekstem ECI
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  headline: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  type: TechArticle
- description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  name: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  steps:
  - name: What if my scanner doesn’t recognize the Cyrillic part?
    text: Make sure the scanning app advertises ECI support. Older hardware may ignore
      the ECI segment and treat the bytes as ISO‑8859‑1, resulting in garbled characters.
  - name: Can I add more than two fragments?
    text: Absolutely. Call `add_plain_codetext` or `add_eci_codetext` as many times
      as you need. The builder will concatenate them in the order you invoke the methods.
  - name: How do I change the QR Code size or foreground color?
    text: 'Use the `qr_generator.parameters` object:'
  - name: Is there a way to embed binary data (e.g., a small file) alongside text?
    text: Yes. Use `add_binary_codetext` with a byte array, and pair it with an appropriate
      ECI if the binary represents a specific character set. The builder will handle
      the necessary mode switches.
  type: HowTo
tags:
- barcode
- Aspose
- Python
- QR Code
- ECI
title: 'Użyj extcodetextbuilder Aspose: generowanie kodów QR z mieszanym tekstem ECI'
url: /pl/python/general/use-extcodetextbuilder-aspose-generate-qr-codes-with-mixed-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# użyj extcodetextbuilder aspose – Budowanie kodów QR z mieszanym tekstem ECI

Zastanawiałeś się kiedyś, jak **use extcodetextbuilder aspose** wstawić zarówno zwykły angielski, jak i cyrylicę do jednego kodu QR? Nie jesteś sam. Wielu programistów napotyka problem, gdy muszą mieszać dane ASCII i nie‑ASCII, szczególnie gdy skaner docelowy oczekuje prawidłowych znaczników ECI (Extended Channel Interpretation).

W tym samouczku przeprowadzimy Cię krok po kroku przez proces tworzenia kodu QR, który zawiera „HELLO123” **i** rosyjskie słowo „Привет”, przy użyciu API Python Aspose.Barcode. Po zakończeniu będziesz mieć gotowy do uruchomienia skrypt, zrozumiesz, dlaczego każde wywołanie ma znaczenie, i będziesz wiedział, jak dostosować proces do innych języków lub formatów danych.

## Czego się nauczysz

- Jak **initialize ExtCodetextBuilder** i dodać zwykłe oraz fragmenty zakodowane ECI.  
- Dlaczego wartość **ECI encoding** `3` odpowiada UTF‑8 i jak wpływa to na skanowanie.  
- Dokładna kolejność ustawień **QR Code generator** z Aspose.Barcode.  
- Jak zapisać powstały obraz i zweryfikować mieszane treści.  

**Prerequisites** – potrzebujesz Pythona 3.8+, pakietu `aspose-barcode` zainstalowanego (`pip install aspose-barcode`) oraz folderu, w którym możesz zapisywać obrazy. Nic więcej.

---

## użyj extcodetextbuilder aspose do budowania mieszanej treści kodu

Pierwszą rzeczą, której potrzebujemy, jest instancja `ExtCodetextBuilder`. Pomyśl o niej jako o wzorcu builder, który konkatenatuje różne fragmenty tekstu, automatycznie wstawiając odpowiednie znaczniki ECI w tle.

```python
# Step 1: Build an extended codetext that mixes plain and ECI‑encoded fragments
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

# Create the builder object
ext_builder = ExtCodetextBuilder()

# Add plain ASCII text – this part needs no special handling
ext_builder.add_plain_codetext("HELLO123")                     # Plain ASCII text

# Add UTF‑8 encoded Russian text – ECI value 3 signals UTF‑8 to the scanner
ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")  # UTF‑8 encoded Russian text

# Retrieve the combined string that Aspose.Barcode will consume
extended_codetext = ext_builder.get_extended_codetext()
```

**Dlaczego to jest ważne:**  
- `add_plain_codetext` zachowuje dane w niezmienionej formie, co jest idealne dla liczb lub liter angielskich.  
- `add_eci_codetext` wstawia segment ECI (`[ECI:3]`) przed podanym ciągiem, informując każdy zgodny czytnik, że kolejne bajty są w UTF‑8. Bez tego skaner zinterpretowałby bajty cyrylicy jako śmieci.

> **Pro tip:** Jeśli potrzebujesz innego zestawu znaków, zmień wartość `eci_encoding` zgodnie z tabelą ECI (np. `26` dla ISO‑8859‑1).  

---

## Inicjalizacja generowania kodu QR przy użyciu Aspose.Barcode

Teraz, gdy mamy prawidłowo sformatowany `extended_codetext`, możemy przekazać go generatorowi kodu QR. Aspose.Barcode ukrywa niskopoziomowe tworzenie macierzy QR, pozwalając Ci skupić się na danych.

```python
# Step 2: Initialise a QR Code generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)   # Choose QR as the symbology
```

**Co się tutaj dzieje?**  
- `BarcodeGenerator()` tworzy nowy obiekt generatora z ustawieniami domyślnymi (rozmiar, rozdzielczość itp.).  
- `set_symbology` informuje silnik, że chcemy kod QR, a nie np. Code128.  

Jeśli potrzebujesz wyższego poziomu korekcji błędów, możesz wywołać `qr_generator.parameters.barcode.qr_error_level = ...` przed przypisaniem kodu tekstowego.

---

## Przypisanie rozszerzonego kodu tekstowego do generatora QR

Gdy generator jest gotowy, następnym krokiem jest po prostu podanie mieszanej łańcucha, który zbudowaliśmy wcześniej.

```python
# Step 3: Assign the extended codetext to the generator
qr_generator.set_extended_codetext(extended_codetext)
```

**Dlaczego nie używać `set_codetext`?**  
`set_codetext` traktuje wejście jako zwykły tekst, usuwając wszystkie znaczniki ECI. `set_extended_codetext` zachowuje surowe bajty, włącznie z segmentem ECI, zapewniając, że skaner zobaczy prawidłową zmianę języka.

---

## Zapisz obraz kodu QR i zweryfikuj wynik

Na koniec zapisujemy kod QR na dysku. Aspose.Barcode obsługuje PNG, JPEG, BMP i więcej; PNG jest bezpiecznym domyślnym wyborem, ponieważ zachowuje dane bezstratnie.

```python
# Step 4: Save the generated QR Code image
qr_generator.save("YOUR_DIRECTORY/qr_extended.png")
```

Powinieneś teraz mieć plik PNG w określonej lokalizacji. Otwórz go w dowolnej aplikacji skanującej QR, która obsługuje ECI (większość nowoczesnych smartfonów tak robi). Zeskanuj raz – zobaczysz „HELLO123”. Zeskanuj ponownie (lub użyj skanera wyświetlającego surowe dane) – otrzymasz także „Привет”. Dwa fragmenty pojawiają się jako jedyne ładunek, dokładnie tak, jak go zbudowaliśmy.

![przykład kodu QR używającego extcodetextbuilder aspose z mieszanym tekstem ECI](YOUR_DIRECTORY/qr_extended.png)

*Tekst alternatywny obrazu: przykład kodu QR używającego extcodetextbuilder aspose pokazujący mieszany tekst ECI*

---

## Pełny, gotowy do uruchomienia skrypt

Łącząc wszystko razem, oto kompletny program, który możesz skopiować‑wkleić do pliku o nazwie `qr_mixed_eci.py`:

```python
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

def generate_mixed_eci_qr(output_path: str):
    # Build mixed codetext
    ext_builder = ExtCodetextBuilder()
    ext_builder.add_plain_codetext("HELLO123")
    ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_codetext = ext_builder.get_extended_codetext()

    # Initialise QR generator
    qr_generator = BarcodeGenerator()
    qr_generator.set_symbology(Symbology.QR)

    # Assign extended codetext
    qr_generator.set_extended_codetext(extended_codetext)

    # Save image
    qr_generator.save(output_path)
    print(f"QR Code saved to {output_path}")

if __name__ == "__main__":
    generate_mixed_eci_qr("qr_extended.png")
```

Uruchom go za pomocą:

```bash
python qr_mixed_eci.py
```

Zobaczysz komunikat w konsoli potwierdzający lokalizację zapisu, a plik PNG pojawi się dokładnie tam, gdzie wskazałeś.

---

## Częste pytania i przypadki brzegowe

### Co jeśli mój skaner nie rozpoznaje części cyrylicznej?
Upewnij się, że aplikacja skanująca reklamuje obsługę ECI. Starszy sprzęt może zignorować segment ECI i traktować bajty jako ISO‑8859‑1, co skutkuje zniekształconymi znakami.

### Czy mogę dodać więcej niż dwa fragmenty?
Oczywiście. Wywołaj `add_plain_codetext` lub `add_eci_codetext` tak wiele razy, jak potrzebujesz. Builder połączy je w kolejności, w jakiej wywołujesz metody.

### Jak zmienić rozmiar kodu QR lub kolor pierwszego planu?
Użyj obiektu `qr_generator.parameters`:

```python
qr_generator.parameters.barcode.x_dimension = 4   # module size in points
qr_generator.parameters.barcode.qr_error_level = qr_generator.parameters.barcode.QrErrorLevel.QR_ECLEVEL_Q
qr_generator.save("qr_custom.png", BarCodeImageFormat.PNG, 300)  # 300 DPI
```

### Czy istnieje sposób na osadzenie danych binarnych (np. małego pliku) wraz z tekstem?
Tak. Użyj `add_binary_codetext` z tablicą bajtów i połącz to z odpowiednim ECI, jeśli binaria reprezentują konkretny zestaw znaków. Builder obsłuży niezbędne przełączniki trybu.

---

## Zakończenie

Teraz wiesz **how to use extcodetextbuilder aspose**, aby tworzyć kody QR płynnie łączące zwykły ASCII i tekst rosyjski zakodowany w UTF‑8. Korzystając z `ExtCodetextBuilder`, ustawiając właściwe **ECI encoding** i przekazując wynik do **Aspose.Barcode QR Code generator**, otrzymujesz pojedynczy, zgodny ze standardem obraz, który działa na nowoczesnych skanerach.  

Od tego momentu spróbuj zamienić `eci_encoding=3` na inne identyfikatory językowe lub eksperymentuj z dodatkowymi fragmentami tekstu, aby budować wielojęzyczne ładunki. Możesz także zbadać opcje `BarCodeImageFormat`, aby wyeksportować SVG lub PDF, jeśli potrzebujesz grafiki wektorowej.  

Miłego kodowania i nie wahaj się zostawić komentarza, jeśli napotkasz problemy — Twoja opinia pomaga ulepszać te przewodniki!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują tematy ściśle powiązane, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia w własnych projektach.

- [Generate Barcode Java - Set Code Text using Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)
- [Create barcode aspose .net - Configuring DataMatrix Code Text](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Aztec Code Text Encoding with Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}