---
date: 2026-03-02
description: Dowiedz się, jak generować kod kreskowy przy użyciu Aspose.BarCode dla
  .NET, w tym wskazówki dotyczące generowania kodów kreskowych w Visual Studio, w
  tym przewodniku krok po kroku dotyczącym konfiguracji stosunku szerokiego do wąskiego.
linktitle: One-Dimensional Wide-Narrow Ratio Configuration
second_title: Aspose.BarCode .NET API
title: Jak wygenerować kod kreskowy – konfiguracja stosunku szerokiego do wąskiego
url: /pl/net/one-dimensional-barcode-types/one-dimensional-wide-narrow-ratio-configuration/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfiguracja stosunku szeroki‑wąski w jednowymiarowych kodach kreskowych

Czy szukasz sposobu **jak generować kod kreskowy** bez wysiłku w swoich aplikacjach .NET? Aspose.BarCode for .NET ułatwia generowanie kodów kreskowych w projektach Visual Studio, czyniąc je prostymi i potężnymi. W tym samouczku przeprowadzimy Cię przez tworzenie jednowymiarowych kodów kreskowych z niestandardowym stosunkiem szeroki‑wąski, wyjaśnimy, dlaczego stosunek ma znaczenie, i pokażemy, jak dostosować go do różnych środowisk skanowania.

## Szybkie odpowiedzi
- **Co kontroluje stosunek szeroki‑wąski?** Określa względną szerokość „szerokich” pasków w stosunku do „wąskich” w jednowymiarowym kodzie kreskowym.  
- **Jakiego typu kod kreskowy jest użyty w przykładzie?** Code 39 Extended, popularna symbologia dla danych alfanumerycznych.  
- **Czy mogę zmienić stosunek w czasie działania?** Tak – wystarczy ustawić `gen.Parameters.Barcode.WideNarrowRatio` na żądaną wartość przed zapisaniem.  
- **Czy potrzebna jest licencja do tej funkcji?** Stosunek szeroki‑wąski działa w wersji próbnej; pełna licencja odblokowuje wszystkie opcje renderowania.  
- **Czy jest to kompatybilne z .NET Core?** Absolutnie – Aspose.BarCode obsługuje .NET Framework, .NET Core oraz .NET 5/6+.

## Co to jest stosunek szeroki‑wąski?
W jednowymiarowych kodach kreskowych każdy pasek jest albo „szeroki”, albo „wąski”. Stosunek (np. 2 lub 5) określa, ile razy szeroki pasek jest szerszy od wąskiego. Dostosowanie tego stosunku może poprawić czytelność na drukarkach lub skanerach o niskiej rozdzielczości.

## Dlaczego warto używać Aspose.BarCode dla .NET?
* **Pełna kontrola** – Każdy aspekt wizualny, w tym stosunek szeroki‑wąski, można ustawić programowo.  
* **Cross‑platform** – Działa w Visual Studio, Visual Studio Code i na dowolnym środowisku .NET.  
* **Brak zewnętrznych zależności** – Nie wymaga natywnych plików DLL ani narzędzi firm trzecich.  
* **Bogata dokumentacja i wsparcie** – Zawiera przykłady, fora oraz przewodniki szybkiego startu.

## Wymagania wstępne

Zanim zanurkujemy w świat kodów kreskowych z Aspose.BarCode for .NET, musisz spełnić następujące wymagania:

### 1. Środowisko Visual Studio
   - Upewnij się, że masz zainstalowane Visual Studio, aby pracować z aplikacjami .NET.

### 2. Biblioteka Aspose.BarCode for .NET
   - Musisz mieć zainstalowaną bibliotekę Aspose.BarCode for .NET. Możesz ją pobrać ze [strony internetowej](https://releases.aspose.com/barcode/net/).

### 3. Klucz licencyjny (opcjonalnie)
   - Jeśli posiadasz klucz licencyjny, możesz go użyć do odblokowania dodatkowych funkcji biblioteki. Tymczasową licencję możesz uzyskać [tutaj](https://purchase.aspose.com/temporary-license/).

Teraz, gdy masz już spełnione wymagania, przejdźmy do tworzenia jednowymiarowych kodów kreskowych z konfiguracją stosunku szeroki‑wąski przy użyciu Aspose.BarCode for .NET.

## Importowanie przestrzeni nazw

Najpierw musisz dodać niezbędne przestrzenie nazw do swojego projektu, aby uzyskać dostęp do funkcji Aspose.BarCode for .NET. Możesz to zrobić, dodając następujące instrukcje using na początku swojego kodu:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Krok 1: Zdefiniuj ścieżkę katalogu

Rozpocznij od określenia ścieżki, w której chcesz zapisać wygenerowane obrazy kodów kreskowych. Możesz to zrobić przy pomocy poniższego kodu:

```csharp
string path = "Your Directory Path";
```

Zastąp `"Your Directory Path"` rzeczywistą ścieżką katalogu, w którym chcesz zapisywać obrazy kodów kreskowych.

## Krok 2: Utwórz jednowymiarowy kod kreskowy z konfiguracją stosunku szeroki‑wąski

Teraz utwórzmy jednowymiarowy kod kreskowy z konfiguracją stosunku szeroki‑wąski przy użyciu Aspose.BarCode for .NET. W tym przykładzie użyjemy typu kodowania Code39Extended i ustawimy dane na `"ASPOSE"`:

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code39Extended, "ASPOSE");
```

Ten wiersz kodu inicjalizuje generator kodów kreskowych z określonym typem kodowania i danymi.

## Krok 3: Ustaw stosunek szeroki‑wąski

Stosunek szeroki‑wąski określa proporcję między szerokimi a wąskimi elementami w kodzie kreskowym. W tym kroku ustawimy stosunek szeroki‑wąski na **2**:

```csharp
gen.Parameters.Barcode.WideNarrowRatio = 2;
```

A następnie zapiszemy wygenerowany obraz kodu kreskowego w określonej ścieżce:

```csharp
gen.Save($"{path}WideNarrow2Code39.png", BarCodeImageFormat.Png);
```

## Krok 4: Dostosuj stosunek szeroki‑wąski

Możesz eksperymentować z różnymi stosunkami szeroki‑wąski, aby uzyskać pożądany wygląd kodu kreskowego. Na przykład, jeśli chcesz szerszy kod, ustaw stosunek szeroki‑wąski na **5**:

```csharp
gen.Parameters.Barcode.WideNarrowRatio = 5;
```

I zapisz obraz kodu kreskowego:

```csharp
gen.Save($"{path}WideNarrow5Code39.png", BarCodeImageFormat.Png);
```

Teraz pomyślnie utworzyłeś jednowymiarowe kody kreskowe z różnymi stosunkami szeroki‑wąski przy użyciu Aspose.BarCode for .NET. Biblioteka ta zapewnia elastyczność w generowaniu kodów dostosowanych do Twoich konkretnych wymagań.

## Typowe problemy i rozwiązania
- **Obraz nie został zapisany** – Sprawdź, czy zmienna `path` wskazuje istniejący folder i czy aplikacja ma uprawnienia do zapisu.  
- **Kod kreskowy wygląda na zniekształcony** – Spróbuj niższego stosunku (np. 2) dla drukarek o niskiej rozdzielczości; wyższe stosunki mogą powodować artefakty drukowania.  
- **Nieobsługiwane znaki** – Code 39 Extended obsługuje pełny zestaw ASCII; upewnij się, że ciąg danych nie zawiera zakazanych znaków kontrolnych.

## Podsumowanie

Aspose.BarCode for .NET to wszechstronna biblioteka, która upraszcza generowanie i dostosowywanie kodów kreskowych w Twoich aplikacjach .NET. W tym samouczku omówiliśmy podstawy tworzenia jednowymiarowych kodów kreskowych z konfiguracją stosunku szeroki‑wąski. Dzięki możliwości precyzyjnego dostrajania różnych parametrów możesz tworzyć kody idealnie dopasowane do Twoich potrzeb, niezależnie od tego, czy budujesz funkcję **jak generować kod kreskowy** w aplikacji desktopowej, czy usługę **generowania kodów kreskowych w Visual Studio**.

## Najczęściej zadawane pytania

### 1. Jak mogę uzyskać licencję na Aspose.BarCode for .NET?
Możesz zakupić licencję na [stronie Aspose](https://purchase.aspose.com/buy).

### 2. Czy mogę używać Aspose.BarCode for .NET bez licencji?
Tak, możesz korzystać z wersji tymczasowej licencji, która zapewnia ograniczoną funkcjonalność.

### 3. Czy Aspose.BarCode for .NET jest kompatybilny z .NET Core?
Tak, Aspose.BarCode for .NET jest kompatybilny z .NET Core oraz .NET Framework.

### 4. Czy istnieją ograniczenia dotyczące typów kodów kreskowych, które mogę generować?
Aspose.BarCode for .NET obsługuje szeroką gamę symbologii kodów kreskowych, w tym QR Code, Code 39 i wiele innych.

### 5. Jak mogę uzyskać wsparcie lub zadać pytania dotyczące Aspose.BarCode for .NET?
Możesz odwiedzić [forum Aspose.BarCode](https://forum.aspose.com/c/barcode/13), aby uzyskać wsparcie i dyskusje.

### Dodatkowe pytania i odpowiedzi

**P: Czy zmiana stosunku szeroki‑wąski wpływa na szybkość skanowania?**  
O: Wyższy stosunek może sprawić, że paski będą grubsze, co może poprawić czytelność na słabej jakości skanerach, ale może nieco zwiększyć ilość danych przetwarzanych przez skaner.

**P: Czy mogę ustawić stosunek dla innych symbologii, takich jak Code128?**  
O: Tak, właściwość `WideNarrowRatio` ma zastosowanie do wszystkich jednowymiarowych symbologii, które obsługują elementy szerokie i wąskie.

---

**Ostatnia aktualizacja:** 2026-03-02  
**Testowane z:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}