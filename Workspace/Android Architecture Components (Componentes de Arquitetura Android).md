# Android Architecture Components (Componentes de Arquitetura Android)

[![Paulo Linhares](https://miro.medium.com/fit/c/96/96/1*AaAAUIhiI8QGC8Jz9ahnQg.png)](https://medium.com/@paulo_linhares?source=post_page-----6c6be539f47e-----------------------------------)

[Paulo Linhares](https://medium.com/@paulo_linhares?source=post_page-----6c6be539f47e-----------------------------------) - [Mar 23, 2018](https://medium.com/iterative/android-architecture-components-componentes-de-arquitetura-android-6c6be539f47e?source=post_page-----6c6be539f47e-----------------------------------) · 6 min read



<iframe src="https://cdn.embedly.com/widgets/media.html?src=https%3A%2F%2Fgiphy.com%2Fembed%2F1jDgjPIpH0mn6%2Ftwitter%2Fiframe&amp;url=https%3A%2F%2Fmedia.giphy.com%2Fmedia%2F1jDgjPIpH0mn6%2Fgiphy.gif&amp;image=https%3A%2F%2Fmedia.giphy.com%2Fmedia%2F1jDgjPIpH0mn6%2Fgiphy-downsized-large.gif&amp;key=a19fcc184b9711e1b4764040d3dc5c07&amp;type=text%2Fhtml&amp;schema=giphy" allowfullscreen="" frameborder="0" height="244" width="435" title="Dance Android GIF - Find &amp; Share on GIPHY" class="t u v sk aj" scrolling="auto" style="box-sizing: inherit; position: absolute; top: 0px; left: 0px; width: 680px; height: 381.424px;"></iframe>

Durante toda a história do desenvolvimento Android, o Google nunca nos deu sua opinião sobre qual o padrão de arquitetura de software deveríamos utilizar para construir aplicativos **Android**. Com isso, várias frentes de Design Patterns foram surgindo.— principalmente depois do êxodo dos Testes Automatizados. E entenda “surgindo” como não sendo novos Patterns criados em especial para **Android**, ou muito menos algo oficial e visto como padrão para esta plataforma. O que se viu foi muitas adaptações de outras plataformas e tecnologias para tentar mitigar o jeito **MVC** (Model View Controller) de se construir Aplicativos Android. Dentre estes Patterns, os que mais ganharam murmuro de sua utilização no **Android**, em ordem de volume de utilização, foram: **MVP** (Model View Presenter), **MVVM** (Model View ViewModel), **VIPER**(View Interactor Presenter Entity Routing) e **Riblets**.

# Mas por que não mais MVC ?

O ponto de partida, podemos dizer que, foi meramente acidental e intimamente ligado a Testes Automatizados/Integração. Mas três pontos tem maior relevância aqui: seu Aplicativo precisa ser ***testável\***; ser ***escalável\***; e por ultimo e mais complexo: precisa ser ***robusto\*** o suficiente para lidar com os infinitos cenários de uso mobile e singularidades da plataforma.

## #Testável

Nos últimos 2 anos se proliferou bastante o conceito de **Testes Automatizados** **| de integração**. E um aplicativo mobile arquitetado em **MVC**, torna essa prática um tanto que meio impossível. Isso ocorre por conta do alto acoplamento da lógica de negócio do seu APP com as APIs nativas da plataforma **Android**.

É principalmente esse problema que a implementação do **MVP** e do **MVVM** tentou solucionar no **Android**. E, diga-se de passagem, esses dois Patterns atenderam bem para este fim. O problema é que eles não são suficientes o bastante para lidar com as outras questões do meio mobile. Também vale ressaltar uma das maiores queixas dos desenvolvedores que passaram por experiências de uso com esses Patterns: *o volume de código da sua aplicação se torna infinitamente mais volumoso a ponto de comprometer sua manutenibilidade; e o caso do Callbacks Hell (Inferno de callbacks) — termo que ficou conhecido devido ao emaranhado de callbacks (listeners) que sua aplicação precisa adquirir ao se trabalhar com esses patterns — principalmente com* ***MVP\***. Ou seja, programação além do necessário, termo conhecido no mundo do desenvolvimento de software como [***Overengineering\***](https://en.wikipedia.org/wiki/Overengineering).

## #Escalável

Não dá para negar que o uso de **MVP** ou **MVVM** foi também pensando para tornar sua aplicação escalável, mas também não podemos afirmar que sim. O caso mais comum nesse cenário, foi a tentativa da implementação, no **Android**, do **VIPER**, um Pattern criado originalmente no eco-sistema **IOS**.

Talvez o **VIPER** tenha enchido os olhos de alguns desenvolvedores **Android** por se tratar de um pattern baseado em [**Clean Architecture**](https://8thlight.com/blog/uncle-bob/2012/08/13/the-clean-architecture.html), um conceito bem conciso de boas práticas em engenharia de software. Mas também não ganhou força no **Android** devido a semelhança entre esses dois Frameworks — Android e IOS — estarem apenas ligados pelo termo Mobile e quase nada mais.

Outra força de expressão nesse meio foi o caso da multinacional Uber, que baseado nos conceitos de Testes e Escalabilidade, tiveram que refatorar todo o Aplicativo Usuário da empresa. E por conta dessa inconsistência de um Pattern oficial e “estável”, resolveram criar o seu próprio: o **Riblets**. — Por ser algo relativamente novo, não há nenhum APP publicado, com excessão, é claro, do APP Uber Client. O que existem são apenas esboços no GitHub, e até tentativas de dedução de como esse Pattern devesse funcionar já que a Empresa Uber demorou para liberar informações técnicas mais detalhadas sobre o mesmo. Particularmente não acredito que vá ganhar força no desenvolvimento **Android**, exatamente por não se tratar de um Pattern pensado exclusivamente para o eco-sistema do Google. Pelo contrário, a Uber queria algo que pudesse ser utilizado nas duas principais plataformas dos APPs da empresa, **Android** e **IOS**. — *E arrisco dizer que não funcionou muito bem para a Uber, pois como usuário assíduo do APP deles, eu ainda vejo alguns mesmos bugs conhecidos da versão antiga, que ainda ocorrem pós refatoração para o Riblets, mas podemos dizer que pelo menos para a implementação do serviço Uber Pool funcionou bem, já que a empresa bateu muito nessa tecla sobre barreira na escalabilidade para novos serviços que vinham enfrentando com a Arquitetura antiga do APP*.

## #Robusto

Por último, e não a toa, o mais complexo dos temas envolvendo a construção de Aplicativos **Android**.

O Framework **Android** não chegou ao posto de maior Sistema Operacional Mobile utilizado no mundo a toa, ainda mais se observarmos o desafio de fazer isso acontecer em um cenário com uma infinidade de aparelhos, que vão de marcas de distribuidores totalmente distintas à tipos de devices totalmente heterogêneos: como automóveis, relógios, e até mesmo eletrônicos domésticos, com diferentes características de hardware e interface.

Só um sistema muito bem planejado e totalmente pensado em *escalabilidade* poderia ter chegado ao posto que chegou.

— *Um belo exemplo de escalabilidade no Android são as Support Library (Bibliotecas de suporte), que sempre estão permitindo— dependendo da vontade de seus engenheiros — que usuários com versões mais antigas do SO possam também usufruir de novas funcionalidades criadas em versões mais atuais do Android.*

> Esse modelo funciona tão bem no Android que o Google chegou a sugerir que seu projeto, mesmo que seja voltado apenas para as versões mais atuais do Android, seja desenvolvido utilizando as Bibliotecas de Suporte e não as nativas sempre que possível, pois além de se obter várias vantagens com isso, para você ter uma ideia, existem APIs de uso bem atuais no Android que foram criadas diretamente na API de Suporte e nem se quer existem na Nativa|junto ao sistema operacional. É o caso do **ViewPage** e **CardView**, etc.

Por isso, há um desafio enorme, de sua parte como desenvolvedor **Android**, em construir Aplicativos com o mesmo nível de robustez da plataforma. E isso requer que seu projeto enteja conceituado com um Padrão de Design que atenda não só suas necessidades particulares de regra de negócios, bem como leve — principalmente — em considerações as peculiaridades da plataforma **Android**.

# A reposta do Google

O Google mostrou que não passou despercebido a todo esse murmuro sobre Padrão de Design no **Android** e, mesmo que bem tardiamente — ou à seu tempo, dependendo do ponto de vista— , lançou o Pattern perfeito para as características do seu SO mobile: **Android Architecture Components (ARC).**

O **ARC** é o resultado da extração, de cada Pattern já utilizado no Android, dos pontos positivos desses Patterns e anulação dos erros já cometidos e, assim o Google conseguiu agregar o que temos de mais atual em desenvolvimento de software: conceitos relacionados a *programação reativa*; características e necessidades que os APPs demonstram possuir em seu desenvolvimento — como controle de *ciclo de vida* e recriação de Views — ; *modularidade* e sustentabilidade de seu código; experiência de usuário; um maior respeito/controle a questões que podem onerar o usuário em consumo de dados por banda — persistência de dados em containers de dados bem mais poderosos que simples Bundle’s — ; View’s bindable’s que respondem de forma direta à alterações de dados; e acima de tudo, unindo tudo isso à *singularidade* total do sistema **Android**.

> É importante frisar, que embora, estejamos a todo momento nos referindo ao **Android Architecture Components (ARC)** como uma implementação singular e isolada — assim como **MVP**, **MVVM**… — , estamos na verdade diante de um conjunto de APIs /Componentes que juntos ajudam formar todo o conceito por trás da ideia do Google, que podem ser usados de forma isolada ou, em conjunto para extrair todo o poder fornecido pela proposta.

Todas as APIs/Componentes do **ARC** podem ser encontradas dentro do pacote `**android.arch**`e, até o momento podemos considerar que existem cinco principais módulos que ajudam a formar essa arquitetura:

**Handling LyfeCicles**, **LiveData**, **ViewModel**, **Room** e ***Paging**.

A melhor forma de entrar em detalhe em cada um deles é com a mão na massa, e iremos deixar isso para nosso próximo post.

Então é isso galera, a ideia aqui era simular apenas um pouco do que conversaríamos numa roda de amigos a respeito desse momento que o Android vive, e por se tratar de um marco importante em sua história, não poderíamos ficar sem bater esse papo. Por isso convido a todos que puderem agregar de qualquer forma com mais informações, casos de uso, ou mesmo se discorda de algum ponto mencionado. Acho muito válido podermos trocar nossos pontos de vista sobre o assunto.

Num próximo post irei mostrar um projeto de exemplo completo implementado com ARC utilizando todos os módulos disponíveis.

Valeu e aguardo vocês nos comentários.