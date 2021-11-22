# Primeiros passos com a linguagem

## Conhecendo o Dart - Introdução

<video class="elasticMedia" frameborder="0" controls="" controlslist="nodownload" style="box-sizing: inherit; margin: 0px; padding: 0px; position: absolute; top: 0px; left: 0px; width: 820px; height: 461.25px; border: 0px;"></video>

Olá, tudo bem? Meu nome é Timóteo Holanda e serei o instrutor do curso de **Dart** na Alura.

Nesse curso aprenderemos o que é Dart e quais as características dele e por que aprendê-lo.

Veremos também como instalar o Dart em nossas máquinas e preparar um ambiente de desenvolvimento utilizando o Visual Studio Code e alguns *plugins* que facilitarão nosso trabalho nessa jornada que é programar com o Dart.

Como esse é um curso básico, caso já tenha conhecimento em programação ou programa em outras linguagens como o Java, Jacascript, C# e C++, por exemplo, nesse curso entenderemos a diferença de sintaxe da linguagem Dart para outras. Se estiver iniciando agora sua carreira na programação, o curso possui todo o conteúdo necessário para ter uma noção de como programar usando o Dart.

Veremos assuntos como **variáveis**, **condicionais**, **variáveis booleanas**, **fluxos de controle**, **laços de repetição** com `for`e com `while`, e aprenderemos a diferença entre esses dois.

Também veremos o **break**, uma forma de sair dos laços de repetição, e os **laços de repetição alinhados**, assim como a maneira de executar o Dart no nosso terminal e obter a saída do nosso programa.

Se tiver interesse em entender mais sobre Dart, nos vemos no curso.

## Conhecendo o Dart - O que é Dart?

<video class="elasticMedia" frameborder="0" controls="" controlslist="nodownload" style="box-sizing: inherit; margin: 0px; padding: 0px; position: absolute; top: 0px; left: 0px; width: 820px; height: 461.25px; border: 0px;"></video>

Antes de começar a colocar a mão na massa com o código, conversaremos sobre o que afinal de contas é o Dart e por que devemos ou queremos aprender a linguagem.

O Dart é uma linguagem de programação que nasceu em 2011 e foi desenvolvida pela famosa gigante da tecnologia Google. Ele foi construído desde o início pensando em desenvolvimento rápido e multiplataformas.

Geralmente, conhecemos o Dart por causa do **Flutter**, uma *framework* construída também pelo Google com o objetivo de dar suporte a desenvolvedores para desenvolverem aplicações nativas, tanto para Android quanto IOS. Com ele também é possível desenvolver aplicações web e Desktop.

Porém, precisamos evitar confundi-los.O Dart é uma linguagem criada para o desenvolvimento das aplicações. O Flutter é a ferramenta que utiliza essa linguagem, tornando possível o desenvolvimento de aplicações móveis. Logo, o Dart funciona sem o Flutter, mas o Flutter não funciona sem o Dart.

Se já tivermos facilidade com a linguagem C e seus filhos, como o C++, o Java, o C# e assim por diante, o aprendizado será facilitado, pois o Dart foi construído com a intenção de ser fácil para aqueles que já estão no ramo. Mas não há muitos problemas para quem está começando na programação, pois o pensamento de simplificar a linguagem tornou-a fácil o bastante para quem ainda não possui conhecimento na área.

Para os que já tem familiaridade com as linguagens voltadas para a web, tal qual o Javascript, será interessante saber que o Dart foi aprovado pela Associação Europeia de Fabricantes de Computadores, a **ECMA**. Esta é a mesma organização que ditou os padrões de linguagem do Javascript. Isso é importante porque os padrões aprovados para o Dart, o ECMA-408, segue os mesmos padrões que o do Javascript, o ECMA-262, o que influencia diretamente no funcionamento interno da linguagem.

Apesar das duas linguagens serem pouco parecidas, nesse aspecto são quase irmãs, a ponto do Dart possuir um compilador interno conhecido como **dart2js** que será próprio para traduzir o código para Javascript, a fim de rodá-lo facilmente em navegadores.

Essa pode parecer uma má ideia, pois poderíamos escrever o código em Javascript diretamente ao invés de usar o Dart e depois convertê-lo. Mas a tradução indica que o Google investiu em otimização interna e segundo dados da própria empresa o Dart compilado para Javascript pode ter uma performance 50% melhor do que o V8, o interpretador de Javascript mais potente atualmente e que curiosamente também foi gerado pelo Google.

Há gráficos para observar a diferença de performance entre os dois em testes bem conhecidos quando nos tratamos da comparação entre duas ou mais linguagens. O Delta Blue e o Richards são métricas de velocidade baseadas em um programa médio, porque foram feitas para simular atividades comuns que os programas farão no computador. Eles analisam quanto tempo cada programa desenvolvido leva para realizar as atividades. Ambos mostram um desempenho melhor do dart2js com relação ao V8.

Mas afinal, por que precisamos de uma nova linguagem de programação se podemos usar o Javascript programando para a web e o Java para dispositivos? A resposta é que já estava na hora de haver uma nova linguagem, pois o Dart não coleta funcionalidades redudantes através dos anos.

Tanto o Javascript quanto o Java, linguagem com as quais estamos comparando o Dart, foram lançadas em 1995. As duas possuem vestígios de desenvolvimento de mais de 20 anos. Isso quer dizer que a versão que podemos baixar e executar nesse momento possui códigos de mais de 20 anos, já que todas as novidades foram acopladas ao mesmo código ao longo do tempo.

O Dart foi criado em 2011 e desde sua fundação foi pensado para ter a melhor performance e abranger todos os dispositivos possíveis da atualidade, Esta é uma nova linguagem com um novo objetivo para alcançar um novo campo de desenvolvimento em um futuro próximo, tanto na web quanto em dispositivos móveis e Desktop.

## Instalação e o primeiro programa - Instalando o Dart

<video class="elasticMedia" frameborder="0" controls="" controlslist="nodownload" style="box-sizing: inherit; margin: 0px; padding: 0px; position: absolute; top: 0px; left: 0px; width: 820px; height: 461.25px; border: 0px;"></video>

Hoje veremos como instalar tudo que precisamos para iniciar o desenvolvimento com a ferramenta que conhecemos como Dart.

O primeiro passo será acessar a internet com nosso navegador e acessar o site [dart.dev](https://dart.dev/) . Quem não souber Inglês não precisará se assustar, nós passaremos passo a passo o que for necessário para instalar o Dart em nossas máquinas. Para quem entende, também não se preocupe. A página dá a entender que o Dart é uma linguagem para construir aplicativos, mas dá muito foco à construção de interfaces gráficas. E o Dart realmente foi otimizado para uma boa construção de interfaces gráficas, mas começaremos com ele como uma linguagem de programação básica.

Clicaremos no botão "*Get Dart*". localizado na barra superior à direita da tela e uma nova página será aberta. Nela haverá instruções para a instalação de todas as versões do Dart. Numa parte da tela estará escrito "*Install the Dart SDK*". Este será o kit de desenvolvimento de software do Dart.

Diferentemente do Java, não precisaremos de uma JRE,. uma versão de ambiente da linguagem. O Dart só tem uma versão, portanto apenas uma precisará ser instalada por sistema operacional. Teremos a opção de instalação para Windows, Linux e Mac, usaremos o Windows devido às configurações da máquina.

Dentro da opção para Windows teremos ainda duas opções, a do Chocolatey, que pra quem ainda não conhece, é um gerenciador de pacote para Windows que tem algumas vantagens e desvantagens. Porém, a instalação por meio dele só será recomendável para os que já forem familiarizados com a ferramenta.

A segunda opção oferecida será a do guia de instalação. Bastará clicarmos no link e seremos transportados para outra página em que teremos ainda mais duas versões. Uma delas será a estável, a última lançada oficialmente pelos desenvolvedores do Dart. Todos as ferramentas agregadas à linguagem e que foram consideradas estáveis, sem *bugs*, estarão nessa versão.

Entretanto, se quiser acesso mais rápido às novas ferramentas sendo constantemente lançadas por quem desenvolve o Dart, é possível baixar a versão *Dev*, que permite o acesso a essas ferramentas que não existem na versão estável e não são consideradas prontas para a produção, então podem haver *bugs*, não sendo a mais recomendável.

As instruções de instalação para usuários do Linux e Mac também estarão na página do Dart Dev. No caso do Linux, para quem utiliza qualquer derivado do Debian será possível usar o segundo link, com uma forma semelhante a do Windows, baixar o arquivo e executá-lo no computador. Dessa forma, ainda será necessário rodar no terminal os dois comandos presentes nesta tela para instalar todos os binários do Dart e colocar o link para eles nas variáveis de ambiente da máquina.

Há ainda a opção de utilizá-lo pelo `apt-get` executando os quatro primeiros comandos da página e logo em seguida os dois seguintes para instalar a versão instável, ou outros três para a versão de desenvolvimento.

Voltando ao Mac, podemos rodar os dois comandos presentes no site no terminal do Mac para instalar no computador o Dart instável ou o comando seguinte para instalar o *Dev*.

Quanto a versão para Windows que baixamos, executaremos o arquivo, será aberto o *prompt* para executar como administrador, e aceitaremos os termos de contrato para continuar a instalação. Clicaremos em *Install* ao final do processo e baixaremos os dados.

Para verificar se o Dart estará instalado pelo Windows, podemos usar o "cmd". Abriremos o menu inicial, digitaremos "cmd" e teremos acesso ao terminal do computador, Para nos certificarmos de que o Dart estará instalado, abriremos o "cmd" e escreveremos `Dart --version` . Pressionaremos "Enter" e se virmos uma mensagem semelhante a `Dart VM version:` seguida do número da versão e data da instalação, isso significa que a instalação foi bem sucedida.

## Sobre o curso Dart: primeiros passos com a linguagem

O [curso Dart: primeiros passos com a linguagem](https://www.alura.com.br/curso-online-dart-primeiro-passos) possui **155 minutos de vídeos**, em um total de **48 atividades**. Gostou? Conheça nossos outros **[cursos de Dart](https://www.alura.com.br/cursos-online-programacao/dart)** em **[Programação](https://www.alura.com.br/cursos-online-programacao)**, ou leia nossos [artigos de Programação](https://www.alura.com.br/artigos/programacao).

Matricule-se e comece a estudar com a gente hoje! Conheça outros tópicos abordados durante o curso:

- Conhecendo o Dart
- Instalação e o primeiro programa
- Tipos de variáveis
- Condicionais
- Laços de repetição

## Aprenda Dart acessando integralmente esse e outros cursos, comece hoje!