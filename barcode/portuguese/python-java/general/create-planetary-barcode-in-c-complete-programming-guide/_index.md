---
category: general
date: 2026-07-30
description: Crie um código de barras planetário rapidamente com C#. Aprenda a gerar
  o código de barras planetário, definir a altura personalizada do código de barras
  e exportar a imagem do código de barras.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planetary barcode
- generate planet barcode
- custom barcode height
- export barcode image
- customize postal barcode
language: pt
lastmod: 2026-07-30
og_description: Crie um código de barras planetário em C# e gere instantaneamente
  o código de barras do planeta com altura personalizada, depois exporte a imagem
  do código de barras para qualquer sistema postal.
og_image_alt: Screenshot showing a generated planetary barcode saved as a PNG file
og_title: Crie código de barras planetário em C# – Tutorial completo passo a passo
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Create planetary barcode quickly with C#. Learn how to generate planet
    barcode, set custom barcode height, and export barcode image.
  headline: Create planetary barcode in C# – Complete Programming Guide
  type: TechArticle
- description: Create planetary barcode quickly with C#. Learn how to generate planet
    barcode, set custom barcode height, and export barcode image.
  name: Create planetary barcode in C# – Complete Programming Guide
  steps:
  - name: 'Example 1: Default planetary barcode (auto height)'
    text: '```csharp using Aspose.Barcode; using Aspose.Barcode.Generation;'
  - name: 'Example 2: Planet barcode with a custom 100‑pixel bar height'
    text: 'Sometimes you need a taller barcode for a specific label printer. Here’s
      how to set a **custom barcode height**:'
  - name: 'Example 3: RM4SCC barcode with a custom 100‑pixel bar height'
    text: 'The Planet format isn’t the only postal symbology you might encounter.
      Let’s **customize postal barcode** for RM4SCC, which is popular in the UK and
      parts of Europe:'
  type: HowTo
tags:
- barcode
- C#
- planetary barcode
title: Crie código de barras planetário em C# – Guia completo de programação
url: /pt/python-java/general/create-planetary-barcode-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar planetary barcode em C# – Guia de Programação Completo

Já precisou **create planetary barcode** mas não tinha certeza de quais propriedades ajustar? Você não está sozinho; a simbologia Planet pode parecer um pouco misteriosa até que você a veja em ação. Neste guia, vamos **generate planet barcode** objetos, ajustar uma **custom barcode height**, e finalmente **export barcode image** arquivos que funcionam com qualquer fluxo de trabalho postal.

Pense no planetary barcode como a versão da agência postal de um QR code — compacto, legível por máquina e surpreendentemente flexível. Ao final deste tutorial, você será capaz de **customize postal barcode** sem precisar vasculhar intermináveis documentos de API, e terá três trechos de código prontos‑para‑executar que podem ser inseridos diretamente no seu projeto.

---

## Prerequisites – What you need before you start

| Requirement | Why it matters |
|-------------|----------------|
| .NET 6.0 or later | Modern runtime, full support for Aspose.Barcode |
| Visual Studio 2022 (or any C# IDE) | Convenient debugging and IntelliSense |
| **Aspose.Barcode for .NET** NuGet package | Provides `BarcodeGenerator`, `EncodeTypes`, and image formats |
| Write access to a folder on disk | Needed for the `Save` call that **export barcode image** |

Você pode adicionar a biblioteca via Package Manager Console:

```powershell
Install-Package Aspose.Barcode
```

É só isso — sem DLLs extras, sem serviços externos. Pronto? Vamos mergulhar.

---

## Create planetary barcode – Step‑by‑Step

A seguir, vamos percorrer três exemplos práticos:

1. **Default‑height planetary barcode** (auto‑sized)
2. **Planet barcode with a custom 100‑pixel bar height**
3. **RM4SCC barcode with a custom height** (mostra como **customize postal barcode** além do Planet)

Cada exemplo se baseia no anterior, então sinta‑se à vontade para copiar‑colar o bloco inteiro em um novo console app e executá‑lo.

### Example 1: Default planetary barcode (auto height)

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a generator for the Planet symbology and supply the data to encode
        BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Step 2: Define the module (X) size – 4 pixels per bar
        gen.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 3: Render the barcode to a PNG file (this will **export barcode image**)
        gen.Save(@"C:\Barcodes\PostalPlanetAuto.png", BarCodeImageFormat.Png);
    }
}
```

**What just happened?**  
O `BarcodeGenerator` é seu ponto de entrada; você informa *o que* (Planet) e *qual dado* (`"123456"`). A X‑dimension controla a largura de cada barra e, como não alteramos a altura, a biblioteca escolhe automaticamente um tamanho razoável para os padrões postais. Quando você executar o programa, encontrará um PNG chamado **PostalPlanetAuto.png** em `C:\Barcodes`.

> **Pro tip:** Se estiver depurando, abra o PNG com qualquer visualizador de imagens — note como as barras estão nítidas e uniformemente espaçadas. Essa é a base para uma operação confiável de **generate planet barcode**.

### Example 2: Planet barcode with a custom 100‑pixel bar height

Às vezes você precisa de um código de barras mais alto para uma impressora de etiquetas específica. Veja como definir uma **custom barcode height**:

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

class Program
{
    static void Main()
    {
        // Initialise the generator with the same data
        BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Set the X dimension (module width)
        gen.Parameters.Barcode.XDimension.Pixels = 4;

        // Override the default bar height to 100 pixels
        gen.Parameters.Barcode.BarHeight.Pixels = 100;

        // Save the customised barcode image
        gen.Save(@"C:\Barcodes\PostalPlanetHeight100.png", BarCodeImageFormat.Png);
    }
}
```

**Why adjust the height?**  
Uma barra mais alta pode melhorar a confiabilidade da leitura em impressoras de baixa resolução, e alguns serviços postais solicitam explicitamente uma altura mínima. Ajustando `BarHeight.Pixels` mantemos controle total sobre o peso visual do símbolo enquanto ainda **generate planet barcode** nos bastidores.

### Example 3: RM4SCC barcode with a custom 100‑pixel bar height

O formato Planet não é a única simbologia postal que você pode encontrar. Vamos **customize postal barcode** para RM4SCC, que é popular no Reino Unido e em partes da Europa:

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

class Program
{
    static void Main()
    {
        // Create a generator for the RM4SCC symbology
        BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

        // Set the X dimension (module width)
        gen.Parameters.Barcode.XDimension.Pixels = 4;

        // Specify a 100‑pixel bar height
        gen.Parameters.Barcode.BarHeight.Pixels = 100;

        // Export the barcode to a PNG file
        gen.Save(@"C:\Barcodes\PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);
    }
}
```

Observe como o código é quase idêntico ao Example 2 — apenas o enum `EncodeTypes` muda. Essa é a beleza do Aspose.Barcode: você **customize postal barcode** sem precisar aprender uma nova API.

---

## Understanding the key properties

| Property | Meaning | Typical values |
|----------|---------|----------------|
| `XDimension.Pixels` | Width of a single module (the smallest bar) | 2‑6 px for most printers |
| `BarHeight.Pixels` | Height of the tallest bar (in pixels) | 50‑150 px, depending on label size |
| `EncodeTypes` | Symbology to generate (Planet, RM4SCC, etc.) | `EncodeTypes.Planet`, `EncodeTypes.RM4SCC` |
| `BarCodeImageFormat` | Output image format | `.Png`, `.Jpeg`, `.Bmp` |

Quando você **export barcode image**, a biblioteca rasteriza os dados vetoriais no formato escolhido. PNG é sem perdas, tornando‑o perfeito para etiquetas de alta qualidade. Se precisar de um arquivo menor para uso web, troque para `BarCodeImageFormat.Jpeg` e ajuste a compressão.

---

## Common pitfalls and how to avoid them

* **Incorrect module width** – Definir `XDimension.Pixels` muito baixo pode fazer as barras se fundirem ao imprimir. Teste com uma impressora física antes da produção em massa.
* **Missing write permissions** – O método `Save` lança exceção se a pasta de destino não for gravável. Sempre verifique o caminho ou use `Path.GetTempPath()` para testes rápidos.
* **Wrong data length** – Planet espera uma string numérica de 6‑8 dígitos. Fornecer caracteres alfabéticos gerará erro de validação.
* **Forgetting to dispose** – `BarcodeGenerator` implementa `IDisposable`. Em um serviço de longa execução, envolva‑o em um bloco `using` para liberar recursos nativos.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(...))
{
    // configure and save...
}
```

---

## Expected output – What you should see

Depois de executar os três exemplos, a pasta `C:\Barcodes` conterá:

| File | Description |
|------|-------------|
| `PostalPlanetAuto.png` | Default‑height Planet barcode (auto‑sized) |
| `PostalPlanetHeight100.png` | Planet barcode com **custom barcode height** de 100 px |
| `PostalRM4SCCHeight100.png` | RM4SCC barcode, também com **custom barcode height** de 100 px |

Abra qualquer um desses PNGs; você notará barras verticais limpas com os dados numéricos codificados abaixo (ou acima, dependendo da simbologia). Escaneie‑os com um aplicativo de leitura de códigos de barras no smartphone — se o app reconhecer “123456”, você concluiu com sucesso **create planetary barcode** e **export barcode image**.

---

## Going further – Next steps and related topics

* **Batch generation** – Loop through a CSV list of postal codes and save each barcode automatically.
* **Embedding in PDFs** – Use `PdfDocument` from Aspose.PDF to place the PNG directly onto a shipping label.
* **Dynamic sizing** – Calculate `BarHeight.Pixels` based on the label’s DPI to guarantee consistent physical dimensions.
* **Other postal symbologies** – Explore `EncodeTypes.Postnet`, `EncodeTypes.USPSIntelligentMail`, or `EncodeTypes.Aztec` for broader coverage.

Se você tem curiosidade sobre cálculos de **custom barcode height**, confira a documentação oficial do Aspose.Barcode sobre *module dimensions* — as fórmulas são simples e funcionam em todas as simbologias suportadas.

---

## Conclusion

Percorremos um processo completo e prático para **create planetary barcode** em C#. Partindo de um gerador simples, aprendemos a **generate planet barcode**, aplicar uma **custom barcode height** e, finalmente, **export barcode image** arquivos que atendem aos padrões postais. Ajustando apenas algumas propriedades, você também pode **customize postal barcode** para RM4SCC ou qualquer outro formato suportado.

Experimente: altere a string de dados, experimente valores diferentes de `XDimension`, ou troque PNG por JPEG. A biblioteca é flexível o suficiente para a maioria dos cenários reais, e agora você tem uma base sólida para evoluir.

Tem perguntas ou quer compartilhar seus próprios truques de códigos de barras? Deixe um comentário abaixo, e feliz codificação!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Create Barcode Custom Height – One-Dimensional Barcodes](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}