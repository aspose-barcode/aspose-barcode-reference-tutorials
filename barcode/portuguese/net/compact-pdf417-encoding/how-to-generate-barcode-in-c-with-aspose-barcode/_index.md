---
category: general
date: 2026-09-16
description: Aprenda como gerar código de barras e definir o tamanho do código de
  barras em C#. Guia passo a passo usando Aspose.BarCode para criar uma imagem Micro
  PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- set barcode size
language: pt
lastmod: 2026-09-16
og_description: Como gerar código de barras em C# e definir o tamanho do código de
  barras com Aspose.BarCode. Siga este tutorial conciso para produzir um PNG Micro
  PDF417.
og_image_alt: Example output showing how to generate barcode using C#
og_title: Como gerar código de barras em C# – guia completo do Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to generate barcode and set barcode size in C#. Step‑by‑step
    guide using Aspose.BarCode to create a Micro PDF417 image.
  headline: How to generate barcode in C# with Aspose.BarCode
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Como gerar código de barras em C# com Aspose.BarCode
url: /pt/net/compact-pdf417-encoding/how-to-generate-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar código de barras em C# com Aspose.BarCode

Se você precisa saber **como gerar código de barras** em um projeto .NET, este tutorial o guiará por todo o processo usando a biblioteca Aspose.BarCode. Você também aprenderá como **definir o tamanho do código de barras** para que a imagem se ajuste à sua UI ou aos requisitos de impressão.

O guia cobre tudo, desde a instalação do pacote NuGet até a configuração de um símbolo Micro PDF417 e a gravação dele como um arquivo PNG. Ao final, você terá um exemplo de código executável que pode ser inserido em qualquer aplicação console ou web em C#.

## O que você precisará

- .NET 6.0 ou superior (o código também funciona com .NET Framework 4.6+)
- Visual Studio 2022 ou qualquer IDE que suporte C#
- Acesso à internet para baixar o pacote NuGet **Aspose.BarCode**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Familiaridade básica com a sintaxe C#

## Como gerar código de barras com Aspose.BarCode

O primeiro passo é criar uma instância de `BarcodeGenerator` que saiba qual simbologia usar e quais dados codificar.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a Micro PDF417 barcode generator with the data to encode
var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Micro data");
```

**Por que isso importa:** `EncodeTypes.MicroPdf417` indica à biblioteca que ela deve produzir uma variante compacta do PDF417, ideal para rótulos pequenos ou áreas semelhantes a QR‑code. A string `"Micro data"` torna‑se a carga útil legível por humanos incorporada ao código de barras.

## Definir tamanho e dimensões do código de barras

Um código de barras legível deve ter a dimensão de módulo (X) correta e colunas suficientes para conter os dados. É aqui que você **define o tamanho do código de barras**.

```csharp
// Step 2: Define the module size (X dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Set the maximum number of columns for the Micro PDF417 symbol
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

- **XDimension** controla a largura da barra mais estreita (o “módulo”). Um valor de `2` pixels funciona bem para exibição em tela; aumente-o para impressão em alta resolução.
- **Pdf417.Columns** limita o número de colunas verticais. O formato Micro PDF417 suporta até 7 colunas; `4` oferece um tamanho equilibrado sem sacrificar a capacidade de dados.

> **Dica profissional:** Se a imagem gerada parecer muito pequena, aumente `XDimension.Pixels` para `3` ou `4`. Por outro lado, para espaços de UI densos, você pode reduzi‑lo para `1`, mas certifique‑se de que o scanner que você pretende usar ainda consiga ler o símbolo.

## Salvar a imagem do código de barras

Depois de configurar o tamanho, basta instruir o gerador a gravar a imagem no disco.

```csharp
// Step 4: Save the generated barcode as a PNG image
barcodeGenerator.Save("micro.png", BarCodeImageFormat.Png);
```

O método `Save` aceita qualquer formato suportado pelo Aspose.BarCode (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`). PNG é sem perdas, preservando as bordas nítidas necessárias para uma leitura confiável.

**Saída esperada:** Um arquivo chamado `micro.png` aparecerá no diretório de trabalho do projeto. Ao abri‑lo, você verá um pequeno código de barras Micro PDF417 de alto contraste, pronto para teste com qualquer scanner padrão.

## Exemplo completo

Juntando todas as peças, você obtém um programa autocontido que pode ser executado imediatamente.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for Micro PDF417
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Micro data");

            // Set size parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
            generator.Parameters.Barcode.Pdf417.Columns = 4;    // column count

            // Choose output path (adjust as needed)
            string outputPath = "micro.png";

            // Save as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Execute o programa (`dotnet run` no console) e você verá a mensagem de confirmação. O PNG gerado pode ser incorporado em relatórios, impresso em rótulos de produto ou exibido em uma página web.

## Perguntas frequentes e casos de borda

| Pergunta | Resposta |
|---|---|
| **Posso gerar outros tipos de código de barras?** | Sim. Substitua `EncodeTypes.MicroPdf417` por qualquer valor do enum `EncodeTypes` (ex.: `EncodeTypes.Code128`, `EncodeTypes.QR`). |
| **E se eu precisar de uma imagem maior?** | Aumente `XDimension.Pixels` ou use `generator.Parameters.Image.Width/Height` para forçar um tamanho de pixel específico. |
| **A biblioteca suporta fundos transparentes?** | Defina `generator.Parameters.Barcode.BackColor = System.Drawing.Color.Transparent;` antes de chamar `Save`. |
| **Como faço para ler o código de barras de volta?** | Use `Aspose.BarCode.BarCodeReader` na imagem salva; ele detecta a simbologia automaticamente. |
| **O PNG é seguro para impressão?** | PNG é sem perdas, mas para impressão CMYK considere salvar como TIFF (`BarCodeImageFormat.Tiff`). |

## Conclusão

Agora você sabe **como gerar código de barras** em C# e como **definir o tamanho do código de barras** usando Aspose.BarCode. O exemplo completo demonstra a criação de um símbolo Micro PDF417, o ajuste de suas dimensões e a exportação para um arquivo PNG. Com essa base, você pode explorar outras simbologias, personalizar cores ou integrar a geração de códigos de barras em serviços ASP.NET Core.

### Próximos passos

- Experimente gerar um QR code (`EncodeTypes.QR`) e compare os tamanhos dos módulos.  
- Experimente `generator.Parameters.Image` para adicionar margens ou alterar DPI para saída pronta para impressão.  
- Combine a geração de códigos de barras com **Aspose.PDF** para incorporar a imagem diretamente em um relatório PDF.

Bom desenvolvimento, e aproveite a flexibilidade que o Aspose.BarCode traz aos seus projetos .NET de códigos de barras!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [How to Generate Barcode in C# – Complete Aspose.BarCode Guide](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}