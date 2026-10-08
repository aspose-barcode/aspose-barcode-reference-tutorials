---
category: general
date: 2026-09-10
description: Aprenda a decodificar códigos de barras a partir de imagens usando um
  exemplo conciso de leitor de códigos de barras em C# que lê códigos Macro PDF417
  em apenas algumas linhas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- decode barcode from image
- c# barcode reader example
- read barcode C#
- barcode decoding tutorial
- Macro PDF417 C#
language: pt
lastmod: 2026-09-10
og_description: Decodifique o código de barras a partir de uma imagem usando um exemplo
  curto de leitor de código de barras em C#. Siga o guia passo a passo para ler dados
  Macro PDF417 instantaneamente.
og_image_alt: Screenshot of console output showing decoded Macro PDF417 barcode information
og_title: Decodifique código de barras a partir de imagem com um exemplo de leitor
  de código de barras em C#
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to decode barcode from image using a concise C# barcode reader
    example that reads Macro PDF417 codes in just a few lines.
  headline: Decode barcode from image with a C# barcode reader example
  type: TechArticle
- description: Learn how to decode barcode from image using a concise C# barcode reader
    example that reads Macro PDF417 codes in just a few lines.
  name: Decode barcode from image with a C# barcode reader example
  steps:
  - name: '**Initialize** a `BarCodeReader` for the target image.'
    text: '**Initialize** a `BarCodeReader` for the target image.'
  - name: '**Iterate** over every detected barcode.'
    text: '**Iterate** over every detected barcode.'
  - name: '**Print** the standard and extended Macro PDF417 data.'
    text: '**Print** the standard and extended Macro PDF417 data.'
  type: HowTo
tags:
- barcode
- C#
- image processing
title: Decodificar código de barras de uma imagem com um exemplo de leitor de código
  de barras em C#
url: /pt/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Decodificar código de barras a partir de imagem com um exemplo de leitor de código de barras C#

Se você precisa **decodificar código de barras a partir de imagem**, este guia mostra exatamente como fazer isso em C#. Usando um **exemplo compacto de leitor de código de barras C#**, você lerá dados Macro PDF417 com apenas algumas linhas de código.

Você verá um programa completo e executável, entenderá por que cada parte é importante e aprenderá dicas que evitam armadilhas comuns. Nenhuma documentação externa é necessária — tudo o que você precisa está aqui.

## O que você aprenderá

- Configurar o pacote NuGet necessário para decodificação de códigos de barras.  
- Escrever um **exemplo de leitor de código de barras C#** que abre um arquivo de imagem e extrai todos os códigos de barras.  
- Acessar campos estendidos do Macro PDF417, como o ID do arquivo.  
- Verificar a saída e adaptar o código para outros tipos de códigos de barras.

### Pré-requisitos

- .NET 6.0 SDK ou posterior (o código também funciona com .NET Core 3.1 e .NET Framework 4.7+).  
- Familiaridade básica com aplicações console em C#.  
- Um arquivo de imagem que contém um código de barras Macro PDF417 (por exemplo, `MacroPdf417.png`).  

## Etapa 1: Instalar a biblioteca de códigos de barras

O exemplo usa **Aspose.BarCode for .NET**, uma biblioteca amplamente utilizada que suporta a decodificação de Macro PDF417.

```bash
dotnet add package Aspose.BarCode
```

> **Por que esta biblioteca?**  
> Ela fornece uma única classe `BarCodeReader` que lida com muitos formatos, oferece alta precisão e retorna informações estendidas para códigos Macro PDF417 — tudo sem configuração adicional.

## Etapa 2: Criar um exemplo de leitor de código de barras C#

Crie um novo projeto console e substitua o `Program.cs` gerado pelo código abaixo. O exemplo segue três ações claras:

1. **Inicializar** um `BarCodeReader` para a imagem alvo.  
2. **Iterar** sobre cada código de barras detectado.  
3. **Imprimir** os dados padrão e estendidos do Macro PDF417.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Path to the image that contains the Macro PDF417 barcode
            const string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            // 1️⃣ Create a BarCodeReader configured for Macro PDF417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Read all barcodes found in the image
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Display basic information
                    Console.WriteLine($"Code Type: {result.CodeTypeName}");
                    Console.WriteLine($"Code Text: {result.CodeText}");

                    // 3️⃣ Display Macro PDF417 extended fields (if available)
                    if (result.Extended?.Pdf417?.MacroPdf417FileID != null)
                    {
                        Console.WriteLine($"Macro PDF417 File ID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

### Explicação de cada seção

- **Construtor `BarCodeReader`** – O primeiro argumento é o caminho da imagem; o segundo indica à biblioteca que procure especificamente por códigos Macro PDF417. Essa decodificação focada melhora o desempenho em comparação com a varredura de todos os formatos possíveis.  
- **`ReadBarCodes()`** – Retorna um enumerável de todos os códigos de barras detectados na imagem, permitindo lidar com múltiplos códigos em um único arquivo.  
- **`result.Extended.Pdf417.MacroPdf417FileID`** – O Macro PDF417 armazena metadados adicionais (ID do arquivo, contagem de segmentos, etc.). O exemplo verifica se é nulo para evitar uma `NullReferenceException` quando a imagem contém um código de barras que não é Macro.  

## Etapa 3: Executar o programa e verificar a saída

Build and run the console application:

```bash
dotnet run
```

You should see output similar to:

```
Code Type: MacroPdf417
Code Text: 1234567890ABCDEF
Macro PDF417 File ID: 42
----------------------------------------
```

Se a imagem não contiver um código de barras Macro PDF417, o programa ainda listará quaisquer outros formatos detectados, mas o campo estendido será omitido.

## Dica profissional: Decodificar outros tipos de códigos de barras sem mudar muito o código

Para **decodificar código de barras a partir de imagem** para um formato diferente, altere o valor do enum `DecodeType`:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.QR))
```

Você também pode passar `DecodeType.AllSupportedTypes` para permitir que a biblioteca detecte qualquer código de barras que ela reconheça.

## Armadilhas comuns e como evitá‑las

| Sintoma | Causa | Correção |
|---------|-------|-----|
| Nenhuma saída | Caminho da imagem errado ou formato de arquivo não suportado | Verifique o caminho, assegure que o arquivo seja uma imagem suportada (PNG, JPEG, BMP) |
| `result.Extended` é nulo para Macro PDF417 | O código de barras não é uma variante Macro PDF417 | Confirme que a imagem de origem realmente contém um código Macro PDF417 |
| Exceção `System.IO.FileNotFoundException` | Pacote NuGet ausente em tempo de execução | Execute `dotnet restore` e assegure que o `Aspose.BarCode.dll` seja copiado para a pasta de saída |

## Listagem completa do código-fonte para copiar‑e‑colar rápido

Abaixo está o programa completo, pronto para ser copiado para `Program.cs`. Nenhum arquivo adicional é necessário.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            const string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type: {result.CodeTypeName}");
                    Console.WriteLine($"Code Text: {result.CodeText}");

                    if (result.Extended?.Pdf417?.MacroPdf417FileID != null)
                    {
                        Console.WriteLine($"Macro PDF417 File ID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

## Próximos passos

- **Explorar outros campos estendidos** como `MacroPdf417SegmentID` ou `MacroPdf417FileSize` para construir fluxos de trabalho de reconstrução de documentos completos.  
- **Integrar o leitor em uma API web** para que clientes possam enviar imagens e receber dados decodificados instantaneamente.  
- **Medir desempenho** decodificando grandes lotes de imagens; o `BarCodeReader` suporta processamento assíncrono nas versões mais recentes da Aspose.

---

Seguindo este **exemplo de leitor de código de barras C#**, você agora tem um método confiável para **decodificar código de barras a partir de imagem** e extrair informações ricas do Macro PDF417. Experimente diferentes valores de `DecodeType`, combine essa lógica com observadores de arquivos ou incorpore-a em back‑ends móveis — suas capacidades de processamento de códigos de barras estão prontas para escalar.

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como ler PDF417 em C# – Exemplo completo de leitor de código de barras](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Gerar código de barras com texto – Guia completo de PDF417 Macro](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)
- [Como criar código de barras PDF417 com Aspose – Guia completo passo a passo](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}