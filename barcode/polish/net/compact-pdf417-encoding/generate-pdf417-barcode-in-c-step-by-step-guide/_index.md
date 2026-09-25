---
category: general
date: 2026-08-09
description: Szybko generuj kod kreskowy PDF417 w C#. Dowiedz się, jak generować PDF417
  w trybie kompaktowym, z kontrolą kolumn i wyjściem PNG przy użyciu API BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create pdf417 barcode c#
- barcode generator c#
- compact pdf417 settings
- pdf417 png output
language: pl
lastmod: 2026-08-09
og_description: Generuj kod kreskowy PDF417 w C# przy użyciu zwięzłego przykładu.
  Ten przewodnik pokazuje, jak skonfigurować tryb kompaktowy, ustawić liczbę kolumn
  i zapisać wynik jako obraz PNG.
og_image_alt: Generated PDF417 barcode image saved as PNG
og_title: Generowanie kodu kreskowego PDF417 w C# – kompletny poradnik
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    with compact mode, column control, and PNG output using the BarcodeGenerator API.
  headline: Generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- C#
- Aspose.BarCode
title: Generowanie kodu kreskowego PDF417 w C# – przewodnik krok po kroku
url: /pl/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Wygeneruj kod kreskowy PDF417 w C# – przewodnik krok po kroku

Jeśli potrzebujesz **wygenerować kod kreskowy PDF417** w aplikacji .NET, ten tutorial pokaże Ci dokładnie, jak to zrobić. Zobaczysz kompletny, działający program, który tworzy kompaktowy kod kreskowy PDF417, dostosowuje jego rozmiar i zapisuje obraz jako plik PNG.

Generowanie kodu kreskowego PDF417 jest powszechnym wymogiem w przypadku biletów mobilnych, śledzenia zapasów i zabezpieczania dokumentów. Ten przewodnik obejmuje niezbędne opcje konfiguracji, wyjaśnia, dlaczego każde ustawienie ma znaczenie, i dostarcza praktycznych wskazówek do zastosowań w rzeczywistym świecie.

## Wymagania wstępne

* .NET 6.0 SDK lub nowszy zainstalowany  
* IDE C# takie jak Visual Studio 2022 lub Visual Studio Code  
* Pakiet NuGet **Aspose.BarCode for .NET** (wersja 23.10 lub nowsza)  

Możesz zainstalować pakiet przy użyciu następującego polecenia CLI:

```bash
dotnet add package Aspose.BarCode
```

Poniższy kod zakłada, że pakiet jest odwołany i że masz uprawnienia do zapisu w katalogu wyjściowym.

## Krok 1: Utwórz projekt i zaimportuj przestrzenie nazw

Utwórz nowy projekt konsolowy i dodaj wymagane dyrektywy `using`. Te przestrzenie nazw udostępniają klasę `BarcodeGenerator` oraz wyliczenie formatu obrazu.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;
```

**Dlaczego to ważne:** Importowanie właściwych przestrzeni nazw zapewnia, że kompilator może znaleźć typ `BarcodeGenerator` oraz wyliczenie `BarCodeImageFormat`. Brak przestrzeni nazw powoduje błąd kompilacji, który zatrzymuje proces generowania kodu kreskowego.

## Krok 2: Zainicjalizuj `BarcodeGenerator` z kodowaniem PDF417

Konstruktor `BarcodeGenerator` przyjmuje dwa argumenty: symbolikę kodu kreskowego (`EncodeTypes.Pdf417`) oraz tekst, który chcesz zakodować. PDF417 obsługuje szeroki zakres znaków, w tym symbole Unicode.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**Wyjaśnienie:**  
* `EncodeTypes.Pdf417` informuje bibliotekę, aby użyła standardu PDF417.  
* Przykładowy tekst zawiera znaki diakrytyczne oraz symbol praw autorskich, aby zademonstrować obsługę Unicode.

Jeśli potrzebujesz zakodować wyłącznie dane numeryczne, możesz przekazać zwykły ciąg znaków, np. `"1234567890"`.

## Krok 3: Dostosuj wymiar X dla wyższej rozdzielczości

Wymiar X kontroluje szerokość pojedynczego modułu kodu kreskowego (najmniejszego czarnego lub białego elementu). Ustawienie mniejszej wartości w pikselach daje obraz o wyższej rozdzielczości.

```csharp
// Step 3: Adjust the module (X) dimension for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Dlaczego to dostosować?** Domyślny wymiar X wynoszący 3–4 piksele może powodować, że kod kreskowy wygląda surowo na ekranach o wysokiej rozdzielczości DPI. Zmniejszenie go do **2 pikseli** równoważy czytelność z rozmiarem pliku, szczególnie gdy później włączysz tryb kompaktowy.

## Krok 4: Skonfiguruj liczbę kolumn

PDF417 pozwala określić, ile kolumn ma zawierać kod kreskowy. Mniej kolumn sprawia, że kod jest węższy, ale wyższy, natomiast więcej kolumn tworzy szerszy, niższy kod.

```csharp
// Step 4: Set the number of columns to control the barcode width
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

**Praktyczna wskazówka:** Dla biletów mobilnych, które muszą zmieścić się w wąskiej etykiecie, liczba kolumn **3–5** sprawdza się dobrze. Zwiększ liczbę, jeśli masz dużo danych i chcesz krótszy kod kreskowy.

## Krok 5: Włącz tryb kompaktowy, aby usunąć puste wiersze

Tryb kompaktowy usuwa niepotrzebne wiersze z macierzy kodu kreskowego, zmniejszając całkowity rozmiar obrazu bez utraty zakodowanych danych.

```csharp
// Step 5: Enable compact mode to truncate the barcode and reduce size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

**Kiedy używać:** Jeśli generujesz kody kreskowe do przechowywania lub transmisji sieciowej, tryb kompaktowy może zmniejszyć plik PNG nawet o 30 %. Jednak niektóre starsze skanery mogą nie obsługiwać przyciętego PDF417; przetestuj na docelowym sprzęcie.

## Krok 6: Zapisz kod kreskowy jako obraz PNG

Wybierz ścieżkę wyjściową i wywołaj `Save`. Wyliczenie `BarCodeImageFormat.Png` generuje obraz bezstratny, odpowiedni dla większości zastosowań.

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

**Weryfikacja wyniku:** Otwórz plik PNG w dowolnym przeglądarce obrazów. Powinieneś zobaczyć gęsty, wysokokontrastowy kod kreskowy, który odpowiada przykładowemu tekstowi. Zeskanowanie obrazu przy użyciu czytnika PDF417 (np. ZXing lub aplikacji na smartfon) zwraca oryginalny ciąg `"Åspóse.Barcóde©"`.

![Wygenerowany obraz kodu kreskowego PDF417 zapisany jako PNG](compact-pdf417.png "Wygenerowany kod kreskowy PDF417 w C#")

*Powyższy obraz przedstawia końcowy wynik kodu z tutorialu.*

## Pełny, działający przykład

Łącząc wszystkie elementy, oto kompletny program konsolowy, który możesz skopiować, wkleić i uruchomić.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;

namespace Pdf417GeneratorDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with PDF417 encoding
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // 2️⃣ Fine‑tune module size for sharper output
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set a narrow column count to keep the barcode slim
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Activate compact mode to drop empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define where the PNG will be written
            string outputPath = @"C:\Barcodes\CompactPdf417.png";

            // 6️⃣ Save the image
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Oczekiwany wynik

Uruchomienie programu wypisuje:

```
Barcode saved to C:\Barcodes\CompactPdf417.png
```

Plik `CompactPdf417.png` zawiera kompaktowy kod kreskowy PDF417, który koduje podany ciąg Unicode. Zeskanowanie obrazu standardowym czytnikiem PDF417 zwraca dokładny tekst.

## Typowe warianty i przypadki brzegowe

| Sytuacja | Dostosowanie | Powód |
|-----------|------------|--------|
| **Dłuższy ładunek danych** (np. > 150 znaków) | Zwiększ `generator.Parameters.Barcode.Pdf417.Columns` do 6‑8 | Więcej kolumn zapobiega nadmiernemu wydłużeniu kodu. |
| **Potrzeba przezroczystego tła** | Użyj `generator.Save(outputPath, BarCodeImageFormat.Png, new ImageSaveOptions { BackgroundColor = Color.Transparent })` | Przezroczysty PNG lepiej integruje się z nakładkami UI. |
| **Generowanie JPEG dla sieci** | Zmień format na `BarCodeImageFormat.Jpeg` i opcjonalnie ustaw `ImageQuality` | JPEG zmniejsza rozmiar pliku kosztem utraty bezstratnej jakości. |
| **Obsługa null lub pustego wejścia** | Zabezpiecz wejście przed utworzeniem generatora: `if (string.IsNullOrEmpty(text)) throw new ArgumentException("Text cannot be empty.");` | Zapobiega wyjątkom w czasie wykonywania i zapewnia sensowne kody kreskowe. |

## Wskazówki do użycia w produkcji

* **Obsługa wyjątków:** Otocz logikę generowania w blok `try/catch`, aby rejestrować błędy, takie jak niewystarczająca przestrzeń dyskowa lub nieprawidłowe parametry.  
* **Wydajność:** Ponownie używaj jednej instancji `BarcodeGenerator` przy generowaniu wielu kodów kreskowych z tymi samymi ustawieniami; aktualizuj jedynie właściwość `CodeText` pomiędzy zapisami.  
* **Bezpieczeństwo:** Gdy zakodowany tekst zawiera wrażliwe informacje, rozważ jego szyfrowanie przed przekazaniem do generatora oraz odszyfrowanie po zeskanowaniu.  

## Podsumowanie

Teraz wiesz, jak **wygenerować kod kreskowy PDF417** w C# przy użyciu biblioteki Aspose.BarCode, skonfigurować tryb kompaktowy, kontrolować liczbę kolumn i wyeksportować wynik jako obraz PNG. Ten tutorial omówił każdy krok, od konfiguracji projektu po obsługę przypadków brzegowych, dostarczając gotowe rozwiązanie dla aplikacji opartych na kodach kreskowych.

Następnie, zapoznaj się z powiązanymi tematami, takimi jak **tworzenie kodów QR w C#**, **generowanie kodów kreskowych w partiach** oraz **integracja skanowania kodów kreskowych z aplikacjami mobilnymi**. Każdy z nich opiera się na tych samych podstawach `BarcodeGenerator`, które właśnie opanowałeś.

Miłego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe tutoriale obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak generować kody kreskowe PDF417 – kompaktowe kodowanie PDF417](/barcode/english/net/compact-pdf417-encoding/)
- [Jak utworzyć kod kreskowy – kompaktowy PDF417 z Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak generować kod kreskowy Aztec z niestandardowym współczynnikiem proporcji przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}