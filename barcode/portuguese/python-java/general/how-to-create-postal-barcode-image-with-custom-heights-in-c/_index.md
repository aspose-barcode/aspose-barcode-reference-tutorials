---
category: general
date: 2026-09-26
description: Aprenda como criar imagem de código de barras postal em C#. Este guia
  mostra como gerar código de barras planetário e definir a altura do código de barras
  para saída personalizada.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- barcode generator custom height
- how to set barcode height
language: pt
lastmod: 2026-09-26
og_description: Crie rapidamente uma imagem de código de barras postal em C#. Siga
  este tutorial para gerar o código de barras planetário, definir a altura do código
  de barras e produzir arquivos PNG de alta qualidade.
og_image_alt: Screenshot of a generated postal barcode image with custom bar height
og_title: Crie imagem de código de barras postal com alturas personalizadas em C#
  – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create postal barcode image in C#. This guide shows you
    how to generate planet barcode and set barcode height for custom output.
  headline: How to create postal barcode image with custom heights in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: Como criar imagem de código de barras postal com alturas personalizadas em
  C#
url: /pt/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar imagem de código de barras postal com alturas personalizadas em C#

Se você precisa **criar imagem de código de barras postal** para etiquetas de envio, este tutorial mostra os passos exatos. Você aprenderá como gerar um código de barras Planet, ajustar a altura das barras e salvar o resultado como um arquivo PNG — tudo com a biblioteca Aspose.BarCode para .NET.

Criar uma imagem de código de barras não requer uma ferramenta de design externa. Ao final deste guia, você poderá produzir códigos de barras tanto com altura padrão quanto com altura personalizada para os padrões Planet e RM4SCC, prontos para integração em qualquer fluxo de trabalho de envio.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 ou posterior instalado  
* Visual Studio 2022 (ou qualquer IDE C#)  
* Aspose.BarCode para .NET adicionado via NuGet (`Install-Package Aspose.BarCode`)  

Nenhuma configuração adicional é necessária; a biblioteca lida com a renderização da imagem internamente.

## Etapa 1: Configurar o projeto e importar namespaces

Crie um novo aplicativo de console e adicione as instruções `using` necessárias.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Esses namespaces expõem a classe `BarcodeGenerator` e a enumeração `EncodeTypes` que você usará para **gerar código de barras planet** e outros formatos postais.

## Etapa 2: Criar um código de barras Planet com a altura padrão

O primeiro exemplo cria um código de barras Planet usando a altura padrão da biblioteca. Isso demonstra a saída de referência antes de aplicar qualquer dimensionamento personalizado.

```csharp
// Initialize the generator for a Planet barcode
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels for better readability
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the barcode image; the default bar height is applied automatically
planetGenerator.Save("PostalPlanetBarHeightDefault.png", BarCodeImageFormat.Png);
```

**Por que isso importa:** A altura padrão é adequada para a maioria das impressoras de etiquetas, mas alguns fluxos de trabalho exigem barras mais altas para maior confiabilidade de leitura. O código acima fornece uma imagem de referência para comparar com a versão de altura personalizada.

## Etapa 3: Aplicar uma altura de barra personalizada ao código de barras Planet

Para **definir a altura do código de barras** manualmente, atribua um valor em pixels a `BarHeight.Pixels`. O trecho a seguir cria um código de barras Planet com 100 pixels de altura.

```csharp
// Initialize a second generator for the same data
BarcodeGenerator planetHeightGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Define X‑dimension and a custom bar height of 100 pixels
planetHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the custom‑height image
planetHeightGenerator.Save("PostalPlanetBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

**Dica profissional:** Escolha uma altura de barra que corresponda ao DPI da sua impressora. Para uma impressora de 300 dpi, uma barra de 100 pixels equivale a aproximadamente 0,33 polegadas, o que costuma ser recomendado para scanners postais.

## Etapa 4: Gerar um código de barras RM4SCC com altura padrão

RM4SCC é outra simbologia postal comum. O processo espelha o exemplo Planet, mas usa `EncodeTypes.RM4SCC`.

```csharp
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Set X‑dimension; the library applies the default bar height automatically
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccGenerator.Save("PostalRM4SCCBarHeightDefault.png", BarCodeImageFormat.Png);
```

Esta etapa confirma que a mesma lógica de **gerador de código de barras com altura personalizada** funciona em diferentes formatos postais.

## Etapa 5: Aplicar uma altura personalizada ao código de barras RM4SCC

Por fim, ajuste a altura da barra para o código de barras RM4SCC da mesma forma que fez para o código de barras Planet.

```csharp
BarcodeGenerator rm4sccHeightGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Define both X‑dimension and a 100‑pixel bar height
rm4sccHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the custom‑height image
rm4sccHeightGenerator.Save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

## Saída esperada

Executar o programa completo produz quatro arquivos PNG no diretório de saída do projeto:

| Nome do arquivo                              | Altura da barra | Simbologia |
|----------------------------------------------|-----------------|------------|
| `PostalPlanetBarHeightDefault.png`           | padrão          | Planet     |
| `PostalPlanetBarHeight100Pixels.png`         | 100 px          | Planet     |
| `PostalRM4SCCBarHeightDefault.png`           | padrão          | RM4SCC     |
| `PostalRM4SCCBarHeight100Pixels.png`         | 100 px          | RM4SCC     |

Cada imagem exibe um código de barras nítido e de alto contraste, pronto para impressão em etiquetas de envio. Você pode abrir os arquivos PNG em qualquer visualizador de imagens para verificar as dimensões das barras.

## Perguntas comuns e casos de borda

**E se eu precisar de uma altura de barra em milímetros em vez de pixels?**  
A biblioteca trabalha em pixels porque mapeia diretamente para a resolução do bitmap. Converta milímetros para pixels usando o DPI da impressora:  
`pixels = (mm / 25.4) * DPI`. Defina `BarHeight.Pixels` com o valor calculado.

**Posso mudar a altura da barra após chamar `Save`?**  
Não. A imagem do código de barras é renderizada no momento em que `Save` é invocado. Ajuste todos os parâmetros antes de chamar `Save`.

**É necessário um X‑Dimension maior para barras mais altas?**  
Aumentar `XDimension` deixa cada módulo mais largo, o que pode melhorar a legibilidade em impressoras de baixa resolução. Contudo, isso também amplia a largura total do código de barras. Teste ambos os valores para encontrar o equilíbrio ideal para o tamanho da sua etiqueta.

**O mesmo código funciona no .NET Framework 4.8?**  
Sim. Aspose.BarCode suporta .NET Framework 4.6.2 e posteriores, portanto você pode direcionar runtimes mais antigos sem alterações.

## Código‑fonte completo para copiar‑colar rapidamente

Abaixo está o programa completo e executável que incorpora todas as etapas descritas acima.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // ---------- Planet barcode (default height) ----------
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        planetGenerator.Save("PostalPlanetBarHeightDefault.png", BarCodeImageFormat.Png);

        // ---------- Planet barcode (custom 100‑pixel height) ----------
        BarcodeGenerator planetHeightGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        planetHeightGenerator.Save("PostalPlanetBarHeight100Pixels.png", BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode (default height) ----------
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccGenerator.Save("PostalRM4SCCBarHeightDefault.png", BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode (custom 100‑pixel height) ----------
        BarcodeGenerator rm4sccHeightGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4sccHeightGenerator.Save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);

        Console.WriteLine("All barcode images have been generated successfully.");
    }
}
```

Execute o programa e o console confirmará que cada imagem foi salva. Agora você pode incorporar esses arquivos PNG aos seus modelos de etiquetas de envio, imprimi‑los ou enviá‑los para uma API de logística de terceiros.

## Conclusão

Agora você sabe como **criar arquivos de imagem de código de barras postal** em C# usando Aspose.BarCode. O guia abordou a geração de um código de barras Planet, o ajuste da altura da barra e a aplicação da mesma técnica aos códigos de barras RM4SCC. Ao controlar `XDimension` e `BarHeight.Pixels`, você obtém resultados visuais precisos que atendem aos requisitos dos serviços postais.

Em seguida, explore tópicos relacionados, como **gerar códigos QR para rastreamento**, **incorporar códigos de barras em faturas PDF** ou **processar em lote múltiplas imagens de códigos de barras**. Ajustar a altura da barra é apenas uma alavanca; você também pode personalizar cores, adicionar texto legível por humanos ou exportar para SVG para uso na web.

Feliz codificação, e que suas remessas sejam escaneadas sem falhas!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [Create postal barcode image in C# – step‑by‑step guide](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)
- [Create Postal Barcode Images – Change Barcode Height Easily](/barcode/english/python-java/general/create-postal-barcode-images-change-barcode-height-easily/)
- [How to generate postal barcode in C# with custom dimensions](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}