---
category: general
date: 2026-08-03
description: Leia o código de barras PDF417 de uma imagem usando C# BarCodeReader
  – um exemplo completo de leitor de códigos de barras que também mostra como ler
  vários códigos de barras.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read PDF417 barcode
- barcode reader example
- read multiple barcodes
- read barcodes image
language: pt
lastmod: 2026-08-03
og_description: Leia o código de barras PDF417 rapidamente com um exemplo de BarCodeReader
  em C#. Siga este guia passo a passo para decodificar macro PDF417 e ler vários códigos
  de barras de uma imagem.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: Ler código de barras PDF417 em C# – exemplo completo de leitor de código
  de barras
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  headline: Read PDF417 barcode in C# – barcode reader example
  type: TechArticle
- description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  name: Read PDF417 barcode in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
title: Ler código de barras PDF417 em C# – exemplo de leitor de código de barras
url: /pt/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ler código de barras PDF417 em C# – exemplo de leitor de código de barras

Se você precisar ler dados de código de barras PDF417 a partir de uma imagem, este guia mostra como fazer isso com a classe **BarCodeReader** em C#. Você aprenderá um exemplo de leitor de código de barras que também lida com macro PDF417 e pode ler vários códigos de barras em uma única imagem.

Trabalhar com códigos de barras geralmente significa lidar com diferentes fontes de imagem, condições de iluminação variadas e, às vezes, dados compostos como segmentos de macro PDF417. Este tutorial cobre tudo o que você precisa para decodificar um código de barras PDF417, extrair seus campos estendidos e processar vários códigos de barras da mesma foto. Ao final, você terá um programa de console executável que lê códigos de barras de um arquivo de imagem e imprime informações detalhadas no console.

## O que você vai precisar

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou posterior instalado  
* Uma versão recente do pacote NuGet **Aspose.BarCode for .NET** (ou qualquer biblioteca compatível que forneça `BarCodeReader` e `DecodeType.MacroPdf417`)  
* Um arquivo de imagem que contenha um código de barras PDF417 ou macro PDF417 (o exemplo usa `ExtPDF417Meta.png`)  
* Um editor de código ou IDE, como Visual Studio 2022  

Nenhum serviço adicional ou API externa é necessário.

## Configurando o projeto para leitura de código de barras

1. **Crie um novo projeto de console**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Adicione a biblioteca de código de barras**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Copie a imagem do código de barras**  

   Coloque `ExtPDF417Meta.png` (ou qualquer imagem que contenha um código de barras PDF417) na pasta do projeto.  
   Para este tutorial, assumimos que o arquivo está em `YOUR_DIRECTORY/ExtPDF417Meta.png`.

O projeto agora está pronto para compilar e executar o exemplo de leitor de código de barras.

## Como ler código de barras PDF417 com BarCodeReader

O núcleo da solução é um bloco `using` que cria uma instância de `BarCodeReader`, especifica `DecodeType.MacroPdf417` e itera sobre cada código de barras detectado. O código a seguir é um programa completo e autocontido que você pode colar em `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
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

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Por que isso funciona**:  

* `DecodeType.MacroPdf417` indica ao leitor que procure a extensão macro do PDF417, que contém metadados adicionais como ID do arquivo, contagem de segmentos e timestamps.  
* A instrução `using` garante que recursos não gerenciados (manipuladores de arquivos, buffers nativos de decodificação) sejam liberados prontamente.  
* O laço `foreach` processa automaticamente **todos** os códigos de barras que a imagem contém, atendendo ao requisito de *ler múltiplos códigos de barras*.  

Quando você executar o programa (`dotnet run`), deverá ver uma saída semelhante à seguinte:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

Se a imagem contiver mais de um código de barras PDF417, o laço imprimirá um bloco separado para cada código, demonstrando como **ler múltiplos códigos de barras** a partir de uma única foto.

## Lendo múltiplos códigos de barras de uma imagem

A mesma instância de `BarCodeReader` pode decodificar vários tipos de código de barras ao mesmo tempo. Para ampliar o escopo de apenas macro PDF417 para qualquer PDF417 (ou até QR, Code128, etc.), ajuste a flag `DecodeType`:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* é uma máscara de bits, portanto você pode combinar qualquer número de formatos suportados. Essa flexibilidade torna o trecho um **exemplo de leitor de código de barras** que funciona para uma ampla variedade de casos de uso, como a leitura de rótulos de produtos, ingressos ou carteiras de identidade.

## Acessando campos macro PDF417 com segurança

Macro PDF417 adiciona um conjunto rico de propriedades estendidas. Contudo, nem todo código de barras inclui todos os campos. Acessar uma propriedade ausente pode gerar uma `NullReferenceException`. A abordagem mais segura é verificar cada propriedade antes de imprimi‑la:

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Por que isso importa*: Em implantações reais você pode receber códigos de barras PDF417 simples que não possuem dados macro. A verificação defensiva garante que seu aplicativo continue em execução sem travar.

## Armadilhas comuns e boas práticas

| Problema | Por que acontece | Correção recomendada |
|----------|------------------|----------------------|
| O caminho da imagem está incorreto | `BarCodeReader` lança uma exceção de arquivo não encontrado antes de qualquer decodificação | Use `Path.Combine` e valide a existência do arquivo com `File.Exists` |
| Imagem de baixa resolução | O decodificador não consegue localizar as bordas do código, resultando em zero detecções | Forneça uma resolução mínima de 300 dpi para resultados confiáveis |
| Código de barras rotacionado > 45° | Muitas bibliotecas assumem orientação vertical | Ative `reader.RecognitionOptions.RotateImage = true` se a imagem estiver inclinada |

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como ler códigos de barras DataMatrix com Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Ler código de barras DataMatrix em C# – Gerar modo DataMatrix (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Ler código de barras a partir de imagem – Dominando a extração de região de código de barras em Java com Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}