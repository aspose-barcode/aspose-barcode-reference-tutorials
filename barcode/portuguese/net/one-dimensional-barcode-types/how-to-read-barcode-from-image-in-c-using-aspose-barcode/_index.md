---
category: general
date: 2026-10-18
description: Aprenda a ler códigos de barras de imagens em C# com Aspose.BarCode,
  abordando a extração de metadados Macro PDF417 e um código de exemplo completo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode from image
- C# barcode reader
- Macro PDF417 metadata
- BarCodeReader class
- DecodeType.MacroPdf417
- barcode metadata extraction
language: pt
lastmod: 2026-10-18
og_description: Como ler código de barras a partir de uma imagem usando C# Aspose.BarCode.
  Siga este tutorial passo a passo para extrair metadados Macro PDF417 e lidar com
  cenários comuns.
og_image_alt: Screenshot showing output of how to read barcode from image with C#
  Aspose.BarCode
og_title: Como ler código de barras a partir de imagem em C# – guia completo do Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  headline: How to read barcode from image in C# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  name: How to read barcode from image in C# using Aspose.BarCode
  steps:
  - name: Expected console output
    text: '``` CodeType: MacroPdf417 CodeText: https://example.com/document.pdf MacroFileID:
      12345 MacroSegmentID: 1 MacroSegmentsCount: 3 MacroFileName: document.pdf MacroChecksum:
      0x1A2B3C4D MacroFileSize: 204800 MacroTimeStamp: 2023-07-15T10:23:45Z MacroAddressee:
      Acme Corp MacroSender: Warehouse 7 MacroTer'
  - name: Large images
    text: 'Reading very large images can consume significant memory. Use the `BarcodeReader`
      overload that accepts `ReaderParameters` to limit the maximum image size:'
  - name: Missing or corrupted metadata
    text: If any of the Macro fields are missing, the corresponding property returns
      `null` or `0`. Log these cases and decide whether to treat the barcode as incomplete.
  - name: Multiple barcode types in one image
    text: 'If an image may contain other barcode formats, you can pass an array of
      `DecodeType` values:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Como ler código de barras de uma imagem em C# usando Aspose.BarCode
url: /pt/net/one-dimensional-barcode-types/how-to-read-barcode-from-image-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como ler código de barras a partir de imagem em C# usando Aspose.BarCode

Se você precisa **como ler código de barras a partir de imagem** em uma aplicação .NET, este guia mostra os passos exatos com Aspose.BarCode. Seja processando documentos escaneados, recibos ou etiquetas de inventário, você verá como ler o código de barras, extrair os metadados Macro PDF417 e lidar com casos de borda típicos.

Ler um código de barras a partir de uma imagem é uma tarefa rotineira, mas extrair os campos estendidos Macro PDF417 adiciona uma camada de complexidade. Este tutorial cobre o fluxo de trabalho completo, desde a configuração do projeto até um exemplo totalmente executável, para que você possa copiar‑colar o código e ver resultados imediatos.

## O que você aprenderá

- Como configurar o Aspose.BarCode para projetos C#.
- A forma correta de instanciar o **leitor de código de barras C#** para uma imagem Macro PDF417.
- Como iterar sobre cada código de barras detectado e exibir informações básicas.
- Como acessar os **metadados Macro PDF417** como ID do arquivo, ID do segmento e checksum.
- Dicas para lidar com metadados ausentes, imagens grandes e erros comuns de decodificação.

**Pré-requisitos**

- .NET 6.0 (ou superior) instalado.  
- Familiaridade básica com C# e Visual Studio (qualquer IDE funciona).  
- Um arquivo de imagem que contém um código de barras Macro PDF417 (por exemplo, `ExtPDF417Meta.png`).  

## Etapa 1: Instalar Aspose.BarCode

Abra um terminal na pasta do seu projeto e execute:

```bash
dotnet add package Aspose.BarCode
```

O pacote inclui a **classe BarCodeReader**, que implementa a funcionalidade do **leitor de código de barras C#** necessária para este tutorial.

## Etapa 2: Configurar o ambiente de desenvolvimento

Crie uma nova aplicação console se ainda não tiver uma:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Adicione as diretivas `using` no início do `Program.cs`:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

Esses namespaces expõem a **classe BarCodeReader** e a enumeração `DecodeType` necessária para a decodificação Macro PDF417.

## Etapa 3: Inicializar o BarCodeReader para Macro PDF417

O núcleo de **como ler código de barras a partir de imagem** é criar uma instância de `BarCodeReader` que aponta para o `DecodeType` específico. Para Macro PDF417 você deve passar `DecodeType.MacroPdf417`:

```csharp
// Step 3: Create a barcode reader for a Macro PDF417 image
using (BarCodeReader reader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png", DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
}
```

**Por que isso importa:**  
Selecionar `DecodeType.MacroPdf417` indica à biblioteca que procure o formato estendido Macro PDF417, que contém campos adicionais além dos dados básicos do código de barras. Se você usar um `DecodeType.Pdf417` genérico, esses campos extras seriam ignorados.

## Etapa 4: Iterar sobre os códigos de barras detectados

Uma única imagem pode conter múltiplos códigos de barras. O método `ReadBarCodes()` retorna uma coleção enumerável de objetos `BarCodeResult`. Percorra-os para exibir as informações básicas de cada código de barras:

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"CodeType: {result.CodeTypeName}");
    Console.WriteLine($"CodeText: {result.CodeText}");
}
```

`CodeTypeName` informa a simbologia exata do código de barras (por exemplo, “MacroPdf417”), enquanto `CodeText` contém a string decodificada.

## Etapa 5: Extrair e exibir metadados Macro PDF417

Quando o código de barras é um Macro PDF417, a propriedade `Extended.Pdf417` fornece um conjunto rico de campos de metadados. Acesse-os diretamente como mostrado abaixo:

```csharp
Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Esses campos fornecem tudo que você precisa para reconstruir o arquivo original de múltiplos segmentos, verificar a integridade e associar o código de barras a um documento ou remetente específico.

### Saída esperada no console

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
MacroFileID: 12345
MacroSegmentID: 1
MacroSegmentsCount: 3
MacroFileName: document.pdf
MacroChecksum: 0x1A2B3C4D
MacroFileSize: 204800
MacroTimeStamp: 2023-07-15T10:23:45Z
MacroAddressee: Acme Corp
MacroSender: Warehouse 7
MacroTerminator: END
```

Se a imagem não contiver um código de barras Macro PDF417, o objeto `Extended.Pdf417` será `null`. Proteja-se contra isso para evitar `NullReferenceException`:

```csharp
if (result.Extended?.Pdf417 != null)
{
    // Safe to read metadata
}
else
{
    Console.WriteLine("No Macro PDF417 metadata found.");
}
```

## Etapa 6: Tratamento de erros comuns e casos de borda

### Imagens grandes

Ler imagens muito grandes pode consumir memória significativa. Use a sobrecarga `BarcodeReader` que aceita `ReaderParameters` para limitar o tamanho máximo da imagem:

```csharp
ReaderParameters parameters = new ReaderParameters
{
    MaxImageSize = 4096 // pixels
};

using (BarCodeReader reader = new BarCodeReader(
           "large_image.png", DecodeType.MacroPdf417, parameters))
{
    // Process as before
}
```

### Metadados ausentes ou corrompidos

Se algum dos campos Macro estiver ausente, a propriedade correspondente retornará `null` ou `0`. Registre esses casos e decida se trata o código de barras como incompleto.

### Vários tipos de código de barras em uma imagem

Se uma imagem puder conter outros formatos de código de barras, você pode passar um array de valores `DecodeType`:

```csharp
DecodeType[] types = { DecodeType.MacroPdf417, DecodeType.QR, DecodeType.Code128 };
using (BarCodeReader reader = new BarCodeReader("mixed.png", types))
{
    // Iterate as before
}
```

Esta abordagem mantém a lógica de **como ler código de barras a partir de imagem** flexível sem sacrificar o desempenho.

## Etapa 7: Código-fonte completo

Abaixo está o programa completo, pronto‑para‑executar. Substitua `YOUR_DIRECTORY/ExtPDF417Meta.png` pelo caminho da sua própria imagem.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the C# barcode reader for Macro PDF417
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate over all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // Safely access Macro PDF417 metadata
                    if (result.Extended?.Pdf417 != null)
                    {
                        Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                        Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                        Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                        Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                        Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                        Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                        Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                        Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                        Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                        Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro PDF417 metadata found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Barcode processing completed.");
        }
    }
}
```

Execute o programa com:

```bash
dotnet run
```

Você deverá ver o tipo de código de barras, o texto decodificado e todos os campos Macro PDF417 disponíveis impressos no console.

## Conclusão

Neste tutorial você aprendeu **como ler código de barras a partir de imagem** usando Aspose.BarCode para C#. O guia abordou a configuração do **leitor de código de barras C#**,

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá-lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Ler código de barras a partir de imagem C# – guia completo com Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Como criar código de barras macro PDF417 em C# usando Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Como ler código de barras PDF417 c# – guia completo passo a passo](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}