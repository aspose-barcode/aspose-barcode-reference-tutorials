---
category: general
date: 2026-11-27
description: Aprenda a gerar código de barras PDF417 em C# usando Aspose.BarCode.
  Ajuste as dimensões, defina a contagem de colunas e salve como PNG em poucas linhas
  de código.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode C#
- PDF417 barcode dimensions
- barcode image PNG
- BarcodeGenerator usage
language: pt
lastmod: 2026-11-27
og_description: Gere código de barras PDF417 em C# instantaneamente. Este tutorial
  mostra como configurar dimensões, contagem de colunas e salvar o resultado como
  uma imagem PNG.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: Gerar código de barras PDF417 em C# – guia rápido com Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  headline: How to generate PDF417 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  name: How to generate PDF417 barcode in C# with Aspose.BarCode
  steps:
  - name: Why each line matters
    text: '* **BarcodeGenerator** – the core class that creates a barcode image. Passing
      `EncodeTypes.Pdf417` selects the PDF417 symbology. * **XDimension.Pixels** –
      determines the smallest bar width. Smaller values shrink the image; larger values
      improve readability on low‑resolution scanners. * **Pdf417.Colu'
  - name: Changing the encoded data
    text: 'Replace the second argument of `BarcodeGenerator` with any UTF‑8 string,
      e.g.:'
  - name: Adjusting image size without losing quality
    text: 'If you need a larger image for printing, increase `XDimension.Pixels`:'
  - name: Handling very long inputs
    text: 'PDF417 can encode up to 1 850 characters. For extremely long strings, you
      may want to increase the column count:'
  - name: Saving in other formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the format like
      this:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Como gerar código de barras PDF417 em C# com Aspose.BarCode
url: /pt/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar código de barras PDF417 em C# com Aspose.BarCode

Se você precisa **gerar código de barras PDF417** em uma aplicação .NET, este guia mostra uma solução concisa e completa. Você verá como criar o código de barras, ajustar seu tamanho e gravar o resultado em um arquivo PNG — tudo com a biblioteca Aspose.BarCode.

Gerar um código de barras PDF417 é comum quando é necessário codificar grandes quantidades de dados para leitura em dispositivos móveis, cartões de embarque ou etiquetas de inventário. Ao final deste tutorial você terá um programa de console pronto‑para‑executar que produz uma imagem PNG de alta qualidade.

## Pré-requisitos

* .NET 6.0 SDK ou posterior instalado  
* Uma versão recente do **Aspose.BarCode for .NET** (o pacote NuGet `Aspose.BarCode`)  
* Uma IDE ou editor (Visual Studio, VS Code, Rider, etc.)  

O código funciona no Windows, Linux e macOS porque o Aspose.BarCode é multiplataforma.

## Etapa 1: Criar um novo projeto de console

Abra um terminal e execute:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Isso cria um projeto C# mínimo chamado **Pdf417Demo** e adiciona a dependência `Aspose.BarCode`.

## Etapa 2: Escrever o código de geração do código de barras

Abra **Program.cs** e substitua seu conteúdo pelo seguinte:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Create a PDF417 barcode generator with the desired text
            // EncodeTypes.Pdf417 tells Aspose.BarCode which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417, "Sample text for PDF417 barcode");

            // 2️⃣ Adjust barcode dimensions and column count
            // XDimension controls the width of a single module (pixel size).
            // Setting it to 2 pixels yields a compact yet readable barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Columns define how many data columns the barcode will have.
            // A value of 3 works well for short strings; increase for longer data.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Optional: increase error correction level for more robust scanning.
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 2;

            // 3️⃣ Save the generated barcode as a PNG file
            // The output path can be absolute or relative to the project folder.
            string outputPath = "Pdf417Basic.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to '{outputPath}'.");
        }
    }
}
```

### Por que cada linha é importante

* **BarcodeGenerator** – a classe principal que cria a imagem do código de barras. Passar `EncodeTypes.Pdf417` seleciona a simbologia PDF417.  
* **XDimension.Pixels** – determina a menor largura de barra. Valores menores reduzem a imagem; valores maiores melhoram a legibilidade em scanners de baixa resolução.  
* **Pdf417.Columns** – controla o número de colunas de dados. Mais colunas produzem um código de barras mais curto, porém mais alto; menos colunas o tornam mais largo.  
* **ErrorCorrectionLevel** – níveis mais altos adicionam dados redundantes, tornando o código de barras tolerante a danos ao custo de tamanho.  
* **Save(..., BarCodeImageFormat.Png)** – grava a imagem no disco no formato PNG, um formato sem perdas ideal para processamento adicional ou incorporação em documentos.

## Etapa 3: Compilar e executar o programa

Do terminal, execute:

```bash
dotnet run
```

Você deverá ver:

```
PDF417 barcode saved to 'Pdf417Basic.png'.
```

Um arquivo chamado **Pdf417Basic.png** aparece na pasta do projeto. Ao abri‑lo, mostra um código de barras PDF417 nítido que codifica o texto *“Sample text for PDF417 barcode”*.

![Código de barras PDF417 gerado salvo como arquivo PNG](pdf417-barcode-example.png "Código de barras PDF417 gerado em formato PNG")

*Texto alternativo da imagem: captura de tela de um código de barras PDF417 gerado salvo como arquivo PNG, demonstrando o resultado do tutorial de geração de código de barras PDF417.*

## Etapa 4: Variações comuns e casos extremos

### Alterando os dados codificados

Substitua o segundo argumento de `BarcodeGenerator` por qualquer string UTF‑8, por exemplo:

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "https://example.com/checkout?order=12345")
```

O gerador divide automaticamente os dados entre linhas e colunas.

### Ajustando o tamanho da imagem sem perder qualidade

Se precisar de uma imagem maior para impressão, aumente `XDimension.Pixels`:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // double the module width
```

### Lidando com entradas muito longas

PDF417 pode codificar até 1 850 caracteres. Para strings extremamente longas, talvez você queira aumentar o número de colunas:

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 5; // more columns, less height
```

Se o conteúdo exceder a capacidade máxima, o Aspose.BarCode lança uma `ArgumentException`. Envolva o código de geração em um bloco try‑catch para apresentar uma mensagem de erro amigável.

### Salvando em outros formatos

Aspose.BarCode suporta BMP, JPEG, TIFF e SVG. Altere o formato assim:

```csharp
generator.Save("Pdf417Vector.svg", BarCodeImageFormat.Svg);
```

## Etapa 5: Verificar o código de barras

Você pode confirmar que o código de barras é válido escaneando‑o com qualquer aplicativo leitor de PDF417 (por exemplo, aplicativos de câmera de smartphone que suportam leitura de códigos de barras). O texto decodificado deve corresponder à string que você passou ao gerador.

Se a leitura falhar:

* Certifique‑se de que a imagem não está comprimida (use PNG ou SVG sem perdas).  
* Verifique se `ErrorCorrectionLevel` está alto o suficiente para o ambiente pretendido.  
* Verifique se as dimensões do código de barras são adequadas para a resolução do scanner.

## Conclusão

Agora você sabe como **gerar código de barras PDF417** em C# usando Aspose.BarCode, personalizar suas dimensões, definir o número de colunas e exportar o resultado como uma imagem PNG. Essa abordagem funciona para uma ampla variedade de cenários, desde bilhetagem móvel até gerenciamento de inventário.

Em seguida, você pode explorar:

* **Leitura** de um código de barras PDF417 com `BarCodeReader`.  
* Gerar outras simbologias como QR Code ou DataMatrix.  
* Incorporar o PNG em PDFs, relatórios ou páginas web.  

Sinta‑se à vontade para experimentar diferentes níveis de correção de erro, formatos de imagem e cargas de dados para atender às necessidades do seu projeto. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar código de barras PDF417 em C# com Aspose.BarCode BarcodeGenerator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/)
- [Como gerar código de barras PDF417 e renderizá‑lo como PNG](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-and-render-it-as-png/)
- [Como gerar código de barras PDF417 em C# e definir o tamanho do código de barras](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}