---
category: general
date: 2026-09-07
description: tutorial de gerador de código de barras em C# que mostra como gerar arquivos
  PNG de códigos de barras e criar códigos de barras DataBar com linhas e colunas
  personalizáveis
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- generate barcode PNG
- create DataBar barcode
language: pt
lastmod: 2026-09-07
og_description: 'tutorial de gerador de código de barras C#: aprenda a gerar arquivos
  PNG de códigos de barras e criar códigos DataBar com linhas e colunas personalizadas
  em apenas minutos'
og_image_alt: Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator
  C#
og_title: gerador de código de barras C# – crie códigos de barras DataBar e imagens
  PNG
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: barcode generator C# tutorial that shows you how to generate barcode
    PNG files and create DataBar barcodes with customizable rows and columns
  headline: How to use a barcode generator C# to create DataBar barcodes
  type: TechArticle
tags:
- barcode
- C#
- DataBar
title: Como usar um gerador de código de barras C# para criar códigos de barras DataBar
url: /pt/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como usar um gerador de código de barras C# para criar códigos DataBar

Se você precisa de um **barcode generator C#** para criar códigos de barras de alta qualidade, este guia mostra como **gerar arquivos PNG de código de barras** e **criar códigos DataBar** com linhas e colunas personalizadas. Seja para construir um sistema de inventário de varejo ou uma plataforma de bilhetagem, os passos abaixo permitem produzir um código DataBar Expanded Stacked em um único exemplo autocontido.

Neste tutorial você aprenderá:

* Como instanciar o `BarcodeGenerator` para a simbologia DataBar Expanded Stacked.  
* Como ajustar as configurações de colunas e linhas para atender às especificações ISO / GS1.  
* Como salvar a saída como uma imagem PNG que pode ser incorporada em páginas web ou impressa em etiquetas.  

Nenhum serviço externo é necessário — apenas a biblioteca Aspose.BarCode para .NET (ou qualquer biblioteca compatível que siga a mesma API). O código funciona em .NET 6+ e funciona no Visual Studio, Rider ou qualquer IDE que suporte C#.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6 SDK ou posterior instalado.  
* Uma referência ao pacote NuGet `Aspose.BarCode` (ou uma biblioteca equivalente que forneça `BarcodeGenerator`, `EncodeTypes` e `BarCodeImageFormat`).  
* Familiaridade básica com a sintaxe C# e a estrutura de projetos.  

Você pode adicionar o pacote via linha de comando:

```bash
dotnet add package Aspose.BarCode
```

## Etapa 1: Inicializar o gerador de código de barras C# para DataBar Expanded Stacked

O primeiro passo é criar uma instância de `BarcodeGenerator` que tenha como alvo a simbologia **DataBar Expanded Stacked**. Esse objeto contém todos os parâmetros de renderização, incluindo o texto a ser codificado.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,          // Symbology
    "Databar Expanded Stacked long");            // Data to encode
```

**Por que isso importa:** O valor do enum `EncodeTypes.DatabarExpandedStacked` informa à biblioteca qual padrão de código de barras aplicar. Usar o enum correto garante que a imagem gerada esteja em conformidade com as especificações GS1 DataBar.

## Etapa 2: Configurar o número de colunas (as linhas padrão são usadas)

DataBar Expanded Stacked pode ser dividido em várias colunas. Ajustar a contagem de colunas altera a densidade visual e pode ajudar a encaixar strings de dados mais longas em espaço limitado.

```csharp
// Step 2: Set the number of columns (default rows are used)
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

**Dica profissional:** O número padrão de colunas é 1. Definir 4 cria quatro colunas empilhadas, o que é ideal para strings numéricas mais longas enquanto mantém a altura do código de barras manejável.

## Etapa 3: Gerar PNG de código de barras com a configuração de coluna aplicada

Agora salve o código de barras como uma imagem PNG. PNG preserva as bordas nítidas necessárias para os scanners e funciona bem tanto na web quanto em mídia impressa.

```csharp
// Step 3: Save the barcode image with the column setting applied
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

O arquivo `DatabarCols4.png` contém um **barcode PNG** que você pode incorporar diretamente em HTML:

```html
<img src="DatabarCols4.png" alt="Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#">
```

## Etapa 4: Criar uma instância separada do gerador para configuração de linhas

Se precisar controlar o número de linhas em vez de colunas, instancie um novo `BarcodeGenerator`. Reutilizar a mesma instância após mudar uma dimensão pode gerar artefatos inesperados de layout, portanto, um objeto novo é a abordagem mais segura.

```csharp
// Step 4: Create a new generator instance for the same barcode type
BarcodeGenerator rowBarcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## Etapa 5: Definir o número de linhas (as colunas padrão são usadas)

Linhas afetam o empilhamento vertical dos módulos do código de barras. Aumentar o número de linhas pode tornar o código de barras mais alto, o que pode ser necessário para certos tamanhos de etiqueta.

```csharp
// Step 5: Set the number of rows (default columns are used)
rowBarcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

**Por que linhas vs. colunas:** Colunas dividem o código de barras horizontalmente, enquanto linhas o estendem verticalmente. Escolha a orientação que melhor se adapta ao layout da sua etiqueta.

## Etapa 6: Gerar PNG de código de barras com a configuração de linha aplicada

Por fim, salve o código de barras ajustado por linhas como um arquivo PNG.

```csharp
// Step 6: Save the barcode image with the row setting applied
rowBarcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

Agora você tem dois arquivos PNG distintos:

* `DatabarCols4.png` – 4 colunas, 1 linha.  
* `DatabarRows3.png` – 1 coluna, 3 linhas.

Ambas as imagens estão prontas para uso imediato em aplicativos, relatórios ou etiquetas impressas.

## Como gerar arquivos PNG de código de barras em C# com dimensões personalizadas

O padrão mostrado acima pode ser reutilizado para qualquer variante DataBar ou outras simbologias suportadas pela biblioteca. Aqui está um modelo compacto que você pode copiar‑colar em uma classe utilitária:

```csharp
public static void GenerateDatabar(string data, int columns = 1, int rows = 1, string outputPath = "output.png")
{
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, data);
    generator.Parameters.Barcode.DataBar.Columns = columns;
    generator.Parameters.Barcode.DataBar.Rows = rows;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Chame o método assim:

```csharp
GenerateDatabar("1234567890123", columns: 4, outputPath: "DatabarCols4.png");
GenerateDatabar("1234567890123", rows: 3, outputPath: "DatabarRows3.png");
```

**Casos de borda a considerar**

* **Comprimento dos dados** – DataBar Expanded Stacked pode codificar até 74 caracteres numéricos. Exceder esse limite lança uma exceção. Valide o comprimento da entrada antes de chamar o gerador.  
* **Dimensões inválidas** – A biblioteca restringe colunas a 1‑4 e linhas a 1‑3 para essa simbologia. Valores fora desses intervalos serão ignorados ou causarão erro.  
* **DPI da imagem** – Se precisar de resolução maior para impressão, defina `generator.Parameters.ImageResolution` antes de salvar.

## Saída esperada

Ao abrir `DatabarCols4.png` ou `DatabarRows3.png` você deverá ver um código DataBar nítido e de alto contraste. Escanear a imagem com um leitor compatível GS1 retorna o texto original `"Databar Expanded Stacked long"`.

![Exemplo de código DataBar Expanded Stacked salvo como PNG usando barcode generator C#](image.png)

*Texto alternativo: Exemplo de código DataBar Expanded Stacked salvo como PNG usando barcode generator C#*

## Conclusão

Este tutorial demonstrou como um **barcode generator C#** pode ser usado para **criar códigos DataBar** e **gerar arquivos PNG de código de barras** com configurações personalizadas de linhas e colunas. Seguindo as seis etapas — inicializar o gerador, configurar colunas ou linhas e salvar como PNG — você obtém imagens prontas para produção, adequadas para sistemas de inventário, bilhetagem ou qualquer cenário que exija renderização confiável de códigos de barras.

Em seguida, você pode explorar:

* Adicionar cor ou imagens de fundo ao PNG (ainda compatível com a maioria dos scanners).  
* Usar outras simbologias como QR, Code 128 ou PDF417 via a mesma API `BarcodeGenerator`.  
* Incorporar o PNG gerado diretamente em visualizações ASP.NET Core MVC ou componentes Blazor.

Sinta‑se à vontade para experimentar diferentes strings de dados, dimensões e formatos de imagem (por exemplo, JPEG, BMP). O mesmo padrão se aplica, tornando o **barcode generator C#** uma ferramenta versátil na caixa de ferramentas de qualquer desenvolvedor .NET. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Generate barcode C# – Create DataBar barcode](/barcode/english/python-java/general/generate-barcode-c-create-databar-barcode/)
- [Barcode Generator Example – Build DataBar Image in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}