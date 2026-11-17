---
category: general
date: 2026-11-17
description: Aprenda a gerar código de barras PDF417, definir o tamanho do código
  de barras e renderizar o código de barras em imagem usando C#. Guia completo passo
  a passo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- render barcode to image
- how to set barcode size
language: pt
lastmod: 2026-11-17
og_description: Gerar código de barras PDF417 em C# e renderizar o código de barras
  em imagem. Siga este guia para definir o tamanho do código de barras e salvar um
  arquivo PNG.
og_image_alt: Screenshot of a generated PDF417 barcode saved as a PNG image
og_title: Gerar código de barras PDF417 e renderizar como PNG – Guia C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to generate PDF417 barcode, set barcode size, and render
    barcode to image using C#. Complete step‑by‑step guide.
  headline: How to generate PDF417 barcode and render it as PNG
  type: TechArticle
- description: Learn how to generate PDF417 barcode, set barcode size, and render
    barcode to image using C#. Complete step‑by‑step guide.
  name: How to generate PDF417 barcode and render it as PNG
  steps:
  - name: Open the PNG file in any image viewer.
    text: Open the PNG file in any image viewer.
  - name: Use a smartphone barcode scanning app that supports PDF417 (e.g., Google
      Lens, QR & Barcode Scanner).
    text: Use a smartphone barcode scanning app that supports PDF417 (e.g., Google
      Lens, QR & Barcode Scanner).
  - name: Scan the image; the app should return the text *Layout demo*.
    text: Scan the image; the app should return the text *Layout demo*.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- image generation
title: Como gerar código de barras PDF417 e renderizá-lo como PNG
url: /pt/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-and-render-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar código de barras PDF417 e renderizá-lo como PNG

Se você precisa **gerar código de barras PDF417** em uma aplicação .NET, este tutorial mostra exatamente como fazer. Você verá como definir o tamanho do código de barras, configurar o layout e **renderizar o código de barras para imagem** com apenas algumas linhas de código C#.

Gerar um código de barras PDF417 é comum quando você deseja codificar grandes quantidades de dados para escaneamento em dispositivos móveis ou impressoras. Ao final deste guia, você terá um arquivo PNG pronto‑para‑uso que pode ser incorporado em relatórios, e‑mails ou páginas da web.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

- .NET 6.0 SDK ou posterior instalado  
- Um IDE C# como o Visual Studio 2022 (qualquer editor funciona)  
- O pacote NuGet **Aspose.BarCode for .NET** (ou qualquer biblioteca compatível que forneça `BarcodeGenerator`)  

Você pode adicionar o pacote com:

```bash
dotnet add package Aspose.BarCode
```

## Passo 1: Criar um projeto de console C#

Primeiro, configure uma aplicação de console mínima que hospedará o código de geração do código de barras.

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
            // The barcode generation logic will be placed here.
        }
    }
}
```

> **Dica profissional:** Mantenha o método `Main` curto e delegue o trabalho pesado para métodos auxiliares. Isso melhora a legibilidade e facilita os testes unitários.

## Passo 2: Gerar código de barras PDF417 com tamanho personalizado

Agora vamos **gerar código de barras PDF417** e especificar o tamanho do módulo (dimensão X). A dimensão X controla quão largo cada quadradinho do código de barras é, definindo efetivamente o tamanho geral do código.

```csharp
static void GeneratePdf417(string text, string outputPath)
{
    // Initialize a PDF417 barcode generator with the desired text
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, text);

    // Set the size of a single barcode module (X‑dimension) in pixels
    generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module

    // Optional: adjust the number of columns and rows for layout control
    generator.Parameters.Barcode.Pdf417.Columns = 4;   // 4 columns
    generator.Parameters.Barcode.Pdf417.Rows    = 9;   // 9 rows

    // Render the barcode and save it as a PNG image
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

### Por que definir a X‑dimension?

A etapa **como definir o tamanho do código de barras** é importante porque uma dimensão X muito pequena pode tornar o código de barras ilegível em scanners de baixa resolução, enquanto um valor muito grande desperdiça espaço. Um valor de `2` pixels funciona bem na maioria das telas e cenários de impressão.

## Passo 3: Chamar o método de geração a partir do `Main`

Una tudo invocando `GeneratePdf417` com o texto desejado e o local de saída.

```csharp
static void Main(string[] args)
{
    string barcodeText = "Layout demo";
    string outputFile = @"C:\Barcodes\LayoutPdf417.png";

    GeneratePdf417(barcodeText, outputFile);

    Console.WriteLine($"PDF417 barcode saved to {outputFile}");
}
```

Executar o programa cria `LayoutPdf417.png` contendo o código de barras:

![Código de barras PDF417 gerado](/images/layout-pdf417.png "Código de barras PDF417 gerado pelo código do tutorial"){: .align-center alt="Código de barras PDF417 gerado salvo como PNG"}

> **Saída esperada:** Um arquivo PNG com tamanho aproximadamente 200 × 100 px (dependendo das configurações de colunas/linhas) que exibe um padrão PDF417 claro pronto para escaneamento.

## Passo 4: Verificar se o código de barras funciona

Para garantir que o código de barras seja válido:

1. Abra o arquivo PNG em qualquer visualizador de imagens.  
2. Use um aplicativo de escaneamento de código de barras para smartphone que suporte PDF417 (por exemplo, Google Lens, QR & Barcode Scanner).  
3. Escaneie a imagem; o aplicativo deve retornar o texto *Layout demo*.

Se a leitura falhar, verifique novamente a dimensão X e os valores de coluna/linha — módulos maiores melhoram a legibilidade em câmeras de baixa resolução.

## Variações comuns e casos extremos

| Cenário | Ajuste |
|----------|------------|
| **Mais dados** (e.g., uma URL) | Aumente `Columns` ou `Rows` para acomodar codewords extras. |
| **Impressão de alta resolução** | Eleve `XDimension.Pixels` para 3‑4 px para barras mais nítidas. |
| **Fundo transparente** | Use `generator.Save(outputPath, BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })`. |
| **Formato de imagem diferente** | Substitua `BarCodeImageFormat.Png` por `Jpeg` ou `Bmp` conforme necessário. |

Essas variações respondem à pergunta **como gerar PDF417** para diferentes requisitos, mantendo a lógica central idêntica.

## Conclusão

Agora você sabe como **gerar código de barras PDF417**, **definir o tamanho do código de barras** e **renderizar o código de barras para imagem** usando C#. O exemplo completo e executável cria um arquivo PNG que pode ser incorporado onde precisar de um código de barras legível por máquina.

Em seguida, explore tópicos relacionados como **incorporar o PNG em um PDF** (procure *render barcode to PDF*), ou **gerar outros códigos de barras 2‑D** como QR codes. Ajuste os parâmetros de layout para se adequar ao design da sua UI e experimente opções de cor para branding.

Feliz codificação, e deixe seus códigos de barras fazerem o trabalho pesado!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar código de barras PDF417 em C# – guia completo passo a passo](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Como gerar código de barras micro PDF417 em C# – guia passo a passo](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [Como definir o nível de erro no código de barras PDF417 – guia completo](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}