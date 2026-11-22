---
category: general
date: 2026-11-20
description: Aprenda a criar código de barras macro PDF417 em C# usando Aspose.BarCode.
  Este guia aborda metadados, parâmetros e a gravação da imagem.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- macro PDF417 metadata
- Aspose.BarCode C#
- PDF417 macro parameters
- barcode generator example
language: pt
lastmod: 2026-11-20
og_description: Crie código de barras macro PDF417 em C# com Aspose.BarCode. Siga
  este tutorial completo para definir metadados, configurar parâmetros e exportar
  um PNG.
og_image_alt: Screenshot of a generated macro PDF417 barcode image
og_title: Criar código de barras macro PDF417 em C# – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  headline: How to create macro PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  name: How to create macro PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: Expected output
    text: 'Running the program prints a confirmation line similar to:'
  - name: What if I need more than 20 segments?
    text: The `MacroPdf417SegmentsCount` property can be set up to `255`. Ensure the
      receiving system can handle the larger segment count, and consider splitting
      the data into a manageable number of symbols.
  - name: How does the checksum affect scanning?
    text: The CCITT‑16 checksum (`MacroPdf417Checksum`) provides an additional error‑checking
      layer. If a scanner detects a mismatch, it will reject the barcode. You can
      omit the checksum if your workflow does not require it.
  - name: Can I generate a PDF417 macro barcode without Aspose?
    text: Yes, other libraries (e.g., ZXing.Net, Dynamsoft) support PDF417, but macro‑specific
      fields are often missing. Aspose.BarCode offers the most complete implementation
      for macro metadata.
  - name: What image formats are supported for saving?
    text: The `Save` method accepts any format defined in `BarCodeImageFormat`, such
      as `Png`, `Jpeg`, `Gif`, `Bmp`, and `Tiff`. Choose a format that matches your
      downstream processing pipeline.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Como criar um código de barras macro PDF417 com Aspose.BarCode em C#
url: /pt/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar código de barras macro PDF417 com Aspose.BarCode em C#

Se você precisa **criar um código de barras macro PDF417** em uma aplicação .NET, este tutorial mostra os passos exatos. Você verá como configurar metadados específicos de macro, ajustar as configurações visuais e salvar o resultado como um arquivo PNG.

Gerar um código de barras macro PDF417 é útil quando você deseja dividir um grande conjunto de dados em vários símbolos, preservando um identificador de todo o arquivo. No exemplo abaixo usamos a biblioteca Aspose.BarCode, que fornece uma API fluente para todos os recursos do PDF417.

Ao final deste guia você terá um programa de console pronto‑para‑executar que produz uma imagem de código de barras contendo todas as informações de macro.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou posterior instalado.
* Visual Studio 2022 (ou qualquer IDE que suporte C#).
* O pacote NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`).

Você pode adicionar o pacote com o seguinte comando:

```bash
dotnet add package Aspose.BarCode
```

## Etapa 1: Inicializar o gerador de código de barras para macro PDF417

O primeiro passo é instanciar um `BarcodeGenerator` com o valor enum `EncodeTypes.MacroPdf417`. Isso indica à biblioteca que o código de barras deve ser tratado como um símbolo macro PDF417.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The generator is now ready for further configuration.
```

*Por que isso importa*: Selecionar `MacroPdf417` habilita todas as propriedades relacionadas a macro no objeto de parâmetro `Pdf417`.

## Etapa 2: Definir a aparência visual básica

Um código de barras legível começa com um tamanho de módulo e contagem de colunas adequados. A propriedade `XDimension.Pixels` controla a largura de um único módulo, enquanto `Pdf417.Columns` define quantas colunas de dados cada linha contém.

```csharp
    // Set module width to 2 pixels.
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

    // Use 5 columns per row – a compact layout for this example.
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
```

Ajustar esses valores influencia tanto a confiabilidade do scanner quanto o tamanho da imagem.

## Etapa 3: Definir detalhes de identificação do arquivo macro

Macro PDF417 requer um identificador de arquivo, um identificador de segmento e a contagem total de segmentos. Esses três campos permitem que um scanner reconstitua o conjunto de dados original.

```csharp
    // Unique file identifier for the whole macro file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (starting at 0 or 1 based on your protocol).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the complete file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Optional human‑readable file name.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

Esses **parâmetros macro PDF417** são o núcleo da funcionalidade macro. Sem eles, um scanner não pode vincular os símbolos entre si.

## Etapa 4: Adicionar metadados macro opcionais

Além dos identificadores obrigatórios, o formato macro suporta campos adicionais como checksum, tamanho do arquivo, timestamp, destinatário, remetente e uma bandeira de terminador. Fornecer esses dados melhora a detecção de erros e fornece contexto para sistemas downstream.

```csharp
    // CCITT‑16 checksum example.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate file size in bytes (helps the receiver allocate buffers).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

    // Timestamp of when the macro file was generated.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the final segment.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Dica profissional*: Se seu fluxo de trabalho não precisar de um campo específico, você pode deixá‑lo com o valor padrão. A biblioteca omitirá o elemento de dados correspondente do código de barras.

## Etapa 5: Salvar a imagem do código de barras

Depois de configurar todos os parâmetros, chame `Save` para exportar o código de barras. O exemplo armazena o arquivo PNG em um diretório especificado pelo usuário.

```csharp
    // Replace with a valid folder on your machine.
    string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

    // Save as PNG – other formats (Jpeg, Gif, etc.) are also supported.
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Quando o programa termina, `ExtPDF417Meta.png` contém um código de barras macro PDF417 que codifica o texto `"Åspóse.Barcóde©"` juntamente com todos os metadados macro.

## Código-fonte completo

Abaixo está o programa completo e autocontido. Copie‑o para um novo projeto de console e execute‑o após instalar o pacote NuGet Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a macro PDF417 barcode generator.
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Visual appearance.
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

                // Step 3: Core macro identifiers.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Step 4: Optional macro metadata.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 5: Export the image.
                string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Macro PDF417 barcode saved to {outputPath}");
            }
        }
    }
}
```

### Saída esperada

Executar o programa imprime uma linha de confirmação semelhante a:

```
Macro PDF417 barcode saved to YOUR_DIRECTORY/ExtPDF417Meta.png
```

Abrir o arquivo PNG mostra um código de barras denso e de alto contraste. Escaneá‑lo com um scanner compatível com PDF417 retorna o texto original mais todos os campos macro.

## Perguntas comuns e casos extremos

### E se eu precisar de mais de 20 segmentos?

A propriedade `MacroPdf417SegmentsCount` pode ser definida até `255`. Certifique‑se de que o sistema receptor pode lidar com a contagem maior de segmentos e considere dividir os dados em um número manejável de símbolos.

### Como o checksum afeta a leitura?

O checksum CCITT‑16 (`MacroPdf417Checksum`) fornece uma camada adicional de verificação de erros. Se um scanner detectar uma incompatibilidade, ele rejeitará o código de barras. Você pode omitir o checksum se seu fluxo de trabalho não o exigir.

### Posso gerar um código de barras macro PDF417 sem o Aspose?

Sim, outras bibliotecas (ex.: ZXing.Net, Dynamsoft) suportam PDF417, mas os campos específicos de macro frequentemente estão ausentes. Aspose.BarCode oferece a implementação mais completa para metadados macro.

### Quais formatos de imagem são suportados para salvamento?

O método `Save` aceita qualquer formato definido em `BarCodeImageFormat`, como `Png`, `Jpeg`, `Gif`, `Bmp` e `Tiff`. Escolha um formato que corresponda ao seu pipeline de processamento downstream.

## Conclusão

Agora você sabe como **criar um código de barras macro PDF417** em C# usando Aspose.BarCode. O tutorial abordou a inicialização do gerador, configurações visuais, identificadores de arquivo macro, metadados opcionais e exportação de imagem. Com essa base você pode incorporar macro PDFs em sistemas de inventário, rastreamento de documentos ou qualquer cenário que exija transmissão de dados segmentados.

Os próximos passos incluem experimentar diferentes valores de `XDimension` para maior resolução, adicionar ajustes de nível de correção de erro ou integrar o código de barras em uma API web que retorne o fluxo PNG diretamente. Para tópicos relacionados, veja tutoriais sobre **exemplo de gerador de código de barras**, **parâmetros macro PDF417** e **manipulação de metadados macro PDF417**.

Feliz codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como criar imagem de código de barras PDF417 em C# com opções Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [Ler código de barras a partir de imagem C# – guia completo com Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Como criar código de barras PDF417 com Aspose – Guia completo passo a passo](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}