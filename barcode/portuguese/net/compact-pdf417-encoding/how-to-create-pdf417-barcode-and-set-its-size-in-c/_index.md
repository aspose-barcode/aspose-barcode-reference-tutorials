---
category: general
date: 2026-09-22
description: Aprenda a criar códigos de barras PDF417 em C#, definir o tamanho do
  código de barras e gerar arquivos de imagem do código de barras com exemplos de
  código claros, passo a passo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to create PDF417
- set barcode size
- create barcode image c#
language: pt
lastmod: 2026-09-22
og_description: Crie código de barras PDF417 em C# rapidamente. Este tutorial mostra
  como definir o tamanho do código de barras, habilitar o modo compacto e gerar imagens
  PNG para qualquer projeto .NET.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Criar código de barras PDF417 em C# – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to create PDF417 barcode in C#, set barcode size, and generate
    barcode image files with clear step‑by‑step code examples.
  headline: How to create PDF417 barcode and set its size in C#
  type: TechArticle
tags:
- PDF417
- C#
- Barcode
- Imaging
title: Como criar código de barras PDF417 e definir seu tamanho em C#
url: /pt/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar código de barras PDF417 e definir seu tamanho em C#

Se você precisa **criar código de barras PDF417** em C#, este guia mostra como gerar o código, controlar suas dimensões e salvar o resultado como um arquivo de imagem. Seja para um sistema de bilhetagem, uma etiqueta de logística ou uma credencial segura, dominar o formato PDF417 permite codificar grandes quantidades de dados em uma forma visual compacta.

Neste tutorial você aprenderá a:

* **Criar código de barras PDF417** com a biblioteca Aspose.BarCode (ou qualquer compatível).  
* **Definir o tamanho do código de barras** ajustando a X‑dimension e a contagem de colunas.  
* Gerar uma **imagem do código de barras em C#** para saída PNG, JPEG ou BMP.  

O exemplo usa a edição gratuita da comunidade do Aspose.BarCode para .NET, mas os mesmos conceitos se aplicam a outras bibliotecas que exponham propriedades semelhantes.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou superior instalado.  
* Uma IDE C# (Visual Studio, Visual Studio Code, Rider, etc.).  
* O pacote NuGet `Aspose.BarCode` (`dotnet add package Aspose.BarCode`).  

Nenhuma configuração adicional é necessária; a biblioteca funciona no Windows, Linux e macOS.

## Etapa 1: Criar um código de barras PDF417 básico e definir seu tamanho

O primeiro passo é instanciar um `BarcodeGenerator` com o enum `EncodeTypes.Pdf417` e fornecer o texto que você deseja codificar. Em seguida, ajuste a **X‑dimension** (largura do módulo) e o número de **colunas** para controlar o tamanho geral.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Define the text that the barcode will represent.
string data = "Sample text for PDF417 barcode";

// Create a basic PDF417 barcode generator.
var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Set the module width to 2 pixels (controls bar thickness).
basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Set the column count; 3 columns yields a compact visual but still readable.
basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image.
string basicPath = Path.Combine("YOUR_DIRECTORY", "Pdf417Basic.png");
basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
```

**Por que essas configurações são importantes**

* `XDimension.Pixels` determina a largura da barra mais estreita. Valores menores produzem um código de barras mais compacto, enquanto valores maiores aumentam a legibilidade em scanners de baixa resolução.  
* `Pdf417.Columns` influencia a proporção do código de barras. Menos colunas deixam o código mais alto; mais colunas o achatam. Ajustar as colunas é a forma principal de **definir o tamanho do código de barras** sem alterar os dados codificados.

Após executar o código, você encontrará `Pdf417Basic.png` na pasta especificada. A imagem se parece com a captura de tela abaixo:

<img src="images/pdf417-basic.png" alt="create PDF417 barcode example showing basic barcode layout">

## Etapa 2: Criar um código de barras PDF417 compacto (modo truncate) com o mesmo tamanho

Às vezes você precisa de um código de barras mais curto para espaços limitados. O PDF417 oferece um modo *truncate* (compacto) que remove o padrão de parada e reduz a altura geral. A propriedade `Truncate` alterna esse comportamento.

```csharp
// Reuse the same data string.
var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Keep the same module width and column count for a fair size comparison.
compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Enable compact (truncate) mode – this removes the stop pattern.
compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version.
string compactPath = Path.Combine("YOUR_DIRECTORY", "CompactPdf417.png");
compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
```

**O que muda com `Truncate = true`?**

* O código de barras fica aproximadamente 15‑20 % mais curto verticalmente, o que é útil para etiquetas pequenas ou telas móveis.  
* Os dados permanecem totalmente recuperáveis; a maioria dos scanners modernos entende o modo truncate automaticamente.

O `CompactPdf417.png` resultante aparece como uma versão mais fina do código de barras básico.

## Etapa 3: Criar um código de barras Micro PDF417, ajustar colunas e salvá‑lo

Micro PDF417 é uma variante de alta densidade projetada para espaços muito pequenos (por exemplo, cartões de identidade). Ele suporta apenas 1‑4 colunas, e a biblioteca expõe a mesma propriedade `XDimension` para controle de tamanho.

```csharp
// Create a Micro PDF417 generator.
var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);

// Set module width – 2 pixels works well for most printers.
microPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Micro PDF417 allows only 1 to 4 columns; choose 4 for a more square shape.
microPdf417.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode.
string microPath = Path.Combine("YOUR_DIRECTORY", "MicroPdf417.png");
microPdf417.Save(microPath, BarCodeImageFormat.Png);
```

**Pontos chave para Micro PDF417**

* O enum `EncodeTypes.MicroPdf417` seleciona automaticamente a variante micro.  
* Como o símbolo é mais denso, pode ser necessário uma impressora com DPI mais alto (300 dpi ou mais) para manter a legibilidade.  
* Ajustar a contagem de colunas é a única alavanca de tamanho disponível; a biblioteca ainda respeita `XDimension`.

## Como definir o tamanho do código de barras para diferentes formatos de saída

Os exemplos acima usam PNG, mas o mesmo método `Save` funciona com JPEG, BMP ou TIFF. Se você precisar de uma dimensão de imagem específica (por exemplo, 300 × 150 px), combine `XDimension` com `ResolutionX`/`ResolutionY`:

```csharp
basicPdf417.Parameters.ImageResolution = 300; // DPI
basicPdf417.Parameters.Barcode.XDimension.Pixels = 3; // larger modules for higher DPI
basicPdf417.Save("Pdf417HighRes.jpg", BarCodeImageFormat.Jpeg);
```

Aumentar `ImageResolution` enquanto escala `XDimension` preserva a qualidade visual em impressões de alta resolução.

## Armadilhas comuns e dicas avançadas

| Problema | Por que acontece | Solução |
|----------|------------------|---------|
| Código de barras aparece borrado na tela | DPI baixo combinado com XDimension pequeno | Aumente `ImageResolution` e/ou `XDimension.Pixels` |
| Scanner não lê modo truncate | Firmware de scanner antigo não oferece suporte | Use o modo completo (não truncado) para hardware legado |
| Micro PDF417 ilegível | Impresso com < 300 dpi ou contraste insuficiente | Imprima em papel fosco a 300 dpi ou mais, garantindo fundo escuro |
| Arquivo de saída corrompido | Falta de permissão de gravação na pasta de destino | Verifique se `YOUR_DIRECTORY` existe e tem permissão de escrita |

**Dica profissional:** Sempre gere o código de barras como PNG quando precisar de qualidade sem perdas para processamento posterior (por exemplo, incorporação em PDFs). PNG preserva os valores de pixel exatos, enquanto JPEG introduz artefatos de compressão que podem afetar a legibilidade do código.

## Exemplo completo, pronto para execução

Abaixo está um aplicativo console completo que demonstra os três tipos de código de barras em uma única execução. Copie o código para um novo projeto console .NET e execute.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // The text to encode – change this to whatever data you need.
        const string data = "Sample text for PDF417 barcode";

        // Directory where images will be saved.
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // ---------- Basic PDF417 ----------
        var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        string basicPath = Path.Combine(outputDir, "Pdf417Basic.png");
        basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Basic PDF417 saved to {basicPath}");

        // ---------- Compact (Truncate) PDF417 ----------
        var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;
        string compactPath = Path.Combine(outputDir, "CompactPdf417.png");
        compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Compact PDF417 saved to {compactPath}");

        // ---------- Micro PDF417 ----------
        var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);
        microPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        microPdf417.Parameters.Barcode.Pdf417.Columns = 4; // 1‑4 allowed
        string microPath = Path.Combine(outputDir, "MicroPdf417.png");
        microPdf417.Save(microPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Micro PDF417 saved to {microPath}");
    }
}
```

**Saída esperada**

Ao executar o programa, três arquivos PNG são criados dentro da pasta `Barcodes`:

* `Pdf417Basic.png` – um código de barras PDF417 padrão com três colunas.  
* `CompactPdf417.png` – os mesmos dados no modo truncate (compacto), ligeiramente mais curto.  
* `MicroPdf417.png` – uma variante Micro PDF417 de alta densidade com quatro colunas.

Abra qualquer imagem em um visualizador; você deverá ver o distintivo padrão empilhado.

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Create PDF417 Barcode Metadata in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}