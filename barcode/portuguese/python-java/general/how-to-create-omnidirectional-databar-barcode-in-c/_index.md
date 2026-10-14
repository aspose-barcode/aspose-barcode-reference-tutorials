---
category: general
date: 2026-09-29
description: Aprenda a criar códigos de barras Databar omnidirecionais em C# com Aspose.BarCode.
  Ajuste a dimensão X, defina a proporção e salve imagens PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional databar barcode
- DataBar stacked omnidirectional barcode
- set barcode aspect ratio
- Aspose.BarCode C#
- generate barcode image
language: pt
lastmod: 2026-09-29
og_description: Crie código de barras Databar omnidirecional em C# usando Aspose.BarCode.
  Aprenda a definir a dimensão X, ajustar a proporção e exportar arquivos PNG.
og_image_alt: Screenshot showing two PNG files of an omnidirectional Databar barcode
  with different aspect ratios
og_title: Crie código de barras Databar omnidirecional em C# – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  headline: How to create omnidirectional Databar barcode in C#
  type: TechArticle
- description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  name: How to create omnidirectional Databar barcode in C#
  steps:
  - name: What if I need a different X‑dimension?
    text: You can assign any integer value to `XDimension.Pixels`. Values below `1`
      are ignored, and values above `10` may produce oversized modules that exceed
      printer margins. Test the visual output after each change.
  - name: How do I encode other AI‑generated data (e.g., UPC, EAN)?
    text: Replace the data string in the `BarcodeGenerator` constructor with the appropriate
      Application Identifier (AI). For a UPC‑A code, use `"012345678905"` without
      an AI prefix.
  - name: Can I export to formats other than PNG?
    text: Yes. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`,
      `BarCodeImageFormat.Tiff`, and `BarCodeImageFormat.Bmp`. Choose the format that
      matches your downstream workflow.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Como criar um código de barras Databar omnidirecional em C#
url: /pt/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar código de barras Databar omnidirecional em C#

Se você precisa **criar código de barras Databar omnidirecional** em uma aplicação .NET, este guia mostra os passos exatos. Você verá como inicializar um código de barras DataBar stacked omnidirecional, configurar sua dimensão X, alterar a proporção e gerar imagens PNG com Aspose.BarCode.

Gerar um **código de barras DataBar stacked omnidirecional** é comum quando você deve codificar identificadores de produto para scanners de varejo. Neste tutorial você aprenderá a **definir a proporção do código de barras**, controlar o tamanho do módulo e exportar o resultado sem sair do IDE.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

- .NET 6.0 ou superior instalado
- Visual Studio 2022 (ou qualquer IDE compatível com C#)
- O pacote **Aspose.BarCode for .NET** do NuGet (versão 23.12 ou mais recente)

Você pode adicionar o pacote via NuGet Package Manager:

```bash
dotnet add package Aspose.BarCode
```

## Etapa 1: Inicializar o código de barras Databar omnidirecional

O primeiro passo é criar uma instância de `BarcodeGenerator` que tem como alvo a simbologia **DataBar stacked omnidirecional**. O construtor recebe o tipo de codificação e a string de dados.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialise a DataBar stacked omnidirectional barcode with GTIN data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Por que isso importa:** O valor `EncodeTypes.DatabarStackedOmniDirectional` indica ao Aspose.BarCode para renderizar o formato omnidirecional Databar específico, que é necessário para a leitura em ambas as direções.

## Etapa 2: Definir a dimensão X (tamanho do módulo)

A dimensão X controla a largura de um único módulo do código de barras em pixels. Um valor de `2` pixels funciona bem para renderização na tela e na maioria das impressoras.

```csharp
        // Set the basic size of the barcode modules (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Por que isso importa:** Uma dimensão X consistente garante que o código de barras atenda às especificações mínimas de tamanho para scanners de varejo, ao mesmo tempo que mantém o tamanho do arquivo de imagem gerenciável.

## Etapa 3: Definir a primeira proporção e salvar a imagem

A **proporção** determina a relação altura‑largura do DataBar. Uma proporção de `15` produz um código de barras compacto e alto, ideal para espaços estreitos de rótulo.

```csharp
        // Apply aspect ratio 15 and save the first PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Por que isso importa:** Ajustar a proporção permite encaixar o código de barras em diferentes layouts de rótulo sem sacrificar a legibilidade. O PNG salvo pode ser visualizado em qualquer visualizador de imagens.

## Etapa 4: Alterar a proporção e gerar uma segunda imagem

Às vezes, um código de barras mais largo é necessário — por exemplo, quando o rótulo tem mais espaço horizontal. Alterar a proporção para `30` cria uma aparência mais plana.

```csharp
        // Change aspect ratio to 30 and save a second PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Por que isso importa:** Ao expor a propriedade **set barcode aspect ratio**, você pode produzir múltiplas variações do código de barras a partir de um único código‑fonte, simplificando pipelines automatizados de geração de rótulos.

## Saída esperada

Executar o programa produz dois arquivos PNG na pasta de saída da aplicação:

| Nome do arquivo                | Proporção | Descrição visual |
|--------------------------------|-----------|-------------------|
| `DatabarAspectRatio15.png`     | 15        | Código de barras alto e estreito, adequado para rótulos estreitos |
| `DatabarAspectRatio30.png`     | 30        | Código de barras mais largo que preenche mais espaço horizontal |

Você pode incorporar essas imagens em relatórios, imprimi‑las em embalagens de produtos ou enviá‑las a um serviço web para processamento adicional.

![Criar exemplo de código de barras Databar omnidirecional](databar-example.png "Criar exemplo de código de barras Databar omnidirecional")

*A captura de tela mostra os dois arquivos PNG gerados lado a lado.*

## Perguntas comuns e casos de borda

### E se eu precisar de uma dimensão X diferente?

Você pode atribuir qualquer valor inteiro a `XDimension.Pixels`. Valores abaixo de `1` são ignorados, e valores acima de `10` podem gerar módulos superdimensionados que excedem as margens da impressora. Teste a saída visual após cada alteração.

### Como codifico outros dados gerados por AI (por exemplo, UPC, EAN)?

Substitua a string de dados no construtor `BarcodeGenerator` pelo Identificador de Aplicação (AI) apropriado. Para um código UPC‑A, use `"012345678905"` sem prefixo AI.

### Posso exportar para formatos diferentes de PNG?

Sim. O método `Save` aceita `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`, `BarCodeImageFormat.Tiff` e `BarCodeImageFormat.Bmp`. Escolha o formato que corresponde ao seu fluxo de trabalho posterior.

## Dica profissional: reutilizar o gerador para processamento em lote

Se precisar gerar dezenas de códigos de barras com diferentes proporções, mantenha a instância `BarcodeGenerator` viva e modifique apenas `DataBar.AspectRatio` antes de cada `Save`. Isso evita a sobrecarga de reinstanciar o gerador para cada imagem.

```csharp
var ratios = new[] { 10, 15, 20, 30 };
foreach (var ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    generator.Save($"DatabarAspectRatio{ratio}.png", BarCodeImageFormat.Png);
}
```

## Conclusão

Agora você sabe como **criar código de barras Databar omnidirecional** em C# usando Aspose.BarCode. Ao inicializar um `BarcodeGenerator`, definir a dimensão X, ajustar a **set barcode aspect ratio** e salvar arquivos PNG, você pode produzir imagens de códigos de barras que atendem a diversos requisitos de rótulo.  

Em seguida, explore tópicos relacionados como **gerar imagem de código de barras** para QR codes, validação de **DataBar stacked omnidirectional barcode**, ou a integração dos PNGs gerados em faturas PDF com Aspose.PDF. Experimente diferentes proporções e tamanhos de módulo para encontrar a configuração ideal para o seu hardware de impressão específico.

---


## O que você deve aprender a seguir?


Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como usar um gerador de código de barras C# para criar códigos de barras DataBar omnidirecional](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [Databar stacked omnidirectional barcode em C# – Guia completo](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [Como gerar código de barras em C# – criar imagem de código de barras c# com DataBar Expanded](/barcode/english/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}