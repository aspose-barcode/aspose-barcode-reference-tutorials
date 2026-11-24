---
category: general
date: 2026-11-23
description: Aprenda a gerar imagem de código de barras usando Aspose.BarCode para
  .NET com metadados MacroPdf417 em C#. Siga o guia completo passo a passo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode image
- MacroPdf417 barcode
- Aspose.BarCode for .NET
- set barcode metadata
- barcode image format
- C# barcode generation
language: pt
lastmod: 2026-11-23
og_description: Como gerar imagem de código de barras usando Aspose.BarCode para .NET.
  Este tutorial mostra a configuração de metadados MacroPdf417 e a geração de código
  de barras em C#.
og_image_alt: Barcode image generated with MacroPdf417 using C#
og_title: Como gerar imagem de código de barras com MacroPdf417 em C#
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to generate barcode image using Aspose.BarCode for .NET with
    MacroPdf417 metadata in C#. Follow the complete step‑by‑step guide.
  headline: How to generate barcode image with MacroPdf417 in C#
  type: TechArticle
- description: Learn how to generate barcode image using Aspose.BarCode for .NET with
    MacroPdf417 metadata in C#. Follow the complete step‑by‑step guide.
  name: How to generate barcode image with MacroPdf417 in C#
  steps:
  - name: Open a terminal or the Package Manager Console in Visual Studio.
    text: Open a terminal or the Package Manager Console in Visual Studio.
  - name: 'Run the following command:'
    text: 'Run the following command:'
  - name: '**Visual inspection** – The barcode should display a series of stacked
      columns with a quiet zone (white margin) around it.'
    text: '**Visual inspection** – The barcode should display a series of stacked
      columns with a quiet zone (white margin) around it.'
  - name: '**Decoding test** – Use a barcode scanner app or the Aspose.BarCode `BarCodeReader`
      class to read the image back and confirm that all metadata fields are correctly
      embedded.'
    text: '**Decoding test** – Use a barcode scanner app or the Aspose.BarCode `BarCodeReader`
      class to read the image back and confirm that all metadata fields are correctly
      embedded.'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- PDF417
title: Como gerar imagem de código de barras com MacroPdf417 em C#
url: /pt/net/compact-pdf417-encoding/how-to-generate-barcode-image-with-macropdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar imagem de código de barras com MacroPdf417 em C#

Se você precisa **gerar imagem de código de barras** em uma aplicação .NET, este guia mostra exatamente como fazer isso com **Aspose.BarCode for .NET**. Vamos percorrer a criação de um **código de barras MacroPdf417**, a configuração de seus metadados e a gravação do resultado como um arquivo PNG.

Este tutorial cobre tudo, desde a instalação da biblioteca até a escrita de um programa console completo e executável. Ao final, você terá um exemplo de código pronto‑para‑uso que produz uma imagem de código de barras de alta qualidade e entenderá como **definir metadados do código de barras**, escolher um **formato de imagem do código de barras** e solucionar armadilhas comuns. Não é necessário ter experiência prévia com Aspose — apenas um conhecimento básico de C#.

## Instalar Aspose.BarCode for .NET

Antes de poder **gerar imagem de código de barras**, você precisa do pacote NuGet Aspose.BarCode.

1. Abra um terminal ou o Package Manager Console no Visual Studio.  
2. Execute o seguinte comando:

```bash
dotnet add package Aspose.BarCode
```

O pacote adiciona o namespace `Aspose.BarCode.Generation`, que contém a classe `BarcodeGenerator` usada para **geração de código de barras em C#**.

> **Dica de especialista:** Use a versão estável mais recente (em novembro 2026 a versão atual é 24.11) para obter os recursos mais novos e correções de bugs.

## Criar a instância de BarcodeGenerator

O primeiro passo do código cria um `BarcodeGenerator` configurado para o tipo **código de barras MacroPdf417** e fornece a string de dados que você deseja codificar.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a BarcodeGenerator for MacroPdf417 with the desired text
            using (BarcodeGenerator barcodeGenerator =
                   new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Subsequent configuration goes here...
```

O bloco `using` garante que o gerador seja descartado corretamente, liberando quaisquer recursos não gerenciados.

## Configurar aparência básica

Um código de barras legível começa com dimensões sensatas. Aqui definimos a largura em pixels de cada módulo (`XDimension`) e o número de colunas para a matriz PDF417.

```csharp
                // Step 2: Set basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel width of a module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

*Por que esses valores?*  
- **XDimension** controla a espessura de cada barra; 2 pixels funciona bem para visualização em tela e a maioria das impressoras.  
- **Columns** afeta a largura geral; um número pequeno de colunas mantém o código de barras compacto enquanto preserva a capacidade de correção de erros.

## Definir metadados do código de barras (específico do MacroPdf417)

MacroPdf417 permite incorporar informações ao nível de arquivo diretamente no código de barras. É aqui que você **define metadados do código de barras**, como ID do arquivo, ID do segmento e timestamps.

```csharp
                // Step 3: Configure MacroPdf417 specific metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### O que cada propriedade significa

| Propriedade | Finalidade |
|-------------|------------|
| **MacroPdf417FileID** | Identificador único para o arquivo lógico ao qual o código de barras pertence. |
| **MacroPdf417SegmentID** | Índice do segmento atual (baseado em zero). |
| **MacroPdf417SegmentsCount** | Número total de segmentos que compõem o arquivo completo. |
| **MacroPdf417FileName** | Nome legível do arquivo fonte. |
| **MacroPdf417Checksum** | Checksum CCITT‑16 opcional para verificação de integridade dos dados. |
| **MacroPdf417FileSize** | Tamanho esperado do arquivo original em bytes. |
| **MacroPdf417TimeStamp** | Data e hora em que o código de barras foi gerado – útil para rastreamento de versões. |
| **MacroPdf417Addressee / Sender** | Strings personalizadas que podem conter informações de roteamento. |
| **MacroPdf417Terminator** | Indica se este segmento é o final (`Set`) ou não (`Unset`). |

> **Caso extremo:** Se você planeja dividir um documento grande em muitos segmentos, mantenha o `SegmentsCount` consistente em todos os códigos de barras gerados. Contagens incompatíveis causarão falhas na decodificação.

## Escolher o formato da imagem do código de barras e salvar

Aspose suporta muitos **formatos de imagem de código de barras** (PNG, JPEG, BMP, TIFF, etc.). PNG é sem perdas e funciona bem na maioria dos cenários web e de impressão.

```csharp
                // Step 4: Save the generated barcode image
                string outputPath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode image saved to: {outputPath}");
            } // end using
        }
    }
}
```

Substitua `YOUR_DIRECTORY` por um caminho absoluto ou relativo onde a aplicação tenha permissão de gravação.

Quando o programa for executado, você verá uma mensagem no console confirmando a localização do arquivo. Abra o arquivo PNG com qualquer visualizador de imagens — você verá um **código de barras MacroPdf417** nítido que codifica o texto fornecido e os metadados que você definiu.

### Saída esperada

```
Barcode image saved to: C:\Projects\BarcodeDemo\ExtPDF417Meta.png
```

O tamanho do arquivo de imagem será aproximadamente 30‑40 KB, dependendo do `XDimension` e da contagem de colunas escolhidos.

## Verificar o código de barras e solucionar problemas

1. **Inspeção visual** – O código de barras deve exibir uma série de colunas empilhadas com uma zona silenciosa (margem branca) ao redor.  
2. **Teste de decodificação** – Use um aplicativo de scanner de códigos de barras ou a classe `BarCodeReader` do Aspose.BarCode para ler a imagem de volta e confirmar que todos os campos de metadados foram incorporados corretamente.  



## O que você deve aprender a seguir?

Os tutoriais abaixo abordam tópicos intimamente relacionados que expandem as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Generate PDF417 barcode image with Aspose.BarCode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-barcode-image-with-pdf417-in-c-step-by-step-gu/)
- [How to generate barcode with custom text using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/)
- [How to read barcodes from image using C# with Aspose.BarCode – step‑by‑step guide](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}