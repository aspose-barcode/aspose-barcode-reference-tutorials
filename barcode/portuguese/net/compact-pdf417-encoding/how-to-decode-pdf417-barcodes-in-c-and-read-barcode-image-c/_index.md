---
category: general
date: 2026-10-28
description: Como decodificar códigos de barras PDF417 em C# rapidamente. Aprenda
  a ler imagens de códigos de barras em C# usando Aspose.BarCode com um exemplo completo
  e executável.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcode image c#
- PDF417 decoding C#
- barcode reader C#
- Aspose.BarCode example
language: pt
lastmod: 2026-10-28
og_description: Como decodificar códigos de barras PDF417 em C# com Aspose.BarCode.
  Este guia mostra como ler a imagem do código de barras em C# passo a passo, completo
  com código.
og_image_alt: Screenshot of C# code that decodes a PDF417 barcode from an image
og_title: Como decodificar códigos de barras PDF417 em C# – tutorial C# para ler imagem
  de código de barras
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to decode PDF417 barcodes in C# quickly. Learn to read barcode
    image C# using Aspose.BarCode with a complete, runnable example.
  headline: How to decode PDF417 barcodes in C# and read barcode image C#
  type: TechArticle
- description: How to decode PDF417 barcodes in C# quickly. Learn to read barcode
    image C# using Aspose.BarCode with a complete, runnable example.
  name: How to decode PDF417 barcodes in C# and read barcode image C#
  steps:
  - name: What each line does
    text: '| Line | Explanation | |------|-------------| | `result.CodeTypeName` |
      Human‑readable name of the detected barcode type (e.g., “MacroPdf417”). | |
      `result.CodeText` | The raw data encoded in the barcode. | | `result.Extended.Pdf417.MacroPdf417FileID`
      | Identifier that ties all segments of a macro P'
  - name: Handling common edge cases
    text: '| Situation | Recommended handling | |-----------|----------------------|
      | **No barcode found** | Check `reader.ReadBarCodes().Any()` before the loop
      and display a friendly message. | | **Corrupted image** | Wrap the `BarCodeReader`
      creation in a `try/catch` block for `BarCodeException`. | | **Mult'
  - name: Next steps
    text: '* Explore other barcode formats by changing `DecodeType` (e.g., `DecodeType.QR`,
      `DecodeType.Code128`). * Combine multiple decoded segments to reconstruct the
      original document. * Use the `BarCodeGenerator` class to create test PDF417
      barcodes on the fly.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Como decodificar códigos de barras PDF417 em C# e ler a imagem do código de
  barras em C#
url: /pt/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-and-read-barcode-image-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como decodificar códigos de barras PDF417 em C# e ler imagem de código de barras C#

Se você precisa de **como decodificar pdf417** em uma aplicação .NET, este guia oferece uma solução pronta‑para‑usar. Você verá exatamente como **read barcode image c#** usando a biblioteca Aspose.BarCode, extrair os campos macro‑PDF417 e exibi‑los no console.

A decodificação de códigos de barras PDF417 costuma aparecer em logística, bilhetagem e sistemas de verificação de identidade. Ao final deste tutorial você será capaz de carregar qualquer imagem que contenha um código de barras Macro PDF417, decodificá‑la e acessar os valores de file ID, segment ID e segment count, essenciais para montar documentos de múltiplos segmentos.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou superior instalado  
* Visual Studio 2022 (ou qualquer IDE C#)  
* Um pacote NuGet Aspose.BarCode for .NET (`Aspose.BarCode`)  
* Um arquivo de imagem que contenha um código de barras Macro PDF417 (o exemplo usa `ExtPDF417Meta.png`)

Você pode adicionar o pacote NuGet com o seguinte comando:

```bash
dotnet add package Aspose.BarCode
```

## Etapa 1: Configurar o projeto e importar namespaces

Crie um novo projeto de console e importe os namespaces necessários. As diretivas `using` dão acesso ao `BarCodeReader`, `DecodeType` e aos objetos de extensão de resultado.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

> **Por que esta etapa importa** – Importar os namespaces corretos evita erros de compilação e disponibiliza a superfície da API para a lógica de decodificação subsequente.

## Etapa 2: Especificar o caminho da imagem

Defina o caminho completo ou relativo para a imagem do código de barras. Manter o caminho em uma variável torna o código reutilizável para diferentes imagens.

```csharp
// Step 2: Specify the path to the image that contains a Macro PDF417 barcode
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

> **Dica:** Use `Path.Combine` se você montar o caminho a partir de várias partes; ele trata os separadores de diretório em diferentes sistemas operacionais.

## Etapa 3: Criar um `BarCodeReader` configurado para decodificação Macro PDF417

Instancie `BarCodeReader` com o caminho da imagem e a flag `DecodeType.MacroPdf417`. Isso indica à biblioteca que ela deve procurar especificamente por símbolos Macro PDF417.

```csharp
// Step 3: Create a BarCodeReader configured for MacroPdf417 decoding
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
```

> **Por que esta etapa importa** – Selecionar o `DecodeType` adequado melhora o desempenho porque o motor ignora formatos de código de barras não relacionados.

## Etapa 4: Ler todos os códigos de barras e exibir informações macro

Percorra cada `BarCodeResult` retornado por `reader.ReadBarCodes()`. O objeto de resultado contém campos genéricos (`CodeTypeName`, `CodeText`) e extensões específicas do Macro PDF417 (`MacroPdf417FileID`, `MacroPdf417SegmentID`, `MacroPdf417SegmentsCount`).

```csharp
    // Step 4: Read all barcodes in the image and display the most relevant macro information
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Code Type : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // Macro PDF417 specific fields
        Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment ID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Segments  : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
    }
}
```

### O que cada linha faz

| Linha | Explicação |
|------|-------------|
| `result.CodeTypeName` | Nome legível do tipo de código de barras detectado (ex.: “MacroPdf417”). |
| `result.CodeText` | Os dados brutos codificados no código de barras. |
| `result.Extended.Pdf417.MacroPdf417FileID` | Identificador que une todos os segmentos de um documento macro PDF417. |
| `result.Extended.Pdf417.MacroPdf417SegmentID` | Índice do segmento atual dentro do documento completo. |
| `result.Extended.Pdf417.MacroPdf417SegmentsCount` | Número total de segmentos esperados para o documento. |

> **Dica de especialista:** Armazene os campos macro em um banco de dados se precisar remontar o documento completo mais tarde. O `File ID` permite agrupar segmentos pertencentes à mesma origem.

## Etapa 5: Executar o programa e verificar a saída

Compile e execute a aplicação de console:

```bash
dotnet run
```

A saída típica no console se parece com isto:

```
Code Type : MacroPdf417
Code Text : 0123456789ABCD
File ID   : 101
Segment ID: 1
Segments  : 3
```

Se a imagem contiver múltiplos símbolos Macro PDF417, o loop imprimirá cada um sequencialmente.

### Tratamento de casos de borda comuns

| Situação | Manipulação recomendada |
|-----------|----------------------|
| **Nenhum código de barras encontrado** | Verifique `reader.ReadBarCodes().Any()` antes do loop e exiba uma mensagem amigável. |
| **Imagem corrompida** | Envolva a criação do `BarCodeReader` em um bloco `try/catch` para `BarCodeException`. |
| **Múltiplos formatos de código de barras** | Use `DecodeType.AllSupported` e filtre os resultados por `result.CodeTypeName == "MacroPdf417"`. |
| **Imagens grandes** | Reduza a escala da imagem antes da decodificação para melhorar o desempenho; a biblioteca aceita um objeto `Bitmap`. |

## Código‑fonte completo

Abaixo está o programa completo e autocontido. Copie‑o para `Program.cs` de um novo projeto de console e substitua `YOUR_DIRECTORY/ExtPDF417Meta.png` pelo caminho real da sua imagem.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417Decoder
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Specify the path to the image that contains a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Step 3: Create a BarCodeReader configured for MacroPdf417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Step 4: Read all barcodes in the image and display the most relevant macro information
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // Macro PDF417 specific fields
                    Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments  : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                }
            }
        }
    }
}
```

## Conclusão

Agora você sabe **como decodificar pdf417** em C# e como **read barcode image c#** usando Aspose.BarCode. O tutorial guiou você pela configuração do projeto, carregamento da imagem, configuração do leitor, extração de resultados e tratamento de casos de borda. Com essa base, você pode integrar a decodificação PDF417 em sistemas de inventário, validadores de ingressos ou qualquer fluxo de trabalho que dependa de dados macro‑codificados.

### Próximos passos

* Explore outros formatos de código de barras alterando `DecodeType` (ex.: `DecodeType.QR`, `DecodeType.Code128`).  
* Combine múltiplos segmentos decodificados para reconstruir o documento original.  
* Use a classe `BarCodeGenerator` para criar códigos de barras PDF417 de teste on‑the‑fly.  

Sinta‑se à vontade para experimentar diferentes fontes de imagem, ajustar a saída do console ou incorporar a lógica de decodificação em uma API web para processamento em tempo real. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to decode PDF417 in C# with a barcode reader example](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/)
- [How to generate PDF417 barcodes in C# with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [How to read barcode from image c# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}