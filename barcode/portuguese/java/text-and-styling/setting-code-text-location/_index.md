---
date: 2025-12-27
description: Aprenda a criar códigos de barras Data Matrix e como definir a localização
  do texto do código de barras em Java usando Aspose.BarCode. Siga nosso guia passo
  a passo para personalização completa.
linktitle: Setting Code Text Location
second_title: Aspose.BarCode Java API
title: Criar código de barras Data Matrix e definir a localização do texto do código
  em Java
url: /pt/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar código de barras Data Matrix e definir a localização do texto do código em Java

## Introdução

Gerar códigos de barras é uma necessidade rotineira para inventário, envio e muitas outras aplicações baseadas em Java. Com **Aspose.BarCode for Java** você pode **criar código de barras Data Matrix** rapidamente e controlar todos os aspectos visuais, incluindo onde o texto legível por humanos aparece. Neste tutorial, percorreremos os passos exatos para **criar código de barras Data Matrix** e demonstraremos **como definir o texto do código de barras** acima do símbolo para que corresponda às especificações de design.

## Respostas Rápidas
- **Qual biblioteca é usada?** Aspose.BarCode for Java  
- **Qual tipo de código de barras é demonstrado?** Data Matrix  
- **Como posicionar o texto do código?** Usando `CodeLocation.ABOVE`  
- **É necessário uma licença para produção?** Sim, é necessária uma licença comercial  
- **O código pode ser executado em Java 8+?** Absolutamente, ele suporta Java 8 e versões posteriores  

## O que é um código de barras Data Matrix?

Um código de barras Data Matrix é um símbolo bidimensional (2‑D) que armazena grandes quantidades de dados em um padrão quadrado ou retangular compacto. É amplamente usado para marcar itens pequenos, eletrônicos e dispositivos médicos porque pode codificar até 2.335 caracteres alfanuméricos.

## Por que definir a localização do texto do código de barras?

Colocar o texto legível por humanos **acima**, **abaixo** ou **ao lado** do código de barras ajuda os usuários a verificar rapidamente os dados codificados sem precisar escanear. Ajustar a localização do texto melhora a consistência da interface do usuário e atende às diretrizes de branding.

## Pré-requisitos

- Conhecimento básico de programação Java.  
- Java Development Kit (JDK) instalado.  
- Uma IDE como Eclipse ou IntelliJ IDEA.  
- Biblioteca Aspose.BarCode for Java (faça o download [aqui](https://releases.aspose.com/barcode/java/)).  

## Importar Pacotes

Primeiro, importe as classes essenciais do Aspose.BarCode para o seu projeto:

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Guia passo a passo

### Etapa 1: Definir caminhos de diretório

Especifique onde você deseja ler/gravar arquivos. Substitua os marcadores pelos caminhos reais em sua máquina.

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

### Etapa 3: Como definir a localização do texto do código de barras

Use a enumeração `CodeLocation` para mover o texto legível por humanos. Neste exemplo, posicionamos o texto **acima** do código de barras.

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

### Etapa 4: Salvar a imagem do código de barras gerado

Finalmente, grave a imagem do código de barras no disco. O arquivo conterá o símbolo Data Matrix com o texto posicionado acima dele.

```java
generator.save(dataDir + "codetextAbove.png");
```

## Problemas Comuns e Soluções
- **Texto não aparece:** Certifique-se de que está usando uma versão do Aspose.BarCode que suporte `CodeLocation`.  
- **Erros no caminho do arquivo:** Verifique se `dataDir` termina com um separador de arquivos (`/` ou `\\`) apropriado para o seu SO.  
- **Caracteres não suportados:** Data Matrix pode codificar apenas um conjunto limitado de caracteres; evite símbolos especiais que não estejam no padrão ISO/IEC 16022.  

## Perguntas Frequentes (FAQs)

### Q: Posso personalizar a aparência do código de barras gerado?
A: Sim, Aspose.BarCode oferece opções extensas de personalização, permitindo controlar cores, margens e estilos de fonte.

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

Agora você aprendeu como **criar código de barras Data Matrix** em Java e controlar precisamente **como definir a localização do texto do código de barras** usando Aspose.BarCode. Experimente outros valores de `CodeLocation` e opções de estilo para atender aos requisitos de design da sua aplicação.

---

**Última atualização:** 2025-12-27  
**Testado com:** Aspose.BarCode for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}