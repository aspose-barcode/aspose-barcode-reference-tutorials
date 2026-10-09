---
category: general
date: 2026-09-29
description: Como definir a largura de um código de barras GS1 DataBar Omni‑Directional
  e como alterar a altura usando C#. Siga um guia passo a passo com código completo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to change height
language: pt
lastmod: 2026-09-29
og_description: Como definir a largura de um código de barras GS1 DataBar Omni‑Directional
  e como alterar a altura em C#. Aprenda as chamadas de API exatas e veja um exemplo
  completo e executável.
og_image_alt: Screenshot of two GS1 DataBar barcodes with different heights
og_title: Como definir a largura de um código de barras GS1 DataBar – Guia C#
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  headline: How to set width and adjust height for a GS1 DataBar Omni‑Directional
    barcode in C#
  type: TechArticle
- description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  name: How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode
    in C#
  steps:
  - name: Why the X‑dimension matters
    text: '* **Scanner tolerance** – Most scanners expect a minimum module width;
      too small a value can cause read errors. * **Print resolution** – When printing
      at 300 dpi, a 2 px module translates to ~0.17 mm, which is within the recommended
      range for GS1 DataBar. * **Image size** – Larger X‑dimension values'
  - name: Tips for reliable width settings
    text: '* **Never set XDimension below 1 px** – the library will clamp the value,
      but the resulting barcode may be unreadable. * **Match the target DPI** – if
      you render to a high‑resolution format (e.g., TIFF at 600 dpi), increase XDimension
      proportionally. * **Test with a real scanner** – after changing t'
  - name: Understanding bar height
    text: '* **Visual balance** – Taller bars improve readability on low‑contrast
      backgrounds but increase the image’s vertical footprint. * **Regulatory limits**
      – Some standards (e.g., retail labeling) specify a maximum bar height; adjust
      accordingly. * **Aspect ratio** – Changing height does not affect the '
  - name: Edge‑case handling for height adjustments
    text: '| Situation | Recommended approach | |-----------|----------------------|
      | Height < 10 px | Increase to at least 10 px; very short bars may be ignored
      by scanners. | | Very tall bars (≥ 100 px) | Verify that the output medium (paper,
      label) can accommodate the extra space. | | Need proportional sca'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
- GS1 DataBar
title: Como definir a largura e ajustar a altura de um código de barras GS1 DataBar
  Omni‑Directional em C#
url: /pt/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como definir a largura e ajustar a altura de um código de barras GS1 DataBar Omni‑Directional em C#

Definir a largura de um código de barras GS1 DataBar Omni‑Directional é uma tarefa frequente quando você precisa de dimensionamento exato para equipamentos de leitura. Neste tutorial, você também aprenderá **como alterar a altura** para que o código de barras se ajuste perfeitamente ao seu layout. O guia conduz você por todo o processo, desde a configuração do projeto até um exemplo de código totalmente executável.

Cobriremos:

* O pacote NuGet necessário e a versão do .NET.
* Por que a X‑dimension (largura do módulo) importa para a legibilidade do código de barras.
* As chamadas de API exatas para **como definir a largura** e **como alterar a altura**.
* Tratamento de casos extremos, como largura mínima do módulo e renderização em alta resolução.
* Um exemplo completo, pronto para copiar e colar, que produz dois arquivos PNG com alturas de barra diferentes.

## Pré-requisitos

| Requisito | Motivo |
|------------|--------|
| .NET 6.0 SDK ou posterior | O exemplo usa recursos modernos de C# e funciona no Windows, Linux ou macOS. |
| Visual Studio 2022 (ou qualquer IDE C#) | Fornece IntelliSense para a API Aspose.Barcode. |
| **Aspose.Barcode for .NET** NuGet package | Contém `BarcodeGenerator`, `EncodeTypes` e suporte a formatos de imagem. Instale com `dotnet add package Aspose.Barcode`. |
| Permissão de gravação em uma pasta onde os arquivos PNG serão salvos | O gerador grava as imagens de saída no disco. |

## Como definir a largura do código de barras

A etapa **como definir a largura** é realizada configurando a propriedade `XDimension` dos parâmetros do código de barras. `XDimension` representa a largura do módulo (a menor barra ou espaço) em pixels, pontos ou milímetros. Defini‑la corretamente garante que o código de barras atenda às especificações do scanner.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a generator for a GS1 DataBar Omni‑Directional barcode.
            // The value "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ **How to set width**: define the module width (X‑dimension) in pixels.
            // A value of 2 px is a common choice that balances readability and image size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // The remaining steps (height, saving) are shown in the next section.
```

### Por que a dimensão X é importante

* **Tolerância do scanner** – A maioria dos scanners espera uma largura mínima de módulo; um valor muito pequeno pode causar erros de leitura.
* **Resolução de impressão** – Ao imprimir a 300 dpi, um módulo de 2 px equivale a ~0,17 mm, que está dentro da faixa recomendada para GS1 DataBar.
* **Tamanho da imagem** – Valores maiores de dimensão X aumentam a largura total do código de barras, o que pode afetar as restrições de layout.

### Dicas para configurações de largura confiáveis

* **Nunca defina XDimension abaixo de 1 px** – a biblioteca limitará o valor, mas o código de barras resultante pode ficar ilegível.
* **Combine com o DPI alvo** – se você renderizar para um formato de alta resolução (ex.: TIFF a 600 dpi), aumente XDimension proporcionalmente.
* **Teste com um scanner real** – após alterar a largura, valide o código de barras no dispositivo que o lerá.

## Como alterar a altura do código de barras

Uma vez que a largura esteja definida, você pode controlar o tamanho vertical com a propriedade `BarHeight`. O código a seguir demonstra **como alterar a altura** de 30 px para 60 px e salvar duas imagens separadas.

```csharp
            // 3️⃣ Set the first bar height to 30 pixels and save the image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ **How to change height**: increase the bar height to 60 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            // The program ends here; two PNG files are written to the execution folder.
        }
    }
}
```

### Entendendo a altura da barra

* **Equilíbrio visual** – Barras mais altas melhoram a legibilidade em fundos de baixo contraste, mas aumentam a pegada vertical da imagem.
* **Limites regulatórios** – Algumas normas (ex.: rotulagem de varejo) especificam uma altura máxima da barra; ajuste conforme necessário.
* **Proporção** – Alterar a altura não afeta a largura do módulo; você pode ajustar ambos independentemente.

### Tratamento de casos extremos para ajustes de altura

| Situação | Abordagem recomendada |
|-----------|----------------------|
| Height < 10 px | Aumente para pelo menos 10 px; barras muito curtas podem ser ignoradas pelos scanners. |
| Very tall bars (≥ 100 px) | Verifique se o meio de saída (papel, etiqueta) pode acomodar o espaço extra. |
| Need proportional scaling | Calcule `BarHeight = XDimension * desiredRatio` para manter a consistência visual. |

## Exemplo completo e executável

Abaixo está o programa completo que combina as etapas **como definir a largura** e **como alterar a altura**. Copie o código para um novo projeto de console, restaure o pacote NuGet Aspose.Barcode e execute‑o. Dois arquivos PNG aparecerão na pasta `bin/Debug/net6.0`.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // Initialize the barcode generator (GS1 DataBar Omni‑Directional)
            // ------------------------------------------------------------
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // ------------------------------------------------------------
            // **How to set width** – define the module width (X‑dimension)
            // ------------------------------------------------------------
            generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px = ~0.17 mm at 300 dpi

            // ------------------------------------------------------------
            // First image: bar height = 30 px
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight30Pixels.png");

            // ------------------------------------------------------------
            // **How to change height** – increase to 60 px and save again
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight60Pixels.png");

            // ------------------------------------------------------------
            // End of demo
            // ------------------------------------------------------------
        }
    }
}
```

**Saída esperada**

Executar o programa produz dois arquivos PNG:

* `DatabarBarHeight30Pixels.png` – um código de barras com 30 px de altura, módulos de 2 px de largura.
* `DatabarBarHeight60Pixels.png` – o mesmo código de barras com o dobro da altura vertical.

Abra qualquer uma das imagens em qualquer visualizador; você verá um símbolo GS1 DataBar Omni‑Directional limpo, pronto para leitura.

## Perguntas comuns respondidas

| Pergunta | Resposta |
|----------|----------|
| *Posso usar milímetros em vez de pixels?* | Sim. Defina `generator.Parameters.Barcode.XDimension.Millimeters` e `BarHeight.Millimeters`. A biblioteca converte para pixels do dispositivo com base no DPI da imagem. |
| *E se eu precisar de um tipo de código de barras diferente?* | Substitua `EncodeTypes.DatabarOmniDirectional` por qualquer outro valor de `EncodeTypes` (ex.: `EncodeTypes.QR`). As propriedades de largura e altura funcionam da mesma forma. |
| *Existe uma maneira de gerar SVG em vez de PNG?* | Use `BarCodeImageFormat.Svg` na chamada `Save`. As configurações de largura/altura permanecem aplicáveis. |
| *Preciso chamar `generator.Dispose()`?* | O `BarcodeGenerator` implementa `IDisposable`. Em um aplicativo de console você pode envolvê‑lo em um bloco `using`, mas para exemplos de curta duração é opcional. |

## Conclusão

Você agora sabe **como definir a largura** de um código de barras GS1 DataBar Omni‑Directional e **como alterar a altura** usando a API Aspose.Barcode em C#. O exemplo completo demonstra a criação de um gerador, a configuração de `XDimension` e `BarHeight`, e a gravação de arquivos PNG com diferentes tamanhos verticais.  

A partir daqui, você pode:

* Experimentar com outros `EncodeTypes` (ex.: QR, Code128).
* Renderizar para formatos de alta resolução como TIFF para impressão.
* Integrar o gerador em uma API web que devolva códigos de barras sob demanda.

Feliz codificação, e que seus códigos de barras sejam sempre lidos com clareza!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Como Alterar a Altura do Código de Barras em C# – Guia Completo](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Exemplo de gerador de código de barras em C# – definir largura e altura](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [Como usar um gerador de código de barras C# para criar códigos DataBar Omni‑directional](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}