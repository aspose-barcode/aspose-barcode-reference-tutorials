---
category: general
date: 2026-10-24
description: Aprenda a ler códigos de barras PDF417 em C# usando Aspose.BarCode. Este
  tutorial aborda a leitura de uma imagem de código de barras, a extração de campos
  Macro PDF417 e o tratamento de cenários comuns.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode image c#
- read barcode with aspose
language: pt
lastmod: 2026-10-24
og_description: Como ler código de barras PDF417 em C# usando Aspose.BarCode. Siga
  este tutorial completo para decodificar imagens, recuperar metadados Macro PDF417
  e evitar armadilhas comuns.
og_image_alt: Screenshot showing how to read PDF417 barcode results in a C# console
  application
og_title: Como ler código de barras PDF417 em C# com Aspose – guia completo
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  headline: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  name: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  steps:
  - name: Why use `DecodeType.MacroPdf417`?
    text: '* **Macro PDF417** stores additional fields (file ID, segment count, timestamps,
      etc.) that are not present in standard PDF417. * The `Extended` property of
      `BarCodeResult` is populated only when you request the macro type, saving you
      a separate parsing step.'
  - name: What each property means
    text: '| Property | Description | |----------|-------------| | **MacroPdf417FileID**
      | Unique identifier for the whole multi‑segment document. | | **MacroPdf417SegmentID**
      | Index of the current segment (starting at 0). | | **MacroPdf417SegmentsCount**
      | Total number of segments that belong to the file. | '
  - name: Missing macro fields
    text: 'Sometimes a PDF417 barcode is generated without the optional macro fields.
      Accessing a missing property returns `null` or `0`. Guard against this if you
      plan to store the values:'
  - name: Corrupted or low‑quality images
    text: 'If the image is blurry, you can improve detection by enabling the `BarCodeReader`
      quality options:'
  - name: Multiple barcode formats in one image
    text: 'If you suspect other barcode types might be present, use `DecodeType.AllSupported`
      and filter results:'
  type: HowTo
- questions:
  - answer: Yes. Change `DecodeType.MacroPdf417` to `DecodeType.Pdf417`. The `Extended`
      property will be empty, but `CodeText` and `CodeTypeName` remain available.
    question: Can I read a standard PDF417 (non‑macro) with the same code?
  - answer: Absolutely. Use the overload `new BarCodeReader(Stream, DecodeType)` and
      pass a `FileStream` or `MemoryStream`. This is useful when the image comes from
      a web API.
    question: Does Aspose.BarCode support reading from a stream instead of a file
      path?
  - answer: 'The `MacroPdf417Checksum` field contains the raw CRC‑16 value. You can
      recompute the checksum on the reconstructed file and compare it to ensure data
      integrity. ## Next steps and related topics * **Write PDF417 barcodes** – explore
      `BarCodeGenerator` to create macro barcodes for testing. * **Combine'
    question: How do I validate the checksum?
  type: FAQPage
tags:
- barcode
- Aspose.BarCode
- C#
title: Como ler código de barras PDF417 em C# com Aspose – guia passo a passo
url: /pt/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-with-aspose-step-by-step-gui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como ler código de barras PDF417 em C# com Aspose – guia passo a passo

Se você precisa **como ler código de barras PDF417** em uma aplicação .NET, este guia mostra exatamente como ler código de barras PDF417 em C# usando a biblioteca Aspose.BarCode. Seja processando documentos digitalizados, capturas móveis ou imagens importadas em lote, o código abaixo decodifica o código de barras e extrai todas as propriedades Macro PDF417 que você possa precisar.

Ler uma imagem de código de barras em C# pode parecer assustador, especialmente quando o código contém metadados estendidos. Este tutorial elimina as suposições ao fornecer um exemplo completo e executável, explicando cada linha e abordando casos de borda como segmentos macro ausentes ou imagens corrompidas. Ao final, você será capaz de integrar a decodificação PDF417 em qualquer projeto C# com confiança.

## Prerequisites

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou posterior instalado  
* Visual Studio 2022 (ou qualquer IDE que suporte .NET)  
* Uma licença ou avaliação gratuita do **Aspose.BarCode for .NET** – você pode obter uma chave temporária no site da Aspose  
* Um arquivo de imagem que contém um código de barras Macro PDF417 (por exemplo, `ExtPDF417Meta.png`)

> **Dica profissional:** Se você só precisa experimentar, a Aspose oferece um teste de 30 dias que inclui funcionalidade completa para leitura de códigos de barras.

## Step 1: Install the Aspose.BarCode NuGet package

Abra a pasta do seu projeto em um terminal e execute:

```bash
dotnet add package Aspose.BarCode
```

O pacote adiciona o namespace `Aspose.BarCode.ReadRecognition`, que contém a classe `BarCodeReader` usada para decodificar imagens.

## Step 2: Create a BarCodeReader for a PDF417 image

O construtor `BarCodeReader` recebe dois argumentos: o caminho para o arquivo de imagem e o `DecodeType` que você deseja direcionar. Especificar `DecodeType.MacroPdf417` indica à Aspose que procure símbolos Macro PDF417 e preencha as propriedades estendidas automaticamente.

```csharp
using Aspose.BarCode.ReadRecognition;

// Replace with the actual path to your barcode image
string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image
```

### Por que usar `DecodeType.MacroPdf417`?

* **Macro PDF417** armazena campos adicionais (ID do arquivo, contagem de segmentos, timestamps, etc.) que não estão presentes no PDF417 padrão.  
* A propriedade `Extended` de `BarCodeResult` é preenchida somente quando você solicita o tipo macro, economizando uma etapa de análise separada.

## Step 3: Iterate through all detected barcodes

Uma única imagem pode conter múltiplos símbolos PDF417 (por exemplo, quando um documento é dividido em várias páginas). O método `ReadBarCodes()` retorna um `IEnumerable<BarCodeResult>` que você pode percorrer.

```csharp
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Basic information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

Se a imagem não contiver nenhum código de barras, o laço simplesmente nunca será executado e o programa encerrará de forma graciosa. Esse comportamento torna o código seguro para processamento em lote onde alguns arquivos podem estar sem código de barras.

## Step 4: Output Macro PDF417 extended properties

A propriedade `Extended.Pdf417` agrupa todos os campos específicos do macro. Cada campo mapeia diretamente para a especificação PDF417, permitindo que você os armazene em um banco de dados, registre-os ou use-os para validações adicionais.

```csharp
        // Macro PDF417 extended properties
        Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
    }
}
```

### O que cada propriedade significa

| Propriedade | Descrição |
|-------------|-----------|
| **MacroPdf417FileID** | Identificador único para todo o documento multi‑segmento. |
| **MacroPdf417SegmentID** | Índice do segmento atual (começando em 0). |
| **MacroPdf417SegmentsCount** | Número total de segmentos que pertencem ao arquivo. |
| **MacroPdf417FileName** | Nome de arquivo opcional incorporado no código de barras. |
| **MacroPdf417Checksum** | Checksum CRC‑16 para o bloco de dados macro. |
| **MacroPdf417FileSize** | Tamanho original do arquivo em bytes. |
| **MacroPdf417TimeStamp** | Timestamp (data/hora) quando o código de barras macro foi gerado. |
| **MacroPdf417Addressee** | Destinatário pretendido do documento. |
| **MacroPdf417Sender** | Remetente do documento. |
| **MacroPdf417Terminator** | Sinalizador terminador indicando o fim da sequência macro. |

Esses campos são especialmente úteis quando você está reconstruindo um PDF ou imagem grande que foi dividido em vários símbolos PDF417 para impressão em mídia de baixa resolução.

## Step 5: Handle common edge cases

### Campos macro ausentes

Às vezes um código de barras PDF417 é gerado sem os campos macro opcionais. Acessar uma propriedade inexistente retorna `null` ou `0`. Proteja seu código contra isso se planeja armazenar os valores:

```csharp
string fileName = result.Extended.Pdf417.MacroPdf417FileName ?? "Unnamed";
long fileSize = result.Extended.Pdf417.MacroPdf417FileSize;
```

### Imagens corrompidas ou de baixa qualidade

Se a imagem estiver borrada, você pode melhorar a detecção habilitando as opções de qualidade do `BarCodeReader`:

```csharp
reader.BarcodeSettings.ImageQuality = 90; // value between 0‑100
reader.BarcodeSettings.PureBarcode = false; // allow detection in noisy backgrounds
```

Essas configurações são opcionais, mas podem aumentar drasticamente a taxa de sucesso para documentos escaneados.

### Vários formatos de código de barras em uma única imagem

Se suspeitar que outros tipos de código de barras possam estar presentes, use `DecodeType.AllSupported` e filtre os resultados:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        if (result.CodeType == DecodeType.MacroPdf417)
        {
            // Process macro PDF417 as shown above
        }
    }
}
```

## Complete runnable example

Copie o programa a seguir para um novo projeto de console (`dotnet new console`) e execute-o. Substitua a variável `imagePath` pela localização da sua própria imagem Macro PDF417.

```csharp
using System;
using Aspose.BarCode.ReadRecognition;

class Program
{
    static void Main()
    {
        // Path to the barcode image
        string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Optional: improve detection on low‑quality scans
            reader.BarcodeSettings.ImageQuality = 90;
            reader.BarcodeSettings.PureBarcode = false;

            // Iterate through every barcode found in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Output extended Macro PDF417 fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender ?? \"N/A\"}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Saída esperada** (os valores variarão conforme sua imagem):

```
CodeType: MacroPdf417
CodeText: 1234567890ABCDEFGHIJ
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: Invoice_2026_10.pdf
Pdf417MacroChecksum: 32768
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2026-10-24T14:32:10Z
Pdf417MacroAddressee: AccountingDept
Pdf417MacroSender: SalesTeam
MacroPdf417Terminator: True
----------------------------------------
```

Se a imagem não contiver símbolos Macro PDF417, o programa não escreverá nada e encerrará silenciosamente — perfeito para jobs em lote que processam muitos arquivos.

## Frequently asked questions

**Q: Posso ler um PDF417 padrão (não‑macro) com o mesmo código?**  
A: Sim. Altere `DecodeType.MacroPdf417` para `DecodeType.Pdf417`. A propriedade `Extended` ficará vazia, mas `CodeText` e `CodeTypeName` permanecerão disponíveis.

**Q: O Aspose.BarCode suporta leitura a partir de um stream em vez de um caminho de arquivo?**  
A: Absolutamente. Use a sobrecarga `new BarCodeReader(Stream, DecodeType)` e passe um `FileStream` ou `MemoryStream`. Isso é útil quando a imagem vem de uma API web.

**Q: Como validar o checksum?**  
A: O campo `MacroPdf417Checksum` contém o valor bruto CRC‑16. Você pode recalcular o checksum no arquivo reconstruído e compará‑lo para garantir a integridade dos dados.

## Next steps and related topics

* **Criar códigos de barras PDF417** – explore `BarCodeGenerator` para criar códigos de barras macro para testes.  
* **Combinar múltiplos segmentos** – após ler todos os segmentos, ordene‑os por `MacroPdf417SegmentID` e concatene `CodeText` para reconstruir a carga original.  
* **Ajuste de desempenho** – para cenários de alta taxa de transferência, reutilize uma única instância `BarCodeReader` em muitas imagens e

## What Should You Learn Next?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que expandem as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como ler PDF417 em C# – Exemplo completo de código de barras](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [Como criar código de barras macro PDF417 em C# usando Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Ler código de barras de imagem C# – guia completo com Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}