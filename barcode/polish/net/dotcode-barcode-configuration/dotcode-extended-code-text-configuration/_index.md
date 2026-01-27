---
date: 2026-01-27
description: Dowiedz się, jak tworzyć rozszerzony tekst kodu DotCode przy użyciu Aspose.BarCode
  dla .NET – krok po kroku przewodnik po generowaniu kodów kreskowych DotCode z rozszerzonym
  tekstem kodu.
linktitle: DotCode Extended Code Text Configuration
second_title: Aspose.BarCode .NET API
title: Jak utworzyć rozszerzony kod tekstowy dotcode przy użyciu Aspose.BarCode dla
  .NET
url: /pl/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć rozszerzony kod tekstowy dotcode przy użyciu Aspose.BarCode dla .NET

## Wprowadzenie

W dziedzinie generowania i zarządzania kodami kreskowymi Aspose.BarCode dla .NET wyróżnia się jako wszechstronne i wydajne rozwiązanie. Niezależnie od tego, czy potrzebujesz generować kody kreskowe dla produktów, zapasów czy innej aplikacji, Aspose.BarCode dla .NET ma Cię w pełni zabezpieczony. W tym obszernej tutorialu **utworzymy rozszerzony kod tekstowy dotcode** i wyjaśnimy, dlaczego ta funkcja jest niezbędna w nowoczesnych środowiskach bogatych w dane. DotCode to dwuwymiarowy kod macierzowy, który może kodować zarówno dane tekstowe, jak i binarne, co czyni go cennym narzędziem w różnych branżach.

## Szybkie odpowiedzi
- **Co oznacza „utworzyć rozszerzony kod tekstowy dotcode”?** Oznacza to zbudowanie kodu kreskowego DotCode, który zawiera FNC1, ECICodetext, zwykły tekst oraz separatory symboli w jednym rozszerzonym ładunku.  
- **Jakiej biblioteki potrzebujesz?** Aspose.BarCode dla .NET.  
- **Czy potrzebna jest licencja?** Tymczasowa licencja wystarczy do oceny; pełna licencja jest wymagana w produkcji.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Jak długo trwa implementacja?** Około 10‑15 minut dla podstawowego przykładu.

## Jak utworzyć rozszerzony kod tekstowy dotcode

Poniżej znajduje się zwięzły, krok po kroku przewodnik, który pokazuje dokładnie, jak zbudować rozszerzony kod tekstowy i wygenerować obraz kodu kreskowego.

## Wymagania wstępne

Zanim przejdziemy do szczegółowego przewodnika, musisz spełnić kilka wymagań, aby móc skutecznie podążać za instrukcjami:

1. Aspose.BarCode dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.BarCode dla .NET. Jeśli nie, możesz ją pobrać z [dokumentacji Aspose.BarCode dla .NET](https://reference.aspose.com/barcode/net/).

2. Środowisko programistyczne: Powinno być zainstalowane działające środowisko .NET, najlepiej Visual Studio.

Mając te elementy na miejscu, możemy przystąpić do generowania rozszerzonego kodu tekstowego DotCode.

## Importowanie przestrzeni nazw

Najpierw musisz zaimportować niezbędne przestrzenie nazw do swojego projektu .NET, aby uzyskać dostęp do funkcji biblioteki Aspose.BarCode. Oto jak to zrobić:

```csharp
using Aspose.BarCode.Generation;
```

Teraz, gdy spełniliśmy wymagania wstępne, przejdźmy do szczegółowego podziału procesu generowania rozszerzonego kodu tekstowego DotCode.

## Krok 1: Definiowanie ścieżki katalogu

W tym kroku musisz określić ścieżkę katalogu, w którym chcesz zapisać wygenerowany obraz rozszerzonego kodu tekstowego DotCode.

```csharp
string path = "Your Directory Path";
```

Zastąp `"Your Directory Path"` rzeczywistą ścieżką w swoim systemie.

## Krok 2: Utworzenie rozszerzonego kodu tekstowego DotCode

Aby utworzyć rozszerzony kod tekstowy DotCode, wykonaj następujące podkroki:

### 2.1 Dodaj identyfikator formatu FNC1

Identyfikator formatu FNC1 służy do wskazania początku nowego pola danych. Jest on niezbędnym elementem rozszerzonego kodu tekstowego DotCode.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 Dodaj ECICodetext

ECICodetext pozwala kodować znaki specjalne i tekst międzynarodowy. W tym przykładzie zakodowaliśmy `"犬Right狗"` przy użyciu kodowania UTF‑8.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 Dodaj zwykły kod tekstowy

Możesz również dodać zwykły tekst do rozszerzonego kodu tekstowego DotCode. Tutaj dodaliśmy `"Plain text"`.

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 Dodaj separator symboli FNC3

Separator symboli FNC3 służy do oddzielenia różnych sekcji kodu.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 Dodaj inicjalizację czytnika FNC3

Ten krok dodaje informacje o inicjalizacji czytnika FNC3.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 Wygeneruj kod tekstowy

Teraz wygeneruj rozszerzony kod tekstowy DotCode, wywołując metodę `GetExtendedCodetext` na obiekcie `textBuilder`.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## Krok 3: Generowanie obrazu DotCode

Aby wygenerować rozszerzony kod tekstowy DotCode jako obraz, wykonaj następujące podkroki:

#### 4.1 Inicjalizacja generatora kodów kreskowych

Zainicjalizuj `BarcodeGenerator` z odpowiednimi parametrami. W tym przypadku używamy `EncodeTypes.DotCode` oraz wygenerowanego kodu tekstowego.

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

I to wszystko! Pomyślnie wygenerowałeś rozszerzony kod tekstowy DotCode przy użyciu Aspose.BarCode dla .NET.

## Zakończenie

Aspose.BarCode dla .NET to potężne narzędzie upraszczające generowanie kodów kreskowych. W tym tutorialu skupiliśmy się na **tworzeniu rozszerzonego kodu tekstowego dotcode**, co jest kluczowe w różnych branżach, szczególnie tam, gdzie wymagana jest wielojęzyczna i specjalistyczna enkodacja znaków. Postępując zgodnie z opisanymi krokami, możesz łatwo utworzyć rozszerzony kod tekstowy DotCode dopasowany do Twoich potrzeb.

Jeśli potrzebujesz dalszych wskazówek lub masz pytania, odwiedź [dokumentację Aspose.BarCode dla .NET](https://reference.aspose.com/barcode/net/) lub dołącz do społeczności na [forum wsparcia Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

## FAQ

### Q1: Do czego służy DotCode?

A1: DotCode służy do kodowania zarówno danych tekstowych, jak i binarnych i jest powszechnie stosowany w branżach takich jak opieka zdrowotna i logistyka do śledzenia oraz kodowania danych.

### Q2: Czy mogę dostosować wygląd kodów kreskowych DotCode?

A2: Tak, Aspose.BarCode dla .NET oferuje opcje dostosowywania wyglądu kodów kreskowych DotCode, w tym rozmiar i tryb kodowania.

### Q3: Czy Aspose.BarCode dla .NET jest kompatybilny z różnymi frameworkami .NET?

A3: Tak, Aspose.BarCode dla .NET jest kompatybilny z szeroką gamą frameworków .NET, zapewniając elastyczność i łatwość integracji.

### Q4: Jak uzyskać tymczasową licencję dla Aspose.BarCode dla .NET?

A4: Tymczasową licencję możesz uzyskać ze [strony Aspose](https://purchase.aspose.com/temporary-license/) w celu oceny i testów.

### Q5: Czy Aspose.BarCode dla .NET nadaje się do generowania kodów kreskowych na poziomie przedsiębiorstwa?

A5: Absolutnie, Aspose.BarCode dla .NET jest zaprojektowany tak, aby sprostać potrzebom zarówno małych, jak i dużych przedsiębiorstw, oferując skalowalność i niezawodność.

## Najczęściej zadawane pytania

**Q: Czy mogę używać wygenerowanego kodu kreskowego w aplikacji mobilnej?**  
A: Tak. Obraz PNG wygenerowany przez generator może być osadzony w iOS, Androidzie lub dowolnej aplikacji mobilnej wieloplatformowej.

**Q: Co zrobić, jeśli muszę zakodować dane binarne zamiast tekstu?**  
A: Użyj metody `AddECICodetext` z odpowiednim `ECIEncodings` (np. `ECIEncodings.Base64`), aby osadzić ładunek binarny.

**Q: Jak zmienić rozmiar kodu kreskowego bez utraty czytelności?**  
A: Dostosuj właściwość `XDimension.Pixels`; wyższe wartości zwiększają rozmiar modułu, niższe czynią kod bardziej zwartym.

**Q: Czy można dodać strefę ciszy wokół kodu kreskowego?**  
A: Tak. Ustaw `gen.Parameters.Barcode.Margin`, aby określić pożądaną strefę ciszy w pikselach.

**Q: Czy biblioteka obsługuje .NET 8?**  
A: Najnowsze wydania Aspose.BarCode są kompatybilne z .NET 8; wystarczy odwołać się do odpowiedniej wersji pakietu NuGet.

---

**Ostatnia aktualizacja:** 2026-01-27  
**Testowano z:** Aspose.BarCode 24.12 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}