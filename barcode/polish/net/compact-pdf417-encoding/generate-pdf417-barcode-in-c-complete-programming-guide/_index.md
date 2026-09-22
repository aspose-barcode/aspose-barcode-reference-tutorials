---
category: general
date: 2026-07-18
description: Szybko generuj kod kreskowy PDF417. Dowiedz się, jak ustawić tryb powiązany
  i jak generować kod PDF417 przy użyciu Aspose.BarCode w przejrzystym samouczku krok
  po kroku.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to set linked mode
- how to generate pdf417 barcode
language: pl
lastmod: 2026-07-18
og_description: Generuj kod kreskowy PDF417 natychmiast. Ten samouczek pokazuje, jak
  ustawić tryb powiązany i jak generować kod kreskowy PDF417 przy użyciu Aspose.BarCode,
  wraz z gotowym do uruchomienia kodem.
og_image_alt: Screenshot of a generated PDF417 barcode with linked mode enabled
og_title: Generowanie kodu kreskowego PDF417 w C# – Pełny przewodnik krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate PDF417 barcode quickly. Learn how to set linked mode and how
    to generate PDF417 barcode with Aspose.BarCode in a clear step‑by‑step tutorial.
  headline: Generate PDF417 Barcode in C# – Complete Programming Guide
  type: TechArticle
- description: Generate PDF417 barcode quickly. Learn how to set linked mode and how
    to generate PDF417 barcode with Aspose.BarCode in a clear step‑by‑step tutorial.
  name: Generate PDF417 Barcode in C# – Complete Programming Guide
  steps:
  - name: Prerequisites
    text: '- .NET 6.0 or later (the code also works on .NET Framework 4.7+). - Basic
      C# knowledge. - Visual Studio 2022 (or any IDE you prefer). - A free Aspose.BarCode
      trial or licensed copy.'
  - name: Expected Output
    text: Running the program prints a confirmation line, and the folder now contains
      `Pdf417Linked.png`. Opening the PNG shows a three‑column PDF417 barcode that
      may span two rows (thanks to linked mode). Scanning it with a smartphone app
      reveals the text **“Aspose”**.
  - name: 1. *What if the barcode looks blurry?*
    text: Usually this is a DPI issue. Increase `XDimension.Pixels` or save the image
      at a higher resolution using `generator.Save(..., BarCodeImageFormat.Png, 300)`
      where `300` is the DPI.
  - name: 2. *Can I encode longer strings?*
    text: Yes—PDF417 can hold up to ~1,850 characters. If you exceed the capacity
      of the chosen column count, the library automatically adds rows. Adjust `Columns`
      or enable `IsLinked` to keep the barcode compact.
  - name: 3. *Do I need a license for production?*
    text: Aspose.BarCode works in evaluation mode, but the generated barcode will
      have a small watermark. Purchase a license to remove it and unlock advanced
      features like error‑correction level tweaking.
  - name: 4. *How to generate PDF417 barcode in other formats?*
    text: Simply change the second argument of `Save`. For JPEG use `BarCodeImageFormat.Jpeg`;
      for PDF use `BarCodeImageFormat.Pdf`.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspose
title: Generowanie kodu kreskowego PDF417 w C# – Kompletny przewodnik programistyczny
url: /pl/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generowanie kodu kreskowego PDF417 w C# – Kompletny przewodnik programistyczny

Kiedykolwiek potrzebowałeś **wygenerować kod kreskowy PDF417** w aplikacji .NET, ale nie wiedziałeś od czego zacząć? Nie jesteś sam. Niezależnie od tego, czy tworzysz drukarkę biletów lotniczych, skaner magazynowy, czy po prostu eksperymentujesz z kodami 2‑D, uruchomienie PDF417 jest prostsze niż myślisz.

W tym przewodniku przejdziemy krok po kroku przez **generowanie kodu kreskowego PDF417** przy użyciu Aspose.BarCode, pokażemy **jak ustawić tryb połączony (linked mode)** oraz omówimy **jak wygenerować kod PDF417** z własnymi parametrami – wszystko w jednym, gotowym do skopiowania przykładzie.

## Czego się nauczysz

- Minimalny pakiet NuGet, którego potrzebujesz.
- Jak zainicjalizować generator PDF417 z własnym tekstem.
- **Jak ustawić tryb połączony**, aby kod mógł rozciągać się na wiele wierszy.
- Dodatkowe ustawienia, takie jak rozmiar modułu i liczba kolumn.
- Jak zapisać wynik jako PNG, JPEG lub dowolny obsługiwany format.
- Typowe pułapki i szybkie wskazówki diagnostyczne.

### Wymagania wstępne

- .NET 6.0 lub nowszy (kod działa także na .NET Framework 4.7+).
- Podstawowa znajomość C#.
- Visual Studio 2022 (lub dowolne inne IDE).
- Bezpłatna wersja próbna Aspose.BarCode lub licencjonowana kopia.

> **Pro tip:** Jeśli pracujesz na nowej maszynie, uruchom `dotnet add package Aspose.BarCode` w terminalu w katalogu projektu. Pobierze to wszystkie niezbędne pliki.

---

## Krok 1: Zainstaluj Aspose.BarCode i dodaj przestrzenie nazw

Na początek – wprowadźmy bibliotekę do projektu.

```csharp
// Using the .NET CLI
dotnet add package Aspose.BarCode
```

Następnie, na początku pliku C#, dołącz wymagane przestrzenie nazw:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;   // For image format enums
```

> **Dlaczego to ważne:** Bez przestrzeni nazw `Aspose.BarCode.Generation` nie będziesz mieć dostępu do `BarcodeGenerator`, a `System.Drawing.Imaging` dostarcza wyliczenie `ImageFormat` potrzebne do zapisywania plików.

---

## Krok 2: Zainicjalizuj generator kodu PDF417

Teraz tworzymy instancję generatora i podajemy tekst, który ma zostać zakodowany. To jest sedno **jak wygenerować kod PDF417**.

```csharp
// Step 2: Create a generator for PDF417 with the desired payload
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Aspose");
```

> **Wyjaśnienie:** `EncodeTypes.Pdf417` informuje Aspose, że używamy symboliki PDF417. Drugi argument, `"Aspose"`, to dane, które pojawią się po zeskanowaniu kodu.

---

## Krok 3: Określ rozmiar modułu (X‑Dimension)

Rozmiar modułu kontroluje, jak duży będzie każdy mały kwadrat (czy „piksel”) kodu. Mniejsze wartości dają bardziej zwartą grafikę; większe zwiększają czytelność na drukarkach o niskiej rozdzielczości.

```csharp
// Step 3: Set the X‑dimension in pixels (module size)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Typowy zakres:** 1–4 piksele sprawdzają się na większości ekranów. Jeśli drukujesz na drukarce etykiet o wysokim DPI, podnieś wartość do 3 lub 4.

---

## Krok 4: Skonfiguruj liczbę kolumn i włącz tryb połączony

Tutaj odpowiadamy na pytanie **jak ustawić tryb połączony**. Tryb połączony pozwala kodowi PDF417 rozdzielić się na kilka wierszy, co jest przydatne przy ograniczonej szerokości.

```csharp
// Step 4a: Choose the number of columns (affects data capacity & shape)
generator.Parameters.Barcode.Pdf417.Columns = 3;

// Step 4b: Turn on linked mode so the barcode can wrap
generator.Parameters.Barcode.Pdf417.IsLinked = true;
```

> **Dlaczego tryb połączony?** Wyobraź sobie, że kod musi zmieścić się w wąskim elemencie UI. Ustawiając `IsLinked = true`, biblioteka automatycznie dzieli symbol na wiersze, zachowując możliwość skanowania.

> **Przypadek brzegowy:** Jeśli ustawisz zbyt małą liczbę `Columns` i jednocześnie włączysz tryb połączony, Aspose może znacznie zwiększyć liczbę wierszy, co może przekroczyć rozmiar małego płótna obrazu. Monitoruj końcowe wymiary obrazu.

---

## Krok 5: Zapisz obraz kodu kreskowego

Na koniec zapisujemy kod do pliku. Możesz wybrać PNG, JPEG, BMP lub nawet PDF. PNG jest bezstratny, co czyni go idealnym do dalszej obróbki.

```csharp
// Step 5: Persist the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417Linked.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

> **Rezultat:** Otrzymasz wyraźny kod PDF417 z trzema kolumnami, rozmiarem modułu 2 piksele i połączonymi wierszami, jeśli dane nie mieszczą się w jednym wierszu.

---

## Pełny działający przykład

Poniżej znajduje się kompletny, gotowy do uruchomienia program. Skopiuj‑wklej go do nowego projektu konsolowego (`dotnet new console`) i naciśnij **F5**.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator with PDF417 and payload
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Aspose");

        // 2️⃣ Set module size (X‑dimension) – 2 pixels works well on most screens
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Define columns and enable linked mode
        generator.Parameters.Barcode.Pdf417.Columns = 3;
        generator.Parameters.Barcode.Pdf417.IsLinked = true;   // ← how to set linked mode

        // 4️⃣ Choose output path and save as PNG
        string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417Linked.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ PDF417 barcode generated! Saved at: {outputPath}");
    }
}
```

### Oczekiwany wynik

Uruchomienie programu wypisuje linię potwierdzającą, a w folderze pojawia się plik `Pdf417Linked.png`. Otwierając PNG zobaczysz kod PDF417 o trzech kolumnach, który może rozciągać się na dwa wiersze (dzięki trybowi połączonemu). Zeskanowanie go aplikacją na smartfonie wyświetli tekst **„Aspose”**.

---

## Częste pytania i rozwiązywanie problemów

### 1. *Co zrobić, gdy kod jest rozmazany?*  
Zwykle to problem DPI. Zwiększ `XDimension.Pixels` lub zapisz obraz w wyższej rozdzielczości, używając `generator.Save(..., BarCodeImageFormat.Png, 300)`, gdzie `300` to DPI.

### 2. *Czy mogę kodować dłuższe ciągi znaków?*  
Tak – PDF417 pomieści do ~1 850 znaków. Jeśli przekroczysz pojemność przy wybranej liczbie kolumn, biblioteka automatycznie doda wiersze. Dostosuj `Columns` lub włącz `IsLinked`, aby kod pozostał kompaktowy.

### 3. *Czy potrzebna jest licencja do produkcji?*  
Aspose.BarCode działa w trybie ewaluacyjnym, ale wygenerowany kod będzie zawierał mały znak wodny. Kup licencję, aby go usunąć i odblokować zaawansowane funkcje, takie jak regulacja poziomu korekcji błędów.

### 4. *Jak wygenerować kod PDF417 w innych formatach?*  
Po prostu zmień drugi argument metody `Save`. Dla JPEG użyj `BarCodeImageFormat.Jpeg`; dla PDF – `BarCodeImageFormat.Pdf`.

---

## Rozszerzenie przykładu

Teraz, gdy wiesz **jak wygenerować kod PDF417** i **jak ustawić tryb połączony**, możesz eksperymentować z:

- **Poziomem korekcji błędów** – `generator.Parameters.Barcode.Pdf417.ErrorCorrection = Pdf417ErrorCorrectionLevel.Level3;`
- **Dodaniem obramowania** – `generator.Parameters.Barcode.BorderWidth = 1;`
- **Niestandardowymi kolorami** – `generator.Parameters.Barcode.ForeColor = Color.DarkBlue;`
- **Osadzeniem kodu w raporcie PDF** – połącz Aspose.PDF z Aspose.BarCode.

Każda z tych modyfikacji polega na tym samym schemacie: znajdź odpowiednią właściwość pod `generator.Parameters.Barcode.Pdf417` (lub ogólnym obiektem `Barcode`) i ustaw wartość.

---

## Zakończenie

Omówiliśmy wszystko, co potrzebne, aby **generować kod PDF417** w C#, od instalacji Aspose.BarCode, przez konfigurację trybu połączonego, po zapis obrazu. Postępując zgodnie z powyższymi krokami, uzyskasz gotowy do produkcji generator kodów, który możesz wstawić do dowolnego rozwiązania .NET.

Pamiętaj najważniejsze wnioski:

1. Inicjalizuj z `EncodeTypes.Pdf417`.
2. Dostosuj `XDimension` dla przejrzystości wizualnej.
3. Ustaw `Columns` i włącz `IsLinked`, aby kontrolować układ (**jak ustawić tryb połączony**).
4. Zapisz w wybranym formacie.

Śmiało eksperymentuj z dodatkowymi parametrami i nie wahaj się podzielić wynikami lub zadać pytania w komentarzach. Miłego kodowania i niech Twoje kody zawsze skanują się za pierwszym razem!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki dotyczą ściśle powiązanych tematów, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne, działające przykłady kodu oraz szczegółowe wyjaśnienia, aby pomóc Ci opanować dodatkowe funkcje API i poznać alternatywne podejścia w własnych projektach.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}