---
category: general
date: 2026-08-09
description: Crie imagem de código de barras em C# com este guia passo a passo. Aprenda
  como gerar código de barras, ajustar a altura do código de barras em pixels e criar
  múltiplos códigos de barras de forma eficiente.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create multiple barcodes
- barcode height pixels
language: pt
lastmod: 2026-08-09
og_description: Crie rapidamente uma imagem de código de barras em C#. Siga este tutorial
  para aprender como gerar códigos de barras, definir a altura em pixels do código
  de barras e produzir múltiplos códigos de barras.
og_image_alt: Screenshot of barcode images generated with C# code showing different
  heights
og_title: Crie imagem de código de barras em C# – guia completo para desenvolvedores
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  headline: Create barcode image in C# – complete programming guide
  type: TechArticle
- description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  name: Create barcode image in C# – complete programming guide
  steps:
  - name: Define the output folder
    text: Choose a folder where the generated PNG files will be stored. Using an absolute
      path avoids permission surprises.
  - name: Instantiate the barcode generator
    text: For a DataBar Omnidirectional barcode, pass `EncodeTypes.DatabarOmniDirectional`
      and the GS1‑128 data string.
  - name: Set common barcode parameters
    text: The most common visual tweaks are the X‑dimension (module width) and the
      bar height. Both are expressed in pixels.
  - name: Save the first barcode image
    text: '```csharp // Step 4: Save the barcode image with a 30 px height string
      file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"); barcode.Save(file30,
      BarCodeImageFormat.Png); ```'
  - name: Adjust the barcode height pixels
    text: Changing the height does not require a new `BarcodeGenerator` instance—just
      modify the parameter.
  - name: Save the second barcode image
    text: '```csharp // Step 6: Save the barcode image with the new 60 px height string
      file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"); barcode.Save(file60,
      BarCodeImageFormat.Png); ```'
  - name: Expected output
    text: 'After running the full sample, the `Barcodes` folder contains:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Criar imagem de código de barras em C# – guia completo de programação
url: /pt/python-java/general/create-barcode-image-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar imagem de código de barras em C# – guia completo de programação

Se você precisa **criar imagem de código de barras** em uma aplicação .NET, este guia mostra exatamente **como gerar código de barras** usando a biblioteca Aspose.BarCode. Você verá como controlar os **pixels de altura do código de barras**, salvar a imagem e produzir **múltiplos códigos de barras** sem duplicar código.

O tutorial cobre tudo, desde a instalação do pacote até a personalização das dimensões, para que você possa copiar‑colar um exemplo pronto‑para‑executar em seu projeto hoje.

## Pré-requisitos

Antes de começar, certifique-se de que você tem:

* .NET 6.0 SDK ou posterior instalado  
* Visual Studio 2022 (ou qualquer IDE C#)  
* Pacote NuGet `Aspose.BarCode` – instale com  

```bash
dotnet add package Aspose.BarCode
```

Nenhuma dependência adicional é necessária.

## Como gerar imagem de código de barras com BarcodeGenerator C#

A classe principal para criar uma imagem de código de barras é `BarcodeGenerator`. Ela encapsula o tipo de codificação, a string de dados e todos os parâmetros de renderização.

### Etapa 1: Definir a pasta de saída

Escolha uma pasta onde os arquivos PNG gerados serão armazenados. Usar um caminho absoluto evita surpresas de permissão.

```csharp
// Step 1: Define the output folder
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputFolder);
```

> **Por quê?** Criar a pasta programaticamente garante que as chamadas subsequentes de `Save` sejam bem‑sucedidas mesmo em uma máquina nova.

### Etapa 2: Instanciar o gerador de código de barras

Para um código de barras DataBar Omnidirectional, passe `EncodeTypes.DatabarOmniDirectional` e a string de dados GS1‑128.

```csharp
// Step 2: Create a DataBar Omnidirectional barcode generator with the data to encode
var barcode = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

> **Nota:** O objeto `BarcodeGenerator` é reutilizável; você pode alterar seus parâmetros entre salvamentos para **criar múltiplos códigos de barras** a partir dos mesmos dados.

### Etapa 3: Definir parâmetros comuns do código de barras

Os ajustes visuais mais comuns são a X‑dimension (largura do módulo) e a altura da barra. Ambos são expressos em pixels.

```csharp
// Step 3: Set common barcode parameters (X‑dimension and initial height)
barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin modules for sharper output
barcode.Parameters.Barcode.BarHeight.Pixels = 30;  // initial height – 30 px
```

> **Por que definir X‑dimension?** Uma X‑dimension menor produz maior resolução, o que é importante quando a imagem será impressa ou exibida em telas de alta DPI.

### Etapa 4: Salvar a primeira imagem de código de barras

```csharp
// Step 4: Save the barcode image with a 30 px height
string file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png");
barcode.Save(file30, BarCodeImageFormat.Png);
```

O arquivo `DatabarBarHeight30Pixels.png` agora contém um código de barras DataBar Omnidirectional com 30 pixels de altura.

### Etapa 5: Ajustar os pixels de altura do código de barras

Alterar a altura não requer uma nova instância de `BarcodeGenerator`—basta modificar o parâmetro.

```csharp
// Step 5: Change the bar height to 60 px for the same barcode
barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

### Etapa 6: Salvar a segunda imagem de código de barras

```csharp
// Step 6: Save the barcode image with the new 60 px height
string file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png");
barcode.Save(file60, BarCodeImageFormat.Png);
```

Agora você tem dois arquivos PNG com diferentes **pixels de altura do código de barras**, demonstrando como é fácil criar variações de **imagem de código de barras**.

## Definindo pixels de altura do código de barras dinamicamente

Frequentemente você precisa de uma série de códigos de barras com alturas que correspondam a elementos de UI ou etiquetas impressas. O método auxiliar a seguir abstrai a mudança de altura:

```csharp
/// <summary>
/// Saves a barcode image with a custom height.
/// </summary>
/// <param name="generator">Configured BarcodeGenerator instance.</param>
/// <param name="heightPx">Desired bar height in pixels.</param>
/// <param name="fileName">Target file name (including path).</param>
void SaveBarcodeWithHeight(BarcodeGenerator generator, int heightPx, string fileName)
{
    generator.Parameters.Barcode.BarHeight.Pixels = heightPx;
    generator.Save(fileName, BarCodeImageFormat.Png);
}
```

Agora você pode chamar `SaveBarcodeWithHeight(barcode, 45, "BarHeight45.png");` para **criar imagem de código de barras** com altura de 45 pixels em uma única linha.

## Criando múltiplos códigos de barras em um loop

Quando você tem uma coleção de identificadores de produto, um loop `foreach` elimina código repetitivo. Este exemplo mostra como **criar múltiplos códigos de barras** a partir de um array de GTINs.

```csharp
string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
int[] heights = { 30, 45, 60 }; // different heights for visual variety

for (int i = 0; i < gtins.Length; i++)
{
    // Encode each GTIN as a DataBar Omnidirectional barcode
    var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                   $"(01){gtins[i]}");

    // Reuse the X‑dimension setting for consistency
    gen.Parameters.Barcode.XDimension.Pixels = 2;

    // Choose a height from the heights array (or calculate dynamically)
    int height = heights[i % heights.Length];
    string filePath = Path.Combine(outputFolder,
        $"Databar_{gtins[i]}_Height{height}px.png");

    SaveBarcodeWithHeight(gen, height, filePath);
}
```

O loop produz três arquivos PNG, cada um com um valor distinto de **pixels de altura do código de barras**. Como o auxiliar `SaveBarcodeWithHeight` encapsula a mudança de altura, o loop principal permanece limpo e focado nos dados.

### Saída esperada

Após executar o exemplo completo, a pasta `Barcodes` contém:

```
DatabarBarHeight30Pixels.png
DatabarBarHeight60Pixels.png
Databar_01234567890123_Height30px.png
Databar_09876543210987_Height45px.png
Databar_12345098765432_Height60px.png
```

Abrir qualquer PNG mostra um código de barras DataBar Omnidirectional nítido que pode ser escaneado por aplicativos móveis padrão.

## Armadilhas comuns e dicas avançadas

| Problema | Por que acontece | Como evitar |
|----------|------------------|--------------|
| **EncodeTypes errado** | Usar um tipo 1D para um DataBar produzirá uma imagem ilegível. | Sempre escolha `EncodeTypes.DatabarOmniDirectional` (ou outra variante DataBar) para cargas úteis GS1‑128. |
| **X‑dimension insuficiente** | X‑dimension muito baixa pode fazer as barras finas desaparecerem em monitores de baixa resolução. | Mantenha `XDimension.Pixels` ≥ 2 para exibição em tela; aumente para 3‑4 para impressão. |
| **Erros de caminho de arquivo** | Caminhos relativos podem resolver para diretórios inesperados. | Use `Path.Combine` e `Environment.CurrentDirectory` para construir caminhos absolutos. |
| **Sobrescrita de imagens** | Reutilizar o mesmo nome de arquivo em um loop sobrescreve resultados anteriores. | Inclua identificadores únicos (ex.: GTIN ou timestamp) no nome do arquivo. |
| **Pacote NuGet ausente** | O código compila mas lança `FileNotFoundException` em tempo de execução. | Verifique se `Aspose.BarCode` está instalado e o projeto o referencia. |

## Exemplo completo em funcionamento

Abaixo está o programa completo que você pode copiar para uma aplicação console. Ele inclui todas as etapas, métodos auxiliares e tratamento de erros.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Prepare output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // ---------- Single barcode with two heights ----------
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        barcode.Parameters.Barcode.XDimension.Pixels = 2;
        barcode.Parameters.Barcode.BarHeight.Pixels = 30;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);

        // ---------- Helper for dynamic heights ----------
        void SaveBarcodeWithHeight(BarcodeGenerator gen, int heightPx, string fileName)
        {
            gen.Parameters.Barcode.BarHeight.Pixels = heightPx;
            gen.Save(fileName, BarCodeImageFormat.Png);
        }

        // ---------- Multiple barcodes ----------
        string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
        int[] heights = { 30, 45, 60 };

        for (int i = 0; i < gtins.Length; i++)
        {
            var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                           $"(01){gtins[i]}");
            gen.Parameters.Barcode.XDimension.Pixels = 2;

            int height = heights[i % heights.Length];
            string filePath = Path.Combine(outputFolder,
                $"Databar_{gtins[i]}_Height{height}px.png");

            SaveBarcodeWithHeight(gen, height, filePath);
        }

        Console.WriteLine($"Barcode images created in: {outputFolder}");
    }
}
```

Executando este programa

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Criar código de barras com altura personalizada – códigos de barras unidimensionais](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [Criar imagem de código de barras C# – Exemplo GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Criar imagem de código de barras DotCode – linhas & colunas (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}