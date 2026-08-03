---
category: general
date: 2026-08-03
description: Tutorial de gerador de código de barras em C# mostra como gerar imagem
  de código de barras com Aspose.BarCode, definir colunas e linhas e salvar arquivos
  PNG para DataBar Expanded Stacked.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
language: pt
lastmod: 2026-08-03
og_description: Tutorial de geração de código de barras C# explica como gerar imagem
  de código de barras usando Aspose.BarCode, configurar colunas e linhas DataBar Expanded
  Stacked e salvar arquivos PNG.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: Gerador de código de barras C# – guia passo a passo para gerar imagem de
  código de barras
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial shows how to generate barcode image with
    Aspose.BarCode, set columns and rows, and save PNG files for DataBar Expanded
    Stacked.
  headline: Barcode generator C# – generate barcode image
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Gerador de código de barras C# – gerar imagem de código de barras
url: /pt/python-java/general/barcode-generator-c-generate-barcode-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerador de código de barras C# – gerar imagem de código de barras

Se você precisa de um gerador de código de barras C# que possa gerar imagem de código de barras para DataBar Expanded Stacked, este guia o conduzirá através do processo completo. Você aprenderá como configurar as definições de colunas e linhas, salvar o resultado como PNG e adaptar o código para outras simbologias.

Gerar imagens de código de barras programaticamente elimina etapas manuais e garante consistência em faturas, etiquetas de envio e sistemas de inventário. Este tutorial cobre tudo o que você precisa, desde a configuração do projeto até o código-fonte completo, para que você possa executar o exemplo imediatamente.

## Pré-requisitos

* .NET 6.0 ou posterior instalado  
* Uma IDE como Visual Studio 2022 (qualquer editor que suporte C# funciona)  
* Uma licença para **Aspose.BarCode for .NET** – a avaliação gratuita funciona para testes  
* Familiaridade básica com a sintaxe C#  

Se algum desses itens estiver faltando, instale o .NET SDK em dotnet.microsoft.com e obtenha o pacote NuGet Aspose.BarCode com:

```bash
dotnet add package Aspose.BarCode
```

## Etapa 1: Criar um projeto de gerador de código de barras C#

Crie um novo aplicativo de console e adicione as diretivas `using` necessárias:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // The implementation starts in the next sections
        }
    }
}
```

A classe `BarcodeGenerator` é o núcleo da API de gerador de código de barras C#. Ela recebe o tipo de simbologia e o texto a ser codificado.

## Etapa 2: Gerar um código de barras DataBar Expanded Stacked e definir colunas

O primeiro exemplo cria um código de barras com quatro colunas. Ajustar a propriedade `Columns` altera a densidade visual da simbologia DataBar Expanded Stacked.

```csharp
// Step 2: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of columns to 4
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the barcode image as PNG
string colsPath = @"YOUR_DIRECTORY\DatabarCols4.png";
barcodeGenerator.Save(colsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 4 columns saved to {colsPath}");
```

**Por que isso importa:** A contagem de colunas influencia a quantidade de dados que pode ser armazenada em um espaço compacto. Definir para 4 produz um código de barras mais largo que permanece legível pela maioria dos scanners.

## Etapa 3: Gerar um código de barras com contagem de linhas personalizada

O segundo exemplo mostra como controlar o layout vertical definindo a propriedade `Rows`. Uma configuração de três linhas é útil quando você precisa de um código de barras mais alto para espaço horizontal limitado.

```csharp
// Step 3: Create a second barcode generator for the same type
BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of rows to 3
barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

// Save the barcode image as PNG
string rowsPath = @"YOUR_DIRECTORY\DatabarRows3.png";
barcodeGeneratorRows.Save(rowsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 3 rows saved to {rowsPath}");
```

**Por que isso importa:** Ajustar as linhas permite encaixar o código de barras em uma coluna estreita enquanto preserva a legibilidade. O gerador de código de barras C# recalcula automaticamente o tamanho do módulo para atender à especificação.

## Etapa 4: Exemplo completo e executável

Abaixo está um programa autônomo que combina as etapas anteriores. Copie o código para `Program.cs`, substitua `YOUR_DIRECTORY` por um caminho de pasta existente e execute o aplicativo.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ---------- Generate barcode with 4 columns ----------
            BarcodeGenerator colsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            colsGenerator.Parameters.Barcode.DataBar.Columns = 4;

            string colsFile = @"YOUR_DIRECTORY\DatabarCols4.png";
            colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with columns saved to {colsFile}");

            // ---------- Generate barcode with 3 rows ----------
            BarcodeGenerator rowsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            rowsGenerator.Parameters.Barcode.DataBar.Rows = 3;

            string rowsFile = @"YOUR_DIRECTORY\DatabarRows3.png";
            rowsGenerator.Save(rowsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with rows saved to {rowsFile}");
        }
    }
}
```

### Saída esperada

Ao executar o programa, dois arquivos PNG aparecem no diretório de destino:

* **DatabarCols4.png** – um código de barras DataBar Expanded Stacked com quatro colunas  
* **DatabarRows3.png** – os mesmos dados codificados em três linhas  

Abra as imagens com qualquer visualizador; elas exibem códigos de barras nítidos e escaneáveis, prontos para impressão ou incorporação em PDFs.

## Como gerar imagem de código de barras com dimensões personalizadas

Se você precisar de um tamanho de imagem específico, ajuste as propriedades `ImageHeight` e `ImageWidth` antes de chamar `Save`:

```csharp
colsGenerator.Parameters.ImageHeight = 150; // pixels
colsGenerator.Parameters.ImageWidth = 300;  // pixels
colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
```

Alterar as dimensões não afeta os dados codificados; apenas escala a representação visual. Essa técnica é útil ao integrar códigos de barras em componentes de UI com restrições de layout fixas.

## Armadilhas comuns e dicas profissionais

* **Separadores de caminho:** Use strings verbatim (`@"C:\Path\file.png"`) ou `Path.Combine` para evitar problemas de caracteres de escape no Windows.  
* **Aplicação de licença:** Sem uma licença válida, as imagens geradas contêm uma marca d'água. Aplique sua licença logo no início da aplicação:

  ```csharp
  Aspose.BarCode.License license = new Aspose.BarCode.License();
  license.SetLicense("Aspose.BarCode.lic");
  ```

* **Limites de codificação:** DataBar Expanded Stacked suporta até 74 caracteres numéricos. Exceder esse limite lança uma exceção. Valide o comprimento da entrada antes de criar o gerador.  
* **Desempenho:** Reutilizar uma única instância `BarcodeGenerator` para várias gravações reduz a alocação de memória. Alterar as propriedades `Rows` ou `Columns` entre gravações somente se o texto codificado permanecer o mesmo.

## Próximos passos

Agora que você pode gerar imagens de código de barras com o gerador de código de barras C#, considere explorar:

* **Simbologias diferentes** – experimente `EncodeTypes.QR`, `EncodeTypes.Code128` ou `EncodeTypes.Pdf417`.  
* **Personalização de cores** – defina `Parameters.Barcode.ForeColor` e `BackColor` para combinar com a identidade visual.  
* **Incorporação em PDFs** – combine o PNG gerado com Aspose.PDF para criar documentos imprimíveis.  

Essas extensões permitem que você construa uma solução completa de código de barras para aplicações de inventário, logística ou varejo.

---

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá-lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Gerar imagem de código de barras – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Criar imagem de código de barras DotCode – linhas & colunas (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Como gerar códigos de barras DataMatrix (ECC 200) com Aspose.BarCode para .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}