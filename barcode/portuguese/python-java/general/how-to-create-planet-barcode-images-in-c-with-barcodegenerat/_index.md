---
category: general
date: 2026-09-26
description: Aprenda a criar códigos de barras Planet em C# rapidamente. Este guia
  aborda códigos de barras Planet preenchidos e vazios, configurações da dimensão
  X e exportação de imagem.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode C#
- filled planet barcode
- empty planet barcode
- barcode generator parameters
language: pt
lastmod: 2026-09-26
og_description: Crie código de barras Planet em C# com um exemplo completo de código.
  Gere códigos de barras Planet preenchidos e vazios, defina a largura da barra e
  salve como PNG.
og_image_alt: Screenshot showing generated filled and empty planet barcode PNG files
og_title: Crie imagens de código de barras planetário em C# – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create planet barcode in C# quickly. This guide covers
    filled and empty Planet barcodes, X‑dimension settings, and image export.
  headline: How to create planet barcode images in C# with BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Como criar imagens de código de barras planetário em C# com BarcodeGenerator
url: /pt/python-java/general/how-to-create-planet-barcode-images-in-c-with-barcodegenerat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar imagens de código de barras planetário em C# com BarcodeGenerator

Se você precisar **criar código de barras planetário** imagens em uma aplicação .NET, este tutorial mostra os passos exatos. Você aprenderá como gerar tanto um código de barras Planet preenchido quanto um vazio, ajustar a largura das barras e exportar os resultados como arquivos PNG — tudo com a biblioteca Aspose.BarCode for .NET.

Gerar uma solução **Planet barcode C#** é simples assim que você entender os principais **barcode generator parameters**. Nas seções a seguir, percorreremos o código completo e executável, explicaremos por que cada configuração importa e apontaremos armadilhas comuns para que você possa evitá‑las na primeira tentativa.

## Pré-requisitos

* .NET 6.0 SDK ou posterior instalado.
* Visual Studio 2022 (ou qualquer IDE C# que prefira).
* O pacote NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`) adicionado ao seu projeto.

Você pode adicionar o pacote via o Console do Gerenciador de Pacotes NuGet:

```bash
dotnet add package Aspose.BarCode
```

## Etapa 1: Configurar o BarcodeGenerator

A classe `BarcodeGenerator` é o ponto de entrada para todas as tarefas de criação de códigos de barras. Ela requer dois argumentos: o tipo de código de barras (`EncodeTypes.Planet`) e os dados a serem codificados.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PlanetBarcodeDemo
{
    static void Main()
    {
        // Create a generator for a filled Planet barcode
        BarcodeGenerator filledPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*Por que isso importa:* Instanciar o gerador com `EncodeTypes.Planet` indica à biblioteca que deve usar a simbologia **Planet barcode**, que é comumente usada para serviços postais em alguns países. A string `"123456"` é a carga útil que aparecerá no código de barras.

## Etapa 2: Configurar a X‑dimension (largura da barra)

A X‑dimension controla a largura física de cada barra. Um valor típico para renderização em tela é 4 pixels, mas você pode ajustá‑lo para atender aos requisitos de impressão.

```csharp
        // Define the bar width (X dimension) in pixels
        filledPlanet.Parameters.Barcode.XDimension.Pixels = 4;
```

*Por que isso importa:* Definir `XDimension.Pixels` garante que o código de barras gerado não seja nem muito fino (causando falhas de leitura) nem muito grosso (desperdiçando espaço). A mesma configuração será reutilizada para o código de barras vazio.

## Etapa 3: Salvar o código de barras Planet preenchido

Exporte o código de barras para um arquivo PNG usando o método `Save`. O enum `BarCodeImageFormat.Png` indica à biblioteca que deve produzir uma imagem sem perdas adequada para processamento posterior.

```csharp
        // Save the filled barcode as a PNG image
        filledPlanet.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Após executar o programa, você encontrará `PostalPlanetFilledBars.png` na pasta de saída. Abra‑o para verificar que as barras estão sólidas (preenchidas).

## Etapa 4: Criar um gerador para um código de barras Planet vazio

Um **empty planet barcode** exibe os mesmos dados, mas com barras não preenchidas (brancas). Isso é útil para designs visuais que sobrepõem o código de barras em fundos coloridos.

```csharp
        // Create a generator for an empty Planet barcode (unfilled bars)
        BarcodeGenerator emptyPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

A chamada ao construtor é idêntica à versão preenchida; a diferença está no parâmetro que mudaremos a seguir.

## Etapa 5: Reutilizar a mesma X‑dimension

Para manter o tamanho visual consistente, aplique a mesma largura de barra ao código de barras vazio.

```csharp
        // Use the same bar width as before
        emptyPlanet.Parameters.Barcode.XDimension.Pixels = 4;
```

Reutilizar os **barcode generator parameters** garante que ambas as imagens se alinhem perfeitamente quando colocadas lado a lado.

## Etapa 6: Alternar para barras não preenchidas

A flag `FilledBars` determina se as barras são renderizadas como preto sólido (padrão) ou branco transparente.

```csharp
        // Configure the generator to produce empty (unfilled) bars
        emptyPlanet.Parameters.Barcode.FilledBars = false;
```

*Por que isso importa:* Definir `FilledBars = false` inverte o modo de renderização, que é a distinção principal entre um código de barras Planet preenchido e um vazio.

## Etapa 7: Salvar o código de barras Planet vazio

Finalmente, exporte a versão vazia para PNG.

```csharp
        // Save the empty barcode as a PNG image
        emptyPlanet.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

Quando você executar o programa, dois arquivos aparecerão:

* `PostalPlanetFilledBars.png` – barras pretas sólidas.
* `PostalPlanetEmptyBars.png` – barras transparentes (não preenchidas).

Ambas as imagens contêm os mesmos dados (`123456`) e compartilham a mesma X‑dimension, tornando‑as intercambiáveis na maioria dos cenários de UI.

## Exemplo completo e executável

Juntando tudo, aqui está o arquivo fonte completo que você pode copiar‑colar em um novo projeto de console:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PlanetBarcodeDemo
{
    static void Main()
    {
        // ----------- Filled Planet barcode -----------
        BarcodeGenerator filledPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        filledPlanet.Parameters.Barcode.XDimension.Pixels = 4;
        filledPlanet.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // ----------- Empty Planet barcode ------------
        BarcodeGenerator emptyPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        emptyPlanet.Parameters.Barcode.XDimension.Pixels = 4;
        emptyPlanet.Parameters.Barcode.FilledBars = false;
        emptyPlanet.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**Saída esperada**

Executar o programa cria dois arquivos PNG no diretório de trabalho do executável. Abra‑os com qualquer visualizador de imagens:

* **Versão preenchida** – barras escuras e sólidas que são facilmente legíveis por scanners padrão.
* **Versão vazia** – as barras aparecem como lacunas brancas sobre fundo preto, útil para efeitos de sobreposição.

## Armadilhas comuns e dicas avançadas

| Problema | Por que acontece | Como corrigir |
|----------|------------------|---------------|
| Barras parecem muito finas | X‑dimension deixada no padrão (1 pixel) | Defina `XDimension.Pixels` para 3‑5 pixels para uso em tela; aumente para impressões de alta resolução. |
| Código de barras vazio aparece completamente preto | `FilledBars` não definido como `false` | Garanta que `emptyPlanet.Parameters.Barcode.FilledBars = false;` seja executado **depois** de definir a X‑dimension. |
| Arquivo PNG está ausente | Caminho de saída está incorreto ou o diretório não existe | Forneça um caminho completo (`@"C:\Barcodes\PostalPlanetFilledBars.png"`) ou crie o diretório previamente com `Directory.CreateDirectory`. |
| Código de barras não escaneia | String de dados contém caracteres ilegais para a simbologia Planet | Códigos de barras Planet aceitam apenas carga numérica; valide a entrada com `int.TryParse`. |

**Dica avançada:** Se precisar incorporar o código de barras em um PDF, você pode carregar o PNG gerado em um `PdfDocument` usando Aspose.PDF, ou adicionar diretamente o código de barras como um fluxo de imagem sem gravar no disco.

## Próximos passos

Agora que você pode **criar imagens de código de barras planetário**, considere explorar estes tópicos relacionados:

- [Criar código de barras Planet em C# – Guia completo passo a passo](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Gerador de código de barras C# – exemplo de criação de código de barras Planet e RM4SCC](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [Gerar código de barras postal em C# – Guia completo com código de barras Planet](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}