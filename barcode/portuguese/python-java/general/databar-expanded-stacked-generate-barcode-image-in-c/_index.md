---
category: general
date: 2026-08-15
description: Databar expandiu a geração de códigos de barras empilhados em C#. Aprenda
  a gerar a imagem do código de barras, definir colunas e linhas para layouts DataBar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- how to generate barcode
- how to set columns
- how to set rows
language: pt
lastmod: 2026-08-15
og_description: Databar expandiu a geração de códigos de barras empilhados em C#.
  Siga este guia passo a passo para gerar imagens de códigos de barras, definir colunas
  e definir linhas de forma eficiente.
og_image_alt: Screenshot of a databar expanded stacked barcode generated with C#
og_title: Databar expandido empilhado – gerar imagem de código de barras em C#
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Databar expanded stacked barcode generation in C#. Learn how to generate
    barcode image, set columns and rows for DataBar layouts.
  headline: 'Databar expanded stacked: generate barcode image in C#'
  type: TechArticle
- description: Databar expanded stacked barcode generation in C#. Learn how to generate
    barcode image, set columns and rows for DataBar layouts.
  name: 'Databar expanded stacked: generate barcode image in C#'
  steps:
  - name: 1. Install the Aspose.BarCode library
    text: 'The code uses the **Aspose.BarCode for .NET** library, which provides the
      `BarcodeGenerator` class. Install the NuGet package with the following command:'
  - name: 2. Create a barcode generator for **databar expanded stacked**
    text: The generator is the entry point for all barcode operations. You must specify
      the symbology (`EncodeTypes.DatabarExpandedStacked`) and the text to encode.
  - name: 3. How to set columns for DataBar
    text: The `Columns` property controls how many vertical modules appear in the
      stacked barcode. Valid values are 2, 3, or 4. Setting columns influences the
      barcode’s width and the amount of data it can store.
  - name: 4. Save the 4‑column barcode image
    text: Saving the image produces a file that you can embed in reports, invoices,
      or mobile apps. The `Save` method accepts a file path and an image format.
  - name: 5. How to set rows for DataBar
    text: Rows add a second dimension to the stacked layout, allowing more data to
      be encoded without widening the barcode. The `Rows` property defaults to 1;
      you can increase it up to 3 for the expanded stacked variant.
  - name: 6. Save the 3‑row barcode image
    text: '```csharp // Step 5: Save the 3‑row barcode image barcode.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  - name: 7. Complete C# example to generate barcode image
    text: 'Putting all steps together yields a self‑contained program you can copy
      into a console application:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 'Databar expanded stacked: gerar imagem de código de barras em C#'
url: /pt/python-java/general/databar-expanded-stacked-generate-barcode-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Databar expanded stacked: gerar imagem de código de barras em C#

Se você precisa gerar uma imagem de código de barras **databar expanded stacked** em C#, este guia mostra exatamente **como gerar códigos de barras** com layouts personalizados de colunas e linhas. Você verá como definir colunas, como definir linhas e como salvar as imagens resultantes sem sair da IDE.

O tutorial aborda:

* Criação de um gerador de código de barras para a simbologia **databar expanded stacked**.  
* Configuração de um layout de 4 colunas e um layout de 3 linhas.  
* Salvamento de cada configuração como um arquivo PNG.  
* Dicas para lidar com casos de borda, como contagens de colunas inválidas.

Nenhuma documentação externa é necessária; o exemplo completo e executável está incluído.

![Databar expanded stacked barcode example](YOUR_DIRECTORY/DatabarCols4.png){: .center alt="código de barras databar expanded stacked gerado com C#" }

## Etapas para geração de código de barras Databar expanded stacked

### 1. Instale a biblioteca Aspose.BarCode

O código usa a biblioteca **Aspose.BarCode for .NET**, que fornece a classe `BarcodeGenerator`. Instale o pacote NuGet com o seguinte comando:

```bash
dotnet add package Aspose.BarCode
```

Depois que o pacote for instalado, adicione o namespace necessário no topo do seu arquivo:

```csharp
using Aspose.BarCode.Generation;
```

### 2. Crie um gerador de código de barras para **databar expanded stacked**

O gerador é o ponto de entrada para todas as operações de código de barras. Você deve especificar a simbologia (`EncodeTypes.DatabarExpandedStacked`) e o texto a ser codificado.

```csharp
// Step 1: Create a barcode generator for Databar Expanded Stacked
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*Por que isso importa:* O enum `EncodeTypes` informa à biblioteca qual formato de código de barras produzir. Usar **databar expanded stacked** garante que a imagem resultante siga a especificação GS1 DataBar para layouts empilhados.

### 3. Como definir colunas para DataBar

A propriedade `Columns` controla quantos módulos verticais aparecem no código de barras empilhado. Valores válidos são 2, 3 ou 4. Definir colunas influencia a largura do código de barras e a quantidade de dados que ele pode armazenar.

```csharp
// Step 2: Configure a 4‑column layout
barcode.Parameters.Barcode.DataBar.Columns = 4;
```

**Dica:** Se você tentar atribuir um valor fora do intervalo permitido, a biblioteca lançará uma `ArgumentException`. Sempre valide a entrada ao expor a seleção de colunas para os usuários.

### 4. Salve a imagem de código de barras com 4 colunas

Salvar a imagem gera um arquivo que pode ser incorporado em relatórios, notas fiscais ou aplicativos móveis. O método `Save` aceita um caminho de arquivo e um formato de imagem.

```csharp
// Step 3: Save the 4‑column barcode image
barcode.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

Quando o arquivo for gravado, você pode abri‑lo com qualquer visualizador de imagens para confirmar que o padrão **databar expanded stacked** aparece corretamente.

### 5. Como definir linhas para DataBar

Linhas adicionam uma segunda dimensão ao layout empilhado, permitindo mais dados codificados sem ampliar a largura do código de barras. A propriedade `Rows` tem valor padrão 1; você pode aumentá‑la até 3 para a variante expanded stacked.

```csharp
// Step 4: Switch to a 3‑row layout (columns remain unchanged)
barcode.Parameters.Barcode.DataBar.Rows = 3;
```

**Por que as linhas importam:** Aumentar as linhas reduz a largura total enquanto preserva a capacidade de dados, o que é útil para etiquetas estreitas ou telas de dispositivos móveis.

### 6. Salve a imagem de código de barras com 3 linhas

```csharp
// Step 5: Save the 3‑row barcode image
barcode.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

Agora você tem dois arquivos PNG — um com layout de 4 colunas e outro com layout de 3 linhas — ambos usando a simbologia **databar expanded stacked**.

### 7. Exemplo completo em C# para gerar imagem de código de barras

Juntando todas as etapas, obtém‑se um programa autocontido que pode ser copiado para uma aplicação console:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for Databar Expanded Stacked
            BarcodeGenerator barcode = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Configure a 4‑column layout and save
            barcode.Parameters.Barcode.DataBar.Columns = 4;
            barcode.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("4‑column barcode saved.");

            // Change to a 3‑row layout (columns stay at 4) and save
            barcode.Parameters.Barcode.DataBar.Rows = 3;
            barcode.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("3‑row barcode saved.");
        }
    }
}
```

**Saída esperada**

Ao executar o programa, ele imprime:

```
4‑column barcode saved.
3‑row barcode saved.
```

e cria dois arquivos PNG em `YOUR_DIRECTORY`. Abra os arquivos para verificar se cada imagem exibe um código de barras **databar expanded stacked** válido.

## Armadilhas comuns e dicas práticas

* **Existência do diretório** – `Save` não cria pastas ausentes. Garanta que `YOUR_DIRECTORY` exista ou use `Directory.CreateDirectory` antes de salvar.
* **Limites de colunas** – Valores diferentes de 2, 3 ou 4 dispararam uma exceção. Proteja contra erros de entrada do usuário com uma simples verificação de intervalo:

  ```csharp
  int columns = 4;
  if (columns < 2 || columns > 4) throw new ArgumentOutOfRangeException(nameof(columns));
  barcode.Parameters.Barcode.DataBar.Columns = columns;
  ```

* **Limites de linhas** – A variante expanded stacked suporta até 3 linhas. Definir `Rows` como 0 ou um valor maior que 3 também gera uma exceção.
* **Formato de imagem** – `BarCodeImageFormat.Png` fornece qualidade sem perdas, ideal para impressão. Use `Jpeg` somente quando o tamanho do arquivo for a principal preocupação.

## Próximos passos

Agora que você sabe **como gerar imagens de código de barras** com configurações personalizadas de colunas e linhas, pode:

* Integrar o gerador a uma API web para servir imagens de código de barras sob demanda.  
* Combinar o código de barras com bibliotecas de geração de PDF para incorporá‑lo em notas fiscais.  
* Experimentar outras variantes DataBar (`DatabarExpanded`, `DatabarLimited`) usando o mesmo objeto `Parameters.Barcode.DataBar`.

Para personalizações mais avançadas — como alterar a cor das barras, adicionar texto legível por humanos ou aplicar sobreposições de QR‑code — consulte a documentação da Aspose.BarCode sobre as propriedades de `BarcodeGenerator`.

---

Seguindo este guia, você dominou o fluxo de trabalho **databar expanded stacked**, aprendeu **como definir colunas**, **como definir linhas** e produziu duas imagens de código de barras distintas prontas para uso em produção. Boa codificação!


## O que você deve aprender a seguir?


Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}