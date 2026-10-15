---
category: general
date: 2026-10-12
description: Aprenda como criar um exemplo de código de barras Aspose em C# que gera
  um código de barras MacroPdf417 com metadados completos e o lê de volta usando o
  BarCodeReader.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- macroPdf417 barcode
- barcode metadata
- c# barcode generation
- BarCodeReader
language: pt
lastmod: 2026-10-12
og_description: Exemplo de código de barras Aspose em C# que mostra como gerar um
  código de barras MacroPdf417 com metadados incorporados e lê‑lo de volta usando
  BarCodeReader.
og_image_alt: Screenshot of an Aspose barcode example displaying a MacroPdf417 barcode
  with metadata
og_title: Criar um exemplo de código de barras Aspose com MacroPdf417 em C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn how to create an Aspose barcode example in C# that generates
    a MacroPdf417 barcode with full metadata and reads it back using BarCodeReader.
  headline: How to build an Aspose barcode example with MacroPdf417 in C#
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Barcode
title: Como criar um exemplo de código de barras Aspose com MacroPdf417 em C#
url: /pt/net/compact-pdf417-encoding/how-to-build-an-aspose-barcode-example-with-macropdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar um exemplo de barcode Aspose com MacroPdf417 em C#

Se você precisa de um **aspose barcode example** que cria um código de barras MacroPdf417 e lê seus metadados incorporados, este guia mostra o fluxo de trabalho completo. Você verá como configurar o gerador, incorporar informações ao nível de arquivo, salvar a imagem e, em seguida, decodificar os mesmos dados com `BarCodeReader`.

O tutorial cobre tudo o que você precisa saber para **C# barcode generation** com Aspose.BarCode, incluindo armadilhas comuns e dicas para lidar com IDs de arquivos grandes ou timestamps personalizados.

## O que você precisará

* .NET 6.0 SDK ou posterior (o código funciona com .NET Core e .NET Framework)
* Visual Studio 2022 ou qualquer IDE que suporte C#
* Uma licença ativa do Aspose.BarCode (a versão de avaliação gratuita funciona para desenvolvimento)
* O pacote NuGet `Aspose.BarCode` instalado no seu projeto

Esses pré-requisitos garantem que o exemplo seja executado sem configuração adicional.

## Etapa 1: Configurar o projeto de exemplo de barcode Aspose

Crie uma nova aplicação console e adicione a biblioteca Aspose.BarCode:

```bash
dotnet new console -n AsposeMacroPdf417Demo
cd AsposeMacroPdf417Demo
dotnet add package Aspose.BarCode
```

O pacote `Aspose.BarCode` fornece `BarcodeGenerator`, `BarCodeReader` e todos os tipos necessários para o tratamento de MacroPdf417.

### Por que esta etapa é importante
Adicionar o pacote NuGet resolve os enums `EncodeTypes`, `DecodeType` e `BarCodeImageFormat` usados posteriormente. Sem o pacote, o compilador não reconheceria esses símbolos, e o exemplo falharia na compilação.

## Etapa 2: Criar o gerador de barcode MacroPdf417

Abra **Program.cs** e substitua o código de modelo pelo bloco a seguir. Este bloco cria um `BarcodeGenerator` configurado para a simbologia MacroPdf417 e define parâmetros básicos de aparência.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Enums;
using System;

class Program
{
    static void Main()
    {
        // Step 2.1: Initialize the generator with source text.
        using (BarcodeGenerator barcodeGenerator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
        {
            // Adjust the module size – 2 pixels per X‑dimension.
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Reduce the number of columns to keep the barcode compact.
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Step 2.2: Embed MacroPdf417 metadata.
            // ---------------------------------------------------------
            // The following properties are optional but illustrate
            // how a full‑featured barcode can carry file‑level data.
            // ---------------------------------------------------------
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp =
                new DateTime(2024, 9, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator =
                Pdf417MacroTerminator.Set;

            // Step 2.3: Save the barcode image.
            const string outPath = "ExtPDF417Meta.png";
            barcodeGenerator.Save(outPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outPath}");
        }
```

#### Explicação das propriedades principais

| Propriedade | Propósito | Faixa típica / observações |
|-------------|-----------|----------------------------|
| `MacroPdf417FileID` | Identificador único para todo o arquivo | Deve ser ≤ 2³¹‑1 |
| `MacroPdf417SegmentID` | Índice do segmento atual | Começa em 0 |
| `MacroPdf417SegmentsCount` | Número total de segmentos no arquivo | Deve ser ≥ SegmentID |
| `MacroPdf417FileName` | Nome legível por humanos para o arquivo | Até 255 caracteres |
| `MacroPdf417Checksum` | Checksum CCITT‑16 do arquivo original | Calculado por ferramenta externa se necessário |
| `MacroPdf417FileSize` | Tamanho do arquivo original em bytes | Útil para validação |
| `MacroPdf417TimeStamp` | Data/hora em que o arquivo foi criado | Use UTC para consistência |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Informação de roteamento opcional | Qualquer string até 255 caracteres |
| `MacroPdf417Terminator` | Marca o segmento final | Use `Set` para o último segmento |

Esses campos constituem os **barcode metadata** que o leitor pode extrair posteriormente.

## Etapa 3: Decodificar o barcode e exibir os metadados

Após salvar a imagem, o mesmo programa continua abrindo o arquivo com `BarCodeReader`. Adicione o código a seguir dentro do método `Main`, após o bloco `using` anterior:

```csharp
        // Step 3: Open the saved image with a MacroPdf417 reader.
        using (BarCodeReader barcodeReader =
               new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
        {
            // Step 3.1: Iterate through all decoded results.
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                // The Extended property holds the MacroPdf417 specific fields.
                var meta = result.Extended.Pdf417;
                Console.WriteLine($"FileID: {meta.MacroPdf417FileID}");
                Console.WriteLine($"SegmentID: {meta.MacroPdf417SegmentID}");
                Console.WriteLine($"SegmentsCount: {meta.MacroPdf417SegmentsCount}");
                Console.WriteLine($"FileName: {meta.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {meta.MacroPdf417Checksum}");
                Console.WriteLine($"FileSize: {meta.MacroPdf417FileSize}");
                Console.WriteLine($"Timestamp: {meta.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {meta.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {meta.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {meta.MacroPdf417Terminator}");
            }
        }
    }
}
```

### Por que ler de volta é importante
O `BarCodeReader` valida se os metadados incorporados estão codificados corretamente. Se alguma propriedade estiver ausente ou fora do intervalo, o leitor retorna `null` para esse campo, permitindo que você trate erros de forma elegante.

## Etapa 4: Executar e verificar a saída

Execute o programa:

```bash
dotnet run
```

Você deverá ver uma saída no console semelhante a:

```
Barcode saved to ExtPDF417Meta.png
FileID: 12345678
SegmentID: 12
SegmentsCount: 20
FileName: file01
Checksum: 1234
FileSize: 400000
Timestamp: 9/1/2024 12:00:00 AM
Addressee: street
Sender: aspose
Terminator: Set
```

Se os valores coincidirem com os que você definiu na Etapa 2, o **aspose barcode example** funciona como esperado.

## Casos limites e dicas de boas práticas

| Situação | O que observar | Manuseio recomendado |
|----------|----------------|----------------------|
| **FileID exceeds 32‑bit range** | Aspose throws `ArgumentOutOfRangeException`. | Mantenha o ID ≤ 2 147 483 647 ou divida o arquivo em múltiplos blocos MacroPdf417. |
| **Timestamp em horário local** | Leitores em outro fuso horário podem interpretar o valor incorretamente. | Armazene timestamps em UTC (`DateTime.UtcNow`) e converta na exibição se necessário. |
| **Tamanho de arquivo grande** | `MacroPdf417FileSize` é um `int`; valores > 2 GB causam overflow. | Use um campo personalizado ou divida o arquivo em segmentos menores. |
| **Segmento ausente** | Se `SegmentID` não for sequencial, a reconstrução falha. | Valide a ordem dos segmentos antes da codificação ou use configurações de correção de erro. |
| **Formato de imagem não suportado** | Salvar como BMP pode aumentar o tamanho drasticamente. | PNG é um bom padrão; JPEG pode ser usado se aceitar compressão com perdas. |

**Dica profissional:** Quando você gera muitos barcodes em lote, reutilize uma única instância de `BarcodeGenerator` e altere apenas os `EncodeTypes` e o texto de origem. Isso reduz alocações de memória e acelera o processamento.

## Tópicos relacionados que você pode explorar a seguir

* **Other macro symbologies** – Aspose also supports MacroPdf417 with error correction levels.
* **Embedding barcodes in PDFs** – Combine `Aspose.PDF` with the barcode generator to produce printable documents.
* **ASP.NET Core integration** – Serve generated barcodes directly from a web API.
* **Scanning via mobile devices** – Use the `Aspose.BarCode.Cloud` SDK for cross‑platform decoding.

Esses assuntos complementares ampliam naturalmente o **aspose barcode example** e aprofundam sua expertise em **C# barcode generation**.

## Conclusão

Agora você tem um **aspose barcode example** totalmente funcional que cria um barcode MacroPdf417, incorpora ricos **barcode metadata**, salva a imagem e lê os dados de volta com `BarCodeReader`. Seguindo os passos acima, você pode adaptar o código a diferentes IDs de arquivo, timestamps ou até mesmo outros tipos de barcode suportados pela Aspose.

Sinta-se à vontade para experimentar campos de metadados adicionais, mudar o formato da imagem ou integrar o gerador em uma aplicação maior. Feliz codificação!

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}