---
category: general
date: 2026-09-29
description: O guia do gerador de códigos de barras em C# mostra como gerar um código
  de barras MicroPdf417, alterar dimensões, definir colunas e personalizar o tamanho
  do código de barras em apenas algumas linhas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to generate barcode
- how to change dimensions
- how to set columns
- customize barcode size
language: pt
lastmod: 2026-09-29
og_description: Guia do gerador de códigos de barras C# mostra como gerar um código
  de barras MicroPdf417, alterar dimensões, definir colunas e personalizar o tamanho
  do código de barras em apenas algumas linhas.
og_image_alt: Screenshot of a MicroPdf417 barcode generated with a C# barcode generator
og_title: Guia do gerador de código de barras C# – crie e personalize MicroPdf417
schemas:
- author: GroupDocs
  dateModified: '2026-09-29'
  description: Barcode generator C# guide shows how to generate a MicroPdf417 barcode,
    change dimensions, set columns, and customize barcode size in just a few lines.
  headline: 'Barcode generator C# guide: create MicroPdf417'
  type: TechArticle
tags:
- barcode
- C#
- MicroPdf417
- barcode generation
title: 'Guia do gerador de código de barras C#: criar MicroPdf417'
url: /pt/net/compact-pdf417-encoding/barcode-generator-c-guide-create-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Guia de barcode generator C#: criar MicroPdf417

Se você precisa de um **barcode generator C#** para seu projeto .NET, este tutorial orienta você a criar um código de barras MicroPdf417 do zero. Você aprenderá **como gerar barcode**, alterar dimensões, definir colunas e **personalizar o tamanho do barcode** com facilidade.

MicroPdf417 é uma simbologia 2‑D compacta que funciona bem para rotular pequenas peças, ingressos ou etiquetas de inventário. Ao final deste guia você terá um aplicativo console completo e executável que gera uma imagem PNG do código de barras, e entenderá como cada parâmetro influencia o tamanho final.

## Pré-requisitos

Antes de começar, certifique-se de que você tem:

* .NET 6.0 SDK ou posterior (o código também funciona com .NET Framework 4.7+)
* Uma IDE compatível com C# (Visual Studio, VS Code, Rider, etc.)
* O pacote NuGet **GroupDocs.Barcode** – instale-o com  

  ```bash
  dotnet add package GroupDocs.Barcode
  ```

Nenhuma ferramenta externa adicional é necessária; a biblioteca cuida da codificação, renderização e gravação do arquivo.

## Barcode generator C#: inicializando o gerador

O primeiro passo é criar uma instância de `BarcodeGenerator` e especificar a simbologia (`EncodeTypes.MicroPdf417`) junto com os dados que você deseja codificar.

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // Subsequent configuration steps go here...

            // Save the final image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

**Por que isso importa:**  
`BarcodeGenerator` é o ponto de entrada para todas as operações de barcode. O construtor associa o **EncodeTypes** escolhido (MicroPdf417) à string de dados bruta. A biblioteca lida automaticamente com caracteres Unicode como “Å” e “©”, portanto você não precisa de lógica de codificação extra.

## Como alterar as dimensões do barcode

A legibilidade de um barcode depende muito da largura do módulo (a dimensão X). Definir um valor maior em pixels torna as barras mais largas e a imagem mais fácil de escanear, especialmente em telas de baixa resolução.

```csharp
// Step 2 – adjust the X‑dimension (module width) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Explicação:**  
`XDimension.Pixels` controla a largura de um único módulo do barcode. O padrão é 1 pixel, o que pode parecer fino em monitores de alta DPI. Aumentá‑lo para 2 pixels dobra a largura total sem afetar os dados codificados.

**Dica:** Se você pretende imprimir o barcode a 300 dpi, um valor de 3 ou 4 pixels costuma oferecer o melhor equilíbrio entre tamanho e confiabilidade de leitura.

## Como definir colunas para controle de tamanho

MicroPdf417 permite especificar o número de colunas (até 4). Menos colunas produzem um barcode mais alto; mais colunas o tornam mais largo, porém mais curto. Ajustar esse valor é a principal forma de **personalizar o tamanho do barcode**.

```csharp
// Step 3 – set the maximum number of columns (4 is the limit for MicroPdf417)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Por que isso funciona:**  
A propriedade `Pdf417.Columns` é compartilhada por todas as simbologias baseadas em PDF417, incluindo MicroPdf417. Definir o máximo (4) distribui os dados na disposição mais larga possível, reduzindo a altura total. Se precisar de uma altura mais compacta, diminua a contagem de colunas para 2 ou 3.

**Caso especial:** Quando a string de dados é longa, a biblioteca pode aumentar automaticamente as linhas para acomodar o conteúdo, independentemente da contagem de colunas. Mantenha a carga útil abaixo de 50 caracteres para dimensionamento previsível.

## Personalize o tamanho do barcode para diferentes saídas

Além da dimensão X e das colunas, você pode influenciar o tamanho final da imagem selecionando um formato de imagem adequado e DPI. PNG é sem perdas, perfeito para exibição web, enquanto BMP ou TIFF podem ser preferíveis para impressão de alta qualidade.

```csharp
// Step 4 – save as PNG (lossless) with default 96 dpi
generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
```

Se precisar de um DPI maior, pode defini‑lo explicitamente:

```csharp
generator.Parameters.Image.DpiX = 300;
generator.Parameters.Image.DpiY = 300;
generator.Save("MicroPdf417_300dpi.png", BarCodeImageFormat.Png);
```

**Resultado:** O arquivo PNG salvo contém um barcode MicroPdf417 nítido que respeita as dimensões configuradas. Abra o arquivo em qualquer visualizador de imagens para verificar o tamanho visual.

### Saída esperada

Executar o programa gera um arquivo chamado **MicroPdf417.png** (ou **MicroPdf417_300dpi.png** se você definiu DPI). O barcode terá aparência semelhante à ilustração abaixo:

![Barcode generator C# output showing a MicroPdf417 PNG](barcode-micro-pdf417.png)

*Texto alternativo:* *Saída do barcode generator C# mostrando um PNG MicroPdf417*

Escaneando a imagem com um leitor padrão de códigos 2‑D, o resultado será a string original `Åspóse.Barcóde©`.

## Código-fonte completo para copiar e colar rapidamente

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // 2️⃣ Change dimensions – make modules 2 pixels wide
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set columns – use the maximum of 4 for a wider, shorter barcode
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // (Optional) Increase DPI for high‑resolution output
            // generator.Parameters.Image.DpiX = 300;
            // generator.Parameters.Image.DpiY = 300;

            // 4️⃣ Save the barcode as a PNG image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

Copie o código para um novo projeto console, restaure os pacotes NuGet e execute `dotnet run`. O console confirmará a localização da imagem e você verá o barcode gerado na pasta do seu projeto.

## Perguntas frequentes e solução de problemas

| Pergunta | Resposta |
|----------|----------|
| **E se o barcode ficar borrado?** | Aumente `XDimension.Pixels` ou o DPI (`Parameters.Image.DpiX/Y`). Ambos ampliam os módulos e melhoram a fidelidade visual. |
| **Posso usar um formato de imagem diferente?** | Sim. Substitua `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` ou `Tiff`. PNG continua sendo a escolha mais segura para qualidade sem perdas. |
| **Meus dados contêm emojis — eles serão codificados?** | MicroPdf417 suporta UTF‑8, então a maioria dos emojis é codificada corretamente. Se encontrar erros, verifique se a string está devidamente normalizada (`System.Text.Encoding.UTF8`). |
| **Como gerar outras simbologias?** | Altere `EncodeTypes.MicroPdf417` para qualquer outro valor de `EncodeTypes` ( |

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [How to Generate Barcode Image in C# – MicroPdf417 Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)
- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}