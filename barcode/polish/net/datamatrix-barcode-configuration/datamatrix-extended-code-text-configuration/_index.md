---
date: 2026-09-23
description: Dowiedz się, jak używać Aspose.BarCode do generowania kodu kreskowego
  DataMatrix z rozszerzonym tekstem kodu w .NET, idealnego dla aplikacji magazynowych
  i logistycznych.
keywords:
- how to use aspose
- create barcode for inventory
- barcode generation .net core
- generate barcode image c#
lastmod: 2026-09-23
linktitle: Konfiguracja rozszerzonego tekstu kodu DataMatrix
og_description: Jak używać Aspose.BarCode do generowania kodu kreskowego DataMatrix
  z rozszerzonym tekstem kodu w .NET. Skorzystaj z szybkiego przewodnika krok po kroku
  dla rozwiązań magazynowych i logistycznych.
og_image_alt: Screenshot of a DataMatrix barcode generated with Aspose.BarCode in
  a .NET console app
og_title: Jak używać Aspose.BarCode do tworzenia tekstu kodu DataMatrix w .NET
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  headline: How to use Aspose.BarCode to create DataMatrix code text in .NET
  type: TechArticle
- description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  name: How to use Aspose.BarCode to create DataMatrix code text in .NET
  steps:
  - name: Define the output folder
    text: Specify where the generated barcode image will be saved. Replace the placeholder
      with a valid path on your machine.
  - name: Build the extended code text
    text: '`DataMatrixExtCodetextBuilder` is a helper class that assembles the extended
      code text according to the DataMatrix specification. It automatically inserts
      the required ECI (Extended Channel Interpretation) markers. This mix demonstrates
      how you can combine Unicode characters, C40 encoding, plain tex'
  - name: Generate the final codetext string
    text: After configuring all parts, retrieve the combined string that Aspose.BarCode
      will embed into the barcode.
  - name: Create the DataMatrix barcode
    text: '`BarcodeGenerator` is the core class that produces barcode images. Instantiate
      it with `EncodeTypes.DataMatrix` and the extended codetext, then set visual
      parameters such as X‑dimension, image format, and optional human‑readable text.
      The above code **creates barcode aspose .net** with the desired e'
  - name: Verify the barcode by reading it back
    text: '`BarCodeReader` validates that the generated symbol can be decoded correctly,
      which is essential for automated test pipelines and quality assurance. If everything
      is set up properly, the console will output the exact extended code text you
      built earlier.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library is needed?
  - answer: DataMatrix with extended code text
    question: Which barcode type?
  - answer: Yes, the API is cross‑platform
    question: Can I use .NET Core / .NET 6?
  - answer: A free trial works for development; a license is required for production
    question: Do I need a license for testing?
  - answer: About 10‑15 minutes for a basic example
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- Aspose.BarCode
- DataMatrix
- .NET barcode
- C# barcode generation
- inventory labeling
title: Jak używać Aspose.BarCode do tworzenia tekstu kodu DataMatrix w .NET
url: /pl/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak używać Aspose.BarCode do tworzenia tekstu kodu DataMatrix w .NET

Integracja kodów kreskowych w nowoczesnych aplikacjach .NET nie jest już niszowym zadaniem — to podstawowy wymóg dla zarządzania zapasami, logistyki i rozwiązań skanowania mobilnego. W tym przewodniku **dowiesz się, jak używać Aspose.BarCode** do skonfigurowania kodu DataMatrix z rozszerzonym tekstem kodu, wygenerowania obrazu i weryfikacji go programowo. Zobaczysz, dlaczego takie podejście jest idealne do tworzenia kodów kreskowych dla zapasów i jak pasuje do projektów .NET Core lub .NET 6.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebujesz?** Aspose.BarCode for .NET  
- **Jaki typ kodu kreskowego?** DataMatrix with extended code text  
- **Czy mogę używać .NET Core / .NET 6?** Yes, the API is cross‑platform  
- **Czy potrzebna jest licencja do testów?** A free trial works for development; a license is required for production  
- **Jak długo trwa implementacja?** About 10‑15 minutes for a basic example  

## Czym jest Aspose.BarCode dla .NET?
Aspose.BarCode for .NET to komercyjna biblioteka, która umożliwia programistom generowanie i rozpoznawanie ponad 30 symbologii kodów kreskowych, w tym DataMatrix, QR i Code 128, oraz tworzenie obrazów o rozdzielczości do 10 000 × 10 000 pikseli bez zewnętrznych zależności. Obsługuje .NET Framework 4.5+, .NET Core 3.1+ oraz .NET 5/6/7.

## Dlaczego używać rozszerzonego tekstu kodu DataMatrix?
Rozszerzony tekst kodu DataMatrix pozwala osadzić wiele schematów kodowania — UTF‑8, C40, Text, X12 — w jednym symbolu, umożliwiając do **3116 kodów** (około 155 KB danych) w jednym zwartym kwadracie. Ta funkcja jest idealna do wielojęzycznego oznakowania produktów, śledzenia wyrobów medycznych oraz inteligentnego pakowania, gdzie konieczne jest połączenie alfanumerycznych identyfikatorów z ładunkami binarnymi.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz następujące elementy:

1. **Aspose.BarCode for .NET** – pobierz go z oficjalnej strony **[Aspose.BarCode .NET download page](https://releases.aspose.com/barcode/net/)**.  
2. **Środowisko programistyczne .NET** – Visual Studio, Rider lub VS Code z .NET SDK.  
3. **Podstawowa znajomość C#** – powinieneś być zaznajomiony z klasami, przestrzeniami nazw i dyrektywą `using`.

## Importowanie przestrzeni nazw

Dodaj wymagane przestrzenie nazw na początku pliku C#, aby kompilator wiedział, gdzie znaleźć klasy kodów kreskowych.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Te przestrzenie nazw zapewniają dostęp zarówno do funkcji generowania, jak i rozpoznawania kodów kreskowych.

## Jak skonfigurować rozszerzony tekst kodu DataMatrix?

Załaduj builder, dodaj żądane segmenty i pozwól Aspose.BarCode automatycznie obsłużyć znaczniki ECI. Ten bezpośredni akapit opisuje dokładne kroki: utwórz `DataMatrixExtCodetextBuilder`, dodaj segmenty Unicode, C40, zwykły tekst oraz tryb Text, a następnie pobierz połączony ciąg dla generatora.

### Krok 1: Określ folder wyjściowy

Określ, gdzie zostanie zapisany wygenerowany obraz kodu kreskowego. Zastąp placeholder prawidłową ścieżką na swoim komputerze.

```csharp
string path = "Your Directory Path";
```

### Krok 2: Zbuduj rozszerzony tekst kodu

`DataMatrixExtCodetextBuilder` to klasa pomocnicza, która składa rozszerzony tekst kodu zgodnie ze specyfikacją DataMatrix. Automatycznie wstawia wymagane znaczniki ECI (Extended Channel Interpretation).

```csharp
DataMatrixExtCodetextBuilder codetextBuilder = new DataMatrixExtCodetextBuilder();
codetextBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
codetextBuilder.AddECICodetextWithEncodeMode(ECIEncodings.UTF8, DataMatrixEncodeMode.C40, "ABCDE");
codetextBuilder.AddPlainCodetext("test");
codetextBuilder.AddCodetextWithEncodeMode(DataMatrixEncodeMode.Text, "abcde");
```

Ten przykład pokazuje, jak można połączyć znaki Unicode, kodowanie C40, zwykły tekst i tryb Text w jednym symbolu DataMatrix.

### Krok 3: Wygeneruj ostateczny ciąg tekstu kodu

Po skonfigurowaniu wszystkich części, pobierz połączony ciąg, który Aspose.BarCode osadzi w kodzie kreskowym.

```csharp
string codetext = codetextBuilder.GetExtendedCodetext();
```

### Krok 4: Utwórz kod DataMatrix

`BarcodeGenerator` to podstawowa klasa generująca obrazy kodów kreskowych. Utwórz jej instancję z `EncodeTypes.DataMatrix` oraz rozszerzonym tekstem kodu, a następnie ustaw parametry wizualne, takie jak wymiar X, format obrazu i opcjonalny tekst czytelny dla człowieka.

```csharp
using (var generator = new BarcodeGenerator(EncodeTypes.DataMatrix, codetext))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended Codetext";
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ExtendedCodetext;

    generator.Save($"{path}DataMatrixExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Powyższy kod **tworzy kod kreskowy aspose .net** z żądanym rozszerzonym tekstem kodu i zapisuje go jako plik PNG.

### Krok 5: Zweryfikuj kod kreskowy odczytując go ponownie

`BarCodeReader` weryfikuje, że wygenerowany symbol może być poprawnie odkodowany, co jest niezbędne w zautomatyzowanych pipeline'ach testowych i zapewnianiu jakości.

```csharp
using (var reader = new BarCodeReader(generator.GenerateBarCodeImage(), DecodeType.DataMatrix))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine("DataMatrixExtendedCodetext:" + result.CodeText);
}
```

Jeśli wszystko jest poprawnie skonfigurowane, konsola wyświetli dokładny rozszerzony tekst kodu, który został wcześniej zbudowany.

## Częste problemy i rozwiązywanie ich

| Problem | Powód | Rozwiązanie |
|---------|-------|-------------|
| Kod nieczytelny | Zbyt mały wymiar X | Zwiększ `XDimension.Pixels` (np. 4 → 6) |
| Zniekształcone znaki | Nieprawidłowe kodowanie ECI | Upewnij się, że `ECIEncodings.UTF8` odpowiada zestawowi znaków |
| Plik nie zapisany | Nieprawidłowa ścieżka | Użyj ścieżki bezwzględnej lub upewnij się, że folder istnieje |
| Wyjątek licencyjny | Okres próbny wygasł | Zastosuj tymczasową lub pełną licencję (zobacz FAQ) |

## Najczęściej zadawane pytania

### Q1: Czym jest Aspose.BarCode dla .NET?
A1: Aspose.BarCode for .NET to potężna biblioteka, która umożliwia programistom generowanie i rozpoznawanie szerokiej gamy symbologii kodów kreskowych, w tym DataMatrix, QR, Code128 i innych.

### Q2: Gdzie mogę znaleźć dokumentację Aspose.BarCode dla .NET?
A2: Pełną dokumentację API można znaleźć pod adresem **[Aspose.BarCode .NET API reference](https://reference.aspose.com/barcode/net/)**.

### Q3: Czy dostępna jest darmowa wersja próbna Aspose.BarCode dla .NET?
A3: Tak, darmową wersję próbną można pobrać z **[Aspose.BarCode free trial download](https://releases.aspose.com/)**.

### Q4: Jak uzyskać tymczasową licencję do testów?
A4: Tymczasowe licencje są udostępniane w celach ewaluacyjnych i można je zamówić na **[Aspose temporary license request page](https://purchase.aspose.com/temporary-license/)**.

### Q5: Gdzie mogę uzyskać wsparcie lub zadać pytania dotyczące Aspose.BarCode dla .NET?
A5: Oficjalne forum Aspose.BarCode jest najlepszym miejscem, aby uzyskać pomoc: **[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)**.

---

**Ostatnia aktualizacja:** 2026-09-23  
**Testowano z:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose

## Powiązane samouczki

- [Jak generować kody DataMatrix przy użyciu Aspose.BarCode dla .NET – Przewodnik krok po kroku](/barcode/net/datamatrix-barcode-configuration/)
- [Generowanie kodu DataMatrix w trybie ASCII przy użyciu Aspose.BarCode dla .NET (C#)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Generowanie kodu Aztec z kodowaniem tekstu przy użyciu Aspose.BarCode dla .NET](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}