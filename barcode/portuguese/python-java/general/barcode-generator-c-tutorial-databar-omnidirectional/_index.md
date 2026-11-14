---
category: general
date: 2026-11-14
description: Tutorial de gerador de código de barras em C# que mostra como criar códigos
  de barras DataBar Omnidirectional, definir a dimensão X e ajustar a altura das barras
  em pixels.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c# tutorial
- DataBar Omnidirectional
- set bar height
- XDimension pixels
- BarCodeImageFormat PNG
language: pt
lastmod: 2026-11-14
og_description: Tutorial de gerador de código de barras em C# explica passo a passo
  como gerar um código de barras DataBar Omnidirectional, definir XDimension em pixels
  e alterar a altura das barras para saída PNG.
og_image_alt: Screenshot of barcode generator C# tutorial output showing a DataBar
  barcode
og_title: Tutorial de gerador de código de barras C# – crie códigos de barras DataBar
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Barcode generator C# tutorial that shows how to create DataBar Omnidirectional
    barcodes, set X‑dimension, and adjust bar height in pixels.
  headline: 'Barcode generator C# tutorial: DataBar Omnidirectional'
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- tutorial
title: 'Tutorial de gerador de código de barras C#: DataBar omnidirecional'
url: /pt/python-java/general/barcode-generator-c-tutorial-databar-omnidirectional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tutorial de gerador de código de barras C# – criar códigos de barras DataBar Omnidirecional

Se você está procurando um **tutorial de gerador de código de barras C#**, chegou ao lugar certo. Este guia orienta você na criação de um código de barras DataBar Omnidirecional, configurando a XDimension em pixels e ajustando a altura das barras para produzir imagens PNG.

Você verá um exemplo completo e executável que cobre tudo, desde a inicialização do gerador até a gravação de várias imagens com diferentes alturas de barra. Nenhuma documentação externa é necessária — basta copiar o código, executá-lo e você terá dois arquivos de código de barras prontos para uso.

## Pré-requisitos

* .NET 6.0 ou posterior instalado  
* Uma referência à biblioteca de códigos de barras que fornece `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat` (por exemplo, Aspose.BarCode for .NET)  
* Familiaridade básica com a sintaxe C# e Visual Studio ou sua IDE preferida  

> **Dica profissional:** Se você estiver usando Aspose.BarCode, adicione o pacote NuGet `Aspose.BarCode` ao seu projeto.

## Tutorial de gerador de código de barras C# – passo 1: criar o gerador

O primeiro passo é instanciar um `BarcodeGenerator` com o tipo de codificação `DatabarOmniDirectional` e os dados que você deseja codificar.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Omnidirectional barcode generator with the desired data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*Por que isso importa:* `EncodeTypes.DatabarOmniDirectional` indica à biblioteca que produza um código de barras que pode ser lido em qualquer direção, o que é ideal para embalagens de varejo e logística.

## Definir pixels XDimension para o código de barras

A X‑dimension define a largura do menor módulo (o “pixel”) no código de barras. Defini‑la em pixels fornece controle preciso sobre a densidade visual do código de barras.

```csharp
        // Step 2: Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Explicação:* Um valor de `2` pixels produz um código de barras nítido o suficiente para a maioria dos scanners, mantendo o tamanho do arquivo de imagem modesto.

## Ajustar a altura das barras e salvar imagens

A altura das barras determina quão altas as barras aparecem. Você pode gerar várias imagens com alturas diferentes alterando a propriedade `BarHeight.Pixels` e chamando `Save` novamente.

```csharp
        // Step 3: Set the bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        string outputPath = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
```

O valor enum `BarCodeImageFormat.Png` garante que a saída seja um arquivo PNG sem perdas, que é o formato recomendado para gráficos de códigos de barras porque preserva as dimensões exatas.

## Alterar a altura das barras para criar múltiplas imagens

Frequentemente você precisa do mesmo código de barras em tamanhos diferentes — por exemplo, um para um rótulo pequeno e outro para um cartaz grande. Altere a altura das barras e reutilize a mesma instância do gerador:

```csharp
        // Step 4: Change the bar height to 60 px and save a second image
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        outputPath = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
    }
}
```

*Caso extremo:* Se a altura das barras for definida muito baixa (por exemplo, abaixo de 10 px), alguns scanners podem ter dificuldade em ler o código. Sempre teste as imagens geradas com o hardware de scanner alvo.

## Código-fonte completo

Abaixo está o programa completo que você pode copiar‑colar em um novo projeto de console. Ele inclui todas as diretivas `using` necessárias e demonstra ambas as variações de altura de barra.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a DataBar Omnidirectional barcode generator
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Set XDimension to 2 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image – 30 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
            generator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 30 px barcode to {path30}");

            // Second image – 60 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
            generator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 60 px barcode to {path60}");
        }
    }
}
```

Execute o programa, substitua `YOUR_DIRECTORY` por um caminho de pasta válido, e você encontrará dois arquivos PNG:

* `DatabarBarHeight30Pixels.png` – barras com 30 px de altura  
* `DatabarBarHeight60Pixels.png` – barras com 60 px de altura  

![saída do tutorial de gerador de código de barras C#](images/databar-example.png "Tutorial de gerador de código de barras C# mostrando duas imagens DataBar")

## Perguntas comuns

| Pergunta | Resposta |
|----------|----------|
| **Posso mudar o formato da imagem?** | Sim. Substitua `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` ou `Gif` conforme necessário. PNG é preferido para qualidade sem perdas. |
| **E se eu precisar de um XDimension diferente?** | Ajuste `generator.Parameters.Barcode.XDimension.Pixels` para qualquer inteiro. Valores maiores aumentam a largura total do código de barras. |
| **O DataBar Omnidirecional é adequado para leitura móvel?** | Sim, desde que o tamanho impresso atenda ao tamanho mínimo de módulo do scanner (geralmente 0,33 mm). O XDimension baseado em pixels ajuda a atender a esse requisito. |
| **Como incorporo o código de barras em um PDF?** | Depois de salvar o PNG, use uma biblioteca PDF (por exemplo, iTextSharp) para inserir a imagem em uma página PDF. |

## Conclusão

Este **tutorial de gerador de código de barras C#** mostrou como criar um código de barras DataBar Omnidirecional, definir a XDimension em pixels e gerar arquivos PNG com diferentes alturas de barra. Agora você tem um trecho de código reutilizável que pode adaptar para qualquer projeto C# que exija a criação de códigos de barras.

### O que vem a seguir?

* Explore outros `EncodeTypes` como `Code128` ou `QR` para ampliar seu repertório de códigos de barras.  
* Combine o PNG gerado com uma biblioteca de geração de PDF para produzir faturas imprimíveis.  
* Experimente `generator.Parameters.Barcode.Color` para adicionar cores personalizadas mantendo-se dentro das especificações do scanner.

Sinta‑se à vontade para modificar o exemplo, testar alturas de barra adicionais ou mudar o formato de saída. Feliz codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como definir largura e ajustar altura para um código de barras GS1 DataBar Omnidirecional](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Como definir a altura do código de barras, gerar código de barras DataBar em C#](/barcode/english/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/)
- [Como criar código de barras Databar omnidirecional em C#](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}