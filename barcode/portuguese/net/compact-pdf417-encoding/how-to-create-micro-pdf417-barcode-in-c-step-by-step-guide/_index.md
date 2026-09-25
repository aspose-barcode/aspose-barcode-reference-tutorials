---
category: general
date: 2026-08-22
description: Aprenda a criar um código de barras micro PDF417 em C# e gerar uma imagem
  PNG do código de barras. Inclui definir as dimensões do código de barras e salvar
  o arquivo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- how to generate barcode png
- create barcode image c#
- how to set barcode dimensions
language: pt
lastmod: 2026-08-22
og_description: Crie um código de barras micro PDF417 em C# e exporte-o como PNG.
  Siga este guia para definir as dimensões do código de barras e gerar rapidamente
  uma imagem do código de barras.
og_image_alt: Screenshot of a micro PDF417 barcode generated with C# code
og_title: Crie código de barras micro PDF417 em C# – tutorial completo de codificação
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  headline: How to create micro PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  name: How to create micro PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Build the project: `dotnet build`.'
    text: 'Build the project: `dotnet build`.'
  - name: 'Execute: `dotnet run`.'
    text: 'Execute: `dotnet run`.'
  - name: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
    text: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
  type: HowTo
tags:
- barcode
- C#
- MicroPdf417
- image generation
title: Como criar código de barras micro PDF417 em C# – guia passo a passo
url: /pt/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar código de barras micro PDF417 em C# – guia passo a passo

Se você precisa **criar código de barras micro PDF417** para um sistema de bilhetagem, etiqueta de inventário ou leitura móvel, este tutorial mostra exatamente como fazer. Você verá o programa completo em C# que gera um PNG de código de barras, aprenderá a definir as dimensões do código de barras e entenderá cada opção de configuração.

Ao final deste guia você será capaz de gerar uma imagem de código de barras em alta resolução, personalizar a dimensão X, escolher a quantidade de colunas e salvar o resultado como um arquivo PNG — tudo com poucas linhas de código.

## O que você precisará

- .NET 6.0 SDK ou superior (o código funciona com .NET Core e .NET Framework)
- Visual Studio 2022 ou qualquer IDE compatível com C#
- O pacote NuGet **Aspose.BarCode for .NET** (ou qualquer biblioteca que suporte `EncodeTypes.MicroPdf417`)
- Familiaridade básica com a sintaxe C#

> **Dica profissional:** A edição comunitária gratuita do Aspose.BarCode é suficiente para desenvolvimento e testes. Para produção, obtenha uma licença para remover as marcas d'água de avaliação.

## Etapa 1: Instalar a biblioteca de código de barras

Abra um terminal na pasta do seu projeto e execute:

```bash
dotnet add package Aspose.BarCode
```

Isso adiciona o assembly `Aspose.BarCode`, que fornece a classe `BarcodeGenerator` usada para **criar imagens de código de barras C#**.

## Etapa 2: Inicializar o gerador – criar código de barras micro PDF417

A primeira linha executável cria uma instância de `BarcodeGenerator` configurada para a simbologia Micro PDF417 e fornece os dados que você deseja codificar.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize a Micro PDF417 barcode generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");
```

*Por que isso importa*: O enum `EncodeTypes.MicroPdf417` indica à biblioteca que deve usar a versão compacta do PDF417, ideal para etiquetas pequenas e telas móveis.

## Etapa 3: Como definir as dimensões do código de barras em C#

Ajustar a largura do módulo (dimensão X) controla a densidade visual do código de barras. Um valor menor produz uma imagem mais nítida, enquanto um valor maior facilita a leitura à distância.

```csharp
        // Step 3: Set the X‑dimension (module width) to 2 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Por que você deve definir dimensões**: Sem ajustar a dimensão X, o valor padrão pode gerar um código de barras que parece borrado quando renderizado em DPI alto. Definir para 2 pixels é um bom equilíbrio para a maioria das leituras baseadas em tela.

## Etapa 4: Escolher o número de colunas – controlando a largura do código de barras

O Micro PDF417 permite entre 1 e 4 colunas. Mais colunas comprimem os dados horizontalmente, reduzindo a largura total da imagem.

```csharp
        // Step 4: Define the number of columns (allowed values: 1‑4)
        generator.Parameters.Barcode.Pdf417.Columns = 4;
```

*Caso extremo*: Se você solicitar 5 colunas, a biblioteca lançará uma `ArgumentOutOfRangeException`. Sempre permaneça dentro do intervalo documentado.

## Etapa 5: Como gerar PNG do código de barras – salvando a imagem

Agora você pode exportar o código de barras gerado para um arquivo PNG. PNG preserva qualidade sem perdas, o que é essencial para leituras confiáveis.

```csharp
        // Step 5: Save the generated barcode as a PNG image
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "MicroPdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

Ao executar o programa, você verá uma mensagem no console confirmando o local do arquivo. O `MicroPdf417.png` resultante se parece com isto:

![Captura de tela mostrando um código de barras micro PDF417 gerado com C#](micro-pdf417-example.png "Código de barras micro PDF417 gerado")

*Texto alternativo da imagem*: **código de barras micro PDF417 gerado em C#** – demonstra a saída final após aplicar as dimensões e configurações de coluna.

## Etapa 6: Executar e verificar a saída

1. Compile o projeto: `dotnet build`.
2. Execute: `dotnet run`.
3. Abra `MicroPdf417.png` na sua área de trabalho e escaneie-o com um aplicativo de leitura de códigos de barras móvel.

Você deverá ver o texto **“Sample text”** decodificado. Se o leitor relatar um erro, verifique novamente a dimensão X e a contagem de colunas – valores extremos podem tornar o código de barras denso demais para alguns dispositivos.

## Variações comuns e solução de problemas

| Situação | Ajuste |
|-----------|------------|
| **Precisa de um código de barras maior para impressoras de baixa resolução** | Aumente `XDimension.Pixels` para 3 ou 4. |
| **Deseja um código de barras mais alto sem mudar a largura** | Defina `generator.Parameters.Barcode.Pdf417.Rows` (intervalo de linhas 3‑90). |
| **Gerando múltiplos códigos de barras em um loop** | Reutilize a mesma instância de `BarcodeGenerator` e altere apenas `CodeText` antes de cada `Save`. |
| **Salvando como JPEG em vez de PNG** | Substitua `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg`. |
| **Executando no .NET Framework 4.7** | O mesmo código funciona; basta referenciar o `Aspose.BarCode.dll` apropriado. |

## Listagem completa do código (executável)

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialize a Micro PDF417 barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");

            // Set the X‑dimension (module width) to 2 pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns (allowed values: 1‑4)
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

**Saída esperada** – um arquivo PNG de 200 × 100 pixels contendo um código de barras Micro PDF417 nítido que decodifica para “Sample text”.

## Conclusão

Agora você sabe como **criar código de barras micro PDF417** em C#, **definir dimensões do código de barras** e **gerar uma imagem PNG** do código de barras. O exemplo completo demonstra cada passo necessário — da instalação da biblioteca ao salvamento do arquivo final — para que você possa incorporar a geração de códigos de barras diretamente em suas próprias aplicações.

Em seguida, explore tópicos relacionados como **criar códigos QR com Aspose.BarCode**, **personalizar cores** ou **incorporar códigos de barras em documentos PDF**. Cada um desses se baseia nos mesmos fundamentos do `BarcodeGenerator` abordados aqui.

Sinta-se à vontade para experimentar diferentes strings de dados, contagens de colunas e valores de dimensão X para adequar ao seu ambiente de leitura específico. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate PDF417 Barcode – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to create Aztec barcode with Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}