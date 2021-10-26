![img](https://blog.rocketseat.com.br/content/images/size/w1000/2019/03/Firebase-O-que-e--Quando-usar.png)

# Firebase: serviços, vantagens, quando utilizar e integrações

[javascript](https://blog.rocketseat.com.br/tag/javascript/)•25 de Dez de 2018



Você alguma vez já deve ter ouvido esse termo ou visto em algum lugar um comentário sobre ele. Mas afinal, o que é o **[Firebase](https://firebase.google.com/)**?

O **Firebase** é um **Baas** (Backend as a Service) para aplicações Web e Mobile do Google, foi lançado em 2004 e com o passar dos anos cresceu muito, se tornando uma ferramenta que hoje para alguns projetos é a melhor opção, devido a quantidade de serviços oferecidos por ele, além da facilidade de implementação.

![img](https://blog.rocketseat.com.br/content/images/2018/12/firebase-logo.png)

A criação de uma aplicação, seja ela Web ou Mobile, não é fácil, é preciso se preocupar com diversos fatores, dentre eles:

- Funcionamento em variados tipos de dispositivos;
- Infraestrutura;
- Atualizações que não gerem mais erros que solucionam;
- Segurança na transferência de dados;
- Mecanismos de Autenticação;
- E o aumento de usuários, para prover a melhor experiência para eles.

Foi pensando em uma maneira de solucionar todos esses problemas que surgiu a motivação para a criação do **Firebase**.

> Obs.: BaaS ou *BackEnd As A Service (MBaaS = Mobile BackEnd As A Service)* é um serviço disponibilizado em que toda a estrutura do *backend* como: configuração de servidor, integração com banco de dados, sistema de *push notification* e outros serviços, que fazem parte do *backend*, estão completamente prontos para se integrar com o seu aplicativo.

## Serviços Oferecidos

O Firebase oferece uma gama de serviços que podem ser utilizados, eles são separados por 4 **grandes** categorias, sendo elas **Analyics**, **Develop**, **Grow** e **Earn**.

![img](https://blog.rocketseat.com.br/content/images/2018/12/firebase-services.png)

Serão listados apenas os serviços mais usados, para que possa ser focado nas vantagens e integrações.

------

### [Analytics](https://firebase.google.com/products/analytics/)

O **Analytics** possibilita a **análise** em **tempo real** sobre o comportamento dos usuários nos seus Apps, além de disponibilizar dados sobre falhas, compras no aplicativo, desempenho de links diretos e muito mais.

Mas esse serviço atualmente tem suporte apenas para Android, IOS, C++ e Unity.

```js
// Analytics on React Native
componentDidMount() {
  Analytics.setAnalyticsCollectionEnabled(true);
  Analytics.setUserId(<userId>);
  Analytics.setUserProperty(<propKey1>, <propValue1>)
  Analytics.setUserProperty(<propKey2>, <propValue2>)
  Analytics.setCurrentScreen(<screenName>, <screenComponent>);
  Analytics.logEvent(<eventName>, {
    <paramKey1>: <paramValue1>,
    <paramKey2>: <paramValue2>
  });
}
```

------

### [Realtime Database](https://firebase.google.com/products/realtime-database/)

O **Banco de Dados em Tempo Real** permite o armazenamento e sincronismo dos dados entre usuários e dispositivos em tempo real com um banco de dados NoSQL hospedado na nuvem.

Os dados atualizados são **sincronizados** em **todos os dispositivos** conectados em segundos. Além disso, seus dados permanecem **disponíveis** caso seu aplicativo fique **off-line**, o que oferece uma ótima experiência do usuário, independentemente da conectividade de rede.

```js
// Gravando no Banco de Dados
writeUserData(email,fname,lname){
  firebase.database().ref('UsersList/').push({
    email,
    name,
  }).then((data)=>{
    console.tron.log('data ' , data)
  }).catch((error)=>{
    console.tron.log('error ' , error)
  })
}

// Lendo do Bando de Dados
readUserData() {
  firebase
    .database()
    .ref('Users/')
    .on('value', function (snapshot) {
      console.tron.log(snapshot.val())
    });
}
```

------

### [Authentication](https://firebase.google.com/products/auth/)

O **Firebase Auth** oferece diversos métodos de **autenticação**, como e-mail/senha, provedores de terceiros, como o Google ou Facebook, Login Anônimo, Confirmação via SMS, ou o uso direto do seu sistema de contas. O gerenciamento de usuários se torna simples e seguro.

```js
// Fazendo Login com o Facebook
const facebookLogin = async () => {
  try {
    const data = await AccessToken.getCurrentAccessToken();

    if (!data) {
      throw new Error('Algo deu errado!');
    }

    const credential = firebase
      .auth
      .FacebookAuthProvider
      .credential(data.accessToken);

    const currentUser = await firebase
      .auth()
      .signInAndRetrieveDataWithCredential(credential);

    console.tron.log(currentUser.user.toJSON())
  } catch (e) {
    console.tron.error(e);
  }
}
```

------

### [Cloud Messaging](https://firebase.google.com/products/cloud-messaging/)

O **Firebase Cloud Messaging (FCM)** oferece o envio de **mensagens** e **notificações** **gratuitamente** para usuários de várias plataformas, seja Android, iOS ou na Web. As mensagens podem ser enviadas para dispositivos únicos, grupos de dispositivos, segmentos de usuários ou tópicos específicos.

```js
// Aguardando mensagens do FCM
componentDidMount() {
  this.messageListener = firebase.messaging()
    .onMessage(message => {
      // Aqui você processa a mensagem recebida!
    });
}

componentWillUnmount() {
  this.messageListener();
}
```

------

### [Storage](https://firebase.google.com/products/storage/)

O **Firebase Cloud Storage** permite que você **armazene** e **compartilhe** facilmente imagens, áudio, vídeo ou outro conteúdo gerado pelos usuários usando um armazenamento de objetos poderoso, simples e econômico criado para a escala do Google.

Os **SDKs** do **Firebase** para Cloud Storage adicionam a **segurança** do Google aos **uploads** e **downloads** de arquivo dos seus aplicativos do Firebase, independentemente da qualidade da rede.

```js
// Fazendo Upload de um Arquivo no formato Blob
const file = ...; // Use um Blog ou arquivo da API
ref.put(file).then(function(snapshot) {
  console.log('Uploaded a blob or file!');
});

// Fazendo Upload de uma String
const message = 'Essa é a mensagem.';
ref.putString(message).then(function(snapshot) {
  console.log('Uploaded a raw string!');
});
```

------

### [AdMob](https://firebase.google.com/docs/admob/)

A **AdMob do Google** é uma plataforma de **publicidade** que pode ser usada para **gerar receita** com sua aplicação. O uso da AdMob com o Google Analytics para **Firebase** fornece recursos adicionais de dados e recursos de análise de aplicativos.

------

A maioria dos serviços do **Firebase** é de uso gratuito, através do plano **Spark**, porém quando a aplicação atinge um nível de uso de recursos do servidor o plano é modificado.

Quando os planos não são mais gratuitos, as opções de planos pagos disponíveis são o **Flame** que tem uma quantidade maior de recursos que o **Spark** e o **Blaze** que é plano onde o pagamento é de acordo com a utilização de recursos, sendo bastante flexível.

Você pode ver mais sobre os planos e recursos de cada um [**nesse link**](https://firebase.google.com/pricing/).

## Vantagens x Desvantagens

Como qualquer outro produto, o **Firebase** tem suas vantagens e desvantagens, afinal, nenhum produto é perfeito para atender todo e qualquer tipo de situação, segue abaixo uma lista de **Vantagens** e **Desvantagens** dessa plataforma **BaaS**.

### Vantagens

- Estrutura Pronta;
- Rápida Implementação;
- Segurança;
- Múltiplas Ferramentas;
- Facilmente Escalável.

### Desvantagens

- Controle e Acesso;
- Limitação da Plataforma;
- Documentação;
- Performance;
- Pode fechar a qualquer momento.

## Afinal, quando devo usar o Firebase?

Se você já viu uma aplicação de um cliente ou colega/amigo programador ter que ser migrada totalmente para outra plataforma **BaaS** porque ela **fechou**, você provavelmente não vai querer voltar para uma plataforma desse tipo.

Entretanto, as **BaaS** não só tem mercado, como também são muito úteis, por isso seguem 3 situações onde o uso do **Firebase** é ótimo:

1. **MVP** - Quando você precisa criar um produto mínimo viável o Firebase se encaixa muito bem, pois é possível focar no desenvolvimento do **front-end** e/ou **mobile**, isso torna o processo mais **rápido**, **simples** e **barato** do que criar todo o back-end. Além de ser possível fazer muito mais testes antes de migrar para um back-end próprio;
2. **Pequenas Aplicações/Aplicações Pessoais**: Sabe aquele projeto que você tem a **ideia** e a **vontade** de fazer mas quase nunca consegue tempo para desenvolver o back-end (ou até não tem essa skill)? Pois é, o **Firebase** com certeza é para você;
3. **Protótipos**: Quando você precisa criar uma aplicação demonstração, ou um projeto para faculdade ou então apenas para testar as requisições de um App não é necessário criar todo o back-end, você pode usar o **Firebase**, agilizando esse processo.

Mas é claro que nada impede que você use em outros tipos de aplicação, as citadas acima são apenas as que depois de testes foram as que mostraram mais vantagens com o uso do **Firebase**.

Caso você tenha conforto e produtividade em desenvolver aplicações usando o **Firebase**, não hesite em usá-lo.

## Integrações

E para utilizar esses recursos citados durante o artigo tem que haver alguma **lib** para criar a ponte entre o **Firebase** e sua aplicação, e pensando nisso a equipe do Firebase criou **SDK's** para as plataformas **Web**, **IOS**, **Android** e demais plataformas.

Abaixo serão listadas alternativas para utilização do **Firebase** em aplicações **ReactJS**, **React Native** e **NodeJS**, afinal essa é a **stack** da **Rocketseat** =)

### Firebase no ReactJS

No **ReactJS** o SDK a ser usado é o **SDK Javascript**, pois o **ReactJS** atua do lado do cliente (browser) e com o SDK Javascript a aplicação consegue enviar as requisições através das funções pré-definidas do SDK para o **Firebase**.

Abaixo segue um link com um **tutorial** da documentação do **Firebase** de como você pode instalar e utilizar o **SDK Javascript** na sua aplicação:

https://firebase.google.com/docs/web/setup

### Firebase no React Native

Já para o **React Native** não há um SDK próprio para uso, o que muitos fazem é utilizar o **SDK Javascript** no React Native, afinal ambos tem por trás a linguagem **Javascript**.

Entretanto, há uma lib que fez um ótimo trabalho em reunir os **SDK's nativos** do **Android** e **IOS** e criar uma ponte entre eles e o **React Native**, ou seja, há uma maneira de se utilizar os pacotes próprios para Android e IOS no React Native, essa lib é o **React Native Firebase** (RNFirebase):

https://rnfirebase.io/docs/v5.x.x/getting-started

No começo pode parecer muito complexo para configurá-la em um projeto React Native, porém a **documentação** da lib é bem **detalhada** nesse ponto, e uma vez com tudo configurado você tem acesso à todos os serviços oferecidos pelo Firebase, como você pode ver em:

https://rnfirebase.io/docs/v5.x.x/getting-started#Supported-Firebase-Features

O SDK Javascript funciona no React Native, porém não é o ideal, pois ele é feito com foco em aplicações Web, portanto não tem acesso à todos os serviços oferecidos pelo Firebase, além de ficar para trás, mesmo que pouco, em testes de performance para o RNFirebase.

### Firebase no NodeJS

Nessa situação **não** faz muito sentido o uso do **Firebase**, visto que o **NodeJS** por sua vez é usado para criação do back-end de uma aplicação, que é justamente o que o **Firebase** oferece.

Não é impossível utilizá-lo no **NodeJS**, porém seria desperdício de performance pois o **NodeJS** atuaria como um **"middleware"** pro **Firebase**.

## The End

Nesse artigo foi explicado o que é, os serviços, as vantagens e desvantagens, quando usar e por fim as integrações do **Firebase**. O objetivo é que você saia com o pensamento bem definido sobre o funcionamento do **Firebase** e como ele pode ajudar no seu dia a dia como desenvolvedor.

E não esqueça de deixar um comentário aí em baixo sobre o que você achou desse post e também dessa ferramenta incrível que é o Firebase :)



### Marcadores

- [javascript](https://blog.rocketseat.com.br/tag/javascript/)
- [firebase](https://blog.rocketseat.com.br/tag/firebase/)

#### Inscreva-se para a nossa lista de email

Receba nossos artigos mais novos diretamente na sua caixa de entrada.

Seu email

Inscreva-se

#### [Claudio Orlandi](https://blog.rocketseat.com.br/author/claudio/)



### Recomendado para você

![img](https://blog.rocketseat.com.br/content/images/size/w600/2019/03/5_ferramentas_em_alta_para_desenvolvedores_React.png)

[Relay](https://blog.rocketseat.com.br/tag/relay/)[5 ferramentas em alta para desenvolvedores Reacthá 3 anos•5 min de leitura](https://blog.rocketseat.com.br/5-ferramentas-em-alta-react/)

![img](https://blog.rocketseat.com.br/content/images/size/w600/2018/12/ambiente-desenvolvimento-javascript.png)

[NodeJS](https://blog.rocketseat.com.br/tag/nodejs/)[Ambiente Javascript: Dicas, VSCode e terminalhá 4 anos•4 min de leitura](https://blog.rocketseat.com.br/ambiente-desenvolvimento-javascript/)

![img](https://blog.rocketseat.com.br/content/images/size/w600/2020/10/blog-rocketseat-upload-de-imagens-no-front-end-com-react-js-e-context-api.png)

[Front End](https://blog.rocketseat.com.br/tag/front-end/)[Upload de imagens no Front End com ReactJS e Context APIhá um ano•17 min de leitura](https://blog.rocketseat.com.br/upload-de-imagens-no-front-end-com-react-js-e-context-api-3/)



Blog da Rocketseat © 2022  •  Publicado com [Ghost](https://ghost.org/)

[Informações de licença JavaScript](https://blog.rocketseat.com.br/assets/html/javascript.html?v=56e866d21a)![img](https://blog.rocketseat.com.br/content/images/size/w1000/2019/03/Firebase-O-que-e--Quando-usar.png)

# Firebase: serviços, vantagens, quando utilizar e integrações

[javascript](https://blog.rocketseat.com.br/tag/javascript/)•25 de Dez de 2018



Você alguma vez já deve ter ouvido esse termo ou visto em algum lugar um comentário sobre ele. Mas afinal, o que é o **[Firebase](https://firebase.google.com/)**?

O **Firebase** é um **Baas** (Backend as a Service) para aplicações Web e Mobile do Google, foi lançado em 2004 e com o passar dos anos cresceu muito, se tornando uma ferramenta que hoje para alguns projetos é a melhor opção, devido a quantidade de serviços oferecidos por ele, além da facilidade de implementação.

![img](https://blog.rocketseat.com.br/content/images/2018/12/firebase-logo.png)

A criação de uma aplicação, seja ela Web ou Mobile, não é fácil, é preciso se preocupar com diversos fatores, dentre eles:

- Funcionamento em variados tipos de dispositivos;
- Infraestrutura;
- Atualizações que não gerem mais erros que solucionam;
- Segurança na transferência de dados;
- Mecanismos de Autenticação;
- E o aumento de usuários, para prover a melhor experiência para eles.

Foi pensando em uma maneira de solucionar todos esses problemas que surgiu a motivação para a criação do **Firebase**.

> Obs.: BaaS ou *BackEnd As A Service (MBaaS = Mobile BackEnd As A Service)* é um serviço disponibilizado em que toda a estrutura do *backend* como: configuração de servidor, integração com banco de dados, sistema de *push notification* e outros serviços, que fazem parte do *backend*, estão completamente prontos para se integrar com o seu aplicativo.

## Serviços Oferecidos

O Firebase oferece uma gama de serviços que podem ser utilizados, eles são separados por 4 **grandes** categorias, sendo elas **Analyics**, **Develop**, **Grow** e **Earn**.

![img](https://blog.rocketseat.com.br/content/images/2018/12/firebase-services.png)

Serão listados apenas os serviços mais usados, para que possa ser focado nas vantagens e integrações.

------

### [Analytics](https://firebase.google.com/products/analytics/)

O **Analytics** possibilita a **análise** em **tempo real** sobre o comportamento dos usuários nos seus Apps, além de disponibilizar dados sobre falhas, compras no aplicativo, desempenho de links diretos e muito mais.

Mas esse serviço atualmente tem suporte apenas para Android, IOS, C++ e Unity.

```js
// Analytics on React Native
componentDidMount() {
  Analytics.setAnalyticsCollectionEnabled(true);
  Analytics.setUserId(<userId>);
  Analytics.setUserProperty(<propKey1>, <propValue1>)
  Analytics.setUserProperty(<propKey2>, <propValue2>)
  Analytics.setCurrentScreen(<screenName>, <screenComponent>);
  Analytics.logEvent(<eventName>, {
    <paramKey1>: <paramValue1>,
    <paramKey2>: <paramValue2>
  });
}
```

------

### [Realtime Database](https://firebase.google.com/products/realtime-database/)

O **Banco de Dados em Tempo Real** permite o armazenamento e sincronismo dos dados entre usuários e dispositivos em tempo real com um banco de dados NoSQL hospedado na nuvem.

Os dados atualizados são **sincronizados** em **todos os dispositivos** conectados em segundos. Além disso, seus dados permanecem **disponíveis** caso seu aplicativo fique **off-line**, o que oferece uma ótima experiência do usuário, independentemente da conectividade de rede.

```js
// Gravando no Banco de Dados
writeUserData(email,fname,lname){
  firebase.database().ref('UsersList/').push({
    email,
    name,
  }).then((data)=>{
    console.tron.log('data ' , data)
  }).catch((error)=>{
    console.tron.log('error ' , error)
  })
}

// Lendo do Bando de Dados
readUserData() {
  firebase
    .database()
    .ref('Users/')
    .on('value', function (snapshot) {
      console.tron.log(snapshot.val())
    });
}
```

------

### [Authentication](https://firebase.google.com/products/auth/)

O **Firebase Auth** oferece diversos métodos de **autenticação**, como e-mail/senha, provedores de terceiros, como o Google ou Facebook, Login Anônimo, Confirmação via SMS, ou o uso direto do seu sistema de contas. O gerenciamento de usuários se torna simples e seguro.

```js
// Fazendo Login com o Facebook
const facebookLogin = async () => {
  try {
    const data = await AccessToken.getCurrentAccessToken();

    if (!data) {
      throw new Error('Algo deu errado!');
    }

    const credential = firebase
      .auth
      .FacebookAuthProvider
      .credential(data.accessToken);

    const currentUser = await firebase
      .auth()
      .signInAndRetrieveDataWithCredential(credential);

    console.tron.log(currentUser.user.toJSON())
  } catch (e) {
    console.tron.error(e);
  }
}
```

------

### [Cloud Messaging](https://firebase.google.com/products/cloud-messaging/)

O **Firebase Cloud Messaging (FCM)** oferece o envio de **mensagens** e **notificações** **gratuitamente** para usuários de várias plataformas, seja Android, iOS ou na Web. As mensagens podem ser enviadas para dispositivos únicos, grupos de dispositivos, segmentos de usuários ou tópicos específicos.

```js
// Aguardando mensagens do FCM
componentDidMount() {
  this.messageListener = firebase.messaging()
    .onMessage(message => {
      // Aqui você processa a mensagem recebida!
    });
}

componentWillUnmount() {
  this.messageListener();
}
```

------

### [Storage](https://firebase.google.com/products/storage/)

O **Firebase Cloud Storage** permite que você **armazene** e **compartilhe** facilmente imagens, áudio, vídeo ou outro conteúdo gerado pelos usuários usando um armazenamento de objetos poderoso, simples e econômico criado para a escala do Google.

Os **SDKs** do **Firebase** para Cloud Storage adicionam a **segurança** do Google aos **uploads** e **downloads** de arquivo dos seus aplicativos do Firebase, independentemente da qualidade da rede.

```js
// Fazendo Upload de um Arquivo no formato Blob
const file = ...; // Use um Blog ou arquivo da API
ref.put(file).then(function(snapshot) {
  console.log('Uploaded a blob or file!');
});

// Fazendo Upload de uma String
const message = 'Essa é a mensagem.';
ref.putString(message).then(function(snapshot) {
  console.log('Uploaded a raw string!');
});
```

------

### [AdMob](https://firebase.google.com/docs/admob/)

A **AdMob do Google** é uma plataforma de **publicidade** que pode ser usada para **gerar receita** com sua aplicação. O uso da AdMob com o Google Analytics para **Firebase** fornece recursos adicionais de dados e recursos de análise de aplicativos.

------

A maioria dos serviços do **Firebase** é de uso gratuito, através do plano **Spark**, porém quando a aplicação atinge um nível de uso de recursos do servidor o plano é modificado.

Quando os planos não são mais gratuitos, as opções de planos pagos disponíveis são o **Flame** que tem uma quantidade maior de recursos que o **Spark** e o **Blaze** que é plano onde o pagamento é de acordo com a utilização de recursos, sendo bastante flexível.

Você pode ver mais sobre os planos e recursos de cada um [**nesse link**](https://firebase.google.com/pricing/).

## Vantagens x Desvantagens

Como qualquer outro produto, o **Firebase** tem suas vantagens e desvantagens, afinal, nenhum produto é perfeito para atender todo e qualquer tipo de situação, segue abaixo uma lista de **Vantagens** e **Desvantagens** dessa plataforma **BaaS**.

### Vantagens

- Estrutura Pronta;
- Rápida Implementação;
- Segurança;
- Múltiplas Ferramentas;
- Facilmente Escalável.

### Desvantagens

- Controle e Acesso;
- Limitação da Plataforma;
- Documentação;
- Performance;
- Pode fechar a qualquer momento.

## Afinal, quando devo usar o Firebase?

Se você já viu uma aplicação de um cliente ou colega/amigo programador ter que ser migrada totalmente para outra plataforma **BaaS** porque ela **fechou**, você provavelmente não vai querer voltar para uma plataforma desse tipo.

Entretanto, as **BaaS** não só tem mercado, como também são muito úteis, por isso seguem 3 situações onde o uso do **Firebase** é ótimo:

1. **MVP** - Quando você precisa criar um produto mínimo viável o Firebase se encaixa muito bem, pois é possível focar no desenvolvimento do **front-end** e/ou **mobile**, isso torna o processo mais **rápido**, **simples** e **barato** do que criar todo o back-end. Além de ser possível fazer muito mais testes antes de migrar para um back-end próprio;
2. **Pequenas Aplicações/Aplicações Pessoais**: Sabe aquele projeto que você tem a **ideia** e a **vontade** de fazer mas quase nunca consegue tempo para desenvolver o back-end (ou até não tem essa skill)? Pois é, o **Firebase** com certeza é para você;
3. **Protótipos**: Quando você precisa criar uma aplicação demonstração, ou um projeto para faculdade ou então apenas para testar as requisições de um App não é necessário criar todo o back-end, você pode usar o **Firebase**, agilizando esse processo.

Mas é claro que nada impede que você use em outros tipos de aplicação, as citadas acima são apenas as que depois de testes foram as que mostraram mais vantagens com o uso do **Firebase**.

Caso você tenha conforto e produtividade em desenvolver aplicações usando o **Firebase**, não hesite em usá-lo.

## Integrações

E para utilizar esses recursos citados durante o artigo tem que haver alguma **lib** para criar a ponte entre o **Firebase** e sua aplicação, e pensando nisso a equipe do Firebase criou **SDK's** para as plataformas **Web**, **IOS**, **Android** e demais plataformas.

Abaixo serão listadas alternativas para utilização do **Firebase** em aplicações **ReactJS**, **React Native** e **NodeJS**, afinal essa é a **stack** da **Rocketseat** =)

### Firebase no ReactJS

No **ReactJS** o SDK a ser usado é o **SDK Javascript**, pois o **ReactJS** atua do lado do cliente (browser) e com o SDK Javascript a aplicação consegue enviar as requisições através das funções pré-definidas do SDK para o **Firebase**.

Abaixo segue um link com um **tutorial** da documentação do **Firebase** de como você pode instalar e utilizar o **SDK Javascript** na sua aplicação:

https://firebase.google.com/docs/web/setup

### Firebase no React Native

Já para o **React Native** não há um SDK próprio para uso, o que muitos fazem é utilizar o **SDK Javascript** no React Native, afinal ambos tem por trás a linguagem **Javascript**.

Entretanto, há uma lib que fez um ótimo trabalho em reunir os **SDK's nativos** do **Android** e **IOS** e criar uma ponte entre eles e o **React Native**, ou seja, há uma maneira de se utilizar os pacotes próprios para Android e IOS no React Native, essa lib é o **React Native Firebase** (RNFirebase):

https://rnfirebase.io/docs/v5.x.x/getting-started

No começo pode parecer muito complexo para configurá-la em um projeto React Native, porém a **documentação** da lib é bem **detalhada** nesse ponto, e uma vez com tudo configurado você tem acesso à todos os serviços oferecidos pelo Firebase, como você pode ver em:

https://rnfirebase.io/docs/v5.x.x/getting-started#Supported-Firebase-Features

O SDK Javascript funciona no React Native, porém não é o ideal, pois ele é feito com foco em aplicações Web, portanto não tem acesso à todos os serviços oferecidos pelo Firebase, além de ficar para trás, mesmo que pouco, em testes de performance para o RNFirebase.

### Firebase no NodeJS

Nessa situação **não** faz muito sentido o uso do **Firebase**, visto que o **NodeJS** por sua vez é usado para criação do back-end de uma aplicação, que é justamente o que o **Firebase** oferece.

Não é impossível utilizá-lo no **NodeJS**, porém seria desperdício de performance pois o **NodeJS** atuaria como um **"middleware"** pro **Firebase**.

## The End

Nesse artigo foi explicado o que é, os serviços, as vantagens e desvantagens, quando usar e por fim as integrações do **Firebase**. O objetivo é que você saia com o pensamento bem definido sobre o funcionamento do **Firebase** e como ele pode ajudar no seu dia a dia como desenvolvedor.

E não esqueça de deixar um comentário aí em baixo sobre o que você achou desse post e também dessa ferramenta incrível que é o Firebase :)



### Marcadores

- [javascript](https://blog.rocketseat.com.br/tag/javascript/)
- [firebase](https://blog.rocketseat.com.br/tag/firebase/)

#### Inscreva-se para a nossa lista de email

Receba nossos artigos mais novos diretamente na sua caixa de entrada.

Seu email

Inscreva-se

#### [Claudio Orlandi](https://blog.rocketseat.com.br/author/claudio/)



### Recomendado para você

![img](https://blog.rocketseat.com.br/content/images/size/w600/2019/03/5_ferramentas_em_alta_para_desenvolvedores_React.png)

[Relay](https://blog.rocketseat.com.br/tag/relay/)[5 ferramentas em alta para desenvolvedores Reacthá 3 anos•5 min de leitura](https://blog.rocketseat.com.br/5-ferramentas-em-alta-react/)

![img](https://blog.rocketseat.com.br/content/images/size/w600/2018/12/ambiente-desenvolvimento-javascript.png)

[NodeJS](https://blog.rocketseat.com.br/tag/nodejs/)[Ambiente Javascript: Dicas, VSCode e terminalhá 4 anos•4 min de leitura](https://blog.rocketseat.com.br/ambiente-desenvolvimento-javascript/)

![img](https://blog.rocketseat.com.br/content/images/size/w600/2020/10/blog-rocketseat-upload-de-imagens-no-front-end-com-react-js-e-context-api.png)

[Front End](https://blog.rocketseat.com.br/tag/front-end/)[Upload de imagens no Front End com ReactJS e Context APIhá um ano•17 min de leitura](https://blog.rocketseat.com.br/upload-de-imagens-no-front-end-com-react-js-e-context-api-3/)



Blog da Rocketseat © 2022  •  Publicado com [Ghost](https://ghost.org/)

[Informações de licença JavaScript](https://blog.rocketseat.com.br/assets/html/javascript.html?v=56e866d21a)