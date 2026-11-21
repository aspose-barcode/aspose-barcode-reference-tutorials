---
category: general
date: 2026-11-20
description: Aprenda como gerar códigos de barras com Aspose.Barcode em C#. Este guia
  orienta você na criação de um código de barras MicroPdf417 e na sua gravação como
  imagem PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
language: pt
lastmod: 2026-11-20
og_description: Como gerar código de barras usando Aspose.Barcode em C#. Siga este
  tutorial completo para criar um código de barras MicroPdf417 e exportá-lo como PNG.
og_image_alt: 'How to generate barcode: sample MicroPdf417 image produced by Aspose.Barcode'
og_title: Como gerar código de barras com Aspose.Barcode – guia passo a passo em C#
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to generate barcode with Aspose.Barcode in C#. This guide
    walks you through creating a MicroPdf417 barcode and saving it as a PNG image.
  headline: How to generate barcode using Aspose.Barcode in C#
  type: TechArticle
- description: Learn how to generate barcode with Aspose.Barcode in C#. This guide
    walks you through creating a MicroPdf417 barcode and saving it as a PNG image.
  name: How to generate barcode using Aspose.Barcode in C#
  steps:
  - name: Install the Aspose.Barcode NuGet package
    text: 'Open a terminal in your project folder and run:'
  - name: Create a `BarcodeGenerator` instance for MicroPdf417
    text: '```csharp using Aspose.Barcode.Generation;'
  - name: Adjust the X‑dimension (module width)
    text: '```csharp // Step 3: Set the module width in pixels – 2 px yields a clear,
      print‑ready image generator.Parameters.Barcode.XDimension.Pixels = 2; ```'
  - name: Choose the number of columns for the PDF417 component
    text: '```csharp // Step 4: Define how many columns the PDF417 component should
      use (1‑4 allowed) generator.Parameters.Barcode.Pdf417.Columns = 4; ```'
  - name: Save the barcode image
    text: '```csharp using System.IO;'
  - name: Full source code
    text: 'Putting all steps together yields a complete, self‑contained console application:'
  - name: Generating other symbologies
    text: 'If you want to **create barcode with Aspose** for QR codes, Code128, or
      UPC, replace `EncodeTypes.MicroPdf417` with the appropriate enum value, e.g.:'
  - name: Changing image format
    text: 'Aspose.Barcode supports multiple raster formats. To export as JPEG with
      90 % quality:'
  - name: Handling large data payloads
    text: MicroPdf417 can store up to 1 KB of data. For larger payloads switch to
      full `EncodeTypes.Pdf417` and adjust `Rows` and `Columns` accordingly.
  - name: Unicode and special characters
    text: The library automatically encodes Unicode strings. However, some legacy
      scanners only recognize ASCII. If you target such devices, limit the input to
      the ASCII range or use a different symbology that guarantees compatibility.
  type: HowTo
tags:
- barcode generation
- Aspose.Barcode
- C#
- MicroPdf417
title: Como gerar código de barras usando Aspose.Barcode em C#
url: /pt/net/compact-pdf417-encoding/how-to-generate-barcode-using-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar código de barras usando Aspose.Barcode em C#

Se você precisa **como gerar código de barras** para um aplicativo desktop ou web, Aspose.Barcode fornece uma API simples. Este tutorial mostra exatamente como gerar um código de barras MicroPdf417, personalizar suas dimensões e salvar o resultado como um arquivo PNG. Você também verá como **criar código de barras com Aspose** para outros formatos sem sair do IDE.

Gerar um código de barras é uma necessidade comum em sistemas de inventário, plataformas de bilhetagem e fluxos de trabalho de documentos seguros. Ao final deste guia você terá um programa executável que produz uma imagem de código de barras de alta qualidade pronta para impressão ou incorporação.

## O que você precisará

* .NET 6.0 SDK ou posterior (o código também funciona com .NET Framework 4.7+)
* Visual Studio 2022 (ou qualquer editor C#)
* Uma licença válida para Aspose.Barcode para .NET – a avaliação gratuita funciona para desenvolvimento e testes
* Familiaridade básica com a sintaxe C#

Nenhum pacote NuGet adicional é necessário além de `Aspose.Barcode`.

## Como gerar código de barras com Aspose.Barcode

As seções a seguir dividem o processo em etapas discretas. Cada etapa explica **por que** o código é necessário, não apenas **o que** ele faz.

### Etapa 1: Instalar o pacote NuGet Aspose.Barcode

Abra um terminal na pasta do seu projeto e execute:

```bash
dotnet add package Aspose.Barcode
```

Este comando adiciona a versão estável mais recente do Aspose.Barcode ao seu arquivo de projeto, garantindo que a classe `BarcodeGenerator` esteja disponível em tempo de compilação.

**Por que isso importa:** O pacote contém o mecanismo central de renderização e um conjunto de `EncodeTypes` predefinidos. Sem ele o compilador não pode resolver `BarcodeGenerator` ou `EncodeTypes`.

### Etapa 2: Criar uma instância `BarcodeGenerator` para MicroPdf417

```csharp
using Aspose.Barcode.Generation;

// Step 2: Initialize the generator with the desired symbology and data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,          // MicroPdf417 is a compact 2‑D barcode
    "Åspóse.Barcóde©");               // Sample text – Unicode characters are supported
```

**Por que isso importa:** O construtor associa a simbologia (`EncodeTypes.MicroPdf417`) aos dados brutos que você deseja codificar. MicroPdf417 é ideal quando você precisa de uma pegada menor que o PDF417 completo, ainda suportando dados alfanuméricos.

### Etapa 3: Ajustar a X‑dimensão (largura do módulo)

```csharp
// Step 3: Set the module width in pixels – 2 px yields a clear, print‑ready image
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Por que isso importa:** A X‑dimensão determina o tamanho de cada célula do código de barras. Um valor muito baixo produz uma imagem borrada; um valor muito alto torna o código de barras desnecessariamente grande. Dois pixels são um padrão equilibrado para a maioria dos cenários de tela e impressão.

### Etapa 4: Escolher o número de colunas para o componente PDF417

```csharp
// Step 4: Define how many columns the PDF417 component should use (1‑4 allowed)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Por que isso importa:** MicroPdf417 usa internamente um componente PDF417. Ajustar a contagem de colunas influencia a proporção do código de barras e a capacidade de dados. Quatro colunas fornecem uma forma compacta mantendo a legibilidade.

### Etapa 5: Salvar a imagem do código de barras

```csharp
using System.IO;

// Step 5: Export the barcode as a PNG file
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "MicroPdf417.png");

generator.Save(outputPath, BarCodeImageFormat.Png);
```

**Por que isso importa:** `Save` grava o código de barras renderizado no disco. PNG é sem perdas, o que preserva bordas nítidas essenciais para leitores. Você pode substituir `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` ou `Gif` se seu fluxo de trabalho exigir outro formato.

### Código-fonte completo

Juntando todas as etapas resulta em um aplicativo console completo e autocontido:

```csharp
using System;
using System.IO;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize generator with MicroPdf417 symbology and sample data
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©");

            // Configure visual appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Determine output location (Desktop for easy access)
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "MicroPdf417.png");

            // Save the barcode image as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to: {outputPath}");
        }
    }
}
```

Execute o programa (`dotnet run`) e você encontrará `MicroPdf417.png` na sua área de trabalho. Abrir o arquivo mostra um código de barras MicroPdf417 nítido que codifica o texto `"Åspóse.Barcóde©"`.

## Verificando o código de barras

Para confirmar que o código de barras foi gerado corretamente:

1. Abra o PNG em qualquer visualizador de imagens.
2. Use um aplicativo móvel de leitura de códigos de barras que suporte PDF417 ou MicroPdf417.
3. Escaneie a imagem; o aplicativo deve exibir o texto original, incluindo os caracteres especiais.

Se o leitor falhar, verifique o seguinte:

* **X‑dimensão:** Valores abaixo de 1 px podem causar artefatos de renderização.
* **Contagem de colunas:** Valores fora de 1‑4 disparam uma exceção.
* **Conjunto de caracteres:** Aspose.Barcode suporta UTF‑8; certifique‑se de que o arquivo fonte esteja salvo com codificação UTF‑8.

## Variações comuns e casos extremos

### Gerando outras simbologias

Se você quiser **criar código de barras com Aspose** para QR codes, Code128 ou UPC, substitua `EncodeTypes.MicroPdf417` pelo valor enum apropriado, por exemplo:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

Todas as demais etapas de configuração (X‑dimensão, salvamento) permanecem as mesmas.

### Alterando o formato da imagem

Aspose.Barcode suporta múltiplos formatos raster. Para exportar como JPEG com 90 % de qualidade:

```csharp
generator.Save(outputPath, BarCodeImageFormat.Jpeg, 90);
```

### Manipulando grandes cargas de dados

MicroPdf417 pode armazenar até 1 KB de dados. Para cargas maiores, troque para o `EncodeTypes.Pdf417` completo e ajuste `Rows` e `Columns` conforme necessário.

### Unicode e caracteres especiais

A biblioteca codifica automaticamente strings Unicode. Contudo, alguns leitores legados reconhecem apenas ASCII. Se você direcionar esses dispositivos, limite a entrada ao intervalo ASCII ou use uma simbologia diferente que garanta compatibilidade.

## Dicas profissionais para uso em produção

* **Cache o gerador** ao gerar muitos códigos de barras com as mesmas configurações – isso reduz a sobrecarga de criação de objetos.
* **Defina `Resolution`** (`generator.Parameters.ImageResolution`) para 300 dpi para saída de impressão de alta qualidade.
* **Habilite correção de erro** para códigos 2‑D (`generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel`) para melhorar a confiabilidade de leitura em mídia danificada.
* **Envolva a lógica de salvamento** em um bloco `try / catch` para tratar exceções de I/O, especialmente ao gravar em compartilhamentos de rede.

## Conclusão

Agora você sabe **como gerar código de barras** usando Aspose.Barcode em C#. O tutorial cobriu a instalação do pacote NuGet, a criação de um `BarcodeGenerator`, a configuração de dimensões e colunas e o salvamento do resultado como imagem PNG. Com essa base você pode **criar código de barras com Aspose** para qualquer simbologia suportada, ajustar parâmetros visuais e integrar a geração de códigos de barras em soluções .NET maiores.

Pronto para explorar mais? Experimente gerar QR codes para encurtamento de URLs, incorporar códigos de barras em relatórios PDF usando Aspose.PDF ou automatizar a criação em lote de códigos de barras para gerenciamento de inventário. Cada novo cenário se baseia nos mesmos conceitos centrais demonstrados aqui. Feliz codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar código de barras PDF417 com Aspose – Guia completo](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Como gerar códigos DataMatrix usando Aspose.BarCode para .NET – Guia passo a passo](/barcode/english/net/datamatrix-barcode-configuration/)
- [Como gerar imagem de código de barras com Aspose.BarCode em C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}