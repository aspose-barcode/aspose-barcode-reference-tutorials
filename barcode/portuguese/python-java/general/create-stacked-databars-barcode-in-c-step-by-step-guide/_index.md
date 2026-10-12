---
category: general
date: 2026-10-02
description: Crie códigos de barras de barras de dados empilhadas em C# rapidamente.
  Aprenda a definir XDimension, ajustar a proporção da imagem e exportar imagens PNG
  com um gerador de códigos de barras.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create stacked databars barcode
- C# barcode generator
- DataBar stacked omnidirectional
- barcode aspect ratio
- XDimension pixel size
- BarCodeImageFormat PNG
language: pt
lastmod: 2026-10-02
og_description: Crie código de barras de barras de dados empilhadas em C# com um exemplo
  completo de código. Ajuste XDimension, altere a proporção e salve arquivos PNG em
  apenas algumas linhas.
og_image_alt: Screenshot showing a create stacked databars barcode example generated
  with C#
og_title: Crie código de barras de barras de dados empilhadas em C# – tutorial rápido
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create stacked databars barcode in C# quickly. Learn to set XDimension,
    adjust aspect ratio, and export PNG images with a barcode generator.
  headline: Create stacked databars barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- Aspose
- image generation
title: Criar código de barras de barras de dados empilhadas em C# – guia passo a passo
url: /pt/python-java/general/create-stacked-databars-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar código de barras stacked databars em C# – guia passo a passo

Se você precisa **criar código de barras stacked databars** em um projeto .NET, este tutorial mostra exatamente como fazer. Você verá como configurar a X‑dimension, alterar as proporções e salvar o resultado como arquivos PNG — tudo com a biblioteca Aspose.BarCode.

Gerar um código de barras stacked DataBar não requer um pipeline gráfico complexo. Ao final deste guia, você terá duas imagens PNG prontas para uso que ilustram diferentes proporções, e entenderá por que esses parâmetros são importantes para a confiabilidade da leitura.

## O que você precisará

- .NET 6.0 ou posterior (o código também funciona com .NET Framework 4.6+)
- Visual Studio 2022 ou qualquer IDE C#
- **Aspose.BarCode for .NET** pacote NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Permissão de gravação em uma pasta onde os arquivos PNG serão salvos

## Etapa 1: Configurar o projeto e importar namespaces

Crie um novo aplicativo de console (ou adicione o código a um projeto existente) e importe os namespaces necessários:

```csharp
using System;
using Aspose.BarCode.Generation;   // BarcodeGenerator lives here
using Aspose.BarCode;               // BarCodeImageFormat enum
```

> **Por que isso importa:** `Aspose.BarCode.Generation` fornece a classe `BarcodeGenerator`, enquanto `Aspose.BarCode` contém a enumeração `BarCodeImageFormat` usada para salvar imagens.

## Etapa 2: Inicializar o gerador para um DataBar omnidirecional empilhado

O valor `EncodeTypes.DatabarStackedOmniDirectional` seleciona a simbologia DataBar empilhada. A string de dados deve seguir o formato GS1 Application Identifier (AI); aqui usamos um valor GTIN‑14 fictício.

```csharp
// Initialise a generator for a stacked omnidirectional DataBar barcode
var barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

> **Por que isso importa:** O tipo de codificação escolhido indica à biblioteca que deve renderizar um código de barras *empilhado*, o que é essencial para rótulos de alta densidade onde o espaço vertical é limitado.

## Etapa 3: Definir o tamanho do módulo (X‑dimension) em pixels

A X‑dimension controla a largura da barra mais fina (o “módulo”). Um valor de 2 pixels funciona bem para a maioria das saídas de resolução de tela.

```csharp
// Set the X‑dimension to 2 pixels (module width)
barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Por que isso importa:** Os scanners interpretam a largura do módulo como a unidade básica de medida. Um valor muito pequeno pode causar impressões borradas; um valor muito grande desperdiça espaço.

## Etapa 4: Salvar a primeira imagem com uma proporção de 15

A propriedade `AspectRatio` influencia a relação altura‑largura de cada segmento empilhado. Uma proporção de 15 é um padrão comum para aplicações de varejo.

```csharp
// Apply aspect ratio 15 and save the first PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **Por que isso importa:** Uma proporção menor produz um código de barras mais plano, que pode ser mais fácil de ler em certos materiais de etiqueta. O formato PNG preserva qualidade sem perdas para testes.

## Etapa 5: Alterar a proporção para 30 e salvar a segunda imagem

Aumentar a proporção torna cada segmento empilhado mais alto, o que pode melhorar a confiabilidade da leitura em fundos de baixo contraste.

```csharp
// Apply aspect ratio 30 and save the second PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

> **Por que isso importa:** Diferentes varejistas ou parceiros logísticos podem exigir dimensões específicas de código de barras. Fornecer ambas as versões permite comparar rapidamente o desempenho da leitura.

## Exemplo completo, executável

Abaixo está o programa completo que você pode copiar e colar em `Program.cs`. Ele compila e executa sem modificações após instalar o pacote NuGet Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace StackedDataBarDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for stacked omnidirectional DataBar
            var barcodeGen = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Define the module (X‑dimension) size in pixels
            barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Save first image with aspect ratio 15
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio15.png");

            // 4️⃣ Save second image with aspect ratio 30
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio30.png");
        }
    }
}
```

### Saída esperada

Executar o programa cria dois arquivos na pasta de execução:

| Nome do arquivo                | Proporção | Descrição visual                                   |
|--------------------------------|-----------|----------------------------------------------------|
| `DatabarAspectRatio15.png`    | 15        | Código de barras empilhado mais curto e plano      |
| `DatabarAspectRatio30.png`    | 30        | Código de barras empilhado mais alto e alongado    |

![Exemplo de código de barras stacked databars](placeholder-image.png){alt="Exemplo de código de barras stacked databars"}

## Perguntas comuns e casos de borda

| Pergunta                                            | Resposta |
|-----------------------------------------------------|----------|
| **Posso usar uma X‑dimension diferente?**          | Sim. Valores típicos variam de 1 a 4 pixels. Valores maiores aumentam o tamanho do código de barras, mas podem melhorar a legibilidade em impressoras de baixa resolução. |
| **E se eu precisar de uma simbologia diferente?**   | Substitua `EncodeTypes.DatabarStackedOmniDirectional` por outro valor `EncodeTypes`, como `DatabarStacked` (não omnidirecional) ou `DatabarLimited`. |
| **Como mudar o formato de saída?**                 | Use `BarCodeImageFormat.Jpeg`, `Gif` ou `Bmp` na chamada `Save`. |
| **O formato GTIN‑14 é obrigatório?**               | A simbologia DataBar espera uma string numérica prefixada com um AI apropriado (por exemplo, `(01)` para GTIN‑14). Ajuste os dados de acordo com seu caso de uso. |
| **E quanto às configurações de DPI?**              | O gerador respeita a propriedade `Resolution`. Para impressões de alta resolução, defina `barcodeGen.Parameters.ImageResolution.DpiX` e `DpiY` adequadamente. |

## Dicas profissionais

- **Geração em lote:** Envolva a lógica de salvamento em um loop e forneça uma lista de GTINs para gerar milhares de códigos de barras automaticamente.
- **Validação:** Use `barcodeGen.Validate()` antes de salvar para detectar dados malformados cedo.
- **Desempenho:** Reutilizar a mesma instância `BarcodeGenerator` (alterando apenas os parâmetros) é mais rápido do que criar um novo objeto para cada imagem.

## Próximos passos

Agora que você pode **criar código de barras stacked databars** com proporções personalizadas, considere explorar:

- Adicionar texto legível por humanos abaixo do código de barras (`barcodeGen.Parameters.Barcode.CodeText`).
- Exportar para **PDF** para folhas de etiquetas imprimíveis (`BarCodeImageFormat.Pdf`).
- Integrar o gerador em uma API web para servir códigos de barras sob demanda.
- Experimentar com outras **palavras‑chave secundárias** como *C# barcode generator* e *barcode aspect ratio* para ajustar sua implementação a hardware específico.

Boa codificação, e aproveite a flexibilidade que o Aspose.BarCode traz para seus projetos de código de barras em C#!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Criar código de barras databar empilhado em C# – guia passo a passo](/barcode/english/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/)
- [Código de barras databar empilhado omnidirecional em C# – Guia completo](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [Como criar imagens PNG de databar com C# e Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}