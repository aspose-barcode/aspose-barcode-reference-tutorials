---
category: general
date: 2026-07-30
description: Utwórz kod kreskowy Databar Stacked Omnidirectional w Pythonie. Postępuj
  zgodnie z tym przewodnikiem krok po kroku, aby skonfigurować współczynnik proporcji,
  XDimension i wyeksportować PNG przy użyciu generatora kodów kreskowych w Pythonie.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked omnidirectional
- python barcode generator
- databar aspect ratio
- xdimension pixel size
- barcodeimageformat png
language: pl
lastmod: 2026-07-30
og_description: Utwórz kod kreskowy Databar Stacked Omnidirectional w Pythonie. Ten
  samouczek pokazuje, jak ustawić XDimension, dostosować proporcje DataBar i zapisać
  jako PNG przy użyciu BarCodeImageFormat.
og_image_alt: Screenshot of a Databar Stacked Omnidirectional barcode saved as a PNG
  file
og_title: Utwórz kod kreskowy Databar Stacked Omnidirectional – samouczek Pythona
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Create Databar Stacked Omnidirectional barcode in Python. Follow this
    step‑by‑step guide to configure aspect ratio, XDimension, and export PNG using
    a python barcode generator.
  headline: Create Databar Stacked Omnidirectional Barcode in Python
  type: TechArticle
tags:
- barcode
- python
- databar
title: Utwórz kod kreskowy Databar Stacked Omnidirectional w Pythonie
url: /pl/python-java/general/create-databar-stacked-omnidirectional-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz kod kreskowy Databar Stacked Omnidirectional w Pythonie

Czy kiedykolwiek potrzebowałeś **utworzyć kod kreskowy databar stacked omnidirectional** w Pythonie, ale nie wiedziałeś od czego zacząć? Nie jesteś sam — wielu programistów napotyka tę barierę, gdy po raz pierwszy pracuje z klasą `BarcodeGenerator`. Dobrą wiadomością jest to, że cały proces jest dość prosty, gdy zrozumiesz kluczowe właściwości.

W tym przewodniku przeprowadzimy Cię przez kompletny, działający przykład, który używa **python barcode generator** do ustawienia XDimension, dopasowania proporcji DataBar oraz ostatecznego wyeksportowania dwóch plików PNG. Po zakończeniu będziesz mieć solidne pojęcie o tym, jak generować wysokiej jakości symbole stacked omnidirectional dla dowolnego projektu związanego z inwentaryzacją lub logistyką.

## Czego się nauczysz

- Jak utworzyć generator **databar stacked omnidirectional** z ładunkiem GTIN‑14.  
- Dlaczego **rozmiar piksela XDimension** ma znaczenie dla niezawodności skanowania.  
- Wpływ **proporcji DataBar** na szerokość wiersza w stosunku do wysokości.  
- Jak zapisać wynik jako plik **BarCodeImageFormat PNG**.  
- Wskazówki dotyczące ponownego użycia tego samego obiektu generatora do tworzenia wielu wariantów bez dodatkowego zużycia pamięci.

### Wymagania wstępne

- Python 3.8+ (biblioteka, której używamy, jest czystym Pythonem, nie wymaga skompilowanych pakietów).  
- Pakiet `barcode-generator` (instaluj za pomocą `pip install barcode-generator`).  
- Folder, do którego możesz zapisywać – skrypt zapisze tam dwa obrazy PNG.

Jeśli czujesz się komfortowo z podstawowymi importami w Pythonie i kodem obiektowym, jesteś gotowy do działania.

## Utwórz kod kreskowy Databar Stacked Omnidirectional – Przegląd kroków

Poniżej dzielimy przepływ pracy na sześć małych kroków. Każdy krok jest samodzielnym fragmentem kodu, który możesz skopiować i wkleić do REPL‑a lub pliku skryptu. Śmiało eksperymentuj — zmiana proporcji lub XDimension natychmiast da Ci inny styl wizualny.

---

## Krok 1: Utwórz generator Databar Stacked Omnidirectional

Pierwszą rzeczą, którą robimy, jest **utworzenie generatora databar stacked omnidirectional**, przekazując odpowiedni enum `EncodeTypes` oraz ciąg danych.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1 – initialize the generator with a GTIN‑14 payload
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)
```

> **Why this matters:** Flaga `EncodeTypes.DatabarStackedOmniDirectional` informuje bibliotekę, że ma wygenerować symbol stacked omnidirectional, który jest jedyną odmianą DataBar zdolną zakodować do 14 cyfr, a jednocześnie pozostaje czytelny pod każdym kątem.

---

## Skonfiguruj rozmiar piksela XDimension

**Rozmiar piksela XDimension** kontroluje najmniejszy moduł (najcieńszą czarną kreskę). Wartość `2` piksele sprawdza się w większości scenariuszy wyświetlania na ekranie.

```python
# Step 2 – set the smallest module to 2 pixels
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2
```

> **Pro tip:** Jeśli planujesz drukować kod kreskowy przy wysokim DPI, zwiększ tę wartość do 3 lub 4, aby uniknąć rozmytych krawędzi.

---

## Dostosuj proporcję DataBar (15)

**Proporcja DataBar** określa, jak szeroki jest każdy wiersz w stosunku do jego wysokości. Proporcja `15` daje szersze wiersze, które wiele skanerów preferuje przy szybkim przechwytywaniu ruchu.

```python
# Step 3 – make rows wider (aspect ratio = 15)
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
```

> **Why 15?** Oficjalna specyfikacja GS1 zaleca stosunek od 10 do 20 dla symboli stacked omnidirectional. Wybraliśmy `15` jako zrównoważoną domyślną wartość.

---

## Eksportuj kod kreskowy jako PNG przy użyciu BarCodeImageFormat

Teraz, gdy generator jest skonfigurowany, zapisujemy obraz. Enum `BarCodeImageFormat.Png` zapewnia bezstratny wynik, idealny do dalszego przetwarzania.

```python
# Step 4 – save the first PNG with the 15 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR15.png",
    BarCodeImageFormat.Png
)
```

> **What you’ll see:** Otwórz wygenerowany plik PNG; powinieneś zauważyć czysty, wysokokontrastowy kod kreskowy z stosunkowo szerokimi wierszami.

---

## Zmień proporcję DataBar na 30

Czasami potrzebne są wyższe wiersze zamiast szerszych — być może, aby dopasować się do wąskiej etykiety. Przełączenie **proporcji DataBar** na `30` sprawia, że każdy wiersz jest wyższy.

```python
# Step 5 – increase the aspect ratio to make rows taller
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
```

> **Edge case:** Bardzo wysokie proporcje (np. >40) mogą spowodować, że kod kreskowy przekroczy typowe wysokości etykiet, więc przetestuj go na rzeczywistym drukarce przed ostatecznym zastosowaniem.

---

## Ponownie eksportuj kod kreskowy z nową proporcją

Na koniec ponownie używamy tego samego obiektu `barcode_generator`, aby zapisać drugi plik PNG. Nie ma potrzeby tworzenia nowego generatora — wystarczy zmienić właściwość i ponownie wywołać `Save`.

```python
# Step 6 – save the second PNG with the 30 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR30.png",
    BarCodeImageFormat.Png
)
```

> **Result:** Masz teraz dwa pliki PNG — jeden z szerokimi wierszami (`AR15`) i drugi z wysokimi wierszami (`AR30`). Porównaj je obok siebie, aby zdecydować, który lepiej pasuje do Twojej konfiguracji skanera.

---

## Pełny działający przykład

Łącząc wszystko razem, oto kompletny skrypt, który możesz uruchomić od razu. Zastąp `YOUR_DIRECTORY` absolutną ścieżką na swoim komputerze.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1️⃣ Initialize generator
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)

# 2️⃣ Set smallest module (XDimension)
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2

# 3️⃣ First aspect ratio – wider rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR15.png", BarCodeImageFormat.Png)

# 4️⃣ Second aspect ratio – taller rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR30.png", BarCodeImageFormat.Png)

print("✅ Two PNG files created – AR15 and AR30")
```

**Oczekiwany wynik** (w konsoli):

```
✅ Two PNG files created – AR15 and AR30
```

I dwa pliki graficzne pojawią się w docelowym folderze, gotowe do testów skanowania.

---

## Podsumowanie

Właśnie **utworzyliśmy kody kreskowe databar stacked omnidirectional** w Pythonie, dostosowaliśmy **rozmiar piksela XDimension**, poeksperymentowaliśmy z dwoma różnymi ustawieniami **proporcji DataBar** i wyeksportowaliśmy wyniki jako pliki **BarCodeImageFormat PNG**. Cały przepływ mieści się w kilku linijkach, a jednocześnie daje pełną kontrolę nad cechami wizualnymi, które mają największe znaczenie dla skanerów.

Co dalej? Spróbuj zamienić ładunek na inny GTIN, baw się kolorami, konwertując PNG na obraz z paletą, lub wygeneruj raport PDF, który umieści oba PNG obok siebie. Klasa `BarcodeGenerator` jest na tyle elastyczna, że poradzi sobie ze wszystkimi tymi scenariuszami, więc śmiało eksperymentuj.

Masz pytania dotyczące konkretnego przypadku użycia lub napotkałeś błąd? zostaw komentarz poniżej, a chętnie pomogę. Szczęśliwego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu wraz z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Generuj obraz kodu kreskowego – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}