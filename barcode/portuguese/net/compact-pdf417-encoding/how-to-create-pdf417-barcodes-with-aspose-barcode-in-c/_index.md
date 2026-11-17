---
category: general
date: 2026-11-17
description: Como criar códigos de barras PDF417 usando Aspose.BarCode – guia passo
  a passo que também mostra como criar código de barras Aspose em C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to create pdf417
- create barcode aspose
language: pt
lastmod: 2026-11-17
og_description: Como criar códigos de barras PDF417 usando Aspose.BarCode. Este tutorial
  orienta você pelos passos exatos para criar o código de barras Aspose, configurar
  os metadados Macro PDF417 e salvar a imagem.
og_image_alt: Screenshot of a PDF417 barcode generated with Aspose.BarCode in C#
og_title: Como criar códigos de barras PDF417 com Aspose.BarCode – guia completo em
  C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: How to create PDF417 barcodes using Aspose.BarCode – step‑by‑step guide
    that also shows how to create barcode aspose in C#.
  headline: How to create PDF417 barcodes with Aspose.BarCode in C#
  type: TechArticle
- description: How to create PDF417 barcodes using Aspose.BarCode – step‑by‑step guide
    that also shows how to create barcode aspose in C#.
  name: How to create PDF417 barcodes with Aspose.BarCode in C#
  steps:
  - name: Set up the project and import Aspose.BarCode
    text: 'Create a new console project and add the Aspose.BarCode NuGet package:'
  - name: Initialise the `BarcodeGenerator` for Macro PDF417
    text: The `BarcodeGenerator` constructor takes the barcode type and the text you
      want to encode. For Macro PDF417 you use `EncodeTypes.MacroPdf417`.
  - name: Configure appearance and Macro PDF417 metadata
    text: Configure appearance and Macro PDF417 metadata
  - name: Save the barcode image
    text: '```csharp // Choose the output folder (ensure it exists) and save as PNG.
      string outputPath = "MacroPdf417.png"; generator.Save(outputPath, BarCodeImageFormat.Png);
      Console.WriteLine($"PDF417 barcode saved to {outputPath}"); } ```'
  - name: Full, runnable example
    text: 'Putting everything together, here’s the complete program you can compile
      and run immediately:'
  type: HowTo
tags:
- barcode
- pdf417
- aspose
- csharp
title: Como criar códigos de barras PDF417 com Aspose.BarCode em C#
url: /pt/net/compact-pdf417-encoding/how-to-create-pdf417-barcodes-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar códigos de barras PDF417 com Aspose.BarCode em C#

Se você precisa **criar códigos de barras PDF417** para inventário, envio ou rastreamento de documentos, este guia mostra os passos exatos com Aspose.BarCode. Você verá como criar o código de barras, configurar os campos Macro PDF417 e exportar o resultado como uma imagem PNG — tudo em um único programa C# executável.

Criar um código de barras PDF417 é comum quando é necessário codificar grandes quantidades de dados em um formato compacto e legível por máquina. Aspose.BarCode simplifica o processo, permitindo ajustar dimensões, colunas e todo o conjunto de metadados Macro PDF417. Ao final deste tutorial você terá um exemplo completo e autônomo que pode ser inserido em qualquer projeto .NET.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou superior (o código também funciona com .NET Framework 4.7+).
* Uma licença válida do Aspose.BarCode para .NET (a avaliação gratuita funciona para testes).
* Visual Studio 2022, VS Code ou qualquer IDE compatível com C#.
* Familiaridade básica com a sintaxe C# e a instrução `using`.

> **Dica profissional:** Se você executar o exemplo sem uma licença, o Aspose adicionará uma pequena marca d'água à imagem gerada.

## Como criar código de barras PDF417 com Aspose.BarCode

As seções a seguir dividem a implementação em quatro etapas claras. Cada etapa inclui um trecho de código, uma explicação do **porquê** o código é necessário e dicas práticas que você pode aplicar em seus próprios projetos.

### Etapa 1: Configurar o projeto e importar Aspose.BarCode

Crie um novo projeto de console e adicione o pacote NuGet Aspose.BarCode:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Em seguida, abra `Program.cs` e adicione os namespaces necessários:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

*Por que isso importa:* Importar `Aspose.BarCode.Generation` fornece acesso ao `BarcodeGenerator` e à enumeração `EncodeTypes`, que são as classes principais para a criação de códigos de barras.

### Etapa 2: Inicializar o `BarcodeGenerator` para Macro PDF417

O construtor `BarcodeGenerator` recebe o tipo de código de barras e o texto que você deseja codificar. Para Macro PDF417 você usa `EncodeTypes.MacroPdf417`.

```csharp
// Initialise a Macro PDF417 generator with the data you want to encode.
using (BarcodeGenerator generator = 
       new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text for PDF417"))
{
    // The generator instance will be disposed automatically at the end of the block.
```

*Por que isso importa:* A instrução `using` garante que recursos não gerenciados (como manipuladores GDI+) sejam liberados prontamente, evitando vazamentos de memória em serviços de longa execução.

### Etapa 3: Configurar a aparência e os metadados Macro PDF417

#### 3.1 Ajustar parâmetros visuais

```csharp
    // Set the module (X) dimension – 2 pixels gives a reasonably dense barcode.
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Define the number of columns; fewer columns make the barcode taller.
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

#### 3.2 Preencher os campos Macro PDF417

Macro PDF417 permite dividir um documento grande em vários segmentos de código de barras. Os campos abaixo são opcionais, mas frequentemente necessários para sistemas de logística ou gerenciamento de documentos.

```csharp
    // Unique identifier for the whole file (must be the same across all segments).
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Segment index (starting at 1). Here we generate the 12th segment.
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that will be produced.
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Human‑readable file name, useful for audits.
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // CCITT‑16 checksum – helps receivers verify data integrity.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate file size in bytes; some scanners use this for validation.
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

    // Timestamp of the original file creation.
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2024, 5, 1);

    // Optional address fields that can be read by advanced scanners.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator tells the scanner that this is the last segment.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;
```

*Por que esses campos são úteis:*  
* **FileID** une todos os segmentos, permitindo a reconstrução.  
* **SegmentID** e **SegmentsCount** informam ao scanner a ordem e quando a série está completa.  
* **Checksum** e **FileSize** fornecem verificações rápidas de integridade sem decodificar todo o payload.

> **Atenção:** O `MacroPdf417FileID` deve ser exclusivo por documento lógico. Reutilizar o mesmo ID para arquivos não relacionados pode causar erros de reconstrução.

### Etapa 4: Salvar a imagem do código de barras

```csharp
    // Choose the output folder (ensure it exists) and save as PNG.
    string outputPath = "MacroPdf417.png";
    generator.Save(outputPath, BarCodeImageFormat.Png);
    Console.WriteLine($"PDF417 barcode saved to {outputPath}");
}
```

*Por que PNG?* PNG preserva os dados de pixel exatos sem artefatos de compressão, o que é ideal para scanners de códigos de barras que dependem de bordas nítidas.

### Exemplo completo e executável

Juntando tudo, aqui está o programa completo que você pode compilar e executar imediatamente:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1‑4: generate a Macro PDF417 barcode and save it as PNG
            using (BarcodeGenerator generator = 
                   new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text for PDF417"))
            {
                // Appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // Macro PDF417 metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
                    new DateTime(2024, 5, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
                    Pdf417MacroTerminator.Set;

                // Save
                string outputPath = "MacroPdf417.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"PDF417 barcode saved to {outputPath}");
            }
        }
    }
}
```

**Saída esperada:** Após executar o programa, você encontrará `MacroPdf417.png` na pasta do projeto. Ao abrir a imagem, verá um código de barras PDF417 denso e de alto contraste que codifica “Sample text for PDF417” junto com os metadados macro que você forneceu.

## Perguntas frequentes e tratamento de casos limites

| Pergunta | Resposta |
|----------|----------|
| *Posso gerar vários segmentos em um loop?* | Sim. Incrementar `MacroPdf417SegmentID` a cada iteração, manter `MacroPdf417FileID` constante e atualizar `MacroPdf417SegmentsCount` somente depois de conhecer o número total de segmentos. |
| *E se os dados excederem um único símbolo PDF417?* | Macro |

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [How to create a micro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}