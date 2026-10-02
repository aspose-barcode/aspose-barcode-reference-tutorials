---
category: general
date: 2026-09-10
description: Como definir código de barras em C# usando um Gerador de Código de Barras.
  Ajuste a largura do módulo do código de barras, gere imagens de códigos de barras
  e aprenda a salvar arquivos de códigos de barras.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- c# barcode generator
- barcode module width
- how to generate barcode
- how to save barcode
language: pt
lastmod: 2026-09-10
og_description: Como definir código de barras em C# com um Gerador de Código de Barras.
  Aprenda a ajustar a largura do módulo, gerar um código de barras e salvar a imagem
  do código de barras de forma eficiente.
og_image_alt: Screenshot showing a Planet barcode with filled and empty bars generated
  by C# code
og_title: Como definir propriedades de código de barras usando o Gerador de Código
  de Barras C#
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: How to set barcode in C# using a Barcode Generator. Adjust barcode
    module width, generate barcode images, and learn how to save barcode files.
  headline: How to set barcode properties with the C# Barcode Generator
  type: TechArticle
tags:
- barcode
- c#
- image generation
title: Como definir propriedades de código de barras com o Gerador de Código de Barras
  C#
url: /pt/python-java/general/how-to-set-barcode-properties-with-the-c-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como definir propriedades de código de barras com o Gerador de Código de Barras C#

Definir propriedades de código de barras é essencial quando você precisa de controle preciso sobre o estilo visual de um código de barras. Este guia mostra como gerar um código de barras Planet, ajustar a largura do módulo do código de barras e salvar a imagem do código de barras usando o Gerador de Código de Barras C#.

Você verá um exemplo completo e executável que cobre cada passo, desde a criação do objeto de código de barras até a gravação dos arquivos PNG no disco. Nenhuma documentação externa é necessária — apenas o código abaixo e a biblioteca Aspose.BarCode (ou qualquer SDK de código de barras compatível). Ao final do tutorial, você poderá responder perguntas como “como gerar código de barras com dimensões personalizadas?” e “como salvar código de barras em diferentes formatos?”.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 ou posterior instalado  
* Visual Studio 2022 (ou qualquer IDE C#)  
* O pacote NuGet **Aspose.BarCode** (ou outra biblioteca que forneça `BarcodeGenerator`)  

Você pode adicionar o pacote com o seguinte comando:

```bash
dotnet add package Aspose.BarCode
```

## Como definir a largura do módulo do código de barras

A *largura do módulo* (também chamada de X‑dimensão) determina o tamanho em pixels de cada barra estreita no código de barras. Definir esse valor permite controlar o tamanho geral e a legibilidade da imagem.

```csharp
// Create a barcode generator for the Planet symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width to 4 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Por que isso importa*: Uma X‑dimensão maior produz um código de barras maior, que é mais fácil de ser lido por scanners à distância, enquanto um valor menor reduz o tamanho do arquivo para renderização na tela.

## Gerando um código de barras com barras preenchidas

O estilo padrão para o código de barras Planet usa **barras preenchidas** (barras pretas sólidas). O código a seguir cria a imagem e a salva como PNG.

```csharp
// Save the barcode with filled bars
barcodeGenerator.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

> **Resultado**: `PostalPlanetFilledBars.png` contém um código de barras Planet padrão onde cada barra está preenchida.

## Criando um código de barras com barras vazias

Às vezes você precisa de um código de barras que mostre apenas os contornos das barras (barras vazias). Para isso, você duplica o gerador, mantém a mesma largura do módulo e desativa a flag `FilledBars`.

```csharp
// Duplicate the generator for an empty‑bar version
BarcodeGenerator emptyBarGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Apply the same X‑dimension
emptyBarGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars so only the outlines are drawn
emptyBarGenerator.Parameters.Barcode.FilledBars = false;

// Save the empty‑bar barcode
emptyBarGenerator.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

> **Resultado**: `PostalPlanetEmptyBars.png` exibe os mesmos dados, mas com barras não preenchidas, útil para documentos com muito design onde você deseja que o código de barras se misture ao fundo.

## Como salvar o código de barras em diferentes formatos

O método `Save` aceita qualquer formato suportado pelo SDK, como **Jpeg**, **Bmp**, **Gif** ou **Svg**. Alterar o formato requer apenas trocar o valor do enum `BarCodeImageFormat`.

```csharp
// Example: save as SVG for lossless scaling
barcodeGenerator.Save("YOUR_DIRECTORY/PostalPlanet.svg", BarCodeImageFormat.Svg);
```

*Dica*: Use SVG quando precisar de um gráfico vetorial que escale sem pixelização, especialmente para PDFs prontos para impressão.

## Exemplo completo e executável

Juntando todas as peças, você obtém um programa autônomo que pode colar em um aplicativo de console.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1. Create a filled‑bar Planet barcode
        BarcodeGenerator filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        filledGenerator.Parameters.Barcode.XDimension.Pixels = 4; // barcode module width
        filledGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // 2. Create an empty‑bar version of the same barcode
        BarcodeGenerator emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4; // same module width
        emptyGenerator.Parameters.Barcode.FilledBars = false;   // how to set barcode to empty bars
        emptyGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

        // 3. Optional: save as SVG for scalable use
        filledGenerator.Save("PostalPlanet.svg", BarCodeImageFormat.Svg);
    }
}
```

**Saída esperada**

| Nome do arquivo                     | Descrição                                                          |
|-------------------------------------|--------------------------------------------------------------------|
| `PostalPlanetFilledBars.png`        | Código de barras Planet com barras pretas sólidas                  |
| `PostalPlanetEmptyBars.png`         | Mesmos dados, barras renderizadas como contornos                    |
| `PostalPlanet.svg`                  | Versão vetorial para escala sem perda                               |

Execute o programa, abra os arquivos gerados e verifique se os códigos de barras correspondem à sequência numérica “123456”.

## Variações comuns e casos extremos

| Situação                               | Ajuste                                                                 |
|----------------------------------------|-----------------------------------------------------------------------|
| Necessidade de um código de barras mais grosso | Aumentar `XDimension.Pixels` (por exemplo, `8`)                     |
| Desejo de um tamanho de arquivo menor | Usar `BarCodeImageFormat.Jpeg` ou reduzir a X‑dimension               |
| Gerar outras simbologias               | Substituir `EncodeTypes.Planet` por `EncodeTypes.Code128`, `QR`, etc. |
| Impressão em impressoras de alta resolução | Salvar como `BarCodeImageFormat.Tiff` para saída raster sem perdas   |
| Execução em servidor sem interface gráfica | Nenhum código de UI necessário; o gerador funciona em um contexto de console ou serviço |

**Dica profissional**: Sempre valide o código de barras gerado com um scanner ou ferramenta de verificação antes de implantá‑lo em produção. Largura de módulo ou formato incorretos podem causar falhas de leitura.

## Conclusão

Agora você sabe como definir propriedades de código de barras usando o Gerador de Código de Barras C#, como controlar a largura do módulo do código de barras, como gerar estilos de barras preenchidas e vazias, e como salvar o código de barras nos formatos PNG ou SVG. Essas etapas fornecem uma base sólida para adicionar a criação de códigos de barras a qualquer aplicação .NET.

Em seguida, explore tópicos relacionados como **c# barcode generator performance tuning**, **embedding barcodes in PDF documents**, e **creating QR codes with custom colors**. Experimente diferentes `EncodeTypes` e formatos de imagem para encontrar a melhor opção para seu projeto.

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como salvar código de barras em C# – Gerar códigos PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Tutorial do Gerador de Código de Barras: Como gerar código de barras PDF417 em C#](/barcode/english/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)
- [Como definir nível de erro no código de barras PDF417 – Guia completo](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}