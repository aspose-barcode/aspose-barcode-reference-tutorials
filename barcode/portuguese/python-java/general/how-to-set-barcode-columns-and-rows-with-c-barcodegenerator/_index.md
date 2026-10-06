---
category: general
date: 2026-09-16
description: Aprenda como definir colunas de código de barras em C# usando BarcodeGenerator
  e também definir linhas de código de barras para códigos DataBar Expanded Stacked.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- set barcode columns
- set barcode rows
- DataBar Expanded Stacked
- BarcodeGenerator C#
- barcode image format
- configure barcode dimensions
language: pt
lastmod: 2026-09-16
og_description: Defina colunas de código de barras em C# rapidamente. Este guia mostra
  como configurar colunas, linhas e formato de imagem com o BarcodeGenerator.
og_image_alt: DataBar Expanded Stacked barcode showing custom columns and rows
og_title: Defina colunas e linhas de código de barras em C# – guia completo do BarcodeGenerator
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set barcode columns in C# using BarcodeGenerator and also
    set barcode rows for DataBar Expanded Stacked barcodes.
  headline: How to set barcode columns and rows with C# BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Como definir colunas e linhas de código de barras com C# BarcodeGenerator
url: /pt/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como definir colunas e linhas de código de barras com C# BarcodeGenerator

Se você precisar definir colunas de código de barras em uma aplicação C#, este tutorial mostra os passos exatos necessários. Você verá como configurar tanto colunas quanto linhas para um código de barras DataBar Expanded Stacked e, em seguida, salvar o resultado como uma imagem PNG.

Gerar códigos de barras programaticamente evita o trabalho manual de design e garante consistência em relatórios, faturas e etiquetas de produtos. O exemplo abaixo cobre todo o fluxo de trabalho, desde a instalação da biblioteca até a produção de duas imagens — uma com contagem de colunas personalizada e outra com contagem de linhas personalizada.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 ou posterior instalado.
* Uma referência ao pacote **Aspose.BarCode for .NET** via NuGet. Instale‑o com:

```bash
dotnet add package Aspose.BarCode
```

* Permissão de gravação em uma pasta onde os arquivos PNG gerados serão salvos.

Esses requisitos garantem que o código compile e execute sem configuração adicional.

## Como definir colunas de código de barras em C#

A primeira etapa importante é criar uma instância de `BarcodeGenerator` para a simbologia **DataBar Expanded Stacked** e atribuir a contagem de colunas desejada.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize a DataBar Expanded Stacked barcode generator with the target text.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the number of columns. The DataBar object exposes a Columns property.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image using the PNG format.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**Por que isso funciona:**  
`EncodeTypes.DatabarExpandedStacked` indica à biblioteca qual simbologia renderizar. Definir `Parameters.Barcode.DataBar.Columns` altera o layout interno dos módulos, influenciando diretamente a largura visual do código de barras. O método `Save` grava a imagem no disco no `BarCodeImageFormat` solicitado.

### Resultado esperado
Abra `C:\Barcodes\DatabarCols4.png` em qualquer visualizador de imagens. Você deverá ver um código de barras DataBar Expanded Stacked mais largo que o padrão, pois utiliza quatro colunas.

## Como definir linhas de código de barras em C#

Depois de salvar a imagem baseada em colunas, você pode querer um código de barras que varie em altura ajustando as linhas. O processo espelha a configuração de colunas, mas usa a propriedade `Rows`.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 4️⃣ Re‑initialize the generator for a fresh configuration.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 5️⃣ Set the number of rows. This property controls the vertical module count.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6️⃣ Save the barcode image with the row configuration.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Por que isso funciona:**  
Reinicializar o gerador garante que a configuração de coluna anterior não interfira na configuração de linhas. Alterar `Parameters.Barcode.DataBar.Rows` modifica a altura do código de barras, produzindo uma imagem mais alta quando a contagem de linhas excede o padrão.

### Resultado esperado
Abra `C:\Barcodes\DatabarRows3.png`. O código de barras aparecerá mais alto, refletindo a configuração de três linhas.

## Exemplo completo de ponta a ponta

Abaixo está um único programa que cria ambas as imagens em uma única execução. Manter o código em um arquivo demonstra como alternar entre configurações de coluna e linha sem reiniciar a aplicação.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Common text for both barcodes.
        const string barcodeText = "Databar Expanded Stacked long";

        // ---------- Column configuration ----------
        var colGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        colGenerator.Parameters.Barcode.DataBar.Columns = 4;
        colGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Row configuration ----------
        var rowGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;
        rowGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

Executar o programa gera dois arquivos PNG:

* **DatabarCols4.png** – código de barras com quatro colunas.  
* **DatabarRows3.png** – código de barras com três linhas.

Ambos os arquivos usam o **formato de imagem de código de barras** PNG, que preserva bordas nítidas e suporta compressão sem perdas — ideal para impressão e exibição digital.

## Perguntas frequentes e dicas

| Pergunta | Resposta |
|----------|----------|
| *Posso usar JPEG em vez de PNG?* | Sim. Substitua `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg`. JPEG é menor, mas introduz artefatos de compressão, o que pode afetar a confiabilidade do scanner. |
| *Qual é o número máximo de colunas ou linhas?* | A biblioteca valida os valores contra a especificação do DataBar. Valores fora do intervalo permitido lançam uma `ArgumentException`. Consulte a documentação do Aspose.BarCode para os limites exatos. |
| *Preciso descartar o `BarcodeGenerator`?* | A classe implementa `IDisposable`. Envolva o gerador em um bloco `using` se você criar muitas instâncias em um loop para liberar recursos não gerenciados rapidamente. |
| *Como mudar o tamanho do código de barras sem alterar colunas/linhas?* | Use `barcodeGenerator.Parameters.Image.Width` e `Height` para escalar a imagem de saída mantendo o layout dos módulos inalterado. |

**Dica profissional:** Ao gerar códigos de barras para impressão em alta resolução, aumente as dimensões da imagem de saída (`Width`/`Height`) em vez de aumentar a contagem de colunas ou linhas. Essa abordagem mantém o tamanho padrão dos módulos definido pela simbologia, proporcionando uma imagem mais nítida.

## Conclusão

Agora você sabe como definir colunas e linhas de código de barras em C# usando a classe **BarcodeGenerator**. O guia abordou a inicialização do gerador, a configuração de contagens de colunas e linhas, a gravação do código de barras em formato PNG e o tratamento de variações comuns, como mudanças de formato de imagem e liberação de recursos.

Em seguida, explore tópicos relacionados como **personalização de cores de código de barras**, **adição de texto legível por humanos** e **incorporação de códigos de barras em documentos PDF**. Todas essas extensões se baseiam no mesmo padrão de configuração demonstrado aqui, permitindo que você crie soluções de código de barras totalmente funcionais para qualquer aplicação .NET.

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que expandem as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [databar expanded stacked barcode guide – how to generate and size it in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}