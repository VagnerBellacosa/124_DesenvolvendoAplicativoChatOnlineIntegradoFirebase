# Conceitos básicos para programar para Android

## Android é um sistema operacional desenvolvido pela Google em meados de 2009 inicialmente para smartphones e tablets, mas que hoje está presente em diversos dispositivos como televisores, automóveis e relógios inteligentes.

- [Artigos](https://www.devmedia.com.br/artigos/)[Mobile](https://www.devmedia.com.br/artigos/mobile)Conceitos básicos para programar para Android

**Android é um sistema operacional desenvolvido pela Google, inicialmente para smartphones**. Hoje, ele está presente em diversos dispositivos como televisores, veículos, relógios inteligentes, e muitos outros.

Por conta disso, poucas carreiras são tão interessantes para o programador atualmente quanto a de desenvolvedor Android. Devido ao constante investimento em hardware feito pelos fabricantes de dispositivos, podemos executar desde utilitários até jogos de alta performance nesse sistema operacional.

Contudo, o que é o Android do ponto de vista da sua arquitetura?

### Conhecendo a arquitetura do Android

Para entendermos melhor como é o **desenvolvimento na plataforma Android** vamos olhar mais atentamente para a sua arquitetura.

Do ponto de vista da arquitetura, o Android é uma pilha de software erguida sobre uma versão customizada do Kernel do Linux. Na **Figura 1** vemos um panorama completo dessa divisão arquitetural. O Kernel é responsável por executar tarefas de baixo nível, mais próximas do hardware do dispositivo, como o gerenciamento de memória.

![Pilha de software do Android](https://arquivo.devmedia.com.br/artigos/40112/arquitetura.png)**Figura 1**. Pilha de software do Android

Ao utilizar o Kernel do Linux como fundação para as camadas superiores do sistema, **o Android também se vale da segurança desse sistema**, conhecido por sua estabilidade. Outra vantagem aqui é oferecer aos fabricantes de dispositivos a oportunidade de criar drivers para seus hardwares a partir de um sistema conhecido, bem documentado e independente.

### HAL - Camada de abstração de hardware

Sobre o kernel, temos a camada de abstração de hardware, também conhecida como HAL. Sua principal função é expor as capacidades do hardware do dispositivo para a API de alto nível, a qual é utilizada pelos desenvolvedores em suas aplicações e sobre a qual falaremos em seguida. É através da HAL que acessamos o hardware do dispositivo, como sua câmera, bluetooth, etc.

Quando o desenvolvedor faz uma chamada ao hardware, por exemplo, para receber um arquivo via bluetooth, o sistema Android carrega o módulo da biblioteca para esse hardware, que por sua vez implementa uma interface para este tipo específico de componente.

Acima da HAL, temos uma divisão entre os componentes que permitem a execução de aplicativos e serviços do sistema e as suas bibliotecas nativas.

### ART - Ambiente de tempo de execução

A Android Runtime, ou ART, é um ambiente de tempo de execução gerenciado no qual são executados os aplicativos e alguns serviços do sistema. Anterior a ele, o Dalvik era a máquina virtual utilizada, que ainda está presente nas versões do sistema menores que a Lollipop, Android 5.0 até 5.1.1. Ambos os ambientes de tempo de execução foram projetados para trabalhar com o formato Dalvik Executable, ou DEX, no qual encontramos um tipo de bytecode otimizado para o baixo consumo de memória.

Dentre as principais funcionalidades do ART temos a compilação de arquivos DEX em executáveis criados para o dispositivo durante a instalação do aplicativo. Além disso, o ART conta com um Garbage Collector otimizado para funcionar com pouco consumo e fragmentação da memória, rápida execução e processamento paralelizado. Por fim, o ART é desenvolvido para facilitar a depuração, geração de relatórios de erro e diagnósticos.

Tanto ART quando HAL possuem diversos componentes e serviços implementados de forma nativa em C/C++. Esse conjunto de bibliotecas, criadas para diversos fins, pode ser acessado a partir de APIs de alto nível, escritas na linguagem Java. É a partir destas APIs que os desenvolvedores, na grande maioria dos casos, criarão suas próprias aplicações.

Tanto ART quando HAL possuem diversos componentes e serviços implementados de forma nativa em C/C++. Esse conjunto de bibliotecas, criadas para diversos fins, pode ser acessado a partir de APIs de alto nível, escritas na linguagem Java. É a partir destas APIs que os desenvolvedores, na grande maioria dos casos, criam os seus próprios aplicativos.

### API

A API Java do Android contém os componentes que precisamos para criar aplicativos utilizando serviços e acessando recursos do sistema operacional. Construída de forma modular, essa API de alto nível implementa diversas funcionalidades como a criação de views, gerenciamento de recursos, notificações e alertas de usuário, navegação entre os aplicativos, etc. Além disso, ela também permite o compartilhamento de dados, como o acesso a agenda de contatos.

É com essa API que o desenvolvedor tem acesso as mesmas funcionalidades dos aplicativos de sistema, pois para o Android não há restrições entre o que uma aplicação do sistema ou outra terceirizada pode fazer. Portanto, uma aplicação terceirizada pode vir a ser o teclado ou navegador padrão para o usuário.

Além disso, os aplicativos fornecem capacidades que podem ser utilizadas pelo desenvolvedor em seus projetos. Por exemplo, mesmo que exista uma aplicação do sistema para envio de SMS você pode desenvolver a sua própria escrevendo todo código necessário para isso ou utilizar as capacidades da aplicação do sistema para envio de mensagens.

### Nível de API

Devido ao fato do **sistema operacional Android** estar presente em diversos dispositivos, com características diferentes, algumas questões devem ser levadas em consideração durante a programação de um aplicativo. Uma delas é o nível de API que escolhemos utilizar.

A medida em que as versões do sistema operacional são produzidas, novas funcionalidades são incorporadas ao código e essas melhorias são publicadas em novas versões da API. Atualmente o Android se encontra na versão 8, Oreo, e a API nível 27 é utilizada para desenvolvimento de aplicativos que serão executados a partir desta versão.

Geralmente, a empresa responsável pelo software deseja atrair para o seu produto a maior audiência possível. Portanto, o programador deve saber como trabalhar com APIs de nível mais baixo, codificando sua aplicação sem os recursos mais novos, visto que eles podem funcionar corretamente apenas em aparelhos de última geração.

Com a popularização do Material Design, para certas funcionalidades e recursos de interface o programador dispõe de uma Biblioteca de Suporte, sem que para isso perca compatibilidade com versões anteriores do sistema operacional.

O site oficial do Android mantém atualizados dados de uso de suas versões baseados em interações com o Google Play. [Nesta página](https://developer.android.com/about/dashboards/) nós podemos ver quais versões são mais utilizadas e quais estão caindo em desuso.

### Android Studio

O desenvolvimento de aplicativos para Android é feito utilizando um conjunto de bibliotecas e a API base do sistema, bem como ferramentas e utilitários para compilação e outras tarefas envolvendo o código. Atualmente, toda essa infraestrutura pode ser obtida a partir do Android Studio, uma IDE criada para o desenvolvimento de aplicativos para dispositivos que executam o sistema operacional Android.

Na **Figura 2** vemos o Android Studio realizando o monitoramento da memória do aparelho durante a execução de um aplicativo.

![Interface do Android Studio](https://arquivo.devmedia.com.br/artigos/40112/android.png)**Figura 2**. Interface do Android Studio

### Em qual linguagem programamos para o Android?

Assim como a API sugere, o **desenvolvimento para Android** se iniciou com a linguagem Java. Sendo essa a principal linguagem de desenvolvimento por tanto tempo, muito código foi produzido nela, incluindo aquele utilizado nas documentações. Portanto, antes de entrar no mercado de aplicativos para essa plataforma, o programador deve ter sólido conhecimento em Java.

É necessário também saber alguns conceitos. Caso o programador não esteja familiarizado com a orientação a objetos e igualmente com a codificação de interfaces, pacotes, classes aninhadas e anônimas, bem como genéricos, ele terá muita dificuldade para avançar na codificação de seus aplicativos ou mesmo compreender o código escrito por outros programadores.

Ao desenvolver aplicativos estamos preocupados com otimização de código na maior parte do tempo, visto que temos recursos limitados, como a memória de execução do aparelho. Isso faz com que utilizemos certos recursos da linguagem Java com maior frequência que em outros contextos.

Por exemplo, é possível que um programador Java web nunca tenha que criar [inicializadores estáticos](https://www.devmedia.com.br/mocks-introducao-a-automatizacao-de-testes-com-mock-object/30641) em suas classes, algo bem comum no desenvolvimento para Android.

### E o Kotlin?

Kotlin é uma linguagem de tipagem estática criada pela JetBrains, empresa por trás do Intellij IDEA, no qual é baseado o Android Studio, e muitas outros IDEs de sucesso. Ela possui uma sintaxe compacta, suporta a orientada a objetos e compatível com o Java.

Recentemente a Google anunciou que o Kotlin seria utilizado no **desenvolvimento de aplicativos Android**, o que despertou o interesse de muitos programadores. Empresas como Uber, Evernote e Pinterest são algumas dentre as pioneiras em adotar essa tecnologia. Em sua versão mais recente, o Android Studio incorporou o suporte a essa linguagem, com a qual podemos criar aplicativos completos ou mesmo desenvolver em conjunto com o código Java.

Para o programador iniciante é importante o domínio da linguagem Java, pois é possível que leve alguns anos para que o número de aplicativos criados em Kotlin se iguale aqueles criados em Java. Além disso, atualmente nem toda a documentação está disponível em Kotlin, sendo necessário o Java para compreender os códigos e exemplos. Isso não significa dizer que o Kotlin não possa ser utilizado desde o início dos seus estudos, mas que conhecer Java é necessário para o aprendizado consistente.

### E agora? Como programar meus primeiros aplicativos?

Na série abaixo você aprenderá como criar aplicativos para Android, utilizando Java e o Android Studio. Confira!

[Saiba maisVeja a Série **#partiu programar para Android?**](https://www.devmedia.com.br/android-developer/)

Tecnologias:

- Android
-  

- Mobile