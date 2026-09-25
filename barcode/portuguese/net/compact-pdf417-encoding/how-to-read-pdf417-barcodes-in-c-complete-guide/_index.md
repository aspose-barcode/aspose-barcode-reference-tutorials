---
category: general
date: 2026-08-22
description: Como ler códigos de barras PDF417 em C# com um guia passo a passo, abordando
  como ler vários códigos de barras de uma imagem e extrair detalhes do MacroPdf417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcodes image c#
language: pt
lastmod: 2026-08-22
og_description: Como ler códigos de barras PDF417 em C# rapidamente. Este tutorial
  mostra como ler vários códigos de barras a partir de uma imagem e recuperar as informações
  estendidas MacroPdf417.
og_image_alt: Developer console displaying MacroPdf417 barcode details extracted by
  C# code
og_title: Como ler códigos de barras PDF417 em C# – tutorial completo de programação
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to read PDF417 barcodes in C# with a step‑by‑step guide, covering
    how to read multiple barcodes from an image and extract MacroPdf417 details.
  headline: How to read PDF417 barcodes in C# – complete guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Como ler códigos de barras PDF417 em C# – guia completo
url: /pt/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como ler códigos de barras PDF417 em C# – guia completo

Se você precisa **como ler PDF417** barras em uma aplicação .NET, este tutorial oferece uma solução pronta‑para‑executar. Você aprenderá a ler vários códigos de barras a partir de uma única imagem, extrair o conjunto completo de dados MacroPdf417 e exibi-lo no console. A abordagem funciona com a biblioteca Aspose.BarCode for .NET e requer apenas algumas linhas de código.

Ler códigos de barras de uma imagem é uma tarefa comum em sistemas de inventário, validação de ingressos e gerenciamento de documentos. Ao final deste guia você será capaz de decodificar qualquer código de barras PDF417 ou MacroPdf417, manipular vários códigos em uma única foto e entender os campos estendidos que o MacroPdf417 fornece.

## Pré‑requisitos

- .NET 6.0 SDK ou posterior (o código também compila com .NET Framework 4.7+)
- Visual Studio 2022 ou qualquer editor C# que você prefira
- Pacote NuGet Aspose.BarCode for .NET (`Install-Package Aspose.BarCode`)
- Uma imagem de exemplo que contenha um código de barras MacroPdf417 (por exemplo, `MacroPdf417.png`)

Nenhuma configuração adicional é necessária; a biblioteca lida com o carregamento e a decodificação da imagem internamente.

## Como ler códigos de barras PDF417 de uma imagem em C#

O núcleo da solução é a classe `BarCodeReader`. Ela abre a imagem, detecta todos os códigos de barras do tipo especificado e devolve uma coleção de objetos `BarCodeResult`. O código a seguir mostra um programa de console completo.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            // Path to the image that contains one or more MacroPdf417 barcodes
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // 1️⃣ Initialize the reader for MacroPdf417 barcodes.
            // DecodeType.MacroPdf417 tells the engine to look for the extended PDF417 format.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Iterate over every barcode found in the image.
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Print basic information.
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // 4️⃣ Access MacroPdf417 extended fields.
                    // The Extended property contains format‑specific data; for PDF417 it is .Pdf417.
                    var macro = result.Extended.Pdf417;

                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Por que cada linha importa

| Etapa | Propósito |
|------|-----------|
| **1️⃣ Initialize** | Cria um `BarCodeReader` vinculado ao arquivo de imagem e restringe a detecção à simbologia MacroPdf417, o que acelera o processamento. |
| **2️⃣ Iterate** | `ReadBarCodes()` devolve **todos** os códigos de barras que correspondem ao tipo solicitado, permitindo que você **leia vários códigos de barras** sem loops extras. |
| **3️⃣ Basic output** | Exibe o genérico `CodeTypeName` e o `CodeText` legível por humanos. Isso é útil para registro ou validação rápida. |
| **4️⃣ Extended data** | MacroPdf417 transporta metadados adicionais (ID do arquivo, contagem de segmentos, timestamps, etc.). O objeto `Extended.Pdf417` expõe cada campo diretamente, para que você possa armazenar ou verificar o pacote de dados completo. |

Executar o programa com uma imagem MacroPdf417 válida produz uma saída no console semelhante ao seguinte:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345678
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x9A3F
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2024-07-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

A saída confirma que a biblioteca leu o código de barras com sucesso, extraiu o texto e forneceu todos os campos MacroPdf417.

## Lendo vários códigos de barras de uma única imagem

Muitos cenários reais colocam vários símbolos PDF417 em um rótulo — pense em um manifesto de envio que contém um código de transportadora, um número de rastreamento e uma declaração aduaneira. O mesmo bloco de código acima já **leu vários códigos de barras** porque `ReadBarCodes()` devolve um enumerável com todas as correspondências. Nenhuma configuração adicional é necessária; basta percorrer os resultados, como demonstrado.

Se você quiser limitar o leitor ao PDF417 padrão (não‑macro) enquanto ainda manipula vários códigos, substitua `DecodeType.MacroPdf417` por `DecodeType.Pdf417`. O restante da lógica permanece inalterado.

## Entendendo os dados estendidos do MacroPdf417

MacroPdf417 é uma extensão da especificação PDF417 regular. Ele divide cargas úteis grandes em múltiplos segmentos e adiciona um pequeno cabeçalho que descreve o arquivo inteiro. Os campos mais relevantes são:

- **MacroPdf417FileID** – um identificador único compartilhado por todos os segmentos do mesmo arquivo.
- **MacroPdf417SegmentID** – o número de sequência do segmento atual.
- **MacroPdf417SegmentsCount** – número total de segmentos esperados.
- **MacroPdf417FileName** – nome de arquivo opcional transmitido com o código de barras.
- **MacroPdf417Checksum** – valor de verificação de erro para o arquivo completo.
- **MacroPdf417FileSize** – tamanho da carga binária original.
- **MacroPdf417TimeStamp** – timestamp ISO‑8601 quando o código de barras foi gerado.
- **MacroPdf417Addressee / Sender** – campos textuais opcionais para roteamento.
- **MacroPdf417Terminator** – indica se este segmento é o final.

Quando você recebe todos os segmentos, pode reconstruir o arquivo original ordenando‑os por `MacroPdf417SegmentID` e concatenando os valores de `CodeText`. Essa lógica é simples de implementar assim que os campos estiverem disponíveis.

## Armadilhas comuns e dicas profissionais

- **A qualidade da imagem importa** – arquivos PNG/JPEG de baixa resolução ou fortemente comprimidos podem causar detecções perdidas. Use pelo menos 300 dpi para códigos de barras impressos.
- **Simbologias mistas** – se a imagem contiver tanto MacroPdf417 quanto PDF417 regular, instancie dois leitores (um para cada `DecodeType`) ou use `DecodeType.AllSupported` e filtre os resultados por `result.CodeTypeName`.
- **Uso de memória** – a instrução `using` descarta o `BarCodeReader` rapidamente, evitando que grandes buffers de imagem permaneçam na memória.
- **Segurança de threads** – `BarCodeReader` não é thread‑safe. Crie uma instância separada por thread se você decodificar imagens em paralelo.
- **Tratamento de erros** – envolva a chamada `ReadBarCodes()` em um bloco try/catch para capturar `BarCodeException` em imagens corrompidas.

## Recapitulação do exemplo completo em funcionamento

Abaixo está o programa completo que você pode copiar para um novo projeto de console. Ele inclui todas as diretivas `using`, uma constante para o caminho da imagem e o padrão de descarte.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    var macro = result.Extended.Pdf417;
                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

Compile com `dotnet build` e execute com `dotnet run`. O console imprime os dados básicos de cada código de barras e o payload completo do MacroPdf417.

## Próximos passos

- **Reconstruct multipart files** – collect all segments, sort by `MacroPdf417SegmentID`, and concatenate `CodeText` to

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar código de barras PDF417 – Codificação Compacta PDF417](/barcode/english/net/compact-pdf417-encoding/)
- [Como ler códigos de barras PDF417 com caracteres turcos em Java](/barcode/english/java/multilingual-support/recognizing-pdf417-turkish-characters/)
- [Como usar Aspose para código de barras PDF417 (Chinês) em Java](/barcode/english/java/multilingual-support/recognizing-pdf417-chinese-characters/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}