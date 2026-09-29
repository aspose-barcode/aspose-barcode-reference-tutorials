---
category: general
date: 2026-08-22
description: Como gerar código de barras rapidamente e aprender como alterar o tamanho
  do código de barras ao exportar a imagem do código de barras como PNG usando Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- change barcode size
- export barcode image
language: pt
lastmod: 2026-08-22
og_description: Como gerar código de barras em C# e alterar facilmente o tamanho do
  código de barras antes de exportar a imagem como PNG. Siga este guia completo.
og_image_alt: Screenshot showing how to generate barcode with Aspose.BarCode in C#
og_title: Como gerar imagens de código de barras com tamanho personalizado em C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode quickly and learn how to change barcode size
    while exporting the barcode image as PNG using Aspose.BarCode.
  headline: How to generate barcode images with custom size in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Como gerar imagens de código de barras com tamanho personalizado em C#
url: /pt/python-java/general/how-to-generate-barcode-images-with-custom-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como gerar imagens de código de barras com tamanho personalizado em C#

Se você precisa **gerar código de barras** para automação postal, rastreamento de inventário ou ingressos de eventos, este guia mostra uma solução completa, pronta‑para‑executar em C#. Você também aprenderá **como alterar o tamanho do código de barras** e **exportar imagens do código de barras** em formato PNG sem sair do seu IDE.

Usaremos a biblioteca Aspose.BarCode porque ela suporta a simbologia OneCode, permite controlar as dimensões pixel a pixel e lida com a exportação de imagens com uma única chamada de método. Ao final do tutorial você terá quatro arquivos PNG — cada um representando um código de barras OneCode com um número diferente de dígitos.

## Pré-requisitos

- .NET 6.0 ou posterior (o código também funciona com .NET Framework 4.6+)
- Visual Studio 2022 (ou qualquer editor C# de sua preferência)
- Uma referência NuGet para **Aspose.BarCode** (`Install-Package Aspose.BarCode`)
- Familiaridade básica com a sintaxe C#

> **Dica profissional:** Se você está avaliando a biblioteca, a Aspose oferece um teste gratuito de 30 dias que inclui todos os recursos de código de barras.

## Etapa 1: Configurar um projeto de console minimalista

Crie um novo aplicativo de console e adicione o pacote Aspose.BarCode:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

O `Program.cs` gerado conterá toda a lógica de geração de código de barras.

## Etapa 2: Como gerar código de barras – criar um método reutilizável

A seguir está um método autônomo que recebe a string de dados, o nome de arquivo desejado e parâmetros de tamanho opcionais. Este método demonstra o padrão central de **gerar código de barras**.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Example calls for different digit lengths
            GenerateOneCode("12345678901234567890", "PostalOneCodeBarcode20Digits.png");
            GenerateOneCode("1234567890123456789012345", "PostalOneCodeBarcode25Digits.png");
            GenerateOneCode("12345678901234567890123456789", "PostalOneCodeBarcode29Digits.png");
            GenerateOneCode("1234567890123456789012345678901", "PostalOneCodeBarcode31Digits.png");
        }

        /// <summary>
        /// Generates a OneCode barcode, applies size settings, and saves as PNG.
        /// </summary>
        /// <param name="data">Numeric string to encode (OneCode supports 20‑31 digits).</param>
        /// <param name="fileName">Target PNG file name.</param>
        /// <param name="xDimension">Width of a single module in pixels (default 4).</param>
        /// <param name="barHeight">Height of the barcode in pixels (default 50).</param>
        static void GenerateOneCode(string data, string fileName,
                                    int xDimension = 4, int barHeight = 50)
        {
            // 1️⃣ Initialize the generator for OneCode symbology
            var generator = new BarcodeGenerator(EncodeTypes.OneCode, data);

            // 2️⃣ **Change barcode size** – adjust module width and total height
            generator.Parameters.Barcode.XDimension.Pixels = xDimension; // module width
            generator.Parameters.Barcode.BarHeight.Pixels = barHeight;   // overall height

            // 3️⃣ **Export barcode image** as PNG; you can also choose JPEG, BMP, etc.
            generator.Save(fileName, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {fileName}");
        }
    }
}
```

### Por que este método é importante

- **Encapsulamento:** Todas as configurações relacionadas ao tamanho ficam em um único local, tornando trivial chamar o método com diferentes dimensões.
- **Reusabilidade:** Você pode reutilizar o mesmo método para qualquer comprimento de string OneCode, o que é essencial porque OneCode aceita apenas de 20 a 31 dígitos.
- **Clareza:** Comentários rotulados com emojis guiam os leitores pelas três fases lógicas — inicialização, alteração de tamanho e exportação.

## Etapa 3: Alterar o tamanho do código de barras para diferentes requisitos

Às vezes um scanner espera um código de barras mais alto, ou um layout de impressão exige um módulo mais estreito. A propriedade `XDimension.Pixels` controla a largura de um único módulo do código de barras, enquanto `BarHeight.Pixels` define a altura total.

```csharp
// Example: generate a larger barcode (8‑pixel modules, 80‑pixel height)
GenerateOneCode(
    data: "12345678901234567890",
    fileName: "LargeOneCode.png",
    xDimension: 8,
    barHeight: 80);
```

**Pontos-chave ao alterar o tamanho:**

- **Dimensão X mínima:** 1 pixel é tecnicamente permitido, mas a maioria dos scanners precisa de pelo menos 2 pixels para leitura confiável.
- **Altura máxima:** Não há limite rígido, mas códigos de barras muito altos podem exceder a área imprimível em etiquetas padrão.
- **Proporção:** Mantenha a proporção altura‑para‑largura‑do‑módulo equilibrada (≈12‑15 × largura do módulo) para evitar distorção.

## Etapa 4: Exportar imagem do código de barras em outros formatos (opcional)

O método `Save` aceita vários valores `BarCodeImageFormat`: `Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`. Se precisar de um formato vetorial sem perdas, pode exportar para `Svg` instead.

```csharp
// Export to SVG for infinite scaling
generator.Save("OneCode.svg", BarCodeImageFormat.Svg);
```

Exportar como PNG é a escolha mais comum porque preserva bordas nítidas e é amplamente suportado por navegadores web e pipelines de impressão.

## Saída esperada

Executar o programa cria quatro arquivos PNG na pasta do projeto:

- `PostalOneCodeBarcode20Digits.png` – código de barras OneCode de 20 dígitos
- `PostalOneCodeBarcode25Digits.png` – código de barras OneCode de 25 dígitos
- `PostalOneCodeBarcode29Digits.png` – código de barras OneCode de 29 dígitos
- `PostalOneCodeBarcode31Digits.png` – código de barras OneCode de 31 dígitos

Cada imagem terá aparência semelhante ao placeholder abaixo (o gráfico real depende dos dados numéricos que você forneceu).

![Exemplo de como gerar código de barras](https://example.com/placeholder.png "Exemplo de como gerar código de barras")

*O texto alternativo da imagem inclui a palavra‑chave principal para acessibilidade e SEO.*

## Perguntas comuns e casos extremos

| Pergunta | Resposta |
|----------|----------|
| **E se a string de dados for mais curta que 20 dígitos?** | OneCode requer no mínimo 20 dígitos. Preencha a string com zeros à esquerda ou use uma simbologia diferente (por exemplo, Code128). |
| **Posso gerar códigos de barras em um ambiente multithread?** | Sim. `BarcodeGenerator` não é thread‑safe, portanto instancie um gerador separado por thread. |
| **Como definir uma cor de fundo?** | Use `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.White;` antes de chamar `Save`. |
| **Existe uma maneira de incorporar a imagem diretamente em uma página HTML?** | Salve a imagem em um `MemoryStream`, converta para Base64 e incorpore com `<img src="data:image/png;base64,..." />`. |

## Conclusão

Agora você sabe **como gerar imagens de código de barras** em C# com Aspose.BarCode, como **alterar o tamanho do código de barras** ajustando a X‑dimension e a altura das barras, e como **exportar imagens de código de barras** em formatos PNG (ou outros). O método reutilizável `GenerateOneCode` permite criar qualquer código de barras OneCode entre 20 e 31 dígitos com uma única linha de código.

- Experimentar outras simbologias (`EncodeTypes.Code128`, `EncodeTypes.QR`).
- Integrar o gerador em uma API web que retorne imagens de código de barras sob demanda.
- Combinar a saída PNG com uma biblioteca PDF para incorporar códigos de barras em etiquetas de envio.

Feliz codificação, e sinta-se à vontade para compartilhar suas próprias variações nos comentários!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Como gerar códigos de barras DataMatrix usando Aspose.BarCode para .NET – Guia passo a passo](/barcode/english/net/datamatrix-barcode-configuration/)
- [Como gerar código de barras Aztec com proporção personalizada usando Aspose.BarCode para .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Como gerar e ajustar a altura do código de barras para Databar unidimensional usando Aspose.BarCode para .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}