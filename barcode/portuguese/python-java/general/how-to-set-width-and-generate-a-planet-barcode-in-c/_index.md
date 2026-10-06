---
category: general
date: 2026-09-16
description: Aprenda como definir a largura, como criar barras vazias e como preencher
  as barras ao gerar o código de barras Planet usando o Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to make empty
- how to fill bars
- generate planet barcode
language: pt
lastmod: 2026-09-16
og_description: Como definir a largura, criar barras vazias e preencher barras ao
  gerar o código de barras Planet com Aspose.BarCode – guia completo passo a passo.
og_image_alt: Screenshot showing how to set width for a Planet barcode in C#
og_title: Como definir a largura e gerar um código de barras Planet em C#
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set width, how to make empty bars, and how to fill bars
    when you generate Planet barcode using Aspose.BarCode.
  headline: How to set width and generate a Planet barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Como definir a largura e gerar um código de barras Planet em C#
url: /pt/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como definir a largura e gerar um código de barras Planet em C#

Se você precisa **definir a largura** para um código de barras Planet, este guia mostra o processo completo. Você também verá **como deixar as barras vazias**, **como preencher as barras**, e os passos exatos para **gerar um código de barras Planet** com Aspose.BarCode para .NET.

Gerar um código de barras Planet no estilo postal é comum ao desenvolver aplicações de etiquetas de correio ou integrações com serviços postais. Ao final deste tutorial você terá um programa de console pronto‑para‑executar que cria tanto uma imagem com barras preenchidas quanto uma imagem com barras vazias, ambas usando a mesma string de dados.

## Pré‑requisitos

- SDK .NET 6.0 ou posterior (o código também funciona com .NET Framework 4.7+)
- Visual Studio 2022 ou qualquer IDE compatível com C#
- Pacote NuGet Aspose.BarCode para .NET (`Aspose.BarCode`)  
  Instale com:

```bash
dotnet add package Aspose.BarCode
```

Nenhuma configuração adicional é necessária; a biblioteca lida com a codificação da imagem internamente.

## Etapa 1: Criar um projeto de console e adicionar a biblioteca

Abra um terminal e execute:

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
dotnet add package Aspose.BarCode
```

Isso cria um arquivo `Program.cs` onde escreveremos a lógica do código de barras.

## Etapa 2: Escrever o código – como definir a largura e gerar o código de barras Planet

Abra `Program.cs` e substitua seu conteúdo pelo exemplo completo a seguir:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Data to encode – the same value is used for both images
        const string data = "123456";

        // -----------------------------------------------------------------
        // Part A: Filled‑bars version (default style)
        // -----------------------------------------------------------------
        // Step 2.1: Create a Planet barcode generator
        var filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, data);

        // Step 2.2: How to set width – define the width of a single bar in pixels
        // The XDimension controls bar width; 4 pixels yields a clear, printable image
        filledGenerator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 2.3: Save the filled‑bars image (default is FilledBars = true)
        string filledPath = "PostalPlanetFilledBars.png";
        filledGenerator.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to {filledPath}");

        // -----------------------------------------------------------------
        // Part B: Empty‑bars version (unfilled style)
        // -----------------------------------------------------------------
        // Step 3.1: Re‑instantiate the generator for the same data
        var emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, data);

        // Step 3.2: How to set width again – required after re‑instantiation
        emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 3.3: How to make empty – disable the filled‑bars flag
        emptyGenerator.Parameters.Barcode.FilledBars = false;

        // Step 3.4: Save the empty‑bars image
        string emptyPath = "PostalPlanetEmptyBars.png";
        emptyGenerator.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to {emptyPath}");

        // -----------------------------------------------------------------
        // Verification output
        // -----------------------------------------------------------------
        Console.WriteLine("Both barcodes generated successfully.");
    }
}
```

### Por que cada passo importa

- **Como definir a largura**: A propriedade `XDimension.Pixels` influencia diretamente o tamanho físico de cada barra. Escolher um valor entre 2 e 6 pixels equilibra a legibilidade na tela e a qualidade de impressão.
- **Como deixar vazias**: Definir `FilledBars = false` indica ao gerador que desenhe apenas os contornos das barras. Esse estilo é útil para impressão “claro‑sobre‑escuro” ou quando se deseja que a textura do papel subjacente apareça.
- **Como preencher as barras**: O padrão `FilledBars = true` cria barras pretas sólidas, que é o padrão para a maioria dos scanners postais.
- **Gerar código de barras Planet**: Usar `EncodeTypes.Planet` seleciona a codificação específica exigida pelo United States Postal Service (USPS) para códigos de barras Planet.

## Etapa 3: Compilar e executar o programa

No diretório do projeto, execute:

```bash
dotnet run
```

Você deverá ver uma saída no console semelhante a:

```
Filled‑bars barcode saved to PostalPlanetFilledBars.png
Empty‑bars barcode saved to PostalPlanetEmptyBars.png
Both barcodes generated successfully.
```

Dois arquivos PNG aparecem no diretório do projeto:

- `PostalPlanetFilledBars.png` – barras pretas sólidas (estilo padrão)
- `PostalPlanetEmptyBars.png` – contorno de barras (estilo vazio)

Abra-os em qualquer visualizador de imagens para verificar se a largura das barras corresponde à configuração de 4 pixels e se a versão vazia mostra barras não preenchidas.

## Perguntas comuns e casos extremos

| Pergunta | Resposta |
|----------|----------|
| *Posso usar um formato de imagem diferente?* | Sim. Substitua `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` ou `Gif` conforme necessário. |
| *E se o código de barras ficar muito largo para a minha etiqueta?* | Reduza `XDimension.Pixels` (ex.: para `2`) ou aumente a largura do módulo da impressora de etiquetas. |
| *Preciso definir `Height` manualmente?* | A biblioteca calcula automaticamente a altura com base na codificação. Você pode sobrescrever com `Parameters.Barcode.BarHeight`. |
| *O estilo de barras vazias é suportado em todas as impressoras?* | A maioria das impressoras térmicas modernas lida com ambos os estilos, preenchido e vazio, mas verifique com uma impressão de teste se você usa um dispositivo antigo. |
| *Como adicionar uma legenda legível por humanos abaixo do código de barras?* | Use `Parameters.Caption` para habilitar e estilizar uma legenda; defina `CaptionAbove` como `false` para posicioná‑la abaixo. |

## Dicas profissionais

- **Reutilize o mesmo gerador** apenas quando mantiver todos os parâmetros idênticos. Alterar `FilledBars` após salvar não afeta a imagem já salva, portanto reinstanciar (conforme mostrado) garante um início limpo.
- **Geração em lote**: Envolva o código em um loop e altere `data` a cada iteração para criar uma série de códigos de barras Planet para envio em massa.
- **Desempenho**: Para milhares de códigos de barras, crie uma única instância de `BarcodeGenerator`, ajuste `XDimension` e `FilledBars` conforme necessário e reutilize o objeto para reduzir alocações de memória.

## Conclusão

Agora você sabe **como definir a largura**, **como deixar vazias**, **como preencher as barras**, e os passos exatos para **gerar um código de barras Planet** com Aspose.BarCode em C#. O exemplo completo e executável produz arquivos PNG com barras preenchidas e vazias, prontos para integração em qualquer fluxo de trabalho de etiquetas de correio.

Em seguida, explore tópicos relacionados, como **como adicionar códigos QR à mesma etiqueta**, **personalizar cores de códigos de barras**, ou **incorporar o código de barras em um documento PDF**. Cada um desses se baseia nos mesmos fundamentos abordados aqui. Feliz codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens de implementação alternativas em seus próprios projetos.

- [Criar imagem de código de barras Planet em C# – Como gerar código de barras postal](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Como criar código de barras Code128 com barras vazias em Java](/barcode/english/java/image-manipulation/generating-barcode-empty-bars/)
- [Como gerar imagem de código de barras em Java com Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}