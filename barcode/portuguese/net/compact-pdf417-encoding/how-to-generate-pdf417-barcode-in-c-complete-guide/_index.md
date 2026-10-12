---
category: general
date: 2026-09-26
description: Gere código de barras PDF417 em C# com Aspose.BarCode. Siga este tutorial
  passo a passo para configurar colunas, habilitar o modo compacto e salvar como PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- pdf417 barcode generator c#
- Aspose.BarCode C#
- barcode image format PNG
- compact PDF417 mode
language: pt
lastmod: 2026-09-26
og_description: Gere código de barras PDF417 em C# usando Aspose.BarCode. Este guia
  mostra como definir colunas, habilitar o modo compacto e exportar o resultado como
  uma imagem PNG.
og_image_alt: Screenshot of a generated PDF417 barcode saved as PNG
og_title: Gerar código de barras PDF417 em C# – tutorial passo a passo
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Generate PDF417 barcode in C# with Aspose.BarCode. Follow this step‑by‑step
    tutorial to configure columns, enable compact mode, and save as PNG.
  headline: How to generate PDF417 barcode in C# – complete guide
  type: TechArticle
tags:
- C#
- barcode
- Aspose
- PDF417
title: Como gerar código de barras PDF417 em C# – guia completo
url: /pt/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar código de barras PDF417 em C# – guia completo

Se você precisa **gerar código de barras PDF417** em uma aplicação .NET, este tutorial mostra uma solução pronta‑para‑executar. Você verá como configurar o tamanho do código, a contagem de colunas e o modo compacto, e então salvar o resultado como um arquivo PNG de alta qualidade.

Gerar um código de barras é uma necessidade comum para sistemas de inventário, plataformas de bilhetagem e codificação de documentos. Ao final deste guia você terá um programa C# autônomo que produz um código de barras PDF417 compacto usando a biblioteca **pdf417 barcode generator C#** da Aspose.

## O que você precisará

- .NET 6.0 SDK ou superior (o código também funciona com .NET Framework 4.7+)
- Uma licença válida do Aspose.BarCode for .NET (a avaliação gratuita funciona para testes)
- Uma IDE ou editor como Visual Studio 2022, Rider ou VS Code
- Familiaridade básica com projetos de console C#

> **Dica profissional:** Se você usar a avaliação gratuita, a imagem gerada conterá uma pequena marca d'água da Aspose. Uma licença adquirida remove a marca d'água e desbloqueia o conjunto completo de recursos.

## Etapa 1: Configurar a biblioteca Aspose.BarCode

Crie um novo projeto de console e adicione o pacote NuGet Aspose.BarCode.

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

O pacote fornece a classe `BarcodeGenerator`, que é o núcleo do fluxo de trabalho **pdf417 barcode generator C#**.

## Etapa 2: Escrever o programa completo de geração de código de barras

Abra `Program.cs` e substitua seu conteúdo pelo código a seguir. O programa demonstra cada passo necessário, desde a inicialização do gerador até a gravação da imagem.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace Pdf417Demo
{
    internal class Program
    {
        private static void Main()
        {
            // Step 2.1: Create a generator for PDF417 with Unicode text.
            // The text contains special characters to prove Unicode handling.
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // Step 2.2: Define the module (pixel) size of each barcode element.
            // XDimension controls the width of a single bar; 2 pixels gives a clear image.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.3: Set the number of columns.
            // PDF417 can automatically choose columns, but fixing it to 3 produces a compact layout.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.4: Enable compact mode.
            // Truncate reduces the amount of data stored, making the barcode smaller.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.5: Choose the output format and file path.
            // PNG preserves the exact pixel dimensions without compression artifacts.
            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### Por que cada linha importa

| Linha | Propósito |
|------|-----------|
| `new BarcodeGenerator(EncodeTypes.Pdf417, "...")` | Instancia um gerador PDF417 e define o texto codificado. PDF417 suporta grandes conjuntos de dados e Unicode, tornando‑o adequado para identificadores complexos. |
| `XDimension.Pixels = 2` | Controla a densidade visual. Valores menores produzem barras mais finas; valores maiores melhoram a legibilidade em telas de baixa resolução. |
| `Pdf417.Columns = 3` | Substitui o cálculo automático de colunas. Colunas fixas são úteis quando você precisa encaixar o código de barras em um espaço pré‑definido. |
| `Pdf417.Truncate = true` | Ativa o modo compacto, que remove preenchimentos desnecessários e reduz o tamanho geral. |
| `Save(..., BarCodeImageFormat.Png)` | Grava o código de barras em um arquivo PNG, um formato sem perdas ideal para processamento posterior ou incorporação em PDFs. |

## Etapa 3: Executar o programa e verificar a saída

Compile e execute o projeto:

```bash
dotnet run
```

Você deverá ver uma mensagem no console confirmando o local do arquivo, e um arquivo chamado **CompactPdf417.png** aparecerá na pasta do projeto.

![Generated PDF417 barcode example](images/compact-pdf417.png){.img-responsive alt="Exemplo de código de barras PDF417 gerado"}

*A imagem mostra um código de barras PDF417 compacto que codifica a string “Åspóse.Barcóde©”.*  

Se você abrir o PNG em um visualizador de imagens, notará três colunas de blocos de dados empilhados, cada barra com 2 pixels de largura. Escanear o código de barras com um leitor padrão de PDF417 retorna o texto original, confirmando que o gerador funciona como esperado.

## Armadilhas comuns e como evitá‑las

| Problema | Motivo | Solução |
|----------|--------|---------|
| O código de barras aparece borrado | `XDimension` definido muito baixo para o DPI alvo | Aumente `XDimension.Pixels` para 3 ou 4, ou renderize em resolução maior usando `generator.Save(..., BarCodeImageFormat.Tiff)` |
| Caracteres Unicode são perdidos | A string de entrada não está codificada como UTF‑8 | Garanta que o arquivo fonte esteja salvo com codificação UTF‑8; o gerador lida automaticamente com Unicode quando o tipo da string é `string`. |
| `Truncate` lança exceção | O tamanho dos dados excede o máximo para a contagem de colunas escolhida | Aumente `Pdf417.Columns` ou defina `Pdf417.Truncate = false` para permitir que o gerador aloque espaço suficiente. |
| Licença não aplicada | Versão de avaliação adiciona marca d'água | Aplique um arquivo de licença válido via `Aspose.BarCode.License` antes de criar o gerador. |

## Expandindo a solução

Depois de ter o fluxo básico de **gerar código de barras PDF417**, você pode explorar recursos adicionais:

- **Nível de correção de erro** – Ajuste `generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel` para aumentar a resiliência contra danos.
- **Personalização de cores** – Use `generator.Parameters.Barcode.ForegroundColor` e `BackgroundColor` para adequar às diretrizes de branding.
- **Incorporação em PDFs** – Combine Aspose.PDF com Aspose.BarCode para colocar o código de barras diretamente dentro de um documento PDF.
- **Geração em lote** – Percorra uma coleção de identificadores para produzir múltiplos arquivos PNG em uma única execução.

Todas essas opções estão documentadas na referência da API Aspose.BarCode e seguem o mesmo padrão demonstrado acima.

## Conclusão

Agora você sabe como **gerar código de barras PDF417** em C# usando Aspose.BarCode, configurar colunas, habilitar o modo compacto e exportar o resultado como imagem PNG. O exemplo completo funciona imediatamente e pode ser adaptado para projetos maiores, como sistemas de bilhetagem, etiquetas de inventário ou codificação segura de documentos.  

Em seguida, experimente as configurações avançadas do **pdf417 barcode generator C#**, como correção de erro e personalização de cores, ou integre o código de barras em um relatório PDF com Aspose.PDF. Teste diferentes valores de `XDimension` e contagens de colunas para encontrar o equilíbrio ideal entre tamanho e confiabilidade de leitura para seu caso de uso específico. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Generate PDF417 barcode in C# – complete guide with compact layout](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide-with-compact-lay/)
- [Aspose barcode example: generate Macro PDF417 in C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}