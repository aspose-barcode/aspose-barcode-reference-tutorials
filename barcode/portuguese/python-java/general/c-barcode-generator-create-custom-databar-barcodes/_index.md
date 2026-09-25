---
category: general
date: 2026-08-19
description: O tutorial do gerador de códigos de barras em C# mostra como gerar códigos
  de barras DataBar Expanded Stacked, personalizar o tamanho do código de barras e
  configurar linhas e colunas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- create databar barcode
- customize barcode size
- configure databar parameters
language: pt
lastmod: 2026-08-19
og_description: O tutorial de gerador de código de barras em C# ensina como gerar
  códigos de barras DataBar, personalizar o tamanho e configurar linhas e colunas
  para uma saída precisa.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: Gerador de códigos de barras em C# – guia passo a passo para códigos DataBar
  personalizados
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: C# barcode generator tutorial shows how to generate DataBar Expanded
    Stacked barcodes, customize barcode size, and configure rows and columns.
  headline: 'C# barcode generator: create custom DataBar barcodes'
  type: TechArticle
- description: C# barcode generator tutorial shows how to generate DataBar Expanded
    Stacked barcodes, customize barcode size, and configure rows and columns.
  name: 'C# barcode generator: create custom DataBar barcodes'
  steps:
  - name: Initialise the barcode generator with sample text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the number of columns (default rows are used)
    text: '```csharp // Configure the DataBar to use four columns. barcodeGenerator.Parameters.Barcode.DataBar.Columns
      = 4; ```'
  - name: Save the barcode image that uses four columns
    text: '```csharp // Save the barcode as a PNG file. barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png",
      BarCodeImageFormat.Png); ```'
  - name: Re‑initialise the generator for a new configuration
    text: '```csharp // Create a new generator instance for the same symbology and
      text. barcodeGenerator = new BarcodeGenerator( EncodeTypes.DatabarExpandedStacked,
      "Databar Expanded Stacked long"); ```'
  - name: Set the number of rows (default columns are used)
    text: '```csharp // Configure the DataBar to use three rows. barcodeGenerator.Parameters.Barcode.DataBar.Rows
      = 3; ```'
  - name: Save the barcode image that uses three rows
    text: '```csharp // Save the barcode with three rows. barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  type: HowTo
tags:
- barcode
- csharp
- databar
title: 'Gerador de código de barras C#: crie códigos DataBar personalizados'
url: /pt/python-java/general/c-barcode-generator-create-custom-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerador de código de barras C#: crie códigos DataBar personalizados

Se você precisa de um **c# barcode generator** que possa produzir símbolos DataBar Expanded Stacked, este guia mostra exatamente como gerar imagens de código de barras com linhas e colunas personalizadas. Você aprenderá a configurar parâmetros databar, ajustar o tamanho do código de barras e salvar o resultado como arquivos PNG.

Gerar códigos de barras programaticamente elimina etapas de design manual e garante saída consistente em todas as plataformas. Neste tutorial você irá:

* Instalar e referenciar a biblioteca Aspose.BarCode para .NET (ou qualquer pacote compatível).
* Criar um gerador de código de barras para a simbologia DataBar Expanded Stacked.
* **Como gerar imagens de código de barras** com configurações específicas de coluna e linha.
* **Personalizar o tamanho do código de barras** controlando linhas e colunas do DataBar.
* **Configurar parâmetros databar** como texto, formato e qualidade da imagem.

## Pré-requisitos

* .NET 6.0 SDK ou posterior instalado.
* Um ambiente de desenvolvimento C# (Visual Studio, VS Code, Rider, etc.).
* Pacote NuGet `Aspose.BarCode` (ou uma biblioteca equivalente que forneça `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat`).

Adicione o pacote usando a CLI do .NET:

```bash
dotnet add package Aspose.BarCode
```

## Usando o gerador de código de barras C# para criar códigos DataBar

As próximas seções guiam você passo a passo. O foco principal está na API **c# barcode generator**, mas o mesmo padrão se aplica a outras bibliotecas de código de barras que exponham propriedades semelhantes.

### Etapa 1: Inicializar o gerador de código de barras com texto de exemplo

```csharp
using Aspose.BarCode.Generation;

// Create a generator for DataBar Expanded Stacked with sample text.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*Por que esta etapa?*  
`BarcodeGenerator` é o ponto de entrada para todas as tarefas de criação de códigos de barras. Fornecer o enum `EncodeTypes.DatabarExpandedStacked` informa à biblioteca qual simbologia usar, enquanto o argumento de texto se torna o valor legível codificado no símbolo.

### Etapa 2: Definir o número de colunas (linhas padrão são usadas)

```csharp
// Configure the DataBar to use four columns.
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

*Por que esta etapa?*  
Os símbolos DataBar Expanded Stacked consistem em elementos lineares empilhados. Ajustar a propriedade `Columns` altera a densidade horizontal, permitindo que você encaixe cadeias de dados mais longas sem aumentar a altura geral. Isso personaliza diretamente **o tamanho do código de barras**.

### Etapa 3: Salvar a imagem do código de barras que usa quatro colunas

```csharp
// Save the barcode as a PNG file.
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

*O que você vê:*  
A imagem salva `DatabarCols4.png` exibe um código de barras DataBar mais largo que o padrão porque contém quatro colunas. Você pode abrir o arquivo em qualquer visualizador de imagens para verificar o resultado.

### Etapa 4: Re‑inicializar o gerador para uma nova configuração

```csharp
// Create a new generator instance for the same symbology and text.
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*Por que re‑inicializar?*  
Mudar a propriedade `Rows` mantendo a configuração de coluna anterior pode gerar uma combinação inesperada. Começar com uma nova instância garante que apenas o parâmetro pretendido (`Rows`) influencie a próxima imagem.

### Etapa 5: Definir o número de linhas (colunas padrão são usadas)

```csharp
// Configure the DataBar to use three rows.
barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

*Por que esta etapa?*  
A propriedade `Rows` controla o empilhamento vertical. Aumentar as linhas torna o código de barras mais alto, o que pode ser útil quando o espaço horizontal é limitado, mas há abundância vertical. Esta é outra forma de **personalizar o tamanho do código de barras**.

### Etapa 6: Salvar a imagem do código de barras que usa três linhas

```csharp
// Save the barcode with three rows.
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

*Resultado:*  
`DatabarRows3.png` mostra um código de barras mais alto com três linhas empilhadas, demonstrando como **configurar parâmetros databar** impacta a aparência visual.

## Exemplo completo executável

Abaixo está um programa completo que você pode copiar, colar e executar. Ele inclui todas as importações, tratamento de erros e comentários para clareza.

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder (adjust as needed).
        string outputFolder = @"C:\Barcodes";

        // -----------------------------------------------------------------
        // Create barcode with custom column count.
        // -----------------------------------------------------------------
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 4 columns – this widens the symbol.
        generator.Parameters.Barcode.DataBar.Columns = 4;

        // Save the first image.
        string colsPath = System.IO.Path.Combine(outputFolder, "DatabarCols4.png");
        generator.Save(colsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with 4 columns to: {colsPath}");

        // -----------------------------------------------------------------
        // Create barcode with custom row count.
        // -----------------------------------------------------------------
        generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 3 rows – this makes the symbol taller.
        generator.Parameters.Barcode.DataBar.Rows = 3;

        // Save the second image.
        string rowsPath = System.IO.Path.Combine(outputFolder, "DatabarRows3.png");
        generator.Save(rowsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with 3 rows to: {rowsPath}");
    }
}
```

**Saída esperada**

Executar o programa gera dois arquivos PNG:

* `DatabarCols4.png` – um código de barras DataBar largo com quatro colunas.
* `DatabarRows3.png` – um código de barras DataBar alto com três linhas.

Abra as imagens para confirmar que as dimensões do código de barras correspondem aos parâmetros configurados.

## Perguntas comuns e tratamento de casos extremos

| Question | Answer |
|----------|--------|
| *E se eu precisar de linhas personalizadas **e** colunas?* | Defina `Rows` **e** `Columns` na mesma instância de `BarcodeGenerator` antes de chamar `Save`. A biblioteca combina ambos os valores para produzir uma grade do tamanho solicitado. |
| *Posso mudar o formato da imagem?* | Sim. Substitua `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` ou `Gif` conforme seu fluxo de trabalho. |
| *O que acontece quando o texto é maior que o símbolo pode suportar?* | O gerador lança uma `ArgumentException`. Reduza o texto ou aumente `Columns`/`Rows` para fornecer mais capacidade. |
| *Existe uma maneira de definir DPI ou resolução da imagem?* | Use `generator.Parameters.ImageResolution` para especificar o DPI desejado antes de salvar. Isso personaliza ainda mais o **tamanho do código de barras** para impressão em alta resolução. |
| *A biblioteca suporta outras variantes do DataBar?* | Sim. Substitua `EncodeTypes.DatabarExpandedStacked` por `DatabarExpanded`, `DatabarLimited`, etc., mantendo a mesma estrutura de parâmetros. |

## Dicas para geração confiável de códigos de barras

* **Dica profissional:** Sempre verifique a imagem gerada com um scanner ou aplicativo móvel antes de implantá‑la em produção.  
* **Atenção:** Diretórios de saída nulos ou vazios—`Save` lançará uma exceção se o caminho não existir. Crie a pasta programaticamente se necessário.  
* **Nota de desempenho:** Reutilizar uma única instância de `BarcodeGenerator` e mudar apenas `Rows` ou `Columns` pode reduzir a sobrecarga de criação de objetos ao gerar muitos códigos de barras em um loop.

## Conclusão

Agora você sabe como usar um **c# barcode generator** para **criar imagens de código de barras databar**, **personalizar o tamanho do código de barras** e **configurar parâmetros databar** como linhas e colunas. Ajustando essas configurações, você pode encaixar códigos de barras em qualquer requisito de layout mantendo a confiabilidade da leitura.

Em seguida, explore tópicos relacionados como **como gerar PDFs de código de barras**, incorporar códigos de barras em relatórios ou mudar para outras simbologias (QR, Code‑128, etc.). Experimente diferentes `Rows`, `Columns` e resoluções de imagem para encontrar a configuração ideal para seu caso de uso específico.

---


## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar e ajustar a altura do código de barras para Databar unidimensional usando Aspose.BarCode para .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Gerar códigos de barras Databar 2D unidimensionais usando a API Aspose.BarCode .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [Gerar código de barras Aspose.BarCode Databar usando a API .NET – Configuração de linhas e colunas](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}