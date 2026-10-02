---
category: general
date: 2026-10-02
description: Aprenda a ler códigos de barras a partir de imagens em C# com um exemplo
  completo que mostra como decodificar códigos de barras PDF417 usando o Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image c#
- how to decode pdf417 barcode
language: pt
lastmod: 2026-10-02
og_description: Leia o código de barras da imagem em C# com Aspose.BarCode. Este tutorial
  explica como decodificar o código de barras PDF417 e extrair metadados estendidos.
og_image_alt: Screenshot showing how to read barcode from image c# in Visual Studio
og_title: Ler código de barras de imagem em C# – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to read barcode from image c# with a complete example that
    shows how to decode PDF417 barcode using Aspose.BarCode.
  headline: How to read barcode from image c# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image c# with a complete example that
    shows how to decode PDF417 barcode using Aspose.BarCode.
  name: How to read barcode from image c# using Aspose.BarCode
  steps:
  - name: Create a `BarCodeReader` for a PDF417 image
    text: '```csharp using System; using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Iterate over all detected barcodes
    text: '```csharp // Step 2: Read every barcode found in the image foreach (BarCodeResult
      barcodeResult in barcodeReader.ReadBarCodes()) { // At this point you have successfully
      read barcode from image c#. ```'
  - name: Access the extended PDF417 macro metadata
    text: '```csharp // Step 3: Grab the macro‑PDF417 extended information var macro
      = barcodeResult.Extended.Pdf417;'
  - name: Output the barcode text and macro details
    text: '```csharp // Step 4: Print the basic barcode information Console.WriteLine($"Type:
      {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");'
  - name: Handle errors and clean up resources
    text: 'The `using` statement automatically disposes the `BarCodeReader`. However,
      you should still catch exceptions that may arise from missing files or unsupported
      formats:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Como ler código de barras de uma imagem em C# usando Aspose.BarCode
url: /pt/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como ler barcode from image c# using Aspose.BarCode

Se você precisa **read barcode from image c#**, este guia leva você passo a passo por uma solução completa e executável. Você aprenderá como decode um PDF417 barcode, acessar seus extended macro data e imprimir os resultados no console.

Ler barcodes a partir de imagens é uma necessidade comum para sistemas de inventário, validação de ingressos e processamento de documentos. Este tutorial cobre tudo o que você precisa: pacotes necessários, explicação do código, tratamento de edge‑case e output esperado. Nenhuma documentação externa é necessária; o exemplo funciona pronto para uso com Aspose.BarCode .NET.

## Prerequisites

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou versão posterior instalada  
* Visual Studio 2022 (ou qualquer IDE C#)  
* Uma referência NuGet ao **Aspose.BarCode** (versão 23.10 ou mais recente)  
* Um arquivo de imagem que contenha um PDF417 barcode – por exemplo `ExtPDF417Meta.png`

Se algum desses itens estiver faltando, instale o .NET SDK, adicione o pacote NuGet com `dotnet add package Aspose.BarCode` e coloque a imagem em uma pasta que você possa referenciar a partir do seu projeto.

## How to read barcode from image c# – step‑by‑step

As seções a seguir dividem a implementação em passos lógicos. Cada passo inclui um snippet de código, uma explicação do **por que** o passo é importante e uma dica que você pode aplicar em projetos reais.

### Step 1: Create a `BarCodeReader` for a PDF417 image

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Initialise the reader for a Macro PDF417 image
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // The DecodeType enum tells the library which symbology to look for.
        // Using DecodeType.MacroPdf417 restricts the scan to PDF417 macro symbols.
        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // The reader is now ready to read barcode from image c# efficiently.
```

**Why this matters** – O construtor `BarCodeReader` aceita o caminho da imagem e o tipo de barcode esperado. Especificar `MacroPdf417` restringe a busca, o que melhora a performance e reduz falsos positivos quando a imagem contém múltiplas simbologias.

**Pro tip:** Se você não tem certeza sobre o tipo de barcode, use `DecodeType.AllSupportedTypes` e filtre os resultados depois.

### Step 2: Iterate over all detected barcodes

```csharp
            // Step 2: Read every barcode found in the image
            foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
            {
                // At this point you have successfully read barcode from image c#.
```

**Why this matters** – Uma imagem PDF417 macro pode conter vários segmentos. O método `ReadBarCodes()` retorna uma coleção, permitindo que você processe cada segmento individualmente.

**Edge case:** Se a imagem não contiver nenhum símbolo PDF417, a coleção estará vazia e o corpo do loop nunca será executado. Considere adicionar uma verificação após o loop para informar o usuário.

### Step 3: Access the extended PDF417 macro metadata

```csharp
                // Step 3: Grab the macro‑PDF417 extended information
                var macro = barcodeResult.Extended.Pdf417;

                // The macro object holds file‑level data that PDF417 uses for
                // multi‑segment documents such as shipping manifests.
```

**Why this matters** – A propriedade `Extended.Pdf417` expõe campos definidos pela especificação PDF417, como file ID, segment ID e file name. Esses dados são essenciais quando você precisa reconstruir um documento multipágina a partir de scans de barcode separados.

**Pro tip:** Sempre verifique se `barcodeResult.Extended` não é null antes de acessar `Pdf417`. A biblioteca retorna `null` para simbologias que não suportam dados estendidos.

### Step 4: Output the barcode text and macro details

```csharp
                // Step 4: Print the basic barcode information
                Console.WriteLine($"Type: {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");

                // Print macro‑specific fields
                Console.WriteLine($"Macro File ID: {macro.MacroPdf417FileID}, Segment ID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count: {macro.MacroPdf417SegmentsCount}, File Name: {macro.MacroPdf417FileName}");
            }
        }
    }
}
```

**Why this matters** – A saída no console fornece visibilidade imediata tanto do texto decodificado quanto dos metadados macro. Isso é útil para depuração e para processamento posterior, como armazenar a informação em um banco de dados.

**Expected output** (assumindo que a imagem de exemplo contém um segmento macro):

```
Type: MacroPdf417, Text: https://example.com/document.pdf
Macro File ID: 12, Segment ID: 1
Segments Count: 3, File Name: shipment_manifest.pdf
```

Se a imagem contiver três segmentos, o loop imprimirá três blocos, cada um com um `Segment ID` diferente.

### Step 5: Handle errors and clean up resources

A instrução `using` descarta automaticamente o `BarCodeReader`. No entanto, você ainda deve capturar exceções que podem surgir de arquivos ausentes ou formatos não suportados:

```csharp
        try
        {
            // Place the entire reader block here (Steps 1‑4)
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"Error while trying to read barcode from image c#: {ex.Message}");
        }
```

**Why this matters** – Aplicações robustas nunca travam porque um arquivo está ausente ou a imagem está corrompida. Fornecer uma mensagem de erro clara ajuda você ou sua equipe de suporte a diagnosticar o problema rapidamente.

## How to decode PDF417 barcode with Aspose.BarCode

A palavra‑chave secundária **how to decode pdf417 barcode** aparece naturalmente nesta seção. Decodificar um PDF417 barcode segue o mesmo padrão mostrado acima, mas você pode omitir a flag `MacroPdf417` se precisar apenas do texto simples:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Decoded text: {result.CodeText}");
    }
}
```

**Why you might choose this variant** – Quando o barcode não carrega informações macro, usar `DecodeType.Pdf417` reduz a sobrecarga de processamento e simplifica o tratamento do resultado.

**Common question:** *E se o barcode estiver rotacionado?*  
Aspose.BarCode detecta automaticamente a rotação e a corrige, portanto você não precisa de código adicional de pré‑processamento de imagem.

## Full, runnable example

Copie todo o programa abaixo para um novo projeto console (`dotnet new console`) e substitua `YOUR_DIRECTORY/ExtPDF417Meta.png` pelo caminho real da sua imagem.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    var macro = barcodeResult.Extended?.Pdf417;

                    Console.WriteLine($"Type: {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");

                    if (macro != null)
                    {
                        Console.WriteLine($"Macro File ID: {macro.MacroPdf417FileID}, Segment ID: {macro.MacroPdf417SegmentID}");
                        Console.WriteLine($"Segments Count: {macro.MacroPdf417SegmentsCount}, File Name: {macro.MacroPdf417FileName}");
                    }
                    else
                    {
                        Console.WriteLine("No macro PDF417 metadata available.");
                    }
                }
            }
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"Error while trying to read barcode from image c#: {ex.Message}");
        }
    }
}
```

Executar o programa imprime o tipo de barcode, o texto decodificado e quaisquer metadados macro. Se a imagem não contiver um PDF417 macro, o programa informa isso de forma elegante.

## Conclusion

Agora você sabe como **read barcode from image c#** com Aspose.BarCode, como **decode PDF417 barcode** e como extrair os campos estendidos macro‑PDF417. A solução cobre inicialização, iteração, acesso a metadados, tratamento de erros e uma variante para decodificação plain PDF417.

A partir daqui você pode:

* Armazenar os dados extraídos em um banco de dados SQL para recuperação futura.  
* Combinar múltiplos segmentos para reconstruir o documento original.  
* Explorar outras simbologias suportadas pelo Aspose.BarCode, como  

## What Should You Learn Next?

Os tutoriais a seguir cobrem tópicos estreitamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como ler PDF417 em C# – Exemplo completo de código de barras](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [Como ler PDF417 em C# – Exemplo completo de leitor de código de barras](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Como gerar imagem de código de barras PDF417 em C# com Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}