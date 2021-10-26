- [Back-end](https://blog.geekhunter.com.br/category/back-end/) - [Full stack](https://blog.geekhunter.com.br/category/full-stack/) - [Mobile](https://blog.geekhunter.com.br/category/mobile/)

# Firebase: o que é e quando usar no desenvolvimento mobile?

- maio 6, 2021

Você sabe para que serve o Firebase e como tirar o melhor proveito dele como desenvolvedor mobile? Acompanhe aqui que hoje você vai entender tudo!

O mercado de desenvolvimento mobile está em plano vapor, e o aumento do uso de smartphones incentiva ainda mais o uso de ferramentas como essa.

A necessidade de respostas cada vez mais rápidas para as demandas dos usuários e da própria tecnologia exigem um rendimento superior dos aplicativos atuais.

É exatamente para isso que o Firebase foi criado e adquirido pelo Google em 2014, possibilitando rapidez na criação de aplicativos, monitoramento de confiança e engajamento de usuários.

Para provar sua capacidade, veja alguns exemplos de empresas usando o Firebase:

- Alibaba;
- The New Yotk Times;
- Duolingo;
- Trivago;
- Halfbrick.

Hoje você vai aprender um pouco mais sobre os seguintes tópicos:

**Conteúdo** [ocultar](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#) 

[1 O que é Firebase?](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#O_que_e_Firebase)

[2 O que faz o Firebase?](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#O_que_faz_o_Firebase)

[2.1 Quais linguagens o Firebase suporta?](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#Quais_linguagens_o_Firebase_suporta)

[3 Para quem é o Firebase](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#Para_quem_e_o_Firebase)

[4 Por que usar o Firebase](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#Por_que_usar_o_Firebase)

[5 Principais serviços do Firebase](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#Principais_servicos_do_Firebase)

[5.1 Realtime Database](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#Realtime_Database)

[5.2 Cloud Storage](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#Cloud_Storage)

[5.3 Authentication](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#Authentication)

[5.4 Hosting](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#Hosting)

[5.5 Remote Config](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#Remote_Config)

[5.6 Notifications](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#Notifications)

[5.7 Test Lab](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#Test_Lab)

[5.8 Analytics](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#Analytics)

[5.9 Crashlytics](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#Crashlytics)

[5.10 Dynamic Links](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#Dynamic_Links)

[5.11 Performance Monitoring](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#Performance_Monitoring)

[6 Quanto custa o Firebase?](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#Quanto_custa_o_Firebase)

[7 Vantagens do Firebase](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#Vantagens_do_Firebase)

[8 Desvantagens do Firebase](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#Desvantagens_do_Firebase)

[9 Como usar Firebase Android](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#Como_usar_Firebase_Android)

[9.1 Tutorial Firebase: como conectar seu Android app](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#Tutorial_Firebase_como_conectar_seu_Android_app)

[9.2 Como adicionar um arquivo de configuração do Firebase](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#Como_adicionar_um_arquivo_de_configuracao_do_Firebase)

[10 Alternativas ao Firebase](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#Alternativas_ao_Firebase)

[10.1 Back4app](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#Back4app)

[10.2 Backendless](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#Backendless)

[10.3 Parse](https://blog.geekhunter.com.br/firebase-o-que-e-e-quando-usar-no-desenvolvimento-mobile/#Parse)

## O que é Firebase?

![Logo do Firebase e ferramentas](https://geekblogti.wpengine.com/wp-content/uploads/2021/05/o-que-e-firebase.png)

Se pudermos rotular o Firebase, diremos que ele é **Backend-as-a-Service (Baas)**.

O Firebase é a plataforma de desenvolvimento de aplicativos móveis do Google que ajuda você a criar, melhorar e expandir seu aplicativo.

Digamos que existe uma variedade de tecnologias do lado do servidor (back-end) disponíveis no mercado para desenvolvedores testarem novas possibilidades de uso e o Firebase é uma das que mais tem atraído a atenção no mundo mobile.

Com ele, é possível oferecer experiências de aplicativos mais ricas para o usuário, otimizando a performance e a experiência da plataforma.

Além disso, o Firebase é versátil e os tipos de aplicativos que podem ser desenvolvidos com Firebase são: **Android**, **iOS** e **Web**.

## O que faz o Firebase?

Neste sentido de servidor, o **Firebase** **fornece aos desenvolvedores uma variedade de ferramentas e serviços para ajudá-los a desenvolver aplicativos de qualidade, aumentar sua base de usuários e ser mais lucrativo.**

Toda sua base é construída na infraestrutura do Google, sendo categorizado como um programa de banco de dados NoSQL, que armazena dados em documentos do tipo JSON.

O Firebase conta um grande conjunto de ferramentas de desenvolvimento. Destas, o **Realtime Database** e o **Cloud Firestore** podem armazenar dados estruturados em documentos e sincronizar os aplicativos correspondentes em milissegundos sempre que ocorre uma transformação de dados.

Isso quer dizer que tanto o aplicativo quanto seu banco de dados ouvem um ao outro, proporcionando ao usuário experiências integradas no aplicativo.

E o **Firebase Cloud Functions** pode até estender essa funcionalidade. Essas funções permitem que o desenvolvedor escreva código de back-end para responder a eventos que acontecem na plataforma Firebase sem precisar diretamente de nenhum servidor.

> Leia **[Programação Mobile: tudo para começar hoje](https://geekblogti.wpengine.com/programacao-mobile-tudo-para-comecar-hoje/)**!

### Quais linguagens o Firebase suporta?

O Firebase suporta o desenvolvimento nas seguintes linguagens: C++, Java, Javascript, Node.js, Objective-C e Swift. Os frameworks Angular, Backbone e React são suportados através da vinculação de nomes (bindings) diretamente com o banco de dados.

O Google também adicionou bibliotecas: FirebaseUI, Geofire, Firebase Queue, FirebaseJobDispatcher.

## Para quem é o Firebase

O Firebase foi projetado para se integrar muito bem com aplicativos da web e mobile com SDKs para uma imensa variedade de linguagens.

É uma suite de aplicativos feitas sob medida para qualquer desenvolvedor que precisa de **ferramentas** para construir apps melhores, mais **robustos**, com **menos erros**, mais **otimizados** para o usuário, **escalável** e ainda mais **lucrativos**.

## Por que usar o Firebase

Como a plataforma oferece um grande número de serviços, você não precisa se preocupar com diversos fatores que costumam gerar dores de cabeça numa aplicação Web ou Mobile, como:

- Segurança na comunicação e transferência de dados;
- Limitações de infraestrutura;
- Bugs de atualizações;
- Compatibilidade com vários tipos de dispositivos diferentes;
- Autenticação;
- Problemas que envolvem UI/UX.

Todos essas situações são passíveis de serem solucionadas por meio dos serviços oferecidos pelo Firebase.

Além disso, o Firebase é gratuito para começar e você pode usar a sua conta do Google! Crescendo a demanda, você poderá adquirir o plano pago, e ainda pagar somente o excedente dos produtos e ferramentas que for usando.

Mais para baixo falaremos sobre os planos e preços.

Como já foi citado, a **velocidade no desenvolvimento** dos aplicativos através do Firebase é outro ponto positivo.

O uso do Firebase e do Firestore permite que os desenvolvedores de frontend gerenciem todo o trabalho e reduzam o tempo necessário para a conclusão.

## Principais serviços do Firebase

![Quadro de Firebase Solutions e ferramentas](https://geekblogti.wpengine.com/wp-content/uploads/2021/05/firebase-solutions-1024x911.png)Gama completa de produtos e soluções do Firebase.

A suite de aplicativos do Firebase é enorme como você pode conferir na imagem acima, portanto iremos focar nos principais serviços utilizados por desenvolvedores:

### Realtime Database

De forma simples e objetiva, com o já mencionado **Realtime Database**, os dados são sincronizados em todos os clientes em tempo real e permanecem disponíveis mesmo quando um aplicativo está offline.

### Cloud Storage

O **Cloud Firestore** oferece uma forma prática de salvar arquivos, de imagens a arquivos, até o Google Cloud Storage diretamente do cliente.

O serviço tem seu próprio sistema de regras de segurança para proteger seus arquivos, enquanto concede privilégios de gravação detalhados aos seus clientes autenticados.

O banco de dados Firestore do Firebase é voltado para oferecer desempenho ideal, confiabilidade, escalonamento automático e usabilidade de referência.

### Authentication

Suporta autenticação usando senhas, números de telefone, perfil do Google, Facebook, Twitter etc.

O Firebase Authentication (SDK) pode ser usado para integrar manualmente um ou mais métodos de login em um aplicativo.

### Hosting

O **Firebase Hosting** fornece hospedagem rápida e segura para um aplicativo da web.

O conteúdo fica armazenado em cache nas redes de distribuição de conteúdo em todo o mundo (CDNs).

Exemplo com Gulp:



```javascript
var gulp = require('gulp');
var superstatic = require('superstatic');
var browserSync = require('browser-sync').create();


gulp.task('serve', function() {
  browserSync.init({
    server: {
      middleware: [superstatic({stack: 'strict'})]
    }
  });
  gulp.watch('public/*.html').on('change', browserSync.reload);
});
```



### Remote Config

Possibilita você personalizar seu aplicativo sem necessariamente implantar uma nova versão, ideal para monitorar as mudanças da plataforma.

### Notifications

As notificações podem ser enviadas com o Firebase sem precisar acrescentar nenhuma linha de código adicional.

Tudo vem pronto da suite de ferramentas do Firebase!

### Test Lab

Como o nome já deixa claro, é um laboratório de testes, assim o aplicativo é testado em dispositivos virtuais e físicos localizados nos data centers do Google.

Você terá acesso aos resultados, capturas de tela, registros e vídeos no console do Firebase.

### Analytics

Com o uso do **Analytics** do Firebase é possível entender melhor sobre seus usuários e como eles usam seu aplicativo.

Tome decisões muito mais inteligentes através de dados de consumo e não consumo do seu aplicativo.

Você também pode aplicar Machine Learning para fazer predições do comportamento do usuário de forma fácil e descomplicada.

Aqui também está inclusa a integração com o Google Ads! Você pode criar campanhas pagas de divulgação baseadas nos dados do Analytics para maior precisão.

### Crashlytics

Obtenha informações claras e acionáveis sobre os bugs que seu aplicativo apresenta em tempo real!

Com isso, você conseguirá rastrear, priorizar e resolver os problemas da sua aplicação.

### Dynamic Links

Os [Dynamic Links](https://firebase.google.com/products/dynamic-links) do Firebase são URLs inteligentes que direcionam o usuários para o lugar que você desejar em apps iOs, Android ou Web.

Explico: em uma pesquisa do Google, você pode ser direcionado diretamente para uma aplicação, mas e se você não tem ela instalada? Você consegue configurar o comportamento desse link e inserir esse tipo de variável.

Além disso, eles sobrevivem à instalação do seu aplicativo na hora, diferente de outros tipos de links que se perdedm nesse processo.

### Performance Monitoring

Obtenha informações sobre os problemas diretamente relacionados ao desempenho do seu aplicativo.

Para mais detalhes ou saber mais sobre outros serviços da plataforma (que são muuuuuitos) voc ê pode visitar o [**site oficial do Firebase**](https://firebase.google.com/).

## Quanto custa o Firebase?

O Firebase possui dois tipos de planos de uso da ferramenta:

**Plano Spark** (gratuito): o Firebase está disponível para uso gratuito de qualquer desenvolvedor, com um limite generoso de autenticações, armazenamento, *invocations*, hospedagem e mais.

**Plano Blaze** (pague conforme o uso): Assim que seu aplicativo for escalonado, você precisará migrar do plano gratuito para o plano pago conforme o uso. Com isso, você só precisa pagar pelos serviços que extrapolarem o limite gratuito do Firebase.

Por exemplo, no plano Spark, você tem limite de 5GB armazenados na Cloud Storage. Quando ultrapassar esse número, você paga US$ 0,026 a cada GB extra que utilizar.

Confira na página de [preços do Firebase](https://firebase.google.com/pricing) todas as informações no detalhe.

## Vantagens do Firebase

O Firebase é ótimo, confira algumas praticidades e benefícios que a plataforma é capaz de proporcionar:

- Dados em tempo real;
- API pronta;
- Autenticação via e-mail, Google, Facebook e Github;
- Segurança;
- Armazenamento de arquivos pelo Google Cloud Storage;
- Hospedagem de arquivos estáticos;
- Aplicativos altamente escaláveis;
- Sem preocupações quanto a infraestrutura.

## Desvantagens do Firebase

Mas como nem tudo são flores, o Firebase ainda sofre com alguns pontos para melhoria, por exemplo:

- Capacidade limitada de consultas devido ao modelo de fluxo de dados do Firebase;
- Os modelos de dados relacionais tradicionais não são aplicáveis ao NoSQL, seus chops SQL não serão transferidos;
- Sem instalação local;
- Não é open-source e também não possui servidores dedicados e suporte empresarial;
- Os preços podem ser difíceis de serem previstos e limitar custos pode ser incômodo.

## Como usar Firebase Android

Existem alguns pré-requisitos para integrar o Firebase ao seu projeto Android:

- Instalar ou atualizar o Android Studio para a versão mais recente;

- Certificar de que seu projeto atenda a estes requisitos:

  - API de nível 16 (Jelly Bean) ou posterior;

  - Gradle 4.1 ou posterior;

  - Jetpack (AndroidX)

     

    com:

    - *com.android.tools.build:gradle* v3.2.1 ou posterior
    - *compileSdkVersion* 28 ou posterior;

- Configurar um dispositivo físico ou usar um emulador para rodar seu app. Os emuladores devem usar uma imagem de emulador com o Google Play;

- Logar no Firebase usando sua conta do Google.

> 5 melhores [linguagens de programação para Android](https://geekblogti.wpengine.com/linguagens-de-programacao-para-android/)

### Tutorial Firebase: como conectar seu Android app

Adicionar o Firebase ao seu aplicativo envolve tarefas no console do Firebase e no projeto aberto do Android (por exemplo, você baixa os arquivos de configuração do Firebase do console e os transfere para o seu projeto do Android).

Para registrar seu app com o Firebase você precisa:

1. Acesse o [console do Firebase](https://console.firebase.google.com/u/0/?pli=1);
2. No centro da página de visão geral do projeto, clique no ícone do Android para iniciar o fluxo de trabalho;
3. Digite o nome do pacote do seu aplicativo em *Android package name*.
4. Clique em *Register app*.

### Como adicionar um arquivo de configuração do Firebase

Para adicionar um arquivo de configuração do Firebase, você precisa:

1. Clicar em *Download google-services.json* para obter seu arquivo de configuração do Firebase Android (google-services.json).
2. Mover seu arquivo de configuração para o diretório do módulo do seu aplicativo.

Para ativar as funcionalidades do Firebase em seu aplicativo, adicione o *[plugin google-services](https://developers.google.com/android/guides/google-services-plugin)* aos seus arquivos *Gradle*.

No seu arquivo Gradle de nível raiz (build.gradle), adicione regras para incluir o plug-in Gradle de serviços do Google. Verifique se você também possui o repositório Maven do Google.

```
buildscript {

  repositories {
    // Verifique se você tem a seguinte linha (se não, adicione-a):
    google()  // repositório Maven
  }

  dependencies {
    // ...

    // Adicionar:
    classpath 'com.google.gms:google-services:4.3.3'  // Google Services plugin
  }
}

allprojects {
  // ...

  repositories {
    // Verifique se você tem a seguinte linha (se não, adicione-a):
    google()  // repositório Maven
    // ...
  }
}
```

No seu arquivo Gradle do módulo (geralmente app / build.gradle), aplique o plug-in Gradle dos Serviços do Google:

```
apply plugin: 'com.android.application'
// Adicionar:
apply plugin: 'com.google.gms.google-services'  // plugin do Google Services

android {
  // ...
}
```

Por fim, você precisa [adicionar SDKs do Firebase ao seu aplicativo](https://firebase.google.com/docs/android/setup#java) conforme utilização do Java ou Kotlin.

## Alternativas ao Firebase

Existem alternativas ao Firebase no mercado, listei as três principais para você conhecer, confira:

### Back4app

Back4app é uma das soluções de BaaS mais fáceis e simples de usar e gerenciar, que pode beneficiar desenvolvedores que procuram uma solução prática e sem muita complexidade desnecessária para o dia a dia.

### Backendless

Backendless é outra alternativa importante ao Firebase, que oferece uma infinidade de recursos do BaaS para serem usados por qualquer desenvolvedor.

Se você deseja modificar qualquer aplicativo existente ou deseja iniciá-lo do zero, o Backendless deve ser considerado.

### Parse

Parse também é um player bastante popular como BaaS.

Possui uma enorme comunidade de desenvolvedores apoiando esta solução e conta com uma incrível variedade de serviços oferecidos com o objetivo de melhorar a funcionalidade de qualquer aplicativo.

Gostou do artigo sobre Firebase? Ficou alguma dúvida? Deixe seu comentário e compartilhe o conteúdo!

> Aproveite e confira as **[vagas para desenvolvedor mobile](https://bit.ly/3up8sfm)**!

![Eduardo Silva](https://s3.amazonaws.com/blog-geek-midia/wp-content/uploads/2020/01/17144506/unnamed-3.png)

[Eduardo Silva](https://blog.geekhunter.com.br/author/edusilva/)