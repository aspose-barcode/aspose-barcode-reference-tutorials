---
category: general
date: 2026-09-23
description: O tutorial de gerador de código de barras em C# mostra como gerar imagens
  de códigos de barras com proporções personalizadas usando a biblioteca Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- DataBar barcode C#
- barcode aspect ratio
- Aspose.BarCode C#
- barcode image export
language: pt
lastmod: 2026-09-23
og_description: O guia do gerador de código de barras em C# orienta você sobre como
  gerar imagens de códigos de barras, ajustar proporções e exportar arquivos PNG usando
  Aspose.BarCode.
og_image_alt: Screenshot of a barcode created with a C# barcode generator
og_title: Crie códigos de barras de alta qualidade com um gerador de códigos de barras
  em C#
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  headline: How to use a C# barcode generator for DataBar codes
  type: TechArticle
- description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  name: How to use a C# barcode generator for DataBar codes
  steps:
  - name: Switching to another barcode type
    text: 'If you need a QR code, Code 128, or PDF417, replace the enum value in the
      constructor:'
  - name: Handling unsupported characters
    text: 'The `BarcodeGenerator` validates the input string against the selected
      symbology. Supplying an illegal character throws an `ArgumentException`. Wrap
      the creation in a try‑catch block to provide a friendly error message:'
  - name: Exporting to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the second argument
      of `Save` accordingly:'
  - name: High‑resolution output for printing
    text: 'When printing on high‑DPI printers, increase the X‑dimension and optionally
      set the `Resolution` property:'
  type: HowTo
tags:
- barcode
- c#
- Aspose
title: Como usar um gerador de código de barras C# para códigos DataBar
url: /pt/python-java/general/how-to-use-a-c-barcode-generator-for-databar-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como usar um gerador de código de barras C# para códigos DataBar

Se você precisa de um **c# barcode generator** que possa produzir símbolos DataBar empilhados Omni‑Directional, este guia oferece uma solução completa, pronta‑para‑executar. Você verá como gerar imagens de código de barras, controlar a dimensão X e alterar a proporção sem sair do IDE.

Gerar códigos de barras é uma necessidade comum para sistemas de inventário, etiquetas de envio e aplicações de ponto de venda. Ao final deste tutorial você poderá criar arquivos PNG com qualquer proporção que escolher e entenderá como adaptar o código para outros tipos de código de barras.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou posterior instalado  
* Visual Studio 2022 (ou qualquer editor C# de sua preferência)  
* Uma referência NuGet ao **Aspose.BarCode** – a biblioteca que fornece a classe `BarcodeGenerator`  

Você não precisa de uma biblioteca gráfica separada; o Aspose.BarCode lida com a codificação de imagens internamente.

## Etapa 1: Instalar o pacote NuGet Aspose.BarCode

Abra um terminal na pasta do seu projeto e execute:

```bash
dotnet add package Aspose.BarCode
```

O comando adiciona a versão estável mais recente da biblioteca ao seu arquivo de projeto, tornando a classe `BarcodeGenerator` disponível para uso.

## Etapa 2: Definir a pasta de saída

Escolha uma pasta onde os arquivos PNG gerados serão salvos. Usar um caminho absoluto ou relativo funciona da mesma forma, mas um caminho relativo mantém o projeto portátil.

```csharp
// Define the output folder (relative to the project root)
string outputFolder = "GeneratedBarcodes/";
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
```

Criar o diretório programaticamente evita erros em tempo de execução caso a pasta esteja ausente.

## Etapa 3: Instanciar o gerador de código de barras C# com dados de exemplo

O construtor `BarcodeGenerator` requer dois argumentos: o tipo de código de barras e a string de dados. Para um símbolo DataBar empilhado Omni‑Directional você usa `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
// Create a barcode generator for a DataBar stacked Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

A string de dados segue o formato do Identificador de Aplicação GS1. O enum `EncodeTypes` contém mais de 150 padrões de código de barras; você pode mudar para outro tipo alterando o valor do enum.

## Etapa 4: Definir a dimensão X (tamanho em pixels) para o código de barras

A dimensão X controla a largura da barra mais estreita. Um valor de pixel 2 gera uma imagem nítida e de alta resolução, adequada para a maioria das telas.

```csharp
// Set the X‑dimension to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Ajustar a dimensão X é opcional, mas oferece controle granular sobre a densidade visual do código de barras.

## Etapa 5: Gerar um código de barras com proporção de 15 e salvá‑lo como PNG

A propriedade `AspectRatio` pertence ao sub‑objeto `DataBar`. Alterar esse valor estica ou comprime o código de barras verticalmente enquanto preserva os dados codificados.

```csharp
// Set aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

O método `Save` grava o código de barras no caminho de arquivo especificado. O enum `BarCodeImageFormat.Png` garante compressão sem perdas.

![exemplo de saída do gerador de código de barras c#](generated_barcode_example.png)

*Imagem: código de barras gerado com proporção de 15.*

## Etapa 6: Alterar a proporção para 30 e gerar uma segunda imagem

Reutilizar a mesma instância de `BarcodeGenerator` evita alocar um novo objeto. Basta atualizar a `AspectRatio` e chamar `Save` novamente.

```csharp
// Update aspect ratio to 30 and save a second image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

Agora você tem dois arquivos PNG que diferem apenas no dimensionamento vertical. Essa técnica é útil quando você precisa dos mesmos dados renderizados para tamanhos de etiqueta diferentes.

## Variações comuns e casos de borda

### Trocar para outro tipo de código de barras

Se precisar de um QR code, Code 128 ou PDF417, substitua o valor do enum no construtor:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(
    EncodeTypes.QR, "https://example.com");
```

Todas as demais etapas de configuração (dimensão X, salvamento) permanecem idênticas.

### Manipulando caracteres não suportados

O `BarcodeGenerator` valida a string de entrada contra a simbologia selecionada. Fornecer um caractere ilegal lança uma `ArgumentException`. Envolva a criação em um bloco try‑catch para fornecer uma mensagem de erro amigável:

```csharp
try
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for the selected barcode type: {ex.Message}");
}
```

### Exportando para outros formatos de imagem

O Aspose.BarCode suporta BMP, JPEG, TIFF e SVG. Altere o segundo argumento de `Save` conforme necessário:

```csharp
barcodeGenerator.Save($"{outputFolder}Databar.svg", BarCodeImageFormat.Svg);
```

### Saída de alta resolução para impressão

Ao imprimir em impressoras de alta DPI, aumente a dimensão X e, opcionalmente, defina a propriedade `Resolution`:

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.ImageResolution.Dpi = 300;
```

Essas configurações produzem arquivos maiores, mas mantêm bordas nítidas em mídia física.

## Saída esperada

Executar o programa completo cria os seguintes arquivos dentro de `GeneratedBarcodes/`:

* `DatabarAspectRatio15.png` – um código DataBar de altura padrão  
* `DatabarAspectRatio30.png` – uma versão verticalmente esticada  

Ambas as imagens contêm os mesmos dados GS1 codificados, e você pode verificá‑las com qualquer aplicativo de scanner de código de barras.

## Código‑fonte completo

Copie o código abaixo para um novo projeto de console (`dotnet new console`) e execute. O programa imprime mensagens de status no console e grava os arquivos PNG no disco.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Define the output folder
        string outputFolder = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputFolder);

        // Step 3: Create a C# barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Step 4: Set common barcode properties (pixel size of X‑dimension)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 5: Generate a barcode with aspect ratio 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputFolder, "DatabarAspectRatio15.png");
        barcodeGenerator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Step 6: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputFolder, "DatabarAspectRatio30.png");
        barcodeGenerator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

A execução do programa produz saída no console semelhante a:

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

## Conclusão

Agora você tem um **c# barcode generator** que pode criar símbolos DataBar empilhados Omni‑Directional, ajustar a dimensão X e exportar arquivos PNG com proporções personalizadas. O mesmo padrão funciona para qualquer outra simbologia suportada pelo Aspose.BarCode, facilitando a integração da criação de códigos de barras em soluções de inventário, envio ou ponto de venda.

Se quiser explorar mais, experimente:

* Gerar códigos QR ou símbolos PDF417 (`how to generate barcode` para aplicativos móveis)  
* Exportar para SVG para gráficos web escaláveis  
* Incorporar as imagens geradas diretamente em faturas PDF usando Aspose.PDF  

Experimente diferentes valores de `AspectRatio`, tamanhos de dimensão X e formatos de saída para corresponder ao exato


## O que você deve aprender a seguir?


Os tutoriais a seguir abordam tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}