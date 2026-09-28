---
date: 2026-09-28
description: Zjistěte, jak vytvořit vlastní prostor čárového kódu pro GS1 kupóny pomocí
  Aspose.BarCode pro .NET a zvýšit čitelnost čárových kódů. Postupujte podle našeho
  podrobného průvodce krok za krokem.
keywords:
- create barcode custom space
- GS1 coupon supplement
- Aspose.BarCode .NET
- increase barcode readability
lastmod: 2026-09-28
linktitle: Konfigurace prostoru doplňku GS1 kupónu
og_description: Zjistěte, jak vytvořit vlastní prostor čárového kódu pro GS1 kupóny
  pomocí Aspose.BarCode pro .NET a zvýšit čitelnost čárových kódů. Obsahuje krok‑za‑krokem
  kód a tipy.
og_image_alt: Screenshot of a GS1 coupon barcode generated with custom supplement
  space using Aspose.BarCode for .NET
og_title: Vytvořte vlastní prostor čárového kódu pro doplněk GS1 kupónu – Aspose.BarCode
  .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  headline: How to create barcode custom space for GS1 coupon supplement
  type: TechArticle
- description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  name: How to create barcode custom space for GS1 coupon supplement
  steps:
  - name: '**Visual Studio** – The primary IDE for .NET development.'
    text: '**Visual Studio** – The primary IDE for .NET development.'
  - name: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
  - name: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
    text: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
  - name: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
    text: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
  - name: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
    text: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
  - name: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
    text: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
  type: HowTo
- questions:
  - answer: It adds a mandatory blank margin around the supplemental data, improving
      scanner reliability and meeting retailer‑specified minimum widths.
    question: What is the purpose of the GS1 Coupon Supplement Space in barcodes?
  - answer: Yes, set `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` to any
      integer value; the library instantly applies the change to the generated image.
    question: Can I customize the width of the GS1 Coupon Supplement Space with Aspose.BarCode
      for .NET?
  - answer: Refer to the [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)
      and visit the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)
      for community assistance.
    question: Where can I find additional documentation and support for Aspose.BarCode
      for .NET?
  - answer: Absolutely. The API offers straightforward methods for quick tasks and
      advanced options for fine‑tuned barcode generation.
    question: Is Aspose.BarCode for .NET suitable for both beginners and experienced
      developers?
  - answer: Yes, request a trial license from the [Aspose temporary license website](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for Aspose.BarCode for .NET to evaluate
      its features?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- barcode configuration
- GS1 standards
- Aspose.BarCode
- .NET barcode generation
title: Jak vytvořit vlastní prostor čárového kódu pro doplněk GS1 kupónu
url: /cs/net/gs1-barcode-encoding/gs1-coupon-supplement-space-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konfigurace doplňkového prostoru GS1 kupónu

V tomto tutoriálu **vytvoříte vlastní prostor čárového kódu** pro doplňkový prostor GS1 kupónu pomocí Aspose.BarCode pro .NET. Úprava doplňkového prostoru je nezbytná, když potřebujete **zvýšit čitelnost čárového kódu** na skenerů s nízkým rozlišením nebo splnit požadavky na okraje stanovené prodejci. Na konci tohoto průvodce pochopíte, proč je doplňkový prostor důležitý, jak jej nastavit programově a jak generovat obrázky s různými hodnotami pixelů.

## Rychlé odpovědi
- **Co řídí doplňkový prostor?** Definuje prázdnou oblast (v pixelech) mezi daty kupónu a zbytkem čárového kódu.  
- **Jaký typ čárového kódu se používá?** `EncodeTypes.UpcaGs1DatabarCoupon`.  
- **Mohu změnit velikost prostoru?** Ano – nastavte `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` na libovolnou celočíselnou hodnotu.  
- **Potřebuji licenci pro tuto funkci?** Dočasná licence funguje pro hodnocení; plná licence je vyžadována pro produkci.  
- **Jaké výstupní formáty jsou podporovány?** PNG, JPEG, BMP, GIF, TIFF a další přes `BarCodeImageFormat`.

## Co je doplňkový prostor GS1 kupónu?
Doplňkový prostor GS1 kupónu je definovaná prázdná oblast, která se objevuje v čárových kódech GS1‑Databar kupónů. Maloobchodní systémy tento prostor používají ke zlepšení spolehlivosti skenování a k dodržení průmyslových specifikací, které vyžadují minimální okraj kolem doplňkových dat.

## Proč konfigurovat doplňkový prostor?
Doplňkový prostor přímo **zvyšuje čitelnost čárového kódu** a pomáhá vám splnit přísné pokyny prodejců. Přidáním dalších pixelů snižujete pravděpodobnost chybného čtení na skenerech s nízkým rozlišením, zajišťujete konzistentní skenování napříč různými velikostmi štítků a získáváte vizuální flexibilitu pro vyvážení čárového kódu v tištěném rozvržení.

## Požadavky

Než se pustíme do konfigurace doplňkového prostoru GS1 kupónu pomocí Aspose.BarCode pro .NET, ujistěte se, že máte následující:

1. **Visual Studio** – Hlavní IDE pro vývoj v .NET.  
2. **Aspose.BarCode for .NET** – Stáhněte knihovnu z [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).  
3. **.NET Framework nebo .NET 5+** – Je vyžadována znalost C# a .NET runtime.

Nyní, když je prostředí připravené, přejděme k implementaci.

## Importujte jmenné prostory

`Aspose.BarCode.Generation` jmenný prostor obsahuje třídu `BarcodeGenerator` a související nastavení.

```csharp
using Aspose.BarCode;
```

## Krok 1: definujte cestu

Vyberte složku, do které budou ukládány generované obrázky. Cesta musí končit příslušným oddělovačem adresářů pro váš operační systém.

```csharp
string path = "Your Directory Path";
```

## Krok 2: vygenerujte konfiguraci doplňkového prostoru GS1 kupónu

Následující úryvek vytvoří čárový kód, nastaví X‑rozměr a upraví doplňkový prostor.

```csharp
System.Console.WriteLine("Gs1CouponSupplementSpace:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.UpcaGs1DatabarCoupon, "123456789012(8110)ASPOSE");
gen.Parameters.Barcode.XDimension.Pixels = 2;

// Set coupon supplement space to 30 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 30;
gen.Save($"{path}Gs1CouponSpace30Pixels.png", BarCodeImageFormat.Png);

// Set coupon supplement space to 50 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 50;
gen.Save($"{path}Gs1CouponSpace50Pixels.png", BarCodeImageFormat.Png);
```

V tomto příkladu:

1. **Vytvořte** instanci `BarcodeGenerator` pro typ `UpcaGs1DatabarCoupon`.  
2. **Nastavte** X‑rozměr na 2 pixely, což určuje nejúžší šířku čáry.  
3. **Upravte** vlastnost `SupplementSpace.Pixels` na 30 px, vygenerujte obrázek a poté opakujte s 50 px.  

Neváhejte experimentovat s jinými hodnotami pixelů, aby odpovídaly vašemu tiskovému workflow.

## Časté problémy a tipy
- **Neplatná cesta** – Ujistěte se, že proměnná `path` končí koncovým zpětným lomítkem (`\`) nebo lomítkem (`/`) vhodným pro váš OS.  
- **Nedostatečná oprávnění** – Spusťte Visual Studio jako administrátor nebo vyberte složku, kde má aplikace právo zápisu.  
- **Nesprávný formát dat** – Řetězec dat musí odpovídat syntaxi GS1 (`(8110)` označuje identifikátor doplňku).  

## Proč je to důležité pro vaše podnikání
Aspose.BarCode podporuje **více než 60 symbologií čárových kódů** a dokáže vykreslit obrázky až do **10 000 × 10 000 pixelů** bez vyčerpání paměti. Pro rozsáhlé maloobchodní nasazení to znamená, že můžete generovat vysoce rozlišené GS1 kupóny v dávkovém režimu a přitom udržet dobu zpracování pod jednou sekundou na obrázek na typickém serverovém hardware.

## Často kladené otázky

**Q: Jaký je účel doplňkového prostoru GS1 kupónu v čárových kódech?**  
A: Přidává povinný prázdný okraj kolem doplňkových dat, zlepšuje spolehlivost skeneru a splňuje minimální šířky specifikované prodejci.

**Q: Mohu přizpůsobit šířku doplňkového prostoru GS1 kupónu pomocí Aspose.BarCode pro .NET?**  
A: Ano, nastavte `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` na libovolnou celočíselnou hodnotu; knihovna okamžitě aplikuje změnu na generovaný obrázek.

**Q: Kde mohu najít další dokumentaci a podporu pro Aspose.BarCode pro .NET?**  
A: Odkazujte se na [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) a navštivte [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) pro komunitní pomoc.

**Q: Je Aspose.BarCode pro .NET vhodný jak pro začátečníky, tak pro zkušené vývojáře?**  
A: Rozhodně. API nabízí jednoduché metody pro rychlé úkoly i pokročilé možnosti pro jemně laděnou generaci čárových kódů.

**Q: Mohu získat dočasnou licenci pro Aspose.BarCode pro .NET k vyhodnocení jeho funkcí?**  
A: Ano, požádejte o zkušební licenci na [Aspose temporary license website](https://purchase.aspose.com/temporary-license/).

## Závěr

Po provedení výše uvedených kroků nyní víte, jak **vytvořit vlastní prostor čárového kódu** pro doplňkový prostor GS1 kupónu, což je klíčová technika pro **zvýšení čitelnosti čárového kódu** a splnění maloobchodních standardů. Začleňte kód do vašich existujících skenovacích řešení, experimentujte s různými hodnotami pixelů a prozkoumejte další typy čárových kódů nabízené Aspose.BarCode pro .NET.

---

**Poslední aktualizace:** 2026-09-28  
**Testováno s:** Aspose.BarCode 24.12 for .NET  
**Autor:** Aspose

## Související tutoriály

- [Vytvořte čárový kód Aspose.BarCode Databar pomocí .NET API – konfigurace řádků a sloupců](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Jak generovat DataMatrix čárové kódy pomocí Aspose.BarCode pro .NET – krok za krokem průvodce](/barcode/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}