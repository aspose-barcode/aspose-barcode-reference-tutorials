---
category: general
date: 2026-08-15
description: Imagem de código de barras PNG em C# – aprenda a gerar códigos de barras
  postais, criar um código de barras Planet e alterar a altura do código de barras
  com um gerador simples.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode image png
- barcode generator c#
- generate postal barcode
- create planet barcode
- change barcode height
language: pt
lastmod: 2026-08-15
og_description: Imagem de código de barras PNG em tutorial C# mostra como gerar códigos
  de barras postais, criar um código de barras Planet e alterar a altura do código
  de barras usando a API BarcodeGenerator.
og_image_alt: Screenshot of generated PNG barcode with custom height using C# BarcodeGenerator
og_title: Imagem de código de barras PNG em C# – gerar e ajustar códigos de barras
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Barcode image PNG in C# – learn how to generate postal barcodes, create
    a Planet barcode, and change barcode height with a simple generator.
  headline: Barcode image PNG in C# generate barcodes, change height
  type: TechArticle
tags:
- barcode
- C#
- PNG
- postal
- generator
title: Imagem de código de barras PNG em C# gerar códigos de barras, alterar altura
url: /pt/python-java/general/barcode-image-png-in-c-generate-barcodes-change-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Imagem de código de barras PNG em C# – gerar códigos de barras, mudar a altura

Se você precisa de uma **imagem de código de barras PNG** em C#, este guia o conduz por todo o processo. Você aprenderá como gerar códigos de barras postais, criar um código de barras Planet e alterar a altura do código de barras sem sair do seu IDE.

Gerar PNGs de códigos de barras confiáveis é uma necessidade comum para etiquetas de envio, sistemas de inventário e soluções de mala direta automatizadas. Ao final deste tutorial você terá um trecho de código reutilizável que produz arquivos PNG de alta qualidade para os formatos Planet e RM4SCC, e entenderá como ajustar a altura das barras para atender às especificações postais.

## O que você precisará

- .NET 6+ ou .NET Framework 4.7.2 (a API BarcodeGenerator funciona com qualquer runtime .NET recente)  
- Uma referência ao pacote NuGet **Aspose.BarCode for .NET** (ou qualquer biblioteca compatível que forneça `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat`)  
- Familiaridade básica com a sintaxe C# e I/O de arquivos  

Nenhuma ferramenta adicional é necessária; o código roda no Visual Studio, Rider ou na CLI `dotnet`.

## Imagem de código de barras PNG – geração básica

O primeiro passo é criar uma **imagem de código de barras PNG** com dimensões padrão. Isso estabelece o arquivo base que você pode personalizar posteriormente.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Define the output folder (replace with your own path)
string outputFolder = @"C:\Barcodes";

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);

// 1️⃣ Create a Planet barcode generator with default height
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width (X‑dimension) to 4 pixels – this defines the thin bar size
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG; this is the first **barcode image PNG** you’ll produce
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

**Por que isso funciona:**  
- `EncodeTypes.Planet` indica ao gerador que use a simbologia Planet, exigida por muitos serviços postais.  
- `XDimension.Pixels` controla a largura da menor barra; um valor de 4 px gera um código de barras legível em tamanhos típicos de etiqueta.  
- O método `Save` grava um arquivo **imagem de código de barras PNG** no disco, preservando todas as informações vetoriais como pixels raster.

## Alterar a altura do código de barras – personalizando o peso visual

Diretrizes postais frequentemente exigem uma altura de barra específica. O trecho a seguir demonstra como definir uma altura personalizada de 100 pixels para o mesmo código de barras Planet.

```csharp
// 2️⃣ Apply a custom 100‑pixel bar height
planetGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Overwrite or save as a new file to keep both versions
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

**Por que mudar a altura:**  
Uma barra mais alta melhora a confiabilidade da leitura em impressoras de baixa resolução, enquanto uma barra mais curta economiza espaço na etiqueta. A propriedade `BarHeight.Pixels` permite ajustar esse atributo sem afetar a dimensão X.

## Gerar código de barras postal – criando um exemplo RM4SCC

O formato RM4SCC é outro código de barras postal comum usado no Reino Unido. As etapas de geração espelham o exemplo Planet, reforçando o padrão **barcode generator c#**.

```csharp
// 3️⃣ Create an RM4SCC barcode generator with default height
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Keep the same module width for consistency
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the default‑height PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

## Alterar a altura do código de barras – variação RM4SCC

Assim como no código de barras Planet, você pode ajustar a altura da barra RM4SCC. O código abaixo define a altura para 100 px, produzindo um segundo **imagem de código de barras PNG** para a mesma string de dados.

```csharp
// 4️⃣ Set a custom 100‑pixel bar height for RM4SCC
rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the customized PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

## Exemplo completo, executável

Juntando todas as etapas, obtém‑se um programa único e autocontido que cria quatro arquivos PNG:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        string outputFolder = @"C:\Barcodes";
        Directory.CreateDirectory(outputFolder);

        // Planet barcode – default height
        var planet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planet.Parameters.Barcode.XDimension.Pixels = 4;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // Planet barcode – custom 100‑pixel height
        planet.Parameters.Barcode.BarHeight.Pixels = 100;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – default height
        var rm4scc = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4scc.Parameters.Barcode.XDimension.Pixels = 4;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – custom 100‑pixel height
        rm4scc.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                    BarCodeImageFormat.Png);

        Console.WriteLine("All barcode PNG files have been generated in " +


## O que você deve aprender a seguir?


Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Create Barcode Custom Height – One-Dimensional Barcodes](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}