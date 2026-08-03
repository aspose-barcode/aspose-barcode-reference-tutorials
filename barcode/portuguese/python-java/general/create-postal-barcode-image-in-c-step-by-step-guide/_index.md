---
category: general
date: 2026-08-03
description: Crie rapidamente uma imagem de código de barras postal em C#. Aprenda
  a gerar código de barras postal, definir as dimensões do código de barras e gerar
  um código Planet.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- how to generate postal barcode
- generate planet barcode
- how to set barcode dimensions
language: pt
lastmod: 2026-08-03
og_description: Crie imagem de código de barras postal em C# com este tutorial completo;
  aprenda a definir as dimensões do código de barras, gerar um código de barras Planet
  e produzir códigos de barras RM4SCC.
og_image_alt: Generated postal barcode image saved as PNG using C# BarcodeGenerator
og_title: Crie imagem de código de barras postal em C# – guia completo de programação
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create postal barcode image in C# quickly. Learn how to generate postal
    barcode, set barcode dimensions, and generate a Planet barcode.
  headline: Create postal barcode image in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- postal barcode
title: Criar imagem de código de barras postal em C# – guia passo a passo
url: /pt/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar imagem de código de barras postal em C# – guia passo a passo

Se você precisa **criar imagem de código de barras postal** em C#, este guia mostra exatamente como fazer. Vamos abordar **como gerar código de barras postal**, **como definir dimensões do código de barras** e como **gerar código de barras Planet** para padrões postais comuns.

Você terminará com dois arquivos PNG prontos para uso — um código de barras Planet e um código de barras RM4SCC — cada um com 100 px de altura. Nenhuma ferramenta adicional é necessária além da biblioteca Aspose.BarCode for .NET.

## Pré-requisitos

* .NET 6 SDK ou posterior (o código também funciona com .NET Framework 4.7+)
* Visual Studio 2022 ou qualquer IDE C#
* Pacote NuGet **Aspose.BarCode** (a biblioteca que fornece `BarcodeGenerator`)

## Etapa 1: Instalar a biblioteca de código de barras

Abra um terminal na pasta do seu projeto e execute:

```bash
dotnet add package Aspose.BarCode
```

O pacote adiciona o namespace `Aspose.BarCode`, que contém `BarcodeGenerator` e a enumeração `EncodeTypes` necessária para códigos de barras postais.

## Etapa 2: Definir a pasta de saída

Criar um caminho de saída confiável evita erros de tempo de execução quando a pasta não existe.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Ensure the directory exists
        string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputFolder);
```

*Por que isso importa*: `Directory.CreateDirectory` é idempotente — cria a pasta somente se ela ainda não existir, evitando exceções em execuções subsequentes.

## Etapa 3: Configurar dimensões comuns do código de barras

Definir a X‑dimension (largura de uma única barra) e a altura total da barra permite controlar o tamanho visual da imagem gerada.

```csharp
        // Common dimension settings
        const int xDimensionPixels = 4;   // Width of a single bar
        const int barHeightPixels = 100; // Desired barcode height
```

**Como definir dimensões do código de barras**: A propriedade `Parameters.Barcode.XDimension.Pixels` define a largura da barra estreita, enquanto `Parameters.Barcode.BarHeight.Pixels` define a altura total. Ajuste esses valores para atender às especificações do seu serviço de correspondência.

## Etapa 4: Gerar um código de barras Planet

Planet é um código de barras postal amplamente usado no Reino Unido. O código a seguir cria um código de barras Planet de 100 px de altura e o salva como PNG.

```csharp
        // Step 4: Generate Planet barcode
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        planetGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;

        string planetPath = Path.Combine(outputFolder, "PostalPlanetBarHeight100Pixels.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);
```

**Por que isso funciona**: `EncodeTypes.Planet` indica ao gerador para usar a simbologia Planet. O método `Save` grava um arquivo PNG no caminho especificado, preservando as dimensões que definimos anteriormente.

## Etapa 5: Gerar um código de barras RM4SCC

RM4SCC é o padrão de código de barras postal holandês. O código abaixo espelha o exemplo Planet, demonstrando **como gerar código de barras postal** de um tipo diferente com dimensões idênticas.

```csharp
        // Step 5: Generate RM4SCC barcode
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;

        string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCBarHeight100Pixels.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);
```

Ambos os arquivos PNG agora residem na pasta `Barcodes`. Abrindo-os, você verá códigos de barras limpos, de 100 px de altura, prontos para impressão ou incorporação em documentos.

## Código-fonte completo

Abaixo está o programa completo e executável que **cria arquivos de imagem de código de barras postal** para os padrões Planet e RM4SCC.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Ensure output directory exists
        string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Dimension settings – reusable for all barcodes
        const int xDimensionPixels = 4;   // Width of a single bar
        const int barHeightPixels = 100; // Height of the barcode

        // ---- Generate Planet barcode ----
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        planetGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;
        string planetPath = Path.Combine(outputFolder, "PostalPlanetBarHeight100Pixels.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);

        // ---- Generate RM4SCC barcode ----
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;
        string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCBarHeight100Pixels.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);

        Console.WriteLine("Barcodes generated:");
        Console.WriteLine($"• {planetPath}");
        Console.WriteLine($"• {rm4sccPath}");
    }
}
```

### Saída esperada

Executar o programa exibe os caminhos dos arquivos e cria dois arquivos PNG:

```
Barcodes/
 ├─ PostalPlanetBarHeight100Pixels.png
 └─ PostalRM4SCCBarHeight100Pixels.png
```

Cada imagem tem 100 px de altura, com largura de barra estreita de 4 pixels, correspondendo às dimensões que definimos.

## Dicas práticas e armadilhas comuns

* **Permissões de pasta** – Se o programa for executado sob uma conta restrita, garanta que a pasta de destino seja gravável.
* **Dimensões diferentes** – Para criar um código de barras mais alto, aumente `barHeightPixels`. Para resolução mais fina, diminua `xDimensionPixels`, mas mantenha ≥ 2 para evitar artefatos de renderização.
* **Outras simbologias postais** – Aspose.BarCode também suporta `EncodeTypes.Postnet` e `EncodeTypes.AustralianPost`. Troque o valor de `EncodeTypes` e mantenha a mesma lógica de dimensões.
* **Formato de imagem** – Use `BarCodeImageFormat.Jpeg` para tamanho de arquivo menor quando a qualidade sem perdas não for necessária.

## Conclusão

Agora você sabe como **criar arquivos de imagem de código de barras postal** em C# configurando dimensões, selecionando a simbologia correta e salvando o resultado como PNG. O tutorial abordou **como gerar código de barras postal**, demonstrou **gerar código de barras Planet** e explicou **como definir dimensões do código de barras** para uma saída consistente.

Em seguida, explore **personalizar cores do código de barras**, adicionar **texto legível por humanos**, ou integrar as imagens em faturas PDF. O mesmo padrão se aplica a qualquer outro tipo de código de barras suportado pelo Aspose.BarCode, permitindo que você estenda esta solução para um fluxo completo de automação postal.

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar código de barras – Tipos de códigos de barras unidimensionais](/barcode/english/net/one-dimensional-barcode-types/)
- [Como gerar código de barras Aztec com proporção personalizada usando Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Como gerar código de barras java – Código de barras Australia Post com Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}