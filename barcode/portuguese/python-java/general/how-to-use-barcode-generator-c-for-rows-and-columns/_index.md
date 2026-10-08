---
category: general
date: 2026-09-26
description: O guia do gerador de códigos de barras em C# mostra como definir linhas
  e como definir colunas ao criar códigos de barras Databar Expanded Stacked em C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to set rows
- how to set columns
- Databar Expanded Stacked barcode
- C# barcode library
language: pt
lastmod: 2026-09-26
og_description: O tutorial de gerador de código de barras C# explica como definir
  linhas e colunas para códigos de barras Databar Expanded Stacked, com código completo
  e dicas.
og_image_alt: Barcode generator C# example showing rows and columns settings
og_title: Gerador de código de barras C# – defina linhas e colunas passo a passo
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: barcode generator C# guide shows how to set rows and how to set columns
    when creating Databar Expanded Stacked barcodes in C#.
  headline: How to use barcode generator C# for rows and columns
  type: TechArticle
- description: barcode generator C# guide shows how to set rows and how to set columns
    when creating Databar Expanded Stacked barcodes in C#.
  name: How to use barcode generator C# for rows and columns
  steps:
  - name: Create a generator for a Databar Expanded Stacked barcode
    text: '```csharp // Create a generator for a Databar Expanded Stacked barcode
      with sample text BarcodeGenerator barcodeGenerator = new BarcodeGenerator( EncodeTypes.DatabarExpandedStacked,
      "Databar Expanded Stacked long"); ```'
  - name: How to set columns – configure the barcode to use 4 columns
    text: '```csharp // How to set columns: set the Columns property to 4 barcodeGenerator.Parameters.Barcode.DataBar.Columns
      = 4; ```'
  - name: Save the barcode image with the column setting
    text: '```csharp // Save the PNG image that reflects the column configuration
      barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
      ```'
  - name: Re‑initialize the generator for a different layout
    text: When you need a separate barcode with a different visual arrangement, create
      a new instance rather than re‑using the previous one. This guarantees that previous
      settings (like columns) do not bleed into the new configuration.
  - name: How to set rows – configure the barcode to use 3 rows
    text: '```csharp // How to set rows: assign the Rows property to 3 barcodeGenerator.Parameters.Barcode.DataBar.Rows
      = 3; ```'
  - name: Save the barcode image that includes the row setting
    text: '```csharp // Save the PNG image that reflects the row configuration barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  - name: Expected output
    text: 'Running the program produces two PNG files:'
  - name: Pro tip
    text: 'If you need to generate many barcodes with varying rows and columns, wrap
      the configuration logic in a helper method:'
  type: HowTo
tags:
- barcode
- C#
- code example
title: Como usar o gerador de código de barras C# para linhas e colunas
url: /pt/python-java/general/how-to-use-barcode-generator-c-for-rows-and-columns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como usar o gerador de código de barras C# para linhas e colunas

Se você precisa de um **barcode generator C#** que permita controlar o layout visual de um código de barras Databar Expanded Stacked, este tutorial oferece uma solução completa e executável. Você aprenderá **como definir linhas** e **como definir colunas** para que a imagem gerada corresponda exatamente ao design que você requer.

Gerar códigos de barras programaticamente costuma parecer um jogo de adivinhação sobre qual propriedade faz o quê. Ao final deste guia você entenderá a superfície da API, evitará armadilhas comuns e terá um exemplo de código pronto‑para‑executar que pode copiar para o seu próprio projeto.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 ou superior instalado (o código funciona também com .NET Core e .NET Framework)
* Uma referência à biblioteca de geração de códigos de barras que fornece `BarcodeGenerator` e `EncodeTypes` (por exemplo, Aspose.BarCode, Dynamsoft ou qualquer SDK compatível)
* Uma IDE como Visual Studio ou VS Code
* Permissão de gravação em uma pasta onde os arquivos PNG serão salvos

Nenhum pacote NuGet adicional é necessário além do próprio SDK de código de barras.

## Barcode generator C# – definindo linhas e colunas

As seções a seguir percorrem cada passo de configuração. Os trechos de código estão completos e podem ser colados diretamente no método `Main` de um aplicativo console.

### Passo 1: Crie um gerador para um código de barras Databar Expanded Stacked

```csharp
// Create a generator for a Databar Expanded Stacked barcode with sample text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
```

*Por que isso importa:* Instanciar `BarcodeGenerator` é a primeira ação que você realiza em qualquer fluxo de trabalho de **barcode generator C#**. O construtor recebe o tipo de codificação e a string de dados que será codificada.

### Passo 2: Como definir colunas – configure o código de barras para usar 4 colunas

```csharp
// How to set columns: set the Columns property to 4
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

Definir a propriedade `Columns` altera o número de módulos verticais que o DataBar utiliza. Um valor de `4` cria um código de barras mais denso e compacto, útil quando você tem espaço horizontal limitado.

### Passo 3: Salve a imagem do código de barras com a configuração de colunas

```csharp
// Save the PNG image that reflects the column configuration
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

O método `Save` grava a imagem gerada no disco. Verifique o arquivo de saída para confirmar que o layout de quatro colunas aparece conforme esperado.

![Exemplo de barcode generator C# mostrando configurações de linhas e colunas](./images/barcode-rows-columns.png)

*A imagem acima ilustra o resultado da configuração de colunas.*

### Passo 4: Re‑inicialize o gerador para um layout diferente

Quando precisar de um código de barras separado com um arranjo visual diferente, crie uma nova instância em vez de reutilizar a anterior. Isso garante que configurações anteriores (como colunas) não se misturem na nova configuração.

```csharp
// Re‑initialize to start a fresh configuration
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
```

### Passo 5: Como definir linhas – configure o código de barras para usar 3 linhas

```csharp
// How to set rows: assign the Rows property to 3
barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

A propriedade `Rows` controla o empilhamento vertical dos módulos do DataBar. Um layout de três linhas é o padrão para muitos dispositivos de leitura, mas você pode aumentá‑lo para maior densidade de dados.

### Passo 6: Salve a imagem do código de barras que inclui a configuração de linhas

```csharp
// Save the PNG image that reflects the row configuration
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

Abra `DatabarRows3.png` para ver o arranjo de três linhas. Se o código de barras não for lido, verifique novamente os valores de linhas/colunas de acordo com as especificações do seu scanner.

## Código‑fonte completo – pronto para copiar

Abaixo está o programa completo que combina todos os passos acima. Substitua `YOUR_DIRECTORY` por um caminho absoluto ou relativo que exista na sua máquina.

```csharp
using System;
using YourBarcodeSdkNamespace;   // Replace with the actual namespace of your SDK

class Program
{
    static void Main()
    {
        // ---------- Columns configuration ----------
        // 1. Create generator
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // 2. Set columns (how to set columns)
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3. Save image with column setting
        barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Rows configuration ----------
        // 4. Re‑initialize generator for a fresh instance
        barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // 5. Set rows (how to set rows)
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6. Save image with row setting
        barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

### Saída esperada

A execução do programa produz dois arquivos PNG:

| Nome do arquivo       | Descrição do layout                         |
|-----------------------|---------------------------------------------|
| `DatabarCols4.png`    | Databar Expanded Stacked com **4 colunas** |
| `DatabarRows3.png`    | Databar Expanded Stacked com **3 linhas**  |

Ambas as imagens devem ser legíveis por leitores de código de barras padrão que suportam a simbologia Databar Expanded Stacked.

## Armadilhas comuns e dicas avançadas

| Armadilha                                            | Por que acontece                              | Correção / Dica |
|------------------------------------------------------|-----------------------------------------------|-----------------|
| Usar a mesma instância de `BarcodeGenerator` para linhas e colunas | O SDK mantém a configuração anterior, de modo que definir linhas após colunas pode gerar uma mistura inesperada | Re‑inicialize o gerador (como mostrado no Passo 4) antes de mudar a outra dimensão |
| Esquecer de definir `EncodeTypes` corretamente       | O SDK usa por padrão uma simbologia diferente, gerando um código de barras inválido | Sempre passe `EncodeTypes.DatabarExpandedStacked` quando precisar desse formato específico |
| Salvar em uma pasta inexistente                      | `Save` lança exceção se o caminho for inválido   | Garanta que `YOUR_DIRECTORY` exista ou use `Directory.CreateDirectory` antes de chamar `Save` |
| Usar valores fora do intervalo permitido (ex.: 0 colunas) | O SDK valida o intervalo e lança `ArgumentOutOfRangeException` | Valores válidos de coluna são 1‑4; valores válidos de linha são 1‑3 para esta simbologia |

### Dica avançada

Se precisar gerar muitos códigos de barras com diferentes linhas e colunas, encapsule a lógica de configuração em um método auxiliar:

```csharp
static void GenerateDatabar(string text, int? rows, int? columns, string outputPath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, text);
    if (rows.HasValue)    generator.Parameters.Barcode.DataBar.Rows = rows.Value;
    if (columns.HasValue) generator.Parameters.Barcode.DataBar.Columns = columns.Value;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Essa abordagem reduz duplicação e torna o código mais fácil de manter.

## Conclusão

Agora você tem um exemplo claro, de ponta a ponta, de como usar um **barcode generator C#** para controlar tanto o número de linhas quanto o número de colunas em um código de barras Databar Expanded Stacked. Seguindo os passos acima, você pode gerar imagens de código de barras precisas que atendem aos requisitos exatos de layout do seu hardware de leitura.

A partir daqui, você pode explorar:

* Ajustar outras propriedades do `DataBar` como **AspectRatio** ou **BarHeight**
* Gerar outras simbologias (ex.: QR, Code128) com a mesma classe `BarcodeGenerator`
* Incorporar o PNG gerado em PDFs ou imprimir diretamente a partir do C#

Sinta‑se à vontade para experimentar diferentes combinações de linhas/colunas e compartilhar seus resultados nos comentários. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to set columns for a Databar Expanded Stacked barcode – complete C# guide](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [databar expanded stacked barcode guide – how to generate and size it in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}