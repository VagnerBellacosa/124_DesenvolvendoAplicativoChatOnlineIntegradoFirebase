# Primeiros passos com a Google Dart

## Veja neste artigo uma abordagem abrangente sobre a nova linguagem de scripts do Google: a Dart. A linguagem permite ao desenvolvedor criar código que roda tanto no cliente quanto no servidor.

A maioria das arquiteturas atuais faz uso de plataformas e linguagens diferentes em ambos os lados cliente e servidor, o que muitas vezes leva a código duplicado e complexidade aumentada, isso sem falar dos custos de manutenção e declínio da produtividade da equipe.

Ver mais

Suporte ao alunoAnotarMarcar como concluídoCódigo fonte

[Artigos](https://www.devmedia.com.br/artigos/)[Dart](https://www.devmedia.com.br/artigos/dart)Primeiros passos com a Google Dart

Foi pensando nisso que o Google criou a **linguagem de programação Dart**, com o intuito de facilitar a forma como integramos a aplicação como um todo.

Neste artigo veremos os principais tópicos acerca dessa linguagem: como ela lida com a [Orientação a Objetos](https://www.devmedia.com.br/principais-conceitos-da-programacao-orientada-a-objetos/32285), sintaxe, responsividade, manipulação de erros, classes, interfaces, dentre outros.

------

##### Guia do artigo:

- [Configuração do ambiente](https://www.devmedia.com.br/primeiros-passos-com-a-google-dart/32954#ambiente)
- [Principais características](https://www.devmedia.com.br/primeiros-passos-com-a-google-dart/32954#Principais)
- [Modularidade e Namespace](https://www.devmedia.com.br/primeiros-passos-com-a-google-dart/32954#Modularidade)
- [Funções e Closures](https://www.devmedia.com.br/primeiros-passos-com-a-google-dart/32954#Closures)
- [Classes](https://www.devmedia.com.br/primeiros-passos-com-a-google-dart/32954#Classes)
- [Mixins](https://www.devmedia.com.br/primeiros-passos-com-a-google-dart/32954#Mixins)
- [Coleções e Genéricos](https://www.devmedia.com.br/primeiros-passos-com-a-google-dart/32954#Genéricos)
- [Erros e Exceções](https://www.devmedia.com.br/primeiros-passos-com-a-google-dart/32954#Erros)
- [Referências](https://www.devmedia.com.br/primeiros-passos-com-a-google-dart/32954#Referências)

------

No fim, o leitor estará apto a introduzir a linguagem nos seus projetos sem se preocupar em perder o poder que tinha antes ao usar [JavaScript](https://www.devmedia.com.br/guia/javascript/34372) e [Node.js](https://www.devmedia.com.br/nodejs/), uma vez que ela gera a conversão para essas e muitas outras tecnologias.

Em meados de 2007 o Google inaugurou a sua primeira linguagem de programação, a [linguagem Go](https://www.devmedia.com.br/primeiros-passos-com-a-linguagem-google-go/34344) ou *golang*, iniciando um ciclo de lançamentos futuros que desencadeariam em poderosas ferramentas como [Angular](https://www.devmedia.com.br/guia/angular/38245), GWT e App Engine. Inicialmente, as linguagens assumiam características estruturadas e estáticas, em detrimento da ampla adoção que a empresa fazia (e ainda faz) de linguagens como [C e C++](https://www.devmedia.com.br/historia-do-c-c/24029).

Mas com o tempo, a necessidade de abraçar os universos front-end, mobile e server side ao mesmo tempo fez com a empresa criasse uma nova linguagem: a Google Dart.

A Dart é uma linguagem desenhada orginalmente para a web, que foi concebida na conferência GOTO na Dinamarca em outubro de 2011, em um projeto fundado pelos desenvolvedores Lars Bark e Kasper Lund. Como toda linguagem client side, a Dart precisou passar por uma bateria de testes junto à *ECMA International* para verificar seu funcionamento em browsers modernos, tendo assim sua primeira especificação aprovada e liberada para a comunidade.

De acordo com o site do projeto “a Dart foi desenhada para facilmente escrever ferramentas de desenvolvimento para aplicações web modernas e capacitadas para ambientes de alta performance”. Dentre as principais características da linguagem, podemos citar:

- É baseada em compilação de código JavaScript;
- Baseada em classes;
- Orientada a objetos;
- Tem sintaxe baseada na linguagem C;
- Implementa heranças simples;
- E suporta os principais tópicos da OO: interfaces, classes abstratas, genéricos e tipos opcionais.

Neste artigo abordaremos os principais conceitos da nova linguagem, sua sintaxe, principais estruturas programáticas, suas bibliotecas e seu SDK, além da grande quantidade de pacotes públicos disponíveis para importação nos seus projetos (conceito semelhante ao de frameworks como Grunt e React).

### Configuração do ambiente

Para se trabalhar com a Dart a primeira coisa a se fazer é efetuar o download da linguagem, juntamente com o Dart Editor, a Dart SDK e o web browser Chrommium que traz consigo uma VM Dart pré-construída e disponibilizada gratuitamente.

Para isso, acesse o site oficial disponível na seção **Links** e clique no botão “*Get Started*”. Após isso, você será redirecionado para a página de definição da plataforma, conforme mostra a **Figura 1**.

![Página de download com opções selecionadas](https://arquivo.devmedia.com.br/REVISTAS/front_end/imagens/edicao7/3/1.png)**Figura 1.** Página de download com opções selecionadas.

Selecione o seu Sistema Operacional, depois clique na opção “*Editor + SDK*” para selecionar o instalador completo e no final os itens na seção “*Download Dart Editor*” irão aparecer para você identificar se o seu SO é 32 ou 64 bits.

Posicione o zip baixado na pasta onde você deseja criar os seus projetos Dart, e descompacte-o lá. Neste arquivo estará contido o executável do Dart Editor, basta executá-lo e você verá uma IDE semelhante à da **Figura 2** aparecer.

![Interface do Dart Editor]()**Figura 2.** Interface do Dart Editor.

Perceba como a interface é muito próxima da IDE Eclipse, isso porque o Google usou o núcleo do projeto Eclipse (que é free e open source) para construir uma nova ferramenta de desenvolvimento.

Esse tipo de estratégia é muito usado no mercado para construir IDEs como Spring IDE, MyEclipse e as ferramentas Rational da IBM. O pacote Dart SDK já vem selecionado e não deve ser removido da IDE para que a linguagem funcione corretamente.

------

##### Saiu na DevMedia!

- [Primeiros passos no Flutter](https://www.devmedia.com.br/flutter/):
  O Flutter é um framework construído pelo Google para facilitar o desenvolvimento multiplataforma. Nessa série veremos como iniciar nessa tecnologia que permite a criação de aplicativos tanto para Android quanto para iOS.

------

#### Saiba mais sobre Flutter ;)

- [Hello World com Flutter](https://www.devmedia.com.br/hello-world-com-flutter/40321):
  Confira neste artigo um passo a passo para a criação de um ambiente de desenvolvimento com o Flutter, o framework do Google para a construção de aplicativos nativos para as plataformas Android e iOS.

A Dart pode ser usada para criar aplicações que não estejam presas ao HTML, de fora do browser. Para isso, basta integrar o seu ambiente ao Node.js.

Porém, como a maioria das aplicações são feitas visando o JavaScript, trataremos de focar num exemplo inicial onde exibimos um menu de navegação no browser e o usuário poderá clicar no mesmo e ser redirecionado para duas telas: uma para inverter o texto num campo de input e outra com informações sobre o site.

Este exemplo nos permitirá entender como a linguagem lida com os eventos de páginas HTML.

A Dart possibilita que criemos várias sortes de aplicações (a maioria com tecnologia Google) como projetos:

- **Console Application:** aplicações de execução direta via terminal de comandos, através da geração de arquivos .bat ou equivalentes de cada SO;
- **App Engine Application:** aplicações focadas na Google App Engine, para execução na nuvem do Google;
- **Chrome App:** aplicações ou plugins para o navegador Google Chrome;
- **Dart Package:** para criar um componente modularizado da Dart;
- **Polymer Web Server:** para hospedar aplicações desenvolvidas com o framework JavaScript [Polymer.js](https://www.devmedia.com.br/web-components-com-polymer/31956);
- **Web Applications:** aplicações web simples, com suporte a JavaScript/bibliotecas, HTML e CSS.

Para isso, vá até o menu “*File > New Application*”. Preencha os campos “*Application name*” com o nome da aplicação e “*Parent directory*” com o diretório onde deseja salvá-la. Vamos dar o nome de **AloMundoDart**.

Mantenha a checkbox “*Generate sample content*” marcada para que a wizard de criação já nos traga uma estrutura pré-criada, e selecione a opção “*Web application*” na lista que aparecer logo abaixo. Clique em “*Finish*”. Isso irá gerar uma estrutura de projeto igual à da **Figura 3**.

![Estrutura de pastas do projeto recém-criado](https://arquivo.devmedia.com.br/REVISTAS/front_end/imagens/edicao7/3/3.png)**Figura 3.** Estrutura de pastas do projeto recém-criado.

A pasta lib conterá todos os arquivos de script da Dart, inclusive com dois gerados para o exemplo criado pela wizard. A pasta web guarda todo tipo de conteúdo relacionado ao front-end: imagens, CSS, arquivos HTML, favicons e outros arquivos .dart.

Antes de executar o projeto, façamos algumas alterações. Abra o arquivo nav_menu.dart e substitua seu conteúdo pelo representado na **Listagem 1**.

**Listagem 1**. Conteúdo do arquivo nav_menu.dart.

```
01 // Copyright (c) 2015, DevMedia. All rights reserved. Use of this source code
02 // is governed by a BSD-style license that can be found in the LICENSE file.
03
04 library nav_menu;
05
06 import 'dart:html';
07
08 initNavMenu() {
09   var navdrawerContainer = querySelector('.navdrawer-container');
10   var appbarElement = querySelector('.app-bar');
11   var menuBtn = querySelector('.menu');
12   var main = querySelector('main');
13
14   closeMenu(e) {
15     document.body.classes.remove('open');
16     appbarElement.classes.remove('open');
17     navdrawerContainer.classes.remove('open');
18   }
19
20   toggleMenu(e) {
21     document.body.classes.toggle('open');
22     appbarElement.classes.toggle('open');
23     navdrawerContainer.classes.toggle('open');
24     navdrawerContainer.classes.add('opened');
25   }
26
27   main.onClick.listen(closeMenu);
28   menuBtn.onClick.listen(toggleMenu);
29   navdrawerContainer.onClick.listen((event) {
30     if (event.target.nodeName == 'A' || event.target.nodeName == 'LI') {
31       closeMenu(event);
32     }
33   });
34 }
```

Vejamos alguns detalhes da implementação:

- Na linha 4 declaramos o nome da biblioteca que estamos implementando (que também pode ser empacotada e importada como um componente independente em outros projetos). Essa biblioteca será responsável por gerenciar o menu de navegação da nossa página.

- Na linha 6 importamos a biblioteca html da Dart. Todos os imports devem ser sempre feitos usando a sintaxe fabricante:biblioteca>.

- Da linha 9 à linha 12 estamos recuperando os elementos HTML referentes às divs de container, botões e barra de menu. A função querySelector() recebe o seletor do elemento a ser recuperado e varre a página buscando-o, caso exista mais de um, um vetor será criado e associado.

- As funções closeMenu() e toggleMenu() (linhas 14 e 20) apenas tratam de mudar as classes CSS dos mesmos elementos recuperados para que eles mudem de estilo quando um item de menu for selecionado e desselecionado.

  A função remove(), por sua vez, remove a classe CSS passada por parâmetro do elemento, enquanto toggle() testa se a classe já existe, senão ela insere a informada como argumento. Já a função add() (linha 24) adiciona a classe informada ao elemento HTML.

- Nas linhas 27 a 29 definimos o ouvinte de click dos componentes de menu para executar as funções de navegação de página. Na Dart, sempre usamos os mesmos atributos dos eventos ouvintes “on” para informar qual evento deve ser executado.

  Já a função listen() da API da Dart recebe uma segunda função como parâmetro para ser executada sempre que o click for efetuado. Veja que a Dart também nos permite criar funções anônimas (linha 30) em vez de defini-las sempre em funções separadas.

Agora abra o arquivo reverser.dart que conterá o código de reversão dos textos e adicione o conteúdo da **Listagem 2**.

**Listagem 2**. Conteúdo do arquivo reverser.dart.

```
01 // Copyright (c) 2015, DevMedia. All rights reserved. Use of this source code
02 // is governed by a BSD-style license that can be found in the LICENSE file.
03
04 library reverser;
05
06 import 'dart:html';
07
08 InputElement get _inputElement => querySelector('#nome');
09 Element get _outputElement => querySelector('#out');
10
11 // Exemplo de gancho no DOM e resposta às mudanças de campos de entrada.
12 initReverser() {
13   // Revete assim que o código inicia.
14   _reverse();
15
16   // Reverte há cada soltura de tecla.
17   _inputElement.onKeyUp.listen((_) => _reverse());
18 }
19
20 _reverse() {
21   _outputElement.text = _inputElement.value.split('').reversed.join();
22 }
```

Vejamos alguns detalhes:

- Na linha 4 definimos novamente o nome da biblioteca, e na linha 6 a importação da lib html.
- Na linha 8 recuperamos o campo de input do nome a ser digitado e adicionamos a um objeto InputElement da API da Dart.
- Na linha 9 recuperamos o elemento referente ao campo de output (a Dart disponibiliza essa e outras novas tags HTML) que imprimirá o texto reverso.
- Na linha 20 chamamos a função _reverse() que simplesmente acessa o valor do campo de input, quebra-o em um vetor de chars (split) e chama a propriedade reversed que será responsável por reverter as posições do vetor. No fim, chamamos a função join() que une o vetor em uma string novamente e o adiciona à propriedade text (como se trata de um campo de output, não usamos o “value” dos input, e sim “text”) do elemento.
- Finalmente, na linha 17 implementamos o evento de onKeyUp para quando o usuário digita algo no campo e associamos a função _reverse() ao mesmo.

Agora precisamos editar o arquivo main.dart que representa o escopo inicial de execução do framework, isto é, ele sempre irá carregar os demais arquivos dart a partir deste. Para isso, adicione o conteúdo da **Listagem 3** ao mesmo.

**Listagem 3**. Conteúdo do arquivo main.dart.

```
01 // Copyright (c) 2015, DevMedia. All rights reserved. Use of this source code
02 // is governed by a BSD-style license that can be found in the LICENSE file.
03
04 import 'dart:html';
05
06 import 'package:AloMundoDart/nav_menu.dart';
07 import 'package:AloMundoDart/reverser.dart';
08 import 'package:route_hierarchical/client.dart';
09
10 void main() {
11   initNavMenu();
12   initReverser();
13
14   // Webapps precisam de routing para ouvir as mudanças na URL.
15   var router = new Router();
16   router.root
17     ..addRoute(name: 'sobre', path: '/sobre', enter: showSobre)
18     ..addRoute(name: 'home', defaultRoute: true, path: '/', enter: showHome);
19   router.listen();
20 }
21
22 void showSobre(RouteEvent e) {
23   // Extremely simple and non-scalable way to show different views.
24   querySelector('#home').style.display = 'none';
25   querySelector('#sobre').style.display = '';
26 }
27
28 void showHome(RouteEvent e) {
29   querySelector('#home').style.display = '';
30   querySelector('#sobre').style.display = 'none';
31 }
```

Vejamos alguns detalhes:

- Nas linhas 6 a 8 vemos a importação dos dois arquivos de script dart que criamos antes, além de um novo client.dart. Esse arquivo será herdado da API para implementar o routing das páginas, ou seja, lidar com as mudanças de URL de acordo com as ações definidas para cada página.
- Na linha 15 criamos um novo objeto Router, que se encarrega de definir as rotas possíveis para a aplicação como um todo. O método addRoute() recebe alguns parâmetros, a saber:
  - **name:** nome da rota.
  - **path:** URL relativa do caminho interno da rota.
  - **enter:** recebe a função a ser chamada quando essa rota for acessada.
  - **defaultRoute (opcional):** booleano para definir se a rota atual é a padrão.
- Os métodos showHome e showSobre se encarregam de exibir e esconder as divs de conteúdo da página. Estas devem ser incrementadas à medida que as páginas aumentam na aplicação.

Para finalizar, vamos editar a página HTML index.html. Ela é um pouco extensa, então vamos dividir em duas partes: cabeçalho/navegação (**Listagem 4**), e página de conversão/página de sobre.

**Listagem 4**. Conteúdo do cabeçalho e div de navegação da página index.html.

```
01 <!DOCTYPE html>
02
03 <html>
04 <head>
05   <meta charset="utf-8">
06   <meta http-equiv="X-UA-Compatible" content="IE=edge">
07   <meta name="viewport" content="width=device-width, initial-scale=1.0">
08   <meta name="scaffolded-by" content="https://github.com/google/stagehand">
09   <title>AloMundoDart</title>
10
11   <!-- Add à homescreen pelo Chrome no Android -->
12   <meta name="mobile-web-app-capable" content="yes">
13   <link rel="icon" sizes="192x192" href="images/touch/chrome-touch-icon-192x192.png">
14
15   <!-- Add à homescreen pelo Safari no iOS -->
16   <meta name="apple-mobile-web-app-capable" content="yes">
17   <meta name="apple-mobile-web-app-status-bar-style" content="black">
18   <meta name="apple-mobile-web-app-title" content="Web Starter Kit">
19   <link rel="apple-touch-icon-precomposed" href="apple-touch-icon-precomposed.png">
20
21   <!-- Tile icon for Win8 (144x144 + tile color) -->
22   <meta name="msapplication-TileImage" content="images/touch/ms-touch-icon-144x144-precomposed.png">
23   <meta name="msapplication-TileColor" content="#3372DF">
24
25   <!-- TODO: Troque as duas referências de folha de estilo para usar o Sass
26     (e tire o transformador sass no arquivo pubspec.yaml. -->
27   <link rel="stylesheet" href="styles/main_gen.css">
28   <!-- link rel="stylesheet" href="styles/main.css" -->
29 </head>
30
31 <body>
32   <!-- conteúdo do exemplo. -->
33
34   <header class="app-bar promote-layer">
35     <div class="app-bar-container">
36       <button class="menu"><img src="images/hamburger.svg" alt="Menu"></button>
37       <h1 class="logo">Reversor de Palavras</h1>
38       <section class="app-bar-actions">
39       <!-- Put App Bar Buttons Here -->
40       <!-- e.g <button><i class="icon icon-star"></i></button> -->
41       </section>
42     </div>
43   </header>
44
45   <nav class="navdrawer-container promote-layer">
46     <h4>Navegação</h4>
47     <ul>
48       <li><a href="/">Home</a></li>
49       <li><a href="/sobre">Sobre</a></li>
50     </ul>
51   </nav>
```

A maior parte dessa listagem compreende tags de importação de estilo e tags meta, além da estrutura de divs HTML para conter o menu de navegação. Vejamos alguns detalhes:

- As tags meta das linhas 12 e 13 servem para criar um atalho da aplicação nos dispositivos Android. Da mesma forma, as representadas nas linhas 16 a 18 fazem o mesmo para dispositivos iOS. Já na linha 22 temos uma representação deste código para dispositivos que rodam Windows 8/Windows Phone.
- Na linha 25 temos o conteúdo da tag de estilo necessária para incutir Sass nas páginas, caso deseje.
- O restante da implementação traz apenas divs e links para a navegação. A estrutura foi feita baseada no CSS disponibilizado pelo Dart no projeto recém-criado.

A segunda parte da página pode ser encontrada na **Listagem 5** e deve ser adicionada logo após o final da anterior.

**Listagem 5**. Conteúdo das páginas de conversão e sobre.

```
01  <main>
02
03    <div id="home">
04      <p>
05        Nome:<br>
06        <input type="text" id="nome" placeholder="Digite o seu nome...">
07      </p>
08
09      <p>
10        Revertido:<br>
11        <output id="out"></output>
12      </p>
13    </div>
14
15    <div id="sobre" style="display:none">
16      <p>
17        Este é um aplicativo de demonstração HTML básico construído com Dart.
18        Para os desenvolvedores que não querem, ou não podem, usam polymer.dart,
19        este é um ponto de partida opcional.
20      </p>
21    </div>
22
23    <div class="sass-hidden">
24      <p>
25        Nota: para usar Sass com esta aplicação,
26        mude as referências de folha de estilo na tag <head>
27        e descomenteo transformador sass no arquivo pubspec.yaml.
28      </p>
29    </div>
30  </main>
31
32  <script type="application/dart" src="main.dart"></script>
33  <script data-pub-inline src="packages/browser/dart.js"></script>
34 </body>
35 </html>
```

Como boa prática de implementação no front-end, estamos importando os arquivos de script da Dart apenas no final, assim ganhamos em performance pois a página já estará carregada quando chegarmos nestes arquivos. Perceba que o atributo type da tag script (comumente preenchido com o valor “text/javascript”) deve ser preenchido com “application/dart” sempre. Já o src aponta para o arquivo main.dart. A segunda tag de script (linha 33) serve para carregar a API da Dart na página.

Note também que a segunda div deve vir escondida (display:none) para que possamos exibi-la somente quando selecionada no menu. Veja como é fácil incutir navegação na Dart: basta criar divs e escondê-las, deixando que a API se encarrega de redirecionar para onde você mandar.

Após isso, salve todos os arquivos e clique no botão *Run* no topo da IDE ou selecione o atalho Ctrl + R. O resultado deverá ser igual ao das **Figuras 4** e **5**.

![Resultado da página de reversão](https://arquivo.devmedia.com.br/REVISTAS/front_end/imagens/edicao7/3/4.png)

**Figura 4.** Resultado da página de reversão.

![Navegando à página de sobre]()**Figura 5.** Navegando à página de sobre.

Note que o Editor abrirá uma janela interna do Google Chrome. Você não precisa ter o browser instalado, já que ele traz uma instância interna do mesmo no pacote de instalação. Essa abordagem é usada pelo Google para evitar fazer testes em browsers internos às IDEs (como no Eclipse, por exemplo), possibilitando testes mais reais e automatizados. A comunicação com frameworks de teste como o Selenium é fácil de ser feita nessa versão do Chromium.

Veja que na barra de URLs do browser interno ele abriu a aplicação no endereço http://localhost:8080. Essa é a URL padrão do framework, pois ele faz uso do Node.js para compilar e executar o JavaScript no servidor. Por acaso se não estiver conseguindo executar ou aparecer algum erro de porta em uso, verifique se não está executando alguma ferramenta que usa a porta 8080, como os servidores Java Tomcat e JBoss, por exemplo.

Ainda sobre a URL, veja que na tela *Sobre* temos a URL com a respectiva terminação. Isso acontece porque definimos que a ação é exibir a div com a propriedade name de valor sobre.

A Dart também gera conteúdo responsivo automaticamente. Logo, se executarmos a mesma tela em um dispositivo smartphone ou tablet, teremos como resultado a tela exibida na **Figura 6**.

![Telas da aplicação em dispositivo menor]()**Figura 6.** Telas da aplicação em dispositivo menor.

### Principais características

A Dart inaugurou uma lista de novos conceitos no mundo da programação. Vejamos alguns deles.

### Modularidade e Namespace

O conceito de modularidade é baseado na divisão em componentes menores e independentes. Além disso, cada módulo precisa ter uma responsabilidade única e fornecer estruturas que permitam se conectar a ele.

Por exemplo, se tivermos um sistema hospitalar e desejamos dividi-lo em módulos que possam ser acoplados a outros sistemas de terceiros, teríamos um módulo para o almoxarifado, outro para o controle de consultas, mais um para o cadastro de exames, e por aí vai.

Esse tipo de recurso é muito usado por softwares de clientes que precisam de alguns componentes enquanto outros do mesmo negócio não. No universo de programação, essa divisão leva o nome de “decomposição”.

Para que cada parte do sistema seja decomposta ela precisa passar por um ciclo de ações: criação, mudança, teste, uso e substituição separada.

A modularidade na Dart é feita através dos pacotes, bibliotecas e classes:

- Uma **biblioteca** expõe as funcionalidades como um conjunto de interfaces e esconde a implementação do resto do mundo. Como um conceito, é muito similar à separação de responsabilidades que temos na Programação Orientada a Objetos, por exemplo.

  Como resultado, o usuário passa a ter menos código concentrado e mais facilidade na hora de manter o mesmo, já que as mudanças se concentram agora sempre num componente só.

  Além disso, o conceito de biblioteca passa a não mais englobar somente APIs server side, mas também frameworks front-end.

- Um **pacote** é um simples diretório que contém um arquivo chamado pubspec.yaml e inclui em si uma quantidade x de bibliotecas e recursos. Este arquivo contém informações importantes sobre o pacote como seus autores, além de suas dependências em relação a outros pacotes.

  Vejamos na **Listagem 6** o conteúdo deste arquivo criado no nosso exemplo de AloMundo. Perceba que ele funciona como uma espécie de Google Doc, porém especificamente para a Dart; além disso, estes são apenas campos básicos, é possível encontrar uma lista das demais opções no site oficial da linguagem (vide seção **Links**).

  Esse arquivo é obrigatório para que o seu Sistema Operacional reconheça o tipo de tecnologia que irá operar ali.

- Antes de ser usado, um pacote deve sempre ser publicado em um “sistema de gerenciamento de pacotes”, que está disponível como um recurso online chamado *pub* (veja na seção **Links** a URL do pub oficial da Dart). Em relação à recuperação dos mesmos pacotes no pub, uma aplicação utilitária de mesmo nome pode ser usada para tal. Esta usa informações sobre as dependências do pubspec.yaml para recuperar todos os pacotes necessários dos seguintes locais:

  - Pacotes recentemente atualizados no site da pub Dart;
  - Repositório Git;
  - Diretório no filesystem local.

- As **classes** podem ser representadas usando funções comuns ou protótipos de herança.

**Listagem 6**. Estrutura de diretórios padrão do projeto.

```
01 name: 'AloMundoDart'
02 version: 0.0.1
03 description: >
04   A mobile-friendly web app with routing, responsive CSS, and (optional) Sass
05   support.
06 #author: <your name> <email@example.com>
07 #homepage: https://www.example.com
08 environment:
09   sdk: '>=1.0.0 <2.0.0'
10 dependencies:
11   browser: '>=0.10.0 <0.11.0'
12   sass: '>=0.4.0 <0.5.0'
13   script_inliner: '>=1.0.0 <2.0.0'
14   route_hierarchical: '>=0.5.0 <0.7.0'
15 transformers:
16 - script_inliner
17 #- sass:
18 #    style: compressed
```

Já os namespaces são containers para todos os membros de uma biblioteca. Um namespace é definido pelo nome da biblioteca. Ou seja, se uma biblioteca é implicitamente nomeada então ela tem um namespace vazio.

Isso resulta muitas vezes em conflitos ao tentar importar bibliotecas com os mesmos namespaces. Tais conflitos podem ser evitados com uma cláusula prefixada (as) e um nome de prefixo.

Veja a **Listagem 7**. Nela, temos um exemplo de biblioteca implicitamente nomeada na qual todos os recursos da dart:html estão disponíveis através do escopo da nossa biblioteca com o prefixo dom. >

**Listagem 7**. Exemplo de biblioteca implicitamente nomeada.

```
01 /**
02 * Biblioteca nomeada implicitamente.
03 * A lib dart:core é automaticamente importada.
04 */
05 import 'dart:html' as dom;
06 /**
07 * Recupera [Elemento] por [id].
08 */
09 dom.Element getById(String id) => dom.querySelector('#$id');
```

Obviamente, todas as marcações e seletores só serão reconhecidos em um ambiente Dart. O browser não consegue interpretar essa notação. Veja que na linha 5 fazemos uso da cláusula “as” para importar o recurso (biblioteca HTML da Dart) de forma dinâmica.

Na linha 9 fazemos a recuperação do elemento id pelo seu atributo id da HTML. Isso é bem semelhante à forma como o jQuery faz a seleção de seus atributos, por exemplo. Contudo, quando for compilado para JavaScript, todo esse código perde as informações das bibliotecas e temos um arquivo bem diferente sendo gerado.

A Dart implementa o conceito de encapsulamento através da privacidade. Cada membro ou identificador de uma biblioteca tem um dos dois níveis de acesso: público ou privado. Membros privados são visíveis apenas de dentro da biblioteca na qual eles são declarados.

Por outro lado, os membros com um acesso público são visíveis em todos os lugares. A diferença entre eles é o prefixo sublinhado (_), como mostrado no código da **Listagem 8**.

**Listagem 8**. Exemplo de encapsulamento na Dart.

```
01 // Biblioteca Animation.
02 library animation;
03 // Classe publicamente disponível em qualquer lugar.
04 class Animation {
05 // ...
06 }
07 // Classe visível apenas dentro da biblioteca.
08 class _AnimationLibrary {
09 // ...
10 }
11 // Variável publicamente disponível em qualquer lugar.
12 var animationSpeed;
```

O código mostra uma biblioteca de animação com duas classes e uma variável. A classe de Animação e a variável animationSpeed são públicas e, portanto, visíveis de fora da biblioteca. A classe _AnimationLibrary é privada e só pode ser utilizada na biblioteca.

Acessos públicos podem ser controlados com as extensões show e hide na declaração de importação. Use a seguinte extensão show com uma classe específica, que estará disponível dentro da biblioteca em que é importada:

```
import 'animation.dart' as animation show Animation;
main() { new animation.Animation(); }
```

O prefixo **animation** na declaração de importação define o namespace para importar a biblioteca animation.dart. Todos os membros da biblioteca animation.dart estão disponíveis no namespace global através deste prefixo.

Já a extensão hide especificada na classe fará com que a mesma esteja inacessível de dentro da biblioteca na qual foi importada. Isso é interessante quando precisamos que uma classe só seja acessa de dentro da própria API, como classes de segurança, conexão com banco, etc.:

```
import 'animation.dart' as animation hide Animation;
main() { var speed = animation.animationSpeed; }
```

### Funções e Closures

Na Dart é possível criar **funções** via variável, isto é, criamos uma referência a uma função e a atribuímos para uma variável, conforme pode ser observado na **Listagem 9**.

**Listagem 9**. Exemplo de função com associação de variáveis a funções.

```
01 library function_var;
02     // Returna a soma de [a] e [b]
03     soma(a, b) {
04           return a + b;
05     }
06     // Operação
07     var operacao;
08     void main() {
09           // Atribui a referência à função [soma]
10           operacao = soma;
11           // Execute operacao
12           var resultado = operacao(2, 1);
13           print("Resultado será ${resultado}");
14     }");
15 }
```

O resultado será 3. Veja que criamos uma função simples de soma de dois valores e adicionamos a função a uma variável (operacao, linha 10) chamando-a em vez de à função soma(). Na linha 13 imprimimos o resultado da soma.

Veja que as impressões no console JavaScript são feitas via método print() e os valores a se concatenar via operador ${}.

A Dart ainda lida com a passagem de funções como argumentos para outras funções; retorno de funções como resultado de outras (return) e consegue salvar funções em estruturas de dados, como vetores, por exemplo.

A função pode ser criada em âmbito global ou no âmbito de uma outra função. Uma função que pode ser referenciada com um acesso para as variáveis no seu escopo léxico é chamada de **closure**. Vejamos o código da **Listagem 10**.

**Listagem 10**. Exemplo de closure na Dart.

```
01 library function_closure;
02
03 // Função retorna uma closure.
04 calcular(base) {
05     // Contador
06     var cont = 1;
07     // Função interna - closure
08     return () => print("Valor será ${base + cont++}");
09 }
10 void main() {
11     // A função externa retorna a interna
12     var f = calcular(2);
13     // Agora chamamos a closure
14     f();
15     f();
16 }
```

A estrutura para criar uma closure é a mesma para as funções comuns. A diferença é que a closure é criada e retornada de dentro de uma função já existente. Ela funciona como uma função anônima que pode ser criada facilmente sem a necessidade de todo o aparato de palavras-chave para formar as funções comuns.

Veja que na linha 8, após criar a variável contadora, estamos associando o ato de imprimir a soma e contador a uma função vazia (). O operador => serve para fazer essa associação, muito comum em estruturas como lambdas.

Após isso, sempre que quisemos chamar essa closure basta retornar para uma variável e efetuar as chamadas: f() (linhas 14 e 15).

Neste exemplo, os resultados serão 3 e 4, respectivamente.

### Classes

No mundo real, encontramos muitos objetos individuais, todos do mesmo tipo. Há muitos carros com a mesma marca e modelo. Cada carro foi construído a partir do mesmo conjunto de projetos. Todos eles contêm os mesmos componentes e cada um é uma instância da classe de objetos conhecida como Carro.

O conceito de classe na orientação a objetos é o mesmo na Dart. Atributos, métodos, classes internas e construtores se mantêm na linguagem. Vejamos a **Listagem 11**, onde temos a representação de um objeto do tipo Carro.

**Listagem 11**. Representação da classe Carro na Dart.

```
01 library carro;
02 //Classe abstrata [Carro] não pode ser instanciada.
03 abstract class Carro {
04     String cor;
05     double velocidade;
06     double capacidade;
07
08     // Construtor da classe
09     Car(this.cor, this. capacidade);
10     // Move o carro de acordo com a [velocidade]
11     void move(double velocidade) {
12           this.velocidade = velocidade;
13     }
14     // Para o carro.
15     void stop() {
16           velocidade = 0.0;
17     }
18 }
```

Vejamos alguns detalhes da listagem:

- Na linha 3 declaramos a classe sendo de um tipo abstrato (abstract). Isso significa que essa classe não poderá nunca ser instanciada (new), e sim somente servir com classe pai de outras.
- Nas linhas 4 a 6 declaramos os atributos, todos globais e públicos (não é preciso usar palavras reservadas para isso). O tipo String pertence à API da Dart e funciona da mesma forma que em outras linguagens OO (Java, C#, etc.). Os tipos primitivos (int, double, char, boolean...) também se mantêm.
- Na linha 9 criamos o construtor da classe que recebe os dois parâmetros para associar aos atributos de cor e capacidade. Veja que não precisamos fazer a associação dos valores manualmente, a própria Dart faz isso para gente automaticamente, simplificando muito o código.
- Os métodos também são públicos. A palavra void define que eles não têm nenhum retorno, apenas executando o código interno.

### Mixins

A Dart tem um sistema de herança baseado em mixins, que permitem que o corpo de certas classes possa ser reusado em classes hierárquicas. Vejamos o código da **Listagem 12**.

**Listagem 12**. Exemplo de classe a ser mixada.

```
01 library reboque;
02 // O reboque
03 class Reboque {
04     // Acessa a informação de [carga] do carro
05     double carga = 0.0;
06     // O reboque pode carregar tanto de [peso]
07     void carregar(double peso) {
08           // O carregamento aumenta com pesos extra.
09           carga += peso;
10     }
11 }
```

A classe Reboque é independente da classe Carro, mas pode aumentar a capacidade de carregar peso do carro. Para adicionar um mixin de Reboque à classe CarroPassageiro podemos usar a palavra-chave with seguida pela classe mixin Reboque, como no código da **Listagem 13**.

**Listagem 13**. Exemplo de mixin na Dart.

```
01 library passenger_carro;
02 import 'carro.dart';
03 import 'reboque.dart';
04 // Carro de passageiro com reboque.
05 class CarroPassageiro extends Carro with Reboque {
06     // Nº max de passageiros.
07     int maxPassageiros = 4;
08     /**
09     * Cria um [Passageiro] com a [cor], [carga] e [maxPassageiros].
10     * Podemos usar o [Reboque] para carregar [pesoExtra].
11     */
12     Passageiro(String cor, double carga, this.maxPassageiros,
13           {double pesoExtra:0.0}) : super(cor, carga) {
14           // Só podemos carregar peso extra com [Reboque]
15           carregar(pesoExtra);
16     }
17 }
```

Com a adição da cláusula with na linha 5 temos agora assimilada a funcionalidade de adicionar mais peso ao reboque do carro (linha 15). Para isso, não precisamos mudar nada na classe CarroPassageiro, basta adicionar o mixin e os métodos serão automaticamente carregados sem a necessidade de uma herança explícita (extends).

Os mixins são semelhantes às interfaces e só podem ser definidos via classe, tendo algumas restrições no seu uso, a saber:

- Não podem ter construtores definidos;
- A superclasse de um mixin só pode ser um Object;
- Eles não podem ter chamadas ao operador super.

### Coleções e Genéricos

A Dart suporta o uso de vetores na forma de classes de List. Digamos que precisamos usar uma lista para salvar informações temporárias.

O dado que você coloca na lista depende do contexto do código. A lista deve conter diferentes tipos de dados ao mesmo tempo, conforme demostrado pela **Listagem 14**.

**Listagem 14**. Exemplo de lista na Dart.

```
01 // Lista de dados aleatórios
02 List lista = [1, "Letra", {'test':'errado'}];
03
04 // Item qualquer
05 double item = 1.53;
06
07 void main() {
08     // Add o item ao array
09     lista.add(item);
10     print(lista);
11 }
```

Neste exemplo adicionamos dados de diferentes tipos ao mesmo array. Quando o código for executado vermos o resultado [1, Letra, {test: errado}, 1.53] ser impresso no console. Esse tipo de funcionalidade é permitido em várias [linguagens de programação](https://www.devmedia.com.br/introducao-as-linguagens-de-programacao/25111).

Entretanto, não é interessante ter dados conflitando em uma estrutura que pode dar erros mais à frente. Para evitar esse tipo de comportamento podemos verificar qual tipo de dado está vindo na lista através do operador **is** (**Listagem 15**).

**Listagem 15**. Exemplo de lista checada na Dart.

```
01 // Array de dados String
02 List parts = ['roda', 'ignição', 'motor'];
03
04 // Item qualquer
05 double item = 1.53;
06
07 void main() {
08     if (item is String) {
09           // Add o item ao array
10           parts.add(item);
11     }
12     print(parts);
13 }
```

Agora o resultado impresso será [roda, ignição, motor]. Dessa forma, garantimos que nenhum tipo de dado que não seja String seja adicionado ao nosso array. Agora, imagine como seria se tivéssemos centenas de arrays no nosso projeto, ao ter de fazer esse tipo de verificação sempre que quisermos criar ou manipular um.

É muito trabalho desnecessário. Para resolver isso podemos usar um analisador estático de código que faz o trabalho todo. Chamamos essas estruturas de Genéricos. Vejamos na **Listagem 16** como ficaria nosso código.

**Listagem 16**. Exemplo de lista com Genéricos na Dart.

```
01 // Array de dados String
02 List<String> parts = ['roda', 'ignição', 'motor'];
03
04 // Ordinary item
05 double item = 1.53;
06
07 void main() {
08     // Add o item ao array
09     parts.add(item);
10     print(parts);
11 }
```

Dessa forma, caso o programador tente informar algum valor que não seja String no vetor, receberá um erro informando a tipagem errada.

### Erros e Exceções

Existe sempre uma confusão muito grande entre a diferença do que é um erro e uma exceção nas linguagens de programação.

**Erros** geralmente acontecem precedidos de falhas graves no fluxo dos algoritmos que impedem a continuação do sistema, como por exemplo o estouro de memória ou quando uma VM não consegue encontrar o recurso (classes, arquivos, etc.) que foi solicitado.

Já as **exceções** são manipuláveis via código, o programador pode capturá-las, entender o que aconteceu e então tomar uma decisão programática.

Vejamos o código da **Listagem 17**. Ele representa um exemplo onde um eventual erro acontece na Dart.

**Listagem 17**. Exemplo de código com “erro” na Dart.

```
01 main() {
02     // Lista de tamanho fixo
03     List lista = new List(5);
04     // Preenche a lista com os valores
05     for (int i = 0; i < 10; i++) {
06           lista[i] = i;
07     }
08     print('Resultado será ${lista}');
09 }
```

Estamos criando uma lista simples com a classe List de um tamanho fixo e preenchendo com os valores do inteiro contador em um loop que contém mais itens do que o tamanho máximo permite. Ao executar este código teremos uma exceção semelhante à da **Figura 7**.

![Tela de erro sendo impresso no console da Dart](https://arquivo.devmedia.com.br/REVISTAS/front_end/imagens/edicao7/3/7.png)**Figura 7.** Tela de erro sendo impresso no console da Dart.

Este erro ocorreu porque foi realizada uma condição de violação em nosso código quando tentamos inserir um valor na lista em um índice fora do intervalo válido.

Principalmente, esses tipos de falhas ocorrem quando o contrato entre o código e a API chamada foi quebrado. No nosso caso, RangeError indica que o pré-requisito foi violado.

Há um monte de erros no Dart SDK como CastError (Erro de conversão de um tipo para outro inválido), NoSuchMethodError (Quando não é possível encontrar um método informado), UnsupportedError (Quando um tipo de dado não é suportado), OutOfMemoryError (Quando não há memória suficiente para carregar objetos) e StackOverflowError (Quando a pilha de memória estoura o limite máximo).

Além disso, existem muitos outros erros que você pode encontrar no arquivo errors.dart como uma parte da biblioteca dart.core.

Todas as classes de erro herdam da classe Error e podem retornar informações de rastreamento de pilha para ajudar a encontrar a causa dos mesmos rapidamente. No exemplo anterior, o erro aconteceu na linha 6 do principal método no arquivo .dart.

Os erros podem ser detectados via código, mas são difíceis de manipular, dada a sua natureza imprevista. O mais ideal é sempre conhecer bem a API de erros da Dart para evitar as situações, que são bem exclusivas.

Exceções, ao contrário de erros, são feitas para serem capturadas e geralmente carregam informações sobre a falha, mas não incluem as informações de rastreamento de pilha.

Exceções acontecem em situações recuperáveis e não param a execução de um programa. Você pode lançar (throw) qualquer objeto não nulo como uma exceção, mas é uma boa prática criar uma nova classe de exceção que implemente a classe abstrata Exception e sobrescrever o método toString da classe Object, a fim de fornecer informações adicionais.

Uma exceção deve ser tratada dentro das cláusulas catch ou propagadas para as chamadas exteriores. Vejamos na **Listagem 18** um exemplo de código sem o uso de exceções, que faz acesso a um arquivo, uma vez que esse tipo de operação é uma das mais propensas a erro nas linguagens de programação em detrimento do acesso a diretórios, permissões, tamanhos dos arquivos, etc.

**Listagem 18**. Exemplo de código com exceção sem tratamento.

```
01 import 'dart:io';
02 main() {
03     // URI do arquivo
04     Uri uri = new Uri.file("teste.json");
05     // Checa a uri
06     if (uri != null) {
07           // Cria o arquivo
08           File file = new File.fromUri(uri);
09           // Checa se o arquivo existe
10           if (file.existsSync()) {
11                  // Abra o arquivo
12                  RandomAccessFile random = file.openSync();
13                  // Checa se o arquivo foi aberto
14                  if (random != null) {
15                  // Lê o arquivo
16                         List<int> conteudoNaoPronto = random.readSync(random.lengthSync());
17                         // Checa o conteúdo não pronto
18                         if (conteudoNaoPronto != null) {
19                                // Converte para String
20                                String conteudo = new String.fromCharCodes(conteudoNaoPronto);
21                                // Imprime o resultado
22                                print('conteúdo: ${conteudo}');
23                         }
24                         // Fecha o arquivo
25                         random.closeSync();
26                  }
27           } else {
28                  print ("Arquivo não existe");
29           }
30     }
31 }
```

O resultado da execução será conteúdo:[{name: teste, length: 150}]. Vejamos alguns detalhes do código:

- Na linha 1 importamos a biblioteca IO da Dart, que se encarrega de todas as operações de Entrada/Saída, incluindo acesso a arquivos e serialização.
- Na linha 4 carregamos a URI (URL interna) do arquivo. O leitor pode usar qualquer arquivo que desejar para efetuar o teste.
- O método fromUri() da linha 8 se encarrega de carregar o arquivo em memória para ser manipulado.
- O método existsSync() da linha 10 verifica se o arquivo de fato existe. Esse é o primeiro tratamento de erro que fazemos, isto é, em vez de manipularmos uma exceção diretamente, fazemos um teste para cada arquivo vendo se ele existe antes de usá-lo.
- Na linha 12 abrimos o arquivo para pegar seus bytes e na linha 16 lemos o seu conteúdo a fim de iterar sobre os dados do mesmo.
- Na linha 22 imprimimos o conteúdo que foi concatenado, fechando o arquivo na linha 25.

É interessante observar que, mesmo que o conteúdo seja impresso com sucesso e nenhuma exceção aconteça pelas precauções que tomamos, ainda assim na linha 25, ao fechar o arquivo, corremos o risco de receber uma exceção por várias razões: o arquivo foi removido por outrem, falha na conexão de rede, etc.

Em vista disso, para se ter uma maior segurança nesse fluxo e manter a organização do código, vamos evoluir o mesmo para o que está contido na **Listagem 19**.

**Listagem 19**. Exemplo de código com exceção e tratamento.

```
01 import 'dart:io';
02 main() {
03     RandomAccessFile random;
04     try {
05           Uri uri = new Uri.file("teste.json");
06
07           File file = new File.fromUri(uri);
08
09           random = file.openSync();
10
11           List<int> notReadyContent = random.readSync(random.lengthSync());
12
13           String conteudo = new String.fromCharCodes(notReadyContent);
14
15           print('conteudo: ${conteudo}');
16     } on ArgumentError catch(ex) {
17           print('Erro de argumento inválido');
18     } on UnsupportedError catch(ex) {
19           print('URI não pode referenciar um arquivo');
20     } on FileSystemException catch(ex) {
21           print ("Arquivo não existe ou está inacessível");
22     } finally {
23           try {
24                  random.closeSync();
25           } on FileSystemException catch(ex) {
26                  print("Arquivo não pode ser fechado");
27           }
28     }
29 }
```

As mudanças não foram tão grandes, mas fazem uma grande diferença na execução final. O bloco **try/on/catch** é a estrutura usada para capturar as exceções e a sintaxe é bem semelhante à das outras linguagens.

O nome do erro/exceção que você imagina que possa acontecer no código deve sempre vir declarado após a cláusula on<, evitando sempre usar superclasses genéricas para capturar as exceções específicas.

Veja que no bloco finally (atrelado ao catch que será obrigatoriamente executado ao final da sentença) efetuamos o fechamento do arquivo, mas caso algum erro aconteça nessa parte também faremos a validação e tratamento do erro. Dessa forma, garantimos um código organizado e livre de falhas que impeçam o sistema de continuar executando.

Existem muitos outros recursos que a linguagem Dart disponibiliza, tais como Anotações (para diminuir a quantidade de código em XML), Proxies dinâmicos (para aumentar a performance salvando dados em cache), reflection (para modificar as próprias estruturas programadas em tempo de execução), bem como outros conceitos da Orientação a Objetos (polimorfismo, interfaces, composição, etc.).

Contudo, com o conteúdo aqui exposto o leitor estará apto a criar aplicações mais robustas usando a Dart, seu SDK e o poderoso Editor que a mesma disponibiliza.

Para publicar suas aplicações, você pode utilizar a página do Google Code ou do próprio [GitHub](https://www.devmedia.com.br/curso/o-que-e-github/2046), bem como participar do projeto open source e ajudar a melhorar cada vez mais a linguagem.

A Dart também se integra facilmente a bancos de dados, web services, outros frameworks JavaScript, como [jQuery](https://www.devmedia.com.br/jquery-tutorial/27299), Prototype.js e AngularJS. Agora é com você e a sua criatividade. Bons estudos!

##### Referências

- [Página de download oficial da Dart](https://dart.dev/get-dart)
- [Página do repositório de pacotes da Dart](https://pub.dev/)

#### Confira também

[
  ](https://www.devmedia.com.br/o-que-e-flutter/40324)