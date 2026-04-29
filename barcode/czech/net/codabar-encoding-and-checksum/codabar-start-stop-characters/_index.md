---
date: 2026-01-04
description: Naučte se, jak generovat čárový kód Codabar se startovacími a koncovými
  znaky pomocí Aspose.BarCode pro .NET. Podrobný návod krok za krokem pro vývojáře.
linktitle: Codabar Start/Stop Characters
second_title: Aspose.BarCode .NET API
title: Generovat čárový kód Codabar se start/stop znaky v Aspose.BarCode pro .NET
url: /cs/net/codabar-encoding-and-checksum/codabar-start-stop-characters/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generování čárového kódu Codabar se start/stop znaky v Aspose.BarCode pro .NET

## Úvod

Vítejte v tomto komplexním průvodci, jak **generovat čárový kód Codabar** s obrázky start/stop znaků pomocí Aspose.BarCode pro .NET. Ať už budujete systém pro maloobchodní inventuru, sledování laboratorních vzorků nebo řešení pro zdravotnické záznamy, Codabar je spolehlivá číselná symbologie, která vyžaduje explicitní start a stop symboly pro přesné skenování. V následujících minutách vás provedeme vším, co potřebujete – od předpokladů až po uložení finálních PNG souborů – abyste mohli okamžitě začít vytvářet čárové kódy Codabar.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.BarCode pro .NET  
- **Do jakého formátu mohu kód uložit?** PNG (BarCodeImageFormat.Png)  
- **Potřebuji licenci pro vývoj?** Bezplatná zkušební verze funguje pro testování; pro produkci je vyžadována komerční licence.  
- **Mohu změnit start/stop symboly?** Ano – použijte CodabarSymbol.A, B, C nebo D.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Předpoklady

Než začneme, ujistěte se, že máte vše potřebné k tomu, abyste mohli sledovat tento tutoriál:

1. **Nastavení prostředí** – Ujistěte se, že máte funkční .NET vývojové prostředí na svém počítači. Pokud potřebujete pomoc, podívejte se do [dokumentace](https://reference.aspose.com/barcode/net/).  
2. **Aspose.BarCode pro .NET knihovna** – Stáhněte a nainstalujte knihovnu z oficiálního [zdroje](https://releases.aspose.com/barcode/net/).  
3. **Základní znalosti .NET** – Znalost C# a Visual Studio (nebo libovolného preferovaného IDE) usnadní jednotlivé kroky.  
4. **IDE** – Visual Studio, Rider nebo Visual Studio Code jsou všechny v pořádku.

Nyní, když jsme prošli předpoklady, pojďme se ponořit do samotného kódu.

## Import jmenných prostorů

Abyste mohli začít pracovat s Aspose.BarCode pro .NET, nezapomeňte importovat potřebný jmenný prostor:

```csharp
using Aspose.BarCode.Generation;
```

## Jak generovat čárový kód Codabar – krok za krokem

### Krok 1: Inicializace generátoru čárových kódů

Vytvořte instanci `BarcodeGenerator`, specifikujte **Codabar** jako typ kódování a poskytněte řetězec dat, který již obsahuje start/stop znaky (např. “-12345-”).

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarStartStop:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

> **Tip:** Pomlčka (`-`) je jedním z platných start/stop symbolů pro Codabar. Můžete také použít A, B, C nebo D podle požadavků vaší aplikace.

### Krok 2: Nastavení X‑dimenze (šířka elementu čárového kódu)

X‑dimenze řídí šířku nejúzkého pruhu. Upravit ji můžete podle podmínek skenování.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Proč je to důležité:** Větší X‑dimenze zlepšuje čitelnost na tiskárnách s nízkým rozlišením, zatímco menší hodnota šetří místo na štítcích s vysokou hustotou.

### Krok 3: Definice start a stop znaků

Codabar podporuje čtyři start/stop symboly (A, B, C, D). Níže jsou příklady pro každou možnost. Vyberte tu, která odpovídá specifikaci systému, do kterého integrujete.

#### Nastavení Start A a Stop A

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.A;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.A;
```

#### Nastavení Start B a Stop B

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.B;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.B;
```

#### Nastavení Start C a Stop C

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.C;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.C;
```

#### Nastavení Start D a Stop D

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.D;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.D;
```

Můžete opakovat konfiguraci pro každý symbol, který potřebujete vygenerovat; níže uvedený příklad uloží čtyři samostatné obrázky – jeden pro každý start/stop pár.

### Krok 4: Uložení vygenerovaných obrázků čárových kódů (PNG)

Nakonec zapište čárový kód do PNG souborů. Tím demonstrujete použití **save barcode png** a získáte připravená aktiva pro testování.

```csharp
gen.Save($"{path}CodabarStartAStopA.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartBStopB.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartCStopC.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartDStopD.png", BarCodeImageFormat.Png);
```

Každý soubor nyní obsahuje **příklad čárového kódu Codabar** s odpovídajícími start/stop znaky.

## Časté problémy a řešení

| Problém | Pravděpodobná příčina | Oprava |
|---------|-----------------------|--------|
| Čárový kód vypadá deformovaně | X‑dimenze je příliš nízká pro zvolenou rozlišení tiskárny | Zvyšte `XDimension.Pixels` (např. na 3 nebo 4) |
| Skenner nedokáže přečíst start/stop | Nesprávný start/stop symbol pro cílový systém | Ověřte požadovaný symbol (A‑D) a nastavte jej správně |
| PNG soubor je prázdný nebo poškozený | Neplatná výstupní cesta nebo nedostatečná oprávnění k zápisu | Ujistěte se, že `path` ukazuje na existující složku a aplikace má právo zapisovat |

## Často kladené otázky

### Q1: Co je Codabar a proč jsou start a stop znaky důležité?

A1: Codabar je číselná symbologie čárových kódů široce používaná v inventářích, knihovnách a zdravotnictví. Start a stop znaky definují hranice čárového kódu, což zajišťuje, že skenery vědí, kde data začínají a končí.

### Q2: Mohu si přizpůsobit vzhled čárových kódů Codabar pomocí Aspose.BarCode pro .NET?

A2: Ano. Kromě X‑dimenze můžete měnit barvy, přidávat okraje a dokonce vložit čárový kód do PDF nebo SVG formátů pomocí stejného API.

### Q3: Existují omezení čárových kódů Codabar z hlediska kódování dat?

A3: Codabar primárně podporuje číselná data (0‑9) a několik speciálních znaků. Není vhodný pro plně alfanumerické řetězce.

### Q4: Je Aspose.BarCode pro .NET vhodný pro komerční použití a jak získám licenci?

A4: Ano, je připravený pro produkci. Zakupte licenci na [stránce nákupu Aspose](https://purchase.aspose.com/buy).

### Q5: Kde mohu získat pomoc nebo diskutovat o problémech souvisejících s Aspose.BarCode pro .NET?

A5: Připojte se ke komunitě na [fóru podpory Aspose.BarCode pro .NET](https://forum.aspose.com/c/barcode/13), kde vám pomohou jak inženýři Aspose, tak ostatní vývojáři.

---

**Poslední aktualizace:** 2026-01-04  
**Testováno s:** Aspose.BarCode 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}