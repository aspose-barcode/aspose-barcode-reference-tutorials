---
category: general
date: 2026-10-02
description: Criar imagem de código de barras em C# usando um gerador de códigos de
  barras, controlar o tamanho dos pixels do código de barras e ajustar a altura do
  código de barras para dimensões personalizadas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- barcode pixel size
- adjust barcode height
- custom barcode dimensions
language: pt
lastmod: 2026-10-02
og_description: Crie imagem de código de barras em C# com um gerador de códigos de
  barras. Aprenda a definir o tamanho dos pixels do código de barras, ajustar a altura
  do código de barras e definir dimensões personalizadas do código de barras.
og_image_alt: Sample DataBar Omnidirectional barcode saved at 30 px height and 60 px
  height
og_title: Criar imagem de código de barras em C# – guia do gerador de código de barras
  e dimensões personalizadas
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode image in C# using a barcode generator, control barcode
    pixel size and adjust barcode height for custom barcode dimensions.
  headline: How to create barcode image in C# with a barcode generator
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: Como criar uma imagem de código de barras em C# com um gerador de códigos de
  barras
url: /pt/python-java/general/how-to-create-barcode-image-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar imagem de código de barras em C# com um gerador de códigos de barras

Se você precisa **criar arquivos de imagem de código de barras** programaticamente, este guia mostra uma solução completa, pronta‑para‑executar em C#. Ao usar um gerador de códigos de barras, você pode controlar o **tamanho do pixel do código de barras**, **ajustar a altura do código de barras** e definir **dimensões personalizadas do código de barras** sem sair do seu IDE.

Você aprenderá a gerar dois arquivos PNG — um com altura de barra de 30 px e outro com 60 px — mantendo a largura do módulo constante. As etapas funcionam com qualquer tipo de código de barras suportado pela biblioteca, de modo que você pode adaptá‑las para QR codes, Code 128 ou outras simbologias.

## O que você precisará

- .NET 6.0 ou posterior (o código também compila com .NET Framework 4.8)
- Uma referência à biblioteca de códigos de barras (por exemplo, Aspose.BarCode for .NET ou qualquer classe compatível `BarcodeGenerator`)
- Conhecimento básico de C#
- Permissão de gravação em uma pasta onde os arquivos PNG serão salvos

## Etapa 1: Inicializar o gerador de códigos de barras para **criar imagem de código de barras**

Primeiro, importe os namespaces necessários e instancie um `BarcodeGenerator`. O construtor recebe o tipo de código de barras (`EncodeTypes.DatabarOmniDirectional`) e a string de dados que você deseja codificar.

```csharp
using Aspose.BarCode.Generation;   // or the namespace of your barcode library
using Aspose.BarCode;               // for BarCodeImageFormat
using System.IO;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator to create barcode image
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Criar o gerador é a base para qualquer fluxo de trabalho **barcode generator c#**. Ele aloca a tela de desenho interna e prepara os dados para renderização.

## Etapa 2: Definir **tamanho do pixel do código de barras** e altura inicial da barra

A qualidade visual da imagem final depende de dois parâmetros:

| Parâmetro | Significado |
|-----------|-------------|
| `XDimension.Pixels` | Largura de um único módulo (o menor elemento preto/branco). |
| `BarHeight.Pixels` | Altura das barras para a imagem atual. |

```csharp
        // Step 2: Set common visual parameters – module size and initial bar height
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // barcode pixel size (module width)
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first image height in pixels
```

Manter o **tamanho do pixel do código de barras** constante enquanto altera a altura permite criar **dimensões personalizadas do código de barras** que atendam a diretrizes de marca ou requisitos de leitura.

## Etapa 3: Salvar o primeiro arquivo PNG (altura de 30 px)

Agora grave a imagem no disco. O método `Save` aceita o caminho do arquivo e o formato de imagem desejado.

```csharp
        // Step 3: Save the first barcode image (30 px height)
        string outputFolder = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputFolder); // ensure the folder exists

        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);
```

O arquivo resultante é uma **imagem de código de barras** com altura de barra de 30 px e largura de módulo de 2 px, ideal para rótulos compactos.

## Etapa 4: **Ajustar a altura do código de barras** para uma versão maior

Para gerar uma segunda imagem com tamanho visual diferente, basta alterar a propriedade `BarHeight.Pixels`. Isso demonstra como é fácil **ajustar a altura do código de barras** sem recriar o gerador.

```csharp
        // Step 4: Change the bar height to 60 px for a larger barcode
        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

Alterar a altura preservando o **tamanho do pixel do código de barras** garante que as barras permaneçam nítidas e que a proporção geral continue consistente.

## Etapa 5: Salvar o segundo arquivo PNG (altura de 60 px)

Por fim, persista a versão maior.

```csharp
        // Step 5: Save the second barcode image (60 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);
    }
}
```

Agora você tem duas **dimensões personalizadas do código de barras** salvas lado a lado:

- `DatabarBarHeight30Pixels.png` – altura de barra de 30 px
- `DatabarBarHeight60Pixels.png` – altura de barra de 60 px

Ambas as imagens compartilham o mesmo **tamanho do pixel do código de barras** de 2 px, garantindo consistência visual entre diferentes tamanhos.

## Por que essas configurações são importantes

- **Tamanho do pixel do código de barras** (`XDimension`) influencia a legibilidade pelo scanner. Uma largura de 2 px é um padrão comum que equilibra tamanho de arquivo e confiabilidade de leitura.
- **Altura da barra** determina o quão alta o código de barras aparece em um rótulo. Alguns scanners de varejo exigem uma altura mínima; outros permitem barras mais altas por razões estéticas.
- Manter a instância do gerador viva enquanto apenas ajusta `BarHeight` reduz alocações de memória e acelera o processamento em lote.

## Casos limites e dicas de boas práticas

| Situação | Abordagem recomendada |
|----------|-----------------------|
| **Formatos de imagem diferentes** (JPEG, BMP) | Altere `BarCodeImageFormat.Jpeg` ou `.Bmp` na chamada `Save`. JPEG é menor, mas pode introduzir artefatos de compressão. |
| **Saída de alta resolução** (ex.: 300 DPI) | Aumente `XDimension.Pixels` proporcionalmente (ex.: 4 px) e ajuste `BarHeight.Pixels` para manter o mesmo tamanho físico. |
| **Strings de dados dinâmicas** | Envolva a criação do gerador em um método que receba a string de dados como parâmetro, então reutilize a mesma instância `barcode` para várias gravações. |
| **Geração em lote thread‑safe** | Instancie um `BarcodeGenerator` separado por thread ou use um pool thread‑local para evitar condições de corrida. |
| **Erros de permissão no sistema de arquivos** | Verifique se `outputFolder` existe e se o processo tem acesso de gravação; trate `IOException` de forma graciosa. |

## Listagem completa do código fonte

Abaixo está o programa completo, autocontido, que você pode copiar, colar e executar.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.IO;

class Program
{
    static void Main()
    {
        // Create a barcode generator – this is the core of the create barcode image workflow
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // Define barcode pixel size (module width) and initial height
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // barcode pixel size
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first image height

        // Prepare output folder
        string outputFolder = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputFolder);

        // Save first image (30 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        // Adjust height for the second image
        barcode.Parameters.Barcode.BarHeight.Pixels = 60; // adjust barcode height

        // Save second image (60 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);
    }
}
```

### Saída esperada

Após executar o programa, a pasta `YOUR_DIRECTORY` conterá dois arquivos PNG:

- **DatabarBarHeight30Pixels.png** – um código de barras compacto, adequado para rótulos pequenos.
- **DatabarBarHeight60Pixels.png** – uma versão maior, ideal para aplicações de alta visibilidade.

Ambos os arquivos podem ser abertos em qualquer visualizador de imagens, impressos ou incorporados em PDFs.

## Conclusão

Agora você sabe como **criar arquivos de imagem de código de barras** em C# com um **barcode generator c#**, controlar o **tamanho do pixel do código de barras**, **ajustar a altura da barra** e produzir **dimensões personalizadas do código de barras** que atendam a requisitos específicos de leitura ou de marca. O exemplo demonstra um padrão limpo e repetível que escala para processamento em lote ou diferentes simbologias.

### O que explorar a seguir

- Troque `EncodeTypes.DatabarOmniDirectional` por outros tipos, como `EncodeTypes.Code128` ou `EncodeTypes.QR`.
- Aplique cores de primeiro plano/fundo via `barcode.Parameters.Barcode.ForeColor` e `BackColor`.
- Gere saídas SVG ou PDF para impressão vetorial.
- Combine múltiplos códigos de barras em uma única imagem usando `Graphics` para rótulos compostos.

Sinta‑se à vontade para experimentar os parâmetros e integrar esse padrão ao seu inventário, sistema de bilhetagem ou qualquer solução que precise de criação programática de códigos de barras. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que expandem as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to create barcode image in C# with adjustable height](/barcode/english/python-java/general/how-to-create-barcode-image-in-c-with-adjustable-height/)
- [How to generate barcode set custom size and save image in C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [Create barcode image C# with barcode generator example](/barcode/english/python-java/general/create-barcode-image-c-with-barcode-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}