---
category: general
date: 2026-09-26
description: Aprenda a decodificar PDF417 em C# com um exemplo passo a passo de leitor
  de código de barras. Este guia mostra como ler imagens de código de barras em C#
  usando Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcode image c#
- c# barcode reader example
language: pt
lastmod: 2026-09-26
og_description: Como decodificar PDF417 em C# rapidamente. Siga este exemplo de leitor
  de código de barras para ler a imagem do código de barras em C# com Aspose.BarCode
  e extrair os detalhes da macro.
og_image_alt: Screenshot showing how to decode PDF417 in C# using Aspose.BarCode
og_title: Como decodificar PDF417 em C# – guia completo do leitor de códigos de barras
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to decode PDF417 in C# with a step‑by‑step barcode reader
    example. This guide shows you how to read barcode image C# using Aspose.BarCode.
  headline: How to decode PDF417 in C# – barcode reader example
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Como decodificar PDF417 em C# – exemplo de leitor de código de barras
url: /pt/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como decodificar PDF417 em C# – exemplo de leitor de código de barras

Se você precisa **como decodificar PDF417** em uma aplicação .NET, este tutorial fornece uma solução completa e pronta‑para‑executar. Você verá como ler uma imagem de código de barras em C# usando a biblioteca Aspose.BarCode, recuperar as informações macro estendidas do PDF417 e exibir cada campo relevante.

Decodificar PDF417 não se limita a texto simples; o formato pode transportar dados de segmentação de arquivos, timestamps e checksums. Este guia orienta você em cada etapa, explica por que o código está estruturado da maneira que está e destaca armadilhas comuns que você pode encontrar ao implementar um exemplo de leitor de código de barras em C#.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* SDK .NET 6.0 (ou posterior) instalado  
* Visual Studio 2022 (ou qualquer IDE compatível com C#)  
* Pacote NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`)  
* Uma imagem de Macro PDF417 de exemplo (por exemplo, `ExtPDF417Meta.png`)

Esses requisitos garantem que o código compile e execute sem configuração adicional.

## Etapa 1: Instalar o pacote NuGet Aspose.BarCode

A primeira etapa em qualquer projeto **read barcode image C#** é adicionar a biblioteca de código de barras. Abra o terminal na pasta da sua solução e execute:

```bash
dotnet add package Aspose.BarCode
```

O pacote fornece `BarCodeReader`, `DecodeType` e a propriedade `Extended` usada para acessar os dados macro. Instalá‑lo uma vez torna as classes disponíveis em todo o seu projeto.

## Etapa 2: Criar um leitor de código de barras para uma imagem Macro PDF417

Agora você pode instanciar `BarCodeReader` com o caminho da imagem e especificar `DecodeType.MacroPdf417`. Isso indica à biblioteca que procure o formato PDF417 estendido que contém informações macro.

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Path to the Macro PDF417 image
string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

// Initialize the reader for Macro PDF417 decoding
using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is ready – next we will extract barcodes.
}
```

**Por que isso importa:**  
`DecodeType.MacroPdf417` ativa o analisador específico de macro. Se você omiti‑lo, o leitor retornará apenas a carga útil de texto simples e ignorará os campos macro que provavelmente são necessários para a reconstrução do arquivo.

## Etapa 3: Ler todos os códigos de barras encontrados na imagem

Uma única imagem pode conter múltiplos símbolos PDF417, especialmente quando os dados são divididos em segmentos. Percorrer `ReadBarCodes()` garante que você capture cada segmento.

```csharp
// Step 3: Iterate over each detected barcode
foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
{
    // Inside the loop we will access both basic and macro data.
}
```

**Por que usar loop:**  
Os dados macro do PDF417 costumam aparecer em vários segmentos. Processar cada `BarCodeResult` assegura que você colete o conjunto completo de campos macro, como `MacroPdf417FileID` e `MacroPdf417SegmentsCount`.

## Etapa 4: Recuperar e exibir os dados básicos do código de barras

O objeto `BarCodeResult` contém o tipo e o texto decodificado. Exibir esses valores ajuda a verificar se o leitor identificou corretamente o símbolo antes de mergulhar nos detalhes macro.

```csharp
Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
Console.WriteLine($"CodeText: {barcodeResult.CodeText}");
```

**Dica:** Se `CodeText` estiver vazio, a imagem pode estar corrompida ou o modo de decodificação está incorreto. Verifique novamente o `DecodeType` usado na inicialização.

## Etapa 5: Extrair as informações macro PDF417 estendidas

Os dados macro ficam em `barcodeResult.Extended.Pdf417`. Cada propriedade corresponde a um campo definido na especificação PDF417.

```csharp
// Step 5: Access macro-specific fields
var macroInfo = barcodeResult.Extended.Pdf417;

Console.WriteLine($"Pdf417MacroFileID: {macroInfo.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {macroInfo.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount: {macroInfo.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName: {macroInfo.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum: {macroInfo.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize: {macroInfo.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp: {macroInfo.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee: {macroInfo.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender: {macroInfo.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator: {macroInfo.MacroPdf417Terminator}");
```

**O que cada campo significa**

| Property | Description |
|----------|-------------|
| `MacroPdf417FileID` | Identificador que agrupa todos os segmentos pertencentes ao mesmo arquivo lógico. |
| `MacroPdf417SegmentID` | Índice do segmento atual (começando em 1). |
| `MacroPdf417SegmentsCount` | Número total de segmentos necessários para reconstruir o arquivo original. |
| `MacroPdf417FileName` | Nome de arquivo opcional incorporado ao macro. |
| `MacroPdf417Checksum` | Checksum CRC‑16 para verificação de integridade. |
| `MacroPdf417FileSize` | Tamanho esperado do arquivo reconstruído (em bytes). |
| `MacroPdf417TimeStamp` | Data‑hora em que o macro foi gerado. |
| `MacroPdf417Addressee` | Identificador opcional do destinatário. |
| `MacroPdf417Sender` | Identificador opcional do remetente. |
| `MacroPdf417Terminator` | Flag terminador; deve ser `true` no último segmento. |

Entender esses campos permite que você reconstrua o arquivo original, valide a integridade dos dados e implemente lógica de negócios personalizada (por exemplo, rejeitar documentos desatualizados).

## Etapa 6: Manipular múltiplos segmentos e reconstruir o arquivo original (avançado)

Quando `MacroPdf417SegmentsCount` for maior que 1, você precisa coletar cada segmento, ordená‑los por `MacroPdf417SegmentID` e concatenar os valores de `CodeText`. Abaixo está uma implementação concisa:

```csharp
// Collect segments in a dictionary keyed by SegmentID
var segments = new SortedDictionary<int, string>();

foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
{
    var macro = result.Extended.Pdf417;
    segments[macro.MacroPdf417SegmentID] = result.CodeText;
}

// Verify that we received all expected segments
int expectedCount = segments.First().Value != null
    ? barcodeReader.ReadBarCodes().First().Extended.Pdf417.MacroPdf417SegmentsCount
    : 0;

if (segments.Count == expectedCount)
{
    // Reconstruct the full payload
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine($"Reconstructed payload ({fullPayload.Length} chars):");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Warning: Expected {expectedCount} segments but received {segments.Count}.");
}
```

**Por que isso importa:**  
Sem ordenação e concatenação, os dados decodificados ficariam incompletos ou corrompidos. O trecho também demonstra programação defensiva ao verificar a contagem de segmentos.

## Etapa 7: Concluir com tratamento de erros e boas práticas

Um **c# barcode reader example** pronto para produção deve antecipar erros de I/O, formatos não suportados e imagens corrompidas.

```csharp
try
{
    // Existing barcode reading code goes here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image file not found: {ex.Message}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode processing error: {ex.Message}");
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Unexpected error: {ex.Message}");
}
```

**Checklist de boas práticas**

* Valide o caminho da imagem antes de criar `BarCodeReader`.  
* Use instruções `using` para garantir a liberação de recursos não gerenciados.  
* Registre os campos macro para trilhas de auditoria—especialmente `MacroPdf417Checksum` e `MacroPdf417TimeStamp`.  
* Ao lidar com arquivos grandes, considere transmitir a carga concatenada para disco em vez de mantê‑la totalmente na memória.

## Saída esperada

Executar o programa completo contra um `ExtPDF417Meta.png` válido produz uma saída semelhante a:

```
CodeType: MacroPdf417
CodeText: <base64‑encoded segment data>
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254312
Pdf417MacroTimeStamp: 2024-03-15T10:23:45Z
Pdf417MacroAddressee: Acme Corp
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: False
...
```

Se os três segmentos estiverem presentes, o bloco de reconstrução imprime a carga completa após a mensagem de verificação.

## Conclusão

Agora você sabe **como decodificar PDF417** em C# usando um exemplo robusto de leitor de código de barras. O tutorial abordou a instalação do Aspose.BarCode, a inicialização de um `BarCodeReader` para Macro PDF417, a iteração sobre múltiplos códigos de barras, a extração de campos macro, a reconstrução de dados segmentados e a implementação de tratamento de erros.  

A partir daqui você pode:

* Integrar o leitor em uma API web que aceita imagens enviadas.  
* Armazenar metadados macro em um banco de dados para fins de auditoria.  
* Expandir a solução para outras simbologias 2‑D trocando `DecodeType` (e

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Read PDF417 barcode in C# – barcode reader example](/barcode/english/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}