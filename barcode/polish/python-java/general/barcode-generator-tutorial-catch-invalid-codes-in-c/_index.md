---
category: general
date: 2026-08-22
description: Samouczek generatora kodów kreskowych pokazujący, jak wygenerować obraz
  kodu kreskowego, zwalidować dane wejściowe i obsłużyć wyjątki nieprawidłowego kodu
  kreskowego w C# z Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator tutorial
- generate barcode image
- how to generate barcode
- invalid barcode example
- how to catch barcode
language: pl
lastmod: 2026-08-22
og_description: Samouczek generatora kodów kreskowych wyjaśnia, jak generować obraz
  kodu kreskowego, walidować dane i wykrywać błędy kodu kreskowego w C# przy użyciu
  Aspose.BarCode.
og_image_alt: barcode generator tutorial showing exception handling for invalid codes
og_title: Samouczek generatora kodów kreskowych – wykrywanie nieprawidłowych kodów
  w C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Barcode generator tutorial showing how to generate barcode image, validate
    input, and catch invalid barcode exceptions in C# with Aspose.BarCode.
  headline: 'Barcode generator tutorial: catch invalid codes in C#'
  type: TechArticle
tags:
- barcode
- C#
- exception‑handling
title: 'Samouczek generatora kodów kreskowych: wyłapywanie nieprawidłowych kodów w
  C#'
url: /pl/python-java/general/barcode-generator-tutorial-catch-invalid-codes-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Samouczek generatora kodów kreskowych – obsługa nieprawidłowych kodów w C#

Jeśli szukasz **samouczka generatora kodów kreskowych**, który nie tylko tworzy obraz kodu kreskowego, ale także chroni Twoją aplikację przed nieprawidłowymi danymi, jesteś we właściwym miejscu. Ten przewodnik przeprowadzi Cię przez cały proces: instalację biblioteki, konfigurację walidacji, generowanie obrazu oraz obsługę wyjątku, gdy tekst kodu jest nieprawidłowy.

Generowanie kodów kreskowych jest powszechnym wymogiem w systemach wysyłki, inwentaryzacji i punktów sprzedaży. Jednak wprowadzenie nieprawidłowego ciągu znaków do generatora może spowodować błędy w czasie wykonywania lub wygenerować nieczytelne kody kreskowe. Po zakończeniu tego samouczka zrozumiesz **jak generować kod kreskowy** obrazy bezpiecznie i zobaczysz praktyczny **przykład nieprawidłowego kodu kreskowego** z odpowiednią obsługą błędów.

## Czego będziesz potrzebować

- .NET 6.0 (lub dowolna nowsza wersja .NET)
- Visual Studio 2022 lub inne IDE C#
- Pakiet NuGet **Aspose.BarCode for .NET**  
  (`Install-Package Aspose.BarCode`)  
- Podstawowa znajomość obsługi wyjątków w C#

## Krok 1: Zainstaluj i odwołaj się do Aspose.BarCode

Otwórz swój projekt w Visual Studio, a następnie uruchom polecenie NuGet:

```powershell
Install-Package Aspose.BarCode
```

Pakiet dodaje przestrzeń nazw `Aspose.BarCode`, która zawiera klasę `BarcodeGenerator` używaną w całym tym samouczku.

## Krok 2: Utwórz generator kodów kreskowych z celowo nieprawidłową wartością

Pierwsza część **przykładu nieprawidłowego kodu kreskowego** pokazuje, jak utworzyć generator dla symboliki *Planet* z kodem naruszającym specyfikację.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 2.1: Planet symbology – the string is too long and contains illegal characters
            BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "1234567WRONG");
```

> **Dlaczego to ważne** – `EncodeTypes.Planet` oczekuje numerycznego ciągu o określonej długości. Podanie `"1234567WRONG"` uruchamia logikę walidacji wewnątrz biblioteki.

## Krok 3: Włącz ścisłą walidację, aby biblioteka rzucała wyjątek

Domyślnie Aspose.BarCode próbuje korygować drobne błędy. Aby uzyskać solidny scenariusz **jak przechwycić kod kreskowy**, powinieneś włączyć explicite walidację:

```csharp
            // Step 3.1: Tell the generator to throw when the code text is incorrect
            planetGenerator.Parameters.Barcode.ThrowExceptionWhenCodeTextIncorrect = true;
```

> **Wyjaśnienie** – Ustawienie `ThrowExceptionWhenCodeTextIncorrect` na `true` zmusza API do podniesienia `ArgumentException`, jeśli podany tekst nie spełnia reguł symboliki. Jest to zalecane podejście, gdy musisz zapewnić integralność danych.

## Krok 4: Wygeneruj obraz kodu kreskowego wewnątrz bloku try‑catch

Teraz próbujemy wygenerować obraz i przechwycić oczekiwany błąd:

```csharp
            try
            {
                // Step 4.1: Attempt to create the barcode image
                planetGenerator.GenerateBarCodeImage();
                Console.WriteLine("Planet barcode generated successfully.");
            }
            catch (Exception ex)
            {
                // Step 4.2: Handle the validation error
                Console.WriteLine($"Planet error: {ex.Message}");
            }
```

**Oczekiwany wynik**

```
Planet error: The code text is invalid for the selected symbology.
```

Komunikat wyjątku potwierdza, że biblioteka poprawnie zidentyfikowała problem.

## Krok 5: Powtórz proces dla innej symboliki (Postnet)

Aby pokazać, że ten sam wzorzec działa dla dowolnego typu kodu kreskowego, powtarzamy kroki dla **Postnet**, powszechnego kodu pocztowego:

```csharp
            // Step 5.1: Create a Postnet generator with an invalid code
            BarcodeGenerator postnetGenerator = new BarcodeGenerator(EncodeTypes.Postnet, "1234567WRONG");
            postnetGenerator.Parameters.Barcode.ThrowExceptionWhenCodeTextIncorrect = true;

            try
            {
                // Step 5.2: Attempt to generate the Postnet image
                postnetGenerator.GenerateBarCodeImage();
                Console.WriteLine("Postnet barcode generated successfully.");
            }
            catch (Exception ex)
            {
                // Step 5.3: Capture the validation error
                Console.WriteLine($"Postnet error: {ex.Message}");
            }
        }
    }
}
```

**Oczekiwany wynik**

```
Postnet error: The code text is invalid for the selected symbology.
```

Oba bloki demonstrują **jak generować kod kreskowy** obrazy przy jednoczesnym bezpiecznym obsługiwaniu nieprawidłowego wejścia.

## Krok 6: Zapisz prawidłowy obraz kodu kreskowego (opcjonalnie)

Jeśli później podasz prawidłowy ciąg, możesz zapisać wygenerowany obraz do pliku:

```csharp
            // Valid example – generate and save a QR code
            BarcodeGenerator qrGenerator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
            qrGenerator.Save("qr.png", BarCodeImageFormat.Png);
            Console.WriteLine("QR code saved as qr.png");
```

> **Wskazówka:** Zawsze waliduj dane wejściowe użytkownika przed przekazaniem ich do `BarcodeGenerator`. Nawet przy wyłączonym `ThrowExceptionWhenCodeTextIncorrect`, nieprawidłowy ciąg może generować nieczytelne kody kreskowe.

## Częste pułapki i jak ich unikać

| Pułapka | Dlaczego się pojawia | Rozwiązanie |
|---------|----------------------|-------------|
| Podawanie znaków alfabetowych do symbolik przyjmujących wyłącznie liczby (np. Planet, Postnet) | Biblioteka cicho przycina lub zamienia znaki, chyba że włączona jest ścisła walidacja | Ustaw `ThrowExceptionWhenCodeTextIncorrect = true` |
| Zapomnienie o odwołaniu do przestrzeni nazw `Aspose.BarCode` | Błąd kompilacji „BarcodeGenerator nie istnieje” | Dodaj `using Aspose.BarCode.Generation;` na początku pliku |
| Używanie przestarzałego pakietu NuGet | Nowe symboliki lub poprawki błędów mogą być nieobecne | Aktualizuj pakiet regularnie (`dotnet add package Aspose.BarCode --version x.x.x`) |

## Pełny, uruchamialny przykład

Poniżej znajduje się kompletny program, który możesz skopiować, wkleić i uruchomić bezpośrednio:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Planet – invalid code
            BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "1234567WRONG");
            planetGenerator.Parameters.Barcode.ThrowExceptionWhenCodeTextIncorrect = true;

            try
            {
                planetGenerator.GenerateBarCodeImage();
                Console.WriteLine("Planet barcode generated successfully.");
            }
            catch (Exception ex)
            {
                Console.WriteLine($"Planet error: {ex.Message}");
            }

            // Postnet – invalid code
            BarcodeGenerator postnetGenerator = new BarcodeGenerator(EncodeTypes.Postnet, "1234567WRONG");
            postnetGenerator.Parameters.Barcode.ThrowExceptionWhenCodeTextIncorrect = true;

            try
            {
                postnetGenerator.GenerateBarCodeImage();
                Console.WriteLine("Postnet barcode generated successfully.");
            }
            catch (Exception ex)
            {
                Console.WriteLine($"Postnet error: {ex.Message}");
            }

            // Valid QR code – optional saving
            BarcodeGenerator qrGenerator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
            qrGenerator.Save("qr.png", BarCodeImageFormat.Png);
            Console.WriteLine("QR code saved as qr.png");
        }
    }
}
```

Uruchomienie tego programu wypisuje dwa komunikaty o błędach dla nieprawidłowych kodów kreskowych i tworzy plik `qr.png` dla prawidłowego kodu QR.

## Zakończenie

Ten **samouczek generatora kodów kreskowych** pokazał, jak **generować obiekty obrazu kodu kreskowego**, wymusić ścisłą walidację oraz **jak przechwycić wyjątki związane z kodem kreskowym** w C#. Dzięki włączeniu `ThrowExceptionWhenCodeTextIncorrect` zamieniasz nieprawidłowe dane wejściowe w kontrolowany błąd zamiast cichej awarii.

Z tego miejsca możesz:

- Zbadaj inne symboliki, takie jak Code128, EAN13 lub DataMatrix.
- Dostosuj kolory, rozmiary i marginesy za pomocą `GeneratorParameters`.
- Zintegruj generowanie kodów kreskowych z API ASP.NET Core lub aplikacjami Windows Forms.

Pamiętaj, że walidacja danych wejściowych **przed** wywołaniem `GenerateBarCodeImage` jest najbezpieczniejszym sposobem, aby utrzymać system niezawodnym i skany wolne od błędów. Szczęśliwego kodowania!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak wygenerować obraz kodu kreskowego z dostosowaniem dodatkowej przestrzeni przy użyciu Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Jak generować kody DataMatrix przy użyciu Aspose.BarCode dla .NET – przewodnik krok po kroku](/barcode/english/net/datamatrix-barcode-configuration/)
- [Jak generować kod Aztec z niestandardowym współczynnikiem proporcji przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}