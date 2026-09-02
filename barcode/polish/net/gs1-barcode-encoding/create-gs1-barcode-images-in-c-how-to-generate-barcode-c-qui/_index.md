---
category: general
date: 2026-07-18
description: Twórz obrazy kodów kreskowych GS1 w C# dzięki temu przewodnikowi krok
  po kroku, jak generować kody kreskowe w C# przy użyciu Aspose.BarCode – bez zbędnych
  dodatków, tylko działający kod.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create gs1 barcode images
- how to generate barcode c#
language: pl
lastmod: 2026-07-18
og_description: Twórz obrazy kodów kreskowych GS1 w C# dzięki temu zwięzłemu samouczkowi.
  Dowiedz się, jak generować kody kreskowe w C# przy użyciu Aspose.BarCode i zapisywać
  pliki PNG w kilka sekund.
og_image_alt: Screenshot of a generated GS1‑MicroPDF417 barcode saved as a PNG file
og_title: Tworzenie obrazów kodów kreskowych GS1 w C# – Kompletny przewodnik krok
  po kroku
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create GS1 barcode images in C# with this step‑by‑step guide on how
    to generate barcode C# using Aspose.BarCode – no fluff, just working code.
  headline: Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly
  type: TechArticle
tags:
- barcode
- csharp
- gs1
- aspose
title: Tworzenie obrazów kodów kreskowych GS1 w C# – Jak szybko generować kody kreskowe
  w C#
url: /pl/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz obrazy kodów kreskowych GS1 w C# – Jak wygenerować kod kreskowy w C#

Czy kiedykolwiek potrzebowałeś **utworzyć obrazy kodów kreskowych gs1** na etykietę opakowania, ale nie wiedziałeś, od czego zacząć? Nie jesteś sam. W tym samouczku zobaczysz dokładnie **jak wygenerować kod kreskowy c#**, który tworzy obrazy GS1‑MicroPDF417 w ciągu kilku minut.

Przejdziemy przez cały proces — instalację biblioteki, konfigurację generatora, wymianę danych AI (Application Identifier) oraz ostateczne zapisanie zestawu plików PNG. Po zakończeniu będziesz mieć gotową do uruchomienia aplikację konsolową, która generuje kilka obrazów kodów kreskowych GS1, każdy odzwierciedlający inną kombinację AI.

---

## Czego będziesz potrzebować

- **.NET 6+** (lub .NET Framework 4.6+). Najnowszy runtime działa najlepiej z Aspose.BarCode.
- **Aspose.BarCode for .NET** – zainstaluj przez NuGet (`Install-Package Aspose.BarCode`).
- Folder na dysku, w którym będą zapisywane pliki PNG (nazwijmy go `YOUR_DIRECTORY`).
- Podstawowa znajomość składni C# — nic skomplikowanego nie jest wymagane.

Jeśli już je masz, świetnie. Jeśli nie, najpierw pobierz pakiet NuGet; to jedynie jedna linia w konsoli Package Manager i zajmuje się wszystkimi zależnościami.

---

## Krok 1: Utwórz minimalny projekt konsolowy

Otwórz ulubione IDE (Visual Studio, Rider lub VS Code) i utwórz nowy projekt konsolowy:

```bash
dotnet new console -n Gs1BarcodeDemo
cd Gs1BarcodeDemo
dotnet add package Aspose.BarCode
```

Zastąp automatycznie wygenerowany plik `Program.cs` kodem pokazanym w kolejnych krokach. Ten szkielet daje nam czystą bazę do **utworzenia obrazów kodów kreskowych gs1** bez dodatkowego bałaganu.

---

## Krok 2: Jak utworzyć obrazy kodów kreskowych gs1 – Inicjalizacja generatora

Sercem operacji jest `BarcodeGenerator`. Rozpoczniemy go od początkowej wartości GS1‑MicroPDF417, na przykład `(17)991231(10)ABCD`. Ten ciąg koduje dwa AI: datę ważności (17) oraz partię/lot (10).

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with a GS1‑MicroPDF417 barcode type
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(17)991231(10)ABCD");
```

**Dlaczego to ważne:** `EncodeTypes.GS1MicroPdf417` informuje Aspose, że pracujemy z kompaktowym, wysokogęstościowym formatem GS1. Rozpoczęcie od prawidłowego ciągu AI zapewnia, że pierwszy zapisany PNG już spełnia standardy GS1.

---

## Krok 3: Dostosuj parametry wizualne – precyzyjne ustawienie rozmiaru i układu

Kod kreskowy, który jest zbyt mały lub o dziwnym kształcie, nie zostanie zeskanowany. Tutaj ustawiamy wymiar X (szerokość modułu) na 2 piksele, ograniczamy liczbę kolumn, aby obraz był wąski, oraz włączamy łączenie, aby w razie potrzeby można było połączyć kilka kodów kreskowych.

```csharp
        // Set visual parameters for a crisp, scannable image
        barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;      // module width
        barcodeGen.Parameters.Barcode.Pdf417.Columns = 2;        // column count
        barcodeGen.Parameters.Barcode.Pdf417.IsLinked = true;   // enable linking
```

**Wskazówka:** Jeśli potrzebujesz wyższego kodu kreskowego, zwiększ `Rows` zamiast kolumn. Dostosuj `XDimension`, aby spełnić minimalny rozmiar modułu 0,33 mm wymagany przez większość skanerów.

---

## Krok 4: Zapisz pierwszy kod kreskowy – AI 17 + AI 10

Teraz faktycznie zapisujemy obraz na dysku. Nazwa pliku odzwierciedla użyte AI, co ułatwia późniejsze odnalezienie.

```csharp
        // Save the first image (AI 17 + AI 10)
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_17_10.png",
                        BarCodeImageFormat.Png);
```

Po uruchomieniu programu powinieneś zobaczyć wyraźny PNG w `YOUR_DIRECTORY`. Otwórz go — zauważysz małe paski oraz czytelny dla człowieka tekst pod spodem. To pierwszy z wielu **obrazów kodów kreskowych gs1**, które wygenerujemy.

---

## Krok 5: Zmień zakodowane dane – ponowne użycie tego samego generatora

Zamiast tworzyć nowy `BarcodeGenerator` dla każdej pary AI, po prostu zamieniamy właściwość `CodeText` i ponownie wywołujemy `Save`. To podejście jest najefektywniejszym sposobem na **tworzenie obrazów kodów kreskowych gs1** masowo.

```csharp
        // AI 15 (best before) + AI 10 (batch)
        barcodeGen.CodeText = "(15)991231(10)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_15_10.png",
                        BarCodeImageFormat.Png);

        // AI 13 (production date) + AI 21 (serial)
        barcodeGen.CodeText = "(13)991231(21)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_13_21.png",
                        BarCodeImageFormat.Png);

        // AI 11 (manufacture date) + AI 21 (serial)
        barcodeGen.CodeText = "(11)991231(21)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_11_21.png",
                        BarCodeImageFormat.Png);

        // Only AI 17 (expiration) – no batch number
        barcodeGen.CodeText = "(17)991231";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_17.png",
                        BarCodeImageFormat.Png);
```

**Dlaczego ponowne użycie?** Zmiana `CodeText` eliminuje koszty ponownego tworzenia generatora i zapewnia spójne ustawienia wizualne we wszystkich obrazach.

---

## Krok 6: Uruchom, zweryfikuj i dostosuj

Skompiluj i uruchom:

```bash
dotnet run
```

Powinieneś teraz mieć pięć plików PNG, każdy nazwany po parze AI, którą zawiera. Otwórz dowolny z nich w przeglądarce obrazów; zobaczysz kod kreskowy i zakodowany tekst pod spodem. Aby podwójnie sprawdzić poprawność danych, użyj darmowej aplikacji skanera GS1 na telefonie — skieruj ją na PNG na ekranie i obserwuj wyświetlane wartości AI.

**Typowe problemy i jak ich unikać**

| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| Kod kreskowy nieczytelny | `XDimension` zbyt niska (np. 1 piksel) | Zwiększ do 2 lub 3 pikseli |
| Brak nawiasów AI | Nieprawidłowy format `CodeText` | Zawsze otaczaj każdy AI nawiasami |
| Obraz zbyt duży | Zbyt wiele kolumn/wierszy | Zredukuj `Columns` lub pozwól Aspose automatycznie dopasować rozmiar |
| Błąd wykonania `EncodeTypes` nie znaleziony | Brak `using Aspose.BarCode.Generation` | Dodaj brakujący dyrektyw `using` |

---

## Krok 7: Rozszerzenie przykładu – generowanie większej liczby kombinacji AI

Jeśli potrzebujesz **utworzyć obrazy kodów kreskowych gs1** dla dziesiątek wariantów produktu, rozważ wczytanie par AI z pliku CSV:

```csharp
using System.IO;

string[] lines = File.ReadAllLines(@"ai_pairs.csv"); // format: "(17)991231,(10)ABCD"
foreach (var line in lines)
{
    barcodeGen.CodeText = line.Replace(',', ' ');
    string fileName = $"GS1MicroPdf417_{line.Replace("(", "").Replace(")", "").Replace(",", "_")}.png";
    barcodeGen.Save(Path.Combine(@"YOUR_DIRECTORY", fileName), BarCodeImageFormat.Png);
}
```

---

## Zakończenie

Masz teraz kompletny, gotowy do uruchomienia program w C#, który **tworzy obrazy kodów kreskowych gs1** dla wielu scenariuszy AI, demonstrując najprostszy sposób **jak wygenerować kod kreskowy w C#** przy użyciu Aspose.BarCode. Dzięki ponownemu użyciu jednej instancji `BarcodeGenerator`, dostosowywaniu parametrów wizualnych i zamianie `CodeText`, możesz wygenerować dowolną liczbę zgodnych z GS1‑MicroPDF417 plików PNG, jakie wymaga Twój projekt.

Co dalej? Spróbuj dodać kolory (`barcodeGen.Parameters.Barcode.ForeColor`), osadzić kod kreskowy w PDF lub przejść na inną symbologię GS1, taką jak DataMatrix. Ten sam schemat ma zastosowanie — inicjalizuj, konfiguruj, ustaw `CodeText` i zapisz.

Śmiało zostaw komentarz, jeśli napotkasz problemy, lub podziel się własnymi wariantami. Szczęśliwego kodowania i niech Twoje skany zawsze będą czyste!

## Co powinieneś nauczyć się dalej?

Poniższe samouczki obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każdy zasób zawiera kompletne działające przykłady kodu z krok po kroku wyjaśnieniami, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak utworzyć strefę ciszy kodu kreskowego dla Code 16K przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Jak utworzyć strefę ciszy kodu kreskowego dla ITF-14 przy użyciu Aspose.BarCode dla .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Jak wygenerować kod kreskowy – konfiguracja Code 39 przy użyciu Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}