---
category: general
date: 2026-09-19
description: O guia do gerador de código de barras C# mostra como gerar um código
  de barras Planet e exportar a imagem do código de barras como PNG em apenas algumas
  linhas.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- how to generate barcode
- create planet barcode
- export barcode image
language: pt
lastmod: 2026-09-19
og_description: O gerador de código de barras C# permite criar rapidamente um código
  de barras Planet e exportar a imagem como PNG para qualquer aplicativo .NET.
og_image_alt: Screenshot of a Planet barcode generated with barcode generator C# showing
  empty bars
og_title: gerador de código de barras C# – criar código de barras Planet e exportar
  imagem
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator C# guide shows how to generate a Planet barcode and
    export barcode image as PNG in just a few lines.
  headline: How to use barcode generator C# for Planet barcode
  type: TechArticle
tags:
- barcode
- C#
- image export
title: Como usar o gerador de código de barras C# para código de barras Planet
url: /pt/python-java/general/how-to-use-barcode-generator-c-for-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como usar o gerador de código de barras C# para o código Planet

Se você precisa de um **gerador de código de barras C#** que possa produzir um código Planet, este guia oferece uma solução completa. Você aprenderá **como gerar dados de código de barras**, personalizar a aparência e **exportar a imagem do código de barras** como um arquivo PNG com apenas algumas linhas de código.

Criar códigos de barras é uma necessidade comum para sistemas de inventário, plataformas de bilhetagem e dispositivos IoT. Ao final deste tutorial você terá um aplicativo console autônomo que gera um código Planet limpo, desabilita o preenchimento das barras e salva o resultado no disco. Nenhuma ferramenta externa é necessária além da biblioteca de códigos de barras.

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

* .NET 6.0 SDK ou posterior instalado  
* Uma biblioteca de códigos de barras compatível com C# (o exemplo usa **Aspose.BarCode for .NET**, que suporta a simbologia Planet)  
* Uma IDE ou editor como Visual Studio 2022, VS Code ou Rider  

A biblioteca pode ser adicionada via NuGet:

```bash
dotnet add package Aspose.BarCode
```

> **Dica:** Use a versão estável mais recente do pacote para se beneficiar de correções de bugs e melhorias de desempenho.

## Usando o gerador de código de barras C# para criar um código Planet

O primeiro passo é instanciar o gerador com a simbologia Planet e os dados que você deseja codificar.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for the Planet symbology with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

`BarcodeGenerator` é o ponto de entrada para todas as operações de código de barras. O construtor recebe a simbologia (`EncodeTypes.Planet`) e os dados brutos (`"123456"`). Este código **cria um código Planet** que pode ser renderizado posteriormente como imagem.

## Ajustando parâmetros do código de barras

Para controlar a qualidade visual você pode modificar a dimensão X (largura do módulo) e decidir se as barras serão preenchidas.

```csharp
        // Step 2: Adjust the X-dimension (module width) to 4 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 3: Disable filling of the bars so that only the outlines are drawn
        generator.Parameters.Barcode.FilledBars = false;
```

* Definir `XDimension.Pixels` como **4** gera um código de barras de resolução mais alta sem aumentar o tamanho do arquivo de forma drástica.  
* `FilledBars = false` produz um estilo apenas de contorno, útil quando você deseja que o código de barras se misture ao fundo ou ao imprimir em dispositivos de baixa tinta.

## Exportar imagem do código de barras

Depois de configurar o gerador, salve o resultado em um arquivo PNG. O método `Save` aceita um caminho completo e o formato de imagem desejado.

```csharp
        // Step 4: Save the generated barcode image as a PNG file
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "PlanetEmptyBars.png");

        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

O código grava **export barcode image** `PlanetEmptyBars.png` na Área de Trabalho do usuário. PNG é um formato sem perdas que preserva as bordas nítidas do código de barras, tornando‑o ideal tanto para exibição em tela quanto para impressão em alta resolução.

> **Caso especial:** Se precisar de um formato diferente (JPEG, BMP, GIF), substitua `BarCodeImageFormat.Png` pelo valor de enum correspondente. JPEG introduz artefatos de compressão que podem afetar a legibilidade pelo scanner, portanto use‑o apenas quando o tamanho do arquivo for crítico.

## Exemplo completo e executável

Abaixo está o programa completo que você pode copiar, colar e executar imediatamente.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Create a barcode generator for the Planet symbology with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Adjust the X-dimension (module width) to 4 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 4;

        // Disable filling of the bars so that only the outlines are drawn
        generator.Parameters.Barcode.FilledBars = false;

        // Define the output file path (Desktop folder is used for convenience)
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "PlanetEmptyBars.png");

        // Export the barcode image as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

Ao executar o programa, você deverá ver uma mensagem semelhante a:

```
Barcode saved to: C:\Users\YourName\Desktop\PlanetEmptyBars.png
```

Abrir o arquivo PNG exibe um código Planet limpo com barras vazias, exatamente como configurado.

![exemplo de gerador de código de barras C#](/images/barcode-generator-csharp.png){alt="exemplo de gerador de código de barras C#"}

## Perguntas frequentes e solução de problemas

| Pergunta | Resposta |
|----------|----------|
| **Posso gerar outras simbologias com o mesmo código?** | Sim. Substitua `EncodeTypes.Planet` por qualquer tipo suportado, como `EncodeTypes.Code128` ou `EncodeTypes.QR`. |
| **E se o código de barras não for lido?** | Verifique se o comprimento dos dados está de acordo com a especificação Planet (exatamente 6 caracteres numéricos). Também assegure contraste suficiente entre o código de barras e o fundo. |
| **Como altero o tamanho da imagem?** | Ajuste `generator.Parameters.ImageWidth` e `generator.Parameters.ImageHeight` ou modifique `XDimension` para escalar o código de barras proporcionalmente. |
| **É possível adicionar uma legenda abaixo do código de barras?** | Use `generator.Parameters.Barcode.CodeTextVisible = true;` e personalize `CodeTextParameters` para fonte, alinhamento e margem. |

## Próximos passos

Agora que você dominou **como gerar imagens de código de barras** com um **gerador de código de barras C#**, pode explorar:

* Gerar arquivos de código de barras em lote usando uma lista CSV de valores.  
* Incorporar o PNG em faturas PDF com Aspose.PDF.  
* Trocar para formatos de **export barcode image** como SVG para gráficos web escaláveis.  

Essas extensões aprofundam seu entendimento sobre automação de códigos de barras em .NET e preparam você para cenários reais de integração.

---

**Resumo:** Este tutorial demonstrou um fluxo completo de **gerador de código de barras C#** — criação de um código Planet, personalização da aparência e **exportação da imagem do código de barras** como PNG. Você pode adaptar o mesmo padrão para outras simbologias, formatos de imagem e destinos de saída. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Barcode generator C# – generate barcode image](/barcode/english/python-java/general/barcode-generator-c-generate-barcode-image/)
- [Create Planet Barcode Image in C# – How to Generate Postal Barcode](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}