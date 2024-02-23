# Resumo Aula 4 - Sistemas operacionais



## 🧠Gerenciamento de Memória
O gerenciamento de memória é o processo pelo qual o sistema operacional gerencia a memória principal do computador. Ele envolve o rastreamento de cada byte na memória e decidir qual processo receberá memória, quando e quanto.

- Tipos: Incluem alocação contígua, alocação particionada, paginação e segmentação.
- Características: Eficiência, proteção, compartilhamento e localidade.
- Virtualização: Permite que um sistema operacional use mais memória do que fisicamente disponível, usando o disco rígido para armazenar informações que normalmente estariam na RAM.

------
## 💽 Swapping
Swapping é uma técnica de gerenciamento de memória onde um processo pode ser trocado temporariamente para fora da memória principal (RAM) para o armazenamento secundário (geralmente um disco rígido) e depois trazido de volta para a memória principal quando necessário.

- Tipos: Swapping de processos inteiros, Swapping de páginas.
- Características: Libera a memória principal, permite a execução de mais processos do que a memória principal pode suportar.

-----------
## 🌐Memória Virtual
A memória virtual é uma técnica que permite a execução de processos que podem não estar completamente na memória. Isso é feito dividindo a memória em pequenos pedaços, chamados páginas ou segmentos.

- Paginação: Divide a memória em pequenas partes iguais chamadas páginas.
- Segmentação: Divide a memória em segmentos que correspondem às unidades lógicas do programa (como funções, arrays, etc.).
- Virtualização: Permite que um programa acesse mais memória do que fisicamente disponível.

--------------
## 🖥️Gerenciamento de Dispositivos de Entrada e Saída
O gerenciamento de dispositivos de entrada e saída é uma função do sistema operacional que controla todos os dispositivos de entrada e saída do sistema, como teclado, mouse, impressoras, discos, etc.

- Conceitos: Controladores de dispositivo, interrupções, buffers.
- Rotinas: Inicialização, leitura, escrita, controle.
- Tipos: Dispositivos de bloco, dispositivos de caractere.
- Características: Eficiência, escalabilidade, flexibilidade.
