---
category: general
date: 2026-10-15
description: Como ler imagens de código de barras em C# rapidamente usando BarCodeReader.
  Aprenda a ler múltiplos códigos de barras e veja um exemplo de leitor de código
  de barras em C# que funciona com Macro‑PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode
- read multiple barcodes
- c# barcode reader example
- Macro‑PDF417 decoding
- barcode metadata extraction
language: pt
lastmod: 2026-10-15
og_description: Como ler código de barras em C# usando BarCodeReader. Este tutorial
  mostra um exemplo completo de leitor de código de barras em C# que lida com múltiplos
  códigos de barras e extrai metadados Macro‑PDF417.
og_image_alt: Screenshot showing how to read barcode with C# BarCodeReader
og_title: Como ler código de barras em C# – exemplo passo a passo
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  headline: How to read barcode images in C# – full example guide
  type: TechArticle
- description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  name: How to read barcode images in C# – full example guide
  steps:
  - name: Initialise the `BarCodeReader`
    text: '```csharp using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Read all barcodes present in the image
    text: '```csharp // Step 2: Read all barcodes in the image BarCodeResult[] results
      = reader.ReadBarCodes(); ```'
  - name: Display basic barcode details
    text: '```csharp foreach (BarCodeResult result in results) { Console.WriteLine($"CodeType:
      {result.CodeTypeName}"); Console.WriteLine($"CodeText: {result.CodeText}");
      ```'
  - name: Retrieve and show Macro‑PDF417 specific metadata
    text: '```csharp // Macro‑PDF417 extended data Console.WriteLine($"FileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Segment: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Count: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
      Console.WriteLine($"FileName'
  - name: Full runnable program
    text: Below is a self‑contained console application that puts all four steps together.
      Copy the code into a new `.cs` file, adjust the `imagePath`, and run `dotnet
      run`.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Como ler imagens de códigos de barras em C# – guia completo com exemplo
url: /pt/net/one-dimensional-barcode-types/how-to-read-barcode-images-in-c-full-example-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como ler imagens de código de barras em C# – guia completo de exemplo

Se você precisa **como ler código de barras** a partir de uma imagem em uma aplicação .NET, este guia fornece uma solução pronta‑para‑executar. Você verá um **exemplo de leitor de código de barras c#** completo que funciona com símbolos Macro‑PDF417 e pode **ler múltiplos códigos de barras** de uma única imagem.

A leitura de códigos de barras é uma necessidade comum para sistemas de inventário, validação de ingressos e processamento de documentos. Ao final deste tutorial você será capaz de:

* Inicializar o `BarCodeReader` para qualquer formato suportado.  
* Extrair informações básicas como tipo de código e texto decodificado.  
* Recuperar metadados específicos do Macro‑PDF417 (ID do arquivo, segmento, checksum, …).  
* Manipular imagens que contêm vários códigos de barras sem código adicional.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou posterior instalado.  
* Um ambiente de desenvolvimento (Visual Studio 2022, VS Code ou Rider).  
* O pacote NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`) – ele fornece a classe `BarCodeReader` usada no exemplo.  
* Um arquivo de imagem que contém um código de barras Macro‑PDF417 (por exemplo, `MacroPdf417.png`).  

Você pode instalar o pacote NuGet com o seguinte comando:

```bash
dotnet add package Aspose.BarCode
```

## Como ler código de barras com BarCodeReader em C#

O núcleo da solução está dividido em quatro passos concisos. Cada passo é envolvido em um bloco `using` para garantir que recursos não gerenciados sejam liberados rapidamente.

### Etapa 1: Inicializar o `BarCodeReader`

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Path to the image that contains the Macro‑PDF417 barcode(s)
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for the specific DecodeType
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The remaining steps are inside this block
}
```

**Por que isso importa:**  
`BarCodeReader` aceita um caminho de arquivo e um `DecodeType`. Especificar `DecodeType.MacroPdf417` indica à biblioteca que procure apenas símbolos Macro‑PDF417, o que melhora a velocidade de detecção e reduz falsos positivos.

### Etapa 2: Ler todos os códigos de barras presentes na imagem

```csharp
    // Step 2: Read all barcodes in the image
    BarCodeResult[] results = reader.ReadBarCodes();
```

**Por que isso importa:**  
O método `ReadBarCodes()` retorna um array que pode conter um ou vários objetos `BarCodeResult`. Este é o ponto onde a capacidade de **ler múltiplos códigos de barras** se destaca – você não precisa de um loop separado para cada código de barras possível.

### Etapa 3: Exibir detalhes básicos do código de barras

```csharp
    foreach (BarCodeResult result in results)
    {
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

**Por que isso importa:**  
`CodeTypeName` informa qual simbologia foi detectada (por exemplo, “MacroPDF417”), enquanto `CodeText` contém a carga decodificada. Esses dois campos são os mais usados na lógica subsequente.

### Etapa 4: Recuperar e exibir metadados específicos do Macro‑PDF417

```csharp
        // Macro‑PDF417 extended data
        Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
        Console.WriteLine(new string('-', 40));
    }
}
```

**Por que isso importa:**  
Macro‑PDF417 estende o formato PDF417 regular com metadados a nível de documento. Acessar a propriedade `Extended.Pdf417` fornece tudo que você precisa para reconstruir o arquivo original, validar a integridade ou encaminhar os dados ao destinatário correto.

### Programa completo executável

Abaixo está um aplicativo console autônomo que reúne as quatro etapas. Copie o código para um novo arquivo `.cs`, ajuste o `imagePath` e execute `dotnet run`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // 1️⃣ Initialise the BarCodeReader for Macro‑PDF417 images
            // ------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // ------------------------------------------------------------
                // 2️⃣ Read all barcodes present in the image
                // ------------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes were detected.");
                    return;
                }

                // ------------------------------------------------------------
                // 3️⃣ Iterate over each result – this is where we **read multiple barcodes**
                // ------------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // ------------------------------------------------------------
                    // 4️⃣ Extract Macro‑PDF417 metadata (c# barcode reader example)
                    // ------------------------------------------------------------
                    Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

#### Saída esperada no console

```
CodeType: MacroPDF417
CodeText: https://example.com/document
FileID:    12
Segment:   3
Count:     5
FileName:  report.pdf
Checksum:  0x1A2B3C4D
FileSize:  1048576
Time:      2024-08-15T14:23:00Z
Addressee: John Doe
Sender:    Acme Corp.
Terminator:END
----------------------------------------
```

Se a imagem contiver mais de um símbolo Macro‑PDF417, o programa imprime um bloco separado para cada código de barras, demonstrando a capacidade de **ler múltiplos códigos de barras** sem nenhum código extra.

## Lidando com casos de borda comuns

| Situação | O que fazer | Razão |
|-----------|------------|--------|
| **Arquivo não encontrado** | Envolva a construção do `BarCodeReader` em um bloco `try/catch (FileNotFoundException)` e exiba uma mensagem amigável. | Impede que a aplicação trave e informa ao usuário sobre o recurso ausente. |
| **Nenhum código de barras detectado** | Verifique `results.Length == 0` (conforme mostrado no programa completo) e trate‑o de forma elegante. | Fornece feedback claro quando a imagem não contém nenhuma simbologia suportada. |
| **Tipo de código de barras diferente** | Altere `DecodeType.MacroPdf417` para `DecodeType.AllSupportedTypes` ou outro valor específico do enum. | Permite que a mesma base de código funcione com QR, Code128, DataMatrix, etc., enquanto ainda suporta **ler múltiplos códigos de barras**. |
| **Imagens grandes** | Defina `reader.AutoSize = true` ou reduza a escala da imagem antes de enviá‑la ao leitor. | Melhora o desempenho e reduz a pressão de memória no CLR. |
| **Uso thread‑safe** | Crie uma instância separada de `BarCodeReader` por thread; a classe não é thread‑safe. | Evita condições de corrida em scanners ou serviços web multithread. |

## Dicas profissionais para código de produção

* **Dispose cedo:** A instrução `using` garante que recursos nativos (por exemplo, buffers de imagem) sejam liberados rapidamente. Em serviços de longa duração, libere o leitor assim que terminar de processar cada imagem.  
* **Processamento em lote**

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Ler código de barras a partir de imagem C# – guia completo com Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Como criar código de barras macro PDF417 em C# usando Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Como ler PDF417 em C# – Exemplo completo de leitor de código de barras](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}