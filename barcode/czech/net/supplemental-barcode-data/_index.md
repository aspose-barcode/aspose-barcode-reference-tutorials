---
date: 2026-03-07
description: Naučte se, jak vytvořit čárový kód EAN‑2 a provádět generování čárových
  kódů v .NET pomocí Aspose.BarCode pro .NET. Ovládněte dnes přizpůsobení doplňkových
  dat čárových kódů!
linktitle: Supplemental Barcode Data
second_title: Aspose.BarCode .NET API
title: Vytvořte čárový kód EAN‑2 pomocí Aspose.BarCode pro .NET
url: /cs/net/supplemental-barcode-data/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření čárového kódu EAN-2 pomocí Aspose.BarCode pro .NET

## Úvod

Jste vývojář .NET a chcete **vytvořit čárový kód EAN-2** a využít sílu doplňkových dat čárových kódů? Pak jste na správném místě. V tomto komplexním průvodci vás provede vším, co potřebujete vědět – od základní konfigurace po jemné doladění prostoru kolem vašich symbolů. Ať už budujete nový inventární systém nebo vylepšujete existující pokladní aplikaci, zvládnutí těchto funkcí učiní vaše .NET projekty generování čárových kódů flexibilnějšími a spolehlivějšími.

## Rychlé odpovědi
- **Co mohu generovat?** Doplňkové čárové kódy EAN‑2 a EAN‑5.  
- **Potřebuji licenci?** Bezplatná zkušební verze stačí pro vývoj; pro produkci je vyžadována komerční licence.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Kolik kódu je potřeba?** Pouze několik řádků – Aspose.BarCode zvládne těžkou část.  
- **Mohu přizpůsobit mezery?** Ano, můžete přímo řídit X‑dimenzi a prostor doplňku.

## Co jsou doplňková data čárových kódů?

Doplňková data čárových kódů jsou malé dodatečné symboly (EAN‑2, EAN‑5), které se objevují vedle hlavního čárového kódu a typicky slouží k číslům vydání, rozšířením ceny nebo jiným pomocným informacím. Aspose.BarCode pro .NET vám umožňuje tyto symboly generovat programově a poskytuje plnou kontrolu nad jejich vzhledem a umístěním.

## Proč použít Aspose.BarCode pro .NET?

- **Plná integrace s .NET** – funguje s C#, VB.NET i F#.  
- **Vysoce kvalitní vykreslování** – vytváří skenovatelné čárové kódy v libovolném rozlišení.  
- **Rozsáhlé přizpůsobení** – od typu symbologie po X‑dimenzi, tiché zóny a prostor doplňku.  
- **Žádné externí závislosti** – čistě spravovaná knihovna, snadná nasazení.

## Konfigurace doplňkových dat čárových kódů

Začneme ponořením se do světa konfigurace doplňkových dat čárových kódů. Aspose.BarCode pro .NET vám poskytuje nástroje pro snadné generování doplňkových čárových kódů a dává vám úplnou kontrolu nad čárovými kódy EAN‑2 a EAN‑5. Jak ale začít?

Nejprve stáhněte a nainstalujte Aspose.BarCode pro .NET. Můžete vyzkoušet bezplatnou zkušební verzi a otestovat funkce v praxi. Jakmile budete připraveni, postupujte podle našeho krok‑za‑krokem průvodce, který vás provede procesem a zajistí, že zvládnete konfiguraci doplňkových dat čárových kódů s lehkostí.

Na konci této sekce budete mít pevné základy pro vytváření čárových kódů EAN‑2 a EAN‑5, což vás učiní univerzálnějším .NET vývojářem.

## Jak vytvořit čárový kód EAN-2? (Kroky konfigurace)

1. **Vytvořte generátor čárových kódů** – použijte třídu `BarcodeGenerator` a nastavte symbologii na `EncodeTypes.EAN13` (nebo jiný primární typ).  
2. **Povolte doplňkovou část** – nastavte vlastnost `SupplementData` na požadovaný číselný řetězec (např. `"12"` pro doplněk EAN‑2).  
3. **Upravte vizuální nastavení** – volitelně změňte `XDimension`, `BarHeight` a `QuietZone`, aby odpovídaly požadavkům vašeho rozvržení.  
4. **Uložte nebo vykreslete** – zavolejte `Save` pro zápis obrázku do souboru nebo proudu.

> *Tip:* Délka doplňkových dat musí být přesně 2 číslice pro EAN‑2 a 5 číslic pro EAN‑5; jinak může být čárový kód nečitelné.

## Přizpůsobení prostoru doplňku čárového kódu

Ve světě čárových kódů je přizpůsobitelnost klíčová a právě zde Aspose.BarCode pro .NET vyniká. Nyní se zaměříme na přizpůsobení prostoru doplňku. Tento aspekt se týká řízení X‑dimenze a prostoru doplňku ve vašich čárových kódech.

Opět začnete instalací Aspose.BarCode pro .NET a využitím bezplatné zkušební verze. Poté budete následovat naše pokyny, jak upravit mezery ve vašich čárových kódech. Toto přizpůsobení může být neuvěřitelně užitečné pro různé aplikace, od správy zásob po pokladní systémy.

Svoboda přizpůsobit čárové kódy vašim konkrétním potřebám je cenná dovednost a tato sekce vás na to připraví.

## Jak přizpůsobit prostor doplňku?

- **X‑Dimension** – určuje šířku jednoho modulu; vyšší hodnoty zvětšují celkovou velikost čárového kódu.  
- **Supplement Space** – mezera mezi primárním čárovým kódem a doplňkovou částí; nastavuje se pomocí vlastnosti `SupplementSpace`.  
- **Quiet Zone** – povinný prázdný okraj kolem celého čárového kódu; udržujte alespoň 10 X‑Dimension jednotek pro spolehlivé skenování.

Experimentujte s těmito nastaveními v testovacím projektu, dokud nedosáhnete vizuální rovnováhy požadované vaším skenovacím hardwarem.

## Běžné scénáře použití

| Scénář | Proč doplňková data pomáhají |
|----------|------------------------------|
| **Rozšíření cen v maloobchodě** | EAN‑5 může přímo na štítku kódovat informaci o ceně. |
| **Čísla vydání časopisů** | EAN‑2 identifikuje vydání, což umožňuje rychlé třídění. |
| **Logistika a sledování** | Přidání malého doplňku k primárnímu čárovému kódu poskytuje extra informace o trase bez zvětšování velikosti štítku. |

## Tutoriály doplňkových dat čárových kódů
### [Konfigurace doplňkových dat čárových kódů](./supplemental-barcode-data-configuration/)
Generujte doplňková data čárových kódů pomocí Aspose.BarCode pro .NET. Přizpůsobte čárové kódy EAN-2 a EAN-5 bez námahy. Krok‑za‑krokem průvodce pro .NET vývojáře.
### [Přizpůsobení prostoru doplňku čárových kódů](./supplemental-barcode-space-customization/)
Jednoduše přizpůsobte čárové kódy pomocí Aspose.BarCode pro .NET. Ovládejte X‑Dimension a prostor doplňku. Vyzkoušejte bezplatnou zkušební verzi!

## Často kladené otázky

**Q: Mohu generovat jak EAN‑2, tak EAN‑5 stejným kódem?**  
A: Ano. Stačí změnit délku `SupplementData` (2 číslice pro EAN‑2, 5 číslic pro EAN‑5) a knihovna vykreslí správnou symbologii.

**Q: Musím počítat kontrolní součty pro doplněk?**  
A: Ne. Aspose.BarCode automaticky vypočítá a připojí požadovaný kontrolní součet.

**Q: Existuje limit, kolik čárových kódů mohu generovat v cyklu?**  
A: Knihovna je optimalizována pro hromadnou generaci; jen dbejte na využití paměti při práci s velmi velkými kolekcemi obrázků.

**Q: Jak vložit čárový kód do PDF nebo Word dokumentu?**  
A: Uložte čárový kód jako obrázek (PNG, JPEG, atd.) a poté jej vložte pomocí preferovaného API pro generování dokumentů (např. Aspose.PDF nebo Aspose.Words).

**Q: Co když můj skener nedokáže přečíst doplňkovou část?**  
A: Ověřte, že `SupplementSpace` je alespoň 2 X‑Dimension jednotky a že tichá zóna splňuje specifikace skeneru.

---

**Poslední aktualizace:** 2026-03-07  
**Testováno s:** Aspose.BarCode pro .NET 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}