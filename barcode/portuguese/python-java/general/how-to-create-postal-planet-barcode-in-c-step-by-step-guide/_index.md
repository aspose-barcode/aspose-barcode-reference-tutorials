---
category: general
date: 2026-09-23
description: Aprenda a criar imagens de código de barras Postal Planet em C# com barras
  preenchidas e vazias. Siga este exemplo completo usando BarcodeGenerator e configurações
  de dimensão X.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal planet barcode
- Planet barcode generator C#
- barcode X‑dimension pixels
- filled bars vs empty bars
- BarCodeImageFormat PNG
language: pt
lastmod: 2026-09-23
og_description: Crie o código de barras Postal Planet em C# com este tutorial detalhado.
  Gere estilos de barras preenchidas e vazias usando BarcodeGenerator e configurações
  de dimensão X.
og_image_alt: Screenshot showing a created postal planet barcode with filled bars
og_title: Crie o código de barras Postal Planet em C# – guia completo de programação
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to create postal planet barcode images in C# with filled
    and empty bars. Follow this complete example using BarcodeGenerator and X‑dimension
    settings.
  headline: How to create postal planet barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: Como criar código de barras Postal Planet em C# – guia passo a passo
url: /pt/python-java/general/how-to-create-postal-planet-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar código de barras postal Planet em C# – guia passo a passo

Se você precisa **criar imagens de código de barras postal Planet** em uma aplicação .NET, este tutorial mostra uma solução pronta‑para‑usar. Seja construindo um sistema de etiquetas de envio ou uma ferramenta de verificação de endereço, você verá exatamente como gerar variantes de barras preenchidas e barras vazias com a classe Aspose.Barcode `BarcodeGenerator`.

Você aprenderá como configurar o **gerador de código de barras Planet**, definir a **X‑dimension** (a largura de cada barra) em pixels e salvar o resultado como um arquivo PNG. O guia também explica por que você pode escolher barras preenchidas versus barras vazias e como alternar entre as duas com uma única linha de código.

## O que você precisará

* .NET 6.0 SDK ou posterior (o código funciona também com .NET Core e .NET Framework)
* Visual Studio 2022 (ou qualquer IDE que suporte C#)
* O pacote NuGet Aspose.Barcode for .NET (`Aspose.Barcode`) instalado no seu projeto
* Permissão de gravação em uma pasta onde os arquivos PNG gerados serão salvos

Esses pré-requisitos garantem que o exemplo compile sem configuração adicional.

## Etapa 1: Configurar a pasta de saída

O primeiro passo é definir onde as imagens de código de barras serão gravadas. Usar um caminho absoluto ou relativo funciona; apenas certifique-se de que a pasta exista ou crie-a programaticamente.

```csharp
// Step 1: Define the output folder
string outputFolder = "C:/Barcodes/";

// Ensure the folder exists
if (!Directory.Exists(outputFolder))
{
    Directory.CreateDirectory(outputFolder);
}
```

*Por que isso importa*: Se a pasta não existir, `BarcodeGenerator.Save` lança uma exceção. Criar a pasta antecipadamente torna o código mais robusto para ambientes de implantação.

## Etapa 2: Inicializar um gerador de código de barras Planet

O **gerador de código de barras Planet** (EncodeTypes.Planet) é a simbologia específica usada por muitos serviços postais. Você o inicializa com os dados que deseja codificar — neste caso, a string numérica `"123456"`.

```csharp
// Step 2: Create a Planet barcode generator with the data "123456"
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*Por que isso importa*: `EncodeTypes.Planet` indica ao Aspose.Barcode para usar a simbologia Planet, que possui um padrão fixo de barras e espaços adequado para roteamento postal.

## Etapa 3: Configurar a X‑dimension do código de barras

A **X‑dimension do código de barras** controla a largura de cada barra individual. Definir para 4 pixels produz um código de barras claro e legível que imprime bem em impressoras de etiquetas padrão.

```csharp
// Step 3: Set the X‑dimension (width of each bar) to 4 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Por que isso importa*: Uma X‑dimension muito pequena pode tornar o código de barras ilegível, enquanto um valor muito grande desperdiça espaço da etiqueta. Quatro pixels é um ponto ideal comum para impressoras de 300 dpi.

## Etapa 4: Gerar um código de barras Planet com barras preenchidas

O modo de renderização padrão usa **barras preenchidas** (barras pretas em fundo branco). Salve a imagem como PNG para preservar a qualidade sem perdas.

```csharp
// Step 4: Save the barcode using the default setting (filled bars)
barcodeGenerator.Save($"{outputFolder}PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

**Saída esperada**: `PostalPlanetFilledBars.png` mostra um código de barras Planet clássico onde cada barra está preenchida.  

![Example of a created postal planet barcode with filled bars](https://example.com/filled-bars.png "Example of a created postal planet barcode with filled bars")

*Por que isso importa*: Barras preenchidas são a aparência padrão da indústria para a maioria dos scanners postais. Usar PNG garante que a imagem permaneça nítida quando impressa.

## Etapa 5: Criar um segundo gerador para barras vazias

Para ilustrar a comparação **barras preenchidas vs barras vazias**, criamos outra instância de `BarcodeGenerator` com os mesmos dados. Reutilizar os mesmos dados garante que ambas as imagens sejam visualmente comparáveis.

```csharp
// Step 5: Create another Planet barcode generator for the same data
BarcodeGenerator emptyBarGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

## Etapa 6: Aplicar a mesma X‑dimension e mudar para barras vazias

A propriedade `FilledBars` alterna o modo de renderização. Definir como `false` produz **barras vazias** (barras brancas em fundo preto). A X‑dimension permanece idêntica para manter o tamanho consistente.

```csharp
// Step 6: Apply the same X‑dimension and configure the barcode to use empty bars
emptyBarGenerator.Parameters.Barcode.XDimension.Pixels = 4;
emptyBarGenerator.Parameters.Barcode.FilledBars = false;
```

*Por que isso importa*: Alguns serviços postais ou fluxos de trabalho personalizados exigem o esquema de cores inverso para melhor contraste em mídia de tom escuro. A flag `FilledBars` oferece essa flexibilidade com uma única linha de código.

## Etapa 7: Gerar o código de barras Planet com barras vazias

Finalmente, salve a versão de barras vazias na mesma pasta de saída.

```csharp
// Step 7: Save the barcode with empty bars
emptyBarGenerator.Save($"{outputFolder}PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Saída esperada**: `PostalPlanetEmptyBars.png` exibe o mesmo padrão Planet, mas as barras são vazias (brancas) enquanto o fundo é preto.

![Example of a created postal planet barcode with empty bars](https://example.com/empty-bars.png "Example of a created postal planet barcode with empty bars")

## Verificar os resultados

Abra os dois arquivos PNG em qualquer visualizador de imagens. Você deve ver dois códigos de barras visualmente idênticos, diferindo apenas na inversão de cores. Para confirmar que os códigos de barras são legíveis, você pode usar um aplicativo de leitura de códigos de barras no smartphone que suporte a simbologia Planet.

Se as imagens aparecerem distorcidas, verifique novamente o valor da **X‑dimension** e assegure que o caminho da pasta de saída não contenha caracteres ilegais.

## Armadilhas comuns e dicas de boas práticas

| Problema | Por que acontece | Solução |
|----------|------------------|---------|
| **Pasta não encontrada** | `Save` lança `DirectoryNotFoundException` quando o caminho está ausente. | Crie a pasta com `Directory.CreateDirectory` antes de salvar. |
| **Tamanho de código de barras incorreto** | Usar uma X‑dimension não inteira ou um valor < 2 pixels produz códigos ilegíveis. | Mantenha a X‑dimension ≥ 2 pixels; 4 pixels funciona na maioria das impressoras. |
| **Inversão de cor não aplicada** | Esquecer de definir `FilledBars = false`. | Defina explicitamente `FilledBars` após configurar a X‑dimension. |
| **Formato de imagem errado** | Salvar como JPEG pode introduzir artefatos de compressão. | Use `BarCodeImageFormat.Png` para saída sem perdas. |

## Expandindo o exemplo

* **Alterar os dados** – Substitua `"123456"` por qualquer string numérica de até 12 caracteres (Planet suporta até 12 dígitos).  
* **Ajustar o tamanho da imagem** – Modifique `XDimension.Pixels` ou defina `Height`/`Width` via `barcodeGenerator.Parameters.Image`.  
* **Adicionar uma borda** – Use `barcodeGenerator.Parameters.Barcode.BorderWidth` para desenhar um contorno fino ao redor do código de barras.  
* **Exportar para outros formatos** – Altere `BarCodeImageFormat.Png` para `Jpeg`, `Bmp` ou `Tiff` se seu fluxo de trabalho exigir.

## Conclusão

Agora você sabe como **criar imagens de código de barras postal Planet** em C# usando o Aspose.Barcode `BarcodeGenerator`. O tutorial abordou a inicialização do **gerador de código de barras Planet**, a definição da **X‑dimension do código de barras** e a produção de arquivos PNG com **barras preenchidas** e **barras vazias**. Com esses fundamentos, você pode integrar a geração de códigos de barras postais em qualquer aplicação .NET, personalizar a aparência e garantir a leitura confiável em sistemas de envio do mundo real.

Pronto para explorar mais? Tente gerar outras simbologias postais (por exemplo, **Postnet** ou **Intelligent Mail**) ou combine o código de barras com uma etiqueta PDF usando Aspose.PDF. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir cobrem tópicos estreitamente relacionados que se baseiam nas técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá-lo a dominar recursos adicionais da API e explorar abordagens alternativas de implementação em seus próprios projetos.

- [Criar imagem de código de barras Planet em C# – Como gerar código de barras postal](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Gerador de código de barras C# – criar código de barras Planet e exemplo RM4SCC](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [Criar código de barras Planet em C# – Guia completo passo a passo](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}