---
category: general
date: 2026-10-21
description: Gere uma imagem de código de barras databar expanded stacked em C# usando
  BarcodeGenerator. Siga este guia passo a passo para criar imagens de códigos de
  barras, personalizar linhas e colunas e exportar arquivos PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- barcode generator c#
- how to generate databar
- create databar barcode
language: pt
lastmod: 2026-10-21
og_description: Gere um código de barras databar expandido empilhado em C# com este
  tutorial. Aprenda a usar o BarcodeGenerator, definir linhas e colunas e salvar imagens
  PNG.
og_image_alt: Sample databar expanded stacked barcode image generated with C#
og_title: Gerar um código de barras Databar Expanded Stacked em C# – guia completo
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  headline: How to generate a databar expanded stacked barcode in C#
  type: TechArticle
- description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  name: How to generate a databar expanded stacked barcode in C#
  steps:
  - name: Basic barcode generation
    text: The simplest way to generate a **databar expanded stacked** image is to
      instantiate `BarcodeGenerator` with the desired `EncodeTypes` value and a plain
      text payload.
  - name: Customizing columns – create databar barcode with 4 columns
    text: You can control the number of columns using the `Parameters.Barcode.DataBar.Columns`
      property. The following example creates a barcode with **4 columns** while keeping
      the default row count.
  - name: Customizing rows – create databar barcode with 3 rows
    text: Similarly, you can adjust the row count via `Parameters.Barcode.DataBar.Rows`.
      The code below generates a barcode with **3 rows** and the default column count
      (4).
  - name: Exporting to other formats
    text: 'If you need a different image type (e.g., JPEG, BMP, or SVG), replace `BarCodeImageFormat.Png`
      with the appropriate enum value:'
  - name: Saving to a memory stream
    text: 'Sometimes you want to embed the barcode directly into a web response or
      a PDF without touching the file system. Use a `MemoryStream`:'
  - name: Handling invalid input
    text: 'The `BarcodeGenerator` validates the payload against the chosen symbology.
      If the data contains prohibited characters, an `ArgumentException` is thrown.
      Wrap the generation code in a try‑catch block to provide a friendly error message:'
  - name: Scaling the barcode image
    text: 'You can change the image size without altering the encoded data by setting
      `Parameters.Image.Width` and `Parameters.Image.Height`:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Como gerar um código de barras Databar Expanded Stacked em C#
url: /pt/python-java/general/how-to-generate-a-databar-expanded-stacked-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar um código de barras databar expanded stacked em C#

Se você precisar gerar um **databar expanded stacked** barcode em C#, este guia mostra como fazer. A simbologia databar expanded stacked é ideal para codificar grandes quantidades de dados de forma compacta, e você pode criar a imagem com apenas algumas linhas de código. Você também aprenderá como **gerar arquivos de imagem de código de barras** em diferentes formatos e personalizar linhas ou colunas para adequar ao seu ambiente de escaneamento.

Este tutorial cobre tudo o que você precisa para começar a produzir códigos de barras databar: instalar a biblioteca necessária, preparar a pasta de saída, criar o código de barras com linhas ou colunas personalizadas e salvar o resultado como um arquivo PNG. Ao final, você será capaz de **criar imagens de código de barras databar** programaticamente e adaptar o código para outros formatos de imagem ou cenários de tempo de execução.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou posterior (o código também funciona com .NET Core 3.1 e .NET Framework 4.7+)
* Um ambiente de desenvolvimento como Visual Studio 2022, Visual Studio Code ou Rider
* Acesso à internet para instalar o pacote NuGet **Barcode Generator C#** (Aspose.BarCode for .NET)

> **Dica profissional:** Se você estiver usando um pipeline CI/CD, adicione a referência ao pacote NuGet no seu arquivo de projeto para que as compilações sejam reproduzíveis.

## Instalar a biblioteca Barcode Generator C#

O exemplo usa a biblioteca Aspose.BarCode, que fornece a classe `BarcodeGenerator` e a enumeração `EncodeTypes.DatabarExpandedStacked`.

```bash
dotnet add package Aspose.BarCode
```

O comando adiciona a versão estável mais recente ao seu projeto. Após a instalação, você pode importar o namespace nos seus arquivos C#:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

## Preparar a pasta de saída

Um caminho de arquivo confiável evita erros em tempo de execução quando a biblioteca tenta gravar a imagem. O código a seguir cria o diretório caso ele não exista:

```csharp
using System;
using System.IO;

// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);
```

> **Por que isso importa:** Tentar salvar em um diretório inexistente lança uma `IOException`. Criar a pasta antecipadamente torna o código robusto tanto para desenvolvimento local quanto para ambientes de produção.

## Gerando uma imagem de código de barras databar expanded stacked

### Geração básica de código de barras

A maneira mais simples de gerar uma imagem **databar expanded stacked** é instanciar `BarcodeGenerator` com o valor desejado de `EncodeTypes` e uma carga útil de texto simples.

```csharp
// Create a barcode that encodes a long numeric string
var basicGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "01234567890123456789");

// Save the barcode as PNG
basicGenerator.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
    BarCodeImageFormat.Png);
```

Executar o trecho produz `DatabarBasic.png` na pasta *Barcodes*. A imagem contém um símbolo padrão databar expanded stacked com o layout padrão (4 colunas × 4 linhas).

### Personalizando colunas – criar código de barras databar com 4 colunas

Você pode controlar o número de colunas usando a propriedade `Parameters.Barcode.DataBar.Columns`. O exemplo a seguir cria um código de barras com **4 colunas** mantendo a contagem padrão de linhas.

```csharp
// Step 1: Define a generator with custom column count
var columnGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the column count to 4 (default rows = 4)
columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the image
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
    BarCodeImageFormat.Png);
```

O arquivo resultante, **DatabarCols4.png**, tem a seguinte aparência:

![Código de barras databar expanded stacked com 4 colunas](databar_cols4.png "Código de barras databar expanded stacked com 4 colunas – gerado com C#")

*Texto alternativo da imagem (og_image_alt):* **Exemplo de imagem de código de barras databar expanded stacked gerada com C#** – isso satisfaz o requisito de SEO para texto alternativo de imagem.

### Personalizando linhas – criar código de barras databar com 3 linhas

Da mesma forma, você pode ajustar a contagem de linhas via `Parameters.Barcode.DataBar.Rows`. O código abaixo gera um código de barras com **3 linhas** e a contagem padrão de colunas (4).

```csharp
// Step 2: Define a generator with custom row count
var rowGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the row count to 3 (default columns = 4)
rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

// Save the image
rowGenerator.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
    BarCodeImageFormat.Png);
```

O arquivo **DatabarRows3.png** contém um símbolo databar expanded stacked que é ligeiramente mais curto verticalmente, o que pode ser útil para rótulos com espaço limitado.

### Exportando para outros formatos

Se precisar de um tipo de imagem diferente (por exemplo, JPEG, BMP ou SVG), substitua `BarCodeImageFormat.Png` pelo valor da enumeração correspondente:

```csharp
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
    BarCodeImageFormat.Jpeg);
```

A biblioteca também oferece suporte a formatos vetoriais como SVG, que são ideais para impressão em alta resolução.

## Cenários avançados

### Salvando em um fluxo de memória

Às vezes você deseja incorporar o código de barras diretamente em uma resposta web ou em um PDF sem tocar no sistema de arquivos. Use um `MemoryStream`:

```csharp
using System.IO;

// Generate barcode into a memory stream
using var ms = new MemoryStream();
columnGenerator.Save(ms, BarCodeImageFormat.Png);

// Reset stream position before reading
ms.Position = 0;

// Example: return the stream as a file download in ASP.NET Core
// return File(ms.ToArray(), "image/png", "databar.png");
```

### Tratamento de entrada inválida

O `BarcodeGenerator` valida a carga útil em relação à simbologia escolhida. Se os dados contiverem caracteres proibidos, uma `ArgumentException` é lançada. Envolva o código de geração em um bloco try‑catch para fornecer uma mensagem de erro amigável:

```csharp
try
{
    var gen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "INVALID*DATA");
    gen.Save(Path.Combine(outputFolder, "Invalid.png"), BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

### Redimensionando a imagem do código de barras

Você pode alterar o tamanho da imagem sem modificar os dados codificados definindo `Parameters.Image.Width` e `Parameters.Image.Height`:

```csharp
columnGenerator.Parameters.Image.Width = 300;   // pixels
columnGenerator.Parameters.Image.Height = 150; // pixels
columnGenerator.Save(Path.Combine(outputFolder, "DatabarLarge.png"),
    BarCodeImageFormat.Png);
```

O redimensionamento é útil quando o código de barras deve atender a um requisito específico de DPI para os scanners.

## Exemplo completo funcional

Abaixo está um aplicativo de console completo, pronto para ser executado, que demonstra todas as etapas discutidas:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Prepare output folder
            string outputFolder = Path.Combine(
                Environment.CurrentDirectory, "Barcodes");
            Directory.CreateDirectory(outputFolder);

            // 2️⃣ Generate basic barcode
            var basic = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "01234567890123456789");
            basic.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
                BarCodeImageFormat.Png);

            // 3️⃣ Generate barcode with 4 columns
            var colGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            colGen.Parameters.Barcode.DataBar.Columns = 4;
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
                BarCodeImageFormat.Png);

            // 4️⃣ Generate barcode with 3 rows
            var rowGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            rowGen.Parameters.Barcode.DataBar.Rows = 3;
            rowGen.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
                BarCodeImageFormat.Png);

            // 5️⃣ Export to JPEG as an extra format
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
                BarCodeImageFormat.Jpeg);

            Console.WriteLine("All barcode images have been generated in:");
            Console.WriteLine(outputFolder);
        }
    }
}
```

**Saída esperada**

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como definir colunas para um código de barras Databar Expanded Stacked – guia completo em C#](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [Como criar um exemplo de gerador de código de barras em C# com DataBar Expanded Stacked](/barcode/english/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/)
- [Guia de código de barras databar expanded stacked – como gerar e dimensionar em C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}