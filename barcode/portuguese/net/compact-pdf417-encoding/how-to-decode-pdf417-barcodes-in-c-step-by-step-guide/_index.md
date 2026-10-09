---
category: general
date: 2026-09-29
description: Como decodificar códigos de barras PDF417 em C# usando Aspose.BarCode.
  Aprenda um exemplo de leitor de código de barras que mostra como ler imagens de
  códigos de barras e extrair dados macro.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- how to read barcode
- barcode reader example
- read pdf417 barcode
- read barcode image c#
language: pt
lastmod: 2026-09-29
og_description: Como decodificar códigos de barras PDF417 em C# com Aspose.BarCode.
  Este guia mostra um exemplo pronto‑para‑executar de leitor de código de barras para
  ler imagens de códigos de barras.
og_image_alt: Screenshot of C# code decoding a PDF417 macro barcode and printing its
  fields
og_title: Como decodificar códigos de barras PDF417 em C# – exemplo completo de leitor
  de códigos de barras
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to decode PDF417 barcodes in C# using Aspose.BarCode. Learn a barcode
    reader example that shows how to read barcode images and extract macro data.
  headline: How to decode PDF417 barcodes in C# – step‑by‑step guide
  type: TechArticle
- description: How to decode PDF417 barcodes in C# using Aspose.BarCode. Learn a barcode
    reader example that shows how to read barcode images and extract macro data.
  name: How to decode PDF417 barcodes in C# – step‑by‑step guide
  steps:
  - name: Expected console output
    text: '``` Pdf417MacroFileID: 12345 Pdf417MacroSegmentID: 1 Pdf417MacroFileName:
      Invoice_2026_09_29.pdf ```'
  - name: No barcode detected
    text: '```csharp var results = reader.ReadBarCodes().ToList(); if (!results.Any())
      { Console.WriteLine("No PDF417 barcode found in the image."); return; } ```'
  - name: Unsupported image format
    text: Aspose.BarCode supports PNG, JPEG, BMP, TIFF, and GIF. Attempting to read
      a RAW or WebP file throws `ArgumentException`. Convert the image to a supported
      format before feeding it to the reader.
  - name: Large macro files
    text: Macro‑PDF417 can span many segments. To reconstruct the original file you
      must collect all segments (ordered by `MacroPdf417SegmentID`) and concatenate
      their payloads. The example above only prints individual segment metadata; a
      production implementation would store each segment in a dictionary, the
  - name: Performance tip
    text: If you process thousands of images, reuse a single `BarCodeReader` instance
      with the `SetImage` method instead of creating a new object for each file. This
      reduces memory allocations and speeds up decoding.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- Aspose.BarCode
title: Como decodificar códigos de barras PDF417 em C# – guia passo a passo
url: /pt/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como decodificar códigos de barras PDF417 em C# – guia passo a passo

Se você precisa **como decodificar PDF417** códigos de barras em C#, este tutorial oferece uma solução completa e executável. Você verá um **exemplo de leitor de código de barras** que demonstra **como ler código de barras** em imagens, extrai informações macro e imprime os resultados no console.

Decodificar PDF417 é comum ao processar etiquetas de envio, ingressos ou documentos de identidade governamentais. Ao final deste guia você será capaz de ler uma imagem de código de barras PDF417, acessar seus campos macro e lidar com casos de borda típicos. Nenhuma documentação externa é necessária – tudo o que você precisa está incluído.

## O que você aprenderá

- Instalar a biblioteca Aspose.BarCode para .NET  
- Criar um `BarCodeReader` que **leia dados de código de barras PDF417** de um arquivo PNG ou JPEG  
- Iterar sobre objetos `BarCodeResult` e recuperar propriedades macro‑PDF417  
- Solucionar problemas comuns, como formatos de imagem não suportados ou dados macro ausentes  

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

| Requisito | Motivo |
|-----------|--------|
| .NET 6.0 SDK ou posterior | Fornece o runtime para projetos C# |
| Visual Studio 2022 (ou qualquer IDE que suporte .NET) | Facilita a criação e depuração de projetos |
| Pacote NuGet **Aspose.BarCode** | Disponibiliza a classe `BarCodeReader` usada no exemplo |
| Uma imagem macro PDF417 (ex.: `ExtPDF417Meta.png`) | O arquivo fonte que o leitor decodificará |

> **Dica profissional:** Se você não tem uma imagem PDF417, pode gerar uma com a demonstração online gratuita do Aspose.BarCode ou escanear uma etiqueta real.

## Passo 1: Instalar Aspose.BarCode via NuGet

Abra um terminal na pasta da sua solução e execute:

```bash
dotnet add package Aspose.BarCode
```

O comando adiciona a versão estável mais recente do Aspose.BarCode ao seu projeto e atualiza o arquivo `.csproj`. Esta biblioteca implementa a funcionalidade **read barcode image C#** para dezenas de simbologias, incluindo PDF417.

## Passo 2: Criar um BarCodeReader para **decodificar PDF417**

O núcleo do processo de **como ler código de barras** é o `BarCodeReader`. Você deve informar ao leitor tanto o caminho do arquivo quanto a simbologia esperada (`DecodeType.MacroPdf417`). Fornecer o `DecodeType` correto melhora a velocidade e a precisão da detecção.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Adjust the path to point at your PDF417 macro image
string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

// The reader is disposable; wrap it in a using block to release resources automatically.
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Step 3 is inside this block.
}
```

**Por que isso importa:**  
- `DecodeType.MacroPdf417` indica ao motor que ele deve procurar campos macro‑PDF417 (ID do arquivo, ID do segmento, etc.).  
- Usar `using` garante que o fluxo de imagem subjacente seja fechado, evitando problemas de bloqueio de arquivo no Windows.

## Passo 3: Iterar sobre códigos de barras detectados

Uma única imagem pode conter múltiplos códigos de barras. O método `ReadBarCodes()` devolve um `IEnumerable<BarCodeResult>` que pode ser percorrido em um laço.

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside the loop we will extract macro data.
}
```

Se a imagem não contiver símbolos PDF417, o corpo do laço nunca será executado, e você pode tratar esse caso após o laço (veja a seção “Tratamento de erros”).

## Passo 4: Acessar campos macro PDF417

Cada `BarCodeResult` expõe uma propriedade `Extended` com um sub‑objeto `Pdf417`. Os campos macro que você mais costuma precisar são:

| Propriedade | Significado |
|-------------|-------------|
| `MacroPdf417FileID` | Identificador de todo o arquivo macro PDF417 |
| `MacroPdf417SegmentID` | Número de sequência do segmento atual |
| `MacroPdf417FileName` | Nome de arquivo opcional armazenado no macro |

Aqui está o código completo que imprime esses valores:

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Macro fields are nullable; use the null‑conditional operator to avoid exceptions.
    Console.WriteLine($"Pdf417MacroFileID:   {result.Extended?.Pdf417?.MacroPdf417FileID}");
    Console.WriteLine($"Pdf417MacroSegmentID:{result.Extended?.Pdf417?.MacroPdf417SegmentID}");
    Console.WriteLine($"Pdf417MacroFileName: {result.Extended?.Pdf417?.MacroPdf417FileName}");

    // You can also read other macro properties, such as:
    // result.Extended.Pdf417.MacroPdf417Addressee
    // result.Extended.Pdf417.MacroPdf417Sender
}
```

### Saída esperada no console

```
Pdf417MacroFileID:    12345
Pdf417MacroSegmentID: 1
Pdf417MacroFileName:  Invoice_2026_09_29.pdf
```

Se os campos macro não estiverem presentes, a saída mostrará linhas em branco porque as propriedades são `null`. Isso é normal para códigos de barras PDF417 que não são macro.

## Passo 5: Lidar com armadilhas comuns (tratamento de erros & casos de borda)

### Nenhum código de barras detectado

```csharp
var results = reader.ReadBarCodes().ToList();
if (!results.Any())
{
    Console.WriteLine("No PDF417 barcode found in the image.");
    return;
}
```

### Formato de imagem não suportado

Aspose.BarCode suporta PNG, JPEG, BMP, TIFF e GIF. Tentar ler um arquivo RAW ou WebP lança `ArgumentException`. Converta a imagem para um formato suportado antes de enviá‑la ao leitor.

### Arquivos macro grandes

Macro‑PDF417 pode abranger muitos segmentos. Para reconstruir o arquivo original, você deve coletar todos os segmentos (ordenados por `MacroPdf417SegmentID`) e concatenar seus payloads. O exemplo acima apenas imprime metadados de cada segmento; uma implementação de produção armazenaria cada segmento em um dicionário e os reuniria após a leitura completa.

### Dica de desempenho

Se você processar milhares de imagens, reutilize uma única instância de `BarCodeReader` com o método `SetImage` em vez de criar um novo objeto para cada arquivo. Isso reduz alocações de memória e acelera a decodificação.

```csharp
using (BarCodeReader reader = new BarCodeReader(null, DecodeType.MacroPdf417))
{
    foreach (string file in Directory.GetFiles(@"YOUR_DIRECTORY", "*.png"))
    {
        reader.SetImage(file);
        // read barcodes as shown earlier
    }
}
```

## Exemplo completo em funcionamento

Copie o programa a seguir para um novo projeto Console App (`dotnet new console`). Ele inclui todas as etapas, tratamento de erros e comentários.

```csharp
// Program.cs
using System;
using System.IO;
using System.Linq;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the PDF417 macro image – update to your actual location.
        string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Verify the file exists before attempting to read.
        if (!File.Exists(imagePath))
        {
            Console.WriteLine($"File not found: {imagePath}");
            return;
        }

        // Initialize the reader for Macro PDF417.
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            var results = reader.ReadBarCodes().ToList();

            if (!results.Any())
            {
                Console.WriteLine("No PDF417 barcode detected in the image.");
                return;
            }

            foreach (BarCodeResult result in results)
            {
                // Print macro information safely.
                Console.WriteLine($"Pdf417MacroFileID:   {result.Extended?.Pdf417?.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID:{result.Extended?.Pdf417?.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended?.Pdf417?.MacroPdf417FileName}");
                Console.WriteLine(); // blank line for readability
            }
        }
    }
}
```

**Executando o programa**

```bash
dotnet run
```

Você deverá ver os campos macro impressos no console, correspondendo à saída esperada mostrada anteriormente.

## Conclusão

Neste tutorial você aprendeu **como decodificar PDF417** códigos de barras em C# com um conciso **exemplo de leitor de código de barras**. Ao instalar o Aspose.BarCode, criar um `BarCodeReader` para `MacroPdf417`, iterar sobre os resultados e acessar as propriedades macro `Extended.Pdf417`, você pode ler de forma confiável dados de **código de barras PDF417** de qualquer imagem suportada.  

A partir daqui você pode:

- Implementar a agregação de segmentos para reconstruir arquivos macro de múltiplos segmentos.  
- Explorar outras simbologias (QR, Code128) usando o mesmo padrão `BarCodeReader`.  
- Integrar o decodificador em uma API web que processe imagens enviadas (`read barcode image C#` em um contexto de serviço).  

Sinta‑se à vontade para experimentar diferentes fontes de imagem, estratégias de tratamento de erros e otimizações de desempenho. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como ler PDF417 em C# – guia completo de leitor de código de barras](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/)
- [Como gerar código de barras PDF417 com Aspose – Guia completo](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Como criar código de barras PDF417 com Aspose – Guia passo a passo completo](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}