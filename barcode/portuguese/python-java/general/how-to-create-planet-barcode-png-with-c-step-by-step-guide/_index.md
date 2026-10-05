---
category: general
date: 2026-09-07
description: Crie códigos de barras planetários PNG em C# rapidamente. Aprenda como
  gerar imagens de códigos de barras planetários usando Aspose.BarCode com barras
  preenchidas e vazias.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode png
- how to generate planet barcode
language: pt
lastmod: 2026-09-07
og_description: Crie um código de barras planetário PNG em C# rapidamente. Siga este
  guia para aprender a gerar imagens de código de barras planetário com barras preenchidas
  e vazias usando Aspose.BarCode.
og_image_alt: Planet barcode PNG image showing filled bars and empty‑bars version
og_title: Criar código de barras planetário PNG em C# – tutorial completo de programação
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  headline: How to create planet barcode PNG with C# – step‑by‑step guide
  type: TechArticle
- description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  name: How to create planet barcode PNG with C# – step‑by‑step guide
  steps:
  - name: What if I need a different data format?
    text: 'Planet barcodes accept numeric strings up to 12 digits. If you pass a non‑numeric
      value, Aspose throws an `ArgumentException`. Validate the input before creating
      the generator:'
  - name: How do I change the image size without altering bar thickness?
    text: 'Use the `Resolution` property or scale the resulting bitmap after saving:'
  - name: Can I generate other image formats?
    text: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`, `Bmp`,
      or `Gif`. The API supports all common raster formats.
  - name: What about color customization?
    text: 'Set `BarColor` and `BackColor` on the `Barcode` parameters:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Como criar um código de barras planetário PNG com C# – guia passo a passo
url: /pt/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar planet barcode PNG com C# – guia passo a passo

Se você precisar **criar planet barcode PNG** arquivos em C#, este guia mostra as etapas exatas. Seja construindo uma integração de serviço postal ou um painel de logística, você aprenderá **como gerar planet barcode** imagens com barras preenchidas e vazias usando a biblioteca Aspose.BarCode.

Neste tutorial você vai:

* Configurar a pasta de saída para suas imagens.  
* Configurar um `BarcodeGenerator` para a simbologia Planet.  
* Gerar um PNG com o estilo padrão de barras preenchidas.  
* Gerar um PNG com barras vazias para contraste visual.  

Nenhum serviço externo é necessário — tudo roda localmente no .NET 6 ou posterior.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

| Requisito | Por que é importante |
|-------------|----------------|
| .NET 6 SDK (ou mais recente) | Fornece o runtime para o aplicativo console em C#. |
| Visual Studio 2022 ou VS Code | Qualquer IDE que possa compilar projetos C#. |
| Aspose.BarCode for .NET (pacote NuGet `Aspose.BarCode`) | Fornece a classe `BarcodeGenerator` usada para renderizar planet barcodes. |
| Permissão de gravação em uma pasta no disco | Os arquivos PNG serão salvos neste local. |

Instale o pacote NuGet com o seguinte comando:

```bash
dotnet add package Aspose.BarCode
```

## Etapa 1: Criar um novo projeto console

Abra um terminal e execute:

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
```

Isso cria uma aplicação console C# mínima chamada **PlanetBarcodeDemo**.

## Etapa 2: Definir o diretório de saída

A primeira parte do código determina onde os arquivos PNG gerados serão armazenados. Usar um caminho absoluto ou relativo funciona; basta garantir que a pasta exista ou deixar o programa criá‑la.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Define the output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputDir); // Guarantees the folder exists
```

*Por que esta etapa?* Separar a saída do código‑fonte mantém seu projeto organizado e evita sobrescritas acidentais.

## Etapa 3: Gerar um planet barcode com barras preenchidas

Um planet barcode consiste em círculos concêntricos (preenchidos por padrão). Configuramos a X‑dimension (largura em pixels de cada barra) e então salvamos a imagem como PNG.

```csharp
        // Step 3: Create a Planet barcode with the default (filled) bars
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4; // Controls bar thickness

        // Save the filled‑bars barcode as PNG
        string filledPath = Path.Combine(outputDir, "PostalPlanetFilledBars.png");
        planetFilled.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to: {filledPath}");
```

**Explicação**

* `EncodeTypes.Planet` indica ao Aspose que deve usar a simbologia Planet, comum em serviços postais.  
* `XDimension.Pixels = 4` produz um tamanho claro e imprimível sem necessidade de escala manual.  
* O método `Save` grava um arquivo PNG; você também pode escolher JPEG ou BMP alterando o `BarCodeImageFormat`.

## Etapa 4: Gerar um planet barcode com barras vazias

Às vezes, um visual com barras vazias (transparentes) é necessário — por exemplo, quando o código de barras é sobreposto a um fundo colorido. Definir `FilledBars` como `false` produz esse estilo.

```csharp
        // Step 4: Create a Planet barcode with empty bars
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmpty.Parameters.Barcode.FilledBars = false; // Switch to empty‑bars mode

        // Save the empty‑bars barcode as PNG
        string emptyPath = Path.Combine(outputDir, "PostalPlanetEmptyBars.png");
        planetEmpty.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to: {emptyPath}");
```

**Explicação**

* `FilledBars = false` desativa os círculos sólidos, deixando apenas os contornos.  
* Todas as demais configurações (X‑dimension, string de dados) permanecem idênticas, garantindo que ambas as imagens representem os mesmos dados.

## Etapa 5: Executar o programa e verificar a saída

Compile e execute:

```bash
dotnet run
```

Você deverá ver mensagens no console confirmando os arquivos salvos, e a pasta `Barcodes` conterá:

* `PostalPlanetFilledBars.png` – um planet barcode clássico com barras preenchidas.  
* `PostalPlanetEmptyBars.png` – os mesmos dados renderizados com barras vazias.

Abra os PNGs em qualquer visualizador de imagens. Ambas as imagens codificam a string numérica **123456** e podem ser lidas por leitores padrão de códigos de barras postais.

## Perguntas comuns e tratamento de casos extremos

### E se eu precisar de um formato de dados diferente?

Planet barcodes aceitam strings numéricas de até 12 dígitos. Se você passar um valor não numérico, o Aspose lança uma `ArgumentException`. Valide a entrada antes de criar o gerador:

```csharp
if (!Regex.IsMatch(data, @"^\d{1,12}$"))
    throw new ArgumentException("Planet barcode data must be numeric and up to 12 digits.");
```

### Como mudar o tamanho da imagem sem alterar a espessura das barras?

Use a propriedade `Resolution` ou escale o bitmap resultante após a gravação:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI for high‑resolution print
```

### Posso gerar outros formatos de imagem?

Sim. Substitua `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg`, `Bmp` ou `Gif`. A API suporta todos os formatos raster comuns.

### E quanto à personalização de cores?

Defina `BarColor` e `BackColor` nos parâmetros do `Barcode`:

```csharp
planetFilled.Parameters.Barcode.BarColor = Color.DarkBlue;
planetFilled.Parameters.Barcode.BackColor = Color.LightYellow;
```

Essas opções funcionam tanto para as versões com barras preenchidas quanto para as com barras vazias.

## Dicas profissionais para uso em produção

* **Cache o gerador** quando precisar renderizar muitos códigos de barras com as mesmas configurações — inicializar o objeto repetidamente adiciona sobrecarga.  
* **Dispose** dos objetos `BarcodeGenerator` se você criar muitos em um loop (eles implementam `IDisposable`).  
* **Valide a pasta de saída** logo no início para evitar exceções em tempo de execução em diretórios protegidos contra gravação.  

## Conclusão

Agora você sabe como **criar planet barcode PNG** arquivos em C# e entende **como gerar planet barcode** imagens com estilos de barras preenchidas e vazias. O exemplo completo e executável demonstra como configurar o diretório de saída, configurar o `BarcodeGenerator` e salvar os resultados como arquivos PNG.

Em seguida, você pode explorar:

* Adicionar **texto legível por humanos** abaixo do código de barras (`planetFilled.Parameters.Caption.Visible = true`).  
* Integrar os PNGs gerados em uma **fatura PDF** usando Aspose.PDF.  
* Trocar para outras simbologias postais como **IMB** ou **ITF** (`EncodeTypes.IMB`, `EncodeTypes.ITF`).  

Sinta‑se à vontade para experimentar a espessura das barras, cores e resoluções de imagem para atender aos requisitos específicos da sua aplicação. Feliz codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Create Planet Barcode Image in C# – How to Generate Postal Barcode](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Generate PNG Barcode with Aspose.BarCode for .NET: One-Dimensional Filled Bars](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-filled-bars-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}