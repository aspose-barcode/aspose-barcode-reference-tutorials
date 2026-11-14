---
category: general
date: 2026-11-14
description: Aprenda como criar imagem de código de barras em C# usando Aspose.BarCode.
  Este guia passo a passo cobre a configuração do gerador de código de barras em C#,
  formatação GS1 e exportação PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create gs1 barcode
- barcode image from data
language: pt
lastmod: 2026-11-14
og_description: Crie imagem de código de barras em C# rapidamente. Siga este guia
  para aprender como gerar código de barras, usar o gerador de código de barras C#
  e exportar um PNG GS1 MicroPDF417.
og_image_alt: Screenshot of a GS1 MicroPDF417 barcode generated in C#
og_title: Criar imagem de código de barras em C# – guia completo para GS1 MicroPDF417
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create barcode image in C# using Aspose.BarCode. This
    step‑by‑step guide covers barcode generator c# setup, GS1 formatting and PNG export.
  headline: How to create barcode image in C# with GS1 MicroPDF417
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Como criar imagem de código de barras em C# com GS1 MicroPDF417
url: /pt/net/gs1-barcode-encoding/how-to-create-barcode-image-in-c-with-gs1-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar imagem de código de barras em C# com GS1 MicroPDF417

Se você precisa **criar imagem de código de barras** em C#, este guia mostra uma solução completa, pronta‑para‑executar. Você verá **como gerar dados de código de barras** que seguem o padrão GS1, configurar o gerador e exportar um arquivo PNG de alta qualidade.

O tutorial cobre tudo, desde a instalação da biblioteca necessária até o tratamento de armadilhas comuns de formato de dados. Ao final, você será capaz de produzir uma **imagem de código de barras a partir de dados** com apenas algumas linhas de código, e entenderá por que cada configuração é importante.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 ou superior instalado (o código também funciona com .NET Framework 4.7+).
* Uma IDE como Visual Studio 2022 ou Visual Studio Code.
* O pacote NuGet **Aspose.BarCode for .NET**. Instale‑o com:

```bash
dotnet add package Aspose.BarCode
```

* Familiaridade básica com a sintaxe C# e o formato de Identificador de Aplicação GS1 (AI).

> **Dica profissional:** Mantenha a versão da biblioteca atualizada; a versão mais recente adiciona suporte a novas simbologias de código de barras e melhorias de desempenho.

## Criar imagem de código de barras com BarcodeGenerator

Esta seção contém a implementação principal. O código cria uma instância **barcode generator c#**, configura a dimensão X para legibilidade e salva o resultado como um arquivo PNG.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialise the generator with the GS1 MicroPDF417 symbology
// The data string follows the GS1 syntax: (01)GTIN(21)SerialNumber
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,
    "(01)12345678901234(21)ABC123");

// Step 2: Adjust the module width (X‑dimension) to improve scan reliability
// A value of 2 pixels works well for most screen‑displayed barcodes.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Export the barcode as a PNG image
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "GS1MicroPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
```

### Por que cada linha importa

* **EncodeTypes.MicroPdf417** indica à biblioteca que deve usar a simbologia GS1 MicroPDF417, que é compacta e ideal para leitura móvel.
* A **string de dados** deve começar com o AI GS1 `(01)` para o Global Trade Item Number (GTIN) seguido de `(21)` para o número de série. Se o formato estiver incorreto, o gerador lançará uma exceção.
* **XDimension.Pixels** controla a largura da barra mais fina. Um valor maior aumenta a legibilidade em telas de baixa resolução, enquanto um valor menor reduz o tamanho da imagem.
* **BarCodeImageFormat.Png** produz uma imagem sem perdas, preservando as bordas nítidas necessárias para a leitura confiável.

Executar o programa cria `GS1MicroPdf417.png` na sua área de trabalho. Abrir o arquivo mostra um código de barras denso, preto‑sobre‑branco, que codifica o GTIN `12345678901234` e o serial `ABC123`.

## Como gerar código de barras usando GS1 MicroPDF417

Se você é novo na formatação GS1, aqui estão as regras essenciais:

| GS1 AI | Significado                 | Exemplo               |
|--------|-----------------------------|-----------------------|
| (01)   | Global Trade Item Number    | 12345678901234        |
| (21)   | Número de série (opcional) | ABC123                |

Ao concatenar os AIs com seus valores, envolva cada AI entre parênteses e coloque os valores diretamente depois. A string resultante pode ser passada para o **barcode generator c#** sem codificação adicional.

### Armadilhas comuns

* **Parênteses ausentes** – O gerador trata a string como dados brutos e não aplicará as verificações GS1.
* **Exceder limites de comprimento** – MicroPDF417 suporta até 155 caracteres. Remova espaços em branco desnecessários.
* **Caracteres inválidos** – Apenas caracteres numéricos são permitidos para o GTIN; o serial pode incluir letras maiúsculas e dígitos.

## Personalizando a imagem de código de barras a partir de dados

Além da dimensão X básica, o Aspose.BarCode oferece várias opções visuais. Abaixo estão alguns ajustes que você pode aplicar dependendo dos requisitos do seu projeto.

```csharp
// Set background to transparent (useful for overlaying on UI)
generator.Parameters.ImageBackgroundColor = Color.Transparent;

// Change foreground color to dark blue for branding
generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);

// Increase image resolution to 300 dpi for print‑ready output
generator.Parameters.ImageResolution = 300;
```

Cada configuração é opcional; os padrões já produzem uma **imagem de código de barras** limpa e legível. Experimente cores e resoluções somente depois de confirmar que os leitores ainda conseguem ler o código.

## Salvando o código de barras em outros formatos

Embora PNG seja o formato mais comum para web e dispositivos móveis, você pode precisar de JPEG, BMP ou SVG. O método `Save` aceita qualquer valor de `BarCodeImageFormat`.

```csharp
generator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

* JPEG reduz o tamanho do arquivo, mas introduz artefatos de compressão que podem afetar a legibilidade.
* SVG preserva a qualidade vetorial e é ideal para designs responsivos na web.

## Verificando o código de barras gerado

Uma maneira rápida de confirmar que a etapa **create barcode image** foi bem‑sucedida é usar um aplicativo de scanner móvel que suporte GS1 MicroPDF417. Escaneie o PNG salvo; o app deve exibir:

```
GTIN: 12345678901234
Serial: ABC123
```

Se o scanner relatar um erro, verifique novamente a formatação dos AIs e o valor da dimensão X.

## Exemplo completo – programa de console autônomo

A seguir, um programa completo que você pode copiar, colar e executar sem modificações (exceto a etapa de instalação do NuGet).

```csharp
using System;
using System.IO;
using System.Drawing;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with GS1 MicroPDF417 and sample data
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "(01)12345678901234(21)ABC123");

            // Improve readability by setting module width
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Optional visual customisation
            generator.Parameters.ImageBackgroundColor = Color.Transparent;
            generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);
            generator.Parameters.ImageResolution = 300;

            // Define output path (Desktop folder)
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "GS1MicroPdf417.png");

            // Save the barcode as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

Ao executar o programa, o console imprime o caminho completo do arquivo, e o PNG aparece na sua área de trabalho. Este exemplo demonstra **como gerar código de barras**, personalizar a aparência e exportar uma **imagem de código de barras a partir de dados** em um fluxo de trabalho único e coeso.

## Perguntas frequentes

| Pergunta | Resposta |
|----------|----------|
| *Posso gerar outras simbologias GS1?* | Sim. Substitua `EncodeTypes.MicroPdf417` por `EncodeTypes.Pdf417`, `EncodeTypes.DataMatrix`, etc., e ajuste a string de dados conforme necessário. |
| *E se meus dados excederem a capacidade do MicroPDF417?* | Troque para a simbologia PDF417 regular, que suporta cargas úteis maiores. |
| *Preciso de licença para Aspose.BarCode?* | Uma licença de avaliação gratuita funciona para desenvolvimento. Para produção, adquira uma licença para remover a marca d'água de avaliação. |
| *O PNG é adequado para impressão em etiquetas?* | Aumente `ImageResolution` para 300 dpi ou mais, e considere salvar como TIFF para impressoras industriais. |

## Conclusão

Agora você sabe como **criar imagem de código de barras** em C# usando a abordagem **barcode generator c#**, formatar dados para um cenário **create gs1 barcode**, e exportar o resultado como PNG ou outro tipo de imagem. O exemplo completo demonstra cada passo — da preparação dos dados à personalização visual — para que você possa integrar a criação de códigos de barras em qualquer aplicação .NET.

Em seguida, explore tópicos relacionados como **barcode image from data** para QR codes, adicionar múltiplos códigos de barras a um único PDF, ou automatizar a geração em lote para sistemas de inventário. Experimente diferentes valores de dimensão X e formatos de imagem para encontrar o ponto ideal para o seu ambiente de leitura.

Feliz codificação, e que suas aplicações comecem a **criar imagens de códigos de barras** que funcionem de forma confiável no mundo real!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to create barcode image with Aspose.Barcode in C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [How to create postal barcode image in C# using Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)
- [How to create PDF417 barcode image in C# – complete guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}