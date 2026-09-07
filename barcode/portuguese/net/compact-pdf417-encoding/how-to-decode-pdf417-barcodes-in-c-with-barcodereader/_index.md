---
category: general
date: 2026-09-07
description: Aprenda a decodificar códigos de barras PDF417 em C# usando o BarCodeReader.
  Este guia passo a passo também explica como ler dados PDF417 de forma eficiente.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- how to read pdf417
- PDF417 barcode decoding C#
- MacroPdf417 extraction C#
- barcode reader BarCodeReader
- GroupDocs.Barcode tutorial
language: pt
lastmod: 2026-09-07
og_description: Como decodificar códigos de barras PDF417 em C# usando o BarCodeReader.
  Siga este tutorial para aprender a ler dados PDF417 e extrair campos MacroPdf417.
og_image_alt: Screenshot of C# code reading PDF417 barcode fields in the console
og_title: Como decodificar códigos de barras PDF417 em C# – guia completo
schemas:
- author: GroupDocs
  dateModified: '2026-09-07'
  description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  headline: How to decode PDF417 barcodes in C# with BarCodeReader
  type: TechArticle
- description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  name: How to decode PDF417 barcodes in C# with BarCodeReader
  steps:
  - name: Prepare the project and import namespaces
    text: '```csharp using System; using GroupDocs.Barcode; using GroupDocs.Barcode.Common;
      ```'
  - name: Define the image path
    text: '```csharp // Replace with the absolute or relative path to your barcode
      image string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png"; ```'
  - name: Initialize the barcode reader for MacroPdf417 decoding
    text: '```csharp using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
      { // Step 4 runs inside this block } ```'
  - name: Read every barcode found in the image
    text: '```csharp foreach (BarCodeResult result in reader.ReadBarCodes()) { //
      Step 5 extracts the MacroPdf417 fields } ```'
  - name: Retrieve and display Macro PDF417 specific data
    text: '```csharp Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
      Console.WriteLine'
  - name: Full runnable example
    text: 'Combine the snippets above into a single `Program.cs` file:'
  type: HowTo
tags:
- PDF417
- C#
- barcode decoding
title: Como decodificar códigos de barras PDF417 em C# com BarCodeReader
url: /pt/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-with-barcodereader/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como decodificar códigos de barras PDF417 em C# com BarCodeReader

Se você precisa **como decodificar PDF417** códigos de barras em uma aplicação .NET, este guia o conduz por todo o processo. Você também descobrirá **como ler PDF417** dados como identificadores de arquivo e segmento MacroPdf417, tudo com algumas linhas de C#.

Decodificar PDF417 é comum ao trabalhar com bilhetes de transporte, carteiras de motorista ou etiquetas de envio. Ao final deste tutorial você terá um programa de console executável que imprime cada campo MacroPdf417 exposto pelo SDK GroupDocs.Barcode.

## Pré-requisitos

* .NET 6.0 SDK ou posterior (o código compila com .NET Core e .NET Framework)
* Visual Studio 2022 ou qualquer IDE que suporte C#
* O pacote NuGet **GroupDocs.Barcode** (`GroupDocs.Barcode` ≥ 23.3)
* Um arquivo de imagem que contém um código de barras Macro PDF417 (ex.: `ExtPDF417Meta.png`)

> **Dica profissional:** Instale o pacote via a CLI:  
> `dotnet add package GroupDocs.Barcode --version 23.3`

## Como decodificar códigos de barras PDF417 em C#

As seções a seguir dividem a solução em etapas lógicas. Cada etapa inclui o código exato que você precisa e uma breve explicação do porquê é importante.

### Etapa 1: Prepare o projeto e importe os namespaces

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;
```

*Por quê?*  
`GroupDocs.Barcode` fornece a classe `BarCodeReader`, enquanto `GroupDocs.Barcode.Common` contém a enumeração `DecodeType` necessária para a decodificação de PDF417.

### Etapa 2: Defina o caminho da imagem

```csharp
// Replace with the absolute or relative path to your barcode image
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

*Por quê?*  
O leitor funciona com qualquer formato de imagem suportado pelo .NET (`.png`, `.jpg`, `.bmp`). Fornecer o caminho correto garante que o SDK possa localizar o arquivo.

### Etapa 3: Inicialize o leitor de códigos de barras para decodificação MacroPdf417

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Step 4 runs inside this block
}
```

*Por quê?*  
`DecodeType.MacroPdf417` indica ao SDK que procure o formato Macro PDF417 estendido, que contém metadados adicionais como IDs de arquivo e segmento. Usar a instrução `using` garante que recursos não gerenciados sejam liberados rapidamente.

### Etapa 4: Leia todos os códigos de barras encontrados na imagem

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Step 5 extracts the MacroPdf417 fields
}
```

*Por quê?*  
Uma imagem pode conter múltiplos códigos de barras. O método `ReadBarCodes()` retorna uma coleção, permitindo que você processe cada um individualmente.

### Etapa 5: Recupere e exiba os dados específicos do Macro PDF417

```csharp
Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
```

*Por quê?*  
O objeto `Extended.Pdf417` expõe todos os campos Macro PDF417 definidos pela especificação. Imprimi‑los permite verificar que a operação de decodificação foi bem‑sucedida e fornece os dados necessários para o processamento subsequente.

### Exemplo completo executável

Combine os trechos acima em um único arquivo `Program.cs`:

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // 1️⃣ Path to the image that contains the Macro PDF417 barcode
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 2️⃣ Create a reader configured for MacroPdf417 decoding
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 3️⃣ Iterate over all detected barcodes
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // 4️⃣ Output Macro PDF417 metadata
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
                Console.WriteLine(); // Blank line for readability
            }
        }
    }
}
```

**Saída esperada no console** (os valores variarão conforme o conteúdo do código de barras):

```
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentCount: 3
Pdf417MacroFileName: shipment_data
Pdf417MacroTimestamp: 2024-07-15T10:23:45Z
```

Se a imagem não contiver um código de barras Macro PDF417, a coleção `ReadBarCodes()` ficará vazia e nada será impresso.

## Variações comuns e casos de borda

| Situação | Como adaptar o código |
|-----------|----------------------|
| **Standard (non‑macro) PDF417** | Altere `DecodeType.MacroPdf417` para `DecodeType.Pdf417`. O objeto `Extended.Pdf417` será `null`, portanto proteja contra referências nulas. |
| **Multiple images** | Envolva a inicialização do leitor em um loop `foreach (var path in imagePaths)`. |
| **Large images** | Defina `reader.Options.ImageProcessingOptions.MaxImageDimension = 2000;` para limitar o uso de memória. |
| **Performance‑critical batch** | Reutilize uma única instância de `BarCodeReader` com `reader.SetImage(path)` em vez de criar um novo objeto para cada arquivo. |

## Lista de verificação de solução de problemas

* **Sem saída:** Verifique se `imagePath` aponta para um arquivo válido e se a imagem realmente contém um código de barras PDF417. |
* **`Extended.Pdf417` nulo:** Você provavelmente usou `DecodeType.Pdf417` em vez de `MacroPdf417`. |
* **Exceção `FileNotFoundException`:** Certifique‑se de que o diretório de trabalho corresponde ao caminho ou use um caminho absoluto. |
* **Pontuação de confiança baixa:** Aumente a qualidade da imagem ou ajuste as configurações `reader.Options.Quality`.

## Conclusão

Agora você sabe **como decodificar PDF417** códigos de barras em C# e **como ler PDF417** metadados como IDs de arquivo Macro, IDs de segmento e timestamps. O exemplo completo demonstra a inicialização do `BarCodeReader`, a seleção do tipo de decodificação correto, a iteração sobre os resultados e a extração de todos os campos MacroPdf417 disponíveis.

A partir daqui você pode:

* Integrar os dados extraídos em um sistema de logística ou validação de bilhetes.
* Expandir o aplicativo de console para gravar resultados em um banco de dados ou arquivo JSON.
* Explorar outros formatos de código de barras suportados pelo GroupDocs.Barcode (QR, DataMatrix, Code128, etc.) trocando a enumeração `DecodeType`.

Feliz codificação, e sinta‑se à vontade para experimentar diferentes imagens e configurações de códigos de barras para dominar a decodificação PDF417 em seus projetos .NET!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como ler PDF417 em C# – Guia completo passo a passo](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [Como ler PDF417 em C# – Exemplo completo de leitor de código de barras](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Como gerar código de barras PDF417 – Guia completo de programação](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}