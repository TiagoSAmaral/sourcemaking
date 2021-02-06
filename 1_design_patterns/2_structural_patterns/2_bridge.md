# Bridge
## Intenção 
 Desacoplar uma abstração de sua implementação, para que as duas possam ser variar independetemente.

## Problema
O "Endurecimento das artérias de software" tem ocorrido devido ao uso de subclasses de uma classe abstrata base para fornecer implementações alternativas. Isso trava em tempo-de-execução o vínculo entre a interface e a implementação. A abstração e a implementação não podem ser independentemente extendidas ou compostas.

## Moticação

 Considere o domínio de "thread scheduling" (Agendador de Tarefa):
<img src="https://sourcemaking.com/files/v2/content/patterns/Bridge-2x.png" alt="drawing" width="500"/>

Estes são dois tipos de agendadores de tarefas e dois tipos de sistemas operacionais ou "plataformas". Dada essa abordagem de especialização, temos que definir uma classe para cada permutação dessas duas dimensões. E se adicionarmos uma nova plataforma (digamos... Java`s Vitual Machine), como será que nossa hieraquia irá parecer?
<img src="https://sourcemaking.com/files/v2/content/patterns/Bridge_-2x.png" alt="drawing" width="500"/>

 E se tivessemos 3 tipos de agendadores de tarefas, e quatro tipos de plataformas? E se tivessemos 5 tipos de agendadores de tarefas e dez tipos de plataformas? O número de classes que teremos que definir é o produto do número de esquemas de agendamento e o número de plataformas.

 (Agendadores X Plataformas = Classes)

 O padrão Bridge propõe a refatoração dessa hierarquia de herança exponencialmente explosiva em duas hierarquias ortogonal - um para abstrações independentes de plataforma e outra para implementações dependentes de plataforma.
<img src="https://sourcemaking.com/files/v2/content/patterns/Bridge__-2x.png" alt="drawing" width="500"/>

## Discussão

Decompor a interface e implementação dos componentes em uma hierarquia de classes ortogonal. A interface da classe contém um ponteiro para a implementação abstrata da classe. Esse ponteiro é inicializado com uma instância da implementação concreta da classe, mas todas as interações da interface da classe com a implementação é limitado pela abstração contida na implementação da classe base. O cliente interage com a interface da classe, e isso por sua vez "delega" todas as requisições para a implementação da classe.

## Estrutura

## Exemplo

## Check List

## Regras de Ouro
