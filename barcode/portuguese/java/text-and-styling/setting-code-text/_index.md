---
date: 2025-12-30
description: Aprenda como gerar códigos de barras em Java usando Aspose.BarCode. Este
  guia passo a passo mostra como definir texto personalizado para o código de barras,
  ajustar a largura e salvar a imagem.
linktitle: Setting Code Text
second_title: Aspose.BarCode Java API
title: 'Gerar Código de Barras em Java: Definir Texto do Código usando Aspose.BarCode'
url: /pt/java/text-and-styling/setting-code-text/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Gerar Código de Barras Java: Definir Texto do Código usando Aspose.BarCode

## Introdução

Neste tutorial, você aprenderá como **gerar barcode java** com a biblioteca Aspose.BarCode para Java. Seja construindo um sistema de inventário, uma solução de rastreamento de documentos ou qualquer aplicação que necessite de códigos de barras, este guia o conduzirá por cada passo — desde a criação de um código de barras **Code128** até a personalização do texto do código e ajuste da largura das barras. Ao final, você terá uma imagem pronta para uso que pode incorporar onde precisar.

## Respostas Rápidas
- **Qual biblioteca devo usar?** Aspose.BarCode for Java.
- **Qual tipo de código de barras é demonstrado?** CODE_128.
- **Como definir texto de código de barras personalizado?** Use o construtor `BarcodeGenerator` ou o método `setCodeText`.
- **Posso mudar a largura da barra?** Sim, via `XDimension` em milímetros.
- **Preciso de licença para produção?** Sim, é necessária uma licença comercial.

## Pré-requisitos

- Compreensão básica de programação Java.  
- Um ambiente de desenvolvimento Java funcional instalado.  
- Biblioteca Aspose.BarCode para Java. Você pode baixá‑la **[here](https://releases.aspose.com/barcode/java/)**.  
- Um editor de código, como IntelliJ IDEA ou Eclipse.  

## Importar Pacotes

Comece importando os pacotes necessários para o seu projeto Java. Esses pacotes são essenciais para trabalhar com Aspose.BarCode.

```java
import com.aspose.barcode.generation.BarcodeGenerator;
```

Agora, vamos explorar o processo de definição do texto do código usando Aspose.BarCode em Java. Siga estes passos:

## Tutorial do Gerador de Código de Barras: Criar um Código de Barras Code128

### Etapa 1: Criar uma Instância de `BarcodeGenerator`

```java
// The path to the documents directory.
String path = "Your Directory Path";
// The path to the resource directory.
String dataDir = "Your Document Directory";
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
```

Aqui, criamos uma instância de `BarcodeGenerator`, especificando a simbologia do código de barras (**CODE_128**) e o **texto de código de barras personalizado** `"12345678"`.

### Etapa 2: Ajustar a Largura do Código de Barras para Texto Personalizado

```java
generator.getParameters().getBarcode().getXDimension().setMillimeters(0.5f);
```

Ajuste a largura das barras conforme sua preferência. Neste exemplo, **ajustamos a largura do código de barras** para `0.5` mm, o que funciona bem para a maioria dos tamanhos de etiquetas.

### Etapa 3: Salvar a Imagem do Código de Barras

```java
generator.save(dataDir + "setCodeText.jpg");
```

Salve a imagem do código de barras gerado no diretório especificado. Neste caso, o arquivo é salvo como **`setCodeText.jpg`** dentro do seu diretório de documentos.

## Por que Usar Aspose.BarCode para Java?

- **API abrangente** – Suporta mais de 60 simbologias de código de barras, incluindo Code128, QR, DataMatrix e outras.  
- **Renderização de alta qualidade** – Gera imagens nítidas em formatos PNG, JPEG, SVG e PDF.  
- **Facilidade de personalização** – Altere texto, tamanho, cores e até adicione legendas legíveis com algumas linhas de código.  
- **Multiplataforma** – Funciona no Windows, Linux e macOS com qualquer runtime Java 8+.

## Problemas Comuns e Soluções

| Problema | Solução |
|----------|---------|
| **Barcode looks blurry** | Aumente a resolução da imagem ou exporte para formatos vetoriais (SVG, PDF). |
| **Text is truncated** | Certifique‑se de que o `XDimension` (largura da barra) e `BarHeight` sejam grandes o suficiente para a simbologia escolhida. |
| **License not applied** | Coloque seu arquivo de licença (`Aspose.BarCode.lic`) na raiz do projeto e carregue‑o com `License license = new License(); license.setLicense("Aspose.BarCode.lic");`. |

## Perguntas Frequentes (FAQs)

### Posso usar Aspose.BarCode para Java em projetos comerciais?
Sim, Aspose.BarCode para Java é um produto comercial. Você pode encontrar detalhes da licença **[here](https://purchase.aspose.com/buy)**.

### Existe uma versão de avaliação gratuita disponível?
Sim, você pode obter uma avaliação gratuita **[here](https://releases.aspose.com/)**.

### Onde posso encontrar a documentação do Aspose.BarCode para Java?
A documentação está disponível **[here](https://reference.aspose.com/barcode/java/)**.

### Como obtenho suporte para Aspose.BarCode para Java?
Visite o **[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)** para suporte.

### Posso usar uma licença temporária para fins de teste?
Sim, você pode obter uma licença temporária **[here](https://purchase.aspose.com/temporary-license/)**.

## Perguntas Frequentes Adicionais

**Q:** *Qual é a diferença entre `CODE_128` e outras variantes do Code128?*  
**A:** `CODE_128` é a simbologia padrão que seleciona automaticamente a codificação mais eficiente (A, B ou C) com base no texto de entrada.

**Q:** *Posso mudar o formato de saída para PNG em vez de JPEG?*  
**A:** Absolutamente. Use `generator.save(dataDir + "setCodeText.png", com.aspose.barcode.BarcodeImageFormat.PNG);`.

**Q:** *É possível adicionar uma legenda legível abaixo do código de barras?*  
**A:** Sim. Defina `generator.getParameters().getBarcode().getCaption().setTopMargin(5);` e especifique o texto da legenda.

**Q:** *O Aspose.BarCode suporta caracteres Unicode?*  
**A:** Sim. Forneça o texto em UTF‑8 e certifique‑se de que a simbologia escolhida suporte o conjunto de caracteres.

**Q:** *Como posso gerar múltiplos códigos de barras em um loop?*  
**A:** Instancie um novo `BarcodeGenerator` dentro do loop, defina o texto para cada iteração e chame `save` com um nome de arquivo único.

**Última atualização:** 2025-12-30  
**Testado com:** Aspose.BarCode 24.12 para Java  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}