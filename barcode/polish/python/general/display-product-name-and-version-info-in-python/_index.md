---
category: general
date: 2026-09-29
description: Wyświetl nazwę produktu w Pythonie, drukując datę wydania i pobierając
  szczegóły wersji z biblioteki barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- display product name
- print release date
- how to get version
- how to print product
- show minor version
language: pl
lastmod: 2026-09-29
og_description: Wyświetl nazwę produktu w Pythonie i dowiedz się, jak wydrukować datę
  wydania, uzyskać wersję oraz pokazać wersję podrzędną w kilku linijkach kodu.
og_image_alt: Screenshot of terminal output showing product name, version, and release
  date
og_title: Wyświetl nazwę produktu i informacje o wersji w Pythonie
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Display product name in Python while printing release date and retrieving
    version details from the barcode library.
  headline: Display product name and version info in Python
  type: TechArticle
tags:
- Python
- barcode library
- version information
title: Wyświetl nazwę produktu i informacje o wersji w Pythonie
url: /pl/python/general/display-product-name-and-version-info-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wyświetlanie nazwy produktu i informacji o wersji w Pythonie

Jeśli potrzebujesz **wyświetlić nazwę produktu** z biblioteki, ten przewodnik pokaże Ci dokładnie, jak to zrobić. Dowiesz się także, jak **wydrukować datę wydania**, **jak uzyskać wersję** oraz **wyświetlić wersję minor** przy użyciu zwięzłego kodu w Pythonie.

Wielu programistów integruje funkcje skanowania lub generowania kodów kreskowych i musi udostępniać metadane biblioteki użytkownikom lub w logach. Ten tutorial obejmuje wszystko, co potrzebne, aby niezawodnie pobrać i przedstawić te informacje.

## Czego się nauczysz

* Pobierz informacje o wersji z biblioteki `barcode`.  
* **Wyświetl nazwę produktu** wraz z numerami wersji głównej i minor.  
* **Wydrukuj datę wydania** w formacie przyjaznym dla człowieka.  
* Obsłuż brakujące atrybuty w sposób elegancki.  

**Wymagania wstępne**  
* Python 3.8 lub nowszy.  
* Dostęp do pakietu `barcode` (zainstaluj za pomocą `pip install python-barcode` lub biblioteki, która udostępnia `BuildVersionInfo`).  

---

## Jak wyświetlić nazwę produktu i informacje o wersji w Pythonie

Pierwszym krokiem jest zaimportowanie biblioteki i wywołanie metody, która zwraca obiekt z informacjami o wersji. Obiekt zawiera atrybuty takie jak `PRODUCT`, `PRODUCT_MAJOR`, `PRODUCT_MINOR` oraz `RELEASE_DATE`.

```python
import barcode

def main():
    # Step 1: Retrieve version information from the barcode library
    info = barcode.BuildVersionInfo()

    # Step 2: Display product name
    print(f"Product: {info.PRODUCT}")

    # Step 3: Show major and minor version numbers
    print(f"Version: {info.PRODUCT_MAJOR}.{info.PRODUCT_MINOR}")

    # Step 4: Print release date
    print(f"Release date: {info.RELEASE_DATE}")

if __name__ == "__main__":
    main()
```

**Dlaczego to działa**  
`BuildVersionInfo()` zwraca lekki obiekt, którego atrybuty są wypełniane w czasie importu. Bezpośredni dostęp do atrybutów unika dodatkowego I/O i zapewnia, że wyświetlane dane odpowiadają wersji biblioteki, której faktycznie używa Twój kod.

### Oczekiwany wynik

```
Product: BarcodeLib
Version: 2.5
Release date: 2024-03-15
```

Dokładne wartości zależą od zainstalowanej wersji biblioteki barcode.

---

## Jak uzyskać wersję z biblioteki barcode

Jeśli potrzebujesz tylko numerów wersji, możesz pominąć drukowanie nazwy produktu i skupić się na polach liczbowych.

```python
import barcode

info = barcode.BuildVersionInfo()
major = info.PRODUCT_MAJOR
minor = info.PRODUCT_MINOR

print(f"Current version: {major}.{minor}")
```

*`PRODUCT_MAJOR` i `PRODUCT_MINOR` stosują semantyczne wersjonowanie, co pozwala porównywać wersje programowo.*

---

## Jak wydrukować datę wydania

Data wydania jest przechowywana jako ciąg znaków w formacie `YYYY‑MM‑DD`. Aby przedstawić ją w innym locale, najpierw przekształć ją w obiekt `datetime`.

```python
import barcode
from datetime import datetime

info = barcode.BuildVersionInfo()
raw_date = info.RELEASE_DATE          # e.g., "2024-03-15"
date_obj = datetime.strptime(raw_date, "%Y-%m-%d")
formatted = date_obj.strftime("%B %d, %Y")  # "March 15, 2024"

print(f"Release date: {formatted}")
```

**Wskazówka:** Zawsze waliduj ciąg daty przed parsowaniem, aby uniknąć `ValueError`, gdy biblioteka zmieni swój format.

---

## Wyświetl wersję minor obok wersji major

Czasami trzeba wyświetlić wersję minor osobno, na przykład przy logowaniu ostrzeżeń o kompatybilności.

```python
import barcode

info = barcode.BuildVersionInfo()
print(f"Major version: {info.PRODUCT_MAJOR}")
print(f"Minor version: {info.PRODUCT_MINOR}")
```

**Pro tip:** Użyj wersji minor do uruchamiania flag funkcji:

```python
if info.PRODUCT_MINOR >= 5:
    enable_new_feature()
```

---

## Obsługa brakujących atrybutów (przypadki brzegowe)

Starsze wydania biblioteki barcode mogą nie udostępniać wszystkich atrybutów. Owiń dostęp do atrybutów w `getattr` z rozsądnymi wartościami domyślnymi.

```python
import barcode

info = barcode.BuildVersionInfo()

product = getattr(info, "PRODUCT", "Unknown Product")
major = getattr(info, "PRODUCT_MAJOR", 0)
minor = getattr(info, "PRODUCT_MINOR", 0)
release = getattr(info, "RELEASE_DATE", "N/A")

print(f"Product: {product}")
print(f"Version: {major}.{minor}")
print(f"Release date: {release}")
```

Ten wzorzec zapewnia, że Twój skrypt nigdy nie wykrzyknie błędu z powodu brakującego pola, co czyni go odpornym w pipeline'ach CI, które mogą działać na różnych wersjach biblioteki.

---

## Pełny, uruchamialny przykład

Poniżej znajduje się kompletny skrypt, który łączy wszystkie najlepsze praktyki: walidację atrybutów, formatowanie daty i czytelny output.

```python
import barcode
from datetime import datetime

def fetch_info():
    """Retrieve version info safely, providing defaults for missing attributes."""
    raw = barcode.BuildVersionInfo()
    return {
        "product": getattr(raw, "PRODUCT", "Unknown Product"),
        "major": getattr(raw, "PRODUCT_MAJOR", 0),
        "minor": getattr(raw, "PRODUCT_MINOR", 0),
        "release_raw": getattr(raw, "RELEASE_DATE", "N/A")
    }

def format_release(date_str):
    """Convert YYYY‑MM‑DD to a friendly format; fall back to the original string."""
    try:
        dt = datetime.strptime(date_str, "%Y-%m-%d")
        return dt.strftime("%B %d, %Y")
    except (ValueError, TypeError):
        return date_str

def main():
    info = fetch_info()

    # Display product name
    print(f"Product: {info['product']}")

    # Show major and minor version numbers
    print(f"Version: {info['major']}.{info['minor']}")

    # Print release date in a readable form
    print(f"Release date: {format_release(info['release_raw'])}")

if __name__ == "__main__":
    main()
```

Uruchomienie tego skryptu na systemie z zainstalowaną biblioteką barcode daje wynik podobny do wcześniejszego przykładu, ale teraz chroni przed brakującymi polami i ładnie formatuje datę.

---

## Podsumowanie

Teraz wiesz, jak **wyświetlić nazwę produktu**, **wydrukować datę wydania**, **uzyskać wersję**, **wydrukować produkt** oraz **wyświetlić wersję minor** przy użyciu prostego przepływu pracy w Pythonie. Pełny przykład demonstruje niezawodny dostęp do atrybutów, obsługę dat i porównywanie wersji — umiejętności, które możesz ponownie wykorzystać w każdej zewnętrznej bibliotece udostępniającej obiekty metadanych.

**Kolejne kroki**

* Zbadaj inne metody metadanych biblioteki barcode, takie jak `BuildCommitInfo()`.  
* Zintegruj output z frameworkiem logowania (np. `logging.info`).  
* Porównuj wersje programowo, aby wymusić minimalne wymagane wersje w swojej aplikacji.

Śmiało eksperymentuj z różnymi formatami wyjścia lub rozbuduj skrypt, aby zapisywał informacje do pliku w celach audytu. Szczęśliwego kodowania!  

![Wyjście terminala pokazujące nazwę produktu i szczegóły wersji](image.png "Wyjście terminala")

## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [wyświetlanie nazwy produktu przy użyciu biblioteki Python barcode – przewodnik krok po kroku](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)
- [Jak wydrukować wersję Aspose.Barcode (Python)](/barcode/english/python/general/how-to-print-version-of-aspose-barcode-python/)
- [Jak generować kod kreskowy przy użyciu Aspose.BarCode w Pythonie](/barcode/english/python-java/general/how-to-generate-barcode-with-aspose-barcode-in-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}