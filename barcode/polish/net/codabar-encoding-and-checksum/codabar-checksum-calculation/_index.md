---
date: 2026-06-29
description: Dowiedz się, jak generować kod kreskowy Codabar z sumą kontrolną przy
  użyciu Aspose.BarCode dla .NET. Przewodnik krok po kroku obejmujący tryby sum kontrolnych
  Mod10 i Mod16.
keywords:
- generate codabar barcode
- aspose barcode .net
- codabar checksum
- mod10 checksum
- mod16 checksum
linktitle: Obliczanie sumy kontrolnej Codabar
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to generate Codabar barcode with checksum using Aspose.BarCode
    for .NET. Step‑by‑step guide covering Mod10 and Mod16 checksum modes.
  headline: Generate Codabar barcode with checksum (Aspose.BarCode .NET)
  type: TechArticle
- questions:
  - answer: Absolutely. Mod16 provides stronger error detection, which is beneficial
      for high‑throughput environments like libraries.
    question: Can I use the Mod16 checksum for library book barcodes?
  - answer: The additional digit adds negligible processing time; most scanners handle
      it without noticeable delay.
    question: Does enabling checksum affect scanning speed?
  - answer: After generating the barcode, recompute the checksum using the same `CodabarChecksumMode`
      and compare it to the last character of the encoded string.
    question: How do I verify the checksum programmatically?
  - answer: Yes. Use the `BarcodeGenerator` appearance settings (e.g., `BarHeight`,
      `ForeColor`) to style the entire barcode, including the checksum digit.
    question: Is it possible to customize the appearance of the checksum digit?
  - answer: Instantiate a single `BarcodeGenerator`, update the `CodeText` property
      for each iteration, and call `Save` with a unique filename each time.
    question: What if I need to generate multiple barcodes in a loop?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Generuj kod kreskowy Codabar z sumą kontrolną (Aspose.BarCode .NET)
url: /pl/net/codabar-encoding-and-checksum/codabar-checksum-calculation/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generuj kod kreskowy Codabar z sumą kontrolną (Aspose.BarCode .NET)

Codabar jest szeroko stosowaną liniową symbologią kodów kreskowych używaną w logistyce, bibliotekach i opiece zdrowotnej. **Generowanie kodu kreskowego Codabar z sumą kontrolną** znacząco poprawia integralność danych, wykrywając błędy transkrypcji, zanim spowodują problemy. W tym samouczku dowiesz się, jak dodać sumę kontrolną podczas *generowania kodu kreskowego Codabar* przy użyciu Aspose.BarCode dla .NET oraz zobaczysz w działaniu tryby sumy kontrolnej Mod10 i Mod16.

## Szybkie odpowiedzi
- **Co oznacza „dodaj sumę kontrolną” dla Codabar?** Dodaje cyfrę wykrywającą błąd, która waliduje zakodowane dane.  
- **Jakie tryby sumy kontrolnej są obsługiwane?** Mod10 (standardowy) i Mod16 (wyższa dokładność).  
- **Czy potrzebna jest licencja do używania tej funkcji?** Tak – wymagana jest ważna licencja Aspose.BarCode dla .NET w środowisku produkcyjnym.  
- **Jakie wersje .NET są kompatybilne?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Gdzie zapisywane są wygenerowane obrazy?** W folderze określonym w zmiennej `path`.

## Jak wygenerować kod kreskowy Codabar z sumą kontrolną?

Wczytaj dane, włącz sumę kontrolną, wybierz `CodabarChecksumMode.Mod10` lub `CodabarChecksumMode.Mod16` i wywołaj `Save`. Aspose.BarCode obsługuje obliczenia i automatycznie dopisuje cyfrę sumy kontrolnej, dzięki czemu otrzymujesz gotowy do skanowania obraz w jednym wywołaniu metody. Możesz także określić folder wyjściowy, nazwę pliku i format obrazu (np. PNG) przy zapisie.

## Dlaczego dodać sumę kontrolną do kodu kreskowego Codabar?

Dodanie sumy kontrolnej zmniejsza liczbę błędów pojedynczych znaków o **do 99,9 %** i wykrywa większość pomyłek przestawiania, co jest kluczowe w branżach takich jak banki krwi, gdzie pojedynczy błąd cyfry może mieć poważne konsekwencje. Spełnia także wymogi regulacyjne wielu standardów logistycznych.

## Wymagania wstępne

1. **Aspose.BarCode for .NET** – pobierz najnowszą wersję z [tutaj](https://releases.aspose.com/barcode/net/).  
2. **Środowisko programistyczne C#** – Visual Studio, VS Code lub dowolne IDE obsługujące .NET.

Teraz, gdy wszystko jest gotowe, przejdźmy do implementacji.

## Importowanie przestrzeni nazw

Klasa `BarcodeGenerator` znajduje się w przestrzeni nazw `Aspose.BarCode.Generation`. Zaimportuj ją na początku pliku:

`using Aspose.BarCode.Generation;`

## Co to jest klasa BarcodeGenerator?

Klasa `BarcodeGenerator` jest podstawowym obiektem Aspose.BarCode, który tworzy, konfiguruje i renderuje obraz kodu kreskowego. Zawiera wszystkie ustawienia specyficzne dla kodu, takie jak symbologia, tekst, rozmiar i opcje sumy kontrolnej, umożliwiając generowanie obrazów jednym wywołaniem `Save`. Modyfikując właściwość `Parameters`, możesz dostosować wygląd, tryb kodowania i funkcje wykrywania błędów dla dowolnego obsługiwanego typu kodu.

## Krok 1: Inicjalizacja generatora kodów kreskowych

Utwórz instancję `BarcodeGenerator`, określ symbologię Codabar i podaj dane do zakodowania. Zastąp `"Your Directory Path"` rzeczywistą ścieżką folderu, w którym chcesz zapisywać obrazy.

`var generator = new BarcodeGenerator(EncodeTypes.Codabar, "A123456A");`  
`string path = @"Your Directory Path";`

## Krok 2: Generowanie kodu kreskowego Codabar **bez** sumy kontrolnej

Jeśli starszy system oczekuje prostego kodu, ustaw opcję sumy kontrolnej na `Default`. To wyłącza dodatkową cyfrę.

`generator.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Default;`  
`generator.Save($"{path}\\Codabar_NoChecksum.png", BarCodeImageFormat.Png);`

## Krok 3: Generowanie kodu kreskowego Codabar z sumą kontrolną **Mod10**

Włącz sumę kontrolną i wybierz algorytm Mod10, który jest najczęściej używanym trybem dla Codabar.

`generator.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;`  
`generator.Parameters.Barcode.CodabarChecksumMode = CodabarChecksumMode.Mod10;`  
`generator.Save($"{path}\\Codabar_Mod10.png", BarCodeImageFormat.Png);`

## Krok 4: Generowanie kodu kreskowego Codabar z sumą kontrolną **Mod16**

Dla scenariuszy wymagających wyższego wykrywania błędów przełącz się na Mod16. Zmiana ogranicza się do jednej instrukcji przypisania.

`generator.Parameters.Barcode.CodabarChecksumMode = CodabarChecksumMode.Mod16;`  
`generator.Save($"{path}\\Codabar_Mod16.png", BarCodeImageFormat.Png);`

Dzięki tym czterem prostym krokom nauczyłeś się **jak generować kod kreskowy Codabar** z sumą kontrolną oraz jak przełączać się między trybami Mod10 i Mod16 przy użyciu Aspose.BarCode dla .NET.

## Częste problemy i rozwiązania

| Problem | Powód | Rozwiązanie |
|---------|-------|-------------|
| Wygenerowany obraz jest pusty | `path` wskazuje na nieistniejący folder | Upewnij się, że katalog istnieje lub wywołaj `Directory.CreateDirectory(path)` przed zapisem |
| Suma kontrolna nie została zastosowana | `IsChecksumEnabled` pozostawiono jako `Default` | Ustaw `IsChecksumEnabled = EnableChecksum.Yes` przed zapisem |
| Nieprawidłowy tryb sumy kontrolnej | Użyto niewłaściwej wartości wyliczenia | Użyj `CodabarChecksumMode.Mod10` lub `CodabarChecksumMode.Mod16` w zależności od potrzeb |

## Najczęściej zadawane pytania

**Q: Czy mogę używać sumy kontrolnej Mod16 dla kodów kreskowych książek w bibliotece?**  
A: Oczywiście. Mod16 zapewnia silniejsze wykrywanie błędów, co jest korzystne w środowiskach o dużym natężeniu, takich jak biblioteki.

**Q: Czy włączenie sumy kontrolnej wpływa na prędkość skanowania?**  
A: Dodatkowa cyfra wprowadza znikomy czas przetwarzania; większość skanerów radzi sobie z nią bez zauważalnego opóźnienia.

**Q: Jak programowo zweryfikować sumę kontrolną?**  
A: Po wygenerowaniu kodu, ponownie oblicz sumę kontrolną przy użyciu tego samego `CodabarChecksumMode` i porównaj ją z ostatnim znakiem zakodowanego ciągu.

**Q: Czy można dostosować wygląd cyfry sumy kontrolnej?**  
A: Tak. Użyj ustawień wyglądu `BarcodeGenerator` (np. `BarHeight`, `ForeColor`), aby stylizować cały kod, w tym cyfrę sumy kontrolnej.

**Q: Co zrobić, jeśli muszę generować wiele kodów w pętli?**  
A: Utwórz jedną instancję `BarcodeGenerator`, aktualizuj właściwość `CodeText` w każdej iteracji i wywołuj `Save` z unikalną nazwą pliku za każdym razem.

Jeśli napotkasz jakiekolwiek trudności, społeczność Aspose.BarCode jest gotowa pomóc na [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

---

**Ostatnia aktualizacja:** 2026-06-29  
**Testowano z:** Aspose.BarCode 24.11 dla .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarChecksum:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Default;
gen.Save($"{path}CodabarChecksumNone.png", BarCodeImageFormat.Png);
```

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod10;
gen.Save($"{path}CodabarChecksumMod10.png", BarCodeImageFormat.Png);
```

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod16;
gen.Save($"{path}CodabarChecksumMod16.png", BarCodeImageFormat.Png);
```

## Powiązane samouczki

- [Generuj kod kreskowy Codabar ze znakami start/stop w Aspose.BarCode dla .NET](/barcode/net/codabar-encoding-and-checksum/codabar-start-stop-characters/)
- [Kompleksowe samouczki i przykłady Aspose.BarCode dla .NET](/barcode/net/)
- [Generuj kod DataMatrix – przewodnik pro z Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}