# Desenvolvimento iOS: Conheça a linguagem Swift

## Este artigo mostra na teoria e na prática as melhorias que a linguagem Swift apresenta para os programadores iOS e qual a melhor forma de adquirir conhecimento na linguagem Swift.

- [Artigos](https://www.devmedia.com.br/artigos/)[Mobile](https://www.devmedia.com.br/artigos/mobile)Desenvolvimento iOS: Conheça a linguagem Swift

A **linguagem da Apple chamada Swift** está cada vez mais sendo utilizada. Muitos já estão criando ou modificando seus projetos e aprendendo as vantagens que a linguagem traz. Este artigo mostra na teoria e na prática as melhorias que Swift apresenta para os desenvolvedores, principalmente para aqueles que estão iniciando seus projetos iOS e qual a melhor forma de adquirir conhecimento na linguagem.

<iframe src="https://www.youtube.com/embed/aLDqoXJgN4U?rel=0&amp;showinfo=0" style="outline: none; -webkit-tap-highlight-color: transparent; max-width: 100%; margin: auto; height: 455.062px; width: 809px;"></iframe>

Relacionado: [Curso de IOS](https://www.devmedia.com.br/curso/curso-de-ios-introducao-ao-desenvolvimento-mobile/355)

A Apple divulgou na [WWDC](https://developer.apple.com/wwdc/) (Apple Worldwide Developers Conference) a sua **nova linguagem chamada Swift** deixando muitas pessoas surpresas e até aquele momento não ocorreu nenhum vazamento de informações por nenhum meio de comunicação, mesmo assim a linguagem estava há anos sendo desenvolvida em segredo.

Comparada com [Objective-C](https://www.devmedia.com.br/introducao-ao-objective-c/23061) que está há mais de 20 anos no mercado, **Swift traz facilidades e característica que a antiga linguagem da Apple não tem** como [Generics](https://www.devmedia.com.br/usando-generics-em-java/28981) e sintaxes mais simples onde com poucas linhas de código o programador consegue fazer mais coisas do que faria com Objective-C, lembrando linguagens de script como [Ruby](https://www.devmedia.com.br/introducao-ao-recursos-basicos-da-linguagem-ruby/31504) e [Python](https://www.devmedia.com.br/curso/curso-python/426), porém mantendo as chamadas dos métodos principais parecidas com Objective-C facilitando assim a migração de novos e antigos desenvolvedores.

O Rivest Cipher 4 é uma cifra de encriptação inventada em 1987 por Ron Rivest, um dos inventores do algoritmo de chave pública RSA e co-fundador da segurança RSA. Essa cifra de encriptação teve muito sucesso e graças a sua simplicidade e eficiência foi usada em vários protocolos populares como WEP , WPA, SSL ou TLS. Infelizmente, ela tem algumas fraquezas e não é mais usada nos protocolos modernos. O algoritmo RC4 gera uma chave pseudo-random que é usada para gerar o texto cifrado. Esta chave é chamada de pseudo-random porque gera uma sequência de números que se aproximam de propriedades randômicas, ou seja, parece aleatório mas não é já que todo output é o mesmo caso seja passado o mesmo input. A Apple implementou o RC4 nas linguagens Objective-C, Python e Swift e comparou a velocidade de execução de cada uma delas. **O estudo comparativo mostrou que a Swift é 220 vezes mais rápida que Python** e 93 vezes mais rápida que Objective-C.

Como se sabe até o momento, Objective-C traduz as chamadas dos métodos para uma outra chamada objc_msgSend. Ela é responsável por selecionar o que se quer enviar e o seu objeto, procurando exatamente pela parte do código que deveria supostamente tratar os eventos desse método através da tabela de métodos da classe. Felizmente, isto é extremamente rápido, porém as vezes faz muito mais do que o necessário. Quando se declara um objeto MyObject*, ele pode ser MyObject ou uma subclasse, pode ser uma instância de um tipo estático e até uma instância de uma classe completamente diferente. Dessa forma, pode-se mentir para o compilador sobre o tipo do objeto que se está enviando e mesmo assim seu código vai funcionar.

Considerando o código da **Listagem 1**, o compilador tem algumas garantias providas pela linguagem. Em Swift não se pode mentir para o compilador, o objeto precisa ser mais específico, se instanciarmos um objeto da classe MinhaClass ele pode ser tanto uma instância de MinhaClass como de MinhaSubclass, nada além disso. Em vez de usar objc_msgSend, o compilador do Swift emite um código que faz uma chamada em uma vtable, um array de funções e ponteiros que é acessado por um index:

```
chamadaMetodo = object->class.vtable[indexOfMetodo1]
chamadaMetodo()
class MinhaClass {
        func metodo1() { print("chamando metodo1") }
        @final func metodo2() { print("chamando metodo2") }
}

class MinhaSubClass: MinhaClass {
        override func metodo1() { print("chamando metodo1 subclass") }
}

func TestarClass(obj: MinhaClass) {
        obj.metodo1()
        obj.metodo2()
}
```

**Listagem 1**. Exemplo de classe em Objective-C

Essa forma é mais rápida que objc_msgSend, mesmo fazendo cache e transformando em código assembly, a performance é superior. Já o metodo 2 é diferente. O compilador não precisa gerar um código e procurar na vtable, ele sabe que nada pode sobrescrever esse método, então ele gera um nome hash para o método, vai diretamente na implementação da classe e faz a chamada normalmente utilizando o [hash](https://www.devmedia.com.br/como-funciona-a-criptografia-hash-em-java/31139).

O compilador também sabe quando o método não faz absolutamente nada, ou seja, ele não emite a chamada caso não tenha implementação dentro do seu corpo. Isso acontece também com todos os métodos mesmo aqueles que não são marcados como final. Por exemplo:

```
for i in 0..1000000 {

    obj.metodo2()
}
```

Nesse caso, o compilador quando percebe que o método não tem código implementado, ele pode eliminar completamente todo o loop fazendo com que nada seja executado.

### A alocação de memória foi aprimorada

A alocação de memória tornou-se mais eficiente para eliminar algumas alocações quando o objeto nunca é usado fora do local de escopo. O compilador pode alocar um objeto na stack onde o acesso é muito mais rápido, também pode optar por não alocar caso ele nunca seja usado:

```
for(int i = 0; i < 1000000; i++)

  [[[NSObject alloc] init] self
  ];
```

A alocação desse exemplo em Objective-C seria executada um milhão de vezes mandando milhares de mensagens para construir e destruir o objeto. Mas passando esse código para Swift com o novo compilador, ele não executaria nada se percebesse que self nunca é usado e é apenas referenciado dentro do loop podendo também retirar o código no processo de compilação.

### Swift é fácil de aprender

A linguagem é parecida com algumas linguagens como Ruby e Python mas não é só isso que a torna fácil e sim por que diferentemente da Objective-C, além de ter tipagem forte ela pode ser dinâmica, ou seja, você não precisa definir o tipo da variável, ele vai ser definido na primeira vez que a variável receber um valor.

Essa linguagem desenvolvida também pode se tornar mais uma opção para quem quiser aprender a usar o Cocoa framework. Sendo assim, ele consegue coexistir com Objective-C. Você pode criar classes Swift em seu projeto Objective-C e fazer a comunicação entre eles sem ter que passar completamente seu projeto para Swift. Esse framework contém funções que permitem os desenvolvedores desenhar imagens e textos na tela, respondendo a interação do usuário. Dessa forma, quando você ouvir que precisa ainda aprender Objective-C para fazer aplicações para IOS, a maioria quer dizer que você precisa aprender como se usa o framework Cocoa Touch e com Swift você tem mais uma maneira de começar a usar esse framework. Felizmente, para aprender essa linguagem você não precisa saber previamente Objective-C, por que **o Swift é tão flexível que pode se adaptar à sua maneira de programar**. Mas se você já programa em outra linguagem, a única dificuldade vai ser se adaptar aos novos padrões da sintaxe, por exemplo:

```
if let blogId = json[“blogs”]?[“blog”]?[0]:[“id”]?.number {
       println(“blog ID: \(blogId)”)
  }
```

Mas caso você já saiba Objective-C, será muito mais fácil pois a maior parte dos tutoriais encontrados na internet para atividades específicas como passar de uma tela para outra programaticamente, estão em Objective-C.

### Playground

Com o **lançamento da Swift, a Apple aprimorou sua ferramenta de desenvolvimento chamada de Xcode** adicionando uma parte Playground (ver **Figura 1**) onde o programador pode facilmente testar seu código sem precisar fazer o build ou compilar. Ele, além de mostrar o resultado imediatamente, mostra também os gráficos sobre a performance do código, neste caso há mais uma característica da linguagem que é a de poder ser interpretada. Poderá ser desenvolvida toda uma aplicação usando o Playground e testar protótipos com a finalidade de melhorar a implementação durante a fase de desenvolvimento do projeto.

![lançamento da Swift a Apple aprimorou sua ferramenta de desenvolvimento chamada de Xcode adicionando uma parte Playground]()**Figura 1**. Playground

### Características da linguagem Swift

Essa linguagem vem inovando de várias maneiras, mas temos uma bem peculiar ao criar constantes e variáveis. Por exemplo: ela permite criar variáveis com caracteres especiais incluindo o conteúdo delas, o que torna possível nomear uma variável ou constante com emoticons e outros caracteres. Além disso, traz vantagens tanto na forma de implementação como em padrões que Objective-C não apresenta. Falando em padrões, com Swift é possível implementar Generics, o que torna viável criar códigos mais flexíveis, como mostra o código da **Listagem 2**, sendo possível achar um valor dentro de qualquer array.

```
func findIndex<T>(array: [T], valueToFind: T) -> Int? {
      for (index, value) in enumerate(array) {
          if value == valueToFind {
              return index
          }
      }
      return nil
  }
```

**Listagem 2**. Exemplo de uso de Generics em Swift

Quanto mais o leitor se aprofunda no livro, mais códigos e sintaxes ele vai conhecendo e aprendendo. Outra novidade é o caso do switch. Agora seus cases podem receber um range que permite mais flexibilidade para o desenvolvedor implementar sua lógica, como demonstra o código da **Listagem 3**.

.

```
switch count {
    case 0:
      naturalCount = "no"
    case 1...3:
        naturalCount = "a few"
    case 4...9:
      naturalCount = "several"
    case 10...99:
      naturalCount = "tens of"
    case 100...999:
      naturalCount = "hundreds of"
    case 1000...999_999:
      naturalCount = "thousands of"
    default:
      naturalCount = "millions and millions of"
  }
```

**Listagem 3**. Exemplo de switch

Para uma visualização mais prática e melhor entendimento das próximas características, o algoritmo apresentado na **Listagem 4** mistura Loops, Ternary e Array. Seguindo o mesmo princípio aplicado em switches, o loop também aceita ranges. A Apple criou outros sinais para determinar como são tratados esses ranges, como vimos anteriormente o sinal aplicado foi “**…**” entre os números, mas existe também “**..<**” ou “**..>**”.

```
let words = ["The", "Swift", "Programming", "Language"]
  let loops = 100
  var singleWord:String?
  var defaultWord:String?
  var count = 0;
  var list:[String] = []
  for i in 0..<loops {
       singleWord = i % 2 == 0 ? defaultWord : nil
       defaultWord = singleWord ?? words[count]
       count = i % words.count
       if (singleWord != defaultWord) list += [defaultWord!]
       else list[0…total-1] = [singleWord!]
  }
  print(list)
```

**Listagem 4**. Exemplo de sinais para tratamento de ranges

### Pesquisa

Uma pesquisa foi realizada por meio do Facebook e enviada para comunidades de desenvolvimento com Swift com os seguintes objetivos: Qual o percentual de desenvolvedores que acreditam nessa nova linguagem da Apple, também qual o percentual de desenvolvedores que estão trabalhando em projetos que permitam o crescimento dessa comunidade e finalmente qual a experiência desses desenvolvedores com Objective-C.

Como resultado desta pesquisa foram obtidas 105 respostas. No gráfico da **Figura 2** temos como resultado o conhecimento dos desenvolvedores e quais as linguagens que eles já conhecem. A lista de linguagens não foi escolhida aleatoriamente, mas sim baseada na forma de programar, sintaxe, plataforma e o quanto essas linguagens se assemelham a Swift. Como podemos ver, [Android](https://www.devmedia.com.br/guia/android/34580), [JavaScript](https://www.devmedia.com.br/curso/curso-de-javascript-completo/388) e outras linguagens como [Java](https://www.devmedia.com.br/guia/linguagem-java/38169) e [PHP](https://www.devmedia.com.br/guias/php) ficaram nas primeiras colocações.

![Gráfico com a experiência profissional de desenvolvedores com Objective-C]()**Figura 2**. Experiência profissional

O gráfico da **Figura 3** refere-se ao resultado da experiência dos programadores com Objective-C, o que torna interessante essa pergunta é que ela está relacionada com o próximo resultado de forma que apenas com esses dois gráficos poderemos chegar a uma conclusão razoável da pesquisa. O gráfico mostrou que 58% dos desenvolvedores não tem experiência com Objective-C, 42% sabem algo da linguagem e apenas 7% deles usam essa linguagem há três anos ou mais.

![Resultado da experiência dos programadores com Objective-C]()**Figura 3**. Experiência Objective-C

Já o gráfico da **Figura 4** mostrou que 42% por cento dos **entrevistados acreditam que um dia Swift substituirá completamente Objective-C**. A maioria, ou seja, 52%, acredita que só o tempo pode revelar essa resposta com mais exatidão e apenas 6% respondeu que ela não vai substituir a antiga linguagem da Apple.

![42% por cento dos entrevistados acreditam que um dia Swift substituirá completamente Objective-C]()**Figura 4**. Swift projects

Apenas 21% dos entrevistados começaram algum projeto ou protótipo com Swift, enquanto que 79% não faz nenhuma aplicação da mesma, como mostra a **Figura 5**.

![Qual o futuro do Swift]()**Figura 5**. O futuro do Swift

Após análise dos gráficos, poderá se dizer que Swift ainda está dando seus primeiros passos para o seu crescimento dentro da comunidade. Há poucos exemplos na internet para os novos desenvolvedores conseguirem algo mais concreto e a linguagem junto com [Xcode](https://www.devmedia.com.br/desenvolvendo-em-swift-com-xcode-e-ios-8/32858) ainda estão em uma fase beta. Porém, para o Swift começar a realmente se expandir e chegar em um nível do qual os 52% de desenvolvedores esperam que ela chegue, é necessário que os 79% restantes dos desenvolvedores que ainda não começaram os seus projetos nessa linguagem comecem a criar protótipos e publicar artigos. Isso faria com que Swift chegasse ao nível de linguagem que essa comunidade precisa. Lembrando que Swift não foi desenvolvida para substituir a Objective-C, mas sim para complementá-la e dar mais uma opção de desenvolvimento para quem quer fazer algo para iOS.

### Soap bubbles

O desenvolvimento com Swift está apenas começando e ainda não existe a possibilidade de ser publicado nenhum aplicativo na loja da Apple. Porém, muitos desenvolvedores estão criando protótipos com o objetivo de aprimorar seus conhecimentos e gradativamente ampliar a gama de conhecimentos da comunidade. Deste modo, a partir de agora veremos a construção de um pequeno jogo que utiliza SpriteKit para criar as animações e movimentação dos objetos.

### SpriteKit com Swift

Para o desenvolvimento de jogos aplicando conceitos de física ou até mesmo para facilitar a implementação é preciso utilizar frameworks, caso contrário provavelmente você reinventaria a roda.

O SpriteKit é um framework que provê uma infraestrutura de renderização e animação gráfica onde cada frame é processado antes de renderizar. Seu trabalho é montar a animação de forma eficiente usando o hardware gráfico. SpriteKit é tão otimizado que as posições dos sprites podem mudar arbitrariamente em cada frame da animação sem que haja perda de performance. Para o desenvolvimento de jogos, o SpriteKit também provê outras funcionalidades como suporte para som e simulação física. Além disso, o Xcode tem suporte built-in que ajuda a criar efeitos especiais complexos e mapa de texturas.

A melhor maneira de aprender Sprite Kit é ver na prática. Porém, antes de construir algo usando Sprite Kit e Swift, vamos ver alguns exemplos de como esse framework pode ajudar na construção de games. Um exemplo disso é a criação de animações com sprite. É possível criar uma sequência de imagens e dinamicamente colocar um tempo para a exibição de cada imagem. Isto pode ser feito apenas com poucas linhas de código dependendo da quantidade de imagens a serem utilizadas. O código da **Listagem 5** cria uma textura contendo as figuras necessárias para fazer a sequência e adiciona uma ação de remoção após a finalização da animação.

```
let textureAtlas = SKTextureAtlas(named:"bubble.atlas")
  var animationList:Array = Array<SKTexture>();
  animationList.append(textureAtlas.textureNamed("ready_countdown"));
  animationList.append(textureAtlas.textureNamed("3_countdown"));
  animationList.append(textureAtlas.textureNamed("2_countdown"));
  animationList.append(textureAtlas.textureNamed("1_countdown"));
  animationList.append(textureAtlas.textureNamed("go_countdown"));
  let animateAction = SKAction.animateWithTextures(animationList, timePerFrame:1)
  let sequenceAction = SKAction.sequence([animateAction, SKAction.removeFromParent()])
```

**Listagem 5**. Exemplo de textura contendo figuras para fazer sequência de animação

### Iniciando o projeto

O objetivo principal do jogo é clicar nos números primos que sobem na tela e não deixar que o tempo acabe. Os balões errados diminuem os pontos e o tempo enquanto os certos fazem a ação contrária lhe dando mais tempo e pontos. Para criar seu projeto Swift é preciso ter o Xcode 6 beta instalado, depois, basta ir nas opções de novo projeto para gerar um projeto para iOS com as configurações mostradas nas **Figuras 6** e **7**.

![Criação de projeto no Swift]()**Figura 6**. Criação do projeto

![Configuração de projeto no Swift]()**Figura 7**. Configurações do projeto

A estrutura de classes do jogo é bem simples. Seria possível implementar tudo na classe **GameScene**, porém o entendimento seria bem mais complexo. A **Figura 8** mostra como o projeto está estruturado.

Basicamente, o jogo se resume à classe GameScene, que contém toda a mecânica principal do jogo utilizando os managers para o controle. É ela que apresenta os estados do jogo para o jogador. Ao contrário da classe GameViewController que apenas é necessária para criação da GameScene. As classes TimeManager, ScoreManager e BubbleManager controlam respectivamente o tempo, a pontuação e a criação e remoção das bolhas no cenário tornando o código implementado na GameScene muito mais limpo e objetivo. As classes managers são responsáveis por quase todo o funcionamento do jogo, deixando apenas para a GameScene o trabalho de intermediar a comunicação entre a tela de jogo e os inputs do jogador.

![Diagramação do projeto no Swift](https://arquivo.devmedia.com.br/revistas/mobile/imagens/63/4/image008.png)**Figura 8**. Diagrama do projeto

Após criar o projeto é preciso fazer uma modificação na classe GameViewController, gerada automaticamente pelo Xcode, para passar a responsabilidade da criação da tela do jogo para a classe GameScene (veja o código da **Listagem 6**). Nela vamos implementar a parte principal do jogo e essa modificação envolve **SpriteKit** para que seja criada a cena do jogo ao iniciar a aplicação, não sendo necessário alterar nenhuma propriedade do Main.storyboard.

O SpriteKit cria basicamente uma camada de canvas por cima do controller, onde é possível desenhar os objetos do jogo e movimentá-los de acordo com nossa necessidade. Podemos criar várias cenas dentro de um mesmo controller, mas para nosso jogo é preciso apenas uma. É importante lembrar que para fazer um jogo com Swift não é preciso utilizar esse framework, mas provavelmente a implementação irá ser bem mais complexa.

```
private var skView:SKView!
  private var scene:GameScene!

  override func viewWillLayoutSubviews() {

  skView = self.view as SKView
  skView.ignoresSiblingOrder = true

  scene = GameScene.sceneWithSize(skView.bounds.size) as GameScene
  scene.scaleMode = SKSceneScaleMode.AspectFill
  skView.presentScene(scene)
  }
```

**Listagem 6**. Criação da cena no GameViewController

Conforme a **Figura 8** a próxima classe a ser implementada é GameScene, a classe principal do jogo. Porém, ela contém todos os gerenciadores e por isso antes de mostrar a cena do jogo é preciso entender como as outras classes funcionam. O primeiro gerenciador é o TimeManager que determina se o jogo ainda está ativo ou já finalizou. Veja o código da **Listagem 7**.

A configuração do tempo e suas variáveis é feito no método init da linha 10 à 14 e as suas variáveis e constantes são declaradas antes dele nas linhas 2 a 8. Um dos métodos mais importantes chamado update é implementado da linha 16 à 21 e serve para recalcular constantemente o tempo corrente e total do jogo fornecendo para a cena as informações atualizadas através dos métodos getStartTime e getTime nas linhas 35 à 43. A função reset posicionada nas linhas 45 à 48 é chamada tanto na inicialização da classe quanto na reinicialização do jogo pela classe GameScene.

```
class TimeManager {
  static let START_GAME_INTERVAL:Float = 5
  static let UPDATE_TIME:Float = 1 / 60
  static let BONUS_TIME:Float = 4.5
  private var timeInterval:Float?
  private var totalTime:Float = 0
  private var startTime:Float = 0
  private var initTime:Float = 0

 init(total:Float, interval:Float) {
      initTime = total + START_GAME_INTERVAL
      timeInterval = interval
      reset()
 }

 func update() {
      startTime = startTime > 0 ? startTime - UPDATE_TIME : 0
      if (isStarted()) {
            totalTime = totalTime > 0 ? totalTime - UPDATE_TIME : 0
      }
 }

 func addTime() {
      totalTime += BONUS_TIME
 }

 func isOver() -> Bool {
      return totalTime == 0
 }

 func isStarted() -> Bool {
      return startTime <= 1
 }

 func getStartTime() -> String {
      var formatter : NSString = NSString(format: "%.01f", startTime)
      return formatter.description
 }

 func getTime() -> String {
      var formatter : NSString = NSString(format: "%.01f", totalTime)
      return formatter.description
 }

 func reset() {
      totalTime = initTime
      startTime = START_GAME_INTERVAL
 }
}
```

**Listagem 7**. Classe de gerenciamento de tempo

As classes podem ter seu construtor manualmente implementado apenas sobrescrevendo o método init(). Não é obrigatório implementar esse método e caso necessário, ele funciona como em outras linguagens orientadas a objetos atuais. As classes e estruturas podem ter vários construtores mas apenas classes podem ter o desconstrutor (deinit()) que é chamado quando o objeto é removido da memória.

Um bom jogo deve conseguir manipular a pontuação do jogador de forma objetiva. A complexidade da mesma depende da necessidade do jogo e por isso a classe ScoreManager foi implementada da forma mais simples possível, como demonstra o código da **Listagem 8**.

```
class ScoreManager {
  static let SCORE_POINT:Int = 10
  static let SCORE_LOST:Int = 50
  private var score:Int = 0

  func addPoint() {
  score += SCORE_POINT
  }

  func subPoint() {
  score -= SCORE_LOST
  if score < 0 {
  score = 0
  }
  }

  func getScore() -> String {
  return String(score)
  }

  func getIntScore() -> Int {
  return score
  }

  func reset() {
  score = 0
  }
  }
```

**Listagem 8**. Controlador da pontuação

Por último temos a classe que gerencia as bolhas. BubbleManager é responsável por criar e remover as bolhas da cena quando necessário. É o gerenciador mais complexo do jogo e também essencial para que o jogo funcione. Para construir a lista de bolhas com seus respectivos números o gerenciador usa o GameNumberUtil, responsável por gerar todos os números que são utilizados no jogo e apresentado na **Listagem 9**.

Os números usados no jogo quando usados não podem ser repetidos. O método getRandomNumber() funciona excluindo o número da lista e checa caso alguma lista esteja vazia gerando todos os números novamente.

Diferente do TimeManager e outras classes, o GameNumberUtil não implementa o método init. Suas [constantes e variáveis](https://www.devmedia.com.br/forum/duvida-sobre-variaveis-e-constantes/571288) inicializadas estão da linha 2 à 6. Já nas linhas 8 à 26 é implementado o método principal da classe chamado generateNumbers. Esse método preenche suas listas utilizando duas iterações, a primeira é baseada nas constantes de número mínimo e máximo declaradas no começo da classe e a segunda serve para checar se o número gerado é primo. O método getRandomNumber nas linhas 32 à 46 utiliza o generateNumbers caso as listas não tenham sido preenchidas e depois utilizando o método random, linhas 28 a 30, escolhe o número a ser retornado removendo-o de sua lista respectiva. O método reset nas linhas 52 à 54 é utilizado pela GameScene para recriar os números ao reiniciar o jogo.

```
class GameNumberUtil {
  static let MIN_NUMBER:Int = 2
  static let MAX_NUMBER:Int = 1000
  private var primeNumbers = [Int]();
  private var lastPrimeNumbers = [Int]();
  private var allNumbers = [Int]();

  private func generateNumbers() {
       primeNumbers = [Int]();
      allNumbers = [Int]();
      for var i = MIN_NUMBER; i < MAX_NUMBER; i++ {
            var isPrimeNumber = true
            for var j = 2; j < i; j++ {
                 if (i % j == 0) {
                      isPrimeNumber = false
                      break
                 }
            }
            if (isPrimeNumber) {
                 primeNumbers.append(i);
            }
            allNumbers.append(i);
      }

      lastPrimeNumbers = primeNumbers
 }

 private func random(total:Int) -> Int {
      return Int(arc4random_uniform(UInt32(total)))
 }

 func getRandomNumber() -> Int {
      if (allNumbers.count == 0 || primeNumbers.count == 0) {
            generateNumbers()
      }
      var index = random(allNumbers.count)
      var number = allNumbers[index]
      if random(primeNumbers.count) % 3 == 0 {
            index = random(primeNumbers.count)
            number = primeNumbers[index]
            primeNumbers.removeAtIndex(index)
      } else {
            allNumbers.removeAtIndex(index)
      }
      return number
 }

 func isPrime(number:String) -> Bool {
      return lastPrimeNumbers.filter { $0 == number.toInt() }.count > 0
 }

 func reset() {
      generateNumbers()
 }
}
```

**Listagem 9**. Gerador de números e gerenciador da lista de números

A classe GameNumberUtil utiliza três listas para armazenar os números gerados separando os números primos dos restantes. Porém a utilização das duas listas que contém os primos é diferente. A lista principal primeNumbers mantém apenas os números não utilizados nas bolhas enquanto lastPrimeNumbers permanece com todos os números primos gerados, essa lista também é utilizada na checagem dos números selecionados pelo player durante o jogo. O método isPrime() verifica se existe um número dentro da lista.

Os objetos das bolhas precisam ser criados para que o jogo tenha sentido. Esse método cria vários objetos e os junta em um node. Esse node pode servir como layer ou simplesmente podemos chama-lo de agrupador de objetos. Caso o node seja deletado, todos os seus filhos ou objetos agrupados irão ser excluídos também. A bolha é composta por três objetos: o background, o texto e uma imagem transparente, que podemos chamá-la de bubblehit. Veja o código da **Listagem 10**.

A classe BubbleManager segue o mesmo padrão das outras classes até agora, as suas variáveis e constantes são declaradas nas primeiras linhas, nesse caso da 3 à 11. Ela contém o construtor init da linha 17 à 38. Ele recebe o parâmetro bounds:CGPoint para determinar os limites de criação e remoção das bolhas. A animação da explosão da bolha também é criada nas linhas 24 a 37 do construtor, já o método principal da classe chamado createBubble é implementado na linha 40 a 57 utilizando para criar o label da bolha o método createNumber na linha 59 a 65.

```
class BubbleManager {

  static let BUBBLE_EXPLOSION_FRAME_TIME : NSTimeInterval = 0.1
  static let FONT_NAME:String = "System"
  static let FONT_SIZE:CGFloat = 12.5
  static let BUBBLE_FONT_SIZE:Float = 25
  let bubbleTextureAtlas = SKTextureAtlas(named: "bubble")
  private var explodeAction : SKAction?
  private var gameNumbers:GameNumberUtil = GameNumberUtil()
 private var bubbleList:NSMutableArray = NSMutableArray()
 private var bubbleBounds:CGPoint?

 func reset() {
      gameNumbers.reset()
 }

 init(bounds:CGPoint) {
      bubbleBounds = bounds
      /*
      * Criação da animação de explosão da bolha.
      * NOTA: Todas as imagens usadas no jogo estão na pasta bubble.atlas
      * e todos os SKTextureAtlas fazem referencia a pasta.
      */
      var bubbleExploreArray:Array = Array<SKTexture>();
bubbleExploreArray.append(bubbleTextureAtlas.textureNamed("bubble_explode1"));
                 bubbleExploreArray.append(bubbleTextureAtlas.textureNamed("bubble_explode2"));
   bubbleExploreArray.append(bubbleTextureAtlas.textureNamed("bubble_explode3"));
   bubbleExploreArray.append(bubbleTextureAtlas.textureNamed("bubble_explode4"));
 let animateAction = SKAction.animateWithTextures(bubbleExploreArray,
 timePerFrame:BUBBLE_EXPLOSION_FRAME_TIME)
      /*
      * Sequência da animação.
      * NOTA: O desenvolvedor pode determinar qual ação vai ser executada
      * depois que a animação finalizar. No caso da explosão o objeto
      * vai ser removido automaticamente da tela.
      */
      let sequenceAction = SKAction.sequence([animateAction, SKAction.removeFromParent()])
      explodeAction = SKAction.repeatAction(sequenceAction, count: 1)
 }

 func createBubble(speed:NSTimeInterval) -> SKSpriteNode {
      var bubble:SKSpriteNode = SKSpriteNode(texture:bubbleTextureAtlas.textureNamed("bubble"))
      let minX = bubble.size.width
      let maxX = bubbleBounds!.x - bubble.size.width / 2
      let rangeX = maxX - minX
      let position:CGFloat = CGFloat(arc4random()) % CGFloat(rangeX) + CGFloat(minX)
      bubble.position = CGPointMake(position, -bubble.size.height * 1.5)
      var label:SKLabelNode = createNumber()
      bubble.addChild(label)
      let bubblehit = SKSpriteNode(texture: bubbleTextureAtlas.textureNamed("bubblehit"))
      bubblehit.name = label.text
      bubble.addChild(bubblehit)
      let moveAction = SKAction.moveTo(CGPoint(x: position, y: bubbleBounds!.y), duration: speed)
      bubble.runAction(moveAction)
      bubbleList.addObject(bubble)

      return bubble
 }

 private func createNumber() -> SKLabelNode {
      var numberLabel:SKLabelNode = SKLabelNode(fontNamed:FONT_NAME)
      numberLabel.fontSize = CGFloat(BUBBLE_FONT_SIZE)
      numberLabel.text = gameNumbers.getRandomNumber().description
      numberLabel.position = CGPointMake(0, CGFloat(-BUBBLE_FONT_SIZE / 2))
      return numberLabel
 }
```

**Listagem 10**. Gerenciador de bolhas

O método checkTouch(), exposto na **Listagem 11**, é responsável por checar se o toque na tela foi em alguma bolha e retorna um score positivo ou negativo dependendo se a bolha tiver um número primário ou não. O objeto bubblehit é usado para detectar o toque no node, observando que touches é uma lista dos objetos da scene e que ele também inclui a própria scene, a detecção é feita comparando o nome do objeto com o nome da cena. Todas as bolhas têm o bubblehit com o atributo name igual ao texto do label.

O método update implementado nas linhas 1 à 18 é responsável por verificar se alguma bolha ultrapassou o limite superior e removê-la tanto da cena quanto da lista de bolhas. Assim como o update, o método destroyAllBubbles nas linhas 20 à 27 serve para remover as bolhas da cena, porém ele é chamado apenas quando o tempo do jogo acaba.

```
func checkTouch(scene:SKScene, touches: NSSet) -> Bool {
       var score:Bool = false
             for touch: AnyObject in touches {
             let location = touch.locationInNode(scene)
             let touchedNode = scene.nodeAtPoint(location)
             if (touchedNode.name != scene.name) {
                  score = gameNumbers.isPrime(touchedNode.name!)
                  let object = touchedNode.parent as SKSpriteNode
                  if score {
                      bubbleList.removeObject(object)
                      object.runAction(explodeAction)
                 } else {
                      object.texture = bubbleTextureAtlas.textureNamed("redbubble")
                 }
            }
      }
      return score
 }

 func update() {
      for bubble in bubbleList {
            if (bubble.position.y >= bubbleBounds!.y) {
                 bubble.removeFromParent()
                 bubbleList.removeObject(bubble)
            }
      }
 }

 // Método para remover todas as bolhas da tela
 func destroyAllBubbles() {
 for bubble in bubbleList {
      bubbleList.removeObject(bubble)
      bubble.runAction(explodeAction)
      }
 }
}
```

**Listagem 11**. Detectando o touch nas bolhas

No método createBubble(), a imagem bubblehit é usada dentro do node, ficando por cima do label e da imagem representativa da bolha. A função dessa imagem é garantir que qualquer lugar que o player toque no objeto bolha seja identificado independentemente de quantos objetos a bolha contenha dentro do node. Se tivéssemos apenas as imagens, background e label, teríamos que verificar se o toque foi feito no label ou no background e para isso é necessário definir nomes para os dois nodes.

### GameScene

A parte principal de nosso projeto é a **GameScene**, apresentada na **Listagem 12**. É nela que são adicionados todos os objetos e camadas, assim como labels, background e animações. Podem existir várias cenas dentro do jogo, cada uma pode ter uma funcionalidade específica como apresentar o menu principal ou mostrar lista das melhores pontuações. Porém, é recomendado que o desenvolvedor use os recursos e objetos padrões para criação da tela caso for fazer algo que ele consiga sem utilizar uma cena. No caso do Soap Bubbles, a cena principal também contém um pouco da lógica de interação do jogo.

```
class GameScene: SKScene {
  static let FONT_NAME:String = "System"
  static let DEFAULT_GAME_TIME:Float = 5
  static let START_GAME_INTERVAL_ANIMATION:NSTimeInterval = 1
  static let SCREEN_BORDER:CGFloat = 10
  static let BUBBLE_MOVIMENT_TIME:Float = 10
  static let BUBBLE_SPEED_MULTIPLIER:Float = 0.05
  static let MAX_BUBBLES_SPEED:Float = 2
  static let UPDATE_TIME:Float = 1 / 60
  static let BUBBLE_CREATE_TIME:Float = 1.1
  private var scoreLabel:SKLabelNode = SKLabelNode(fontNamed:FONT_NAME)
  private var timeLabel:SKLabelNode = SKLabelNode(fontNamed:FONT_NAME)
  private var bubbleCreateTime:Float = 0
  private var timeManager:TimeManager = TimeManager(total: DEFAULT_GAME_TIME, interval: 1)
  private var scoreManager:ScoreManager = ScoreManager()
  private var bubbleManager:BubbleManager?
  private var uiLayer : SKNode = SKNode()
  private var bubbleLayer : SKNode = SKNode()
  private var startAnimation:SKSpriteNode?
  private var overAnimation:SKSpriteNode?
  private var gameOver:Bool = false
  private var startAction:SKAction?
```

**Listagem 12**. Cena principal do jogo

A **Listagem 13** mostra como é feita a animação inicial da contagem regressiva. O **textureAtlas** contém um mapa de todas as imagens da pasta bubble.atlas, dessa forma pode retornar a textura de cada uma delas bastando apenas chamar a função textureNamed passando o nome da imagem.

O método didMoveToView nas linhas 29 a 54, é utilizado pelo framework do SpriteKit quando a view é criada e renderizada na tela, permitindo a utilização das configurações de tela para criar os labels e layers do jogo.

```
func createStartAnimation() {
  if (startAction == nil) {
       let textureAtlas = SKTextureAtlas(named:"bubble.atlas")
       startAnimation = SKSpriteNode(texture: textureAtlas.textureNamed("start_countdown"))
       overAnimation = SKSpriteNode(texture: textureAtlas.textureNamed("gameover_countdown"))
       var animationList:Array = Array<SKTexture>();
       animationList.append(textureAtlas.textureNamed("ready_countdown"));
       animationList.append(textureAtlas.textureNamed("3_countdown"));
       animationList.append(textureAtlas.textureNamed("2_countdown"));
      animationList.append(textureAtlas.textureNamed("1_countdown"));
      animationList.append(textureAtlas.textureNamed("go_countdown"));

      let animateAction = SKAction.animateWithTextures(animationList,
      timePerFrame:START_GAME_INTERVAL_ANIMATION)
      let sequenceAction = SKAction.sequence([animateAction, SKAction
      .removeFromParent()])
      startAction = SKAction.repeatAction(sequenceAction, count: 1)
      let position = CGPoint(x: self.frame.width / 2, y:self.frame.height / 2)
      startAnimation!.position = position
      overAnimation!.position = position
 }
 uiLayer.addChild(startAnimation!)
 startAnimation!.runAction(startAction)
}

/*
* A criação de todos os labels e objetos iniciais da tela
* é feita nesse método. Quando a tela aparecer os objetos já estarão
* criados e posicionados nela.
*/
override func didMoveToView(view: SKView) {
 bubbleManager = BubbleManager(bounds: CGPoint(x: self.frame.width, y: self.frame.height))
 scoreLabel.fontSize = FONT_SIZE
 scoreLabel.position = CGPoint(x:SCREEN_BORDER, y:FONT_SIZE)
 scoreLabel.horizontalAlignmentMode = SKLabelHorizontalAlignmentMode.Left
 scoreLabel.fontColor = SKColor.blackColor()
 timeLabel.fontSize = FONT_SIZE
 timeLabel.position = CGPoint(x:CGRectGetMidX(self.frame) + SCREEN_BORDER, y:FONT_SIZE)
 timeLabel.horizontalAlignmentMode = SKLabelHorizontalAlignmentMode.Left
 timeLabel.fontColor = SKColor.blackColor()
 // Configura o background da tela para branco
 self.backgroundColor = SKColor.whiteColor()
 /*
 * Configura a posição do layer que contém os labels
 * para ficar na frente de todos os outros layers.
 */
 uiLayer.zPosition = 1
 // Adiciona os layers na tela
 self.addChild(bubbleLayer)
 self.addChild(uiLayer)
 // Adiciona os labels no layer
 uiLayer.addChild(scoreLabel)
 uiLayer.addChild(timeLabel)
 // Cria e inicia a animação do começo do jogo
 createStartAnimation()
}
```

**Listagem 13**. Criando animação inicial

A cena possui o método touchesBegan() que pode ser sobrescrito, conforme o código da **Listagem 14**. No caso do jogo, a implementação está verificando se o score retorna positivo ou negativo. Caso o tempo do jogo já tenha zerado, o jogo é reiniciado ao detectar um novo toque na tela.

```
override func touchesBegan(touches: (NSSet!), withEvent event: (UIEvent!)) {
  if (!gameOver) {
  var score:Bool = bubbleManager!.checkTouch(self, touches: touches)
  if (score) {
  scoreManager.addPoint()
  timeManager.addTime()
  } else {
  scoreManager.subPoint()
  }
  } else {
  resetGame()
  }
  }
```

**Listagem 14**. Detectando toques na cena

Para aumentar a dificuldade do jogo, o método getBubbleMovimentSpeed() trabalha retornando dois resultados (vide **Listagem 15**). O primeiro resultado é a velocidade que a bolha se movimentará pela tela e o segundo é o tempo de criação das bolhas. Essa função é necessária para que sempre haja bolhas ocupando boa parte da tela mesmo com o aumento da velocidade, caso contrário elas passariam tão rápido que praticamente não haveria bolhas visíveis dentro da área de toque. Os dois resultados são inversamente proporcionais.

O método de update implementado da linha 7 à 34 controla todo fluxo do jogo inclusive a detecção do estado de gameover. Quando o tempo do jogo acaba, o método callGameOver, posicionado nas linhas 46 à 50, é chamado removendo toda a tela e colocando o jogo em estado de espera até o jogador tocar na tela. Nesse caso, o resetGame, linhas 37 à 44, é executado reiniciando o jogo por completo.

```
func getBubbleMovimentSpeed() -> (Float, NSTimeInterval) {
       let calSpeed = BUBBLE_MOVIMENT_TIME - Float(scoreManager.getIntScore()) *
       BUBBLE_SPEED_MULTIPLIER
       let speed = (calSpeed < MAX_BUBBLES_SPEED ? MAX_BUBBLES_SPEED : calSpeed)
       return (speed, NSTimeInterval(speed))
  }

  override func update(currentTime: CFTimeInterval) {
       if (!gameOver) {
             // Atualiza o tempo do jogo.
            timeManager.update()
            if (timeManager.isStarted()) {
                 // Atualiza as configurações das bolhas.
                 bubbleManager!.update()
                 // Mostra o tempo e score nos labels
                 timeLabel.text = "Time: " + timeManager.getTime()
                 scoreLabel.text = "Score: " + scoreManager.getScore()
                 // Verifica se o jogo ainda está ativo
                 if (!timeManager.isOver()) {
                      bubbleCreateTime += UPDATE_TIME
                      let speed = getBubbleMovimentSpeed()
                      if (bubbleCreateTime >= BUBBLE_CREATE_TIME - (speed.0 / 100)) {
                           bubbleCreateTime = 0
                      bubbleLayer.addChild(bubbleManager!.createBubble(speed.1))
                      }
                 /*
                 * Se o tempo acabou e a tela de game over ainda não
                 * foi chamada o jogo chama a animação final e remove
                 * todas as bolhas da tela.
                 */
                 } else if !gameOver {
                 callGameOver()
            }
      }
 }
 }

 func resetGame() {
      bubbleManager!.reset()
      scoreManager.reset()
      timeManager.reset()
      gameOver = false
      overAnimation?.removeFromParent()
      createStartAnimation()
 }

 func callGameOver() {
      gameOver = true
      uiLayer.addChild(overAnimation!)
      bubbleManager!.destroyAllBubbles()
 }
}
```

**Listagem 15**. Aumentando a velocidade das bolhas

O resultado obtido ao executar nosso jogo pode ser verificado na **Figura 9**.

![Telas de um jogo criado para Iphone com Swift]()**Figura 9**. Telas do jogo no simulador iPhone 5s

**O Swift abre uma grande oportunidade para os desenvolvedores iniciarem seus projetos na plataforma da Apple**. Mesmo estando em um crescimento inicial, cada vez mais os desenvolvedores vêm utilizando a linguagem para criação de seus projetos e protótipos pela facilidade que o código Swift traz.

A curva de aprendizado não é grande mesmo para aqueles que nunca mexeram com Objective-C e principalmente quem já entende das linguagens JavaScript, Ruby ou Python, podendo também utilizar o playground para testar e melhorar o código.

A Apple entendeu que para melhorar o ambiente do desenvolvedor não é preciso inutilizar o que ele passou anos aprendendo e praticando e sim agregar valor e flexibilidade no seu mundo. **Swift veio para ficar e foi feito para ser utilizado em conjunto com seu irmão mais velho Objective-C**. Dessa forma, a modificação e criação de novos softwares é mais facilmente implementada e explorada. Principalmente para o público em geral, **Swift vem sendo visto com bons olhos pelos desenvolvedores quanto por pessoas adeptas a Apple**. Não basta apenas agregar padrões, é preciso facilitar a vida dos programadores e abrir o leque de possibilidades para criatividade e isso Swift está conseguindo.

------

#### Links Úteis

- [JavaScript Replace: substituindo valores em uma string](https://www.devmedia.com.br/javascript-replace-substituindo-valores-em-uma-string/39176): Conheça o método replace() e aprenda a substituir uma sequência de caracteres por outra.
- [PostgreSQL: deixando seu banco de dados seguro e rápido](https://www.devmedia.com.br/postgresql-deixando-seu-banco-de-dados-seguro-e-rapido/39175): Este artigo traz uma abordagem prática, contextualizando problemas de performance e segurança, abordando soluções cotidianas que visam resolver os principais problemas durante a configuração do banco de dados.
- [Formulário de cadastro com Django e Bootstrap](https://www.devmedia.com.br/exemplo/formulario-de-cadastro-com-django-e-bootstrap/43): Aprenda neste exemplo como criar um formulário de cadastro em Django com Bootstrap.

------

#### Saiba mais sobre Mobile ;)

- [Guias Programação Mobile](https://www.devmedia.com.br/guias/mobile): Aumente seus conhecimentos nas tecnologias móveis. Aqui você encontra um Guia de estudo perfeito para cada ferramenta do mercado. Escolha o seu!
- [Guia de Android](https://www.devmedia.com.br/guia/android/34580): O Android é a plataforma oficial para desenvolvimento de aplicativos mobile do Google. Neste guia você encontrará artigos, vídeos e cursos para aprender tudo sobre esse SDK, que domina o mundo dos dispositivos móveis.
- [Cordova](https://www.devmedia.com.br/guia/cordova/38321): Neste Guia de Referência você encontrará o conteúdo que precisa para aprender a desenvolver aplicativos mobile multiplataforma utilizando o Cordova.

**Links**:

- [GitHub](https://github.com/ThiagoAmanajas/gg_math_b/) - Projeto inicial do Soap Bubbles
- [Swift](https://developer.apple.com/swift/) - Site oficial da linguagem
- [Secrets of Swift’s Speed](https://mikeash.com/pyblog/friday-qa-2014-07-04-secrets-of-swifts-speed.html) - by Mike Ash
- [Documentation](http://nshipster.com/swift-documentation/) - Como fazer comentários no código

Tecnologias:

- iOS
- Mobile
- Swift

https://www.devmedia.com.br/shop/)

![autor](https://www.devmedia.com.br/imagens/fotoscolunistas/389307_20141002175721.jpg)

Por [Thiago](https://www.devmedia.com.br/perfil/thiago-amanajas)Em 2014