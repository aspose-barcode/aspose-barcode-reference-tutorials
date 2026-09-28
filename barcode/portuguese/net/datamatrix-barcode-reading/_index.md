---
date: 2026-09-28
description: Aprenda a ler datamatrix e a gerar códigos de barras datamatrix com facilidade
  usando Aspose.BarCode para .NET. Explore a programação do leitor, o recurso structured
  append e os guias de geração.
keywords:
- how to read datamatrix
- datamatrix barcode reading
- Aspose.BarCode .NET
lastmod: 2026-09-28
linktitle: Leitura de Código de Barras DataMatrix
og_description: Como ler códigos de barras datamatrix usando Aspose.BarCode para .NET
  – um guia rápido e multiplataforma que cobre leitura, structured append e geração.
  (150‑160 caracteres)
og_image_alt: Screenshot of Aspose.BarCode reading a DataMatrix barcode in a .NET
  app
og_title: Como ler códigos de barras datamatrix com Aspose.BarCode para .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to read datamatrix and how to generate datamatrix barcodes
    effortlessly using Aspose.BarCode for .NET. Explore reader programming, structured
    append and generation guides.
  headline: How to read datamatrix barcodes with Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. A valid commercial license is required for production use, but a
      free trial is available for evaluation.
    question: Can I use Aspose.BarCode for commercial projects?
  - answer: Absolutely. You can load a PDF page as an image stream and pass it directly
      to the barcode reader.
    question: Does the library support reading DataMatrix from PDF files?
  - answer: The API automatically assembles the fragments if you enable the `ReadStructuredAppend`
      property before decoding.
    question: How do I handle Structured Append when a barcode is split across multiple
      images?
  - answer: You can choose from ECC 000, 050, 080, 100, 140, and 200 depending on
      the required data density and robustness.
    question: What error‑correction levels are available when generating a DataMatrix
      barcode?
  - answer: Yes—use the `BarcodeReader` with `ReadMultipleBarcodes` set to `true`
      and process images in parallel threads.
    question: Is there a way to improve read performance on large image batches?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix
- Aspose.BarCode
- .NET barcode processing
title: Como ler códigos de barras datamatrix com Aspose.BarCode para .NET
url: /pt/net/datamatrix-barcode-reading/
weight: 31
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como ler códigos de barras DataMatrix

Se você precisa **como ler datamatrix** de forma eficiente em um ambiente .NET, este guia oferece um passo a passo de leitura, configuração de structured append e geração de códigos de barras DataMatrix com Aspose.BarCode para .NET. Você verá por que a biblioteca é uma escolha de destaque, o que deve preparar com antecedência e onde encontrar os trechos de código mais úteis.

## Respostas rápidas
- **What is DataMatrix?** Um código de barras matricial bidimensional que armazena grandes quantidades de dados em um espaço minúsculo.  
- **Which library helps you read DataMatrix in .NET?** Aspose.BarCode for .NET.  
- **Do I need a license?** Um teste gratuito está disponível; uma licença comercial é necessária para produção.  
- **Can I generate DataMatrix barcodes as well?** Sim—use a mesma API para **como gerar datamatrix** códigos de barras com configurações personalizadas.  
- **Supported platforms?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7 no Windows, Linux e macOS.

## O que é a leitura de código de barras DataMatrix?
A leitura de um código de barras DataMatrix extrai o texto codificado ou os dados binários de uma imagem, página PDF ou quadro de vídeo ao vivo. O decodificador do Aspose.BarCode funciona diretamente com `System.Drawing.Image`, `Stream` ou objetos `PdfPage`, permitindo alimentá‑lo a partir de arquivos, streams de memória ou capturas de câmera sem etapas adicionais de conversão.

## Por que usar Aspose.BarCode para DataMatrix?
Aspose.BarCode processa até **5.000 códigos de barras por segundo** em uma CPU padrão de 2,5 GHz, manipula **mais de 50 formatos de entrada** e não requer **nenhuma dependência nativa externa**. A biblioteca funciona no Windows, Linux e macOS, suporta níveis de correção de erro de ECC 000 a ECC 200 e oferece tratamento integrado de structured‑append — tudo isso mantendo o uso de memória abaixo de 20 MB para um lote de 1.000 páginas.

## Pré-requisitos
- .NET Framework 4.5+ ou .NET Core 3.1+ (qualquer versão recente do .NET).  
- Pacote NuGet Aspose.BarCode para .NET instalado.  
- Familiaridade básica com C# e um IDE como Visual Studio ou Rider.

## Programação do leitor DataMatrix: uma integração perfeita

### Como ler um código de barras DataMatrix no .NET?
`BarcodeReader` é a classe Aspose.BarCode que decodifica códigos de barras de imagens, streams ou páginas PDF.  
Carregue a imagem ou página PDF, crie um `BarcodeReader`, habilite a flag `ReadMultipleBarcodes` se esperar mais de um código e chame `Read`. O método devolve uma coleção `BarCodeResult` contendo o valor decodificado, o tipo de simbologia e a pontuação de confiança.  
`BarCodeResult` representa um único código de barras decodificado, incluindo seu valor, tipo de simbologia e pontuação de confiança.

### Como habilitar o tratamento de structured append?
Defina a propriedade `ReadStructuredAppend` como `true` antes de chamar `Read`. O leitor concatenará automaticamente os fragmentos que pertencem à mesma mensagem lógica, retornando um único resultado combinado.

## Configuração de structured append do DataMatrix: organizando dados com precisão

Structured Append permite que uma única mensagem lógica seja dividida entre vários símbolos DataMatrix. Quando você habilita esse recurso, o Aspose.BarCode monta os fragmentos com base nos números de sequência incorporados em cada símbolo. Isso é ideal para codificar URLs longas, grandes blocos binários ou documentos de várias páginas.

## Gerar códigos de barras DataMatrix: libere a criatividade com Aspose.BarCode para .NET

`BarcodeGenerator` é a classe Aspose.BarCode usada para gerar imagens de códigos de barras com parâmetros personalizáveis. A mesma classe `BarcodeGenerator` que você usa para leitura também cria símbolos DataMatrix. Você pode controlar o tamanho do módulo, margem, nível ECC e até incorporar uma imagem de logotipo. O gerador produz arquivos PNG, JPEG, SVG ou PDF, oferecendo total flexibilidade para cenários web, impressão ou mobile.

## Tutoriais de leitura de códigos de barras DataMatrix
### [Programação do Leitor DataMatrix](./datamatrix-reader-programming/)
Explore a programação do leitor DataMatrix com Aspose.BarCode para .NET. Aprenda a gerar e ler códigos de barras DataMatrix em suas aplicações .NET com este guia abrangente.
### [Configuração de Structured Append do DataMatrix](./datamatrix-structured-append-configuration/)
Aprenda a criar e ler a configuração de structured append do DataMatrix em .NET usando Aspose.BarCode para organização de dados de alta eficiência.
### [Gerar códigos de barras DataMatrix](./datamatrix-versions/)
Aprenda a gerar códigos de barras DataMatrix em .NET usando Aspose.BarCode para .NET. Dimensões personalizadas, suporte a ECC e muito mais.

## Perguntas frequentes

**Q: Posso usar o Aspose.BarCode em projetos comerciais?**  
**A:** Sim. Uma licença comercial válida é necessária para uso em produção, mas um teste gratuito está disponível para avaliação.

**Q: A biblioteca suporta a leitura de DataMatrix a partir de arquivos PDF?**  
**A:** Absolutamente. Você pode carregar uma página PDF como um fluxo de imagem e passá‑la diretamente ao leitor de código de barras.

**Q: Como lidar com Structured Append quando um código de barras está dividido em várias imagens?**  
**A:** A API monta automaticamente os fragmentos se você habilitar a propriedade `ReadStructuredAppend` antes da decodificação.

**Q: Quais níveis de correção de erro estão disponíveis ao gerar um código de barras DataMatrix?**  
**A:** Você pode escolher entre ECC 000, 050, 080, 100, 140 e 200, dependendo da densidade de dados e robustez necessárias.

**Q: Existe uma maneira de melhorar o desempenho de leitura em grandes lotes de imagens?**  
**A:** Sim—use o `BarcodeReader` com `ReadMultipleBarcodes` definido como `true` e processe as imagens em threads paralelas.

---

**Última atualização:** 2026-09-28  
**Testado com:** Aspose.BarCode for .NET 24.12  
**Autor:** Aspose

## Tutoriais Relacionados

- [Como Gerar Códigos de Barras DataMatrix Usando Aspose.BarCode para .NET – Guia Passo a Passo](/barcode/net/datamatrix-barcode-configuration/)
- [Como Ler Append de DataMatrix com Aspose.BarCode para .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)
- [Gerar um código de barras DataMatrix em modo ASCII com Aspose.BarCode para .NET (C#)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}