---
category: general
date: 2026-08-12
description: Exemplo de gerador de código de barras que mostra como gerar código de
  barras com tamanho de pixel preciso. Aprenda a definir a largura do módulo, a altura
  da barra e criar códigos de barras Planet.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to generate barcode
- barcode pixel size
- generate planet barcode
- barcode height setting
language: pt
lastmod: 2026-08-12
og_description: O exemplo de gerador de código de barras demonstra como gerar códigos
  de barras com dimensões exatas em pixels. Siga este guia para controlar a largura
  do módulo e a altura da barra para os códigos Planet e RM4SCC.
og_image_alt: Screenshot of a barcode generator example showing a Planet barcode with
  custom pixel size
og_title: exemplo de gerador de código de barras – personalize o tamanho dos pixels
  em C#
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: barcode generator example that shows how to generate barcode with precise
    pixel size. Learn to set module width, bar height and create Planet barcodes.
  headline: barcode generator example – step‑by‑step guide for custom pixel sizes
  type: TechArticle
- description: barcode generator example that shows how to generate barcode with precise
    pixel size. Learn to set module width, bar height and create Planet barcodes.
  name: barcode generator example – step‑by‑step guide for custom pixel sizes
  steps:
  - name: Install the Aspose.BarCode package
    text: 'Open a terminal in your project folder and run:'
  - name: Add the necessary `using` directives
    text: '```csharp using Aspose.BarCode.Generation; using Aspose.BarCode.BarCodeImageFormat;
      ```'
  - name: – generate a Planet barcode with automatically calculated height
    text: '```csharp // Step 1: Generate a Planet barcode with automatically calculated
      height BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet,
      "123456");'
  - name: – generate a Planet barcode with an explicit 100‑pixel height
    text: '```csharp // Step 2: Generate a Planet barcode with an explicit 100‑pixel
      height BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet,
      "123456");'
  - name: – generate an RM4SCC barcode with the same explicit height
    text: '```csharp // Step 3: Generate an RM4SCC barcode with the same explicit
      height BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC,
      "123456");'
  - name: What is **barcode pixel size**?
    text: '*Pixel size* refers to the physical number of screen or printer pixels
      that represent a single module (`XDimension`). A larger pixel size yields a
      bigger barcode, which can be easier for low‑resolution scanners but consumes
      more label real‑estate.'
  - name: How does `BarHeight` affect readability?
    text: The `BarHeight` property controls the vertical length of the bars. Standards
      for most 1‑D barcodes (including Planet and RM4SCC) recommend a minimum height
      of 10 mm when printed at 300 dpi, which translates to roughly 118 pixels. Setting
      a height below that can cause read errors, especially on mobil
  - name: When should you let the library calculate height automatically?
    text: If you’re generating barcodes for on‑screen display only, the automatic
      calculation keeps the aspect ratio consistent and reduces the amount of manual
      tweaking needed. For printed labels that must meet strict ISO specifications,
      you should **explicitly set the bar height**.
  - name: Pro tip on performance
    text: When generating thousands of barcodes in a batch job, reuse a single `BarcodeGenerator`
      instance and only change the `CodeText` and size parameters between saves. This
      avoids repeated allocation of internal rendering objects and can cut execution
      time by up to 30 %.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: exemplo de gerador de código de barras – guia passo a passo para tamanhos de
  pixel personalizados
url: /pt/python-java/general/barcode-generator-example-step-by-step-guide-for-custom-pixe/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# exemplo de gerador de código de barras – guia passo a passo para tamanhos de pixel personalizados

Se você precisa de um **barcode generator example** que permita controlar cada pixel, este guia mostra exatamente como fazer isso. Você aprenderá a definir a largura do módulo, especificar uma altura fixa das barras e gerar códigos de barras Planet e RM4SCC com dimensões previsíveis.

A maioria dos desenvolvedores tem dificuldade em gerar imagens de “como gerar barcode” que pareçam iguais em todas as telas ou impressoras. Os trechos de código abaixo resolvem esse problema ao expor os parâmetros em nível de pixel da biblioteca Aspose.BarCode for .NET, permitindo produzir resultados consistentes sem adivinhações.

## O que você aprenderá

* Como instalar o pacote NuGet necessário.  
* Como gerar um código de barras Planet com altura calculada automaticamente.  
* Como gerar um código de barras Planet com altura explícita de 100 pixels.  
* Como gerar um código de barras RM4SCC usando a mesma altura explícita.  
* Por que o **barcode pixel size** importa para a confiabilidade da leitura.  
* Dicas para solucionar problemas comuns ao gerar imagens de código de barras Planet.  

Você só precisa do .NET 6 ou superior, um ambiente básico de desenvolvimento C# e uma conexão à internet para baixar o pacote NuGet.

---

## exemplo de gerador de código de barras – configure o ambiente de desenvolvimento

Antes de escrever qualquer código, certifique‑se de que a biblioteca Aspose.BarCode está disponível para o seu projeto.

### Instale o pacote Aspose.BarCode

Abra um terminal na pasta do seu projeto e execute:

```bash
dotnet add package Aspose.BarCode
```

O comando adiciona a versão estável mais recente do **Aspose.BarCode** ao seu `csproj`. Após a restauração terminar, você pode começar a usar a classe `BarcodeGenerator`.

> **Pro tip:** Alvo .NET 6 ou .NET 7 para aproveitar as melhorias de desempenho mais recentes e o tratamento padrão UTF‑8.

### Adicione as diretivas `using` necessárias

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;
```

Esses namespaces expõem a classe `BarcodeGenerator` e o enum `BarCodeImageFormat` usados mais adiante no tutorial.

---

## Como gerar código de barras com tamanho de pixel personalizado

Os três passos a seguir ilustram o **barcode generator example** completo. Cada passo se baseia no anterior, de modo que você pode copiar‑colar todo o bloco em um aplicativo console e executá‑lo sem alterações.

### Etapa 1 – gerar um código de barras Planet com altura calculada automaticamente

```csharp
// Step 1: Generate a Planet barcode with automatically calculated height
BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set module width (x‑dimension) to 4 pixels
planetAuto.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG
planetAuto.Save("PlanetAuto.png", BarCodeImageFormat.Png);
```

**Por que isso funciona:**  
*A propriedade `XDimension` define a largura de um único módulo do código de barras (o menor elemento preto ou branco). Quando você omite `BarHeight`, a biblioteca calcula uma altura que mantém a proporção padrão para códigos Planet.*

**Saída esperada:** Um arquivo PNG chamado `PlanetAuto.png` contendo um código Planet limpo. Sua altura se adapta à largura de módulo de 4 pixels, tipicamente cerca de 60 pixels para uma carga útil de seis caracteres.

### Etapa 2 – gerar um código de barras Planet com altura explícita de 100 pixels

```csharp
// Step 2: Generate a Planet barcode with an explicit 100‑pixel height
BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same module width
planetFixed.Parameters.Barcode.XDimension.Pixels = 4;

// Force the bar height to 100 pixels
planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the image
planetFixed.Save("PlanetHeight100.png", BarCodeImageFormat.Png);
```

**Por que você pode precisar disso:**  
Às vezes o equipamento de leitura espera uma altura mínima das barras para detecção confiável. Definindo `BarHeight.Pixels`, você garante que cada imagem gerada atenda a esse requisito, independentemente do comprimento dos dados codificados.

**Saída esperada:** `PlanetHeight100.png` mostra os mesmos dados de antes, mas as barras têm exatamente 100 pixels de altura, dando controle total sobre o tamanho visual.

### Etapa 3 – gerar um código de barras RM4SCC com a mesma altura explícita

```csharp
// Step 3: Generate an RM4SCC barcode with the same explicit height
BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Use the same module width for consistency
rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;

// Apply the 100‑pixel bar height
rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the image
rm4sccFixed.Save("RM4SCCHeight100.png", BarCodeImageFormat.Png);
```

**Por que isso importa:**  
`EncodeTypes.RM4SCC` é um código de barras linear empilhado usado em logística. Alinhar sua altura de barra com a do código Planet simplifica o processamento em lote quando ambas as simbologias aparecem na mesma etiqueta.

**Saída esperada:** `RM4SCCHeight100.png` exibe um código RM4SCC perfeitamente dimensionado, correspondendo à altura de 100 pixels que você definiu para o código Planet.

> **Verificação de resultado:** Abra cada PNG em um visualizador de imagens e confirme que as barras pretas têm exatamente 4 pixels de largura e, onde especificado, 100 pixels de altura. Você também pode enviar os arquivos para um aplicativo de leitura de código de barras para garantir que eles decodifiquem “123456”.

---

## Entendendo o tamanho de pixel do código de barras e a altura das barras

### O que é **barcode pixel size**?

*Pixel size* refere‑se ao número físico de pixels de tela ou impressora que representam um único módulo (`XDimension`). Um tamanho de pixel maior gera um código de barras maior, o que pode ser mais fácil para scanners de baixa resolução, mas consome mais espaço na etiqueta.

### Como `BarHeight` afeta a legibilidade?

A propriedade `BarHeight` controla o comprimento vertical das barras. Normas para a maioria dos códigos 1‑D (incluindo Planet e RM4SCC) recomendam uma altura mínima de 10 mm quando impressos a 300 dpi, o que equivale a aproximadamente 118 pixels. Definir uma altura abaixo disso pode causar erros de leitura, especialmente em câmeras de dispositivos móveis.

### Quando deixar a biblioteca calcular a altura automaticamente?

Se você está gerando códigos de barras apenas para exibição em tela, o cálculo automático mantém a proporção consistente e reduz a necessidade de ajustes manuais. Para etiquetas impressas que precisam atender a especificações ISO rigorosas, você deve **definir explicitamente a altura da barra**.

---

## Armadilhas comuns e boas práticas ao gerar código de barras Planet

| Armadilha | Por que acontece | Solução |
|-----------|------------------|---------|
| As barras aparecem muito finas ou grossas | `XDimension` deixado no padrão (1 pixel) em telas de alta resolução | Defina `XDimension.Pixels` para pelo menos 3‑4 para clareza visual |
| O scanner não consegue ler o código | `BarHeight` está muito pequeno para o comprimento focal do scanner | Use `BarHeight.Pixels` ≥ 100 para a maioria dos scanners móveis |
| A imagem fica borrada após redimensionamento | Salvar como JPEG introduz artefatos de compressão | Salve como PNG (`BarCodeImageFormat.Png`) para saída sem perdas |
| Tipo de código de barras inesperado | Valor errado do enum `EncodeTypes` | Verifique se está usando `EncodeTypes.Planet` para a simbologia Planet |

### Dica profissional sobre desempenho

Ao gerar milhares de códigos de barras em um trabalho em lote, reutilize uma única instância de `BarcodeGenerator` e altere apenas `CodeText` e os parâmetros de tamanho entre as gravações. Isso evita alocações repetidas de objetos internos de renderização e pode reduzir o tempo de execução em até 30 %.

---

## Exemplo completo funcionando – junte tudo

Crie um novo projeto console (`dotnet new console -n BarcodeDemo`) e substitua o conteúdo de `Program.cs` pelo seguinte:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Directory where PNG files will be saved
            string outputDir = Environment.CurrentDirectory;

            // ---------- Planet barcode – automatic height ----------
            var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
            planetAuto.Save($"{outputDir}/PlanetAuto.png", BarCodeImageFormat.Png);
            Console.WriteLine("PlanetAuto.png generated.");

            // ---------- Planet barcode – fixed 100‑pixel height ----------
            var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            planetFixed.Save($"{outputDir}/PlanetHeight100.png", BarCodeImageFormat.Png);
            Console.WriteLine("PlanetHeight100.png generated.");

            // ---------- RM4SCC barcode – same fixed height ----------
            var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            rm4sccFixed.Save($"{outputDir}/RM4SCCHeight100.png", BarCodeImageFormat.Png);
            Console.WriteLine("RM4SCCHeight100.png generated.");

            Console.WriteLine("All barcodes created successfully.");
        }
    }
}
```

Execute o programa com `dotnet run`. Após a execução, você encontrará três arquivos PNG na pasta do projeto, cada um ilustrando um cenário diferente do **barcode generator example**.

---

## Próximos passos e tópicos relacionados

* **Como gerar código de barras em outros formatos** – explore `EncodeTypes.Code128`, `EncodeTypes.QR` e `EncodeTypes.DataMatrix` para necessidades 2‑D.  
* **Incorporando códigos de barras em PDFs** – combine Aspose.BarCode com Aspose.PDF para colocar códigos de barras diretamente em modelos de fatura.  
* **Tamanho dinâmico de código de barras baseado na entrada do usuário** – calculate

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [How to generate barcode java: Create an Exact Barcode Image](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)
- [How to Generate Barcode in Java Create and Set Size for Whole Picture](/barcode/english/java/barcode-basics/creating-setting-size-whole-picture-barcode/)
- [How to create code128 barcode Java and set bar height](/barcode/english/java/barcode-configuration/setting-bars-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}