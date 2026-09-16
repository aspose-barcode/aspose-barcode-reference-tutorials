---
category: general
date: 2026-07-27
description: Crie rapidamente uma imagem de código de barras planetário. Aprenda como
  gerar código de barras planetário com C# e personalize barras preenchidas ou vazias.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode image
- how to generate planet barcode
- planet barcode C#
- barcode X‑dimension
- filled vs empty bars
language: pt
lastmod: 2026-07-27
og_description: Crie imagem de código de barras planetário em segundos. Siga este
  guia para aprender como gerar código de barras planetário, ajustar a dimensão X
  e alternar entre barras preenchidas e vazias.
og_image_alt: Screenshot showing a create planet barcode image with filled bars
og_title: criar imagem de código de barras planetário – Tutorial completo de C#
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: create planet barcode image quickly. Learn how to generate planet barcode
    with C# and customize filled or empty bars.
  headline: create planet barcode image – Step‑by‑Step Guide
  type: TechArticle
- description: create planet barcode image quickly. Learn how to generate planet barcode
    with C# and customize filled or empty bars.
  name: create planet barcode image – Step‑by‑Step Guide
  steps:
  - name: Why the X‑dimension matters
    text: The X‑dimension controls how wide each tiny bar (or “module”) is. A value
      of **4 pixels** yields a barcode that’s clear on screen and prints nicely on
      standard label printers. If you need a denser image for a high‑resolution print,
      bump the value up to 6 or 8.
  - name: Expected output
    text: Open the resulting `PostalPlanetFilledBars.png` and you should see a classic
      Planet barcode—solid vertical bars with a quiet zone on each side. It looks
      just like the example you’d find on a postal envelope.
  - name: What “FilledBars = false” does
    text: Setting `FilledBars` to `false` tells the rendering engine to draw only
      the bar outlines. This is useful when you need a lighter‑weight image for on‑screen
      display or when a printing guideline explicitly requires the empty style.
  - name: Expected output
    text: The `PostalPlanetEmptyBars.png` file shows the same pattern as before, but
      each bar is a thin line instead of a solid block. It’s perfect for low‑contrast
      printing on colored paper.
  - name: When to use RM4SCC
    text: RM4SCC is the Dutch “Postcode” barcode. If you’re building a multi‑country
      logistics platform, having both Planet and RM4SCC generators at hand saves you
      a lot of boilerplate code.
  - name: What if I need a different image format?
    text: Just swap `BarCodeImageFormat.Png` for `Jpeg`, `Bmp`, or `Gif`. The library
      handles the conversion automatically.
  - name: How do I change the barcode height?
    text: Use `planetFilled.Parameters.Barcode.BarHeight = 50; // height in points`
      (or pixels, depending on the library version). Higher values give you a taller
      barcode, which can improve scan reliability on low‑resolution scanners.
  - name: Can I embed the barcode directly into a PDF?
    text: Absolutely. The `Save` method returns a `byte[]` if you call the overload
      that writes to a stream. Feed that stream into a PDF generation library (e.g.,
      iTextSharp) and you’ve got a fully‑automated mailing label.
  - name: What if the data string contains non‑numeric characters?
    text: 'Planet and RM4SCC expect **numeric only** payloads. Passing letters will
      throw an `ArgumentException`. Validate your input first:'
  - name: Does the X‑dimension affect scanning speed?
    text: A larger X‑dimension creates a more robust barcode, which generally improves
      scanning speed, especially on low‑quality scanners. However, it also increases
      the physical size of the label, so balance readability with space constraints.
  type: HowTo
tags:
- barcode
- C#
- imaging
title: criar imagem de código de barras planetário – Guia passo a passo
url: /pt/python-java/general/create-planet-barcode-image-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# create planet barcode image – Complete C# Tutorial

Já se perguntou **como gerar planet barcode** para um sistema de correspondência ou um aplicativo de logística? Você não é o primeiro a ficar coçando a cabeça com isso. Neste tutorial, vamos percorrer tudo o que você precisa para **criar planet barcode image** arquivos, desde o básico da classe `BarcodeGenerator` até ajustar a X‑dimension e trocar barras preenchidas por vazias.

Também daremos uma olhada em uma simbologia relacionada—RM4SCC—para que você veja como o mesmo padrão funciona para outros códigos de barras postais. Ao final, você terá três trechos prontos‑para‑executar que geram arquivos PNG que podem ser inseridos diretamente no seu projeto.

## O que você vai precisar

- .NET 6.0 ou superior (o código também funciona no .NET Framework 4.7+)  
- Uma referência ao **Aspose.BarCode** (ou qualquer biblioteca que exponha `BarcodeGenerator`, `EncodeTypes`, `BarCodeImageFormat`)  
- Uma IDE com a qual você se sinta confortável—Visual Studio, Rider ou VS Code servem  
- Uma pasta onde você possa gravar imagens (substitua `YOUR_DIRECTORY` nos exemplos)

É só isso. Nenhum pacote NuGet extra além da própria biblioteca de códigos de barras.

---

## Etapa 1: Configurar o projeto e os imports

Primeiro de tudo, vamos criar um pequeno aplicativo console para que possamos executar o código imediatamente.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll call helper methods here (see later)
            GeneratePlanetFilledBars();
            GeneratePlanetEmptyBars();
            GenerateRM4SCCFilledBars();
        }
```

> **Dica:** Mantenha seu método `Main` organizado; delegue cada cenário para seu próprio método. Isso deixa o código mais fácil de ler e espelha os três exemplos no trecho original.

---

## Etapa 2: **create planet barcode image** com barras preenchidas padrão

A simbologia Planet é usada por muitos serviços postais para números de rastreamento. Para **create planet barcode image** com as barras sólidas habituais, siga estas três linhas:

```csharp
        static void GeneratePlanetFilledBars()
        {
            // 1️⃣ Create a generator for the Planet symbology with data "123456"
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Set the X‑dimension (module width) to 4 pixels for better visibility
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the barcode as a PNG image
            planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
        }
```

### Por que a X‑dimension importa
A X‑dimension controla quão larga cada barra minúscula (ou “módulo”) é. Um valor de **4 pixels** produz um código de barras que fica nítido na tela e imprime bem em impressoras de etiquetas padrão. Se precisar de uma imagem mais densa para impressão de alta resolução, aumente o valor para 6 ou 8.

### Saída esperada
Abra o `PostalPlanetFilledBars.png` gerado e você verá um clássico código de barras Planet—barras verticais sólidas com uma zona silenciosa em cada lado. Ele se parece exatamente com o exemplo que você encontraria em um envelope postal.

---

## Etapa 3: **create planet barcode image** com barras vazias

Às vezes a especificação postal exige um estilo de *barra vazia*, onde as barras são contornos ao invés de preenchimentos sólidos. Trocar para esse modo é uma única alteração de propriedade.

```csharp
        static void GeneratePlanetEmptyBars()
        {
            // 1️⃣ Create the generator (same data as before)
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Keep the X‑dimension consistent
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Disable filled bars → we get an empty‑bar representation
            planetEmpty.Parameters.Barcode.FilledBars = false;

            // 4️⃣ Save the PNG
            planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
        }
```

### O que “FilledBars = false” faz
Definir `FilledBars` como `false` indica ao motor de renderização que desenhe apenas os contornos das barras. Isso é útil quando você precisa de uma imagem mais leve para exibição em tela ou quando uma diretriz de impressão requer explicitamente o estilo vazio.

### Saída esperada
O arquivo `PostalPlanetEmptyBars.png` mostra o mesmo padrão de antes, mas cada barra é uma linha fina ao invés de um bloco sólido. É perfeito para impressão de baixo contraste em papel colorido.

---

## Etapa 4: Gerar um código de barras RM4SCC (Bônus)

Embora nosso foco principal seja a simbologia Planet, a mesma API permite que você **create planet barcode image**‑like resultados para outros códigos postais. Veja como **how to generate planet barcode**‑style saída para RM4SCC:

```csharp
        static void GenerateRM4SCCFilledBars()
        {
            // 1️⃣ Create a generator for the RM4SCC symbology
            BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

            // 2️⃣ Align X‑dimension with the other examples
            rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the image
            rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
        }
    }
}
```

### Quando usar RM4SCC
RM4SCC é o código de barras “Postcode” holandês. Se você está construindo uma plataforma logística multi‑país, ter geradores tanto para Planet quanto para RM4SCC à mão economiza muito código boilerplate.

---

## Perguntas comuns & casos de borda

### E se eu precisar de um formato de imagem diferente?
Basta trocar `BarCodeImageFormat.Png` por `Jpeg`, `Bmp` ou `Gif`. A biblioteca cuida da conversão automaticamente.

### Como altero a altura do código de barras?
Use `planetFilled.Parameters.Barcode.BarHeight = 50; // height in points` (ou pixels, dependendo da versão da biblioteca). Valores maiores dão um código de barras mais alto, o que pode melhorar a confiabilidade da leitura em scanners de baixa resolução.

### Posso incorporar o código de barras diretamente em um PDF?
Com certeza. O método `Save` retorna um `byte[]` se você chamar a sobrecarga que grava em um stream. Alimente esse stream em uma biblioteca de geração de PDF (por exemplo, iTextSharp) e você terá um rótulo de correspondência totalmente automatizado.

### E se a string de dados contiver caracteres não numéricos?
Planet e RM4SCC esperam **apenas payload numérico**. Passar letras lançará uma `ArgumentException`. Valide sua entrada primeiro:

```csharp
if (!Regex.IsMatch(data, @"^\d+$"))
    throw new ArgumentException("Planet barcode data must be numeric.");
```

### A X‑dimension afeta a velocidade de leitura?
Uma X‑dimension maior cria um código de barras mais robusto, o que geralmente melhora a velocidade de leitura, especialmente em scanners de baixa qualidade. Contudo, isso também aumenta o tamanho físico da etiqueta, então equilibre legibilidade com restrições de espaço.

---

## Exemplo completo (os três métodos)

Abaixo está o programa completo que você pode copiar‑colar em um novo projeto console. Substitua `YOUR_DIRECTORY` por um caminho absoluto ou relativo que seu aplicativo possa gravar.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            GeneratePlanetFilledBars();
            GeneratePlanetEmptyBars();
            GenerateRM4SCCFilledBars();

            Console.WriteLine("All barcode images have been saved.");
        }

        static void GeneratePlanetFilledBars()
        {
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
        }

        static void GeneratePlanetEmptyBars()
        {
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
        }

        static void GenerateRM4SCCFilledBars()
        {
            BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
        }
    }
}
```

Execute o programa, abra os três arquivos PNG e você verá exatamente as imagens descritas anteriormente. Nenhuma configuração adicional é necessária.

---

## Recapitulando & próximos passos

Cobrimos **how to generate planet barcode** imagens do zero, alternando entre estilos sólido e contorno, e estendendo a mesma abordagem para RM4SCC. Os principais aprendizados:

1. Instancie `BarcodeGenerator` com o `EncodeTypes` correto e os dados.  
2. Ajuste `XDimension.Pixels` para controlar a largura das barras.  
3. Use `FilledBars = false` para a variante de barra vazia.  
4. Salve o resultado no formato de imagem que preferir.

Agora que você pode **create planet barcode image** arquivos, considere estas ideias de continuação:

- **Geração em lote**: Percorra um CSV de números de rastreamento e gere um PNG para cada um.  
- **Dimensionamento dinâmico**: Exponha X‑dimension e altura da barra como parâmetros de configuração em uma API web.  
- **Integração com impressoras de etiquetas**: Envie os bytes PNG diretamente para uma impressora compatível com ZPL para criação de etiquetas em tempo real.

Sinta-se à vontade para experimentar—troque a string de dados, teste dimensões diferentes ou combine o código de barras com um QR code na mesma etiqueta. A biblioteca de códigos de barras é flexível o suficiente para lidar com tudo isso.

Tem um cenário complicado que você não tem certeza de como resolver? Deixe um comentário abaixo e vamos solucionar juntos. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}