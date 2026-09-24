---
category: general
date: 2026-08-19
description: Crie arquivos PNG de databar em C# com Aspose.BarCode. Aprenda como gerar
  imagens databar, configurar parâmetros databar e salvar a saída em PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar png
- how to generate databar
- configure databar parameters
language: pt
lastmod: 2026-08-19
og_description: Crie arquivos PNG de databar em C# usando Aspose.BarCode. Este tutorial
  orienta você sobre como gerar imagens databar, configurar parâmetros como dimensão
  X e proporção, e salvar arquivos PNG de alta qualidade para impressão ou uso na
  web.
og_image_alt: create databar PNG example
og_title: Crie imagens PNG de databar em C# – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Create databar PNG files in C# with Aspose.BarCode. Learn how to generate
    databar images, configure databar parameters, and save PNG output.
  headline: How to create databar PNG images with C# and Aspose.BarCode
  type: TechArticle
tags:
- barcode
- databar
- C#
- PNG
- Aspose.BarCode
title: Como criar imagens PNG de databar com C# e Aspose.BarCode
url: /pt/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar imagens PNG de databar com C# e Aspose.BarCode

Se você precisa **criar arquivos PNG de databar** em uma aplicação .NET, este guia mostra exatamente como fazer. Você verá um exemplo completo e executável que gera códigos DataBar omnidirecionais empilhados, configura parâmetros chave e salva dois arquivos PNG com diferentes proporções.

Gerar uma imagem DataBar não se resume a chamar um único método. Também é necessário **configurar os parâmetros do databar** como a dimensão X (largura do módulo) e a proporção para atender às especificações de impressão ou leitura. Ao final deste tutorial você entenderá **como gerar gráficos databar** que funcionam de forma confiável em cenários reais.

## Pré‑requisitos

- .NET 6.0 ou superior (o código também funciona com .NET Framework 4.7+)
- Visual Studio 2022 ou qualquer IDE compatível com C#
- Uma licença válida para **Aspose.BarCode for .NET** (a avaliação gratuita serve para testes)
- Familiaridade básica com a sintaxe C#

> **Dica:** Se ainda não tem uma licença, você pode solicitar uma chave de avaliação temporária no portal da Aspose. A API se comporta da mesma forma; apenas a marca d'água muda.

## Etapa 1: Instalar o pacote NuGet Aspose.BarCode

Abra seu projeto no Visual Studio, clique com o botão direito na solução e selecione **Manage NuGet Packages**. Procure por `Aspose.BarCode` e instale a versão estável mais recente.

```bash
dotnet add package Aspose.BarCode
```

Este comando adiciona o assembly `Aspose.BarCode` ao seu projeto e disponibiliza a classe `BarcodeGenerator`.

## Etapa 2: Inicializar o gerador de código de barras para um DataBar omnidirecional empilhado

O construtor `BarcodeGenerator` recebe dois argumentos: o tipo de código de barras e a string de dados bruta. Para um DataBar omnidirecional empilhado você usa `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace DatabarPngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Initialize the generator with the desired DataBar type
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // GS1 Application Identifier for a 14‑digit GTIN
```

**Por que isso importa:** A constante `EncodeTypes.DatabarStackedOmniDirectional` indica à biblioteca que o código de barras deve ser legível em qualquer orientação, o que é ideal para etiquetas de prateleira no varejo.

## Etapa 3: Configurar a dimensão X (largura do módulo) em pixels

A dimensão X controla o tamanho do menor elemento de barra. Defini‑la em pixels oferece controle preciso sobre o tamanho final da imagem.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Um valor de **2 pixels** é um bom equilíbrio entre legibilidade e compacidade para a maioria das impressoras de etiquetas. Ajuste esse valor se precisar de módulos maiores ou menores.

## Etapa 4: Definir a primeira proporção e salvar o PNG

A proporção influencia a altura do DataBar empilhado. Uma proporção de **15** produz um código de barras relativamente curto, enquanto **30** o torna mais alto.

```csharp
            // Step 4: Set an aspect ratio of 15 and save the image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

O método `Save` grava o código de barras gerado em um arquivo PNG. PNG é sem perdas, o que preserva as bordas nítidas necessárias para os scanners de código de barras.

## Etapa 5: Alterar a proporção e salvar um segundo PNG

Você pode reutilizar a mesma instância de `BarcodeGenerator` para produzir variações simplesmente alterando a proporção.

```csharp
            // Step 5: Change the aspect ratio to 30 and save a new image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        }
    }
}
```

Agora você tem dois arquivos PNG — `DatabarAspectRatio15.png` e `DatabarAspectRatio30.png` — cada um com uma densidade visual diferente.

## Etapa 6: Verificar a saída

Abra os arquivos PNG gerados em qualquer visualizador de imagens. Você deverá ver um código de barras DataBar limpo e de alto contraste. Escanear as imagens com um leitor de código de barras de smartphone confirma que ambas as proporções decodificam o valor GTIN original `12345678901231`.

![exemplo de criação de databar PNG](databar_example.png)

*A imagem acima mostra os dois arquivos PNG lado a lado. A imagem da esquerda usa proporção 15, a da direita usa proporção 30.*

## Variações comuns e casos de borda

| Cenário | O que mudar | Motivo |
|----------|----------------|--------|
| **Dados diferentes** | Substitua a string `(01)12345678901231` por qualquer Identificador de Aplicação GS1 válido e seus dados | Permite codificar IDs de produto, números de série, etc. |
| **Resolução maior** | Aumente `XDimension.Pixels` para 3 ou 4 | Necessário quando o código de barras será impresso em tamanhos grandes ou escaneado à distância. |
| **Outros tipos de DataBar** | Use `EncodeTypes.DatabarStacked` ou `EncodeTypes.DatabarExpanded` | Escolha o tipo que melhor se adapta ao layout da sua etiqueta. |
| **Fundo transparente** | Passe `BarCodeImageFormat.Png` com `barcodeGenerator.Save(..., BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })` | Útil para sobrepor o código de barras em etiquetas coloridas. |

> **Atenção:** Definir uma dimensão X muito pequena (< 1 pixel) pode gerar um código de barras que parece borrado após

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Create One-Dimensional Databar GS1 Encoding with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}