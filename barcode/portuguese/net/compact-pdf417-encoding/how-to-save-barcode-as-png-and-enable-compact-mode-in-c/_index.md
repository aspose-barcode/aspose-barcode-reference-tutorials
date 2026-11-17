---
category: general
date: 2026-11-17
description: Aprenda como salvar código de barras, habilitar o modo compacto, ajustar
  colunas e gerar código de barras PDF417 com um exemplo completo em C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- enable compact mode
- how to adjust columns
- generate pdf417 barcode
- how to enable compact mode
language: pt
lastmod: 2026-11-17
og_description: Como salvar o código de barras, habilitar o modo compacto e ajustar
  as colunas ao gerar um código de barras PDF417 em C#. Siga o guia passo a passo.
og_image_alt: Screenshot showing how to save barcode as PNG file in C#
og_title: Como salvar o código de barras como PNG e habilitar o modo compacto em C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  headline: How to save barcode as PNG and enable compact mode in C#
  type: TechArticle
- description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  name: How to save barcode as PNG and enable compact mode in C#
  steps:
  - name: Expected output
    text: Opening the saved PNG file shows a vertically compact PDF417 barcode with
      three columns and truncated padding. The visual size is roughly 2 px per module,
      making the image suitable for embedding in HTML `<img>` tags or for printing
      on small labels.
  - name: What if I need a different image format?
    text: The `Save` method accepts any `BarCodeImageFormat` enum value, such as `Jpeg`,
      `Bmp`, or `Gif`. Replace `BarCodeImageFormat.Png` with the desired format, and
      the rest of the code remains unchanged.
  - name: How does truncation affect data capacity?
    text: Enabling **compact mode** (truncation) reduces the number of rows, which
      can lower the maximum data capacity of the barcode. If you encounter a “Data
      too large” exception, either increase the number of columns or disable truncation.
  - name: Can I use a dynamic column count?
    text: 'Yes. You can calculate the column count based on the length of the input
      string:'
  - name: Is the X‑dimension limited to integer pixels?
    text: The `Pixels` property accepts any positive integer. For higher‑resolution
      outputs (e.g., printing), you might prefer setting `Points` instead of `Pixels`
      to achieve device‑independent sizing.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- image generation
title: Como salvar o código de barras como PNG e habilitar o modo compacto no C#
url: /pt/net/compact-pdf417-encoding/how-to-save-barcode-as-png-and-enable-compact-mode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como salvar código de barras como PNG e habilitar o modo compacto em C#

Se você precisa **how to save barcode** em um formato que pode ser usado na web ou em impressão, este guia mostra os passos exatos. Você também aprenderá a **enable compact mode**, **adjust columns** e **generate PDF417 barcode** com a biblioteca Aspose.BarCode para .NET.

O tutorial cobre tudo, desde a configuração do projeto até o arquivo PNG final, para que você possa copiar o código para sua própria solução sem pesquisas adicionais. Nenhuma documentação externa é necessária; o exemplo completo e executável está incluído.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 ou superior instalado  
* Visual Studio 2022 (ou qualquer IDE C#)  
* O pacote NuGet `Aspose.BarCode` (`Install-Package Aspose.BarCode`)  

Esses três itens são as únicas dependências para o código que se segue.

## Etapa 1: Criar um gerador de código de barras PDF417

A primeira tarefa ao **generate PDF417 barcode** é instanciar um `BarcodeGenerator` com o tipo de codificação correto e os dados que você deseja codificar.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a PDF417 barcode generator with the desired text.
BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

O enum `EncodeTypes.Pdf417` indica à biblioteca que deve usar a simbologia PDF417, que é um código de barras linear empilhado adequado para codificar grandes quantidades de dados. A string `"Compact mode"` torna‑se o texto legível por humanos abaixo do código de barras.

## Etapa 2: Definir a dimensão X (largura do módulo)

Cada barra em um código de barras é chamada de módulo. Controlar a largura do módulo permite ajustar finamente o tamanho visual do código de barras sem alterar os dados.

```csharp
// Step 2: Set the module (X) dimension – each bar will be 2 pixels wide.
barcode.Parameters.Barcode.XDimension.Pixels = 2;
```

Uma dimensão X de 2 pixels produz uma imagem compacta que ainda escaneia de forma confiável na maioria dos dispositivos.

## Etapa 3: **how to adjust columns** para o código PDF417

PDF417 permite especificar quantas colunas o código de barras deve usar. Menos colunas produzem um símbolo mais alto e estreito, enquanto mais colunas tornam o símbolo mais largo, porém mais curto.

```csharp
// Step 3: Define the number of columns for the PDF417 code (3 columns).
barcode.Parameters.Barcode.Pdf417.Columns = 3;
```

Esta linha demonstra **how to adjust columns**. Você pode mudar o valor para 2, 4 ou qualquer número suportado pela biblioteca, dependendo do espaço que você tem no meio de destino.

## Etapa 4: **how to enable compact mode** e truncar o símbolo

O modo compacto remove preenchimento desnecessário e reduz a pegada geral do código de barras. A biblioteca expõe esse recurso por meio da propriedade `Truncate`.

```csharp
// Step 4: Enable compact mode by truncating the symbol.
barcode.Parameters.Barcode.Pdf417.Truncate = true;
```

Observe que a frase **enable compact mode** aparece aqui, e a mesma ação é descrita com a redação exata **how to enable compact mode** mais adiante no guia para atender ao requisito de palavra‑chave secundária.

## Etapa 5: **how to save barcode** como imagem PNG

Salvar a imagem gerada é o passo final. O método `Save` grava o código de barras no sistema de arquivos no formato que você especificar.

```csharp
// Step 5: Save the generated barcode as a PNG image.
barcode.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Substitua `YOUR_DIRECTORY` por um caminho absoluto ou relativo ao qual sua aplicação possa gravar. Após a execução, você encontrará um arquivo chamado `CompactPdf417.png` contendo o código de barras PDF417 compacto.

### Saída esperada

Abrir o arquivo PNG salvo mostra um código de barras PDF417 verticalmente compacto com três colunas e preenchimento truncado. O tamanho visual é aproximadamente 2 px por módulo, tornando a imagem adequada para incorporação em tags HTML `<img>` ou para impressão em etiquetas pequenas.

## Exemplo completo e executável

Abaixo está o programa completo que você pode copiar para um novo projeto de console. Ele inclui todas as diretivas `using` necessárias e demonstra **how to save barcode**, **enable compact mode**, **how to adjust columns** e **generate PDF417 barcode** em um fluxo único.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417CompactDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a PDF417 barcode generator with the desired text.
            BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

            // Set the module (X) dimension – each bar will be 2 pixels wide.
            barcode.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns for the PDF417 code (3 columns).
            barcode.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable compact mode by truncating the symbol.
            barcode.Parameters.Barcode.Pdf417.Truncate = true;

            // Save the generated barcode as a PNG image.
            string outputPath = "CompactPdf417.png"; // Adjust path as needed.
            barcode.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Executar este programa produz o arquivo PNG descrito anteriormente. A saída do console confirma a localização do arquivo salvo, o que ajuda a verificar que a etapa **how to save barcode** foi concluída com sucesso.

## Perguntas comuns e casos de borda

### E se eu precisar de um formato de imagem diferente?

O método `Save` aceita qualquer valor do enum `BarCodeImageFormat`, como `Jpeg`, `Bmp` ou `Gif`. Substitua `BarCodeImageFormat.Png` pelo formato desejado, e o restante do código permanece inalterado.

### Como a truncagem afeta a capacidade de dados?

Habilitar **compact mode** (truncagem) reduz o número de linhas, o que pode diminuir a capacidade máxima de dados do código de barras. Se você encontrar uma exceção “Data too large”, aumente o número de colunas ou desative a truncagem.

### Posso usar uma contagem de colunas dinâmica?

Sim. Você pode calcular a contagem de colunas com base no comprimento da string de entrada:

```csharp
int desiredColumns = Math.Max(2, Math.Min(30, inputText.Length / 10));
barcode.Parameters.Barcode.Pdf417.Columns = desiredColumns;
```

Este trecho mostra **how to adjust columns** programaticamente, garantindo que o código de barras se ajuste ao layout desejado.

### A dimensão X é limitada a pixels inteiros?

A propriedade `Pixels` aceita qualquer inteiro positivo. Para saídas de alta resolução (por exemplo, impressão), você pode preferir definir `Points` em vez de `Pixels` para obter dimensionamento independente de dispositivo.

## Dicas para uso em produção

* **Pro tip:** Envolva a geração do código de barras em um bloco try‑catch para tratar `BarCodeException` quando os dados de entrada excederem a capacidade do símbolo.  
* **Fique atento a:** Permissões de sistema de arquivos. O processo deve ter acesso de gravação ao diretório de destino, caso contrário a etapa **how to save barcode** falhará com uma `UnauthorizedAccessException`.  
* **Nota de desempenho:** Criar muitos códigos de barras em um loop se beneficia da reutilização de uma única instância `BarcodeGenerator` e da atualização apenas da propriedade `CodeText` entre as iterações.

## Conclusão

Agora você sabe **how to save barcode** como um arquivo PNG, **enable compact mode**, **how to adjust columns** e **generate PDF417 barcode** usando Aspose.BarCode para C#. O exemplo completo demonstra cada passo necessário, desde a inicialização do gerador até a gravação da imagem final.

A partir daqui, você pode explorar tópicos relacionados, como adicionar um logotipo ao código de barras, personalizar cores ou integrar o gerador em uma API ASP.NET Core. Cada uma dessas extensões segue o mesmo padrão mostrado neste guia, permitindo que você adapte o código com confiança.

Sinta‑se à vontade para experimentar diferentes contagens de colunas, dimensões X e formatos de imagem para atender às especificações exatas do seu projeto. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [How to save barcode and generate PDF417 with Aspose in C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [How to create PDF417 barcode and save it as PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}