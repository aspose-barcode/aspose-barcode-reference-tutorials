---
category: general
date: 2026-11-23
description: Aprenda a usar o BarCodeReader em C# para ler códigos de barras a partir
  de uma imagem, incluindo decodificação Macro PDF417, com um exemplo de código completo
  e explicações claras.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use barcodereader
- read barcodes from image c#
language: pt
lastmod: 2026-11-23
og_description: Como usar o BarCodeReader em C# para ler códigos de barras a partir
  de uma imagem. Siga este guia passo a passo para decodificar Macro PDF417 e outros
  formatos com código pronto para execução.
og_image_alt: Screenshot of BarCodeReader console output showing decoded Macro PDF417
  data
og_title: Como usar BarCodeReader em C# – leia códigos de barras de imagens rapidamente
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  headline: How to use BarCodeReader in C# to read barcodes from images
  type: TechArticle
- description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  name: How to use BarCodeReader in C# to read barcodes from images
  steps:
  - name: 1. Decoding multiple barcode formats
    text: 'If you need to detect more than one format, pass a combined `DecodeType`
      flag:'
  - name: 2. Managing large images
    text: 'Large images can cause high memory usage. Downscale the image before passing
      it to the reader:'
  - name: 3. Error handling
    text: 'Wrap the reading logic in a try‑catch block to surface decoding failures:'
  type: HowTo
tags:
- barcode
- C#
- image-processing
title: Como usar BarCodeReader em C# para ler códigos de barras de imagens
url: /pt/net/compact-pdf417-encoding/how-to-use-barcodereader-in-c-to-read-barcodes-from-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como usar BarCodeReader em C# para ler códigos de barras a partir de imagens

Se você precisa de **como usar BarCodeReader** para uma leitura rápida de código de barras, este guia mostra exatamente isso. Seja construindo um sistema de ponto de venda ou automatizando a ingestão de documentos, você aprenderá a ler códigos de barras de projetos de imagem em C# com apenas algumas linhas de código.

Neste tutorial você verá um exemplo completo e executável que decodifica um código de barras Macro PDF417, extrai suas propriedades estendidas e imprime informações úteis no console. Nenhuma documentação externa é necessária – tudo o que você precisa está aqui.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 (ou superior) instalado – o código tem como alvo a versão LTS mais recente.  
* Uma referência ao pacote NuGet **Aspose.BarCode** (ou qualquer compatível) que fornece `BarCodeReader`.  
* Um arquivo de imagem contendo um código de barras Macro PDF417 (o exemplo usa `ExtPDF417Meta.png`).

> **Dica:** Se você estiver usando o Visual Studio, adicione o pacote via `dotnet add package Aspose.BarCode` ou pela UI do NuGet Package Manager.

## Etapa 1: Criar uma instância de BarCodeReader

A primeira coisa que você faz ao trabalhar com uma biblioteca de códigos de barras é instanciar um leitor que aponta para a imagem de origem e informa à API quais tipos de código de barras procurar.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Step 1: Initialise BarCodeReader for a Macro PDF417 image
using (BarCodeReader barcodeReader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png",
           DecodeType.MacroPdf417))
{
    // The using block guarantees proper disposal of native resources.
```

*Por que esta etapa importa:*  
`BarCodeReader` abre a imagem, aloca memória nativa e prepara os algoritmos de decodificação para o `DecodeType` especificado. Ao limitar o tipo a `MacroPdf417`, você reduz a sobrecarga de CPU e melhora a precisão da detecção.

## Etapa 2: Ler todos os códigos de barras encontrados na imagem

Uma única imagem pode conter múltiplos códigos de barras, especialmente ao lidar com dados macro‑codificados. O método `ReadBarCodes` retorna um enumerável de objetos `BarCodeResult`, cada um representando um código detectado.

```csharp
    // Step 2: Iterate over every barcode found
    foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
    {
```

*Por que esta etapa importa:*  
Iterar sobre a coleção garante que você capture cada instância, o que é essencial para cenários de processamento em lote ou quando um documento incorpora vários códigos.

## Etapa 3: Acessar as propriedades estendidas do Macro PDF417

Macro PDF417 armazena metadados extras como identificadores de arquivo, números de segmento e contagem total de segmentos. Esses valores são expostos através da propriedade `Extended.Pdf417` de `BarCodeResult`.

```csharp
        // Step 3: Pull extended Macro PDF417 information
        var macroInfo = barcodeResult.Extended.Pdf417;
```

*Por que esta etapa importa:*  
Os campos estendidos permitem reconstruir documentos de múltiplos segmentos ou validar que todas as partes pertencem à mesma origem. Pular esta etapa deixaria você apenas com o texto bruto, perdendo contexto valioso.

## Etapa 4: Exibir as informações mais úteis

Por fim, escreva os dados no console (ou em qualquer logger) para que você possa verificar a operação de leitura. O exemplo imprime o tipo de código, o texto decodificado e vários campos macro.

```csharp
        // Step 4: Display key details
        Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
        Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
        Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
        // Additional macro fields are available:
        // macroInfo.MacroPdf417SegmentID
        // macroInfo.MacroPdf417SegmentsCount
    }
}
```

**Saída esperada no console**

```
Code Type: MacroPdf417
Code Text: 1234567890
Macro PDF417 File ID: 42
```

> **Observação:** Se a imagem não contiver um código de barras Macro PDF417, `ReadBarCodes()` retornará uma coleção vazia e o corpo do laço nunca será executado. Sempre verifique se o resultado está vazio em código de produção.

## Ler códigos de barras a partir de imagem em C# – lidando com cenários comuns

### 1. Decodificando múltiplos formatos de código de barras

Se precisar detectar mais de um formato, passe uma flag combinada de `DecodeType`:

```csharp
using (BarCodeReader reader = new BarCodeReader(
           "sample.png",
           DecodeType.Pdf417 | DecodeType.QR | DecodeType.DataMatrix))
{
    // Same iteration logic as before
}
```

### 2. Gerenciando imagens grandes

Imagens grandes podem causar alto consumo de memória. Reduza a escala da imagem antes de passá‑la ao leitor:

```csharp
using (Bitmap original = new Bitmap("large.png"))
using (Bitmap resized = new Bitmap(original, new Size(1024, 768)))
{
    // Save resized image to a temporary stream and feed it to BarCodeReader
}
```

### 3. Tratamento de erros

Envolva a lógica de leitura em um bloco try‑catch para expor falhas de decodificação:

```csharp
try
{
    // reading code from previous steps
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Exemplo completo funcional

Abaixo está o programa completo que você pode copiar, colar e executar. Ele inclui todas as etapas, diretivas `using` necessárias e um scaffold simples de tratamento de erros.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(
                       imagePath,
                       DecodeType.MacroPdf417))
            {
                bool anyFound = false;

                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    anyFound = true;
                    var macroInfo = barcodeResult.Extended.Pdf417;

                    Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
                    Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
                    Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {macroInfo.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments Count: {macroInfo.MacroPdf417SegmentsCount}");
                    Console.WriteLine(new string('-', 40));
                }

                if (!anyFound)
                {
                    Console.WriteLine("No barcodes were detected in the image.");
                }
            }
        }
        catch (BarCodeException ex)
        {
            Console.Error.WriteLine($"Error reading barcode: {ex.Message}");
        }
    }
}
```

**Executar o programa** imprime cada código de barras Macro PDF417 detectado e seus campos estendidos, ou informa que nenhum código foi encontrado.

## Conclusão

Agora você sabe **como usar BarCodeReader** para ler códigos de barras de aplicações de imagem em C#, incluindo a extração de metadados Macro PDF417. A solução cobre inicialização, iteração, acesso a propriedades estendidas e dicas práticas para lidar com múltiplos formatos, imagens grandes e erros.

Em seguida, você pode explorar:

* **Leitura de QR codes** – substitua `DecodeType.MacroPdf417` por `DecodeType.QR`.  
* **Salvar dados decodificados** em um banco de dados ou arquivo JSON para processamento posterior.  
* **Integrar com ASP.NET Core** para aceitar imagens enviadas via API web.

Sinta‑se à vontade para experimentar diferentes tipos de códigos de barras e fontes de imagem. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [c# barcode reader tutorial – read Macro PDF417 barcodes step by step using GroupDocs.Barcode](/barcode/english/net/compact-pdf417-encoding/c-barcode-reader-tutorial-read-macro-pdf417-barcodes-step-by/)
- [How to use a barcode generator C# for Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/)
- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}