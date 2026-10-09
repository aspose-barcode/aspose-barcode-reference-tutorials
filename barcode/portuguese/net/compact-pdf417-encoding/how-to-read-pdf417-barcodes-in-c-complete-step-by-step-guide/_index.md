---
category: general
date: 2026-09-22
description: Aprenda a ler códigos de barras PDF417 em C# com um exemplo completo
  de leitor de códigos de barras. Este tutorial mostra como ler imagens de códigos
  de barras em C# de forma rápida e confiável.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode image c#
- c# barcode reader example
language: pt
lastmod: 2026-09-22
og_description: Como ler códigos de barras PDF417 em C# usando um exemplo conciso
  de leitor de códigos de barras. Siga o guia para decodificar imagens Macro PDF417
  e extrair metadados.
og_image_alt: Screenshot of C# code that reads a PDF417 barcode and prints its metadata
og_title: Como ler códigos de barras PDF417 em C# – exemplo completo de leitor de
  código de barras
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  headline: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  name: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  steps:
  - name: Why each step matters
    text: '1. **Creating the reader with `DecodeType.MacroPdf417`** – Macro PDF417
      is a special variant that can carry file‑level metadata. Specifying the decode
      type ensures the SDK parses those extra fields instead of treating the code
      as a plain PDF417. 2. **Iterating over `ReadBarCodes()`** – An image can '
  - name: Reading a non‑macro PDF417 barcode
    text: If your source images contain regular PDF417 codes (no macro metadata),
      replace `DecodeType.MacroPdf417` with `DecodeType.Pdf417`. The rest of the code
      stays identical, but the `Extended.Pdf417` block will be empty because those
      fields simply don’t exist.
  - name: Handling multi‑segment PDFs
    text: 'Macro PDF417 can split a large document across several barcode segments.
      To reassemble the original file you must:'
  - name: Dealing with corrupted images
    text: '- **Low contrast** – Increase image preprocessing (e.g., histogram equalization)
      before passing it to `BarCodeReader`. - **Rotation** – Use `barcodeReader.SetRotateAngle(90)`
      or enable auto‑rotate if the SDK supports it. - **Partial scans** – Ensure the
      image resolution is at least 300 dpi; otherwis'
  - name: Next steps
    text: '- Explore **read barcode image C#** techniques for other symbologies (QR,
      DataMatrix) using the same `BarCodeReader` API. - Integrate the barcode decoder
      into an ASP.NET Core service to process uploads on the fly. - Experiment with
      image preprocessing libraries (e.g., `OpenCvSharp`) to boost success'
  type: HowTo
tags:
- barcode
- pdf417
- c#
title: Como ler códigos de barras PDF417 em C# – guia completo passo a passo
url: /pt/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como ler códigos de barras PDF417 em C# – guia completo passo a passo

Se você precisa **como ler pdf417** em uma aplicação .NET, este guia mostra o código exato e o raciocínio que você precisa. Ao final das duas primeiras frases, você saberá como ler imagem de código de barras C# usando a popular classe `BarCodeReader`, e terá um exemplo pronto‑para‑executar que extrai cada parte dos metadados Macro PDF417.

Ler códigos de barras PDF417 é uma necessidade comum ao processar etiquetas de envio, cartões de embarque ou documentos seguros. Este tutorial cobre tudo, desde a configuração do leitor até o tratamento de casos extremos, para que você possa integrar a leitura de códigos de barras com confiança.

## O que você vai alcançar

- Decodificar um arquivo de imagem Macro PDF417.
- Imprimir informações básicas do código de barras (tipo e texto).
- Acessar todos os campos estendidos Macro PDF417, como ID do arquivo, contagem de segmentos e timestamp.
- Compreender armadilhas comuns ao trabalhar com códigos PDF417 de múltiplos segmentos.

**Pré-requisitos**

- .NET 6.0 ou posterior (o código também funciona com .NET Framework 4.7+).
- Uma referência ao SDK de código de barras que fornece `BarCodeReader`, `DecodeType` e `BarCodeResult` (ex.: Aspose.BarCode, Dynamsoft ou qualquer biblioteca que exponha a mesma API).
- Um arquivo de imagem (`ExtPDF417Meta.png`) que contém um código de barras Macro PDF417.

> **Dica profissional:** Coloque a imagem em uma pasta relativa à raiz do seu projeto e defina a propriedade **Copy to Output Directory** como *Copy if newer* para que o caminho funcione durante a depuração.

![Como ler código de barras PDF417 usando C#](https://example.com/placeholder-image.png)

## Como ler código de barras PDF417 em C# – o código completo

Abaixo está um programa autônomo que você pode colar em uma aplicação console. Ele cria um leitor de código de barras, itera sobre cada resultado decodificado e imprime tanto os campos padrão quanto os estendidos do Macro PDF417.

```csharp
using System;
using Aspose.BarCode;          // Replace with the namespace of your barcode SDK
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode reader for a Macro PDF417 image
        // The second argument tells the SDK to look specifically for Macro PDF417 codes.
        using var barcodeReader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417);

        // Step 2: Decode all barcodes present in the image
        foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
        {
            // Step 3: Display the basic barcode information
            Console.WriteLine($"CodeType: {result.CodeTypeName}");
            Console.WriteLine($"CodeText: {result.CodeText}");

            // Step 4: Output Macro PDF417 specific metadata
            // All properties are available through the Extended.Pdf417 object.
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
            Console.WriteLine(new string('-', 40));
        }
    }
}
```

### Por que cada passo importa

1. **Criando o leitor com `DecodeType.MacroPdf417`** – Macro PDF417 é uma variante especial que pode transportar metadados a nível de arquivo. Especificar o tipo de decodificação garante que o SDK analise esses campos extras em vez de tratar o código como um PDF417 simples.
2. **Iterando sobre `ReadBarCodes()`** – Uma imagem pode conter mais de um código de barras (ex.: um QR code ao lado de um PDF417). O loop garante que você capture cada resultado.
3. **Imprimindo `CodeTypeName` e `CodeText`** – Estas são as propriedades mais usadas; elas fornecem o nome da simbologia e a carga útil legível por humanos.
4. **Acessando `Extended.Pdf417`** – O objeto `Extended` aparece apenas para tipos de decodificação relacionados ao PDF417. Cada propriedade mapeia diretamente para a especificação Macro PDF417, permitindo reconstruir o arquivo original ou validar a ordem dos segmentos.

## Variações comuns e casos extremos

### Lendo um código de barras PDF417 não‑macro

Se suas imagens de origem contêm códigos PDF417 regulares (sem metadados macro), substitua `DecodeType.MacroPdf417` por `DecodeType.Pdf417`. O restante do código permanece idêntico, mas o bloco `Extended.Pdf417` ficará vazio porque esses campos simplesmente não existem.

### Manipulando PDFs de múltiplos segmentos

Macro PDF417 pode dividir um documento grande em vários segmentos de código de barras. Para remontar o arquivo original, você deve:

1. Coletar o `Pdf417MacroSegmentID` de cada segmento.
2. Ordenar os segmentos pelo seu ID.
3. Verificar se `Pdf417MacroSegmentsCount` corresponde ao número de segmentos recebidos.
4. Concatenar o `CodeText` de cada segmento na ordem.
5. Opcionalmente validar `Pdf417MacroChecksum`.

Abaixo está um trecho conciso que demonstra a lógica de remontagem:

```csharp
var segments = new SortedDictionary<int, string>();
int expectedCount = 0;

foreach (var result in barcodeReader.ReadBarCodes())
{
    int segId = result.Extended.Pdf417.MacroPdf417SegmentID;
    int segCount = result.Extended.Pdf417.MacroPdf417SegmentsCount;
    expectedCount = segCount;               // will be the same for every segment
    segments[segId] = result.CodeText;       // store payload by segment ID
}

// Verify we have all parts
if (segments.Count == expectedCount)
{
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine("Reassembled payload:");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Missing segments: expected {expectedCount}, received {segments.Count}");
}
```

### Lidando com imagens corrompidas

- **Baixo contraste** – Aumente o pré‑processamento da imagem (ex.: equalização de histograma) antes de passá‑la para `BarCodeReader`.
- **Rotação** – Use `barcodeReader.SetRotateAngle(90)` ou habilite a auto‑rotação se o SDK suportar.
- **Digitalizações parciais** – Garanta que a resolução da imagem seja de pelo menos 300 dpi; caso contrário, o SDK pode perder pequenos segmentos.

## Exemplo de leitor de código de barras c# – boas práticas

| Prática | Motivo |
|----------|--------|
| **Descarte o leitor com `using`** | Garante que os recursos nativos sejam liberados rapidamente, evitando vazamentos de memória. |
| **Valide que `result.Extended` não seja nulo** | Alguns SDKs retornam `null` para códigos não‑macro; a verificação evita uma `NullReferenceException`. |
| **Registre o `Pdf417MacroFileID`** | Este identificador é único por arquivo e útil para trilhas de auditoria. |
| **Envolva a decodificação em um try/catch** | Erros de I/O (arquivo ausente) ou formatos não suportados geram exceções que devem ser tratadas de forma elegante. |

```csharp
try
{
    // decoding logic here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image not found: {ex.FileName}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Saída esperada

Executar o programa completo contra um `ExtPDF417Meta.png` formatado corretamente produz uma saída semelhante a:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-08-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

Se a imagem contiver múltiplos segmentos, o loop imprimirá os metadados de cada segmento sequencialmente.

## Conclusão

Agora você sabe **como ler pdf417** códigos de barras em C# e tem um **exemplo de leitor de código de barras c#** que extrai todos os campos Macro PDF417. A solução cobre decodificação básica, extração de metadados, remontagem de múltiplos segmentos e tratamento de erros, fornecendo uma base pronta para produção em qualquer fluxo de trabalho de processamento de documentos.

### Próximos passos

- Explore técnicas de **read barcode image C#** para outras simbologias (QR, DataMatrix) usando a mesma API `BarCodeReader`.
- Integre o decodificador de código de barras em um serviço ASP.NET Core para processar uploads em tempo real.
- Experimente bibliotecas de pré‑processamento de imagem (ex.: `OpenCvSharp`) para aumentar as taxas de sucesso em digitalizações de baixa qualidade.

Feliz codificação, e sinta-se à vontade para adaptar o exemplo ao seu caso de uso específico!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como salvar código de barras em C# – Gerar códigos de barras PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Como ler PDF417 em C# – Guia completo passo a passo](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [Como definir nível de erro em código de barras PDF417 – Guia completo](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}