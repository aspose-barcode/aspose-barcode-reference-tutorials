---
category: general
date: 2026-07-27
description: Utwórz wszechkierunkowy obraz kodu kreskowego przy użyciu Aspose.BarCode.
  Dowiedz się, jak generować kod kreskowy za pomocą Aspose, dostosować proporcje obrazu
  i zapisywać pliki PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional barcode image
- generate barcode with aspose
language: pl
lastmod: 2026-07-27
og_description: Utwórz wszechkierunkowy obraz kodu kreskowego przy użyciu Aspose.
  Postępuj zgodnie z tym przewodnikiem, aby wygenerować kod kreskowy za pomocą Aspose,
  dostosować proporcje i wyeksportować pliki PNG.
og_image_alt: Screenshot of two omnidirectional barcode images with different aspect
  ratios
og_title: Stwórz obraz wszechkierunkowego kodu kreskowego z Aspose – krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  headline: Create Omnidirectional Barcode Image with Aspose – Full Guide
  type: TechArticle
- description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  name: Create Omnidirectional Barcode Image with Aspose – Full Guide
  steps:
  - name: 1. Different Image Formats
    text: 'Aspose supports BMP, JPEG, TIFF, and SVG in addition to PNG. Swap the enum
      value:'
  - name: 2. Customizing Colors
    text: 'You might need a white barcode on a dark background. Set `ForeColor` and
      `BackColor`:'
  - name: 3. Handling Invalid Aspect Ratios
    text: 'Aspose validates the range (usually 5‑50). If you pass an out‑of‑range
      value, an `ArgumentException` is thrown. Wrap the save call in a try‑catch to
      give a friendly message:'
  - name: 4. Batch Generation
    text: When you have a list of GTINs, loop over them, update `CodeText`, and save
      each file with a unique name. The generator object can be reused, keeping memory
      usage low.
  type: HowTo
tags:
- barcode
- Aspose
- C#
- image-generation
title: Tworzenie wszechkierunkowego obrazu kodu kreskowego przy użyciu Aspose – pełny
  przewodnik
url: /pl/python-java/general/create-omnidirectional-barcode-image-with-aspose-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz obraz kodu kreskowego omnidirectional przy użyciu Aspose – Pełny przewodnik

Czy kiedykolwiek potrzebowałeś **utworzyć obraz kodu kreskowego omnidirectional**, ale nie wiedziałeś, którą bibliotekę wybrać? Nie jesteś jedyny. W wielu projektach logistycznych i detalicznych format DataBar Stacked Omnidirectional jest sekretnym składnikiem umożliwiającym kompaktowe, wysokogęstościowe kodowanie.  

Dobre wieści? Dzięki **Aspose.BarCode** możesz wygenerować ten kod kreskowy w kilku linijkach, dostosować jego współczynnik proporcji i zapisać PNG bezpośrednio na dysku. Poniżej zobaczysz dokładnie, jak **generować kod kreskowy przy użyciu Aspose**, dlaczego każde ustawienie ma znaczenie i na co zwrócić uwagę przy zmianie współczynnika proporcji.

---

## Co obejmuje ten samouczek

Przejdziemy przez cały cykl życia:

1. Konfiguracja folderu wyjściowego.  
2. Tworzenie generatora DataBar Stacked Omnidirectional.  
3. Konfigurowanie wymiarów pikseli i współczynników proporcji.  
4. Zapisywanie kodu kreskowego jako pliki PNG.  
5. Rozszerzanie przykładu o inne formaty i przypadki brzegowe.  

Pod koniec będziesz mieć gotową do uruchomienia aplikację konsolową C#, która wyprodukuje dwa odrębne obrazy kodów kreskowych. Bez zewnętrznych narzędzi, tylko czysty kod Aspose.

**Wymagania wstępne**

- .NET 6.0 SDK lub nowszy (kod działa również na .NET Framework 4.7.2).  
- Pakiet NuGet Aspose.BarCode for .NET (`Install-Package Aspose.BarCode`).  
- Folder na dysku, w którym można zapisywać obrazy.  

Jeśli już masz te elementy, zanurzmy się.

---

## Krok 1: Przygotuj folder wyjściowy

Najpierw wskaż programowi, gdzie ma zapisywać pliki PNG. Hard‑kodowanie ścieżki działa w demonstracji, ale w produkcji prawdopodobnie odczytasz ją z konfiguracji.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Define the folder where the images will be saved
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);   // ensures the folder exists
```

*Dlaczego to ważne:* `Directory.CreateDirectory` jest idempotentny; nie zgłosi wyjątku, jeśli folder już istnieje, co pozwala uniknąć bloku try‑catch.

---

## Krok 2: Utwórz generator DataBar Stacked Omnidirectional

Teraz uruchamiamy generator z określonym typem kodowania i przykładowymi danymi. Ciąg `"(01)12345678901231"` stosuje składnię identyfikatora aplikacji GS1 dla 14‑cyfrowego GTIN.

```csharp
        // Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

*Wyjaśnienie:* `EncodeTypes.DatabarStackedOmniDirectional` informuje Aspose, że ma użyć wariantu omnidirectional, który jest czytelny z dowolnego kierunku — idealny dla małych etykiet, które mogą być obrócone.

---

## Krok 3: Ustaw wspólne parametry kodu kreskowego

Zanim coś wyrenderujemy, definiujemy najmniejszy rozmiar elementu (X‑Dimension). Wartość **2 piksele** daje wyraźny obraz bez nadmiernego zwiększania rozmiaru pliku.

```csharp
        // Step 3: Set common barcode parameters (pixel size of the smallest element)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Wskazówka:* Jeśli potrzebujesz wyższej rozdzielczości do druku, podnieś tę wartość do 3 lub 4. Pamiętaj, że większe X‑Dimension zwiększają zarówno szerokość, jak i wysokość proporcjonalnie.

---

## Krok 4: Generuj i zapisz z współczynnikiem proporcji 15

Rodzina DataBar pozwala dostosować **współczynnik proporcji**, który kontroluje stosunek wysokości do szerokości. Współczynnik  **15** jest powszechnym domyślnym dla kodów omnidirectional.

```csharp
        // Step 4: Generate a barcode with an aspect ratio of 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
```

*Co zobaczysz:* Dość wysoki kod kreskowy, który nadal mieści się wygodnie na etykiecie 2 × 1 cm. Format PNG zachowuje jakość bezstratną, idealną do dalszego przetwarzania lub druku.

---

## Krok 5: Zmień współczynnik proporcji na 30 i zapisz ponownie

Chcesz bardziej „spłaszczony” kod? Po prostu zmień właściwość `AspectRatio` i ponownie wywołaj `Save`. Nie ma potrzeby tworzyć nowego generatora.

```csharp
        // Step 5: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
    }
}
```

*Dlaczego używać tego samego generatora?* Obiekty Aspose są lekkie; zmiana właściwości i ponowne zapisanie jest szybsze niż tworzenie nowej instancji i zapewnia, że te same ustawienia kodowania (np. X‑Dimension) pozostają spójne.

---

## Pełny działający przykład

Łącząc wszystko, oto kompletny, samodzielny program, który możesz skopiować i wkleić do nowego projektu konsolowego.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Initialize generator with omnidirectional DataBar
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Common settings
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // First image – aspect ratio 15
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio15.png");

        // Second image – aspect ratio 30
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio30.png");
    }
}
```

**Oczekiwany wynik**

Uruchomienie programu tworzy podfolder `Barcodes` zawierający:

- `DatabarAspectRatio15.png` – wyższy, klasyczny wygląd.  
- `DatabarAspectRatio30.png` – bardziej płaski, lepszy dla szerokich etykiet.  

Oba obrazy zawierają te same dane GTIN; różnią się jedynie proporcjami wizualnymi.

---

## Rozszerzanie przykładu (przypadki brzegowe i warianty)

### 1. Różne formaty obrazu

Aspose obsługuje BMP, JPEG, TIFF i SVG oprócz PNG. Zamień wartość wyliczenia:

```csharp
barcodeGenerator.Save(Path.Combine(outputFolder, "Databar.svg"),
                      BarCodeImageFormat.Svg);
```

SVG jest wektorowy, co oznacza, że możesz skalować go bez utraty ostrości — przydatne w responsywnych aplikacjach webowych.

### 2. Dostosowywanie kolorów

Możesz potrzebować białego kodu kreskowego na ciemnym tle. Ustaw `ForeColor` i `BackColor`:

```csharp
barcodeGenerator.Parameters.Barcode.ForeColor = System.Drawing.Color.White;
barcodeGenerator.Parameters.Barcode.BackColor = System.Drawing.Color.Black;
```

### 3. Obsługa nieprawidłowych współczynników proporcji

Aspose waliduje zakres (zwykle 5‑50). Jeśli przekażesz wartość spoza zakresu, zostanie rzucony `ArgumentException`. Owiń wywołanie zapisu w try‑catch, aby wyświetlić przyjazny komunikat:

```csharp
try
{
    barcodeGenerator.Save(...);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid aspect ratio: {ex.Message}");
}
```

### 4. Generowanie wsadowe

Gdy masz listę GTIN‑ów, przeiteruj ją, zaktualizuj `CodeText` i zapisz każdy plik pod unikalną nazwą. Obiekt generatora może być ponownie użyty, co utrzymuje niskie zużycie pamięci.

---

## Typowe pułapki i pro tipy

- **Nigdy nie zapominaj ustawić `XDimension`** przed zapisem; domyślna wartość (0,33 mm) może powodować rozmyte obrazy na wyświetlaczach o niskiej rozdzielczości.  
- **Współczynnik proporcji to wysokość‑do‑szerokości**, a nie odwrotnie. Większa liczba sprawia, że kod kreskowy jest *krótszy* w pionie.  
- **Ścieżki plików:** Używaj `Path.Combine`, aby uniknąć problemów ze znakami separatora specyficznymi dla platformy — szczególnie jeśli kod działa w kontenerach Linux.  
- **Licencjonowanie:** Aspose.BarCode jest komercyjny. W trybie próbnym na obrazie pojawia się znak wodny. Zarejestruj licencję wcześnie, aby uniknąć niespodzianek w produkcji.

---

## Zakończenie

Teraz wiesz, jak **utworzyć obraz kodu kreskowego omnidirectional** przy użyciu Aspose, dostosować współczynnik proporcji i wyeksportować pliki PNG — wszystko w mniej niż 30 linijkach C#. Ten samouczek pokazał krok po kroku proces, wyjaśnił, dlaczego każde ustawienie ma znaczenie, i omówił rozszerzenia, takie jak różne formaty, kolory i generowanie wsadowe.

Gotowy na kolejny wyzwanie? Spróbuj wygenerować kody QR, osadzić kod kreskowy w PDF lub zintegrować wynik z API ASP.NET Core. Te same **zasady generowania kodu kreskowego przy użyciu Aspose** obowiązują wszystkie typy kodów, więc możesz ponownie wykorzystać zdobytą wiedzę.

Masz pytania lub chcesz podzielić się własnymi modyfikacjami? zostaw komentarz poniżej — powodzenia w kodowaniu!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki dotyczą ściśle powiązanych tematów, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne przykłady kodu oraz szczegółowe wyjaśnienia, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia w własnych projektach.

- [Jak wygenerować kod Aztec z niestandardowym współczynnikiem proporcji przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Jak utworzyć kod kreskowy Aspose Java – dostosowanie jakości obrazu](/barcode/english/java/image-manipulation/adjusting-image-quality-barcode/)
- [Jak wygenerować obraz kodu kreskowego w Javie przy użyciu Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}