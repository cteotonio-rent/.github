## Motorcycle rent project 👋

## Solicitação
[Aqui está da solicitação](https://github.com/cteotonio-rent/documentacao/blob/main/src/RequisitosDoProjeto.pdf)
.

## Arquitetura da Solução
<img src="https://github.com/cteotonio-rent/documentacao/blob/main/src/Architecture%20Diagram.svg" />

### Arquitetura do Software
#### Hexagonal Architecture Style
A ideia geral por trás do estilo de arquitetura hexagonal é que as dependências (adaptadores) exigidas pelo software para executar são usadas atrás de uma interface (porta).
O software é dividido em Aplicação e Infraestrutura em que os adaptadores são componentes intercambiáveis desenvolvidos e testados isoladamente. O aplicativo é fracamente acoplado aos adaptadores e seus detalhes de implementação.

#### Onion Architecture Style
Muito semelhante a Portas e Adaptadores, eu acrescentaria que os objetos de dados cruzam fronteiras como estruturas de dados simples. Por exemplo, quando o controlador executa um caso de uso, ele passa uma mensagem de entrada imutável. Quando os casos de uso chamam um Presenter, ele fornece uma mensagem de Saída (Objetos de Transferência de Dados, se desejar).

#### Clean Architecture Style
O estilo Clean Architecture se concentra em uma implementação fracamente acoplada de casos de uso e é resumido como:
1) É um estilo de arquitetura que os Casos de Uso são a estrutura organizadora central.
2) Segue o padrão Portas e adaptadores.
3) A implementação é guiada por testes (TDD Outside-In).
4) Desacoplado de detalhes tecnológicos.
5) Segue muitos princípios (Princípio das Abstrações Estáveis, Princípio das Dependências Estáveis, SOLID e assim por diante).


### Design Patterns
#### Controller
Os controladores recebem Solicitações, compilam a mensagem de Entrada e chamam o Caso de Uso, você deve notar que o controlador não cria a Resposta, em vez disso, essa responsabilidade é delegada ao objeto do apresentador.

#### ViewModel
ViewModels (Neste projeto são as Response Objects) são objetos de transferência de dados, eles serão renderizados pela estrutura MVC, então precisamos seguir as diretrizes da estrutura.

#### Unit of Work
Classe destinada a realizar o commit das modificações realizadas nas entidades.

### Domain-Driven Design Patterns
#### Entity
Objetos e mutáveis identificados por seus IDs.

#### Repository
Fornece recursos de persistência.

#### Use Case
É o ponto de entrada do aplicativo para uma interação do usuário. Ele aceita uma mensagem de entrada, executa o algoritmo, em seguida, ele deve dar a mensagem de saída para a porta de saída.

#### Camadas
<img src="https://github.com/cteotonio-rent/documentacao/blob/main/src/Arquitetura%20do%20Software.svg" />
- **Communication**: Contém os ViewsModels (Objetos de Requests e Responses)  
- **Exceptions**: Contém as classes de exceções do projetos, além de um recurso para que o projeto suporte multiplos idiomas  
<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->
