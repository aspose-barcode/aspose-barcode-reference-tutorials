---
date: 2026-09-28
description: Dowiedz się, jak utworzyć kod macierzy 2D przy użyciu Aspose.BarCode
  for .NET – przewodnik krok po kroku generowania kodów DotCode z rozszerzonym tekstem
  kodu.
keywords:
- create 2d matrix barcode
- how to generate dotcode
- dotcode extended codetext
lastmod: 2026-09-28
linktitle: Konfiguracja rozszerzonego tekstu kodu DotCode
og_description: Dowiedz się, jak utworzyć kod macierzy 2D przy użyciu Aspose.BarCode
  for .NET. Ten przewodnik pokazuje krok po kroku, jak generować kody DotCode z rozszerzonym
  tekstem kodu.
og_image_alt: Guide showing how to create a 2d matrix DotCode barcode with extended
  codetext in .NET
og_title: Utwórz kod macierzy 2D przy użyciu Aspose.BarCode for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create 2d matrix barcode with Aspose.BarCode for .NET
    – a step‑by‑step guide for generating DotCode barcodes with extended code text.
  headline: How to create 2d matrix barcode via Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. The PNG image produced by the generator can be embedded in iOS, Android,
      or any cross‑platform mobile application.
    question: Can I use the generated barcode in a mobile app?
  - answer: Use the `AddECICodetext` method with the appropriate `ECIEncodings` (e.g.,
      `ECIEncodings.Base64`) to embed binary payloads.
    question: What if I need to encode binary data instead of text?
  - answer: Adjust the `XDimension.Pixels` property; higher values increase module
      size, while lower values make the barcode more compact.
    question: How do I change the barcode size without affecting readability?
  - answer: Yes. Set `gen.Parameters.Barcode.Margin` to define the desired quiet zone
      in pixels.
    question: Is there a way to add a quiet zone around the barcode?
  - answer: The latest Aspose.BarCode releases are compatible with .NET 8; just reference
      the appropriate NuGet package version.
    question: Does the library support .NET 8?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- dotcode
- Aspose.BarCode
- .NET barcode generation
- 2d matrix barcode
title: Jak utworzyć kod macierzy 2D przy użyciu Aspose.BarCode for .NET
url: /pl/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć 2d matrix barcode przy użyciu Aspose.BarCode dla .NET

## Wprowadzenie

W dziedzinie generowania i zarządzania kodami kreskowymi, Aspose.BarCode dla .NET wyróżnia się jako wszechstronne rozwiązanie, które obsługuje **50+ input and output formats** i może przetwarzać dokumenty liczące setki stron bez wczytywania całego pliku do pamięci. Niezależnie od tego, czy potrzebujesz kodów kreskowych do śledzenia produktów, kontroli zapasów, czy aplikacji bogatych w dane, tworzenie **2d matrix barcode** takiego jak DotCode z rozszerzonym kodem tekstowym pozwala osadzić zarówno tekstowe, jak i binarne ładunki w kompaktowym, kwadratowym symbolu. Ten samouczek przeprowadzi Cię krok po kroku przez budowanie tego rozszerzonego kodu tekstowego i renderowanie ostatecznego obrazu.

## Szybkie odpowiedzi
- **What does “create dotcode extended codetext” mean?** Oznacza to budowanie kodu DotCode, który zawiera FNC1, ECICodetext, zwykły tekst i separatory symboli w jednym rozszerzonym ładunku.  
- **Which library is required?** Aspose.BarCode for .NET.  
- **Do I need a license?** Tymczasowa licencja działa w trybie ewaluacji; pełna licencja jest wymagana w produkcji.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **How long does implementation take?** Około 10‑15 minut dla podstawowego przykładu.

## Jak utworzyć rozszerzony kod tekstowy dotcode

Załaduj swój projekt, ustaw katalog, zbuduj rozszerzony kod tekstowy i wygeneruj obraz – wszystko w mniej niż dwunastu linijkach kodu. Poniższa bezpośrednia odpowiedź podsumowuje cały proces:

Załaduj `BarcodeGenerator` z `EncodeTypes.DotCode`, zbuduj rozszerzony kod tekstowy przy użyciu `DotCodeExtendedCodetextBuilder` (dodając FNC1, ECICodetext, zwykły tekst i separatory FNC3), a następnie wywołaj `Save`, aby zapisać plik PNG. Ta sekwencja tworzy w pełni zgodny 2d matrix barcode w jednym wywołaniu.

## Czym jest rozszerzony kod tekstowy dotcode?

**dotcode extended codetext** to złożony ciąg, który łączy wiele segmentów danych — takich jak identyfikatory FNC1, ECICodetext, zwykły tekst i separatory FNC3 — w jeden ładunek, który DotCode może zdekodować. Umożliwia kodowanie wielojęzycznego tekstu, binarnych blobów i danych strukturalnych w jednym 2d matrix barcode, co czyni go idealnym dla scenariuszy łańcucha dostaw, opieki zdrowotnej i IoT.

## Dlaczego używać Aspose.BarCode do tego zadania?

Aspose.BarCode przetwarza **do 500 stron na sekundę** na typowym sprzęcie serwerowym i obsługuje **ponad 30 symbologii kodów kreskowych**, w tym DotCode. Jego API `GetExtendedCodetext` zapewnia prawidłowe rozmieszczenie znaków kontrolnych, eliminując błędy ręcznego łączenia ciągów i zapewniając zgodność z ISO/IEC 24724. Dodatkowo oferuje wbudowaną korekcję błędów i automatyczne obsługiwanie strefy ciszy, zmniejszając potrzebę ręcznej regulacji.

## Wymagania wstępne

- **Aspose.BarCode for .NET** – pobierz z [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).  
- Środowisko programistyczne .NET (zalecany Visual Studio 2022 lub nowszy).  
- Opcjonalnie: tymczasowy plik licencji do ewaluacji.

## Importuj przestrzenie nazw

`using Aspose.BarCode.Generation;`  
`using Aspose.BarCode.ComplexBarcodes;`  

Te przestrzenie nazw udostępniają klasę `BarcodeGenerator` oraz pomocnika `DotCodeExtendedCodetextBuilder` potrzebnego w przykładzie.

```csharp
using Aspose.BarCode.Generation;
```

Teraz, gdy mamy spełnione wymagania wstępne, przeanalizujmy proces generowania DotCode Extended Code Text w przewodniku krok po kroku.

## Krok 1: określ ścieżkę katalogu

Określ, gdzie zostanie zapisany wygenerowany plik PNG. Użyj ścieżki bezwzględnej lub względnej, do której Twoja aplikacja ma prawo zapisu.

```csharp
string path = "Your Directory Path";
```

Zastąp `"Your Directory Path"` rzeczywistą ścieżką w Twoim systemie.

## Krok 2: utwórz rozszerzony kod tekstowy dotcode

Klasa `DotCodeExtendedCodetextBuilder` łączy różne segmenty w pojedynczy ciąg rozszerzonego kodu tekstowego.

Aby utworzyć DotCode Extended Code Text, wykonaj następujące podkroki:

### 2.1 dodaj identyfikator formatu fnc1

Identyfikator formatu FNC1 oznacza początek nowego pola danych. Jest wymagany dla symboli DotCode zgodnych z GS1.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 dodaj ecicodetext

ECICodetext koduje znaki specjalne i tekst międzynarodowy. W tym przykładzie kodujemy `"犬Right狗"` przy użyciu UTF‑8.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 dodaj zwykły kod tekstowy

Możesz również dodać zwykły tekst do DotCode Extended Code Text. Tutaj dodajemy `"Plain text"`.

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 dodaj separator symboli fnc3

Separator symboli FNC3 oddziela różne sekcje kodu, poprawiając czytelność dla skanerów.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 dodaj inicjalizację czytnika fnc3

Ten krok dodaje informacje o inicjalizacji czytnika FNC3, które informują skaner, jak interpretować następujące dane.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 wygeneruj kod tekstowy

Teraz wygeneruj DotCode Extended Codetext, wywołując metodę `GetExtendedCodetext` na obiekcie `textBuilder`.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## Krok 3: wygeneruj obraz dotcode

Wygeneruj obraz kodu kreskowego z rozszerzonego kodu tekstowego.

#### 3.1 zainicjalizuj generator kodów kreskowych

Klasa `BarcodeGenerator` jest podstawowym obiektem Aspose.BarCode do tworzenia dowolnego kodu kreskowego. Tworzysz jej instancję z żądaną symbologią (`EncodeTypes.DotCode`) oraz rozszerzonym kodem tekstowym, który właśnie zbudowałeś.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Na koniec wywołaj `Save`, aby zapisać plik PNG na dysku. Obraz jest gotowy do osadzenia w raportach, aplikacjach mobilnych lub etykietach drukowanych.

## Typowe problemy i rozwiązania

- **Incorrect encoding** – Upewnij się, że używasz `ECIEncodings.UTF8` przy dodawaniu tekstu wielojęzycznego; w przeciwnym razie znaki mogą być zniekształcone.  
- **File‑access errors** – Sprawdź, czy aplikacja ma uprawnienia do zapisu w docelowym katalogu.  
- **Quiet zone missing** – Ustaw `gen.Parameters.Barcode.Margin`, jeśli skanery wymagają dodatkowej białej przestrzeni wokół symbolu.

## Najczęściej zadawane pytania

**Q: Czy mogę używać wygenerowanego kodu kreskowego w aplikacji mobilnej?**  
A: Tak. Obraz PNG wygenerowany przez generator może być osadzony w iOS, Android lub dowolnej aplikacji mobilnej wieloplatformowej.

**Q: Co zrobić, jeśli muszę zakodować dane binarne zamiast tekstu?**  
A: Użyj metody `AddECICodetext` z odpowiednim `ECIEncodings` (np. `ECIEncodings.Base64`), aby osadzić binarne ładunki.

**Q: Jak zmienić rozmiar kodu kreskowego bez wpływu na czytelność?**  
A: Dostosuj właściwość `XDimension.Pixels`; wyższe wartości zwiększają rozmiar modułu, a niższe wartości sprawiają, że kod jest bardziej zwarty.

**Q: Czy istnieje sposób na dodanie strefy ciszy wokół kodu kreskowego?**  
A: Tak. Ustaw `gen.Parameters.Barcode.Margin`, aby określić wymaganą strefę ciszy w pikselach.

**Q: Czy biblioteka obsługuje .NET 8?**  
A: Najnowsze wydania Aspose.BarCode są kompatybilne z .NET 8; wystarczy odwołać się do odpowiedniej wersji pakietu NuGet.

Jeśli potrzebujesz dalszych wskazówek lub masz pytania, nie wahaj się odwiedzić [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) lub skontaktować się ze społecznością na [Aspose.BarCode support forum](https://forum.aspose.com/c/barcode/13).

---

**Ostatnia aktualizacja:** 2026-09-28  
**Testowano z:** Aspose.BarCode 24.12 for .NET  
**Autor:** Aspose

## Powiązane samouczki

- [Utwórz DotCode Barcode .NET (Tryb automatyczny) z Aspose.BarCode](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)
- [Jak wygenerować kody DataMatrix przy użyciu Aspose.BarCode dla .NET – przewodnik krok po kroku](/barcode/net/datamatrix-barcode-configuration/)
- [Jak utworzyć kod Aztec przy użyciu Aspose.BarCode dla .NET](/barcode/net/aztec-barcode-encoding/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}