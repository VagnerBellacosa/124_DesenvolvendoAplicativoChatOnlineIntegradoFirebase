- [Desenvolvedores Android](https://developer.android.com/?hl=pt-br) - Jetpack - Primeiros passos

# Guia para a arquitetura do app

Este guia aborda as [práticas e a arquitetura recomendadas](https://developer.android.com/jetpack/guide?hl=pt-br#recommended-app-arch) para a criação de apps robustos com alta qualidade de produção.

**Observação**:as informações nesta página pressupõem que você sabe o básico sobre o framework do Android. Se você não tem experiência com o desenvolvimento de apps Android, confira o guia [Noções básicas do Android](https://developer.android.com/courses/android-basics-kotlin/course?hl=pt-br) para começar e saber mais sobre os conceitos mencionados neste guia.

## Experiências dos usuários de apps para dispositivos móveis

Em geral, um app Android contém vários [componentes de app](https://developer.android.com/guide/components/fundamentals?hl=pt-br#components), incluindo [atividades](https://developer.android.com/guide/components/activities/intro-activities?hl=pt-br), [fragmentos](https://developer.android.com/guide/fragments?hl=pt-br), [serviços](https://developer.android.com/guide/components/services?hl=pt-br), [provedores de conteúdo](https://developer.android.com/guide/topics/providers/content-providers?hl=pt-br) e [broadcast receivers](https://developer.android.com/guide/components/broadcasts?hl=pt-br). A maioria desses componentes de app é declarada no [manifesto do app](https://developer.android.com/guide/topics/manifest/manifest-intro?hl=pt-br). O SO Android usa esse arquivo para decidir como integrar o app à experiência geral do usuário do dispositivo. Como um app Android comum pode conter vários componentes e os usuários geralmente interagem com vários apps em um curto período, os apps precisam se adaptar a diferentes tipos de fluxos de trabalho e tarefas direcionados ao usuário.

Lembre-se de que os recursos de dispositivos móveis são limitados, então o sistema operacional pode interromper alguns processos de apps a qualquer momento para dar espaço a outros novos.

Considerando as condições desse ambiente, é possível que os componentes do app sejam iniciados individualmente e fora de ordem, e eles podem ser destruídos a qualquer momento pelo usuário ou pelo sistema operacional. Como esses eventos não estão sob seu controle, não armazene nem mantenha na memória dados ou estados de apps para os componentes do seu app, e não permita que os componentes dele dependam uns dos outros.

## Princípios de arquitetura comuns

Se não é recomendável usar componentes do app para armazenar dados e estados, qual é a melhor forma de criar um app?

Conforme os apps para Android aumentam de tamanho, é importante definir uma arquitetura que permita o escalonamento, melhor robustez e facilite o teste do app.

Uma arquitetura de app define os limites entre as partes do app e as responsabilidades de cada uma. A fim de atender às necessidades mencionadas acima, crie a arquitetura do app para seguir alguns princípios específicos.

### Separação de conceitos

O princípio mais importante que precisa ser seguido é a [separação de conceitos](https://en.wikipedia.org/wiki/Separation_of_concerns) (link em inglês). É um erro comum escrever todo o código em uma [`Activity`](https://developer.android.com/reference/android/app/Activity?hl=pt-br) ou um [`Fragment`](https://developer.android.com/reference/android/app/Fragment?hl=pt-br). Essas classes baseadas em IU precisam conter apenas a lógica que processa as interações entre a IU e o sistema operacional. Ao manter essas classes o mais enxutas possível, você pode evitar muitos problemas relacionados ao ciclo de vida de componentes e melhorar a capacidade de teste dessas classes.

Lembre-se de que você não é proprietário de implementações da `Activity` e do `Fragment`. Na verdade, elas são apenas classes que representam o contrato entre o SO do Android e o app. O SO pode as destruir a qualquer momento com base nas interações do usuário ou devido a condições do sistema, como pouca memória. Para fornecer uma experiência do usuário satisfatória e uma experiência de manutenção de app mais gerenciável, o melhor é minimizar sua dependência dessas classes.

### IU do Drive com base em modelos de dados

Outro princípio importante é que você precisa basear sua IU em modelos de dados, de preferência, modelos persistentes. Os modelos de dados representam os dados de um app. Eles são independentes dos elementos da IU e outros componentes do app. Isso significa que eles não estão vinculados ao ciclo de vida do componente da IU e do app, mas ainda vão ser destruídos quando o SO decidir remover o processo do app da memória.

Os modelos persistentes são ideais por estes motivos:

- Seus usuários não perderão dados se o SO Android destruir o app para liberar recursos.
- O app continuará a funcionar caso uma conexão de rede esteja instável ou indisponível.

Se basear a arquitetura do app em classes de modelo de dados, você o torna mais testável e robusto.

## Arquitetura de app recomendada

Esta seção demonstra como estruturar o app seguindo as práticas recomendadas.

**Observação**: as recomendações e práticas recomendadas apresentadas nesta página podem ser aplicadas a vários tipos de apps para permitir o escalonamento, a melhoria da qualidade e a robustez, além de facilitar os testes. No entanto, trate-as como orientações e as adapte conforme necessário.

Considerando os princípios de arquitetura comuns mencionados na seção anterior, cada aplicativo precisa ter pelo menos duas camadas:

- A *camada de IU* que mostra os dados do aplicativo na tela.
- A *camada de dados* que contém a lógica de negócios do app e expõe os dados do aplicativo.

É possível adicionar uma camada extra conhecida como *camada de domínios* para simplificar e reutilizar as interações entre a IU e as camadas de dados.

![Em uma arquitetura de app típica, a camada de IU recebe os dados do aplicativo     da camada de dados ou da camada de domínios opcional, que fica entre     a camada de IU e a camada de dados.](https://developer.android.com/topic/libraries/architecture/images/mad-arch-overview.png?hl=pt-br)

**Figura 1**. Diagrama de uma arquitetura típica de app.

**Observação**: as setas nos diagramas deste guia representam as dependências entre classes. Por exemplo, a camada do domínio depende das classes de camada de dados.

### Camada de IU

A função da camada de IU (ou *camada de apresentação*) é exibir os dados do aplicativo na tela. Sempre que os dados mudam, seja devido à interação do usuário, como o pressionamento de um botão, ou a uma entrada externa, como uma resposta de rede, a IU é atualizada para refletir as mudanças.

A camada de IU é composta por dois itens:

- Elementos da IU que renderizam os dados na tela. Esses elementos são criados usando funções de visualizações ou do [Jetpack Compose](https://developer.android.com/jetpack/compose?hl=pt-br).
- Holders de estado, como classes [ViewModel](https://developer.android.com/topic/libraries/architecture/viewmodel?hl=pt-br), que armazenam dados, os expõem à IU e processam a lógica.

![Em uma arquitetura típica, os elementos da IU da camada de IU dependem dos holders     do estado, que, por sua vez, dependem de classes da camada de dados ou     da camada de domínios opcional.](https://developer.android.com/topic/libraries/architecture/images/mad-arch-overview-ui.png?hl=pt-br)

**Figura 2**. O papel da camada de IU na arquitetura do app.

Para saber mais sobre essa camada, consulte a [página sobre a camada de IU](https://developer.android.com/jetpack/guide/ui-layer?hl=pt-br).

### Camada de dados

A camada de dados de um app contém a *lógica de negócios*. A lógica de negócios é o que agrega valor ao app. Ela é composta por regras que determinam como o app cria, armazena e muda dados.

A camada de dados é composta por *repositórios* que podem conter de zero a muitas *fontes de dados*. Crie uma classe de repositório para cada tipo diferente de dados processados no app. Por exemplo, você pode criar uma classe `MoviesRepository` para dados relacionados a filmes ou uma classe `PaymentsRepository` para dados relacionados a pagamentos.

![Em uma arquitetura típica, os repositórios da camada de dados fornecem dados     ao restante do app e dependem das fontes de dados.](https://developer.android.com/topic/libraries/architecture/images/mad-arch-overview-data.png?hl=pt-br)

**Figura 3**. O papel da camada de dados na arquitetura do app.

As classes de repositório são responsáveis por estas tarefas:

- Expor os dados ao restante do app.
- Centralizar as mudanças para os dados.
- Resolver conflitos entre várias fontes de dados.
- Abstrair fontes de dados do restante do app.
- Conter uma lógica de negócios.

Cada classe de fonte de dados precisa ser responsável por trabalhar com apenas uma fonte, que pode ser um arquivo, uma rede ou um banco de dados local. As classes de fonte de dados são a ponte entre o aplicativo e o sistema para operações de dados.

Para saber mais sobre essa camada, consulte a [página sobre a camadas de dados](https://developer.android.com/jetpack/guide/data-layer?hl=pt-br).

### Camada de domínios

A camada de domínios é opcional e fica entre a IU e as camadas de dados.

A camada de domínios é responsável por encapsular a lógica de negócios complexa ou simples que é reutilizada por vários ViewModels. Essa camada é opcional, porque nem todos os apps vão ter esses requisitos. Use-a apenas quando necessário, por exemplo, para lidar com a complexidade ou favorecer a reutilização.

![Quando incluída, a camada de domínios opcional oferece dependências para     a camada da IU e depende da camada de dados.](https://developer.android.com/topic/libraries/architecture/images/mad-arch-overview-domain.png?hl=pt-br)

**Figura 4**. O papel da camada de domínios na arquitetura do app.

As classes nessa camada normalmente são chamadas de *casos de uso* ou *interagentes*. Cada caso de uso precisa ser responsável por uma *única* funcionalidade. Por exemplo, o app pode ter uma classe `GetTimeZoneUseCase` se vários ViewModels dependerem de fusos horários para mostrar a mensagem adequada na tela.

Para saber mais sobre essa camada, consulte a [página da camada de domínios](https://developer.android.com/jetpack/guide/domain-layer?hl=pt-br).

## Gerenciar dependências entre componentes

As classes no app dependem de outras para funcionar corretamente. É possível usar um dos padrões de design abaixo para reunir as dependências de uma classe específica:

- [Injeção de dependência (DI, na sigla em inglês)](https://developer.android.com/training/dependency-injection?hl=pt-br): permite que as classes definam as próprias dependências sem as construir. Durante a execução, outra classe é responsável por fornecer essas dependências.
- [Localizador de serviço (link em inglês)](https://en.wikipedia.org/wiki/Service_locator_pattern): esse padrão traz um registro de onde as classes podem buscar as próprias dependências em vez de as construir.

Esses padrões permitem dimensionar o código, porque fornecem padrões claros para gerenciar dependências sem duplicar o código ou elevar a complexidade dele. Além disso, permitem alternar rapidamente entre implementações de teste e de produção.

**Recomendamos seguir os padrões de injeção de dependência e usar a [biblioteca Hilt](https://developer.android.com/training/dependency-injection/hilt-android?hl=pt-br) em apps Android**. A biblioteca Hilt constrói os objetos automaticamente percorrendo a árvore de dependências, além de oferecer garantias de tempo de compilação nas dependências e criar contêineres de dependência para classes do framework do Android.

## Práticas recomendadas gerais

A programação é um campo criativo, e a criação de apps Android não é uma exceção. Há muitas maneiras de resolver um problema: é possível comunicar dados entre várias atividades ou fragmentos, extrair dados remotos e os armazenar localmente no modo off-line ou lidar com qualquer outro cenário comum que apps não triviais encontrem.

Embora as recomendações abaixo não sejam obrigatórias, na maioria dos casos a observação delas torna sua base de código mais robusta, testável e de fácil manutenção a longo prazo:

**Não armazene dados em componentes do app**.

Evite designar os pontos de entrada do app, como atividades, serviços e broadcast receivers, como fontes de dados. Em vez disso, eles precisam se coordenar com outros componentes apenas para extrair o subconjunto de dados relevante para esse ponto de entrada. Cada componente do app tem vida curta, dependendo da interação do usuário com o dispositivo e da integridade geral do sistema.

**Reduza as dependências nas classes do Android**.

Os componentes do app precisam ser as únicas classes que dependem das APIs do SDK do framework do Android, como [`Context`](https://developer.android.com/reference/android/content/Context?hl=pt-br) ou [`Toast`](https://developer.android.com/guide/topics/ui/notifiers/toasts?hl=pt-br). Abstrair outras classes delas no app melhora a capacidade de teste e reduz o [acoplamento](https://en.wikipedia.org/wiki/Coupling_(computer_programming)) no app.

**Crie limites de responsabilidade bem definidos entre os vários módulos do app**.

Por exemplo, não divulgue o código que carrega dados da rede em várias classes ou pacotes na sua base de código. Da mesma forma, não defina várias responsabilidades não relacionadas, como armazenamento de dados em cache e vinculação de dados, na mesma classe. Seguir a [arquitetura de apps recomendada](https://developer.android.com/jetpack/guide?hl=pt-br#recommended-app-arch) vai ajudar com isso.

**Exponha o mínimo possível de cada módulo**.

Por exemplo, não crie um atalho que exponha um detalhe de implementação interna de um módulo. Você pode economizar um pouco de tempo a curto prazo, mas provavelmente vai pagar caro por isso tecnicamente à medida que sua base do código progredir.

**Concentre-se no núcleo exclusivo do seu app para que ele se destaque de outros**.

Não reinvente a roda escrevendo o mesmo código boilerplate várias vezes. Em vez disso, concentre seu tempo e energia no que torna seu app único e deixe que as bibliotecas do Jetpack e outras bibliotecas recomendadas processem o boilerplate repetitivo.

**Considere como tornar cada parte do app testável de forma isolada**.

Por exemplo, ter uma API bem definida para buscar dados da rede facilita os testes do módulo que mantém esses dados em um banco de dados local. Se, em vez disso, você mesclar a lógica desses dois módulos em um só lugar ou distribuir o código de rede por toda a base de código, vai ser muito mais difícil, se não impossível, testá-los.

**Aplique o máximo de persistência possível em dados relevantes e atualizados**.

Dessa forma, os usuários podem aproveitar a funcionalidade do app mesmo quando o dispositivo estiver no modo off-line. Lembre-se de que nem todos os usuários têm conectividade constante e de alta velocidade e, mesmo se tiverem, eles podem ter sinal ruim em alguns lugares lotados.

## Exemplos

Os exemplos do Google abaixo demonstram uma boa arquitetura de apps. Acesse-os para ver a orientação na prática:

- [iosched](https://github.com/google/iosched) (em inglês), o app Google I/O
- [Sunflower](https://github.com/android/sunflower) (em inglês)
- [Trackr](https://github.com/android/trackr) (em inglês)
- [Jetnews](https://github.com/android/compose-samples/tree/main/JetNews) (em inglês), implementado com o Jetpack Compose.
- [Exemplos de arquitetura](https://github.com/android/architecture-samples) (link em inglês)

Isso foi útil?