---
date: 2026-06-09
description: Aprenda como criar código de barras Code128 Java usando Aspose.BarCode.
  Este guia passo a passo mostra como gerar código de barras Java, definir texto personalizado,
  ajustar a largura das barras e salvar a imagem.
keywords:
- create code128 barcode java
- how to generate barcode java
- java barcode generator example
linktitle: Definindo Texto do Código
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create Code128 barcode Java using Aspose.BarCode. This
    step‑by‑step guide shows how to generate barcode Java, set custom text, adjust
    bar width, and save the image.
  headline: Create Code128 Barcode Java – Set Code Text using Aspose.BarCode
  type: TechArticle
- description: Learn how to create Code128 barcode Java using Aspose.BarCode. This
    step‑by‑step guide shows how to generate barcode Java, set custom text, adjust
    bar width, and save the image.
  name: Create Code128 Barcode Java – Set Code Text using Aspose.BarCode
  steps:
  - name: Create an Instance of `BarcodeGenerator`
    text: 'The `BarcodeGenerator` constructor takes two arguments: the barcode symbology
      (`CODE_128`) and the **custom code text** you want to encode, such as `"12345678"`.'
  - name: Adjust Barcode Width for Custom Barcode Text
    text: Set the `XDimension` property (bar width) to control how wide each bar appears.
      In this example we use `0.5` mm, a size that balances readability and label
      space for most applications.
  - name: Save the Barcode Image
    text: Call the `save` method, specifying the output path and image format (JPEG,
      PNG, SVG, etc.). The example saves the file as **`setCodeText.jpg`** in the
      project’s document folder.
  type: HowTo
- questions:
  - answer: Aspose.BarCode for Java.
    question: What library should I use?
  - answer: CODE_128.
    question: Which barcode type is demonstrated?
  - answer: Use the `BarcodeGenerator` constructor or the `setCodeText` method.
    question: How do I set custom barcode text?
  - answer: Yes—adjust `XDimension` (bar width) in millimetres.
    question: Can I change the bar width?
  - answer: A commercial license is required for non‑trial deployments.
    question: Do I need a license for production?
  type: FAQPage
second_title: Aspose.BarCode Java API
title: Criar Código de Barras Code128 Java – Definir Texto do Código usando Aspose.BarCode
url: /pt/java/text-and-styling/setting-code-text/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Código de Barras Code128 em Java – Definir Texto do Código usando Aspose.BarCode

Neste tutorial, você aprenderá como **criar código de barras Code128 Java** usando a biblioteca Aspose.BarCode Java. Seja construindo um sistema de inventário, uma solução de rastreamento de documentos ou qualquer aplicação que precise de códigos de barras, vamos guiá‑lo passo a passo — desde a instanciação de um código de barras **Code128** até a personalização do texto do código e o ajuste fino da largura das barras. Ao final, você terá uma imagem pronta para uso que pode incorporar onde precisar.

## Respostas Rápidas
- **Qual biblioteca devo usar?** Aspose.BarCode for Java.  
- **Qual tipo de código de barras é demonstrado?** CODE_128.  
- **Como definir texto de código de barras personalizado?** Use o construtor `BarcodeGenerator` ou o método `setCodeText`.  
- **Posso alterar a largura das barras?** Sim—ajuste `XDimension` (largura da barra) em milímetros.  
- **Preciso de uma licença para produção?** Uma licença comercial é necessária para implantações não‑trial.

## Como criar um código de barras Code128 em Java?

Carregue o `BarcodeGenerator` com a simbologia `CODE_128` e o texto desejado, defina a largura das barras via `XDimension` e, em seguida, chame `save` para gravar o arquivo de imagem. Esse padrão de três etapas produz um código de barras de alta qualidade em segundos e funciona em qualquer runtime Java 8+, Windows, Linux ou macOS.

## Pré‑requisitos para gerar código de barras Java

- Conhecimento básico de programação Java.  
- Um ambiente de desenvolvimento Java (JDK 8 ou superior).  
- Biblioteca Aspose.BarCode para Java – faça o download **[aqui](https://releases.aspose.com/barcode/java/)**.  
- Sua IDE preferida (IntelliJ IDEA, Eclipse, etc.).

## Importar Pacotes

Importe os namespaces essenciais do Aspose.BarCode para que as classes estejam disponíveis em seu projeto.

## O que é a classe BarcodeGenerator?

`BarcodeGenerator` é a classe central do Aspose.BarCode que cria imagens de códigos de barras na memória. Ela fornece uma API fluente para definir simbologia, texto do código, dimensões, cores e opções adicionais de renderização antes de exportar o resultado para formatos como PNG, JPEG, SVG ou PDF. Você também pode personalizar legendas, margens e níveis de correção de erro conforme necessário.

## Tutorial do Gerador de Código de Barras: Criar um Código de Barras Code128

### Etapa 1: Criar uma Instância de `BarcodeGenerator`

O construtor `BarcodeGenerator` recebe dois argumentos: a simbologia do código de barras (`CODE_128`) e o **texto de código personalizado** que você deseja codificar, como `"12345678"`.

```java
// The path to the documents directory.
String path = "Your Directory Path";
// The path to the resource directory.
String dataDir = "Your Document Directory";
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
```

### Etapa 2: Ajustar a Largura do Código de Barras para Texto Personalizado

Defina a propriedade `XDimension` (largura da barra) para controlar quão larga cada barra aparece. Neste exemplo usamos `0.5` mm, um tamanho que equilibra legibilidade e espaço de etiqueta para a maioria das aplicações.

```java
generator.getParameters().getBarcode().getXDimension().setMillimeters(0.5f);
```

### Etapa 3: Salvar a Imagem do Código de Barras

Chame o método `save`, especificando o caminho de saída e o formato da imagem (JPEG, PNG, SVG, etc.). O exemplo salva o arquivo como **`setCodeText.jpg`** na pasta de documentos do projeto.

```java
generator.save(dataDir + "setCodeText.jpg");
```

## Por que usar Aspose.BarCode para Java?

Aspose.BarCode para Java oferece um conjunto abrangente de recursos que simplificam a geração de códigos de barras em várias plataformas. Ele suporta mais de sessenta simbologias, fornece saídas raster e vetoriais de alta resolução e oferece otimizações de desempenho para processamento em lote, tornando‑o ideal para aplicações de nível empresarial e integração perfeita com projetos Java existentes.

- **Suporte amplo a simbologias** – Mais de **60** tipos de códigos de barras, incluindo Code128, QR, DataMatrix e PDF417.  
- **Renderização de alta resolução** – Gera imagens nítidas PNG, JPEG, SVG e PDF de até **2000 mm** de largura sem perda de qualidade.  
- **Foco em desempenho** – Processa um lote de 500 páginas de códigos de barras em menos de **2 segundos** em hardware de servidor padrão.  
- **Multiplataforma** – Totalmente compatível com Windows, Linux e macOS, e funciona com qualquer runtime Java 8+.

## Problemas Comuns e Soluções

| Problema | Solução |
|----------|---------|
| **Código de barras parece borrado** | Aumente a resolução da imagem ou exporte para um formato vetorial (SVG, PDF). |
| **Texto está truncado** | Aumente `XDimension` e `BarHeight` para dar à simbologia espaço suficiente. |
| **Licença não aplicada** | Coloque `Aspose.BarCode.lic` na raiz do projeto e carregue-a com `License license = new License(); license.setLicense("Aspose.BarCode.lic");`. |

## Perguntas Frequentes

**Q:** *Qual é a diferença entre `CODE_128` e outras variantes do Code128?*  
**A:** `CODE_128` seleciona automaticamente a codificação mais eficiente (A, B ou C) com base na entrada, proporcionando densidade e velocidade ótimas.

**Q:** *Posso mudar o formato de saída para PNG em vez de JPEG?*  
**A:** Sim—use `generator.save(dataDir + "setCodeText.png", com.aspose.barcode.BarcodeImageFormat.PNG);`.

**Q:** *É possível adicionar uma legenda legível por humanos abaixo do código de barras?*  
**A:** Absolutamente. Defina `generator.getParameters().getBarcode().getCaption().setTopMargin(5);` e estabeleça o texto da legenda via `setText`.

**Q:** *O Aspose.BarCode suporta caracteres Unicode?*  
**A:** Sim. Forneça texto codificado em UTF‑8 e assegure que a simbologia selecionada suporte o conjunto de caracteres.

**Q:** *Como posso gerar múltiplos códigos de barras em um loop?*  
**A:** Instancie um novo `BarcodeGenerator` dentro do loop, atribua um texto único para cada iteração e chame `save` com um nome de arquivo distinto.

---

**Última atualização:** 2026-06-09  
**Testado com:** Aspose.BarCode 24.12 for Java  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Criar código de barras Data Matrix e definir localização do texto do código em Java](/barcode/java/text-and-styling/setting-code-text-location/)
- [Como definir a cor do texto do código de barras em Java com Aspose.BarCode](/barcode/java/text-and-styling/setting-code-text-foreground-color/)
- [Gerar código de barras Java – Definir resolução da imagem com Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.barcode.generation.BarcodeGenerator;
```