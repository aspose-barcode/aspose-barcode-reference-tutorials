---
date: 2026-03-02
description: Naučte se, jak generovat čárový kód pomocí Aspose.BarCode pro .NET, včetně
  tipů pro generování čárových kódů ve Visual Studiu, v tomto krok‑za‑krokem průvodci
  konfigurací poměru široký‑úzký.
linktitle: One-Dimensional Wide-Narrow Ratio Configuration
second_title: Aspose.BarCode .NET API
title: Jak generovat čárový kód – konfigurace poměru široké a úzké
url: /cs/net/one-dimensional-barcode-types/one-dimensional-wide-narrow-ratio-configuration/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfigurace poměru široko‑úzký u jednorozměrných čárových kódů

Hledáte **how to generate barcode** snadno ve svých .NET aplikacích? Aspose.BarCode pro .NET usnadňuje generování čárových kódů ve Visual Studio projektech a je výkonný. V tomto tutoriálu vás provedeme tvorbou jednorozměrných čárových kódů s vlastním poměrem široko‑úzký, vysvětlíme, proč je poměr důležitý, a ukážeme, jak jej upravit pro různé skenovací prostředí.

## Rychlé odpovědi
- **What does the wide‑narrow ratio control?** Definuje relativní šířku „širokých“ pruhů oproti „úzkým“ pruhům v 1D čárovém kódu.  
- **Which barcode type is used in the example?** Code 39 Extended, populární symbologie pro alfanumerická data.  
- **Can I change the ratio at runtime?** Ano – stačí nastavit `gen.Parameters.Barcode.WideNarrowRatio` na požadovanou hodnotu před uložením.  
- **Do I need a license for this feature?** Poměr široko‑úzký funguje ve free trial; plná licence odemkne všechny možnosti vykreslování.  
- **Is this compatible with .NET Core?** Naprosto – Aspose.BarCode podporuje .NET Framework, .NET Core i .NET 5/6+.

## Co je poměr široko‑úzký?

V jednorozměrných čárových kódech je každý pruh buď „široký“, nebo „úzký“. Poměr (např. 2 nebo 5) určuje, kolikrát je široký pruh širší než úzký pruh. Úprava tohoto poměru může zlepšit čitelnost na tiskárnách nebo skenerech s nízkým rozlišením.

## Proč používat Aspose.BarCode pro .NET?

* **Full control** – Každý vizuální aspekt, včetně poměru široko‑úzký, lze nastavit programově.  
* **Cross‑platform** – Funguje ve Visual Studio, Visual Studio Code a na jakémkoli .NET runtime.  
* **No external dependencies** – Není potřeba žádné nativní DLL ani nástroje třetích stran.  
* **Rich documentation and support** – Obsahuje příklady, fóra a průvodce pro rychlý start.

## Předpoklady

Než se ponoříme do světa čárových kódů s Aspose.BarCode pro .NET, musíte mít připravené následující předpoklady:

### 1. Prostředí Visual Studio
- Ujistěte se, že máte na svém systému nainstalované Visual Studio pro práci s .NET aplikacemi.

### 2. Knihovna Aspose.BarCode pro .NET
- Musíte mít nainstalovanou knihovnu Aspose.BarCode pro .NET. Můžete si ji stáhnout z [website](https://releases.aspose.com/barcode/net/).

### 3. Licenční klíč (volitelné)
- Pokud máte licenční klíč, můžete jej použít k odemknutí dalších funkcí knihovny. Dočasnou licenci můžete získat [here](https://purchase.aspose.com/temporary-license/).

Nyní, když máte předpoklady připravené, pojďme se pustit do tvorby jednorozměrných čárových kódů s konfigurací poměru široko‑úzký pomocí Aspose.BarCode pro .NET.

## Importujte jmenné prostory

Nejprve musíte do svého projektu zahrnout potřebné jmenné prostory, abyste získali přístup k funkcím Aspose.BarCode pro .NET. To můžete provést přidáním následujících using direktiv na začátek svého kódu:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Krok 1: Definujte cestu k adresáři

Začněte definováním cesty, kam chcete ukládat vygenerované obrázky čárových kódů. Můžete to provést následujícím kódem:

```csharp
string path = "Your Directory Path";
```

Nahraďte `"Your Directory Path"` skutečnou cestou k adresáři, kam chcete ukládat obrázky čárových kódů.

## Krok 2: Vytvořte jednorozměrný čárový kód s poměrem široko‑úzký

Nyní vytvoříme jednorozměrný čárový kód s konfigurací poměru široko‑úzký pomocí Aspose.BarCode pro .NET. V tomto příkladu použijeme typ kódování Code39Extended a nastavíme data na `"ASPOSE"`:

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code39Extended, "ASPOSE");
```

Tento řádek kódu inicializuje generátor čárových kódů se zadaným typem kódování a daty.

## Krok 3: Nastavte poměr široko‑úzký

Poměr široko‑úzký určuje poměr mezi širokými a úzkými prvky v čárovém kódu. V tomto kroku nastavíme poměr široko‑úzký na **2**:

```csharp
gen.Parameters.Barcode.WideNarrowRatio = 2;
```

A poté uložíme vygenerovaný obrázek čárového kódu na zadanou cestu:

```csharp
gen.Save($"{path}WideNarrow2Code39.png", BarCodeImageFormat.Png);
```

## Krok 4: Upravit poměr široko‑úzký

Můžete experimentovat s různými poměry široko‑úzký, abyste dosáhli požadovaného vzhledu čárového kódu. Například pokud chcete širší čárový kód, nastavte poměr široko‑úzký na **5**:

```csharp
gen.Parameters.Barcode.WideNarrowRatio = 5;
```

A uložte obrázek čárového kódu:

```csharp
gen.Save($"{path}WideNarrow5Code39.png", BarCodeImageFormat.Png);
```

Nyní jste úspěšně vytvořili jednorozměrné čárové kódy s různými poměry široko‑úzký pomocí Aspose.BarCode pro .NET. Tato knihovna vám poskytuje flexibilitu generovat čárové kódy přizpůsobené vašim konkrétním požadavkům.

## Časté problémy a řešení
- **Image not saved** – Ověřte, že proměnná `path` ukazuje na existující složku a že má vaše aplikace oprávnění k zápisu.  
- **Barcode appears distorted** – Zkuste nižší poměr (např. 2) pro tiskárny s nízkým rozlišením; vyšší poměry mohou způsobovat artefakty při tisku.  
- **Unsupported characters** – Code 39 Extended podporuje celý ASCII set; ujistěte se, že váš řetězec dat neobsahuje zakázané řídicí znaky.

## Závěr

Aspose.BarCode pro .NET je univerzální knihovna, která zjednodušuje generování a přizpůsobení čárových kódů ve vašich .NET aplikacích. V tomto tutoriálu jsme pokryli základy tvorby jednorozměrných čárových kódů s konfigurací poměru široko‑úzký. Díky možnosti jemně ladit různé parametry můžete vytvářet čárové kódy, které dokonale vyhovují vašim potřebám, ať už vytváříte funkci **how to generate barcode** v desktopové aplikaci nebo službu **barcode generation visual studio**.

## Často kladené otázky

### 1. Jak mohu získat licenci pro Aspose.BarCode pro .NET?
Můžete zakoupit licenci na [Aspose website](https://purchase.aspose.com/buy).

### 2. Mohu používat Aspose.BarCode pro .NET bez licence?
Ano, můžete jej používat s dočasnou licencí, která poskytuje omezenou funkčnost.

### 3. Je Aspose.BarCode pro .NET kompatibilní s .NET Core?
Ano, Aspose.BarCode pro .NET je kompatibilní s .NET Core i .NET Framework.

### 4. Existují omezení typů čárových kódů, které mohu generovat?
Aspose.BarCode pro .NET podporuje širokou škálu symbologií čárových kódů, včetně QR Code, Code 39 a mnoha dalších.

### 5. Jak mohu získat podporu nebo položit otázky ohledně Aspose.BarCode pro .NET?
Můžete navštívit [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) pro podporu a diskuse.

### Additional Q&A

**Q: Ovlivňuje změna poměru široko‑úzký rychlost skenování?**  
A: Vyšší poměr může udělat pruhy silnější, což může zlepšit čitelnost na nízkokvalitních skenerech, ale může mírně zvýšit množství dat, která skener zpracovává.

**Q: Mohu nastavit poměr i pro jiné symbologie jako Code128?**  
A: Ano, vlastnost `WideNarrowRatio` se vztahuje na všechny 1D symbologie, které podporují široké a úzké prvky.

**Last Updated:** 2026-03-02  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}