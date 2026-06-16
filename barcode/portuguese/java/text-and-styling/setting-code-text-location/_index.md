---
date: 2026-05-04
description: Aprenda a criar um código de barras Data Matrix usando uma biblioteca
  de códigos de barras Java e definir a localização do texto do código de barras acima
  do símbolo com Aspose.BarCode. Siga nosso exemplo passo a passo de geração de código
  de barras.
keywords:
- java barcode library
- barcode generation example
- barcode text above
- customize barcode text
linktitle: Configuração da localização do texto do código
second_title: Aspose.BarCode Java API
title: Criar código de barras Data Matrix com a biblioteca Java Barcode e definir
  a localização do texto do código
url: /pt/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar código de barras Data Matrix com Biblioteca de Código de Barras Java e Definir a Localização do Texto do Código

## Introdução

Se você está construindo um sistema de inventário, envio ou rastreamento em Java, descobrirá rapidamente que uma **java barcode library** confiável é essencial. Com **Aspose.BarCode for Java** você pode gerar um **Data Matrix barcode** em apenas algumas linhas de código e controlar totalmente o layout visual, incluindo onde o texto legível por humanos aparece. Neste tutorial, percorreremos um **barcode generation example** completo, mostraremos como **customize barcode text** a posição e explicaremos por que posicionar o texto acima do símbolo pode melhorar a usabilidade.

## Respostas Rápidas
- **Qual biblioteca é usada?** Aspose.BarCode for Java  
- **Qual tipo de código de barras é demonstrado?** Data Matrix  
- **Como posicionar o texto do código?** Using `CodeLocation.ABOVE` (you can also use `BELOW`)  
- **É necessário uma licença para produção?** Yes, a commercial license is required  
- **O código pode ser executado em Java 8+?** Absolutely, it supports Java 8 and later  

## O que é uma biblioteca de código de barras Java?

Uma **java barcode library** fornece aos desenvolvedores APIs prontas para criar, ler e estilizar códigos de barras 1‑D e 2‑D diretamente de aplicações Java. Ela abstrai as regras complexas de codificação e permite que você se concentre na lógica de negócios em vez do processamento de imagem de baixo nível.

## Por que usar uma biblioteca de código de barras Java para exemplo de geração de código de barras?

- **Velocidade:** Generate high‑quality barcodes in milliseconds.  
- **Confiabilidade:** Built‑in compliance with ISO/IEC standards.  
- **Flexibilidade:** Full control over size, color, margins, and **barcode text** placement.  
- **Multiplataforma:** Works on any JVM‑based environment, from desktop apps to cloud services.

## O que é um código de barras Data Matrix?

Um código de barras Data Matrix é um símbolo bidimensional (2‑D) que armazena grandes quantidades de dados em um padrão quadrado ou retangular compacto. É amplamente usado para marcar itens pequenos, eletrônicos e dispositivos médicos porque pode codificar até 2.335 caracteres alfanuméricos.

## Por que definir a localização do texto do código de barras?

Colocar o texto legível por humanos **acima**, **abaixo** ou **ao lado** do código de barras ajuda os usuários a verificar rapidamente os dados codificados sem escanear. Ajustar a localização do texto melhora a consistência da UI, atende às diretrizes de marca e pode reduzir erros na entrada manual de dados.

## Pré-requisitos

- Conhecimento básico de programação Java.  
- Java Development Kit (JDK) instalado.  
- Uma IDE como Eclipse ou IntelliJ IDEA.  
- Aspose.BarCode for Java library (download it from [here](https://releases.aspose.com/barcode/java/)).  

## Importar Pacotes

Primeiro, importe as classes essenciais do Aspose.BarCode para o seu projeto:

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

Essas importações dão acesso ao gerador de códigos de barras e à enumeração que controla a posição do texto.

## Guia passo a passo

### Etapa 1: Definir caminhos de diretório
Especifique onde você deseja ler/gravar arquivos. Substitua os marcadores de posição pelos caminhos reais em sua máquina.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### Etapa 2: Criar uma instância de BarcodeGenerator
Instancie `BarcodeGenerator` com o tipo **Data Matrix** e forneça o texto do código que deseja codificar.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### Etapa 3: Definir a localização do texto do código de barras (personalizar texto do código de barras)
Use a enumeração `CodeLocation` para mover o texto legível por humanos. Neste exemplo, posicionamos **acima** do código de barras.

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

> **Dica profissional:** Para posicionar o texto **abaixo** do símbolo, basta mudar `CodeLocation.ABOVE` para `CodeLocation.BELOW`.

### Etapa 4: Salvar a imagem do código de barras gerado
Finalmente, grave a imagem do código de barras no disco. O arquivo conterá o símbolo Data Matrix com o texto posicionado acima dele.

```java
generator.save(dataDir + "codetextAbove.png");
```

## Problemas comuns e soluções
- **Texto não aparece:** Ensure you are using a version of Aspose.BarCode that supports `CodeLocation`.  
- **Erros de caminho de arquivo:** Verify that `dataDir` ends with a file separator (`/` or `\\`) appropriate for your OS.  
- **Caracteres não suportados:** Data Matrix can encode only a limited set of characters; avoid special symbols not in the ISO/IEC 16022 standard.  

## Perguntas Frequentes (FAQs)

### Q: Posso personalizar a aparência do código de barras gerado?
A: Sim, o Aspose.BarCode oferece amplas opções de personalização, permitindo controlar cores, margens e estilos de fonte.

### Q: O Aspose.BarCode é compatível com Java 8 e versões posteriores?
A: Absolutamente, a biblioteca funciona com Java 8 e todas as versões subsequentes.

### Q: Como posso integrar o Aspose.BarCode ao meu projeto Java existente?
A: Adicione os arquivos JAR do Aspose.BarCode ao classpath do seu projeto, importe os pacotes necessários e você estará pronto para gerar códigos de barras.

### Q: Existe uma versão de avaliação disponível para o Aspose.BarCode?
A: Sim, você pode explorar os recursos do Aspose.BarCode obtendo uma avaliação gratuita [aqui](https://releases.aspose.com/).

### Q: Onde posso buscar ajuda ou suporte para o Aspose.BarCode?
A: Visite o [fórum Aspose.BarCode](https://forum.aspose.com/c/barcode/13) para assistência da comunidade e suporte oficial.

## Perguntas Frequentes Adicionais

**Q: Posso gerar um código de barras com o texto posicionado abaixo do símbolo?**  
A: Sim, defina `CodeLocation.BELOW` no mesmo método `setLocation`.

**Q: A biblioteca suporta outros códigos de barras 2‑D como QR Code?**  
A: Absolutamente, basta mudar `EncodeTypes.DATA_MATRIX` para `EncodeTypes.QR`.

**Q: Como altero o tamanho da fonte do texto do código de barras?**  
A: Use `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)`.

## Conclusão

Agora você aprendeu como **criar um código de barras Data Matrix** em Java usando uma **java barcode library** e controlar precisamente **como definir a localização do texto do código de barras** com o Aspose.BarCode. Experimente outros valores de `CodeLocation`, configurações de fonte e opções de cor para atender aos requisitos de design da sua aplicação.

---

**Última atualização:** 2026-05-04  
**Testado com:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}