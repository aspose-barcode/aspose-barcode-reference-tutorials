---
category: general
date: 2026-09-07
description: Aprenda como criar imagem de código de barras em C# e ajustar sua altura,
  largura e formato para gerar arquivos PNG de código de barras rapidamente.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to set barcode
- how to adjust barcode
- generate barcode png
- change barcode height
language: pt
lastmod: 2026-09-07
og_description: Crie imagens de código de barras em C# e aprenda a definir as dimensões
  do código de barras, mudar a altura do código de barras e gerar arquivos PNG de
  código de barras para qualquer aplicação.
og_image_alt: C# generated barcode image saved as PNG with custom height
og_title: Criar imagem de código de barras em C# – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to create barcode image in C# and adjust its height, width,
    and format to generate barcode PNG files quickly.
  headline: How to create barcode image in C# with adjustable height
  type: TechArticle
- description: Learn how to create barcode image in C# and adjust its height, width,
    and format to generate barcode PNG files quickly.
  name: How to create barcode image in C# with adjustable height
  steps:
  - name: 3.1 Adjust the narrow bar width (X‑dimension)
    text: The X‑dimension controls the thickness of the thinnest bar. A value of **2
      pixels** yields a finer appearance, useful when you need a compact label.
  - name: 3.2 Change barcode height for visual balance
    text: Bar height determines how tall the barcode appears. Below we show two common
      heights—30 pixels for a small label and 60 pixels for a larger visual. This
      demonstrates **how to adjust barcode** height programmatically.
  - name: 4.1 Save the first image (30 px height)
    text: '```csharp // Save a 30‑pixel‑high barcode as PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: 4.2 Increase the height and save a second image
    text: '```csharp // Increase height to 60 pixels for a larger visual generator.Parameters.Barcode.BarHeight.Pixels
      = 60;'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Como criar imagem de código de barras em C# com altura ajustável
url: /pt/python-java/general/how-to-create-barcode-image-in-c-with-adjustable-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar imagem de código de barras em C# com altura ajustável

Se você precisa criar uma imagem de código de barras em C# para um sistema de ponto de venda ou rastreador de inventário, este guia mostra o fluxo de trabalho completo. Você verá como definir os parâmetros do código de barras, alterar a altura do código de barras e gerar arquivos PNG que atendam aos requisitos visuais.

Gerar uma imagem de código de barras é uma tarefa comum ao integrar hardware de leitura, imprimir etiquetas ou criar painéis de relatórios. Ao final deste tutorial você terá um trecho de código reutilizável que permite ajustar a dimensão X, a altura e o formato de saída do código de barras sem sair do seu IDE.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 (ou superior) instalado – o código compila com qualquer SDK .NET recente.
* Uma referência à biblioteca **Aspose.BarCode** (disponível via NuGet `Aspose.BarCode`).
* Familiaridade básica com aplicações console em C#.

Esses requisitos garantem que o exemplo seja executado imediatamente no Windows, Linux ou macOS.

## Etapa 1: Configurar o projeto e importar a biblioteca

Crie um novo projeto console e adicione o pacote de código de barras:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Agora abra *Program.cs* e adicione as diretivas `using` necessárias:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;
using Aspose.BarCode;
```

Essas importações dão acesso a `BarcodeGenerator`, `EncodeTypes` e aos enums de formato de imagem necessários para **criar imagem de código de barras**.

## Etapa 2: Inicializar o gerador com a simbologia desejada

A primeira linha de código cria um `BarcodeGenerator` que sabe qual tipo de código de barras codificar. Neste exemplo usamos a simbologia DataBar Omni‑Directional, mas você pode substituir `EncodeTypes.DatabarOmniDirectional` por qualquer outro tipo suportado pelo Aspose.BarCode.

```csharp
// Initialize a generator for a DataBar Omni‑Directional barcode
var generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

A string `"(01)12345678901231"` segue o formato de Identificador de Aplicação GS1, exigido por muitos varejistas. Inicializar o gerador é a base para toda operação **como definir código de barras** que se segue.

## Etapa 3: Como definir dimensões do código de barras – dimensão X e altura

### 3.1 Ajustar a largura da barra estreita (dimensão X)

A dimensão X controla a espessura da barra mais fina. Um valor de **2 pixels** produz uma aparência mais fina, útil quando você precisa de uma etiqueta compacta.

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

### 3.2 Alterar a altura do código de barras para equilíbrio visual

A altura da barra determina quão alto o código de barras aparece. Abaixo mostramos duas alturas comuns—30 pixels para uma etiqueta pequena e 60 pixels para uma visualização maior. Isso demonstra **como ajustar a altura do código de barras** programaticamente.

```csharp
// Height 30 pixels – suitable for compact labels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

## Etapa 4: Gerar arquivos PNG de código de barras com alturas diferentes

### 4.1 Salvar a primeira imagem (altura de 30 px)

```csharp
// Save a 30‑pixel‑high barcode as PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

### 4.2 Aumentar a altura e salvar uma segunda imagem

```csharp
// Increase height to 60 pixels for a larger visual
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save a 60‑pixel‑high barcode as PNG
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Essas duas chamadas `Save` ilustram **gerar arquivos PNG de código de barras** com dimensões distintas enquanto reutiliza a mesma instância do gerador. O formato da imagem é explicitamente definido como PNG, que preserva qualidade sem perdas—ideal para impressão ou exibição em tela.

## Etapa 5: Exemplo completo e executável

Juntando tudo, obtém‑se um único método `Main` que você pode copiar para qualquer projeto console C#:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar Omni‑Directional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set the narrow bar width (X‑dimension) to 2 pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Create a 30‑pixel‑high barcode and save it as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Change barcode height to 60 pixels and save again
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

Executar este programa produz dois arquivos PNG na pasta de saída do projeto:

* `DatabarBarHeight30Pixels.png` – um código de barras compacto de 30 px.
* `DatabarBarHeight60Pixels.png` – um código de barras maior de 60 px.

Ambos os arquivos contêm uma **criar imagem de código de barras** que pode ser incorporada em HTML, impressa em etiquetas ou enviada a um aplicativo móvel para leitura.

## Perguntas frequentes e tratamento de casos limites

| Pergunta | Resposta |
|----------|----------|
| **E se eu precisar de um formato de imagem diferente?** | Substitua `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg`, `Bmp` ou `Gif`. A biblioteca lida automaticamente com a conversão. |
| **Posso mudar as cores de primeiro plano/fundo?** | Sim. Use `generator.Parameters.Barcode.ForeColor` e `BackColor` para definir valores `System.Drawing.Color` antes de chamar `Save`. |
| **Como gerar um código de barras sem criar um arquivo no disco?** | Chame `generator.GenerateBarCodeImage()` para obter um objeto `System.Drawing.Image`, então envie‑o diretamente para uma resposta ou banco de dados. |
| **E se a string de dados exceder o limite da simbologia?** | O gerador lança `ArgumentException`. Valide o comprimento da entrada ou trunque conforme a especificação da simbologia. |
| **Existe uma forma de processar vários códigos de barras em lote?** | Envolva as etapas dentro de um loop `foreach` que atualiza `generator.CodeText` e `BarHeight` para cada item, então chame `Save` com um nome de arquivo único. |

Abordar esses cenários torna a lógica **como ajustar código de barras** robusta para projetos do mundo real.

## Dicas avançadas para geração confiável de códigos de barras

* **Cache o gerador** quando criar muitos códigos de barras do mesmo tipo; reutilizar o objeto reduz a sobrecarga de alocação.
* **Defina `Resolution`** (`generator.Parameters.ImageResolution.Dpi`) se precisar de PNGs de alta resolução para impressão.
* **Valide os dados GS1** antes de atribuí‑los a `CodeText` para evitar erros de codificação que possam causar falhas de leitura.
* **Teste em scanners reais** após mudar a altura ou a dimensão X—alguns dispositivos legados têm requisitos mínimos de tamanho.

## Conclusão

Agora você sabe como **criar imagem de código de barras** em C#, **como definir dimensões do código de barras**, **como ajustar a altura do código de barras** e **gerar arquivos PNG de código de barras** para qualquer necessidade visual. Ajustando `XDimension` e `BarHeight` você pode produzir códigos de barras compactos ou grandes sem mudar os dados subjacentes.

Em seguida, explore tópicos relacionados como **alterar a altura do código de barras** dinamicamente com base na entrada do usuário, incorporar códigos de barras em relatórios PDF usando Aspose.PDF, ou mudar para geração de QR‑code com `EncodeTypes.QR`. Experimente diferentes simbologias e formatos de saída para dominar completamente a criação de códigos de barras em C#.

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to Generate Barcode Image in C# – MicroPdf417 Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}