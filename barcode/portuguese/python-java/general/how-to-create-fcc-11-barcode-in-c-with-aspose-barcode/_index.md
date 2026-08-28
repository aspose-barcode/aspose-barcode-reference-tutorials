---
category: general
date: 2026-08-22
description: Crie o código de barras FCC 11 em C# usando Aspose.BarCode. Aprenda o
  código passo a passo, configure as dimensões e gere imagens PNG para o Australia
  Post.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create fcc 11 barcode
- Australia Post barcode
- Aspose.BarCode C#
- FCC 59 barcode
- FCC 62 barcode
- N‑Table encoding
- C‑Table encoding
language: pt
lastmod: 2026-08-22
og_description: Crie o código de barras FCC 11 em C# com Aspose.BarCode. Siga este
  tutorial conciso para gerar códigos de barras PNG para o Australia Post, incluindo
  as variantes FCC 59 e FCC 62.
og_image_alt: Screenshot showing a generated FCC 11 barcode image
og_title: Criar código de barras FCC 11 em C# – guia completo do Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  headline: How to create FCC 11 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  name: How to create FCC 11 barcode in C# with Aspose.BarCode
  steps:
  - name: 4.1 FCC 59 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)'
  - name: 4.2 FCC 62 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)'
  - name: 4.3 FCC 62 with C‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix'
  - name: 4.4 FCC 62 with Other encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567321032103210"); // Long payload for "Other" table'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- AustraliaPost
title: Como criar código de barras FCC 11 em C# com Aspose.BarCode
url: /pt/python-java/general/how-to-create-fcc-11-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar código de barras FCC 11 em C# com Aspose.BarCode

Se você precisa **criar código de barras FCC 11** em uma aplicação .NET, este guia mostra o código exato necessário. Você verá como configurar as dimensões do código de barras, escolher a tabela de codificação correta e salvar o resultado como um arquivo PNG.

Gerar códigos de barras da Australia Post é uma necessidade comum para logística, sistemas de correspondência e rastreamento de inventário. Este tutorial cobre o formato FCC 11 e também demonstra como produzir códigos de barras FCC 59 e FCC 62 com diferentes tabelas de codificação, para que você possa reutilizar o mesmo padrão para outros serviços postais.

## O que você precisará

* .NET 6.0 SDK ou posterior instalado  
* Visual Studio 2022 (ou qualquer IDE compatível com C#)  
* Uma licença válida para **Aspose.BarCode for .NET** – a edição comunitária funciona para avaliação  
* Permissão de gravação em uma pasta onde os arquivos PNG serão salvos  

Esses pré-requisitos garantem que o código compile e execute sem configuração adicional.

## Etapa 1: Instalar o pacote NuGet Aspose.BarCode

Abra um terminal na pasta do projeto e execute:

```bash
dotnet add package Aspose.BarCode
```

O comando adiciona a versão estável mais recente da biblioteca ao seu arquivo de projeto. O pacote contém a classe `BarcodeGenerator` usada ao longo deste tutorial.

## Etapa 2: Definir a pasta de saída

Crie uma pasta onde as imagens geradas serão armazenadas. O caminho pode ser absoluto ou relativo ao executável.

```csharp
// Step 2: Define the output folder
string outputPath = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputPath);
```

`Directory.CreateDirectory` garante que a pasta exista, evitando erros em tempo de execução quando o método `Save` grava o arquivo.

## Etapa 3: Gerar o código de barras FCC 11

O formato FCC 11 é a codificação padrão para os códigos de barras postais da Australia Post. O código a seguir cria um código de barras que codifica a sequência numérica `1101234567`.

```csharp
// Step 3: Create a BarcodeGenerator for FCC 11
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,      // Use the Australia Post symbology
    "1101234567");                  // Data for FCC 11

// Configure visual appearance
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;   // Width of a single module
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50; // Height of the barcode

// Save as PNG
string fcc11Path = Path.Combine(outputPath, "PostalAustraliaPostFCC11.png");
barcodeGenerator.Save(fcc11Path, BarCodeImageFormat.Png);
```

**Por que isso funciona:**  
* `EncodeTypes.AustraliaPost` informa à biblioteca para aplicar as regras de codificação da Australia Post.  
* A sequência de dados `1101234567` segue a especificação FCC 11: os dois primeiros dígitos (`11`) identificam o formato, seguidos por uma referência de cliente de 7 dígitos.  
* `XDimension` e `BarHeight` controlam o tamanho do código de barras impresso, o que é importante para a legibilidade pelo scanner.  

Após executar o programa, você encontrará `PostalAustraliaPostFCC11.png` na pasta `Barcodes`. A imagem se parece com isto:

![exemplo de criação de código de barras FCC 11](https://example.com/fcc11.png "Código de barras FCC 11 gerado pelo Aspose.BarCode")

## Etapa 4: Criar códigos de barras adicionais da Australia Post (opcional)

Embora o objetivo principal seja **criar código de barras FCC 11**, muitas vezes você precisa de códigos de barras FCC 59 ou FCC 62 para diferentes classes de correspondência. O código abaixo reutiliza a mesma instância `BarcodeGenerator`, alterando apenas a sequência de dados e a tabela de codificação opcional.

### 4.1 FCC 59 com codificação N‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;

// Use N‑Table for customer information interpretation
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc59Path = Path.Combine(outputPath, "PostalAustraliaPostFCC59NTable.png");
barcodeGenerator.Save(fcc59Path, BarCodeImageFormat.Png);
```

### 4.2 FCC 62 com codificação N‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc62NPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62NTable.png");
barcodeGenerator.Save(fcc62NPath, BarCodeImageFormat.Png);
```

### 4.3 FCC 62 com codificação C‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.CTable;

string fcc62CPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62CTable.png");
barcodeGenerator.Save(fcc62CPath, BarCodeImageFormat.Png);
```

### 4.4 FCC 62 com codificação Other

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567321032103210"); // Long payload for "Other" table

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.Other;

string fcc62OtherPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62OtherTable.png");
barcodeGenerator.Save(fcc62OtherPath, BarCodeImageFormat.Png);
```

Todas as quatro imagens são salvas lado a lado na mesma pasta, facilitando a comparação das diferenças visuais.

## Etapa 5: Entender as tabelas de codificação

A Australia Post define três tabelas de codificação:

* **N‑Table** – interpreta informações numéricas do cliente. Use-a quando a carga útil contém apenas dígitos.  
* **C‑Table** – suporta caracteres alfanuméricos, útil para números de referência que incluem letras.  
* **Other** – uma alternativa para formatos de dados personalizados ou estendidos.  

Escolher a tabela correta garante que o scanner de código de barras decodifique a informação exatamente como pretendido. Se você omitir a propriedade `AustralianPostEncodingTable`, a biblioteca usará a N‑Table por padrão, o que pode truncar caracteres não numéricos.

## Dicas, casos extremos e armadilhas comuns

| Situação | Abordagem recomendada |
|-----------|----------------------|
| Comprimento da string de dados é menor que o necessário | Preencha a parte numérica com zeros à esquerda para atender à especificação FCC. |
| Código de barras aparece borrado quando impresso | Aumente `XDimension` para 5 ou 6 pixels e verifique as configurações de DPI da impressora. |
| Scanner retorna “formato inválido” | Verifique se a tabela de codificação correta (N‑Table, C‑Table, Other) corresponde à carga de dados. |
| Executando no Linux sem interface gráfica | Certifique‑se de que o pacote `System.Drawing.Common` está referenciado, ou use o método `Save` com `BarCodeImageFormat.Png`, que não requer contexto de exibição. |
| Necessita de um formato de imagem diferente | Substitua `BarCodeImageFormat.Png` por `BarCodeImageFormat.Jpeg` ou `BarCodeImageFormat.Tiff`, conforme necessário. |

Essas dicas práticas provêm de implantações reais de soluções de códigos de barras postais.

## Exemplo completo executável

Abaixo está um programa autônomo que você pode copiar para um novo projeto de console (`dotnet new console`) e executar sem modificações.



## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar código de barras java – Código de barras Australia Post com Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)
- [Criar codificação One-Dimensional Databar GS1 com Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Como criar zona silenciosa de código de barras .NET para Code 16K usando Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}