---
date: 2026-09-08
description: Aprenda como criar code 128 barcode e gerar barcodes GS1 em C# com Aspose.BarCode
  para .NET. Guia passo a passo, pré-requisitos e personalização sem código.
keywords:
- create code 128 barcode
- generate gs1 barcode
- how to generate barcode
- create barcode from data
- step by step barcode
lastmod: 2026-09-08
linktitle: Exemplo GS1 Code 128
og_description: Aprenda como criar code 128 barcode e gerar barcodes GS1 em C# com
  Aspose.BarCode para .NET. Siga um guia passo a passo para gerar e salvar imagens
  de barcode rapidamente.
og_image_alt: 'Developer guide: create code 128 barcode with Aspose.BarCode .NET'
og_title: Como criar code 128 barcode com GS1 usando Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-08'
  description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  headline: How to create code 128 barcode with GS1 using Aspose.BarCode
  type: TechArticle
- description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  name: How to create code 128 barcode with GS1 using Aspose.BarCode
  steps:
  - name: set your directory path
    text: Define the folder where the generated image will be stored. Keeping the
      path configurable makes the code reusable across environments. Replace `"Your
      Directory Path"` with an absolute or relative path that your application can
      write to, such as `@"C:\Barcodes"` or `Path.Combine(Environment.CurrentDi
  - name: create a GS1 Code 128 barcode
    text: Create the barcode generator, specify the symbology, and provide GS1‑formatted
      data. The data string must include Application Identifiers wrapped in parentheses.
      The example uses the GTIN `(01)12345678901231`, a serial number `(21)ASPOSE`,
      and an additional custom AI `(30)9876`. Aspose.BarCode autom
  - name: customize barcode parameters
    text: Adjust visual parameters such as `XDimension` (the width of the narrow bar)
      to control the barcode’s density. You can also modify height, colors, and margins.
      Setting `XDimension = 2` yields a barcode that is easily scannable by most handheld
      readers while keeping the image size modest.
  - name: save the barcode image
    text: Persist the generated barcode to disk. You may choose PNG for lossless quality,
      JPEG for smaller files, or TIFF for printing workflows. The `Save` method writes
      the image file in the format indicated by the file extension. Replace `GS1Code128Example.png`
      with any valid filename and extension that ma
  - name: verify the barcode (optional)
    text: After saving, you can load the image back into your application or use a
      barcode scanner to confirm that the encoded data matches the original string.
      This step is useful during development and automated testing.
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode works with .NET Core and .NET 5/6, so you can expose
      a lightweight REST endpoint that returns barcode images on demand.
    question: Can I generate barcodes in a web API without installing the full .NET
      Framework?
  - answer: Absolutely. Loop through a collection of data strings, instantiate a `BarcodeGenerator`
      for each, and call `Save` inside the loop. The library is thread‑safe for parallel
      processing.
    question: Does the library support batch generation of multiple barcodes?
  - answer: Use Aspose.PDF to create a PDF document, then call `PdfPage.AddImage`
      with the barcode image stream. This avoids writing intermediate files to disk.
    question: Is there a way to embed the barcode directly into a PDF?
  - answer: Set `BarcodeGenerator.Options.Barcode.XDimension` to at least 0.33 mm
      and enable `BarHeight` according to the label size. Aspose.BarCode validates
      the AI format and throws an exception for invalid data.
    question: How can I ensure the barcode meets ISO/GS1 quality standards?
  - answer: Aspose offers perpetual, subscription, and cloud‑based licensing models.
      A trial license works for evaluation, but a paid license removes the evaluation
      watermark and unlocks all features.
    question: What licensing options are available for production use?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- create code 128 barcode
- Aspose.BarCode
- .NET barcode generation
title: Como criar code 128 barcode com GS1 usando Aspose.BarCode
url: /pt/net/gs1-barcode-encoding/gs1-code-128-example/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar código de barras code 128 com GS1 usando Aspose.BarCode

Neste tutorial, você aprenderá como **criar código de barras code 128** que está em conformidade com o padrão GS1 usando a biblioteca Aspose.BarCode para .NET. Seja para inventário, envio ou ponto de venda, este guia o acompanha em cada passo — desde a configuração do ambiente de desenvolvimento até a gravação da imagem final — para que você possa começar a gerar códigos de barras confiáveis em minutos.

## Respostas rápidas
- **Qual é a classe principal para gerar um código de barras?** `BarcodeGenerator` cria e configura a imagem do código de barras.  
- **Qual simbologia o GS1 Code 128 usa?** Ele usa o tipo `EncodeTypes.Code128` com formatação de dados específica do GS1.  
- **Preciso de uma licença para desenvolvimento?** Um teste gratuito funciona para avaliação; uma licença comercial é necessária para produção.  
- **Posso mudar o formato da imagem?** Sim — salve como PNG, JPEG, BMP ou TIFF alterando a extensão do arquivo.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ e .NET 6+.

## O que é criar código de barras code 128?
`create code 128 barcode` refere-se à geração de um código de barras linear que codifica dados alfanuméricos usando a simbologia Code 128, amplamente adotada para logística porque suporta o conjunto completo ASCII e pode incorporar Identificadores de Aplicação GS1. O código de barras pode armazenar identificadores de produto, números de série e outros dados personalizados, tornando‑o adequado para uma ampla gama de cenários de negócios.

## Por que usar Aspose.BarCode para GS1 Code 128?
Aspose.BarCode suporta **mais de 30 simbologias de código de barras** e pode renderizar imagens de até **10.000 × 10.000 px** sem perda de qualidade, tornando‑a adequada para impressão de etiquetas de alta resolução. A biblioteca também valida estruturas de dados GS1 automaticamente, reduzindo o risco de códigos de barras malformados nas linhas de produção. Além disso, oferece amplas opções de personalização de tamanho, cor e layout, o que ajuda a atender aos rigorosos padrões da indústria.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem o seguinte:

1. **Ambiente de desenvolvimento .NET** – Visual Studio 2022, Rider ou qualquer IDE que suporte .NET 6+.  
2. **Aspose.BarCode for .NET** – faça o download da **página de download do Aspose.BarCode for .NET** em [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/) e adicione o pacote NuGet `Aspose.BarCode` ao seu projeto.  
3. **Conhecimento básico de C#** – você deve estar confortável em criar aplicações console ou Windows.  
4. **Entendimento do GS1 Code 128** – opcional, mas útil; o GS1 usa Identificadores de Aplicação (AIs) como `(01)` para GTIN e `(21)` para números de série.

## Como criar código de barras code 128 passo a passo

Carregue a biblioteca, configure o tipo de código de barras, defina os dados GS1, personalize as dimensões e, finalmente, salve a imagem. A resposta direta à pergunta “como criar código de barras code 128?” é: **instanciar `BarcodeGenerator` com `EncodeTypes.Code128` e dados formatados para GS1, ajustar `XDimension` se necessário, então chamar `Save` com o nome de arquivo e formato desejados**. As seções a seguir detalham cada passo.

### Etapa 1: defina o caminho do diretório
Defina a pasta onde a imagem gerada será armazenada. Manter o caminho configurável torna o código reutilizável em diferentes ambientes.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Substitua `"Your Directory Path"` por um caminho absoluto ou relativo ao qual sua aplicação possa gravar, como `@"C:\\Barcodes"` ou `Path.Combine(Environment.CurrentDirectory, "Output")`.

### Etapa 2: criar um código de barras GS1 Code 128
Crie o gerador de código de barras, especifique a simbologia e forneça dados formatados para GS1. A string de dados deve incluir Identificadores de Aplicação entre parênteses.

```csharp
string path = "Your Directory Path";
```

O exemplo usa o GTIN `(01)12345678901231`, um número de série `(21)ASPOSE` e um AI personalizado adicional `(30)9876`. Aspose.BarCode insere automaticamente o caractere FNC1 necessário para conformidade GS1.

### Etapa 3: personalizar parâmetros do código de barras
Ajuste parâmetros visuais como `XDimension` (a largura da barra estreita) para controlar a densidade do código de barras. Você também pode modificar altura, cores e margens.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1Code128, "(01)12345678901231(21)ASPOSE(30)9876");
```

Definir `XDimension = 2` gera um código de barras que pode ser escaneado facilmente pela maioria dos leitores portáteis, mantendo o tamanho da imagem modesto.

### Etapa 4: salvar a imagem do código de barras
Persistir o código de barras gerado no disco. Você pode escolher PNG para qualidade sem perdas, JPEG para arquivos menores ou TIFF para fluxos de impressão. O método `Save` grava o arquivo de imagem no formato indicado pela extensão do arquivo.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

Substitua `GS1Code128Example.png` por qualquer nome de arquivo válido e extensão que corresponda ao formato de saída desejado.

### Etapa 5: verificar o código de barras (opcional)
Após salvar, você pode carregar a imagem de volta na sua aplicação ou usar um scanner de código de barras para confirmar que os dados codificados correspondem à string original. Esta etapa é útil durante o desenvolvimento e testes automatizados.

```csharp
gen.Save($"{path}GS1Code128Example.png", BarCodeImageFormat.Png);
```

## Problemas comuns e dicas de solução
- **FNC1 não detectado** – Certifique‑se de que a string de dados começa com um parêntese de abertura e inclui AIs GS1 válidos; a biblioteca insere FNC1 automaticamente apenas para padrões reconhecidos.  
- **Imagem não salva** – Verifique se o diretório de destino existe e se a aplicação tem permissão de gravação. Use `Directory.CreateDirectory(path)` para criá‑lo dinamicamente.  
- **Código de barras muito denso** – Diminua `XDimension` ou aumente a altura da imagem para dar mais espaço aos leitores para ler barras estreitas.  
- **Caracteres não suportados** – Code 128 só pode codificar o conjunto completo ASCII; evite caracteres Unicode fora desse intervalo.

## Perguntas frequentes

**Q: Posso gerar códigos de barras em uma API web sem instalar o .NET Framework completo?**  
A: Sim, Aspose.BarCode funciona com .NET Core e .NET 5/6, portanto você pode expor um endpoint REST leve que retorna imagens de códigos de barras sob demanda.

**Q: A biblioteca suporta geração em lote de múltiplos códigos de barras?**  
A: Absolutamente. Percorra uma coleção de strings de dados, instancie um `BarcodeGenerator` para cada uma e chame `Save` dentro do loop. A biblioteca é thread‑safe para processamento paralelo.

**Q: Existe uma maneira de incorporar o código de barras diretamente em um PDF?**  
A: Use Aspose.PDF para criar um documento PDF, então chame `PdfPage.AddImage` com o fluxo de imagem do código de barras. Isso evita a escrita de arquivos intermediários no disco.

**Q: Como posso garantir que o código de barras atenda aos padrões de qualidade ISO/GS1?**  
A: Defina `BarcodeGenerator.Options.Barcode.XDimension` para pelo menos 0,33 mm e habilite `BarHeight` de acordo com o tamanho da etiqueta. Aspose.BarCode valida o formato AI e lança uma exceção para dados inválidos.

**Q: Quais opções de licenciamento estão disponíveis para uso em produção?**  
A: Aspose oferece modelos de licenciamento perpétuo, por assinatura e baseado em nuvem. Uma licença de avaliação funciona para testes, mas uma licença paga remove a marca d'água de avaliação e desbloqueia todos os recursos.

## Recursos adicionais

- **Documentação** – Acesse a referência completa da API em [https://reference.aspose.com/barcode/net/](https://reference.aspose.com/barcode/net/).  
- **Download** – Obtenha a versão mais recente da biblioteca em [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/).  
- **Teste gratuito** – Inicie um teste de 30 dias em [https://releases.aspose.com/](https://releases.aspose.com/).  
- **Compra** – Adquira uma licença comercial em [https://purchase.aspose.com/buy](https://purchase.aspose.com/buy).  
- **Suporte** – Participe do fórum da comunidade em [https://forum.aspose.com/c/barcode/13](https://forum.aspose.com/c/barcode/13) para ajuda na solução de problemas.

---

**Última atualização:** 2026-09-08  
**Testado com:** Aspose.BarCode 24.11 for .NET  
**Autor:** Aspose

## Tutoriais relacionados

- [Como criar código de barras ITF-14 .NET – Tutoriais abrangentes do Aspose.BarCode](/barcode/net/)
- [Gerar códigos de barras Databar 2D unidimensionais usando Aspose.BarCode .NET API](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}