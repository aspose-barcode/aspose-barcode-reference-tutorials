---
category: general
date: 2026-08-06
description: Gere imagem de código de barras em C# usando Aspose.BarCode. Aprenda
  a gerar Databar, ajustar o tamanho personalizado do código de barras e mudar a altura
  do código de barras com código simples.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- how to generate databar
- custom barcode size
- create databar barcode
- change barcode height
language: pt
lastmod: 2026-08-06
og_description: Gere imagem de código de barras em C# com Aspose.BarCode. Este tutorial
  mostra como criar um código de barras Databar Omnidirecional, personalizar seu tamanho
  e alterar a altura do código de barras de forma eficiente.
og_image_alt: Screenshot of a Databar barcode generated with custom height in C#
og_title: Gerar imagem de código de barras em C# – guia completo do Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Generate barcode image in C# using Aspose.BarCode. Learn how to generate
    Databar, adjust custom barcode size, and change barcode height with simple code.
  headline: Generate barcode image in C# with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: The evaluation version of Aspose.BarCode works without a license but adds
      a small watermark. For production use, apply a purchased license using `License
      license = new License(); license.SetLicense("Aspose.BarCode.lic");`.
    question: Can I generate a barcode without installing a license?
  - answer: Yes. Very small X‑dimensions can make the barcode unreadable on low‑resolution
      printers. A minimum of 1 px for screen rendering is recommended; for print,
      use at least 0.25 mm.
    question: Does changing the X‑dimension affect readability?
  - answer: 'Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. You
      may also set `generator.Parameters.ImageQuality` to control compression. ##
      Conclusion You now know how to **generate barcode image** in C# using Aspose.BarCode,
      how to **create Databar barcode**, adjust a **custom barcode size**, '
    question: What if I need to generate a barcode in JPEG format?
  type: FAQPage
tags:
- barcode
- C#
- Aspose.BarCode
title: Gerar imagem de código de barras em C# com Aspose.BarCode
url: /pt/python-java/general/generate-barcode-image-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerar imagem de código de barras em C# com Aspose.BarCode

Se você precisa **gerar imagem de código de barras** programaticamente, este guia mostra exatamente como fazer. Seja construindo um sistema de inventário de varejo ou um portal de rastreamento logístico, você verá o fluxo completo para criar um código de barras Databar Omnidirecional, ajustar suas dimensões e salvar o resultado como um arquivo PNG.

Gerar uma imagem de código de barras é uma necessidade comum, mas os desenvolvedores frequentemente se perguntam **como gerar Databar** com o tamanho exato que precisam. Neste tutorial você aprenderá a criar um código de barras Databar, personalizar sua largura e altura, e alterar a altura do código de barras sem reescrever todo o gerador.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou superior (o código funciona com .NET Core e .NET Framework)
* Visual Studio 2022 (ou qualquer IDE que suporte C#)
* Uma licença válida do Aspose.BarCode for .NET (a avaliação gratuita funciona para testes)
* Familiaridade básica com a sintaxe C#

## Etapa 1: Instalar Aspose.BarCode

Adicione o pacote NuGet Aspose.BarCode ao seu projeto:

```bash
dotnet add package Aspose.BarCode
```

O pacote contém a classe `BarcodeGenerator` usada ao longo deste tutorial. Após a instalação, restaure o projeto para obter as dependências.

## Etapa 2: Criar um gerador de código de barras básico

A primeira linha de código cria um **gerador de código de barras** que produzirá um símbolo Databar Omnidirecional. O enum `EncodeTypes.DatabarOmniDirectional` indica à biblioteca qual simbologia usar, e a string de dados segue a sintaxe do Identificador de Aplicação GS1.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a Databar Omnidirectional barcode
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231"); // GS1-14 data (example GTIN)
```

**Por que isso importa:** O objeto `BarcodeGenerator` é o ponto de entrada para toda operação de código de barras. Ao selecionar `DatabarOmniDirectional` você garante que a saída esteja em conformidade com o padrão GS1 para leitura no varejo.

## Etapa 3: Definir uma X‑dimension personalizada (largura do módulo)

A X‑dimension controla a largura da barra mais estreita. Definir um valor pequeno em pixels gera um código de barras compacto, enquanto valores maiores aumentam a largura total.

```csharp
        // Step 3: Define a custom X‑dimension (module width) of 2 px
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Explicação:** Uma X‑dimension de 2 pixels é uma escolha comum para telas de alta resolução. Ajuste esse valor se precisar de uma densidade visual mais apertada ou mais espaçada.

## Etapa 4: Gerar a primeira imagem de código de barras com altura específica

A altura do código de barras é independente da X‑dimension. Aqui definimos a altura da barra para **30 px**, então salvamos a imagem como PNG.

```csharp
        // Step 4: Set bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Resultado:** Agora você tem um arquivo chamado `DatabarBarHeight30Pixels.png` que mostra um código de barras Databar com 30 px de altura. Isso demonstra a capacidade de **tamanho de código de barras personalizado** para um caso de uso específico, como um rótulo pequeno.

## Etapa 5: Alterar a altura do código de barras para uma versão maior

Se o mesmo código de barras precisar aparecer em um rótulo maior, basta modificar a propriedade de altura e reutilizar a mesma instância do gerador.

```csharp
        // Step 5: Increase the bar height to 60 px for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
    }
}
```

**Por que você pode reutilizar o gerador:** Alterar `BarHeight.Pixels` atualiza o layout interno sem recriar o objeto, o que economiza memória e mantém a string de dados intacta. Essa é a forma recomendada de **alterar a altura do código de barras** dinamicamente.

## Etapa 6: Verificar a saída

Abra os dois arquivos PNG em qualquer visualizador de imagens. Você deverá ver dois códigos de barras Databar Omnidirecional que codificam o mesmo GTIN, mas diferem em tamanho vertical:

* `DatabarBarHeight30Pixels.png` – 30 px de altura, adequado para recibos compactos.
* `DatabarBarHeight60Pixels.png` – 60 px de altura, ideal para rótulos de prateleira maiores.

Ambas as imagens mantêm a mesma X‑dimension, de modo que a proporção barra‑espaço permanece consistente enquanto a altura total escala.

## Variações comuns e casos de borda

| Situação | Como lidar |
|-----------|------------|
| **Simbologia de código de barras diferente** | Substitua `EncodeTypes.DatabarOmniDirectional` por outro valor de enum (por exemplo, `EncodeTypes.Code128`). O restante do código permanece inalterado. |
| **Dimensões não em pixels** | Use `generator.Parameters.Barcode.XDimension.Millimeters` ou `BarHeight.Millimeters` se precisar de medidas físicas para saída pronta para impressão. |
| **Fundo transparente** | Defina `generator.Parameters.ImageBackgroundColor = Color.Transparent;` antes de chamar `Save`. |
| **Saída de alta resolução** | Aumente tanto `XDimension.Pixels` quanto `BarHeight.Pixels` proporcionalmente, ou salve como `BarCodeImageFormat.Tiff` para qualidade sem perdas. |
| **Múltiplos códigos de barras em uma única imagem** | Crie instâncias separadas de `BarcodeGenerator`, renderize cada uma em um `Bitmap` e então componha-as usando `Graphics.DrawImage`. |

**Dica profissional:** Sempre teste o código de barras gerado com um scanner real antes de colocar em produção. Scanners podem interpretar barras muito finas de forma diferente dependendo da iluminação e da qualidade do sensor.

## Código-fonte completo para referência

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator for a Databar Omnidirectional barcode
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231"); // Example GTIN

            // Custom X‑dimension (module width) – 2 px
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // Second image: 60 px height (larger barcode)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

Copie o código para um novo projeto de console, execute-o e você verá os dois arquivos PNG aparecerem na pasta de saída.

## Perguntas frequentes

**P: Posso gerar um código de barras sem instalar uma licença?**  
R: A versão de avaliação do Aspose.BarCode funciona sem licença, mas adiciona uma pequena marca d'água. Para uso em produção, aplique uma licença adquirida usando `License license = new License(); license.SetLicense("Aspose.BarCode.lic");`.

**P: Alterar a X‑dimension afeta a legibilidade?**  
R: Sim. X‑dimensions muito pequenas podem tornar o código de barras ilegível em impressoras de baixa resolução. Um mínimo de 1 px para renderização em tela é recomendado; para impressão, use ao menos 0,25 mm.

**P: E se eu precisar gerar um código de barras em formato JPEG?**  
R: Substitua `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg`. Você também pode definir `generator.Parameters.ImageQuality` para controlar a compressão.

## Conclusão

Agora você sabe como **gerar imagem de código de barras** em C# usando Aspose.BarCode, como **criar um código de barras Databar**, ajustar um **tamanho de código de barras personalizado** e **alterar a altura do código de barras** sob demanda. O exemplo completo demonstra o fluxo de trabalho mais comum, e a tabela de variações prepara você para lidar com casos reais.

Em seguida, explore tópicos relacionados como **incorporar códigos de barras em documentos PDF**, **gerar lotes de múltiplos códigos de barras** e **usar QR codes para pagamentos móveis**. Cada um desses cenários se baseia nos mesmos princípios abordados aqui, permitindo que você amplie esse conhecimento com confiança.

Bom desenvolvimento, e que seus códigos de barras sejam lidos perfeitamente!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}