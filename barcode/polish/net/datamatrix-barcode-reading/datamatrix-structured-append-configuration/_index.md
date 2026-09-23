---
date: 2026-06-14
description: Dowiedz się, jak odczytywać DataMatrix i generować kody kreskowe typu
  Structured Append w .NET przy użyciu Aspose.BarCode, szybkiej i niezawodnej biblioteki
  kodów kreskowych.
keywords:
- how to read datamatrix
- DataMatrix structured append
- Aspose.BarCode .NET
linktitle: Konfiguracja Structured Append dla DataMatrix
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  headline: How to Read DataMatrix Append with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  name: How to Read DataMatrix Append with Aspose.BarCode for .NET
  steps:
  - name: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
    text: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
  - name: You can also browse other Aspose products [here](https://releases.aspose.com/).
    text: You can also browse other Aspose products [here](https://releases.aspose.com/).
  - name: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
    text: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET.
    question: What library handles DataMatrix structured append?
  - answer: Up to 16 DataMatrix symbols.
    question: How many symbols can a single structured append sequence contain?
  - answer: A free trial works for development and testing.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes, you can decode from a byte array or stream.
    question: Can I read the barcode without an image file?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Jak odczytać DataMatrix Append przy użyciu Aspose.BarCode dla .NET
url: /pl/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfiguracja DataMatrix Structured Append przy użyciu Aspose.BarCode dla .NET

Jeśli jesteś programistą poszukującym **how to read datamatrix** przy użyciu strukturalnego dołączania w aplikacjach .NET, Aspose.BarCode dla .NET jest rozwiązaniem, którego potrzebujesz. W tym przewodniku krok po kroku przejdziemy przez generowanie i dekodowanie kodów DataMatrix podzielonych na wiele symboli. Po zakończeniu tego tutorialu będziesz swobodnie tworzyć, konfigurować i odczytywać kody DataMatrix Structured Append przy użyciu Aspose.BarCode dla .NET.

## Szybkie odpowiedzi
- **Jaką bibliotekę obsługuje DataMatrix Structured Append?** Aspose.BarCode dla .NET.
- **Ile symboli może zawierać pojedyncza sekwencja Structured Append?** Do 16 symboli DataMatrix.
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna wystarcza do rozwoju i testów.
- **Jakie wersje .NET są wspierane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Czy mogę odczytać kod kreskowy bez pliku obrazu?** Tak, możesz dekodować z tablicy bajtów lub strumienia.

## Co to jest how to read datamatrix?
**how to read datamatrix** odnosi się do procesu dekodowania symboli DataMatrix i, w razie potrzeby, łączenia fragmentów sekwencji Structured Append w celu odzyskania oryginalnych danych. Aspose.BarCode zapewnia wbudowane wsparcie dla tego przepływu, automatycznie obsługując kolejność symboli i konkatenację danych.

## Dlaczego warto używać Aspose.BarCode dla DataMatrix Structured Append?
Aspose.BarCode obsługuje **ponad 30 symbologii kodów kreskowych** i potrafi dekodować obrazy o rozdzielczości do **10 000 × 10 000 px** w mniej niż **200 ms** na typowym serwerze. Biblioteka oferuje także **wdrożenie bez zależności**, co oznacza brak konieczności dodatkowych natywnych plików DLL, oraz działa na platformach Windows, Linux i macOS w środowiskach .NET.

## Wymagania wstępne

Przed rozpoczęciem tutorialu potrzebujesz:

1. Biblioteki Aspose.BarCode dla .NET – pobierz ją [tutaj](https://releases.aspose.com/barcode/net/).
2. Możesz również przeglądać inne produkty Aspose [tutaj](https://releases.aspose.com/).
3. Środowiska programistycznego .NET, takiego jak Visual Studio 2022 lub Visual Studio Code z rozszerzeniem C#.

Teraz rozpocznijmy budowanie i odczytywanie kodów DataMatrix Structured Append.

## Importowanie przestrzeni nazw

Pierwszym krokiem jest zaimportowanie przestrzeni nazw, które udostępniają API kodów kreskowych.

Klasa `BarCodeWriter` jest punktem wejścia Aspose.BarCode do tworzenia kodów, natomiast `BarCodeReader` obsługuje dekodowanie.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Po zaimportowaniu wymaganych przestrzeni nazw, wygenerujmy kod Structured Append.

## Jak odczytać kody DataMatrix Structured Append?

Wczytaj wygenerowany obraz (lub strumień) do `BarCodeReader`, włącz opcję `ReadStructuredAppend` i wywołaj `ReadBarcode`. Czytnik automatycznie zwróci połączone dane oraz udostępni szczegóły sekwencji, takie jak `StructuredAppendFileId`, `StructuredAppendTotalCount` i `StructuredAppendSegmentId`. Połączony wynik jest zwracany jako pojedynczy ciąg znaków, a identyfikatory poszczególnych segmentów można pobrać z właściwości `StructuredAppendSegmentId` czytnika w celu własnej obróbki.

```csharp
    using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
    {
        reader.ReadBarCodes();

        Console.WriteLine("Barcode ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodeId);
        Console.WriteLine("Barcodes count: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodesCount);
        Console.WriteLine("File ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendFileId);
    }
}
```

W tym kroku używamy czytnika do wyodrębnienia identyfikatora kodu, całkowitej liczby oraz identyfikatora pliku, potwierdzając prawidłową interpretację konfiguracji Structured Append.

## Krok 1: Konfiguracja DataMatrix Structured Append

Aby utworzyć kod DataMatrix Structured Append, musisz skonfigurować jego ustawienia. Obejmuje to określenie ścieżki katalogu, identyfikatora kodu, liczby kodów oraz identyfikatora pliku.

```csharp
string path = "Your Directory Path";

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;

    // Set DataMatrix structured append mode
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodeId = 3;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodesCount = 5;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendFileId = 150;

    // Generate the barcode image
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

W tym kroku skonfigurowaliśmy kod DataMatrix z żądanymi parametrami.

## Typowe problemy i rozwiązania

- **Nieprawidłowa kolejność segmentów:** Upewnij się, że wartości `StructuredAppendSegmentId` są kolejno numerowane od 0; w przeciwnym razie czytnik nie będzie w stanie poprawnie złożyć danych.
- **Niezgodna całkowita liczba:** `StructuredAppendTotalCount` musi być taka sama we wszystkich symbolach; rozbieżność spowoduje, że czytnik potraktuje sekwencję jako niekompletną.
- **Jakość obrazu:** Niskiej rozdzielczości obrazy mogą powodować niepowodzenia dekodowania. Dąż do co najmniej **300 dpi** przy renderowaniu kodu na bitmapę.

## Najczęściej zadawane pytania

### Q1: Co to jest DataMatrix Structured Append i dlaczego się go używa?

A1: DataMatrix Structured Append to funkcja umożliwiająca podzielenie dużej ilości danych na wiele mniejszych kodów kreskowych. Jest to szczególnie przydatne, gdy miejsce na pojedynczy kod jest ograniczone lub gdy konieczne jest efektywne organizowanie danych. Znajduje zastosowanie w logistyce, ochronie zdrowia i przemyśle.

### Q2: Czy mogę używać Aspose.BarCode dla .NET w projekcie open‑source?

A2: Tak, Aspose.BarCode dla .NET oferuje darmową wersję próbną, którą możesz wykorzystać w projektach open‑source. Wersję próbną znajdziesz [tutaj](https://releases.aspose.com/).

### Q3: Czy istnieje wsparcie społeczności dla Aspose.BarCode dla .NET?

A3: Tak, możesz uzyskać wsparcie społeczności i wymieniać się doświadczeniami z innymi użytkownikami na forum Aspose.BarCode [tutaj](https://forum.aspose.com/c/barcode/13).

### Q4: Jak mogę uzyskać tymczasową licencję dla Aspose.BarCode dla .NET?

A4: Jeśli potrzebujesz tymczasowej licencji do oceny lub testów, możesz ją uzyskać [tutaj](https://purchase.aspose.com/temporary-license/).

### Q5: Czy Aspose.BarCode dla .NET obsługuje inne typy kodów kreskowych?

A5: Tak, Aspose.BarCode dla .NET obsługuje szeroką gamę typów kodów, w tym QR Code, Code 128, EAN‑13 i wiele innych. Pełną dokumentację możesz przeglądać [tutaj](https://reference.aspose.com/barcode/net/), aby zobaczyć kompletną listę wspieranych typów kodów.

---

**Ostatnia aktualizacja:** 2026-06-14  
**Testowano z:** Aspose.BarCode 24.11 dla .NET  
**Autor:** Aspose

## Powiązane tutoriale

- [DataMatrix Reader Programming with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-reader-programming/)
- [Generate DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-versions/)
- [Master DataMatrix Macro Configuration with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}