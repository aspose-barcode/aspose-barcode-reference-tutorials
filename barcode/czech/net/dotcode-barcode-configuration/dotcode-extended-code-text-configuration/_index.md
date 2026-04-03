---
date: 2026-01-27
description: Naučte se, jak vytvořit rozšířený kódový text pro DotCode pomocí Aspose.BarCode
  pro .NET – krok za krokem průvodce generováním čárových kódů DotCode s rozšířeným
  kódovým textem.
linktitle: DotCode Extended Code Text Configuration
second_title: Aspose.BarCode .NET API
title: Jak vytvořit rozšířený kódový text pro DotCode pomocí Aspose.BarCode pro .NET
url: /cs/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit rozšířený kód textu dotcode pomocí Aspose.BarCode pro .NET

## Úvod

V oblasti generování a správy čárových kódů vyniká Aspose.BarCode pro .NET jako všestranné a efektivní řešení. Ať už potřebujete generovat čárové kódy pro produkty, inventář nebo jakoukoli jinou aplikaci, Aspose.BarCode pro .NET vám poskytne vše potřebné. V tomto komplexním tutoriálu **vytvoříme rozšířený kód textu dotcode** a prozkoumáme, proč je tato schopnost nezbytná pro moderní prostředí bohatá na data. DotCode je dvourozměrný maticový čárový kód, který může kódovat jak textová, tak binární data, což z něj činí cenný nástroj v různých odvětvích.

## Rychlé odpovědi
- **Co znamená „vytvořit rozšířený kód textu dotcode“?** Jedná se o vytvoření čárového kódu DotCode, který zahrnuje FNC1, ECICodetext, obyčejný text a symbolové oddělovače v jednom rozšířeném nosiči.  
- **Která knihovna je vyžadována?** Aspose.BarCode pro .NET.  
- **Potřebuji licenci?** Dočasná licence stačí pro hodnocení; pro produkční nasazení je nutná plná licence.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní příklad.

## Jak vytvořit rozšířený kód textu dotcode

Níže je stručný, krok‑za‑krokem průvodce, který ukazuje, jak přesně vytvořit rozšířený kód textu a vygenerovat obrázek čárového kódu.

## Předpoklady

Než se pustíme do podrobného návodu, je potřeba mít připravené následující předpoklady:

1. Aspose.BarCode pro .NET: Ujistěte se, že máte knihovnu Aspose.BarCode pro .NET nainstalovanou a připravenou. Pokud ne, můžete si ji stáhnout z [dokumentace Aspose.BarCode pro .NET](https://reference.aspose.com/barcode/net/).

2. Vývojové prostředí: Měli byste mít funkční .NET vývojové prostředí, nejlépe Visual Studio, nainstalované ve vašem systému.

S těmito předpoklady v pořádku můžeme přistoupit k generování rozšířeného kódu textu DotCode.

## Import Namespaces

Nejprve je třeba importovat potřebné jmenné prostory do vašeho .NET projektu, aby bylo možné využít funkce knihovny Aspose.BarCode. Zde je postup:

```csharp
using Aspose.BarCode.Generation;
```

Nyní, když máme předpoklady pokryté, rozdělíme proces generování rozšířeného kódu textu DotCode na krok‑za‑krokem návod.

## Krok 1: Definujte cestu ke složce

V tomto kroku musíte zadat cestu ke složce, kam chcete uložit vygenerovaný obrázek rozšířeného kódu textu DotCode.

```csharp
string path = "Your Directory Path";
```

Nahraďte `"Your Directory Path"` skutečnou cestou ve vašem systému.

## Krok 2: Vytvořte rozšířený kód textu DotCode

Pro vytvoření rozšířeného kódu textu DotCode postupujte podle následujících podkroků:

### 2.1 Přidejte identifikátor formátu FNC1

Identifikátor formátu FNC1 slouží k označení začátku nového datového pole. Je nezbytnou součástí rozšířeného kódu textu DotCode.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 Přidejte ECICodetext

ECICodetext umožňuje kódovat speciální znaky a mezinárodní text. V tomto příkladu jsme kódovali `"犬Right狗"` pomocí UTF‑8 kódování.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 Přidejte obyčejný kód textu

Můžete také přidat obyčejný text do rozšířeného kódu textu DotCode. Zde jsme přidali `"Plain text"`.

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 Přidejte symbolový oddělovač FNC3

Symbolový oddělovač FNC3 slouží k oddělení různých částí kódu.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 Přidejte inicializaci čtečky FNC3

Tento krok přidává informace o inicializaci čtečky FNC3.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 Vygenerujte kód textu

Nyní vygenerujte rozšířený kód textu DotCode voláním metody `GetExtendedCodetext` na objektu `textBuilder`.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## Krok 3: Vygenerujte obrázek DotCode

Pro vygenerování rozšířeného kódu textu DotCode jako obrázku postupujte podle následujících podkroků:

#### 4.1 Inicializujte generátor čárových kódů

Inicializujte `BarcodeGenerator` s příslušnými parametry. V tomto případě použijeme `EncodeTypes.DotCode` a vygenerovaný kód textu.

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

A to je vše! Úspěšně jste vygenerovali rozšířený kód textu DotCode pomocí Aspose.BarCode pro .NET.

## Závěr

Aspose.BarCode pro .NET je výkonný nástroj, který zjednodušuje generování čárových kódů. V tomto tutoriálu jsme se zaměřili na **vytvoření rozšířeného kódu textu dotcode**, což je klíčové v různých odvětvích, zejména tam, kde je vyžadováno vícejazyčné a specializované kódování znaků. Dodržením výše uvedených kroků můžete snadno vytvořit rozšířený kód textu DotCode pro své konkrétní potřeby.

Pokud potřebujete další pomoc nebo máte otázky, neváhejte navštívit [dokumentaci Aspose.BarCode pro .NET](https://reference.aspose.com/barcode/net/) nebo se zapojit do komunity na [fóru podpory Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

## Často kladené otázky

### Q1: K čemu se DotCode používá?

A1: DotCode se používá k zakódování jak textových, tak binárních dat a je běžně aplikován v odvětvích jako zdravotnictví a logistika pro sledování a kódování dat.

### Q2: Mohu přizpůsobit vzhled čárových kódů DotCode?

A2: Ano, Aspose.BarCode pro .NET poskytuje možnosti přizpůsobení vzhledu čárových kódů DotCode, včetně velikosti a režimu kódování.

### Q3: Je Aspose.BarCode pro .NET kompatibilní s různými .NET frameworky?

A3: Ano, Aspose.BarCode pro .NET je kompatibilní s širokou škálou .NET frameworků, což zajišťuje flexibilitu a snadnou integraci.

### Q4: Jak získám dočasnou licenci pro Aspose.BarCode pro .NET?

A4: Dočasnou licenci můžete získat na [webu Aspose](https://purchase.aspose.com/temporary-license/) pro účely hodnocení a testování.

### Q5: Je Aspose.BarCode pro .NET vhodný pro generování čárových kódů na úrovni podniku?

A5: Rozhodně, Aspose.BarCode pro .NET je navržen tak, aby vyhovoval potřebám jak malých, tak podnikově‑rozsáhlých projektů generování čárových kódů, nabízející škálovatelnost a spolehlivost.

## Frequently Asked Questions

**Q: Mohu použít vygenerovaný čárový kód v mobilní aplikaci?**  
A: Ano. PNG obrázek vytvořený generátorem lze vložit do iOS, Android nebo jakékoli multiplatformní mobilní aplikace.

**Q: Co když potřebuji zakódovat binární data místo textu?**  
A: Použijte metodu `AddECICodetext` s příslušným `ECIEncodings` (např. `ECIEncodings.Base64`) pro vložení binárního nosiče.

**Q: Jak změním velikost čárového kódu, aniž by to ovlivnilo čitelnost?**  
A: Upravit vlastnost `XDimension.Pixels`; vyšší hodnoty zvětší modul, nižší hodnoty učiní čárový kód kompaktnějším.

**Q: Existuje způsob, jak přidat tichou zónu kolem čárového kódu?**  
A: Ano. Nastavte `gen.Parameters.Barcode.Margin` pro definování požadované tiché zóny v pixelech.

**Q: Podporuje knihovna .NET 8?**  
A: Nejnovější verze Aspose.BarCode jsou kompatibilní s .NET 8; stačí odkazovat na odpovídající verzi NuGet balíčku.

---

**Poslední aktualizace:** 2026-01-27  
**Testováno s:** Aspose.BarCode 24.12 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}