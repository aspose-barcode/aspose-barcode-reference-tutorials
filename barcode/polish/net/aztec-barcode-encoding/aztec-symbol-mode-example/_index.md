---
date: 2026-05-24
description: Dowiedz się, jak tworzyć kod kreskowy Aztec w .NET przy użyciu Aspose.BarCode
  dla .NET, obejmując tryby symboli Auto, FullRange, Compact i Rune, z instrukcją
  krok po kroku.
keywords:
- create aztec barcode .net
- aztec symbol mode
- aspose barcode .net
linktitle: Przykład trybu symbolu Aztec
schemas:
- author: Aspose
  dateModified: '2026-05-24'
  description: Learn how to create aztec barcode .net using Aspose.BarCode for .NET,
    covering Auto, FullRange, Compact, and Rune symbol modes with step‑by‑step guidance.
  headline: Create Aztec Barcode .NET with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Aztec Symbol Mode determines how the library packs data into layers, affecting
      size, capacity, and readability.
    question: What is the purpose of Aztec Symbol Mode in barcode generation?
  - answer: Yes, simply assign a new string to the `CodeText` property before calling
      `Save`.
    question: Can I change the code text for Aztec barcodes in Aspose.BarCode for
      .NET?
  - answer: Yes, you can download a free trial version of Aspose.BarCode for .NET
      [here](https://releases.aspose.com/).
    question: Is there a free trial version of Aspose.BarCode for .NET available?
  - answer: You can refer to the complete documentation for Aspose.BarCode for .NET
      [here](https://reference.aspose.com/barcode/net/).
    question: Where can I find the full documentation for Aspose.BarCode for .NET?
  - answer: You can acquire a temporary license for Aspose.BarCode for .NET by visiting
      [this link](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Tworzenie kodu kreskowego Aztec w .NET z Aspose.BarCode
url: /pl/net/aztec-barcode-encoding/aztec-symbol-mode-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Opanowanie trybu symboli Aztec w Aspose.BarCode dla .NET

Jeśli chcesz szybko i niezawodnie **create aztec barcode .net**, Aspose.BarCode dla .NET zapewnia w pełni funkcjonalne API działające na .NET Framework, .NET Core oraz .NET 5/6+. W tym samouczku przyjrzymy się czterem trybom Aztec Symbol Modes — Auto, FullRange, Compact i Rune — pokazując dokładnie, jak przełączać się między nimi i zapisać wynik jako obraz. Po zakończeniu będziesz mógł osadzać kody Aztec w dowolnej aplikacji .NET przy użyciu kilku linijek kodu.

## Szybkie odpowiedzi
- **Jaka biblioteka generuje kody Aztec w .NET?** Aspose.BarCode for .NET.  
- **Ile trybów symboli obsługuje Aztec?** Cztery: Auto, FullRange, Compact i Rune.  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna działa w celach ewaluacyjnych; licencja komercyjna jest wymagana w produkcji.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ i .NET 6+.  
- **Czy mogę wyeksportować PNG, JPEG lub SVG?** Tak — obsługiwany jest każdy standardowy format obrazu.

## Co to jest create aztec barcode .net?
`create aztec barcode .net` odnosi się do procesu generowania dwuwymiarowego kodu Aztec przy użyciu API Aspose.BarCode w środowisku .NET. API automatycznie obsługuje kodowanie, wybór trybu symbolu oraz renderowanie obrazu, umożliwiając programistom tworzenie wysokiej jakości kodów kreskowych bez konieczności zajmowania się szczegółami niskiego poziomu, takimi jak obliczenia korekcji błędów czy manipulacja pikselami.

## Dlaczego używać Aspose.BarCode dla kodów Aztec?
Aspose.BarCode obsługuje **ponad 30 symbologii kodów kreskowych** i może renderować obrazy do **10 000 × 10 000 px** bez ładowania całego pliku do pamięci. Przetwarza dokument o 500 stronach w mniej niż **2 sekundy** na typowym serwerze, co czyni go idealnym rozwiązaniem dla scenariuszy o wysokiej przepustowości w przedsiębiorstwach.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że spełniasz następujące wymagania:

- Praktyczna znajomość programowania w .NET.  
- Zainstalowane Visual Studio na komputerze.  
- Kopia Aspose.BarCode dla .NET. Możesz ją pobrać [tutaj](https://releases.aspose.com/barcode/net/). Możesz również zapoznać się z innymi produktami Aspose [tutaj](https://releases.aspose.com/).

Teraz, gdy wszystko jest gotowe, przejdźmy do przykładów trybu symboli Aztec.

## Importowanie przestrzeni nazw

Najpierw musisz zaimportować niezbędne przestrzenie nazw, aby pracować z Aspose.BarCode dla .NET. Otwórz projekt w Visual Studio i dodaj następujące dyrektywy using na początku pliku kodu:

```csharp
using Aspose.BarCode.Generation;
```

Dzięki zaimportowanym przestrzeniom nazw możesz teraz rozpocząć korzystanie z Aspose.BarCode dla .NET.

## Jak skonfigurować Barcode Generator dla kodów Aztec?

Klasa `BarcodeGenerator` jest podstawowym komponentem, który tworzy obrazy kodów kreskowych na podstawie wybranej symbologii i opcji konfiguracji. Udostępnia prosty interfejs API do określenia typu kodu, danych do zakodowania oraz różnych parametrów renderowania przed zapisaniem wyniku do pliku obrazu.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

W tym kroku skonfigurowaliśmy generator i podaliśmy tekst kodu do zakodowania.

## Jak ustawić Aztec Symbol Mode na Auto?

Wyliczenie `AztecSymbolMode` definiuje cztery możliwe tryby symboli dla kodów Aztec, a opcja **Auto** pozwala bibliotece automatycznie wybrać najbardziej kompaktowy rozmiar, zachowując wszystkie wymagania dotyczące danych i korekcji błędów. Ten tryb jest idealny w większości scenariuszy, gdy chcesz uzyskać najmniejszy możliwy kod bez ręcznej regulacji.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

Ten krok zapewnia automatyczne określenie Aztec Symbol Mode, a powstały obraz kodu zostaje zapisany.

## Jak wymusić FullRange Symbol Mode?

Gdy potrzebujesz maksymalnej pojemności danych, możesz wybrać wartość **FullRange** z wyliczenia `AztecSymbolMode`. Ten tryb wyłącza automatyczne zmniejszanie rozmiaru, pozwalając kodowi przechowywać pełny zakres znaków i osiągnąć najwyższą możliwą gęstość informacji, co jest przydatne przy dużych zestawach danych.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

Spowoduje to utworzenie kodu z trybem FullRange Aztec Symbol Mode.

## Jak wygenerować Compact Aztec barcode?

Wartość **Compact** w wyliczeniu `AztecSymbolMode` tworzy mniejszy kod poprzez zmniejszenie liczby warstw używanych w macierzy. Skutkuje to bardziej oszczędnym pod względem przestrzeni obrazem, co sprawdza się w aplikacjach o ograniczonej powierzchni wyświetlania, takich jak ekrany mobilne czy małe etykiety.

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

Ten krok konfiguruje generowanie kodu z trybem Compact Aztec Symbol Mode.

## Jak utworzyć Rune Aztec barcode?

Tryb **Rune** jest specjalizowaną odmianą symbologii Aztec, która koduje dane numeryczne przy użyciu własnego zestawu znaków, oferując charakterystyczny wygląd przy zachowaniu takiej samej siły korekcji błędów jak inne tryby. Jest przydatny, gdy potrzebny jest kod podkreślający informacje liczbowe.

```csharp
gen.CodeText = "123"; // Change the code text if needed
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

Ten krok zmienia tekst kodu na „123” i generuje kod z trybem Rune Aztec Symbol Mode.

## Typowe problemy i rozwiązania

- **Obraz nie zapisuje się** – Upewnij się, że folder docelowy istnieje i aplikacja ma uprawnienia do zapisu.  
- **Nieoczekiwany rozmiar symbolu** – Sprawdź, czy nie nadpisałeś `EncodeMode` w innym miejscu kodu.  
- **Wyjątek licencyjny** – Wersja próbna dodaje znak wodny; zastosuj ważną licencję, aby go usunąć.

## Najczęściej zadawane pytania

**P: Jaki jest cel Aztec Symbol Mode w generowaniu kodów kreskowych?**  
O: Aztec Symbol Mode określa, w jaki sposób biblioteka układa dane w warstwy, wpływając na rozmiar, pojemność i czytelność.

**P: Czy mogę zmienić tekst kodu dla kodów Aztec w Aspose.BarCode dla .NET?**  
O: Tak, wystarczy przypisać nowy ciąg do właściwości `CodeText` przed wywołaniem `Save`.

**P: Czy dostępna jest darmowa wersja próbna Aspose.BarCode dla .NET?**  
O: Tak, darmową wersję próbną Aspose.BarCode dla .NET możesz pobrać [tutaj](https://releases.aspose.com/).

**P: Gdzie znajdę pełną dokumentację Aspose.BarCode dla .NET?**  
O: Pełną dokumentację Aspose.BarCode dla .NET znajdziesz [tutaj](https://reference.aspose.com/barcode/net/).

**P: Jak uzyskać tymczasową licencję dla Aspose.BarCode dla .NET?**  
O: Tymczasową licencję dla Aspose.BarCode dla .NET możesz uzyskać, odwiedzając [ten link](https://purchase.aspose.com/temporary-license/).

## Zakończenie

W tym samouczku omówiliśmy, jak **create aztec barcode .net** przy użyciu Aspose.BarCode, obejmując tryby Auto, FullRange, Compact i Rune. Masz teraz solidne podstawy, aby osadzać wszechstronne kody Aztec w dowolnej aplikacji .NET, niezależnie od tego, czy działa ona na komputerze stacjonarnym, serwerze internetowym czy w chmurze.

Jeśli masz pytania lub potrzebujesz dalszej pomocy, nie wahaj się skontaktować ze społecznością Aspose.BarCode na ich [forum wsparcia](https://forum.aspose.com/c/barcode/13).

---

**Ostatnia aktualizacja:** 2026-05-24  
**Testowano z:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Kodowanie tekstu Aztec przy użyciu Aspose.BarCode dla .NET](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)
- [Kodowanie bajtów Aztec przy użyciu generatora kodów kreskowych .net](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [Jak utworzyć kod Aztec z korekcją błędów w .NET](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}