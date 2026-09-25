---
category: general
date: 2026-08-22
description: Utwórz kod kreskowy FCC 11 w C# przy użyciu Aspose.BarCode. Poznaj kod
  krok po kroku, skonfiguruj wymiary i wygeneruj obrazy PNG dla Australia Post.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create fcc 11 barcode
- Australia Post barcode
- Aspose.BarCode C#
- FCC 59 barcode
- FCC 62 barcode
- N‑Table encoding
- C‑Table encoding
language: pl
lastmod: 2026-08-22
og_description: Utwórz kod kreskowy FCC 11 w C# przy użyciu Aspose.BarCode. Skorzystaj
  z tego zwięzłego poradnika, aby wygenerować kody kreskowe PNG dla Australia Post,
  w tym warianty FCC 59 i FCC 62.
og_image_alt: Screenshot showing a generated FCC 11 barcode image
og_title: Tworzenie kodu kreskowego FCC 11 w C# – kompletny przewodnik Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  headline: How to create FCC 11 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  name: How to create FCC 11 barcode in C# with Aspose.BarCode
  steps:
  - name: 4.1 FCC 59 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)'
  - name: 4.2 FCC 62 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)'
  - name: 4.3 FCC 62 with C‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix'
  - name: 4.4 FCC 62 with Other encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567321032103210"); // Long payload for "Other" table'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- AustraliaPost
title: Jak utworzyć kod kreskowy FCC 11 w C# przy użyciu Aspose.BarCode
url: /pl/python-java/general/how-to-create-fcc-11-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć kod kreskowy FCC 11 w C# przy użyciu Aspose.BarCode

Jeśli potrzebujesz **utworzyć kod kreskowy FCC 11** w aplikacji .NET, ten przewodnik pokaże Ci dokładny wymagany kod. Zobaczysz, jak skonfigurować wymiary kodu kreskowego, wybrać odpowiednią tabelę kodowania i zapisać wynik jako plik PNG.

Generowanie kodów kreskowych Australia Post jest powszechnym wymogiem w logistyce, systemach pocztowych i śledzeniu zapasów. Ten tutorial obejmuje format FCC 11 oraz pokazuje, jak tworzyć kody kreskowe FCC 59 i FCC 62 przy użyciu różnych tabel kodowania, abyś mógł ponownie wykorzystać ten sam wzorzec dla innych usług pocztowych.

## Czego będziesz potrzebować

* .NET 6.0 SDK lub nowszy zainstalowany  
* Visual Studio 2022 (lub dowolne IDE kompatybilne z C#)  
* Ważna licencja na **Aspose.BarCode for .NET** – edycja community działa w trybie ewaluacyjnym  
* Uprawnienia do zapisu w folderze, w którym będą zapisywane pliki PNG  

Te wymagania wstępne gwarantują, że kod kompiluje się i działa bez dodatkowej konfiguracji.

## Krok 1: Zainstaluj pakiet NuGet Aspose.BarCode

Otwórz terminal w folderze projektu i uruchom:

```bash
dotnet add package Aspose.BarCode
```

Polecenie dodaje najnowszą stabilną wersję biblioteki do pliku projektu. Pakiet zawiera klasę `BarcodeGenerator` używaną w całym tym tutorialu.

## Krok 2: Zdefiniuj folder wyjściowy

Utwórz folder, w którym będą przechowywane wygenerowane obrazy. Ścieżka może być bezwzględna lub względna względem pliku wykonywalnego.

```csharp
// Step 2: Define the output folder
string outputPath = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputPath);
```

`Directory.CreateDirectory` zapewnia, że folder istnieje, zapobiegając błędom w czasie wykonywania, gdy metoda `Save` zapisuje plik.

## Krok 3: Wygeneruj kod kreskowy FCC 11

Format FCC 11 jest domyślnym kodowaniem dla kodów kreskowych poczty Australia Post. Poniższy kod tworzy kod kreskowy, który koduje ciąg liczbowy `1101234567`.

```csharp
// Step 3: Create a BarcodeGenerator for FCC 11
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,      // Use the Australia Post symbology
    "1101234567");                  // Data for FCC 11

// Configure visual appearance
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;   // Width of a single module
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50; // Height of the barcode

// Save as PNG
string fcc11Path = Path.Combine(outputPath, "PostalAustraliaPostFCC11.png");
barcodeGenerator.Save(fcc11Path, BarCodeImageFormat.Png);
```

**Dlaczego to działa:**  
* `EncodeTypes.AustraliaPost` informuje bibliotekę, aby zastosowała reguły kodowania Australia Post.  
* Ciąg danych `1101234567` spełnia specyfikację FCC 11: pierwsze dwie cyfry (`11`) identyfikują format, a następnie 7‑cyfrowy odnośnik klienta.  
* `XDimension` i `BarHeight` kontrolują rozmiar drukowanego kodu kreskowego, co jest ważne dla czytelności przez skaner.  

Po uruchomieniu programu znajdziesz plik `PostalAustraliaPostFCC11.png` w folderze `Barcodes`. Obraz wygląda następująco:

![create fcc 11 barcode example](https://example.com/fcc11.png "FCC 11 barcode generated by Aspose.BarCode")

## Krok 4: Utwórz dodatkowe kody kreskowe Australia Post (opcjonalnie)

Chociaż głównym celem jest **utworzenie kodu kreskowego FCC 11**, często potrzebne są kody FCC 59 lub FCC 62 dla różnych klas pocztowych. Poniższy kod ponownie używa tej samej instancji `BarcodeGenerator`, zmieniając jedynie ciąg danych i opcjonalną tabelę kodowania.

### 4.1 FCC 59 z kodowaniem N‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;

// Use N‑Table for customer information interpretation
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc59Path = Path.Combine(outputPath, "PostalAustraliaPostFCC59NTable.png");
barcodeGenerator.Save(fcc59Path, BarCodeImageFormat.Png);
```

### 4.2 FCC 62 z kodowaniem N‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc62NPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62NTable.png");
barcodeGenerator.Save(fcc62NPath, BarCodeImageFormat.Png);
```

### 4.3 FCC 62 z kodowaniem C‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.CTable;

string fcc62CPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62CTable.png");
barcodeGenerator.Save(fcc62CPath, BarCodeImageFormat.Png);
```

### 4.4 FCC 62 z innym kodowaniem

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567321032103210"); // Long payload for "Other" table

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.Other;

string fcc62OtherPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62OtherTable.png");
barcodeGenerator.Save(fcc62OtherPath, BarCodeImageFormat.Png);
```

Wszystkie cztery obrazy są zapisywane obok siebie w tym samym folderze, co ułatwia porównanie różnic wizualnych.

## Krok 5: Zrozum tabele kodowania

Australia Post definiuje trzy tabele kodowania:

* **N‑Table** – interpretuje numeryczne informacje o kliencie. Używaj jej, gdy ładunek danych zawiera wyłącznie cyfry.  
* **C‑Table** – obsługuje znaki alfanumeryczne, przydatna dla numerów referencyjnych zawierających litery.  
* **Other** – opcja awaryjna dla niestandardowych lub rozszerzonych formatów danych.  

Wybór właściwej tabeli zapewnia, że skaner kodów kreskowych odczyta informacje dokładnie tak, jak zamierzono. Jeśli pominiesz właściwość `AustralianPostEncodingTable`, biblioteka domyślnie użyje N‑Table, co może obciąć znaki nie‑numeryczne.

## Wskazówki, przypadki brzegowe i typowe pułapki

| Sytuacja | Zalecane podejście |
|-----------|----------------------|
| Długość ciągu danych jest krótsza niż wymagana | Uzupełnij część numeryczną zerami wiodącymi, aby spełnić specyfikację FCC. |
| Kod kreskowy jest rozmyty po wydrukowaniu | Zwiększ `XDimension` do 5 lub 6 pikseli i sprawdź ustawienia DPI drukarki. |
| Skaner zwraca „nieprawidłowy format” | Sprawdź, czy właściwa tabela kodowania (N‑Table, C‑Table, Other) odpowiada ładunkowi danych. |
| Uruchamianie na Linuksie bez interfejsu graficznego | Upewnij się, że pakiet `System.Drawing.Common` jest odwołany, lub użyj metody `Save` z `BarCodeImageFormat.Png`, która nie wymaga kontekstu wyświetlania. |
| Potrzebny inny format obrazu | Zastąp `BarCodeImageFormat.Png` przez `BarCodeImageFormat.Jpeg` lub `BarCodeImageFormat.Tiff` w zależności od potrzeb. |

Te praktyczne wskazówki pochodzą z rzeczywistych wdrożeń rozwiązań kodów kreskowych poczty.

## Pełny działający przykład

Poniżej znajduje się samodzielny program, który możesz skopiować do nowego projektu konsolowego (`dotnet new console`) i uruchomić bez modyfikacji.



## Co powinieneś się nauczyć dalej?

Poniższe tutoriale obejmują ściśle powiązane tematy, które rozwijają techniki przedstawione w tym przewodniku. Każde źródło zawiera kompletne działające przykłady kodu z wyjaśnieniami krok po kroku, aby pomóc Ci opanować dodatkowe funkcje API i odkrywać alternatywne podejścia implementacyjne w własnych projektach.

- [Jak generować kod kreskowy java – kod kreskowy Australia Post z Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)
- [Utwórz jednowymiarowy Databar GS1 Encoding z Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Jak utworzyć strefę ciszy kodu kreskowego .NET dla Code 16K przy użyciu Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}