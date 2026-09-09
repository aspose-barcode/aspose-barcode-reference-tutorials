---
category: general
date: 2026-07-15
description: Tutorial de código de barras Databar empilhado omnidirecional em C#.
  Aprenda como gerar Databar, definir a proporção e usar um gerador de código de barras
  C# para resultados perfeitos.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar stacked omnidirectional
- barcode generator c#
- how to set aspect ratio
- how to generate databar
- create databar barcode
language: pt
lastmod: 2026-07-15
og_description: Código de barras Databar empilhado omnidirecional em C# explicado.
  Siga este tutorial passo a passo para gerar Databar, ajustar a proporção e dominar
  o gerador de códigos de barras em C#.
og_image_alt: Two PNG images showing a databar stacked omnidirectional barcode with
  aspect ratios 15 and 30
og_title: Código de barras DataBar empilhado omnidirecional – Guia C#
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: databar stacked omnidirectional barcode in C# tutorial. Learn how to
    generate databar, set aspect ratio, and use a barcode generator c# for perfect
    results.
  headline: databar stacked omnidirectional barcode in C# – Complete Guide
  type: TechArticle
- description: databar stacked omnidirectional barcode in C# tutorial. Learn how to
    generate databar, set aspect ratio, and use a barcode generator c# for perfect
    results.
  name: databar stacked omnidirectional barcode in C# – Complete Guide
  steps:
  - name: The **X‑Dimension** isn’t too low (below 1 pixel is impossible).
    text: The **X‑Dimension** isn’t too low (below 1 pixel is impossible).
  - name: The **AspectRatio** matches what your scanning hardware expects.
    text: The **AspectRatio** matches what your scanning hardware expects.
  - name: The **output path** is writable—sometimes `UnauthorizedAccessException`
      hides behind a silent failure.
    text: The **output path** is writable—sometimes `UnauthorizedAccessException`
      hides behind a silent failure.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Código de barras DataBar empilhado omnidirecional em C# – Guia completo
url: /pt/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# databar stacked omnidirectional barcode em C# – Guia Completo

Já se perguntou como definir a proporção ao gerar um **databar stacked omnidirectional barcode** em C#? Você não está sozinho. Muitos desenvolvedores esbarram ao tentar ajustar esses códigos de barras para rótulos de varejo ou logística, e a documentação pode ser um pouco escassa.  

Neste tutorial vamos percorrer **como gerar databar**, configurar a X‑Dimension e—o mais importante—**como definir a proporção** para que o scanner o leia perfeitamente. Ao final, você terá um exemplo de código pronto‑para‑executar que cria duas imagens de código de barras lado a lado, uma com proporção 15 e outra com 30. Sem mistério, apenas passos claros.

## O que este guia cobre

- Configurar um **barcode generator c#** usando a popular biblioteca Aspose.BarCode.  
- Entender a anatomia de um símbolo **databar stacked omnidirectional**.  
- Ajustar a **aspect ratio** para atender às especificações GS1.  
- Salvar o resultado como arquivos PNG que podem ser inseridos em qualquer projeto .NET.  

Pré‑requisitos? Apenas um SDK .NET recente (4.6+ ou .NET Core 3.1+) e uma referência NuGet ao `Aspose.BarCode`. Se você já tem isso, está pronto para começar.

---

## Entendendo o databar stacked omnidirectional barcode

O formato **databar stacked omnidirectional** compacta um GTIN de 14 dígitos e alguns dígitos suplementares em um símbolo de duas linhas. É a escolha ideal para itens pequenos onde o espaço é limitado—pense em cosméticos, produtos farmacêuticos ou pacotes de lanche diminutos.

Por que a proporção importa? A especificação do código de barras define uma relação largura‑altura que influencia a confiabilidade da leitura. Muito comprimido, e o scanner pode perder uma barra; muito esticado, e o código pode exceder as dimensões do rótulo. A propriedade `AspectRatio` no objeto `DataBar` permite ajustar esse equilíbrio.

---

## Etapa 1: Criar um gerador de código de barras **databar stacked omnidirectional**

Primeiro, inicialize o gerador com o tipo de codificação correto e os dados que você deseja incorporar. Aqui usamos um valor de exemplo GTIN‑14 entre parênteses, como a especificação exige.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Initialize the generator for a DataBar Stacked Omnidirectional barcode
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

> **Dica:** A string deve começar com “(01)” para indicar à biblioteca que os 14 dígitos seguintes são um GTIN. Esquecer os parênteses gera uma `ArgumentException`.

---

## Etapa 2: Definir o tamanho básico das barras (X‑Dimension)

A X‑Dimension controla quantos pixels cada módulo (a barra mais fina) ocupa. Um ponto de partida comum é 2 pixels por módulo, oferecendo um bom equilíbrio entre legibilidade e tamanho do arquivo.

```csharp
// Set 2 pixels per module – a safe default for most printers
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Se você estiver imprimindo em uma impressora a laser de alta resolução, pode aumentar para 3 ou 4 pixels. Apenas lembre‑se: X‑Dimension maior resulta em dimensões gerais do código de barras maiores.

---

## Etapa 3: **Como definir a proporção** – primeira versão (15)

Agora vem a parte que confunde muitas pessoas: o `AspectRatio`. É um inteiro simples, mas influencia diretamente a altura das linhas empilhadas em relação à largura.

```csharp
// Aspect ratio of 15 – the default for many retail scenarios
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;

// Save the first image
barcodeGenerator.Save(@"YOUR_DIRECTORY\DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

O PNG resultante ficará parecido com isto (imagem de exemplo):

![código de barras databar stacked omnidirectional com proporção 15](databar_aspect_ratio_15.png)

*Texto alternativo da imagem (para SEO):* **código de barras databar stacked omnidirectional com proporção 15**.

---

## Etapa 4: **Como definir a proporção** – segunda versão (30)

Às vezes, uma proporção maior é necessária, especialmente quando a altura do rótulo é generosa ou o scanner espera um símbolo mais alto. Vamos mudar para 30 e salvar um segundo arquivo.

```csharp
// Change the aspect ratio to 30 for a taller barcode
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;

// Save the second image
barcodeGenerator.Save(@"YOUR_DIRECTORY\DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

E a saída:

![código de barras databar stacked omnidirectional com proporção 30](databar_aspect_ratio_30.png)

*Texto alternativo da imagem:* **código de barras databar stacked omnidirectional com proporção 30**.

Você notará que as barras ficam mais altas, mas a largura permanece a mesma porque mantivemos a X‑Dimension constante.

---

## Etapa 5: Verificar a saída – checagem rápida

Abra os dois arquivos PNG em qualquer visualizador de imagens. Ambos devem exibir um código de barras de duas linhas limpo, com os mesmos dados numéricos. Se você tiver um scanner portátil à mão, tente ler cada arquivo. O scanner deve retornar a string GTIN bruta `(01)12345678901231`.  

Se a leitura falhar, verifique:

1. Se a **X‑Dimension** não está muito baixa (abaixo de 1 pixel é impossível).  
2. Se a **AspectRatio** corresponde ao que seu hardware de leitura espera.  
3. Se o **caminho de saída** tem permissão de escrita—às vezes `UnauthorizedAccessException` se esconde atrás de uma falha silenciosa.

---

## Armadilhas comuns ao **criar databar barcode**

| Sintoma | Causa provável | Solução |
|---------|----------------|---------|
| Imagem em branco salva | Incompatibilidade de `EncodeTypes` (ex.: usar `DatabarExpanded` em vez de `DatabarStackedOmniDirectional`) | Verifique `EncodeTypes.DatabarStackedOmniDirectional` |
| Código de barras muito largo | X‑Dimension definida muito alta | Reduza `XDimension.Pixels` |
| Scanner relata “formato inválido” | Proporção não suportada pelo modelo do scanner | Ajuste `AspectRatio` para 15 ou 30 conforme as especificações do dispositivo |
| Exceção ao chamar `Save` | Pasta de saída inexistente ou sem permissão de gravação | Crie a pasta ou execute com privilégios elevados |

---

## Avançado: Escolhendo a proporção dinamicamente

Em aplicações reais você pode precisar escolher a proporção com base no tamanho do rótulo. Aqui está um pequeno método auxiliar que seleciona 15 para rótulos estreitos e 30 para rótulos altos.

```csharp
private static int ChooseAspectRatio(int labelWidthPx, int labelHeightPx)
{
    // Simple heuristic: if height > 2× width, use a taller ratio
    return (labelHeightPx > 2 * labelWidthPx) ? 30 : 15;
}

// Usage
int chosenRatio = ChooseAspectRatio(200, 500);
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = chosenRatio;
barcodeGenerator.Save(@"YOUR_DIRECTORY\DatabarDynamic.png", BarCodeImageFormat.Png);
```

Agora seu código **barcode generator c#** adapta-se em tempo real—sem necessidade de codificar duas gravações separadas.

---

## Recapitulando – o que conseguimos

- **Criamos** um gerador de código de barras **databar stacked omnidirectional** em C#.  
- **Definimos** a X‑Dimension para 2 pixels por módulo, garantindo renderização nítida.  
- **Demonstramos** **como definir a proporção** tanto para 15 quanto para 30, salvando cada um como PNG.  
- **Exploramos** erros comuns e oferecemos um pequeno helper para proporção dinâmica.

Tudo isso cabe em um único arquivo autônomo que você pode inserir em qualquer projeto .NET. Sem scripts externos, sem arquivos de configuração misteriosos.

---

## O que vem a seguir? Expanda sua caixa de ferramentas de códigos de barras

Agora que você dominou o básico de **criar databar barcode**, considere explorar:

- **Adicionar texto legível** abaixo do símbolo (`barcodeGenerator.Parameters.Barcode.CodeTextParameters.ShowCodeText = true`).  
- **Incorporar o código de barras** diretamente em um PDF usando `Aspose.Pdf` para geração de notas fiscais.  
- **Processamento em lote** de uma lista de GTINs com um loop `foreach` e nomeando cada arquivo com seu código de produto.  

Cada um desses tópicos se baseia nos mesmos conceitos centrais que você acabou de aprender, e tornará seus projetos **barcode generator c#** ainda mais poderosos.

---

### Considerações finais

Gerar um **databar stacked omnidirectional** barcode em C# não é mágica; são apenas alguns ajustes de propriedades em uma biblioteca robusta. Controlando a X‑Dimension e a **aspect ratio**, você tem total comando sobre a forma do código de barras e sua confiabilidade de leitura.  

Execute o código, ajuste os números e veja o scanner funcionar. Se encontrar algum obstáculo, consulte a tabela “Armadilhas comuns”—a maioria dos problemas se resolve com um ajuste rápido de propriedade.  

Feliz codificação, e que seus rótulos sempre sejam lidos na primeira tentativa!

## O que você deve aprender a seguir?

Os tutoriais abaixo abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [Customize databar stacked omnidirectional Aspect Ratio in .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)
- [One-Dimensional Databar Barcode Height Adjustment](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}