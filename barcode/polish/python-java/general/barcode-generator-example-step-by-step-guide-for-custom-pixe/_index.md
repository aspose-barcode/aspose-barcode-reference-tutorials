---
category: general
date: 2026-08-12
description: Przykład generatora kodów kreskowych, który pokazuje, jak generować kod
  kreskowy o precyzyjnym rozmiarze w pikselach. Dowiedz się, jak ustawić szerokość
  modułu, wysokość kreski i tworzyć kody kreskowe Planet.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to generate barcode
- barcode pixel size
- generate planet barcode
- barcode height setting
language: pl
lastmod: 2026-08-12
og_description: Przykład generatora kodów kreskowych pokazuje, jak generować kod kreskowy
  o dokładnych wymiarach w pikselach. Postępuj zgodnie z tym przewodnikiem, aby kontrolować
  szerokość modułu i wysokość kreski dla kodów Planet i RM4SCC.
og_image_alt: Screenshot of a barcode generator example showing a Planet barcode with
  custom pixel size
og_title: przykład generatora kodów kreskowych – dostosuj rozmiar piksela w C#
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: barcode generator example that shows how to generate barcode with precise
    pixel size. Learn to set module width, bar height and create Planet barcodes.
  headline: barcode generator example – step‑by‑step guide for custom pixel sizes
  type: TechArticle
- description: barcode generator example that shows how to generate barcode with precise
    pixel size. Learn to set module width, bar height and create Planet barcodes.
  name: barcode generator example – step‑by‑step guide for custom pixel sizes
  steps:
  - name: Install the Aspose.BarCode package
    text: 'Open a terminal in your project folder and run:'
  - name: Add the necessary `using` directives
    text: '```csharp using Aspose.BarCode.Generation; using Aspose.BarCode.BarCodeImageFormat;
      ```'
  - name: – generate a Planet barcode with automatically calculated height
    text: '```csharp // Step 1: Generate a Planet barcode with automatically calculated
      height BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet,
      "123456");'
  - name: – generate a Planet barcode with an explicit 100‑pixel height
    text: '```csharp // Step 2: Generate a Planet barcode with an explicit 100‑pixel
      height BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet,
      "123456");'
  - name: – generate an RM4SCC barcode with the same explicit height
    text: '```csharp // Step 3: Generate an RM4SCC barcode with the same explicit
      height BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC,
      "123456");'
  - name: What is **barcode pixel size**?
    text: '*Pixel size* refers to the physical number of screen or printer pixels
      that represent a single module (`XDimension`). A larger pixel size yields a
      bigger barcode, which can be easier for low‑resolution scanners but consumes
      more label real‑estate.'
  - name: How does `BarHeight` affect readability?
    text: The `BarHeight` property controls the vertical length of the bars. Standards
      for most 1‑D barcodes (including Planet and RM4SCC) recommend a minimum height
      of 10 mm when printed at 300 dpi, which translates to roughly 118 pixels. Setting
      a height below that can cause read errors, especially on mobil
  - name: When should you let the library calculate height automatically?
    text: If you’re generating barcodes for on‑screen display only, the automatic
      calculation keeps the aspect ratio consistent and reduces the amount of manual
      tweaking needed. For printed labels that must meet strict ISO specifications,
      you should **explicitly set the bar height**.
  - name: Pro tip on performance
    text: When generating thousands of barcodes in a batch job, reuse a single `BarcodeGenerator`
      instance and only change the `CodeText` and size parameters between saves. This
      avoids repeated allocation of internal rendering objects and can cut execution
      time by up to 30 %.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: przykład generatora kodów kreskowych – przewodnik krok po kroku dla niestandardowych
  rozmiarów pikseli
url: /pl/python-java/general/barcode-generator-example-step-by-step-guide-for-custom-pixe/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Przykład generatora kodów kreskowych – przewodnik krok po kroku dla niestandardowych rozmiarów pikseli

Jeśli potrzebujesz **przykładu generatora kodów kreskowych**, który pozwala kontrolować każdy piksel, ten przewodnik pokazuje dokładnie, jak to zrobić. Nauczysz się ustawiać szerokość modułu, definiować stałą wysokość pasków oraz generować zarówno kody kreskowe Planet, jak i RM4SCC o przewidywalnych wymiarach.

Większość programistów ma problem z obrazami „jak wygenerować kod kreskowy”, które wyglądają tak samo na każdym ekranie lub drukarce. Poniższe fragmenty kodu rozwiązują ten problem, udostępniając parametry na poziomie pikseli biblioteki Aspose.BarCode for .NET, dzięki czemu możesz uzyskać spójny wynik bez zgadywania.

## Czego się nauczysz

* Jak zainstalować wymaganą paczkę NuGet.
* Jak wygenerować kod kreskowy Planet z automatycznie obliczoną wysokością.
* Jak wygenerować kod kreskowy Planet z wyraźną wysokością 100 pikseli.
* Jak wygenerować kod kreskowy RM4SCC używając tej samej wyraźnej wysokości.
* Dlaczego **rozmiar piksela kodu kreskowego** ma znaczenie dla niezawodności skanowania.
* Wskazówki dotyczące rozwiązywania typowych problemów przy generowaniu obrazów kodów kreskowych Planet.

Wystarczy .NET 6 lub nowszy, podstawowe środowisko programistyczne C# oraz połączenie internetowe, aby pobrać pakiet NuGet.

---

## Przykład generatora kodów kreskowych – przygotowanie środowiska programistycznego

Przed napisaniem jakiegokolwiek kodu upewnij się, że biblioteka Aspose.BarCode jest dostępna w Twoim projekcie.

### Zainstaluj pakiet Aspose.BarCode

Otwórz terminal w folderze projektu i uruchom:

```bash
dotnet add package Aspose.BarCode
```

Polecenie dodaje najnowszą stabilną wersję **Aspose.BarCode** do Twojego pliku `csproj`. Po zakończeniu przywracania możesz rozpocząć używanie klasy `BarcodeGenerator`.

> **Wskazówka:** Celuj w .NET 6 lub .NET 7, aby skorzystać z najnowszych ulepszeń wydajności i domyślnego obsługi UTF‑8.

### Dodaj niezbędne dyrektywy `using`

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;
```

Te przestrzenie nazw udostępniają klasę `BarcodeGenerator` oraz wyliczenie `BarCodeImageFormat` używane później w samouczku.

---

## Jak wygenerować kod kreskowy z niestandardowym rozmiarem piksela

Poniższe trzy kroki ilustrują kompletny **przykład generatora kodów kreskowych**. Każdy krok opiera się na poprzednim, więc możesz skopiować‑wkleić cały blok do aplikacji konsolowej i uruchomić go bez zmian.

### Krok 1 – wygeneruj kod kreskowy Planet z automatycznie obliczoną wysokością

```csharp
// Step 1: Generate a Planet barcode with automatically calculated height
BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set module width (x‑dimension) to 4 pixels
planetAuto.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG
planetAuto.Save("PlanetAuto.png", BarCodeImageFormat.Png);
```

**Dlaczego to działa:**  
*Właściwość `XDimension` definiuje szerokość pojedynczego modułu kodu kreskowego (najmniejszego czarnego lub białego elementu). Gdy pomijasz `BarHeight`, biblioteka oblicza wysokość, która zachowuje standardowy współczynnik proporcji dla kodów Planet.*

**Oczekiwany wynik:** Plik PNG o nazwie `PlanetAuto.png` zawierający czysty kod kreskowy Planet. Jego wysokość dostosowuje się do szerokości modułu 4 piksele, zazwyczaj około 60 pikseli dla ładunku sześciu znaków.

### Krok 2 – wygeneruj kod kreskowy Planet z wyraźną wysokością 100 pikseli

```csharp
// Step 2: Generate a Planet barcode with an explicit 100‑pixel height
BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same module width
planetFixed.Parameters.Barcode.XDimension.Pixels = 4;

// Force the bar height to 100 pixels
planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the image
planetFixed.Save("PlanetHeight100.png", BarCodeImageFormat.Png);
```

**Dlaczego możesz tego potrzebować:**  
Czasami sprzęt skanujący wymaga minimalnej wysokości paska dla niezawodnego wykrywania. Ustawiając `BarHeight.Pixels`, zapewniasz, że każdy wygenerowany obraz spełnia ten wymóg, niezależnie od długości kodowanych danych.

**Oczekiwany wynik:** `PlanetHeight100.png` pokazuje te same dane co wcześniej, ale paski mają dokładnie 100 pikseli wysokości, dając pełną kontrolę nad rozmiarem wizualnym.

### Krok 3 – wygeneruj kod kreskowy RM4SCC z tą samą wyraźną wysokością

```csharp
// Step 3: Generate an RM4SCC barcode with the same explicit height
BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Use the same module width for consistency
rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;

// Apply the 100‑pixel bar height
rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the image
rm4sccFixed.Save("RM4SCCHeight100.png", BarCodeImageFormat.Png);
```

**Dlaczego to ma znaczenie:**  
`EncodeTypes.RM4SCC` to układany liniowy kod kreskowy używany w logistyce. Dopasowanie jego wysokości paska do kodu Planet upraszcza przetwarzanie wsadowe, gdy oba symbole pojawiają się na tej samej etykiecie.

**Oczekiwany wynik:** `RM4SCCHeight100.png` wyświetla idealnie wymiarowany kod kreskowy RM4SCC, dopasowany do wysokości 100 pikseli ustawionej dla kodu Planet.

> **Weryfikacja wyniku:** Otwórz każdy plik PNG w przeglądarce obrazów i potwierdź, że czarne paski mają dokładnie 4 piksele szerokości oraz, jeśli określono, 100 pikseli wysokości. Możesz także wprowadzić pliki do aplikacji skanującej kody kreskowe, aby upewnić się, że dekodują się jako „123456”.

## Zrozumienie rozmiaru piksela kodu kreskowego i wysokości paska

### Co to jest **rozmiar piksela kodu kreskowego**?

*Rozmiar piksela* odnosi się do fizycznej liczby pikseli ekranu lub drukarki, które reprezentują pojedynczy moduł (`XDimension`). Większy rozmiar piksela daje większy kod kreskowy, co może być łatwiejsze dla skanerów o niskiej rozdzielczości, ale zajmuje więcej miejsca na etykiecie.

### Jak `BarHeight` wpływa na czytelność?

Właściwość `BarHeight` kontroluje pionową długość pasków. Normy dla większości kodów 1‑D (w tym Planet i RM4SCC) zalecają minimalną wysokość 10 mm przy druku w 300 dpi, co przekłada się na około 118 pikseli. Ustawienie wysokości poniżej tej wartości może powodować błędy odczytu, szczególnie w przypadku kamer mobilnych.

### Kiedy pozwolić bibliotece automatycznie obliczyć wysokość?

Jeśli generujesz kody kreskowe wyłącznie do wyświetlania na ekranie, automatyczne obliczanie utrzymuje stały współczynnik proporcji i zmniejsza potrzebę ręcznych korekt. Dla drukowanych etykiet, które muszą spełniać rygorystyczne normy ISO, powinieneś **wyraźnie ustawić wysokość paska**.

## Typowe pułapki i najlepsze praktyki przy generowaniu kodu kreskowego Planet

| Pułapka | Dlaczego się dzieje | Rozwiązanie |
|---------|---------------------|-------------|
| Paski wydają się zbyt cienkie lub grube | `XDimension` pozostawiony domyślnie (1 piksel) na wyświetlaczach o wysokiej rozdzielczości | Ustaw `XDimension.Pixels` na co najmniej 3‑4 dla lepszej czytelności |
| Skaner nie może odczytać kodu | `BarHeight` jest zbyt mały dla ogniskowej skanera | Użyj `BarHeight.Pixels` ≥ 100 dla większości skanerów mobilnych |
| Obraz jest rozmyty po skalowaniu | Zapisywanie jako JPEG wprowadza artefakty kompresji | Zapisz jako PNG (`BarCodeImageFormat.Png`) dla bezstratnego wyniku |
| Nieoczekiwany typ kodu kreskowego | Błędna wartość wyliczenia `EncodeTypes` | Sprawdź, czy używasz `EncodeTypes.Planet` dla symbologii Planet |

### Wskazówka dotycząca wydajności

Podczas generowania tysięcy kodów kreskowych w zadaniu wsadowym, ponownie używaj jednej instancji `BarcodeGenerator` i zmieniaj jedynie `CodeText` oraz parametry rozmiaru pomiędzy zapisami. Zapobiega to wielokrotnemu przydzielaniu wewnętrznych obiektów renderujących i może skrócić czas wykonania nawet o 30 %.

## Pełny działający przykład – połącz wszystko razem

Utwórz nowy projekt konsolowy (`dotnet new console -n BarcodeDemo`) i zamień zawartość pliku `Program.cs` na następujący:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Directory where PNG files will be saved
            string outputDir = Environment.CurrentDirectory;

            // ---------- Planet barcode – automatic height ----------
            var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
            planetAuto.Save($"{outputDir}/PlanetAuto.png", BarCodeImageFormat.Png);
            Console.WriteLine("PlanetAuto.png generated.");

            // ---------- Planet barcode – fixed 100‑pixel height ----------
            var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            planetFixed.Save($"{outputDir}/PlanetHeight100.png", BarCodeImageFormat.Png);
            Console.WriteLine("PlanetHeight100.png generated.");

            // ---------- RM4SCC barcode – same fixed height ----------
            var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            rm4sccFixed.Save($"{outputDir}/RM4SCCHeight100.png", BarCodeImageFormat.Png);
            Console.WriteLine("RM4SCCHeight100.png generated.");

            Console.WriteLine("All barcodes created successfully.");
        }
    }
}
```

Uruchom program poleceniem `dotnet run`. Po wykonaniu znajdziesz trzy pliki PNG w folderze projektu, każdy ilustrujący inny scenariusz **przykładu generatora kodów kreskowych**.

## Kolejne kroki i powiązane tematy

* **Jak generować kod kreskowy w innych formatach** – poznaj `EncodeTypes.Code128`, `EncodeTypes.QR` i `EncodeTypes.DataMatrix` dla potrzeb 2‑D.  
* **Osadzanie kodów kreskowych w PDF** – połącz Aspose.BarCode z Aspose.PDF, aby umieszczać kody kreskowe bezpośrednio na szablonach faktur.  
* **Dynamiczny rozmiar kodu kreskowego w zależności od danych wejściowych użytkownika** – oblicz  

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [How to generate barcode java: Create an Exact Barcode Image](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)
- [How to Generate Barcode in Java Create and Set Size for Whole Picture](/barcode/english/java/barcode-basics/creating-setting-size-whole-picture-barcode/)
- [How to create code128 barcode Java and set bar height](/barcode/english/java/barcode-configuration/setting-bars-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}