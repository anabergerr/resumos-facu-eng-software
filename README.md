# Revisando conceitos para a prova 04/03 a 09/03 📚



## Sobre Sistemas

- **Microsoft Windows**:
  - Lançado em 1993 pela Microsoft, o Windows veio para substituir as versões do DOS e os anteriores do Windows.
  - É amplamente utilizado em computadores pessoais e em ambientes corporativos.
  - Oferece uma interface gráfica amigável para os usuários interagirem com o hardware e os aplicativos.
  - Possui várias versões, como o Windows 10 e o Windows 11.
- **Unix:**
  - Unix é um sistema operacional criado nos anos 1960.
  - Foi desenvolvido originalmente no Bell Labs e é conhecido por sua robustez e escalabilidade.
  - É amplamente utilizado em servidores, estações de trabalho e sistemas embarcados.
  - Possui várias variantes, como o Linux e o macOS.
- **Linux:**
  - Criado por Linus Torvalds em 1991, o Linux é um sistema operacional de código aberto baseado no kernel do Unix.
  - É utilizado em servidores, desktops, dispositivos móveis e até mesmo em sistemas embarcados.
  - Oferece uma ampla variedade de distribuições, como o Ubuntu, Fedora e Debian.
- **Windows NT:**
  - O Windows NT é uma família de sistemas operacionais da Microsoft.
  - Foi lançado em meados dos anos 1990 e foi projetado para uso em servidores e estações de trabalho.
  - Oferece recursos avançados de segurança e gerenciamento.
  - Versões populares incluem o Windows NT 4.0 e o Windows 2000.



**Sistemas de tempo compartilhado (time-sharing):** O usuário tem a impressão de que o sistema está totalmente disponível para ele e os prazos são rígidos na execução das tarefas.
**Sistema batch:** Vários programas são executados a partir da divisão de tempo do processador.
**Sistema de tempo real:** O tempo é o principal parâmetro de funcionamento e não interagem com o usuário com a aplicação.



## Sobre Processos


- FIFO (First In, First Out). Nesse tipo de escalonamento, os processos são organizados em uma fila e executados na ordem em que chegaram. Cada processo recebe a chance de uso da CPU até que sua execução seja completada, enquanto os demais processos na fila de prontos permanecem esperando sua vez de serem executados. É importante notar que este tipo de escalonamento pode não ser o mais eficiente em termos de utilização da CPU, pois não leva em consideração a prioridade ou o tempo de execução dos processos.


- A denominação descrita é chamada de Exclusão mútua. Este é um princípio fundamental em sistemas operacionais que permite que apenas um processo acesse um recurso de cada vez. Se um recurso está sendo usado por um processo, todos os outros processos que desejam acessar esse recurso devem esperar até que o processo atual termine de usá-lo. Isso ajuda a evitar condições de corrida e outros problemas que podem surgir quando vários processos tentam acessar e modificar o mesmo recurso simultaneamente.

- Problemas de compartilhamento de recurso ocorrem em sistemas operacionais multiprogramáveis quando dois ou mais processos necessitam acessar um recurso comum simultaneamente. Se não for gerenciado corretamente, isso pode levar a condições de corrida, onde os resultados dependem da ordem relativa de execução dos processos. Por exemplo, se dois processos estão lendo e escrevendo em um arquivo compartilhado ao mesmo tempo sem qualquer tipo de coordenação, eles podem acabar sobrescrevendo as alterações uns dos outros, levando a dados inconsistentes ou corrompidos.
Portanto, é crucial que os sistemas operacionais implementem mecanismos para gerenciar o acesso a recursos compartilhados, como semáforos, monitores e bloqueios, para garantir que apenas um processo possa acessar um recurso de cada vez. Isso é conhecido como exclusão mútua. Além disso, os sistemas operacionais também precisam implementar estratégias para evitar condições como deadlock, onde dois ou mais processos estão esperando indefinidamente uns pelos outros para liberar recursos.


- A política de escalonamento preemptiva. Nesse tipo de escalonamento, o sistema operacional tem a capacidade de interromper a execução de um processo para permitir que outro processo seja executado. Isso é feito com base em critérios definidos pelo algoritmo de escalonamento, que pode levar em consideração prioridades, tempo de execução, entre outros fatores. A capacidade de preempção permite que o sistema operacional faça um uso mais eficiente do processador, garantindo que os processos não monopolizem a CPU por muito tempo e que os processos de alta prioridade sejam atendidos prontamente.




--------------

## Sobre arquivos e Sitemas Operacionais

### Conceito de tabela de descritores de arquivos abertos em sistemas operacionais.

Em sistemas operacionais que usam a tabela de descritores de arquivos abertos, essa é uma estrutura global que monitora todos os arquivos atualmente abertos no sistema, abrangendo não apenas aqueles de um sistema de arquivos específico.

Cada entrada na tabela de descritores de arquivos abertos contém um descritor de arquivo virtual, que é o identificador usado pelo processo para referenciar o arquivo, e um descritor de arquivo real, que é mantido pelo sistema operacional e contém informações reais do arquivo.

Assim, quando um processo executa operações de entrada/saída em um arquivo usando seu descritor de arquivo virtual, o sistema operacional o traduz para o descritor de arquivo real correspondente na tabela de descritores de arquivos. Essa tradução assegura que o processo não precise se preocupar com os detalhes internos de como os arquivos são gerenciados pelo sistema operacional.

As tabelas de descritores de arquivos podem variar entre diferentes sistemas operacionais e até mesmo entre diferentes implementações dentro de um mesmo sistema operacional. Além disso, os descritores virtuais de arquivos geralmente precisam de algum tipo de apontador para o descritor real do arquivo, para que o sistema operacional possa identificar e acessar corretamente as informações do arquivo associadas a esse descritor virtual.

O descritor virtual de arquivo serve como uma referência que o processo utiliza para identificar e manipular um arquivo, enquanto o descritor real contém as informações detalhadas sobre o arquivo, como a posição do cursor e as permissões de acesso. Portanto, é necessário haver algum tipo de mapeamento ou apontador entre o descritor virtual e o descritor real para garantir que as operações de E/S sejam realizadas corretamente pelo sistema operacional.


### Organizacao de arquivos 

- Relativa: Os registros são organizados de forma relativa à posição anterior, o que significa que os registros podem ser acessados através de deslocamentos em relação ao registro anterior.
- Analítica: Os registros são organizados em uma estrutura analítica que permite a realização de análises e consultas complexas, geralmente usando índices e estruturas de dados especiais.
- Volátil: Os registros são armazenados de forma volátil na memória RAM, o que significa que eles são perdidos quando o sistema é desligado ou reiniciado.
- Indexada: Os registros são organizados com base em índices que permitem um acesso rápido e eficiente aos dados, geralmente utilizando uma estrutura de árvore B ou outra estrutura de índice.
- Sequencial: Os registros são armazenados em sequência, um após o outro, sem qualquer estrutura adicional. O acesso aos registros é feito na ordem em que foram armazenados.


------------


Para realizar a leitura de um arquivo, é comum encontrar uma função ou chamada similar à READ(Handle, Var, NumBytes). A descrição de cada parâmetro:

- Handle: Um identificador único que o sistema operacional atribui ao abrir o arquivo. Esse identificador é usado para referenciar o arquivo que será lido.
- Var: Um ponteiro para o buffer de memória onde os dados lidos do arquivo serão armazenados.
- NumBytes: O número de bytes que devem ser lidos do arquivo.

Esses parâmetros são usados pelo sistema operacional para realizar a leitura do arquivo especificado.


### Responsabilidades de um Sistema Operacional

## 1. Gerenciamento de Recursos
- Alocação e controle de **memória**, **processador** e **dispositivos de entrada/saída**.
- Garantia de que todos os programas tenham acesso aos recursos necessários.

## 2. Controle de Arquivos e Diretórios
- Gerenciamento do armazenamento de dados no **disco rígido** ou em outros dispositivos.
- Facilitação da organização e acesso às informações armazenadas.

## 3. Interface com o Usuário
- Exibição de elementos gráficos na tela, como **ícones**, **janelas** e **menus**.
- Interpretação dos comandos digitados pelo usuário.

## 4. Execução de Programas
- Fornecimento de um ambiente de execução para **aplicativos**.
- Garantia de que os programas funcionem corretamente e de forma estável.

## 5. Segurança e Integridade dos Dados
- Controle de acesso aos **arquivos** e **recursos** do sistema.
- Proteção contra erros e falhas.

Em resumo, o sistema operacional é o intermediário entre o usuário e o hardware, proporcionando uma interface amigável e facilitando o uso e a operação do computador.

###  Tipos de Memória em um Sistema Computacional

## 1. Memória Principal (RAM)
- Também conhecida como **memória de acesso aleatório**.
- Armazena dados e instruções temporariamente enquanto o computador está ligado.
- A RAM é volátil, o que significa que os dados são perdidos quando o computador é desligado.
- Acesso rápido para processadores e programas em execução.

## 2. Memória Secundária (Disco Rígido, SSD)
- Armazena dados permanentemente, mesmo quando o computador é desligado.
- Exemplos incluem **discos rígidos (HDD)** e **unidades de estado sólido (SSD)**.
- Acesso mais lento em comparação com a RAM, mas capacidade de armazenamento muito maior.
- Utilizada para armazenar o sistema operacional, aplicativos e arquivos de usuário.

## 3. Memória Virtual
- Uma extensão da RAM que utiliza espaço no disco rígido como memória adicional.
- Quando a RAM está cheia, o sistema operacional move dados menos frequentemente usados para a memória virtual.
- Isso permite que o computador execute mais programas simultaneamente, mas com desempenho mais lento.

Em resumo, a **memória principal** é rápida e volátil, a **memória secundária** é permanente e de alta capacidade, e a **memória virtual** é uma extensão usada quando a RAM está sobrecarregada.



