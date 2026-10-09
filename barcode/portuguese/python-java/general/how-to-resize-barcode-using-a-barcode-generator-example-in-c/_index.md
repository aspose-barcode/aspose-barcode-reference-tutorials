---
category: general
date: 2026-10-08
description: Aprenda a redimensionar imagens de código de barras com um exemplo de
  gerador de códigos de barras em C#, ajustando a altura das barras de 30 px para
  60 px em apenas algumas linhas de código.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- barcode generator example c#
language: pt
lastmod: 2026-10-08
og_description: Como redimensionar códigos de barras rapidamente com um exemplo de
  gerador de códigos de barras em C#. Ajuste a altura das barras, salve arquivos PNG
  e evite armadilhas comuns.
og_image_alt: Screenshot showing a resized barcode generated with C# code
og_title: Como redimensionar código de barras em C# – exemplo passo a passo de gerador
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  headline: How to resize barcode using a barcode generator example in C#
  type: TechArticle
- description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  name: How to resize barcode using a barcode generator example in C#
  steps:
  - name: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
    text: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
  - name: Print the images at 100 % scale.
    text: Print the images at 100 % scale.
  - name: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
    text: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
  type: HowTo
tags:
- barcode
- C#
- image processing
title: Como redimensionar código de barras usando um exemplo de gerador de código
  de barras em C#
url: /pt/python-java/general/how-to-resize-barcode-using-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como redimensionar código de barras usando um exemplo de gerador de código de barras em C#

Se você precisa **redimensionar código de barras** em um projeto .NET, este guia mostra a solução completa. Você verá um conciso **exemplo de gerador de código de barras C#** que altera a altura da barra de 30 px para 60 px e salva cada versão como um arquivo PNG.

Redimensionar um código de barras costuma ser necessário quando os mesmos dados devem aparecer em recibos, etiquetas ou páginas de produto em diferentes escalas visuais. Em vez de editar a imagem raster com um editor externo, você pode ajustar as dimensões do código de barras programaticamente, mantendo a integridade dos dados intacta.

Neste tutorial você irá:

* Configurar um gerador de código de barras DataBar Omni‑Directional.  
* Modificar os parâmetros X‑dimension e bar height.  
* Salvar duas imagens com alturas distintas.  
* Entender por que mudar a altura da barra funciona e quais casos‑limite observar.

> **Pré-requisito** – Você tem um ambiente de desenvolvimento .NET (Visual Studio 2022 ou posterior) e a biblioteca de código de barras que fornece `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat`. O código funciona com a versão mais recente da biblioteca em outubro 2026.

## Pré-requisitos para o exemplo de gerador de código de barras C#

Antes de começar, certifique‑se de que você tem:

| Item | Motivo |
|------|--------|
| .NET 6.0 SDK ou mais recente | Fornece o runtime e os recursos de linguagem usados no exemplo. |
| Biblioteca de código de barras (por exemplo, Aspose.BarCode, Dynamsoft ou qualquer biblioteca que exponha `BarcodeGenerator`) | Disponibiliza o enum `EncodeTypes.DatabarOmniDirectional` e os métodos de exportação de imagem. |
| Uma pasta onde você possa gravar (por exemplo, `C:\Temp\Barcodes\`) | O exemplo salva arquivos PNG neste local. |
| Conhecimento básico de C# | O tutorial pressupõe familiaridade com classes, propriedades e interpolação de strings. |

Instale a biblioteca via NuGet se ainda não o fez:

```bash
dotnet add package Aspose.BarCode
```

Substitua o nome do pacote pelo que você realmente usa; a superfície da API mostrada abaixo é comum à maioria dos SDKs de código de barras.

## Como redimensionar código de barras – passo 1: criar o gerador

O primeiro passo é instanciar um `BarcodeGenerator` com a simbologia desejada e a carga de dados. Neste exemplo geramos um código de barras **DataBar Omni‑Directional** que codifica um valor GTIN‑14.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a DataBar Omni‑Directional barcode generator with the desired data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

**Por que isso importa:** O enum `EncodeTypes.DatabarOmniDirectional` indica à biblioteca qual padrão de código de barras usar. A string de dados segue o Identificador de Aplicação GS1 `(01)` para um GTIN de 14 dígitos, garantindo que o código de barras esteja em conformidade com os padrões de comércio global.

## Como redimensionar código de barras – passo 2: definir a largura do módulo e a altura inicial da barra

O tamanho visual de um código de barras depende de dois parâmetros:

* **X‑dimension** – a largura da menor barra (módulo). Medida em pixels ou milímetros.  
* **Bar height** – o comprimento vertical das barras.

Definir esses valores antes de salvar garante que a imagem renderizada corresponda às dimensões que você precisa.

```csharp
// Step 2: Define the X‑dimension (module width) and set the bar height to 30 px
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2 px per module
generator.Parameters.Barcode.BarHeight.Pixels = 30; // 30 px tall bars
```

**Explicação:** Uma X‑dimension de 2 px gera um código de barras compacto que ainda escaneia de forma confiável. A altura de 30 px é um padrão comum para etiquetas pequenas. Você pode ajustar a X‑dimension independentemente da altura se precisar de um padrão mais denso ou mais espaçado.

## Como redimensionar código de barras – passo 3: salvar a primeira imagem (altura 30 px)

Agora exporte o código de barras para um arquivo PNG. O método `Save` aceita um caminho de arquivo e um enum de formato de imagem.

```csharp
// Step 3: Save the barcode image with a 30 px height
string outputPath = @"C:\Temp\Barcodes\";
generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Resultado:** `DatabarBarHeight30Pixels.png` contém um código de barras com 30 px de altura. Você pode abrir o arquivo em qualquer visualizador de imagens para verificar as dimensões.

## Como redimensionar código de barras – passo 4: mudar a altura da barra para 60 px

Para criar uma versão maior, basta modificar a propriedade `BarHeight`. O gerador reutiliza os mesmos dados e X‑dimension, de modo que o padrão do código de barras permanece idêntico — apenas o tamanho visual muda.

```csharp
// Step 4: Change the bar height to 60 px for a larger barcode
generator.Parameters.Barcode.BarHeight.Pixels = 60;
```

**Por que isso funciona:** O motor de renderização do código de barras calcula a geometria de cada barra sob demanda. Atualizar a propriedade de altura antes da próxima chamada a `Save` dispara uma nova rasterização com as novas dimensões.

## Como redimensionar código de barras – passo 5: salvar a segunda imagem (altura 60 px)

```csharp
// Step 5: Save the barcode image with a 60 px height
generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Agora você tem dois arquivos PNG, um pequeno (30 px) e outro maior (60 px), prontos para uso em diferentes tamanhos de etiqueta.

## Código‑fonte completo para o exemplo de gerador de código de barras C#

Abaixo está o programa completo e executável. Copie‑o para um novo projeto de console para testar imediatamente.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeResizeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with DataBar Omni‑Directional symbology
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension and initial bar height (30 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 3️⃣ Define output folder (ensure it exists)
            string outputPath = @"C:\Temp\Barcodes\";
            System.IO.Directory.CreateDirectory(outputPath);

            // 4️⃣ Save the 30 px version
            generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30 px barcode.");

            // 5️⃣ Increase bar height to 60 px
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the 60 px version
            generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60 px barcode.");
        }
    }
}
```

**Saída esperada no console:**

```
Saved 30 px barcode.
Saved 60 px barcode.
```

Após a execução, abra os dois arquivos PNG para ver a diferença visual. Ambos os códigos de barras codificam o mesmo valor GTIN‑14 e serão escaneados identicamente, independentemente da altura.

## Por que ajustar a altura da barra é seguro para a leitura

Os scanners de código de barras leem o padrão de módulos claros e escuros, não a contagem absoluta de pixels. Enquanto a **X‑dimension** permanecer dentro da tolerância do scanner (geralmente de 0,5 mm a 2 mm em unidades físicas), mudar a altura não afeta a legibilidade. A biblioteca escala automaticamente os módulos, preservando as zonas silenciosas e os padrões de alinhamento necessários.

## Armadilhas comuns e como evitá‑las

| Armadilha | Como corrigir |
|-----------|---------------|
| **A pasta de saída não existe** | Chame `Directory.CreateDirectory(outputPath)` antes de salvar. |
| **X‑dimension incorreta causando leituras borradas** | Mantenha `XDimension.Pixels` entre 1 px e 4 px para a maioria das impressoras; teste com um scanner físico. |
| **Usar formato raster para códigos de barras muito grandes** | Troque para `BarCodeImageFormat.Svg` para escalabilidade infinita sem pixelização. |
| **Esquecer de redefinir `BarHeight` antes do segundo salvamento** | Certifique‑se de atribuir a nova altura **antes** de chamar `Save` novamente. |

## Dica profissional: gerar múltiplos tamanhos em um loop

Se você precisar de uma gama de alturas (por exemplo, 30 px, 45 px, 60 px), um simples loop `foreach` reduz a duplicação:

```csharp
int[] heights = { 30, 45, 60 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputPath}DatabarBarHeight{h}Pixels.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {h} px barcode.");
}
```

Esse padrão escala bem para processamento em lote de catálogos de produtos.

## Casos‑limite: diferentes formatos de imagem e configurações de DPI

* **Saída SVG** – Use `BarCodeImageFormat.Svg` para produzir um arquivo vetorial que pode ser redimensionado sem perda de qualidade.  
* **PNG de alta DPI** – Defina `generator.Parameters.Image.DpiX` e `DpiY` para 300 ou 600 para imagens prontas para impressão; a altura da barra ainda será medida em pixels, portanto aumente‑a proporcionalmente.  
* **Simbologias não‑padrão** – Alguns tipos de código de barras (por exemplo, QR Code) possuem uma propriedade `Size` separada em vez de `BarHeight`. Consulte a documentação da biblioteca para esses casos.

## Testando o código de barras redimensionado

1. Abra cada PNG em um visualizador de imagens e verifique as dimensões em pixels (ex.: 150 × 30 px vs. 150 × 60 px).  
2. Imprima as imagens em escala 100 %.  
3. Escaneie com um leitor de código de barras portátil ou um aplicativo móvel. Os dados decodificados devem ser

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Exemplo de gerador de código de barras em C# – definir largura e altura](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [Como redimensionar código de barras em C# com Aspose.BarCode – guia passo a passo](/barcode/english/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/)
- [Como salvar imagens de código de barras com Barcode Generator C# – guia passo a passo](/barcode/english/python-java/general/how-to-save-barcode-images-with-barcode-generator-c-step-by/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}