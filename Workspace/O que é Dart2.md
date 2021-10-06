**[Desenvolvimento](https://www.treinaweb.com.br/blog/categoria/desenvolvimento)**

# O que é Dart?

Confira nesse artigo o que vem a ser o Dart, uma das linguagens de programação da Google.

 mais de 2 anos atrás

[Artigos](https://www.treinaweb.com.br/blog)O que é Dart?

Se você começou a estudar um pouco sobre o Flutter, provavelmente deve ter trabalhado um pouco com o Dart… Se você ainda não mexeu com [Flutter](https://www.treinaweb.com.br/blog/o-que-e-flutter/), deve ter ouvido falar um pouco sobre o Dart, já que várias grandes empresas, como o Nubank, estão começando a migrar suas aplicações para esta linguagem. Porém, o que afinal de contas é o Dart?

### O que vem a ser o Dart?

O Dart é uma linguagem de programação fortemente tipada inicialmente criada pela Google em 2011. A missão inicial do Dart era substituir o [JavaScript](https://www.treinaweb.com.br/blog/o-que-e-e-como-comecar-com-javascript/) para desenvolvimento de scripts em páginas web. Porém, com a evolução da linguagem e com o passar dos anos, ela hoje pode ser considerada uma linguagem multi-paradigma, embora a linguagem apresente fortes estruturas típicas de linguagens orientadas a objeto.

Hoje, sabemos que o Dart não obteve muito sucesso em sua missão inicial em substituir o JavaScript nos navegadores. Porém, o desenvolvimento e posterior sucesso do Flutter, que é fundamentado no Dart, fez com que a linguagem voltasse à tona, atraindo a atenção de muitos desenvolvedores.

O Dart possui algumas variantes no que diz respeito a seu ambiente de execução. O código Dart pode ser executado em uma máquina virtual (chamada DartVM, máquina virtual está inserida em um conjunto de ferramentas chamado Dart Native). Esta máquina virtual ainda pode ser executada em dois modos diferentes: **JIT** *(Just-in-Time Compiler)* e **AOT** *(Ahead-of-Time Compiler)*. De maneira mais simplista, a compilação JIT ocorre no momento da execução de um trecho de código, onde o código Dart é convertido para código de máquina à medida em que ele é executado.

Já na execução AOT, o código é convertido para código de máquina previamente. A outra maneira na qual podemos executar o código Dart é através de um processo de transpilação para JavaScript através da ferramenta dart2js, ferramenta esta também integrante do Dart SDK. Todos estes modos de execução tornam o Dart uma linguagem muito flexível e que pode ser executada tanto em ambientes nativos (como em aplicações mobile e desktop) como em ambientes web (como em uma aplicação web que utilize o Angular, por exemplo).



![Flutter - Fundamentos](https://d2knvm16wkt3ia.cloudfront.net/assets/svg-icon/flutter.svg)

##### CursoFlutter - Fundamentos

[Conhecer o curso](https://www.treinaweb.com.br/curso/flutter-fundamentos)



### A sintaxe do Dart

O Dart possui uma sintaxe com estilo baseado no C. Isso faz com que sua sintaxe seja muito similar à linguagens atualmente populares, como [Java](https://www.treinaweb.com.br/blog/o-que-e-e-como-comecar-com-java/) e [C#](https://www.treinaweb.com.br/blog/o-que-e-e-como-comecar-com-c-sharp/). Porém, o Dart tenta reduzir um pouco os ruídos característicos de linguagens baseadas no C.

Um simples *“Hello World”* em Dart poderia ser escrito da seguinte forma:

Copiar

```dart
main() {
  print('Hello World!');
}
```

Dart também possui algumas características de linguagens funcionais. Isso fica claro no exemplo abaixo, onde uma sequência de Fibonacci é gerada.

Copiar

```dart
int fib(int n) => (n > 2) ? (fib(n - 1) + fib(n - 2)) : 1;

void main() {
  print('fib(20) = ${fib(20)}');
}
```

### Críticas ao Dart

Um dos pontos que dificultaram a adoção do Dart no início foi o fato de que a Google foi acusada de fomentar a fragmentação das plataformas web. Para a maioria dos desenvolvedores e empresas, não fazia sentido trocar uma linguagem consolidada para a web como o JavaScript por uma linguagem nova como o Dart, por mais que a Google tivesse planos de incluir a DartVM de maneira nativa ao Google Chrome na época, já um dos browsers mais utilizados.

A fama que a Google tem por abandonar alguns produtores de maneira abrupta também fizeram com que os desenvolvedores olhassem com uma certa desconfiança para o Dart.

Porém, o sucesso do Flutter serviu para que desenvolvedores em geral começassem a pensar em dar uma chance para o Dart. Suas features desenvolvidas para lidar com uma maneira muito simples com aspectos complicados como concorrência e transições em interfaces serviram para mostrar os valores da linguagem.

Além disso, a Google já não tem mais os planos de fazer com que o Dart venha a substituir o JavaScript, já que este objetivo não foi alcançado no passado. Isso fez com que a Google adotasse o caminho de interoperabilidade entre o JavaScript e o Dart, fazendo com que o transpilador Dart para JavaScript fosse desenvolvido.



![Dart - Orientação a Objetos](https://d2knvm16wkt3ia.cloudfront.net/assets/svg-icon/dart.svg)

##### CursoDart - Orientação a Objetos

[Conhecer o curso](https://www.treinaweb.com.br/curso/dart-orientacao-a-objetos)



- [#dart](https://www.treinaweb.com.br/blog/tag/dart)
-  

- [#linguagem de programação](https://www.treinaweb.com.br/blog/tag/linguagem-de-programacao)
-  

- [#flutter](https://www.treinaweb.com.br/blog/tag/flutter)



#### Autor(a) do artigo

![Marylene Guedes]()

##### Marylene Guedes**[Desenvolvimento](https://www.treinaweb.com.br/blog/categoria/desenvolvimento)**

# O que é Dart?

Confira nesse artigo o que vem a ser o Dart, uma das linguagens de programação da Google.

 mais de 2 anos atrás

[Artigos](https://www.treinaweb.com.br/blog)O que é Dart?

Se você começou a estudar um pouco sobre o Flutter, provavelmente deve ter trabalhado um pouco com o Dart… Se você ainda não mexeu com [Flutter](https://www.treinaweb.com.br/blog/o-que-e-flutter/), deve ter ouvido falar um pouco sobre o Dart, já que várias grandes empresas, como o Nubank, estão começando a migrar suas aplicações para esta linguagem. Porém, o que afinal de contas é o Dart?

### O que vem a ser o Dart?

O Dart é uma linguagem de programação fortemente tipada inicialmente criada pela Google em 2011. A missão inicial do Dart era substituir o [JavaScript](https://www.treinaweb.com.br/blog/o-que-e-e-como-comecar-com-javascript/) para desenvolvimento de scripts em páginas web. Porém, com a evolução da linguagem e com o passar dos anos, ela hoje pode ser considerada uma linguagem multi-paradigma, embora a linguagem apresente fortes estruturas típicas de linguagens orientadas a objeto.

Hoje, sabemos que o Dart não obteve muito sucesso em sua missão inicial em substituir o JavaScript nos navegadores. Porém, o desenvolvimento e posterior sucesso do Flutter, que é fundamentado no Dart, fez com que a linguagem voltasse à tona, atraindo a atenção de muitos desenvolvedores.

O Dart possui algumas variantes no que diz respeito a seu ambiente de execução. O código Dart pode ser executado em uma máquina virtual (chamada DartVM, máquina virtual está inserida em um conjunto de ferramentas chamado Dart Native). Esta máquina virtual ainda pode ser executada em dois modos diferentes: **JIT** *(Just-in-Time Compiler)* e **AOT** *(Ahead-of-Time Compiler)*. De maneira mais simplista, a compilação JIT ocorre no momento da execução de um trecho de código, onde o código Dart é convertido para código de máquina à medida em que ele é executado.

Já na execução AOT, o código é convertido para código de máquina previamente. A outra maneira na qual podemos executar o código Dart é através de um processo de transpilação para JavaScript através da ferramenta dart2js, ferramenta esta também integrante do Dart SDK. Todos estes modos de execução tornam o Dart uma linguagem muito flexível e que pode ser executada tanto em ambientes nativos (como em aplicações mobile e desktop) como em ambientes web (como em uma aplicação web que utilize o Angular, por exemplo).



![Flutter - Fundamentos](https://d2knvm16wkt3ia.cloudfront.net/assets/svg-icon/flutter.svg)

##### CursoFlutter - Fundamentos

[Conhecer o curso](https://www.treinaweb.com.br/curso/flutter-fundamentos)



### A sintaxe do Dart

O Dart possui uma sintaxe com estilo baseado no C. Isso faz com que sua sintaxe seja muito similar à linguagens atualmente populares, como [Java](https://www.treinaweb.com.br/blog/o-que-e-e-como-comecar-com-java/) e [C#](https://www.treinaweb.com.br/blog/o-que-e-e-como-comecar-com-c-sharp/). Porém, o Dart tenta reduzir um pouco os ruídos característicos de linguagens baseadas no C.

Um simples *“Hello World”* em Dart poderia ser escrito da seguinte forma:

Copiar

```dart
main() {
  print('Hello World!');
}
```

Dart também possui algumas características de linguagens funcionais. Isso fica claro no exemplo abaixo, onde uma sequência de Fibonacci é gerada.

Copiar

```dart
int fib(int n) => (n > 2) ? (fib(n - 1) + fib(n - 2)) : 1;

void main() {
  print('fib(20) = ${fib(20)}');
}
```

### Críticas ao Dart

Um dos pontos que dificultaram a adoção do Dart no início foi o fato de que a Google foi acusada de fomentar a fragmentação das plataformas web. Para a maioria dos desenvolvedores e empresas, não fazia sentido trocar uma linguagem consolidada para a web como o JavaScript por uma linguagem nova como o Dart, por mais que a Google tivesse planos de incluir a DartVM de maneira nativa ao Google Chrome na época, já um dos browsers mais utilizados.

A fama que a Google tem por abandonar alguns produtores de maneira abrupta também fizeram com que os desenvolvedores olhassem com uma certa desconfiança para o Dart.

Porém, o sucesso do Flutter serviu para que desenvolvedores em geral começassem a pensar em dar uma chance para o Dart. Suas features desenvolvidas para lidar com uma maneira muito simples com aspectos complicados como concorrência e transições em interfaces serviram para mostrar os valores da linguagem.

Além disso, a Google já não tem mais os planos de fazer com que o Dart venha a substituir o JavaScript, já que este objetivo não foi alcançado no passado. Isso fez com que a Google adotasse o caminho de interoperabilidade entre o JavaScript e o Dart, fazendo com que o transpilador Dart para JavaScript fosse desenvolvido.



![Dart - Orientação a Objetos](https://d2knvm16wkt3ia.cloudfront.net/assets/svg-icon/dart.svg)

##### CursoDart - Orientação a Objetos

[Conhecer o curso](https://www.treinaweb.com.br/curso/dart-orientacao-a-objetos)



- [#dart](https://www.treinaweb.com.br/blog/tag/dart)
-  

- [#linguagem de programação](https://www.treinaweb.com.br/blog/tag/linguagem-de-programacao)
-  

- [#flutter](https://www.treinaweb.com.br/blog/tag/flutter)



#### Autor(a) do artigo

![Marylene Guedes]()

##### Marylene Guedes**[Desenvolvimento](https://www.treinaweb.com.br/blog/categoria/desenvolvimento)**

# O que é Dart?

Confira nesse artigo o que vem a ser o Dart, uma das linguagens de programação da Google.

 mais de 2 anos atrás

[Artigos](https://www.treinaweb.com.br/blog)O que é Dart?

Se você começou a estudar um pouco sobre o Flutter, provavelmente deve ter trabalhado um pouco com o Dart… Se você ainda não mexeu com [Flutter](https://www.treinaweb.com.br/blog/o-que-e-flutter/), deve ter ouvido falar um pouco sobre o Dart, já que várias grandes empresas, como o Nubank, estão começando a migrar suas aplicações para esta linguagem. Porém, o que afinal de contas é o Dart?

### O que vem a ser o Dart?

O Dart é uma linguagem de programação fortemente tipada inicialmente criada pela Google em 2011. A missão inicial do Dart era substituir o [JavaScript](https://www.treinaweb.com.br/blog/o-que-e-e-como-comecar-com-javascript/) para desenvolvimento de scripts em páginas web. Porém, com a evolução da linguagem e com o passar dos anos, ela hoje pode ser considerada uma linguagem multi-paradigma, embora a linguagem apresente fortes estruturas típicas de linguagens orientadas a objeto.

Hoje, sabemos que o Dart não obteve muito sucesso em sua missão inicial em substituir o JavaScript nos navegadores. Porém, o desenvolvimento e posterior sucesso do Flutter, que é fundamentado no Dart, fez com que a linguagem voltasse à tona, atraindo a atenção de muitos desenvolvedores.

O Dart possui algumas variantes no que diz respeito a seu ambiente de execução. O código Dart pode ser executado em uma máquina virtual (chamada DartVM, máquina virtual está inserida em um conjunto de ferramentas chamado Dart Native). Esta máquina virtual ainda pode ser executada em dois modos diferentes: **JIT** *(Just-in-Time Compiler)* e **AOT** *(Ahead-of-Time Compiler)*. De maneira mais simplista, a compilação JIT ocorre no momento da execução de um trecho de código, onde o código Dart é convertido para código de máquina à medida em que ele é executado.

Já na execução AOT, o código é convertido para código de máquina previamente. A outra maneira na qual podemos executar o código Dart é através de um processo de transpilação para JavaScript através da ferramenta dart2js, ferramenta esta também integrante do Dart SDK. Todos estes modos de execução tornam o Dart uma linguagem muito flexível e que pode ser executada tanto em ambientes nativos (como em aplicações mobile e desktop) como em ambientes web (como em uma aplicação web que utilize o Angular, por exemplo).



![Flutter - Fundamentos](https://d2knvm16wkt3ia.cloudfront.net/assets/svg-icon/flutter.svg)

##### CursoFlutter - Fundamentos

[Conhecer o curso](https://www.treinaweb.com.br/curso/flutter-fundamentos)



### A sintaxe do Dart

O Dart possui uma sintaxe com estilo baseado no C. Isso faz com que sua sintaxe seja muito similar à linguagens atualmente populares, como [Java](https://www.treinaweb.com.br/blog/o-que-e-e-como-comecar-com-java/) e [C#](https://www.treinaweb.com.br/blog/o-que-e-e-como-comecar-com-c-sharp/). Porém, o Dart tenta reduzir um pouco os ruídos característicos de linguagens baseadas no C.

Um simples *“Hello World”* em Dart poderia ser escrito da seguinte forma:

Copiar

```dart
main() {
  print('Hello World!');
}
```

Dart também possui algumas características de linguagens funcionais. Isso fica claro no exemplo abaixo, onde uma sequência de Fibonacci é gerada.

Copiar

```dart
int fib(int n) => (n > 2) ? (fib(n - 1) + fib(n - 2)) : 1;

void main() {
  print('fib(20) = ${fib(20)}');
}
```

### Críticas ao Dart

Um dos pontos que dificultaram a adoção do Dart no início foi o fato de que a Google foi acusada de fomentar a fragmentação das plataformas web. Para a maioria dos desenvolvedores e empresas, não fazia sentido trocar uma linguagem consolidada para a web como o JavaScript por uma linguagem nova como o Dart, por mais que a Google tivesse planos de incluir a DartVM de maneira nativa ao Google Chrome na época, já um dos browsers mais utilizados.

A fama que a Google tem por abandonar alguns produtores de maneira abrupta também fizeram com que os desenvolvedores olhassem com uma certa desconfiança para o Dart.

Porém, o sucesso do Flutter serviu para que desenvolvedores em geral começassem a pensar em dar uma chance para o Dart. Suas features desenvolvidas para lidar com uma maneira muito simples com aspectos complicados como concorrência e transições em interfaces serviram para mostrar os valores da linguagem.

Além disso, a Google já não tem mais os planos de fazer com que o Dart venha a substituir o JavaScript, já que este objetivo não foi alcançado no passado. Isso fez com que a Google adotasse o caminho de interoperabilidade entre o JavaScript e o Dart, fazendo com que o transpilador Dart para JavaScript fosse desenvolvido.



![Dart - Orientação a Objetos](https://d2knvm16wkt3ia.cloudfront.net/assets/svg-icon/dart.svg)

##### CursoDart - Orientação a Objetos

[Conhecer o curso](https://www.treinaweb.com.br/curso/dart-orientacao-a-objetos)



- [#dart](https://www.treinaweb.com.br/blog/tag/dart)
-  

- [#linguagem de programação](https://www.treinaweb.com.br/blog/tag/linguagem-de-programacao)
-  

- [#flutter](https://www.treinaweb.com.br/blog/tag/flutter)



#### Autor(a) do artigo

![Marylene Guedes]()

##### Marylene Guedes