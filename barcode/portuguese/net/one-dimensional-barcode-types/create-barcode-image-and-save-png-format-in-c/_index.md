---
category: general
date: 2026-11-27
description: Criar imagem de código de barras em C# e salvar a imagem no formato PNG
  com Aspose.BarCode – guia passo a passo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- save image PNG format
- Aspose.BarCode C#
- Macro PDF417 barcode
- barcode generation .NET
language: pt
lastmod: 2026-11-27
og_description: Criar imagem de código de barras em C# e salvar a imagem no formato
  PNG usando Aspose.BarCode. Siga este tutorial para gerar um código de barras Macro
  PDF417 passo a passo.
og_image_alt: Screenshot of a created barcode image saved as PNG
og_title: Criar imagem de código de barras e salvar em formato PNG em C# – guia completo
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Create barcode image in C# and save image PNG format with Aspose.BarCode
    – step‑by‑step guide.
  headline: Create barcode image and save PNG format in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Criar imagem de código de barras e salvar em formato PNG em C#
url: /pt/net/one-dimensional-barcode-types/create-barcode-image-and-save-png-format-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar imagem de código de barras e salvar em formato PNG em C#

Se você precisa **criar uma imagem de código de barras** em uma aplicação .NET, este guia mostra como gerar um código de barras Macro PDF417 e **salvar a imagem em formato PNG** usando Aspose.BarCode. Você obterá um exemplo completo e executável e uma explicação de cada configuração para que possa adaptar o código às suas próprias necessidades.

Gerar um código de barras vai além de chamar um único método; é necessário configurar o tamanho do módulo, os parâmetros macro e o formato de saída. Ao final deste tutorial você entenderá por que cada propriedade é importante, como lidar com casos de borda comuns e como verificar se o arquivo PNG foi gravado corretamente.

## O que você precisará

- .NET 6.0 ou posterior (o código também funciona com .NET Framework 4.6+)
- Aspose.BarCode for .NET (disponível via NuGet: `Install-Package Aspose.BarCode`)
- Uma IDE como Visual Studio 2022 ou Visual Studio Code
- Permissão de gravação em uma pasta onde o arquivo PNG será salvo

## Etapa 1: Inicializar o gerador de código de barras

A primeira etapa é criar uma instância de `BarcodeGenerator` especificando a simbologia `EncodeTypes.MacroPdf417` e o texto que você deseja codificar.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Initialize a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps go here
}
```

**Por que isso importa:**  
`EncodeTypes.MacroPdf417` indica à biblioteca que deve usar a variante macro do PDF417, que suporta segmentação de arquivos e metadados adicionais. O construtor também recebe o texto legível que será codificado no código de barras.

## Etapa 2: Definir o tamanho do módulo (dimensão X)

A dimensão X controla a largura de um único módulo do código de barras (o menor elemento preto/branco). Um valor de `2` pixels funciona bem para PNGs exibidos na tela.

```csharp
    // Step 2: Define the module size (X‑dimension) in pixels
    generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Dica prática:**  
Se você pretende imprimir o código de barras, aumente o valor em pixels (por exemplo, `4` ou `5`) para evitar saída borrada em impressoras de baixa resolução.

## Etapa 3: Configurar os parâmetros macro do PDF417

Macro PDF417 adiciona vários campos opcionais que ajudam a identificar o arquivo de origem, a ordem dos segmentos e verificações de integridade. Abaixo está um conjunto completo de parâmetros típicos; você pode omitir qualquer um que não precisar.

```csharp
    // Step 3: Set PDF417 macro parameters
    generator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // Current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;  // Approximate file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**Por que esses campos são úteis:**  

| Parameter | Purpose |
|-----------|---------|
| `Columns` | Controla a largura do código de barras; menos colunas produzem um código de barras mais alto. |
| `MacroPdf417FileID` | Identificador único que une todos os segmentos. |
| `MacroPdf417SegmentID` | Posição deste segmento dentro do arquivo completo. |
| `MacroPdf417SegmentsCount` | Número total de segmentos; necessário para a reconstrução. |
| `MacroPdf417FileName` | Nome legível que pode ser exibido por aplicativos de leitura. |
| `MacroPdf417Checksum` | Ajuda os receptores a verificar a integridade dos dados (CCITT‑16). |
| `MacroPdf417FileSize` | Dica opcional de tamanho para o arquivo original. |
| `MacroPdf417TimeStamp` | Carimbo de data/hora da criação do arquivo original. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Metadados para roteamento ou propriedade. |
| `MacroPdf417Terminator` | Indica se este é o segmento final (`Set`) ou um intermediário (`Unset`). |

**Caso de borda:** Se você gerar um código de barras de segmento único, defina `MacroPdf417SegmentsCount` como `1` e `MacroPdf417Terminator` como `Unset`. A biblioteca omitirá automaticamente os campos relacionados a segmentos que não são aplicáveis.

## Etapa 4: Salvar o código de barras gerado como imagem PNG

Por fim, chame `Save` com um caminho de arquivo e o valor do enum `BarCodeImageFormat.Png`. O método grava a imagem no disco no formato PNG sem perdas.

```csharp
    // Step 4: Save the generated barcode as a PNG image
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

**Por que PNG?**  
PNG preserva os valores exatos dos pixels, o que é essencial para leitores de código de barras que dependem de contraste nítido. A compressão JPEG pode introduzir artefatos que quebram o padrão do código de barras.

### Verificando a saída

Depois que o programa for executado, você deverá ver um arquivo chamado `ExtPDF417Meta.png` na pasta de execução. Abrindo-o com qualquer visualizador de imagens, será exibido um código de barras denso e retangular. Você pode verificar a correção escaneando a imagem com um leitor de código de barras móvel que suporte PDF417 macro; o aplicativo normalmente mostrará os metadados incorporados (ID do arquivo, número do segmento, etc.).

## Armadilhas comuns e como evitá‑las

| Symptom | Likely cause | Fix |
|---------|--------------|-----|
| O código de barras aparece borrado | Dimensão X muito baixa para o DPI escolhido | Aumente `XDimension.Pixels` ou renderize em DPI mais alto (`generator.Parameters.ImageResolution`). |
| O scanner relata “checksum error” | Valor incorreto de `MacroPdf417Checksum` | Deixe o Aspose calcular o checksum automaticamente omitindo a propriedade, ou garanta que o valor corresponda ao algoritmo CCITT‑16. |
| O arquivo PNG está vazio ou não foi criado | Caminho de saída inválido ou falta de permissão de gravação | Use `Path.Combine` com uma pasta conhecida e gravável (por exemplo, `Environment.GetFolderPath(Environment.SpecialFolder.Desktop)`). |
| Campos macro são ignorados | `EncodeTypes` definido como `Pdf417` regular em vez de `MacroPdf417` | Verifique se `EncodeTypes.MacroPdf417` está sendo usado no construtor. |

## Exemplo completo e executável

Abaixo está o programa completo que você pode copiar para uma aplicação console. Ele compila com .NET 6.0 e produz o arquivo PNG descrito acima.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize a Macro PDF417 barcode generator with the desired text
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // Define the module size (X-dimension) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set PDF417 macro parameters
            generator.Parameters.Barcode.Pdf417.Columns = 5;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 checksum
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

**Saída esperada (console):**

```
Barcode image saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Abrir `ExtPDF417Meta.png` mostra um código de barras Macro PDF417 claro, pronto para ser escaneado.

## Próximos passos

- **Alterar o formato da imagem** – substitua `BarCodeImageFormat.Png` por `Jpeg` ou `Bmp` se precisar de outro tipo de arquivo. Lembre‑se de que JPEG introduz artefatos de compressão, o que pode afetar a confiabilidade da leitura.
- **Ajustar a resolução** – use

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [How to create barcode image with Aspose.Barcode in C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [How to create PDF417 barcode image in C# with Macro PDF417 options](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [How to read barcodes from image using C# with Aspose.BarCode – step‑by‑step guide](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}