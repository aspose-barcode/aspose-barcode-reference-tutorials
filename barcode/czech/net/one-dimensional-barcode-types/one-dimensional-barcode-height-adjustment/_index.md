---
date: 2026-02-22
description: Naučte se, jak v .NET pomocí Aspose.BarCode vytvořit čárový kód s vlastní
  výškou a rychle a přesně nastavit výšku jednorozměrného čárového kódu.
linktitle: Create Barcode Custom Height – One-Dimensional Barcodes
second_title: Aspose.BarCode .NET API
title: Vytvořit čárový kód s vlastní výškou – jednorozměrné čárové kódy
url: /cs/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření vlastního výšky čárového kódu – jednorozměrné čárové kódy

Když potřebujete **vytvořit vlastní výšku čárového kódu** v .NET aplikaci, Aspose.BarCode pro .NET vám poskytuje plnou kontrolu nad vizuálním vzhledem jednorozměrných čárových kódů. Ať už vytváříte štítky zásob, pokladní účtenky nebo přepravní štítky, možnost jemně doladit výšku čárového kódu zajišťuje optimální výkon skenování a profesionální vzhled. V tomto krok‑za‑krokem průvodci si projdeme vše, co potřebujete vědět k úpravě výšky jednorozměrného čárového kódu pomocí Aspose.BarCode pro .NET.

## Rychlé odpovědi
- **Co znamená „vlastní výška čárového kódu“?** Jedná se o vertikální velikost 1‑D symbolu čárového kódu vyjádřenou v pixelech.  
- **Která vlastnost řídí výšku?** `Parameters.Barcode.BarHeight.Pixels`.  
- **Mohu vygenerovat více výšek během jednoho běhu?** Ano – stačí změnit vlastnost a znovu zavolat `Save()`.  
- **Podporované formáty obrázků?** PNG, JPEG, TIFF, BMP, GIF a další.  
- **Je potřeba licence pro úpravu výšky?** Ne, funkce funguje ve zkušební verzi; licence je vyžadována pro produkční použití.

## Co znamená „vytvořit vlastní výšku čárového kódu“?
Vytvoření čárového kódu s vlastní výškou znamená zadání přesné hodnoty v pixelech pro vertikální rozměr pruhů čárového kódu. To je užitečné, pokud máte přísné požadavky na rozvržení, potřebujete odpovídat existujícím tištěným materiálům nebo chcete zlepšit čitelnost skeneru na různých médiích.

## Proč použít Aspose.BarCode pro .NET?
- **Bohaté API** – Nastavte velikost, barvu, text a další pomocí jednoduchých vlastností.  
- **Cross‑platform** – Funguje s .NET Framework, .NET Core i .NET 5/6+.  
- **Žádné externí závislosti** – Generuje obrázky bez nutnosti dalších knihoven.  
- **Vysoce kvalitní vykreslování** – Zaručuje skenovatelné čárové kódy i při vlastních rozměrech.

## Předpoklady

Než začnete, ujistěte se, že máte připravené následující předpoklady:

- Vývojové prostředí s .NET Framework nebo .NET Core.  
- Aspose.BarCode pro .NET nainstalovaný. Můžete jej stáhnout z webu [zde](https://releases.aspose.com/barcode/net/).  
- Editor kódu dle vašeho výběru.

Nyní, když máme předpoklady pokryté, pojďme se ponořit do procesu úpravy výšky jednorozměrného čárového kódu.

## Import Namespaces

Nejprve musíte do svého projektu importovat potřebné jmenné prostory. Tyto jmenné prostory jsou nezbytné pro práci s Aspose.BarCode pro .NET. Zde je, jak to můžete provést:

```csharp
using Aspose.BarCode.Generation;
```

## Krok 1: Nastavení cesty ke složce

Začněte definováním cesty ke složce, kam chcete ukládat vygenerované obrázky čárových kódů. Nahraďte `"Your Directory Path"` skutečnou cestou ve vašem systému.

```csharp
string path = "Your Directory Path";
```

## Krok 2: Vytvoření generátoru čárového kódu

Nyní vytvořte instanci třídy `BarcodeGenerator`. Můžete specifikovat typ čárového kódu (v tomto případě použijeme `Code128`) a hodnotu čárového kódu (v tomto příkladu `"ASPOSE"`).

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code128, "ASPOSE");
```

## Krok 3: Úprava výšky čárového kódu

V tomto kroku nastavíte výšku čárového kódu pomocí vlastnosti `BarHeight`. Jako příklad upravíme výšku na 40 pixelů a 80 pixelů a uložíme dva obrázky čárových kódů. Tím demonstrujeme, jak snadno lze **vytvořit vlastní výšku čárového kódu** za běhu.

```csharp
// Set BarHeight to 40 pixels
gen.Parameters.Barcode.BarHeight.Pixels = 40;
gen.Save($"{path}BarHeight40Code128.png", BarCodeImageFormat.Png);

// Set BarHeight to 80 pixels
gen.Parameters.Barcode.BarHeight.Pixels = 80;
gen.Save($"{path}BarHeight80Code128.png", BarCodeImageFormat.Png);
```

## Časté problémy a řešení

| Problém | Důvod | Řešení |
|---------|-------|--------|
| Čárový kód se po změně výšky zdá příliš tenký | Šířka není upravena proporcionálně | Použijte `Parameters.Barcode.XDimension` k úpravě šířky pruhu, pokud je to potřeba. |
| Obrázek se neuloží | Neplatná cesta nebo chybějící oprávnění k zápisu | Ověřte, že `path` končí zpětným lomítkem a složka existuje. |
| Vygenerovaný čárový kód nelze naskenovat | Výška je příliš nízká/vysoká pro skener | Testujte s typickým skenerem; udržujte výšku mezi 30‑100 px pro většinu 1‑D kódů. |

## Často kladené otázky

**Q: Jaké typy čárových kódů jsou podporovány v Aspose.BarCode pro .NET?**  
A: Aspose.BarCode pro .NET podporuje širokou škálu typů čárových kódů, včetně Code128, QR Code, DataMatrix a mnoha dalších. Kompletní seznam najdete v dokumentaci.

**Q: Mohu také upravit šířku jednorozměrného čárového kódu?**  
A: Ano, šířku jednorozměrného čárového kódu můžete upravit pomocí Aspose.BarCode pro .NET. Proces je podobný úpravě výšky a máte plnou kontrolu nad rozměry čárového kódu.

**Q: Je k dispozici bezplatná zkušební verze Aspose.BarCode pro .NET?**  
A: Ano, můžete si vyzkoušet Aspose.BarCode pro .NET s bezplatnou zkušební verzí. Stáhnout ji můžete [zde](https://releases.aspose.com/).

**Q: Mohu generovat čárové kódy v různých formátech obrázků?**  
A: Ano, Aspose.BarCode pro .NET podporuje různé formáty obrázků, včetně PNG, JPEG a TIFF. Vyberte formát, který nejlépe vyhovuje požadavkům vaší aplikace.

**Q: Kde najdu podrobnou dokumentaci k Aspose.BarCode pro .NET?**  
A: Dokumentaci najdete [zde](https://reference.aspose.com/barcode/net/) pro podrobné informace o používání Aspose.BarCode ve vašich .NET projektech.

## Závěr

V tomto tutoriálu jsme prošli proces **vytvoření vlastní výšky čárového kódu** pro jednorozměrné čárové kódy pomocí Aspose.BarCode pro .NET. Úpravou vlastnosti `BarHeight` můžete generovat obrázky čárových kódů, které přesně odpovídají vašim požadavkům na rozvržení, ať už potřebujete kompaktní štítek nebo velký, dobře viditelný kód.

Pokud narazíte na jakékoli potíže nebo máte další otázky, neváhejte se obrátit na komunitu Aspose prostřednictvím jejich [fóra podpory](https://forum.aspose.com/c/barcode/13).

---

**Poslední aktualizace:** 2026-02-22  
**Testováno s:** Aspose.BarCode 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}