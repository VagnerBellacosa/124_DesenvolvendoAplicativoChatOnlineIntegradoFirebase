# Swift: conheça a linguagem de programação do iOS

- [Mobile](https://www.zup.com.br/categorias/mobile) -  13 jul 2021

#### Neste artigo você vai ver:

- [Origem e lançamento do Swift](https://www.zup.com.br/blog/swift-linguagem-de-programacao-ios#texto-blog)
  - [O Swift se torna open source](https://www.zup.com.br/blog/swift-linguagem-de-programacao-ios#texto-blog)
- [Beleza, mas e o Objective-C?](https://www.zup.com.br/blog/swift-linguagem-de-programacao-ios#texto-blog)
- [Hmm, me fala mais desse Swift aí](https://www.zup.com.br/blog/swift-linguagem-de-programacao-ios#texto-blog)
  - [Convenceu! Mas eu não tenho um Mac ![🙁](https://s.w.org/images/core/emoji/13.1.0/svg/1f641.svg)](https://www.zup.com.br/blog/swift-linguagem-de-programacao-ios#texto-blog)
- [Concluindo…](https://www.zup.com.br/blog/swift-linguagem-de-programacao-ios#texto-blog)

A grande maioria de vocês, que estão lendo este artigo agora, provavelmente já tiveram contato com algum dispositivo fabricado pela Apple, seja um iPhone, Mac, iPad, ou outros. Caso eu esteja certo, é relativamente seguro afirmar que você já utilizou algum artefato de **software desenvolvido em Swift**, muito provavelmente um App.

Neste artigo vamos entender melhor **como funciona o Swift**, seu relacionamento com o Objective-C e como começar a aprender uma das **linguagens de programação oficiais do iOS**.

## **Origem e lançamento do Swift**

A linguagem Swift se tornou uma das linguagens oficiais para desenvolvimento nas plataformas iOS em **2014**, quando foi lançada pela Apple em sua conferência anual, a WWDC (*Apple Worldwide Developers Conference*).

Logo após o seu lançamento, o Swift foi adotado em massa pela comunidade de desenvolvedores para dispositivos iOS, e essa contribuição e adoção contribuíram muito para o rápido desenvolvimento desta linguagem de programação, com novas versões sendo lançadas aproximadamente a cada cinco ou seis meses. 

De fato, a recepção da linguagem pela comunidade foi tão positiva, que o Swift rapidamente **se tornou uma das 10 linguagens de programação mais populares do mundo**, apenas três anos após seu lançamento oficial, segundo o [TIOBE Index](https://www.tiobe.com/) e a [RedMonk](https://redmonk.com/). 

![Logomarca da linguagem de programação Swift. Um quadrado com bordas arredondadas, de cor laranja, contendo um pássaro branco de asas abertas em posição rasante. Ao lado, a palavra "Swift" escrita em letras grandes na cor preta.](https://secureservercdn.net/198.71.233.31/36q.76e.myftpupload.com/wp-content/uploads/2021/07/logo-Swift.png)

### **O Swift se torna open source**

Em **2015**, com o lançamento da versão 2.2 da linguagem, a Apple anunciou que estaria disponibilizando o c**ódigo fonte do Swift como um projeto open source**, sob a licença Apache 2.0. 

A abertura do código fonte possibilitou a utilização da linguagem em outras esferas do desenvolvimento, principalmente para aplicações Web, com o surgimento de frameworks que apoiavam o desenvolvimento para essa plataforma em Swift, como o Vapor, Perfect e o Kitura, de propriedade da IBM.

## **Beleza, mas e o Objective-C?**

Sim, você deve ter se perguntado: mas e o que aconteceu com o Objective-C, a linguagem oficial do desenvolvimento iOS antes do Swift? A resposta é simples: continua lá, firme e forte. 

O **Objective-C é uma linguagem bastante madura e estável**, e o Swift foi desde o princípio desenhado para ser compatível com ela. Ambos são compatíveis com a Cocoa API e o [Cocoa Touch Framework](https://www.zup.com.br/blog/cocoa-touch-framework-ios), utilizados no desenvolvimento de aplicações para iDevices e Macs. 

Além disso, ambos são compatíveis com a arquitetura LLVM de compiladores, o que torna possível a reutilização de várias *build tool*s de um pra outro. 

Em outras palavras, se você (ainda) usa Objective-C no seu projeto e quer testar o Swift, pode ir sem medo de ser feliz!

## **Hmm, me fala mais desse Swift aí**

Vamos falar de termos técnicos? O Swift é uma linguagem de programação de tipagem **forte**, **estática** e **inferida**. Isso significa que os valores atribuídos a variáveis no Swift, **precisam** ser do mesmo tipo da variável declarada (tipagem forte), que o tipo de uma variável é checado e definido em tempo de compilação (tipagem estática), e que os tipos de variáveis podem ser inferidos pelo compilador através dos valores passados na inicialização (tipagem inferida). 

Outra coisa interessante sobre os tipos de variável no Swift é que eles podem ser **opcionais**. Isso é uma funcionalidade da linguagem que foi pensada de modo a fazer com que houvesse mais segurança ao desenvolver, reduzindo o risco de comportamentos incertos causados pela ausência de valores esperados em certas partes do programa (estou falando de você, JavaScript).

Ainda falando de segurança, pra ter certeza de que seu código é uma fortaleza de tão seguro, o Swift ainda checa se suas variáveis foram inicializadas antes do uso, força a inicialização de objetos pra que eles nunca sejam nulos, verifica a ocorrência de overflow em arrays e inteiros, e gerencia automaticamente a alocação de memória pra você. 

Pra fechar com chave de ouro no quesito segurança, definir constantes é super simples, com a keyword ***let\***, e definir variáveis mais ainda, com a keyword ***var\***.

E se você já estava gostando do Swift, imagina agora que sabe que ele também tem isso aqui:

- Closures unificadas com ponteiros de função;
- Tipos genéricos;
- Tuplas;
- *Super structs*, que suportam a definição de métodos, extensões e implementação de protocolos;
- Controle de fluxo e ainda mais segurança com as keywords *guard*, *defer* e *repeat*.

Além disso, a **linguagem Swift também é multiparadigmas**, suportando o desenvolvimento nos paradigmas orientado a objetos, imperativo, concorrente e funcional. 

E aí, te convenci a dar uma chance pro Swift? 

### **Convenceu! Mas eu não tenho um Mac ![🙁](https://s.w.org/images/core/emoji/13.1.0/svg/1f641.svg)**

Agora vem uma notícia bem legal, então: **você não precisa de um Mac pra aprender a programar ou desenvolver soluções usando Swift**. 

A grande maioria dos editores de texto agnósticos (por exemplo, Atom, VSCode, Sublime etc) já tem suporte ao Swift. 

Além disso, você pode compilar o código escrito em Swift no seu Linux, graças à disponibilização da linguagem como open source! E se você usa Windows, também pode, graças à compatibilidade do Swift com a linguagem C, e à extensa coleção de bibliotecas C já presentes no sistema que o Swift também suporta. 

Agora não tem mais desculpa, né?

## **Concluindo…**

**O Swift é uma linguagem muito segura**, de sintaxe limpa, muito acessível e fácil de aprender, quer você esteja começando aprender a programar, quer você seja um veterano com anos de experiência em outras linguagens. 

É também uma via de acesso ao mundo do desenvolvimento iOS, através do Xcode e do Cocoa Touch Framework, então se esse é o seu objetivo, aprender Swift é um ótimo começo!

Se você ficou curioso e quer saber mais sobre o Swift e os rumos que a linguagem está tomando, um ótimo lugar pra continuar sua jornada é visitando o [portal oficial da linguagem](https://swift.org/), contendo a documentação oficial, as core libraries e o fórum da comunidade de devs.

Inclusive, temos [muitas vagas para pessoas desenvolvedoras iOS](https://boards.greenhouse.io/zupinnovation/jobs/4383438003) na Zup ![😉](https://s.w.org/images/core/emoji/13.1.0/svg/1f609.svg).

Por hoje é só, espero que tenham gostado! Conta pra gente nos comentários o que você pensa do Swift.

![Capa do artigo sobre linguagem de programação Swif com aparelhos que rodam do sistema operacional iOS, como iPhone e iPad.](https://secureservercdn.net/198.71.233.31/36q.76e.myftpupload.com/wp-content/uploads/2021/07/linguagem-de-programacao-Swif-1024x683.jpg)

[![André Felipe Fleck Bedran](https://secureservercdn.net/198.71.233.31/36q.76e.myftpupload.com/wp-content/uploads/2021/07/Foto-Andre-Felipe-Fleck-Bedran-150x150.png)](https://www.zup.com.br/autores/andre-felipe-fleck-bedran)

[André Felipe Fleck Bedran](https://www.zup.com.br/autores/andre-felipe-fleck-bedran)

[Linkedin](https://www.linkedin.com/in/andrebedran/)

iOS Developer

Dev iOS paraense, com um coração meio candango. Ama café, música e D&D, e nas horas vagas tenta (sem sucesso) fazer com que seus dois gatos parem de brigar entre si.

#### Artigos relacionados

[![Capa do artigo "Aprendizado de máquina para reduzir consumo de energia em smartphones" que mostra uma mulher branca de cabelos longos com um smartphone nas mãos onde é possível ver que ele está com a bateria acabando.](https://secureservercdn.net/198.71.233.31/36q.76e.myftpupload.com/wp-content/uploads/2021/09/Aprendizado-de-maquina-para-reduzir-consumo-de-energia-em-smartphones-768x512.jpeg)](https://www.zup.com.br/blog/aprendizado-de-maquina-reduzir-consumo-de-energia-em-smartphones)

[Desenvolvimento](https://www.zup.com.br/categorias/desenvolvimento)

#### [Aprendizado de máquina para reduzir consumo de energia em smartphones](https://www.zup.com.br/blog/aprendizado-de-maquina-reduzir-consumo-de-energia-em-smartphones)

Postado em:28/09/2021•

 

[![Capa do artigo "Flexbox o que é e como usá-lo para ter aplicações mobile responsivas" com 9 caixas coloridas perfeitamente alinhadas](https://secureservercdn.net/198.71.233.31/36q.76e.myftpupload.com/wp-content/uploads/2021/09/Flexbox-o-que-e-e-como-usa-lo-para-ter-aplicacoes-mobile-responsivas-768x570.jpg)](https://www.zup.com.br/blog/flexbox-beagle)

[Mobile](https://www.zup.com.br/categorias/mobile)

#### [Flexbox: o que é e como usá-lo para ter aplicações mobile responsivas](https://www.zup.com.br/blog/flexbox-beagle)

Postado em:02/09/2021•

 

[![Capa do artigo Interoperabilidade entre Swift e Objective-C com vários teclados da Apple](https://secureservercdn.net/198.71.233.31/36q.76e.myftpupload.com/wp-content/uploads/2021/08/Interoperabilidade-entre-Swift-e-Objective-C-768x513.jpg)](https://www.zup.com.br/blog/interoperabilidade-swift-objective-c)

[Mobile](https://www.zup.com.br/categorias/mobile)

#### [Interoperabilidade entre Swift e Objective-C](https://www.zup.com.br/blog/interoperabilidade-swift-objective-c)

Postado em:19/08/2021•