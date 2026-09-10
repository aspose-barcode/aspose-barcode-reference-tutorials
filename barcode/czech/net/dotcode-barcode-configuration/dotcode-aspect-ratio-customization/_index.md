---
date: 2026-06-14
description: Zjistěte, jak vytvořit DotCode barcode .NET a přizpůsobit jeho aspect
  ratio pomocí Aspose.BarCode pro .NET.
keywords:
- create dotcode barcode .net
- dotcode aspect ratio
- aspose barcode .net
- barcode customization
- .net barcode generation
linktitle: DotCode Aspect Ratio Přizpůsobení
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to create DotCode barcode .NET and customize its aspect ratio
    using Aspose.BarCode for .NET.
  headline: Create DotCode Barcode .NET – Customize Aspect Ratio
  type: TechArticle
- description: Learn how to create DotCode barcode .NET and customize its aspect ratio
    using Aspose.BarCode for .NET.
  name: Create DotCode Barcode .NET – Customize Aspect Ratio
  steps:
  - name: '**Aspose.BarCode for .NET** – download the library from the official site [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – download the library from the official site [here](https://releases.aspose.com/barcode/net/).'
  - name: '**IDE** – Visual Studio, Rider, or any .NET‑compatible editor.'
    text: '**IDE** – Visual Studio, Rider, or any .NET‑compatible editor.'
  - name: '**Output folder** – replace “Your Directory Path” in the sample with a
      real folder on your machine.'
    text: '**Output folder** – replace “Your Directory Path” in the sample with a
      real folder on your machine.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode supports DotCode out‑of‑the‑box.
    question: Can I generate DotCode barcodes in .NET?
  - answer: The `AspectRatio` property of `BarcodeGenerator`.
    question: Which property controls the shape?
  - answer: A commercial license is required; a free trial works for development.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Supported .NET versions?
  - answer: Less than a second for a typical 200 × 200 pixel barcode.
    question: How long does the code take to run?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Vytvořte DotCode Barcode .NET – Přizpůsobte Aspect Ratio
url: /cs/net/dotcode-barcode-configuration/dotcode-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořte čárový kód DotCode .NET – Přizpůsobení poměru stran

Pokud potřebujete **vytvořit DotCode barcode .NET** řešení, která se vejdou do úzkých prostorů nebo splňují specifické požadavky na rozvržení, Aspose.BarCode pro .NET vám poskytuje plnou kontrolu. V tomto tutoriálu projdeme celý proces generování čárového kódu DotCode a úpravy jeho poměru stran, aby vypadal přesně tak, jak chcete na obalech, štítcích nebo mobilních obrazovkách.  

## Rychlé odpovědi
- **Mohu v .NET generovat čárové kódy DotCode?** Ano, Aspose.BarCode podporuje DotCode ihned.  
- **Která vlastnost řídí tvar?** Vlastnost `AspectRatio` třídy `BarcodeGenerator`.  
- **Potřebuji licenci pro produkci?** Je vyžadována komerční licence; bezplatná zkušební verze funguje pro vývoj.  
- **Podporované verze .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Jak dlouho kód běží?** Méně než sekunda pro typický 200 × 200 pixelový čárový kód.

## Jaký je hlavní cíl tohoto tutoriálu?
Tutoriál si klade za cíl ukázat, jak generovat čárový kód DotCode pomocí Aspose.BarCode pro .NET a jak upravit jeho poměr stran tak, aby vyhovoval konkrétním požadavkům na rozvržení. Po provedení kroků se naučíte konfigurovat generátor, měnit parametry velikosti a exportovat obrázek do běžných formátů.

## Jak vytvořit DotCode čárový kód v .NET?
Pro vytvoření DotCode čárového kódu v .NET vytvořte instanci `BarcodeGenerator` s `EncodeTypes.DotCode` a daty, která chcete zakódovat. Poté nastavte vlastnosti X‑Dimension a AspectRatio pro řízení velikosti a tvaru a nakonec zavolejte metodu `Save`, která zapíše obrázek do souboru ve požadovaném formátu.

## Požadavky

1. **Aspose.BarCode for .NET** – stáhněte knihovnu z oficiální stránky [here](https://releases.aspose.com/barcode/net/).  
2. **IDE** – Visual Studio, Rider nebo jakýkoli editor kompatibilní s .NET.  
3. **Výstupní složka** – nahraďte „Your Directory Path“ ve vzorku skutečnou složkou na vašem počítači.

## Importovat jmenné prostory

`Aspose.BarCode.Generation` poskytuje třídy potřebné k generování a konfiguraci čárových kódů v .NET.  
```csharp
using Aspose.BarCode.Generation;
```

## Krok 1: Inicializace generátoru čárových kódů

`BarcodeGenerator` je hlavní třída, která vytváří obrázek čárového kódu na základě zadané symbologie a dat.  
```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, "Aspose"))
{
    // Your code goes here
}
```

## Krok 2: Nastavení X‑Dimension (velikost) čárového kódu

`XDimension` určuje šířku jednoho modulu (tečky) v pixelech, což ovlivňuje celkovou velikost čárového kódu.  
```csharp
gen.Parameters.Barcode.XDimension.Pixels = 10;
```

## Krok 3: Přizpůsobení poměru stran

`AspectRatio` nastavuje poměr výšky k šířce každého modulu, což vám umožní vertikálně čárový kód roztáhnout nebo zkomprimovat.  
```csharp
gen.Parameters.Barcode.DotCode.AspectRatio = 0.5f;
```

## Krok 4: Uložení obrázku čárového kódu

`Save` zapíše vygenerovaný čárový kód do souboru ve zvoleném formátu obrázku, např. PNG nebo JPEG.  
```csharp
gen.Save($"{path}DotCodeAspectRatio0.5.png", BarCodeImageFormat.Png);
```

## Proč použít Aspose.BarCode pro přizpůsobení DotCode?
Aspose.BarCode poskytuje komplexní sadu funkcí pro generování DotCode, včetně výstupu ve vysokém rozlišení, široké podpory formátů a detailní kontroly rozměrů čárových kódů, jako je poměr stran. Běží na všech hlavních platformách .NET, nevyžaduje žádné externí závislosti a nabízí rychlý výkon renderování, což z něj činí ideální řešení pro desktopové i webové aplikace.

## Běžné případy použití

- **Zdravotnictví**: Kompaktní štítky s ID pacienta, které musí být umístěny na malé náramky.  
- **Poštovní služby**: Široké přepravní štítky, kde nižší výška zlepšuje spolehlivost skenování.  
- **Výroba**: Inline označování součástí, kde omezení prostoru vyžadují vlastní poměr stran.

## Často kladené otázky

**Q:** Jaký je poměr stran čárového kódu DotCode?  
**A:** Je to poměr výšky modulu k jeho šířce; úprava tohoto poměru mění celkový tvar čárového kódu.

**Q:** Která odvětví nejvíce těží z čárových kódů DotCode?  
**A:** Zdravotnictví, poštovní služby a výroba často používají DotCode pro kompaktní kódování dat s vysokou hustotou.

**Q:** Mohu pomocí Aspose.BarCode pro .NET přizpůsobit i jiné parametry DotCode?  
**A:** Rozhodně. Můžete měnit úroveň opravy chyb, barvy popředí/pozadí a dokonce vložit loga.

**Q:** Je Aspose.BarCode vhodný jak pro webové, tak pro desktopové .NET aplikace?  
**A:** Ano, knihovna funguje hladce v ASP.NET, WPF, WinForms i konzolových aplikacích.

**Q:** Kde najdu další dokumentaci a příklady?  
**A:** Podrobná reference API a ukázky kódu jsou k dispozici [here](https://reference.aspose.com/barcode/net/).

---

**Poslední aktualizace:** 2026-06-14  
**Testováno s:** Aspose.BarCode 24.12 pro .NET  
**Autor:** Aspose

## Související tutoriály

- [Rozšířená konfigurace textu kódu DotCode s Aspose.BarCode pro .NET](/barcode/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Konfigurace strukturovaného režimu připojení DotCode s Aspose.BarCode pro .NET](/barcode/net/dotcode-barcode-configuration/dotcode-structured-append-mode-configuration/)
- [Vytvořit obrázek čárového kódu DotCode – řádky a sloupce (Aspose.BarCode)](/barcode/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}