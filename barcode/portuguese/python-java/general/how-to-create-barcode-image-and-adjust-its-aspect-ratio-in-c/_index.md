---
category: general
date: 2026-10-08
description: Aprenda a criar imagens de código de barras em C# e descubra como ajustar
  a proporção de aspecto para códigos de barras DataBar empilhados omni‑direcionais.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust aspect ratio
- Aspose.BarCode C#
- DataBar stacked omni‑directional
- barcode X‑dimension
language: pt
lastmod: 2026-10-08
og_description: Crie imagem de código de barras em C# e aprenda como ajustar a proporção
  de aspecto para códigos de barras DataBar empilhados omni‑direcionais com um exemplo
  de código completo.
og_image_alt: Result of create barcode image with aspect ratio 15 using Aspose.BarCode
og_title: Criar imagem de código de barras em C# – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  headline: How to create barcode image and adjust its aspect ratio in C#
  type: TechArticle
- description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  name: How to create barcode image and adjust its aspect ratio in C#
  steps:
  - name: Expected output
    text: 'After running the program you will find two PNG files in the execution
      directory:'
  - name: What if I need a different X‑dimension?
    text: You can change `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` to
      any integer greater than zero. For very high‑resolution output (e.g., 300 dpi),
      a value of 3‑4 pixels often yields clearer results.
  - name: How do I choose the right aspect ratio?
    text: 'The optimal ratio depends on the scanning environment: * **Low‑profile
      labels** – use a smaller ratio (e.g., 10‑15) to keep the barcode compact. *
      **Large shipping containers** – a higher ratio (e.g., 25‑35) improves readability
      from a distance. * **Regulatory requirements** – some standards mandate'
  - name: Can I generate other barcode formats with the same code?
    text: Yes. Replace `EncodeTypes.DatabarStackedOmniDirectional` with any other
      `EncodeTypes` value (e.g., `EncodeTypes.Code128`). The rest of the code—X‑dimension,
      aspect ratio (if applicable), and saving—remains the same.
  - name: What if I need to create the image in a different format?
    text: '`BarCodeImageFormat` supports PNG, JPEG, BMP, GIF, and TIFF. Just change
      the second argument of `Save`, for example:'
  - name: Next steps
    text: '* Explore other symbologies such as **Code128** or **QR Code** by swapping
      the `EncodeTypes` value. * Combine the barcode generation with PDF creation
      (e.g., using Aspose.PDF) to embed barcodes directly into invoices. * Experiment
      with dynamic aspect‑ratio selection based on label size—this extends '
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Como criar imagem de código de barras e ajustar sua relação de aspecto em C#
url: /pt/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar imagem de código de barras e ajustar sua proporção em C#

Se você precisa **criar imagem de código de barras** programaticamente, este guia mostra uma solução completa, pronta‑para‑executar. Você verá exatamente **como ajustar a proporção** para um código de barras DataBar empilhado omni‑direcional, um requisito que costuma aparecer em aplicações de varejo e logística.

Neste tutorial você aprenderá a:
* Inicializar um `BarcodeGenerator` da Aspose.BarCode para a simbologia DataBar empilhada omni‑direcional.  
* Definir a X‑dimension (largura do módulo) em pixels para controlar a espessura das barras.  
* Aplicar duas proporções diferentes e salvar cada resultado como um arquivo PNG.  
* Verificar a saída e entender por que a proporção importa.

Nenhuma ferramenta externa é necessária — apenas a biblioteca Aspose.BarCode para .NET e um ambiente de desenvolvimento .NET 6 (ou superior).

## Como criar imagem de código de barras com Aspose.BarCode

O primeiro passo é instanciar o gerador com a simbologia e a string de dados desejadas. O enum `EncodeTypes.DatabarStackedOmniDirectional` indica à Aspose.BarCode que deve produzir um código de barras DataBar empilhado omni‑direcional, amplamente usado em aplicações GS1‑128.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a BarcodeGenerator for DataBar stacked omni‑directional.
        // The data string "(01)12345678901231" follows the GS1 Application Identifier format.
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Por que isso importa:** O objeto `BarcodeGenerator` é o ponto de entrada para todas as tarefas de criação de códigos de barras. Ao especificar a simbologia e os dados brutos antecipadamente, você garante que a imagem gerada esteja em conformidade com o padrão GS1.

## Definindo a X‑dimension (largura do módulo)

A X‑dimension define a largura da barra mais estreita (o módulo). Uma X‑dimension maior produz um código de barras mais espesso, o que pode ser útil para impressoras de baixa resolução.

```csharp
        // 2️⃣ Define the X‑dimension in pixels.
        // A value of 2 pixels provides a good balance between readability and file size.
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Por que isso importa:** Ajustar a X‑dimension faz parte do processo de afinação visual. Não afeta os dados codificados, mas influencia a confiabilidade da leitura em diferentes dispositivos.

## Como ajustar a proporção – primeira versão (15)

A proporção controla a relação altura‑largura do código de barras DataBar. A propriedade `DataBar.AspectRatio` aceita valores inteiros; números maiores produzem barras mais altas.

```csharp
        // 3️⃣ Set the aspect ratio to 15 and save the first image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Por que isso importa:** Uma proporção de 15 é um padrão comum para scanners de varejo. O PNG resultante (`DatabarAspectRatio15.png`) terá uma aparência mais alta, o que pode melhorar o sucesso da leitura em dispositivos portáteis.

## Como ajustar a proporção – segunda versão (30)

Você pode precisar de um código de barras mais alto para formatos de etiqueta específicos. Alterar a proporção é tão simples quanto atribuir um novo valor inteiro antes de chamar `Save` novamente.

```csharp
        // 4️⃣ Change the aspect ratio to 30 and save a second image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Por que isso importa:** Ao demonstrar **como ajustar a proporção**, você pode gerar múltiplas imagens de código de barras a partir da mesma fonte de dados sem recriar o gerador. Isso reduz o uso de memória e acelera o processamento em lote.

### Saída esperada

Após executar o programa, você encontrará dois arquivos PNG no diretório de execução:

| Nome do arquivo                | Proporção | Descrição visual |
|--------------------------------|-----------|-------------------|
| `DatabarAspectRatio15.png`    | 15        | Altura padrão, adequada para a maioria dos scanners de ponto de venda. |
| `DatabarAspectRatio30.png`    | 30        | Barras mais altas, útil para etiquetas grandes ou impressoras de baixa resolução. |

Ambas as imagens contêm o mesmo GTIN codificado `(01)12345678901231`, mas as proporções visuais diferem conforme a proporção que você definiu.

## Perguntas comuns e tratamento de casos extremos

### E se eu precisar de uma X‑dimension diferente?

Você pode alterar `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` para qualquer inteiro maior que zero. Para saída de altíssima resolução (por exemplo, 300 dpi), um valor de 3‑4 pixels costuma gerar resultados mais nítidos.

### Como escolher a proporção correta?

A proporção ideal depende do ambiente de leitura:
* **Etiquetas de perfil baixo** – use uma proporção menor (ex.: 10‑15) para manter o código de barras compacto.
* **Grandes contêineres de envio** – uma proporção maior (ex.: 25‑35) melhora a legibilidade à distância.
* **Requisitos regulatórios** – algumas normas exigem uma altura mínima; consulte a especificação GS1 para valores exatos.

### Posso gerar outros formatos de código de barras com o mesmo código?

Sim. Substitua `EncodeTypes.DatabarStackedOmniDirectional` por qualquer outro valor de `EncodeTypes` (ex.: `EncodeTypes.Code128`). O restante do código — X‑dimension, proporção (se aplicável) e salvamento — permanece o mesmo.

### E se eu precisar criar a imagem em outro formato?

`BarCodeImageFormat` suporta PNG, JPEG, BMP, GIF e TIFF. Basta alterar o segundo argumento de `Save`, por exemplo:

```csharp
barcodeGenerator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

## Dica profissional: reutilizar o gerador para processamento em lote

Quando for necessário criar dezenas de códigos de barras com as mesmas configurações visuais, instancie o gerador uma única vez, atualize apenas a propriedade `CodeText` e chame `Save` repetidamente. Isso evita a sobrecarga de alocar buffers internos a cada iteração.

```csharp
// Example of batch creation
string[] gtins = { "(01)12345678901231", "(01)98765432109876", "(01)55555555555555" };
foreach (var gtin in gtins)
{
    barcodeGenerator.CodeText = gtin;
    barcodeGenerator.Save($"Barcode_{gtin.Substring(4, 6)}.png", BarCodeImageFormat.Png);
}
```

## Conclusão

Agora você sabe como **criar imagem de código de barras** em C# usando Aspose.BarCode e exatamente **como ajustar a proporção** para símbolos DataBar empilhados omni‑direcionais. Controlando a X‑dimension e a proporção, você pode produzir códigos de barras que atendam a qualquer requisito de leitura ou layout, mantendo a implementação simples e fácil de manter.

### Próximos passos

* Explore outras simbologias como **Code128** ou **QR Code** trocando o valor de `EncodeTypes`.  
* Combine a geração de códigos de barras com a criação de PDFs (por exemplo, usando Aspose.PDF) para incorporar códigos diretamente em faturas.  
* Experimente a seleção dinâmica de proporção com base no tamanho da etiqueta — isso amplia o padrão **como ajustar a proporção** para um motor completo de design de etiquetas.

Sinta-se à vontade para adaptar o exemplo, compartilhar seus resultados ou fazer perguntas nos comentários. Boa codificação!

## O que você deve aprender a seguir?

Os tutoriais a seguir abordam tópicos intimamente relacionados que ampliam as técnicas demonstradas neste guia. Cada recurso inclui exemplos de código completos e funcionais com explicações passo a passo para ajudá‑lo a dominar recursos adicionais da API e explorar abordagens alternativas em seus próprios projetos.

- [Como criar código de barras databar empilhado em C# com Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [Como criar imagem de código de barras com Aspose.Barcode em C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [Como ajustar o tamanho do código de barras – Proporção do Codablock F com Aspose.BarCode para .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}