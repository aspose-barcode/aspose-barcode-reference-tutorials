---
category: general
date: 2026-08-25
description: Crie código de barras RM4SCC em C# com passo a passo e aprenda como definir
  a altura do código de barras para dimensionamento preciso.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create rm4scc barcode c#
- how to set barcode height
language: pt
lastmod: 2026-08-25
og_description: Crie código de barras RM4SCC em C# com Aspose.BarCode e aprenda como
  definir a altura do código de barras para controle preciso em suas aplicações .NET.
og_image_alt: Screenshot of an RM4SCC barcode generated with C#
og_title: Criar código de barras RM4SCC em C# – guia para definir a altura do código
  de barras
schemas:
- author: Aspose
  dateModified: '2026-08-25'
  description: Create RM4SCC barcode C# with step‑by‑step code and learn how to set
    barcode height for precise sizing.
  headline: Create RM4SCC barcode C# and set barcode height
  type: TechArticle
tags:
- barcode
- C#
- RM4SCC
- Aspose.BarCode
title: Criar código de barras RM4SCC em C# e definir a altura do código de barras
url: /pt/python-java/general/create-rm4scc-barcode-c-and-set-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar código de barras RM4SCC C# e definir a altura do código de barras

Crie rapidamente um código de barras RM4SCC em C# usando a biblioteca Aspose.BarCode. Este tutorial mostra **como definir a altura do código de barras** e personalizar outras propriedades visuais para que o código de barras se ajuste exatamente ao seu layout.

Você verá um programa de console completo, pronto‑para‑executar, que gera três arquivos PNG:

* um código de barras Planet de altura padrão (para comparação)  
* um código de barras RM4SCC com altura manual de 100 px  
* um código de barras Planet com barras vazias (não preenchidas)  

O exemplo pressupõe que você tem o Visual Studio 2022 (ou qualquer IDE .NET 6+) e uma licença válida do Aspose.BarCode para .NET ou uma cópia de avaliação.

## Pré-requisitos

| Requisito | Motivo |
|-------------|--------|
| .NET 6 SDK (or later) | Fornece o runtime para o aplicativo de console |
| Aspose.BarCode for .NET NuGet package | Fornece `BarcodeGenerator`, `EncodeTypes` e APIs de exportação de imagem |
| Basic C# knowledge | Necessário para entender o fluxo do código |

Instale o pacote NuGet com:

```bash
dotnet add package Aspose.BarCode
```

> **Dica profissional:** Se você executar o código sem uma licença, as imagens geradas conterão uma pequena marca d'água da Aspose.

## Etapa 1: Configurar a estrutura do projeto

Crie um novo projeto de console e adicione as diretivas `using` necessárias:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat; // optional, you can use the enum directly
```

As instruções `using` dão acesso às classes do gerador de códigos de barras e ao enum de formato PNG.

## Etapa 2: Definir a pasta de saída

Escolha uma pasta onde os arquivos PNG serão salvos. A pasta deve existir antes de chamar `Save`.

```csharp
// Step 1: Define the output folder
string outputFolder = "GeneratedBarcodes/";

// Ensure the directory exists
System.IO.Directory.CreateDirectory(outputFolder);
```

Criar o diretório programaticamente evita uma *FileNotFoundException* quando o código é executado em uma máquina nova.

## Etapa 3: Gerar um código de barras Planet com a altura padrão (linha de base)

O código de barras Planet não é o foco deste guia, mas fornece uma linha de base visual para comparar com o código de barras RM4SCC dimensionado manualmente.

```csharp
// Step 2: Generate a Planet barcode with the default (auto) height
BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // controls bar width
planetAuto.Save($"{outputFolder}PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*Por que isso importa:*  
`XDimension` determina a largura de uma única barra. Mantê‑la constante enquanto altera `BarHeight` isola o efeito da altura.

## Etapa 4: **Criar código de barras RM4SCC C#** – definir uma altura manual

Agora abordamos a tarefa principal: **criar código de barras RM4SCC C#** e controlar explicitamente sua altura.

```csharp
// Step 3: Generate an RM4SCC barcode with a manual height of 100 px
BarcodeGenerator rm4sccManual = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccManual.Parameters.Barcode.XDimension.Pixels = 4;           // same bar width as Planet example
rm4sccManual.Parameters.Barcode.BarHeight.Pixels = 100;          // <-- how to set barcode height
rm4sccManual.Save($"{outputFolder}PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

### Como definir a altura do código de barras

A propriedade `BarHeight` está em `Parameters.Barcode`. Ela aceita um valor `float` expresso em **pixels**, **pontos** ou **milímetros**, dependendo da `Unit` que você escolher (`Pixels`, `Points`, `Millimeters`). No exemplo usamos `Pixels` porque o formato de saída é PNG.

Se precisar de uma altura em milímetros, altere a unidade primeiro:

```csharp
rm4sccManual.Parameters.Barcode.BarHeight.Unit = BarHeightUnit.Millimeters;
rm4sccManual.Parameters.Barcode.BarHeight.Value = 25; // 25 mm tall
```

## Etapa 5: Gerar um código de barras Planet com barras vazias (não preenchidas)

Esta etapa demonstra outra propriedade útil—`FilledBars`. Definir como `false` cria um código de barras “vazio”, o que pode ser útil para fins de design.

```csharp
// Step 4: Generate a Planet barcode with empty (unfilled) bars
BarcodeGenerator planetEmptyBars = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetEmptyBars.Parameters.Barcode.XDimension.Pixels = 4;
planetEmptyBars.Parameters.Barcode.FilledBars = false; // makes bars transparent
planetEmptyBars.Save($"{outputFolder}PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

## Programa completo e executável

Copie o código a seguir para `Program.cs`. Compile e execute o projeto; três arquivos PNG aparecerão na pasta `GeneratedBarcodes`.



## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como criar código de barras code128 Java e definir a altura das barras](/barcode/english/java/barcode-configuration/setting-bars-height/)
- [Como criar zona silenciosa de código de barras .NET para Code 16K usando Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Como criar código de barras Aztec com Aspose.BarCode para .NET](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}