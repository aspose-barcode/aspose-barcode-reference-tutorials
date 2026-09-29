---
category: general
date: 2026-08-09
description: Como ler PDF417 em C# usando o BarCodeReader. Aprenda a ler arquivos
  PNG de código de barras, lidar com múltiplos códigos de barras e extrair metadados
  estendidos.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- c# barcode reader
- read multiple barcodes
- read barcode png
- read barcode extended
language: pt
lastmod: 2026-08-09
og_description: Como ler PDF417 em C# com Aspose.BarCode. Este tutorial mostra como
  ler arquivos PNG de códigos de barras, processar vários códigos de barras em uma
  única imagem e recuperar metadados estendidos do PDF417.
og_image_alt: Screenshot of C# BarCodeReader console output displaying PDF417 metadata
og_title: Como ler PDF417 em C# – tutorial de leitor de código de barras
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  headline: How to read PDF417 in C# – complete barcode reader guide
  type: TechArticle
- description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  name: How to read PDF417 in C# – complete barcode reader guide
  steps:
  - name: Verify the file exists before creating the reader.
    text: Verify the file exists before creating the reader.
  - name: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
    text: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
  - name: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
    text: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Como ler PDF417 em C# – guia completo de leitor de código de barras
url: /pt/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como ler PDF417 em C# – guia completo de leitor de código de barras

Se você precisa **como ler PDF417** em uma aplicação .NET, este guia fornece uma solução pronta‑para‑usar. Você verá como ler um PNG de código de barras, processar vários códigos de barras na mesma imagem e extrair os campos estendidos do PDF417 que muitos scanners ocultam.

A leitura de códigos de barras PDF417 é comum em logística, bilhetagem e gerenciamento de documentos. Ao final deste tutorial você poderá decodificar uma imagem Macro PDF417, exibir cada resultado e usar as informações extras (ID do arquivo, contagem de segmentos, timestamps, etc.) na sua própria lógica de negócio.

## Pré-requisitos

- .NET 6.0 ou superior (o código também funciona com .NET Framework 4.7+)
- Visual Studio 2022 ou qualquer IDE C#
- **Aspose.BarCode for .NET** (versão de avaliação gratuita ou pacote NuGet licenciado)
- Uma imagem PNG que contenha um código de barras Macro PDF417 (o arquivo de exemplo se chama `ExtPDF417Meta.png`)

> **Dica Pro:** Instale a biblioteca via console NuGet:  
> `dotnet add package Aspose.BarCode`

## Como ler PDF417 com BarCodeReader em C#

O núcleo da solução é a classe `BarCodeReader`. Ela aceita um caminho de imagem e um enum `DecodeType` que indica ao motor qual simbologia procurar.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.ReadEngine;

class Pdf417Demo
{
    static void Main()
    {
        // Step 1: Create a BarCodeReader for a Macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Display Macro PDF417 extended metadata
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
}
```

### Por que isso funciona

- **`DecodeType.MacroPdf417`** informa ao leitor para buscar a variante Macro PDF417, que armazena os campos extras que você vê na etapa 4.  
- O bloco `using` descarta o leitor automaticamente, liberando os manipuladores de arquivo.  
- `ReadBarCodes()` retorna **todos** os códigos de barras que correspondem ao tipo solicitado, atendendo ao requisito de *ler múltiplos códigos de barras* mesmo que a imagem contenha apenas um.

Executar o programa exibe uma saída semelhante a:

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: invoice_2023.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254321
Pdf417MacroTimeStamp: 2023-03-15T10:45:00Z
Pdf417MacroAddressee: ACME Corp.
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: True
----------------------------------------
```

## Usando o leitor de código de barras C# para ler múltiplos códigos de barras

Se uma imagem contém vários símbolos Macro PDF417 (por exemplo, uma página escaneada com um lote de ingressos), o mesmo loop `foreach` processa cada um. Nenhum código extra é necessário; o leitor agrega os resultados internamente.

```csharp
// Example: processing a batch image
using (BarCodeReader batchReader = new BarCodeReader(
    "batch.png", DecodeType.MacroPdf417))
{
    int index = 0;
    foreach (BarCodeResult item in batchReader.ReadBarCodes())
    {
        Console.WriteLine($"--- Barcode #{++index} ---");
        Console.WriteLine($"Text: {item.CodeText}");
        // extended fields are accessed the same way
    }
}
```

### Armadilhas comuns

- **Formato da imagem:** O leitor suporta PNG, JPEG, BMP e TIFF. Se você tentar um formato que ele não consegue decodificar, receberá uma coleção vazia. Por isso o tutorial destaca *read barcode PNG*.  
- **Resolução:** Imagens de baixa resolução (< 300 dpi) podem causar perda de segmentos. Aumente a escala ou solicite uma digitalização de maior qualidade quando possível.  
- **Flag Macro:** Esquecer `DecodeType.MacroPdf417` limita o motor ao PDF417 simples e descarta os dados estendidos. Sempre especifique o tipo macro quando precisar de campos *read barcode extended*.

## Lendo arquivos PNG de código de barras – melhores práticas

Trabalhar com arquivos PNG é simples porque o formato preserva dados de pixel sem perdas. Aqui está uma lista rápida de verificação:

1. Verifique se o arquivo existe antes de criar o leitor.  
   ```csharp
   if (!File.Exists(path))
       throw new FileNotFoundException($"File not found: {path}");
   ```
2. Use `Image.FromFile` somente quando precisar pré‑processar (rotacionar, recortar). O `BarCodeReader` pode abrir o arquivo diretamente, evitando alocação extra de memória.  
3. Se o PNG contiver transparência, o leitor ainda funciona porque o código de barras é renderizado sobre pixels opacos.

## Acessando metadados estendidos do PDF417

O objeto `Extended.Pdf417` expõe todos os campos opcionais definidos pela especificação PDF417. Você pode mapear esses campos para um modelo de domínio, armazená‑los em um banco de dados ou usá‑los para validação.

```csharp
public class Pdf417Metadata
{
    public int FileID { get; set; }
    public int SegmentID { get; set; }
    public int SegmentsCount { get; set; }
    public string FileName { get; set; }
    public string Checksum { get; set; }
    public long FileSize { get; set; }
    public DateTime TimeStamp { get; set; }
    public string Addressee { get; set; }
    public string Sender { get; set; }
    public bool Terminator { get; set; }
}
```

Preencha o modelo:



## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como ler códigos de barras DataMatrix com Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Como criar código de barras – PDF417 Compacto com Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Ler código de barras DataMatrix C# – Gerar modo DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}