---
date: 2026-03-07
description: Dowiedz się, jak tworzyć jednowymiarowe kody kreskowe Databar zakodowane
  w standardzie GS1 w .NET przy użyciu Aspose.BarCode. Ten przewodnik pokazuje, jak
  ustawić GS1, skonfigurować generator kodów kreskowych i szybko generować kody kreskowe.
linktitle: One-Dimensional Databar GS1 Encoding
second_title: Aspose.BarCode .NET API
title: Utwórz jednowymiarowe kodowanie Databar GS1 przy użyciu Aspose.BarCode
url: /pl/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz jednowymiarowy kod Databar z kodowaniem GS1 przy użyciu Aspose.BarCode

W tym samouczku **utworzysz jednowymiarowe kody Databar**, które spełniają standard GS1, korzystając z biblioteki Aspose.BarCode dla .NET. Niezależnie od tego, czy potrzebujesz ścisłej walidacji GS1, czy bardziej elastycznego kodu kreskowego, przeprowadzimy Cię przez każdy krok — od instalacji biblioteki po obsługę wyjątków kodowania — abyś mógł generować niezawodne kody kreskowe w własnych aplikacjach.

## Szybkie odpowiedzi
- **Co oznacza „utwórz jednowymiarowy databar”?** Oznacza to generowanie liniowego (1‑D) kodu kreskowego z rodziny Databar, często używanego w handlu detalicznym i logistyce.  
- **Jak ustawić walidację GS1?** Ustaw `IsAllowOnlyGS1Encoding` na `true` w parametrach `DataBar`.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna wystarcza do rozwoju; licencja komercyjna jest wymagana w środowisku produkcyjnym.  
- **Jakie wersje .NET są obsługiwane?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Gdzie można pobrać bibliotekę?** Ze strony oficjalnej wersji Aspose (zobacz wymagania wstępne).

## Co to jest „utwórz jednowymiarowy databar”?
Jednowymiarowy Databar (znany także jako RSS) to kompaktowy, liniowy kod kreskowy, który może kodować dane liczbowe, daty lub ciągi AI (Application Identifier). W połączeniu z kodowaniem GS1 kod kreskowy stosuje globalnie rozpoznawaną strukturę danych, co czyni go idealnym rozwiązaniem dla handlu detalicznego, opieki zdrowotnej i łańcucha dostaw.

## Dlaczego warto używać Aspose.BarCode dla .NET?
Aspose.BarCode oferuje płynne API, pełne wsparcie GS1 oraz możliwość precyzyjnego dostosowania każdego wizualnego aspektu kodu kreskowego. Eliminując konieczność ręcznego kodowania niskiego poziomu, pozwala skupić się na logice biznesowej.

## Wymagania wstępne

1. **Aspose.BarCode for .NET** – pobierz i zainstaluj z [tutaj](https://releases.aspose.com/barcode/net/).  
2. **Ścieżka katalogu** – zamień `"Your Directory Path"` w przykładach na folder, w którym masz uprawnienia do zapisu.

## Importowanie przestrzeni nazw

Dodaj wymagane instrukcje `using` na początku pliku C#:

```csharp
using Aspose.BarCode;
using System;
```

## Krok 1: Inicjalizacja generatora kodów kreskowych

Utwórz instancję `BarcodeGenerator` i określ symbolikę Databar Expanded:

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## Krok 2: Jak ustawić GS1 – Generowanie kodu kreskowego z rygorystyczną walidacją GS1

Włącz kodowanie wyłącznie GS1, przypisz zgodny z GS1 tekst kodu i zapisz obraz:

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## Krok 3: Generowanie kodu kreskowego z Aspose – Kodowanie zmienne (bez sprawdzania GS1)

Jeśli potrzebujesz kodu kreskowego, który **nie** wymusza reguł GS1, wyłącz to sprawdzanie:

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## Krok 4: Sprawdzanie GS1 w generatorze kodów kreskowych – Obsługa wyjątku

Gdy `IsAllowOnlyGS1Encoding` jest ustawione na `true`, a tekst kodu nie jest zgodny z GS1, Aspose zgłasza wyjątek. Poniższy wzorzec pokazuje, jak go przechwycić i zalogować:

```csharp
try
{
    gen.CodeText = "ASPOSE";
    gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### Częste pułapki i wskazówki
- **Pułapka:** Podanie ciągu nie‑GS1 przy włączonym sprawdzaniu GS1 spowoduje przerwanie generowania kodu kreskowego.  
- **Pro tip:** Zweryfikuj ciągi AI przed przypisaniem ich do `CodeText`, aby uniknąć błędów w czasie wykonywania.  
- **Wskazówka:** Używaj ścieżek bezwzględnych lub `Path.Combine`, aby bezpiecznie budować nazwy plików na różnych platformach.

## Podsumowanie

Teraz wiesz, jak **utworzyć jednowymiarowy kod Databar** z kodowaniem GS1, jak przełączać sprawdzanie GS1 oraz jak obsługiwać powiązane wyjątki — wszystko przy użyciu Aspose.BarCode dla .NET. Zachęcamy do eksploracji dodatkowych opcji stylizacji, takich jak rozmiar kodu, kolor i marginesy, poprzez obiekt `Parameters.Barcode`.

Jeśli napotkasz problemy, oficjalna dokumentacja i forum społeczności są doskonałymi źródłami pomocy:

- [Dokumentacja Aspose.BarCode](https://reference.aspose.com/barcode/net/)  
- [Forum wsparcia Aspose.BarCode](https://forum.aspose.com/c/barcode/13)

## Najczęściej zadawane pytania

### 1. Czym jest kodowanie GS1 w kodach kreskowych?
Kodowanie GS1 to ustandaryzowany sposób strukturyzacji danych (np. identyfikatorów produktów) wewnątrz kodu kreskowego, zapewniający interoperacyjność między detalistami, producentami i dostawcami logistycznymi.

### 2. Czy mogę dostosować wygląd generowanych kodów kreskowych?
Tak. Aspose.BarCode umożliwia regulację rozmiaru, kolorów, marginesów oraz dodanie tekstu czytelnego dla człowieka poprzez ustawienia `Parameters.Barcode`.

### 3. Gdzie mogę znaleźć dodatkowe zasoby i dokumentację dla Aspose.BarCode?
Kompletną dokumentację i przykłady znajdziesz pod adresem [Dokumentacja Aspose.BarCode](https://reference.aspose.com/barcode/net/). To cenne źródło wiedzy i rozwiązywania problemów.

### 4. Czy dostępna jest wersja próbna Aspose.BarCode?
Tak, darmową wersję próbną Aspose.BarCode dla .NET można pobrać [tutaj](https://releases.aspose.com/).

### 5. Jak mogę zakupić licencję na Aspose.BarCode dla .NET?
Aby zakupić licencję na Aspose.BarCode dla .NET, odwiedź [stronę zakupu](https://purchase.aspose.com/buy) na witrynie Aspose.

---

**Ostatnia aktualizacja:** 2026-03-07  
**Testowano z:** Aspose.BarCode 24.11 dla .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}