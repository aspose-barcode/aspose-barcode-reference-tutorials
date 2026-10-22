---
category: general
date: 2026-10-21
description: Gere código de barras pdf417 rapidamente em C#. Aprenda como gerar código
  de barras pdf417 com layout personalizado, colunas, linhas e saída PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- pdf417 barcode layout
- barcode generator C#
- save barcode as PNG
language: pt
lastmod: 2026-10-21
og_description: Gere código de barras pdf417 em C#. Siga este tutorial para aprender
  como gerar código de barras pdf417 com colunas e linhas personalizadas e saída em
  PNG.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: Gerar código de barras PDF417 em C# – guia completo passo a passo
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  headline: Generate pdf417 barcode in C# with custom columns and rows
  type: TechArticle
- description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  name: Generate pdf417 barcode in C# with custom columns and rows
  steps:
  - name: Open the PNG file in any image viewer.
    text: Open the PNG file in any image viewer.
  - name: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
    text: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
  - name: Confirm that the decoded text matches the original input.
    text: Confirm that the decoded text matches the original input.
  type: HowTo
tags:
- barcode
- pdf417
- C#
- image generation
title: Gerar código de barras pdf417 em C# com colunas e linhas personalizadas
url: /pt/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-with-custom-columns-and-rows/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerar código de barras pdf417 em C# – guia completo de programação

Se você precisa **gerar código de barras pdf417** em uma aplicação .NET, este guia mostra como fazer isso com poucas linhas de código. Você verá um exemplo prático que configura o número de colunas e linhas e, em seguida, salva o resultado como uma imagem PNG. A mesma abordagem funciona para qualquer texto que você queira codificar, podendo ser adaptada para notas fiscais, ingressos ou crachás.

Gerar um **código de barras pdf417** costuma parecer uma tarefa separada do restante do seu código. Ao final deste tutorial, você entenderá por que os parâmetros de layout são importantes, como controlar a qualidade da imagem e quais chamadas de biblioteca são necessárias para **gerar código de barras pdf417** de forma confiável.

## O que você precisará

Antes de começar, certifique‑se de que tem:

* SDK .NET 6.0 ou posterior instalado  
* Uma IDE compatível com C# (Visual Studio, VS Code, Rider, etc.)  
* O pacote NuGet **Aspose.BarCode for .NET** (ou qualquer biblioteca de código de barras compatível)  

Você pode adicionar a biblioteca com o seguinte comando:

```bash
dotnet add package Aspose.BarCode
```

A biblioteca fornece a classe `BarcodeGenerator` usada ao longo deste tutorial.

## Etapa 1: Criar uma instância do gerador de código de barras

A primeira linha cria um objeto que sabe **gerar código de barras pdf417**. Você deve especificar o tipo de codificação (`EncodeTypes.Pdf417`) e o texto que deseja codificar.

```csharp
using Aspose.BarCode.Generation;

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample Text");
```

*Por que esta etapa importa* – O `BarcodeGenerator` encapsula todas as configurações do código de barras. Instanciá‑lo com o `EncodeTypes` correto indica ao motor que deve usar a simbologia PDF417 em vez de QR, Code128 ou outros formatos.

## Etapa 2: Configurar o layout PDF417

O PDF417 permite controlar o número de colunas e linhas, o que influencia diretamente o tamanho e a densidade do código de barras. Ajustar esses valores é o núcleo de **como gerar código de barras pdf417** com um layout personalizado.

```csharp
// Set the number of data columns (valid range: 2‑30)
generator.Parameters.Barcode.Pdf417.Columns = 4;

// Set the number of rows (up to 90 rows)
generator.Parameters.Barcode.Pdf417.Rows = 9;
```

*Por que você pode mudar esses valores* – Mais colunas reduzem a altura do código de barras, enquanto mais linhas aumentam a largura. Escolha valores que se adequem ao dispositivo de leitura alvo e à área de impressão disponível.

> **Dica profissional:** Se você omitir as linhas, a biblioteca calcula automaticamente a contagem ideal com base no tamanho dos dados. Definir explicitamente as linhas é útil quando você precisa de um tamanho de imagem fixo para layouts de UI.

## Etapa 3: Escolher um formato de imagem e salvar o arquivo

Depois de configurar o layout, você pode renderizar o código de barras para uma imagem. O exemplo abaixo salva o código de barras como um arquivo PNG, mas você também pode selecionar JPEG, BMP ou TIFF.

```csharp
using Aspose.BarCode;
using System.IO;

// Define the output path – replace with your actual directory
string outputPath = Path.Combine("C:\\Barcodes", "CustomLayout.png");

// Save the barcode image as PNG
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Quando o código for executado, `CustomLayout.png` conterá um **código de barras pdf417** nítido que corresponde às configurações de coluna/linha que você forneceu.

### Saída esperada

Abrir `CustomLayout.png` mostra um código de barras retangular com quatro colunas de dados e nove linhas. Escanear a imagem com qualquer leitor PDF417 devolve o texto original **“Sample Text”**.

![Exemplo de código de barras PDF417 gerado](generated-pdf417.png){: .center-image alt="Código de barras pdf417 gerado salvo como um arquivo PNG"}

## Etapa 4: Exemplo completo e executável

A seguir, um aplicativo de console autocontido que reúne todas as partes. Copie o código para um novo projeto `.csproj` e execute‑o — nenhum arquivo adicional é necessário.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample Text for PDF417 barcode");

            // 2️⃣ Configure layout – custom columns and rows
            generator.Parameters.Barcode.Pdf417.Columns = 4; // 2‑30
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // up to 90

            // Optional: increase image resolution for sharper output
            generator.Parameters.ImageResolution = 300; // DPI

            // 3️⃣ Define the output location
            string folder = Path.Combine(Environment.CurrentDirectory, "output");
            Directory.CreateDirectory(folder);
            string filePath = Path.Combine(folder, "CustomLayout.png");

            // 4️⃣ Save as PNG
            generator.Save(filePath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode generated at: {filePath}");
        }
    }
}
```

Executar o programa imprime uma linha de confirmação e cria o arquivo PNG dentro de uma subpasta `output`. A imagem pode ser incorporada em relatórios, impressa em etiquetas ou enviada para um dispositivo móvel para leitura.

## Variações comuns e casos de borda

| Cenário | O que mudar | Por que importa |
|----------|----------------|----------------|
| **Codificar uma string longa** | Aumentar `Rows` ou deixar a biblioteca auto‑calcular omitindo a atribuição de `Rows` | PDF417 pode armazenar até 1.850 caracteres; linhas insuficientes causam truncamento |
| **Qualidade visual superior** | Definir `generator.Parameters.ImageResolution` para 600 DPI | Útil para impressão em impressoras de alta resolução |
| **Formato de imagem diferente** | Substituir `BarCodeImageFormat.Png` por `Jpeg` ou `Tiff` | JPEG reduz o tamanho do arquivo; TIFF preserva dados sem perdas para arquivamento |
| **Adicionar zona silenciosa** | `generator.Parameters.Barcode.XDimension = 2;` (ou ajustar `Margins`) | Zonas silenciosas melhoram a confiabilidade do scanner em ambientes ruidosos |
| **Texto dinâmico a partir da entrada do usuário** | Substituir a string fixa por `Console.ReadLine()` | Permite geração em tempo de execução baseada nos dados do usuário |

### Como gerar código de barras pdf417 em uma API web

Se precisar expor a geração de código de barras através de um endpoint ASP.NET Core, retorne a imagem como um array de bytes:

```csharp
[HttpGet("api/barcode/pdf417")]
public IActionResult GetPdf417([FromQuery] string data)
{
    var generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
    generator.Parameters.Barcode.Pdf417.Columns = 5;
    generator.Parameters.Barcode.Pdf417.Rows = 10;

    using var ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return File(ms.ToArray(), "image/png");
}
```

Este trecho responde **como gerar código de barras pdf417** sob demanda sem gravar em disco, ideal para microsserviços ou back‑ends móveis.

## Testando o código de barras gerado

Para verificar se o código de barras foi criado corretamente:

1. Abra o arquivo PNG em qualquer visualizador de imagens.  
2. Use um aplicativo gratuito de scanner PDF417 (por exemplo, ZXing, PDF417 Decoder) para escanear a imagem.  
3. Confirme que o texto decodificado corresponde à entrada original.

Se o scanner relatar erros, verifique novamente os valores de coluna/linha e assegure‑se de que a resolução da imagem seja alta o suficiente para seu dispositivo.

## Conclusão

Agora você sabe como **gerar código de barras pdf417** em C# com controle total sobre colunas, linhas e formato de saída. O exemplo completo demonstra todo o fluxo — da criação do `BarcodeGenerator` ao salvamento de um arquivo PNG — para que você possa integrar a criação de códigos de barras em qualquer projeto .NET.

Em seguida, explore tópicos relacionados como otimização de **layout de código de barras pdf417**, incorporação de códigos de barras em relatórios PDF ou decodificação de códigos de barras em dispositivos móveis. Ajustar os níveis de correção de erro e experimentar diferentes resoluções de imagem ajudará a afinar a solução para seu caso de uso específico. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to generate PDF417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}