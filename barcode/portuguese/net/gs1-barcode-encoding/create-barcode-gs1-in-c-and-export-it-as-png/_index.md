---
category: general
date: 2026-09-29
description: Crie código de barras GS1 em C# e gere imagens PNG de código de barras
  usando BarcodeGenerator. Siga um guia passo a passo para exportar a imagem do código
  de barras de forma eficiente.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode gs1
- generate barcode png
- barcode generator c#
- how to generate barcode
- export barcode image
language: pt
lastmod: 2026-09-29
og_description: Crie código de barras GS1 em C# e gere arquivos PNG de código de barras
  com BarcodeGenerator. Siga este guia completo para exportar a imagem do código de
  barras rapidamente.
og_image_alt: Generated GS1 MicroPDF417 barcode saved as a PNG file
og_title: Crie código de barras GS1 em C# – exporte como PNG em minutos
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create barcode GS1 in C# and generate barcode PNG images using BarcodeGenerator.
    Follow a step‑by‑step guide to export barcode image efficiently.
  headline: Create barcode GS1 in C# and export it as PNG
  type: TechArticle
tags:
- barcode
- C#
- GS1
- PNG
- Aspose
title: Criar código de barras GS1 em C# e exportá-lo como PNG
url: /pt/net/gs1-barcode-encoding/create-barcode-gs1-in-c-and-export-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar código de barras GS1 em C# e exportá‑lo como PNG

Se você precisa **criar código de barras GS1** em uma aplicação .NET, este guia mostra exatamente como fazer isso. Você verá uma solução concisa que gera uma imagem PNG do código de barras e exporta a imagem para o disco, tudo com a classe `BarcodeGenerator` do Aspose.BarCode.

Gerar um código de barras GS1 é uma necessidade comum para inventário, envio e sistemas de ponto de venda. Ao final deste tutorial você será capaz de escrever um pequeno programa em C# que cria um código de barras MicroPDF417 compatível com GS1 e o salva como um arquivo PNG de alta qualidade.

## Prerequisitos

Antes de começar, certifique‑se de que você tem:

* **.NET 6** (ou qualquer versão posterior do .NET) instalado.
* **Visual Studio 2022** ou qualquer IDE que suporte C#.
* O pacote NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`) – ele fornece a API `BarcodeGenerator` usada nos exemplos.
* Familiaridade básica com a sintaxe C#.

> **Dica profissional:** Use a edição comunitária gratuita do Aspose.BarCode ao experimentar; a versão completa remove quaisquer marcas d'água de avaliação.

## Etapa 1 – Criar código de barras GS1 com BarcodeGenerator

A primeira coisa que você precisa é instanciar o `BarcodeGenerator` para o formato *MicroPDF417* e alimentá‑lo com uma string de dados GS1. Os Identificadores de Aplicação GS1 (AIs) são envoltos em parênteses, por exemplo `(01)` para GTIN‑14 e `(21)` para um número de série.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// GS1 data: (01) – GTIN‑14, (21) – serial number
string gs1Data = "(01)12345678901234(21)ABC123";

// Initialise the generator for MicroPDF417 (GS1 compatible)
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);
```

**Por que isso importa:**  
`EncodeTypes.MicroPdf417` trata automaticamente a entrada como dados GS1 quando a string contém AIs válidos. Isso garante que o código de barras gerado esteja em conformidade com a especificação GS1 sem configuração extra.

## Etapa 2 – Definir dimensões do código de barras para tamanho ideal

O tamanho visual de um código de barras é controlado pela sua **X‑dimension** (a largura de um único módulo). Ajustar `XDimension.Pixels` permite afinar o tamanho final da imagem enquanto preserva a legibilidade.

```csharp
// Set the module width to 2 pixels – a good balance for screen and print
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Como gerar PNG do código de barras** – A X‑dimension não afeta os dados codificados; ela apenas altera as dimensões físicas da imagem gerada. Se precisar de um código de barras maior para impressão em alta resolução, aumente esse valor (ex.: `3` ou `4`).

## Etapa 3 – Gerar PNG do código de barras e exportar a imagem

Agora você pode renderizar o código de barras e gravá‑lo em um arquivo PNG. O método `Save` recebe o caminho de destino e o formato de imagem desejado.

```csharp
// Define the output folder (ensure it exists)
string outputFolder = Path.Combine(Environment.CurrentDirectory, "output");
Directory.CreateDirectory(outputFolder);

// Export the barcode image as PNG
string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
generator.Save(pngPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode image saved to: {pngPath}");
```

**O que acontece nos bastidores:**  
`BarcodeGenerator.Save` rasteriza o código de barras em um bitmap, aplica a X‑dimension definida anteriormente e codifica o bitmap como um arquivo PNG. O arquivo resultante pode ser usado diretamente em páginas web, impresso em etiquetas ou incorporado em PDFs.

## Exemplo completo de código fonte

Abaixo está um aplicativo de console completo e autocontido que você pode copiar, colar e executar. Ele demonstra **como gerar PNG de código de barras**, **exportar a imagem do código de barras** e inclui tratamento básico de erros.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Gs1BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // 1️⃣ Initialise the barcode generator for GS1 MicroPDF417
                string gs1Data = "(01)12345678901234(21)ABC123";
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.MicroPdf417, gs1Data);

                // 2️⃣ Adjust X‑dimension to control the visual size
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // 3️⃣ Prepare output folder
                string outputFolder = Path.Combine(
                    Environment.CurrentDirectory, "output");
                Directory.CreateDirectory(outputFolder);

                // 4️⃣ Save the barcode as PNG (export barcode image)
                string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
                generator.Save(pngPath, BarCodeImageFormat.Png);

                Console.WriteLine($"✅ Barcode created and saved as PNG:");
                Console.WriteLine(pngPath);
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error: {ex.Message}");
            }
        }
    }
}
```

### Saída esperada

Ao executar o programa, você deverá ver:

```
✅ Barcode created and saved as PNG:
C:\Path\To\Your\App\output\GS1MicroPdf417.png
```

Abrir o arquivo PNG exibe um código de barras **GS1 MicroPDF417** nítido que codifica o GTIN‑14 `12345678901234` e o número de série `ABC123`. Escaneá‑lo com qualquer leitor compatível com GS1 retornará a string de dados original.

## Armadilhas comuns e boas práticas

| Problema | Por que acontece | Como evitar |
|----------|------------------|-------------|
| **Formatação incorreta do AI** | Parênteses ausentes ou ordem errada tornam o código de barras não‑GS1. | Sempre envolva cada AI em parênteses, ex.: `(01)`. |
| **X‑dimension muito pequena** | O código de barras fica ilegível em dispositivos de baixa resolução. | Mantenha `XDimension.Pixels` ≥ 2 para a maioria das impressoras; aumente para saída em alta DPI. |
| **Pasta de saída inexistente** | `Save` lança `DirectoryNotFoundException`. | Use `Directory.CreateDirectory` antes de chamar `Save`. |
| **Uso do EncodeType errado** | Alguns tipos (ex.: `Code128`) não suportam dados GS1 nativamente. | Escolha `EncodeTypes.MicroPdf417` ou qualquer tipo compatível com GS1. |
| **Referência NuGet ausente** | Erros de compilação como `The type or namespace name 'Aspose' could not be found`. | Instale o pacote `Aspose.BarCode` via NuGet. |

## Expandindo o exemplo

* **Formatos de imagem diferentes** – Substitua `BarCodeImageFormat.Png` por `Jpeg`, `Gif` ou `Bmp` se precisar de outro formato.
* **Saída em alta resolução** – Defina `generator.Parameters.ImageResolution.DpiX` e `DpiY` antes de salvar.
* **Incorporação em PDF** – Use `Aspose.Pdf` para colocar o PNG em uma fatura ou etiqueta PDF.

## Conclusão

Agora você sabe como **criar código de barras GS1** em C# usando o `BarcodeGenerator` do Aspose.BarCode, **gerar PNG do código de barras** e **exportar a imagem do código de barras** para o sistema de arquivos. O guia cobriu cada passo — desde a inicialização do gerador com dados GS1, ajuste da X‑dimension, até a gravação do arquivo PNG final — abordando erros comuns e oferecendo ideias de extensão.

Sinta‑se à vontade para experimentar outros Identificadores de Aplicação GS1, diferentes simbologias de código de barras ou imagens em resolução maior. Quando dominar esses conceitos básicos, gerar códigos de barras compatíveis para inventário, envio ou varejo se tornará uma tarefa rotineira em sua caixa de ferramentas .NET.

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [Create barcode PNG in C# – step‑by‑step guide](/barcode/english/python-java/general/create-barcode-png-in-c-step-by-step-guide/)
- [Create barcode image in C# – complete programming guide](/barcode/english/python-java/general/create-barcode-image-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}