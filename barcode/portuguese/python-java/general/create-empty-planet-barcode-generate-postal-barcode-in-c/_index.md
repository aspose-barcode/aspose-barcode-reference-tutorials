---
category: general
date: 2026-10-08
description: Crie um código de barras planetário vazio com C# e aprenda como gerar
  código de barras postal usando Aspose.BarCode. Código passo a passo e dicas incluídas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create empty planet barcode
- how to generate postal barcode
- Aspose.BarCode C#
- postal barcode example
- barcode XDimension setting
language: pt
lastmod: 2026-10-08
og_description: Crie um código de barras planetário vazio com Aspose.BarCode em C#
  e veja como gerar imagens de códigos de barras postais para aplicações de correio.
og_image_alt: Screenshot of generated empty Planet barcode and filled RM4SCC barcode
og_title: Criar código de barras planetário vazio – Guia de código de barras postal
  em C#
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Create empty planet barcode with C# and learn how to generate postal
    barcode using Aspose.BarCode. Step‑by‑step code and tips included.
  headline: Create empty planet barcode, generate postal barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- postal
title: Criar código de barras de planeta vazio, gerar código de barras postal em C#
url: /pt/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar código de barras planetário vazio, gerar código de barras postal em C#

Se você precisar **criar um código de barras planetário vazio** para um sistema de correspondência, este guia mostra exatamente como fazer isso com Aspose.BarCode para .NET. Você também aprenderá **como gerar códigos de barras postais** como Planet e RM4SCC, personalizar a largura das barras e controlar a opção de barras preenchidas.

Gerar códigos de barras postais não requer uma biblioteca gráfica separada. O SDK Aspose.BarCode fornece uma única API que lida com codificação, renderização de imagem e seleção de formato de imagem. Ao final deste tutorial você terá três arquivos PNG prontos para uso:

* `PostalPlanetEmptyBars.png` – um código de barras Planet com barras vazias  
* `PostalPlanetFilledBars.png` – o código de barras Planet padrão com barras preenchidas  
* `PostalRM4SCCFilledBars.png` – um código de barras RM4SCC com barras preenchidas  

Você pode inserir esses arquivos em qualquer modelo de etiqueta de correspondência, imprimi‑los em envelopes ou enviá‑los a um serviço de terceiros.

## Pré-requisitos

* .NET 6.0 ou superior (o código também funciona com .NET Framework 4.7+).  
* Visual Studio 2022 ou qualquer IDE C#.  
* Aspose.BarCode para .NET – instale via NuGet:

```bash
dotnet add package Aspose.BarCode
```

Nenhuma dependência adicional é necessária.

## Criar código de barras planetário vazio com Aspose.BarCode

A simbologia Planet faz parte da família de códigos de barras do United States Postal Service (USPS). Por padrão, o SDK desenha barras **preenchidas**. Para **criar um código de barras planetário vazio**, você desabilita a flag `FilledBars`.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1 – instantiate a Planet barcode generator with the data to encode.
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Step 2 – set the width of a single bar. XDimension defines the pixel size of one bar.
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Step 3 – disable the FilledBars option to get empty (hollow) bars.
planetEmpty.Parameters.Barcode.FilledBars = false;

// Step 4 – save the image. The PNG format is widely supported by printers and browsers.
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Por que isso funciona:**  
`EncodeTypes.Planet` indica ao gerador que deve usar a simbologia Planet. `XDimension.Pixels` controla a largura física de cada barra, o que é crucial para scanners postais que esperam um tamanho de módulo específico. Definir `FilledBars` como `false` instrui o renderizador a desenhar apenas o contorno de cada barra, produzindo a aparência *vazia* exigida por alguns padrões de correspondência.

### Saída esperada

Você encontrará `PostalPlanetEmptyBars.png` na pasta de destino. A imagem mostra um código de barras Planet onde cada barra é um contorno ao invés de um retângulo sólido.

![Empty Planet barcode example](empty-planet.png){: .align-center alt="Criar código de barras planetário vazio – exemplo de um código de barras Planet com barras vazias"}

## Como gerar imagens de código de barras postal (versão preenchida)

A maioria dos fluxos de trabalho postais usa a versão padrão de barras preenchidas. A mesma API pode gerar um código de barras Planet preenchido e um código de barras RM4SCC com apenas algumas linhas de código.

```csharp
// Filled Planet barcode (default behavior)
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// RM4SCC barcode – another USPS format that always uses filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
```

**Por que você pode precisar do RM4SCC:**  
RM4SCC é o código de barras USPS mais recente que codifica os mesmos dados que o Planet, porém com maior densidade. Alguns transportadores exigem RM4SCC para descontos em envios em massa. O código acima demonstra como **gerar código de barras postal** para ambos os padrões sem alterar o fluxo de trabalho geral.

### Saída esperada

* `PostalPlanetFilledBars.png` – um clássico código de barras Planet com barras preenchidas.  
* `PostalRM4SCCFilledBars.png` – um código de barras RM4SCC com barras preenchidas, visualmente semelhante, mas com espaçamento mais apertado.

Ambos os arquivos podem ser abertos em qualquer visualizador de imagens para verificar os padrões das barras.

## Ajustando a largura das barras para diferentes resoluções de impressão

Scanners postais frequentemente especificam uma largura mínima de módulo (por exemplo, 0.013 polegadas). Se sua impressora trabalha a 300 dpi, um módulo de 4 pixels corresponde a 0.013 polegadas. Ajuste o valor `XDimension.Pixels` para corresponder ao seu hardware:

| Módulo desejado (polegadas) | DPI | Pixels necessários (`XDimension`) |
|-----------------------------|-----|------------------------------------|
| 0.013                       | 300 | 4                                  |
| 0.013                       | 600 | 8                                  |
| 0.015                       | 300 | 5                                  |

**Dica de especialista:** Sempre teste a


## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to create planet barcode PNG with C# – step‑by‑step guide](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/)
- [Generate Postal Barcode in C# – Complete Guide with Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)
- [How to generate postal barcode in C# with Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}