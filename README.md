# 📘 Caderno Temático — Sistemas Operacionais com NotebookLM

> Projeto prático desenvolvido para o desafio da DIO sobre aprendizagem ativa com Inteligência Artificial, curadoria de fontes e engenharia de prompts.

## 🎯 Contexto e objetivos

Este projeto tem como tema **Sistemas Operacionais**, assunto estudado a partir dos materiais disponibilizados no curso e complementado por fontes abertas e documentação técnica.

O objetivo do caderno temático é transformar o conteúdo das aulas em um material de revisão mais organizado, usando o **NotebookLM como ferramenta de aprendizagem ativa**. Em vez de apenas pedir resumos, a proposta foi utilizar a IA para comparar conceitos, explicar assuntos em diferentes níveis de dificuldade, elaborar perguntas de revisão e identificar pontos que ainda precisavam de estudo.

### Objetivos de aprendizagem

- Entender o papel de um sistema operacional e os principais serviços que ele oferece.
- Diferenciar processos, threads e programas.
- Compreender, em nível introdutório, como funciona o gerenciamento da CPU e o escalonamento.
- Entender memória principal, memória virtual, paginação e processos.
- Compreender os conceitos básicos de arquivos, armazenamento e sistemas de arquivos.
- Entender a diferença entre **user mode** e **kernel mode**.
- Utilizar o NotebookLM para revisar, questionar e consolidar o conteúdo estudado.
- Desenvolver prompts mais específicos, verificáveis e úteis para estudo.

---

## 🧠 Ferramenta utilizada

**NotebookLM** — utilizado como ambiente de estudo e consulta às fontes selecionadas.

O princípio utilizado neste projeto foi tratar a IA como **ferramenta de apoio ao estudo**, e não como substituta das fontes. As respostas foram conferidas com o material disponibilizado no caderno sempre que possível.

---

## 📚 Curadoria de fontes

> **Importante:** os PDFs das aulas podem estar sujeitos a direitos autorais. Por isso, eles são usados como fontes dentro do NotebookLM, mas não precisam ser redistribuídos neste repositório público. Registre aqui os nomes exatos dos arquivos utilizados.

### Fontes das aulas

1. **[2-RevisaoSO.pdf]**
   - Tipo: PDF de aula
   - Uso: conceitos fundamentais de sistemas operacionais.

2. **[socm-texto-01.pdf]**
   - Tipo: PDF de aula
   - Uso: processos, threads e/ou gerenciamento da CPU.

3. **[socm-texto-15.pdf]**
   - Tipo: PDF de aula
   - Uso: memória, armazenamento, sistemas de arquivos e/ou outros tópicos abordados no curso.

### Fontes abertas complementares

4. **Operating Systems: Three Easy Pieces (OSTEP)**
   - Autores: Remzi H. Arpaci-Dusseau e Andrea C. Arpaci-Dusseau
   - Tipo: livro didático online de acesso aberto
   - Uso: aprofundamento dos fundamentos de virtualização, concorrência e persistência.
   - Link: https://pages.cs.wisc.edu/~remzi/OSTEP/

5. **Linux Kernel Documentation — Memory Management**
   - Instituição: Linux Kernel
   - Tipo: documentação técnica aberta
   - Uso: consulta sobre gerenciamento de memória e conceitos de memória virtual.
   - Link: https://docs.kernel.org/admin-guide/mm/

6. **Microsoft Learn — User Mode and Kernel Mode**
   - Instituição: Microsoft
   - Tipo: documentação técnica aberta
   - Uso: compreensão da separação entre user mode e kernel mode no Windows.
   - Link: https://learn.microsoft.com/en-us/windows-hardware/drivers/gettingstarted/user-mode-and-kernel-mode

> Para manter o desafio dentro da recomendação de **3 a 5 fontes**, selecione no NotebookLM as fontes que realmente serão utilizadas no projeto. Caso os três PDFs acima já sejam suficientes, mantenha os complementos como referências adicionais e destaque no README as 5 fontes principais que efetivamente sustentaram o estudo.

---

## 🛠️ Engenharia de prompts e experimentos

A principal mudança durante os testes foi perceber que prompts genéricos produzem respostas amplas demais para uma revisão acadêmica. Os melhores resultados vieram quando o prompt definia:

- o nível de conhecimento desejado;
- o formato da resposta;
- o que deveria ser comparado;
- a exigência de usar somente as fontes disponíveis;
- a necessidade de apontar incertezas ou conflitos entre fontes.

### Experimento 1 — Resumo inicial

**Prompt testado:**

> “Faça um resumo de Sistemas Operacionais com base nas fontes deste notebook.”

**Problema encontrado:** resposta muito ampla e pouco direcionada para revisão. Alguns tópicos ficaram misturados e o nível de profundidade não ficou claro.

**Ajuste realizado:** especificar os tópicos, o nível de linguagem e a estrutura desejada.

**Prompt melhorado:**

> “Com base exclusivamente nas fontes deste notebook, produza um resumo introdutório de Sistemas Operacionais para um estudante de nível universitário iniciante. Organize em: 1) função do sistema operacional, 2) processos e threads, 3) escalonamento de CPU, 4) gerenciamento de memória, 5) armazenamento e sistemas de arquivos e 6) user mode e kernel mode. Para cada tópico, explique o conceito, sua finalidade e dê um exemplo prático. Ao final, liste os pontos que merecem maior revisão.”

**Resultado obtido:**

> **### 1\. Função do Sistema Operacional

* **Conceito:** O **sistema operacional (SO)** é uma camada de software que atua diretamente entre o hardware do computador e os programas aplicativos do usuário final[1].
* **Finalidade:** Suas duas finalidades primordiais são a **abstração de recursos** (ocultar a complexidade do hardware criando interfaces de acesso simplificadas e padronizadas) e a **gerência de recursos** (definir políticas para alocar e compartilhar recursos de hardware finitos, como CPU e memória, de forma segura, justa e sem conflitos)[2].
* **Exemplo Prático:** Para ler dados gravados em um disco rígido, o programador utiliza a abstração de **arquivo** através de operações simples como `open`, `read` e `close`[6][7]. Sem o SO, o programador precisaria enviar comandos diretamente aos registradores e portas de entrada/saída do controlador físico do disco[6][7].

---

### 2\. Processos e Threads

* **Conceito:** Um **processo** é uma unidade de alocação de recursos que atua como um contêiner isolado, possuindo seu próprio espaço de endereçamento de memória, arquivos abertos e um descritor no núcleo chamado **PCB** (*Process Control Block*)[8]. Uma **thread** é um fluxo de execução independente mantido dentro de um processo, possuindo seu próprio contexto local (registradores e pilha de execução - TLS) e compartilhando a área de memória e os recursos do processo pai com as demais threads[11].
* **Finalidade:** O isolamento promovido pelos processos garante que falhas em um aplicativo não afetem a estabilidade dos demais[12]. Já as threads permitem que uma mesma aplicação realize múltiplas tarefas simultaneamente com menor consumo de memória e rápida troca de contexto[11].
* **Exemplo Prático:** Um **navegador web moderno** (como Chrome ou Firefox) pode atribuir cada aba aberta a um processo separado para garantir isolamento; internamente, cada processo utiliza threads dedicadas para renderizar a página, tocar áudio e capturar eventos do usuário[15][16].

---

### 3\. Escalonamento de CPU

* **Conceito:** É o mecanismo do núcleo do SO encarregado de selecionar qual processo ou thread na fila de "prontos" receberá o uso do processador e por quanto tempo[17]. O escalonamento pode ser **cooperativo** (a tarefa cede voluntariamente a CPU) ou **preemptivo** (o SO interrompe a tarefa ao fim de um intervalo de tempo chamado *quantum* ou pela chegada de uma tarefa de maior prioridade)[18][19].
* **Finalidade:** Maximizar o uso do processador, garantir uma distribuição proporcional do tempo de CPU, responder rapidamente a aplicações interativas e evitar a **inanição** (*starvation*) de tarefas menos prioritárias[17].
* **Exemplo Prático:** O algoritmo **Round-Robin** (revezamento) alterna a CPU entre os programas prontos a cada fatia fixa de tempo (ex: 2 segundos)[19]. Se você estiver com um editor de texto e um player de música abertos, o escalonador alterna a execução rapidamente entre eles, dando a impressão de paralelismo contínuo[12].

---

### 4\. Gerenciamento de Memória

* **Conceito:** É o subsistema responsável por alocar e organizar a memória principal (RAM) entre o SO e as aplicações[12]. Utiliza o mecanismo de **memória virtual** suportado pela **MMU** (*Memory Management Unit*), desvinculando os endereços lógicos vistos pelas aplicações dos endereços físicos da RAM e estruturando a memória em **páginas** ou **segmentos**[12].
* **Finalidade:** Isolar os espaços de endereçamento dos processos para impedir acessos indevidos e expandir a memória RAM física através da **paginação em disco** (*paging* e área de *swap*)[12].
* **Exemplo Prático:** Quando a memória RAM fica cheia, o SO move páginas de memória ociosas para a partição de *swap* no disco[27][28]. Se o programa tentar acessar essa área posteriormente, a MMU gera uma interrupção de **falta de página** (*page fault*), forçando o SO a trazer a página do disco de volta para a RAM de forma transparente[27].



### 5\. Armazenamento e Sistemas de Arquivos

* **Conceito:** O **sistema de arquivos** é a estrutura lógica não volátil gerenciada pelo SO que organiza o armazenamento bruto oferecido pelos dispositivos de bloco (HDDs, SSDs) nas abstrações de **arquivos**, **diretórios** e **metadados**[31].
* **Finalidade:** Preservar dados de forma não volátil (permanecem salvos após o desligamento do computador)[31], oferecer uma hierarquia legível ao usuário[32] e mapear os nomes de arquivos para blocos físicos no disco, controlando permissões e atributos[35][36].
* **Exemplo Prático:** Ao salvar um trabalho no caminho `/home/usuario/documentos/relatorio.pdf`, o sistema de arquivos (como Ext4 ou NTFS) lê o diretório, localiza o número do *inode* ou registro correspondente e mapeia esse arquivo para os blocos físicos no dispositivo de armazenamento[32][37].



### 6\. User Mode e Kernel Mode

* **Conceito:** São os dois níveis fundamentais de privilégio do processador[38]. O **Kernel Mode** (modo núcleo/supervisor) concede acesso total ao hardware e a todas as instruções da CPU[39]. O **User Mode** (modo usuário) restringe instruções consideradas "perigosas" (como controle de portas de E/S e reinicialização)[40].
* **Finalidade:** Garantir a proteção e estabilidade do sistema, impedindo que aplicações em modo usuário manipulem o hardware diretamente, alterem a memória do núcleo ou desestabilizem outros processos[13]. A comunicação entre os dois modos ocorre via **chamadas de sistema** (*system calls* / *syscalls*)[43][44].
* **Exemplo Prático:** Quando um programa em modo usuário chama a função `write()` para gravar dados em disco, ele invoca a instrução especial `syscall`[45][46]. O processador comuta temporariamente para o *Kernel Mode*, executa a função segura do núcleo (`sys_write`), grava no disco e retorna o controle em *User Mode* para a aplicação[44].



### 🎯 Pontos que Merecem Maior Revisão

Para consolidar a matéria em nível universitário, os tópicos mais cobrados e que exigem maior atenção nos estudos são:

1. **Custo da Troca de Contexto (** **Context Switch** **):** Entender o que é armazenado no PCB/TCB (registradores, PC, SP) e por que a troca de contexto entre threads do mesmo processo é mais rápida do que entre processos distintos[8].
2. **Sincronização e Concorrência:** Conceitos de exclusão mútua, condições de corrida (*race conditions*), semáforos, mutexes, o problema dos produtores/consumidores e a prevenção de *deadlocks*[51][52].
3. **Mapeamento e Tradução da MMU:** Como funciona a tradução de endereços lógicos para físicos, o uso de tabelas de páginas (*Page Tables*), o tratamento de *page faults* e o fenômeno do *thrashing* (hiperpaginação)[23].
4. **Cálculo de Algoritmos de Escalonamento:** Saber calcular o tempo médio de execução e espera para os algoritmos FCFS, Round-Robin (variando o *quantum*), SJF/SRTF e entender como a técnica de *aging* resolve a inanição (*starvation*)[20].
5. **Ciclo de Vida de uma System Call:** A sequência exata desde a passagem de parâmetros pela biblioteca do sistema até a instrução de chaveamento de privilégio de *User Mode* para *Kernel Mode***

**Referências retornadas pelo NotebookLM:**

> **socm-texto-01.pdf socm-texto-02.pdf User Mode and Kernel Mode - Windows drivers | Microsoft Learn socm-texto-04.pdf socm-texto-05.pdf 2-RevisaoSO.pdf socm-texto-06.pdf socm-texto-14.pdf socm-texto-17.pdf socm-texto-21.pdf socm-texto-22.pdf socm-texto-24.pdf socm-texto-25.pdf**



### Experimento 2 — Explicação em diferentes níveis

**Prompt testado:**

> “Explique memória virtual.”

**Problema encontrado:** a resposta pode assumir conhecimentos prévios que ainda não foram consolidados.

**Prompt melhorado:**

> “Explique memória virtual em três níveis: primeiro como se eu nunca tivesse estudado o assunto; depois em nível universitário introdutório; por fim, explique os principais termos técnicos que aparecem nas fontes. Não use informações que não possam ser relacionadas às fontes deste notebook.”

**Resultado obtido:**

> **### Nível 1: Explicação Intuitiva (Para quem nunca estudou o assunto)

Imagine que a memória física do computador (a memória RAM) é como um grande **estacionamento público com vagas numeradas**. Se cada programa tentasse estacionar seu carro diretamente em uma vaga com número fixo, haveria grande confusão: dois programas poderiam tentar ocupar a mesma vaga ao mesmo tempo, ou um programa poderia invadir e alterar o espaço do outro[1][2].

A **memória virtual** é uma solução criada pelo sistema operacional e pelo hardware[1][3]:

* Em vez de dar o mapa real do estacionamento para os programas, o sistema operacional dá a cada programa o **mapa de um estacionamento privativo e fictício**[1]. Para o programa, ele é o único dono daquele espaço e todas as vagas estão organizadas para ele do número 0 até o final[2].
* Quando o programa tenta acessar a "vaga fictícia nº 10", um "manobrista invisível" de hardware intercepta o pedido e traduz esse número fictício para a **vaga real** no estacionamento verdadeiro da RAM[5].
* Se a memória RAM física ficar cheia, o sistema operacional pode pegar partes do programa que não estão sendo usadas no momento e guardá-las temporariamente em um "depósito" no disco rígido ou SSD[8]. Se o programa precisar dessa parte de volta, o manobrista a traz de volta para a RAM de forma transparente[8].

---

### Nível 2: Explicação em Nível Universitário Introdutório

Em termos de arquitetura de sistemas operacionais, a memória virtual é uma abstração que desvincula o espaço de endereçamento visto pelos processos da memória física real[1][3].

1. **Endereços Lógicos vs. Físicos e o Papel da MMU:** Durante a execução de um programa, o processador gera **endereços lógicos (ou virtuais)**[3][6]. A **MMU** (*Memory Management Unit*), um componente de hardware integrado à CPU, intercepta esses endereços e os traduz para **endereços físicos** na memória RAM[5]. Além disso, a MMU verifica se o processo possui permissão de acesso àquela região, isolando os processos entre si e protegendo o espaço exclusivo do núcleo (*kernel*)[2].
2. **Organização por Paginação (** **Paging** **):** O espaço de endereçamento lógico é dividido em blocos de tamanho fixo chamados **páginas** (comumente de 4 KB)[16][17]. A RAM é dividida em blocos de igual tamanho chamados **quadros** (*frames*)[16]. A **Tabela de Páginas** (*Page Table*) de cada processo mantém o mapeamento indicando em qual quadro da RAM cada página se encontra[18][19].
  * Durante a tradução, a MMU decomprime o endereço lógico em **Número de Página** e **Deslocamento (** **offset** **)**[20]. O número da página é usado para consultar a tabela e obter o número do quadro, enquanto o *offset* permanece inalterado para localizar o byte exato dentro do quadro[20].
3. **Mecanismo de Falta de Página (** **Page Fault** **) e** **Swap** **:** Cada entrada da tabela de páginas possui bits de status, como o **bit de presença**[15]. Quando um processo tenta acessar uma página que foi transferida para o disco ou ainda não foi carregada na RAM, seu bit de presença está em 0[9]. A MMU intercepta o acesso e dispara uma interrupção de **falta de página (** **page fault** **)**[11]. O núcleo do SO assume o controle, suspende o processo, busca a página na área de troca (*swap*) do disco, carrega-a em um quadro livre da RAM, atualiza a tabela de páginas e retoma a execução da instrução[9].

---

### Nível 3: Principais Termos Técnicos das Fontes

* **Endereço Lógico (ou Virtual) vs. Endereço Físico:** O endereço lógico é o endereço gerado pela CPU e enxergado pelos processos[3][6]; o endereço físico reflete a posição real dos dados nos chips de memória RAM[3].
* **MMU (** **Memory Management Unit** **):** Unidade de hardware que intercepta e traduz endereços lógicos em físicos em tempo de execução e aplica regras de proteção de memória[5].
* **Página (** **Page** **) e Quadro (** **Frame** **):** Página é um bloco contínuo de tamanho fixo (ex: 4 KB) do espaço de endereçamento lógico[16]; Quadro (*frame*) é o bloco equivalente na memória RAM física[16].
* **Tabela de Páginas (** **Page Table** **) e PTBR:** Estrutura armazenada na RAM que mapeia as páginas do processo para os quadros físicos[18][19]. O **PTBR** (*Page Table Base Register*) é o registrador da MMU que aponta para a tabela do processo ativo[19].
* **TLB (** **Translation Lookaside Buffer** **):** Cache associativo de alta velocidade dentro da MMU que armazena mapeamentos recentes [página, quadro] para acelerar a tradução sem consultar a RAM a cada instrução[24][25].
* **Falta de Página (** **Page Fault** **):** Interrupção de hardware gerada pela MMU quando um processo tenta acessar uma página cujo bit de presença indica que ela não se encontra na RAM[11].
* **Área de Troca (** **Swap Area** **) e Paginação em Disco (** **Paging** **):** Partição ou arquivo reservado no disco usado pelo SO para armazenar páginas ociosas retiradas da RAM[9][10]. A movimentação de páginas individuais entre a memória e o disco é chamada de *paging*[9].
* **Paginação sob Demanda (** **Demand Paging** **):** Técnica na qual as páginas de um código ou arquivo mapeado só são trazidas do disco para a RAM no momento exato em que são referenciadas pela primeira vez[26].
* **Hiperpaginação (** **Thrashing** **):** Estado severo de degradação do sistema em que a RAM é insuficiente para abrigar o conjunto de trabalho dos processos, fazendo com que o SO passe quase todo o tempo realizando trocas de páginas com o disco[29][30].
* **Copy-on-Write (CoW):** Técnica de otimização em que processos compartilham páginas como somente leitura; quando um processo tenta escrever, o SO gera uma falta de página e cria uma cópia privada dessa página para ele**

**O que aprendi com o experimento:**

A mesma pergunta pode gerar respostas mais úteis quando o nível de conhecimento esperado é explicitamente definido. Isso melhora a progressão do estudo e evita receber uma explicação avançada antes de dominar a base.

---

## 🩹 “Cicatrizes” / Troubleshooting

Durante a utilização do NotebookLM, alguns ajustes foram importantes para melhorar a qualidade das respostas.

| Problema | Causa provável | Ajuste feito |
|---|---|---|
| Resposta genérica | Pergunta ampla demais | Definir tópicos e objetivo |
| Explicação difícil | Nível de conhecimento não informado | Pedir linguagem de iniciante/universitário |
| Muito texto | Formato não especificado | Pedir tabela, tópicos ou comparação |
| Resposta parece correta, mas não sei de onde veio | Falta de rastreabilidade | Pedir uso das fontes e verificar as citações |
| Conceitos parecidos foram confundidos | Pergunta não exigia diferenciação | Pedir comparação direta e exemplos |
| IA trouxe detalhes além do objetivo | Escopo muito aberto | Pedir para priorizar somente o conteúdo relevante às fontes |

### Exemplo de melhoria de prompt

**Antes:**

> “Fale sobre processos.”

**Depois:**

> “Com base somente nas fontes deste notebook, explique o conceito de processo para um estudante iniciante. Diferencie processo de programa e thread, explique quais recursos estão associados a um processo e termine com três perguntas de revisão, sem responder às perguntas.”

---

# 📖 Miniguia de estudo — Sistemas Operacionais

## 1. O que é um Sistema Operacional?

Um sistema operacional é o software responsável por intermediar a relação entre os programas e os recursos do computador. Ele organiza e administra recursos como processador, memória, armazenamento e dispositivos de entrada e saída.

De forma simples, ele cria uma camada de abstração para que os programas não precisem controlar diretamente cada detalhe do hardware.

### Ideia-chave

**Aplicação → Sistema Operacional → Hardware**

O sistema operacional também fornece mecanismos e serviços para executar programas, gerenciar recursos e controlar o acesso ao sistema.

---

## 2. Programa, processo e thread

### Programa

É o código armazenado que descreve uma tarefa que pode ser executada.

### Processo

É uma instância de um programa em execução, associada a recursos e a um espaço de memória virtual.

### Thread

É uma unidade de execução dentro de um processo. Um processo pode possuir várias threads.

### Exemplo simples

Um navegador pode ser tratado como um conjunto de processos e threads trabalhando para executar diferentes tarefas. Essa organização permite separar responsabilidades e realizar várias atividades de forma concorrente.

### Para memorizar

**Programa = código**

**Processo = programa em execução + recursos**

**Thread = unidade de execução dentro do processo**

---

## 3. Gerenciamento e escalonamento da CPU

O processador possui capacidade limitada de execução. Quando existem várias tarefas prontas para executar, o sistema operacional precisa decidir quais serão executadas e em que ordem.

Esse trabalho está relacionado ao **escalonamento (scheduling)**.

Um escalonador pode considerar critérios como prioridade, tempo de execução e capacidade de resposta.

### Conceito importante

O computador pode dar a impressão de executar várias tarefas simultaneamente mesmo quando as tarefas precisam compartilhar os mesmos recursos de processamento. Em sistemas modernos, múltiplos núcleos também permitem execução realmente paralela em determinadas situações.

---

## 4. Gerenciamento de memória

O sistema operacional precisa controlar a memória usada pelos programas, evitando conflitos e oferecendo mecanismos para organizar o espaço disponível.

### Memória virtual

Memória virtual é uma técnica que permite que os processos utilizem um espaço de endereçamento virtual, separado da memória física diretamente disponível.

Entre os mecanismos relacionados estão:

- páginas e tabelas de páginas;
- mapeamento de endereços;
- alocação e liberação de memória;
- uso de memória secundária em mecanismos de paginação/swap, quando aplicável.

### Por que isso é importante?

A memória virtual contribui para isolamento entre processos e permite que o sistema organize melhor o uso da memória física.

---

## 5. Armazenamento e sistemas de arquivos

O sistema operacional precisa organizar dados persistentes em dispositivos de armazenamento.

Um **sistema de arquivos** define estruturas e mecanismos para armazenar e recuperar arquivos e diretórios.

### Conceitos essenciais

- arquivo;
- diretório;
- metadados;
- permissões;
- armazenamento persistente;
- operações de leitura e escrita.

O objetivo é permitir que programas manipulem dados de forma estruturada sem precisarem controlar diretamente cada detalhe físico do dispositivo.

---

## 6. User mode e Kernel mode

Em arquiteturas de sistemas modernos, existe uma separação entre código executado no **user mode** e código executado no **kernel mode**.

### User mode

É onde aplicações comuns são executadas. O acesso direto a recursos críticos é limitado.

### Kernel mode

É um modo privilegiado utilizado pelo núcleo do sistema operacional e por componentes que precisam de acesso mais amplo aos recursos do sistema.

### Ideia-chave

A separação existe para contribuir para **isolamento e proteção**. Um programa comum não deve conseguir modificar livremente estruturas críticas do sistema operacional.

---

# 🧾 Glossário

| Termo | Definição simples |
|---|---|
| Sistema Operacional | Software que administra recursos do computador e oferece serviços aos programas. |
| Kernel | Núcleo do sistema operacional. |
| Processo | Instância de um programa em execução, com recursos associados. |
| Thread | Unidade de execução dentro de um processo. |
| Escalonamento | Decisão de quais tarefas receberão tempo de processamento. |
| Scheduler | Componente responsável pelo escalonamento. |
| CPU | Unidade responsável pela execução das instruções. |
| Memória virtual | Abstração que fornece aos processos um espaço de endereçamento virtual. |
| Página | Unidade utilizada em mecanismos de paginação de memória virtual. |
| Tabela de páginas | Estrutura usada para relacionar endereços virtuais e físicos. |
| Memória física | Memória RAM efetivamente disponível no hardware. |
| Sistema de arquivos | Estrutura e conjunto de mecanismos para organizar arquivos e diretórios. |
| Arquivo | Unidade lógica usada para armazenar dados. |
| Diretório | Estrutura usada para organizar arquivos e outros diretórios. |
| User mode | Modo com restrições para execução de aplicações. |
| Kernel mode | Modo privilegiado de execução usado por componentes centrais do sistema. |
| I/O | Entrada e saída de dados entre o sistema e dispositivos. |
| Memória compartilhada | Região/recurso de memória que pode ser compartilhado entre processos ou componentes, conforme o mecanismo utilizado. |
| Concorrência | Organização de várias tarefas que progridem de forma intercalada ou coordenada. |
| Paralelismo | Execução efetivamente simultânea de tarefas em recursos de processamento separados. |

---

# ♻️ Prompts reutilizáveis para futuras revisões

### 1. Resumo direcionado

> “Com base exclusivamente nas fontes deste notebook, resuma [TEMA] para revisão de uma prova. Organize em definição, finalidade, funcionamento, exemplo e pontos que costumam gerar confusão.”

### 2. Explicação para iniciante

> “Explique [TEMA] como se eu estivesse estudando Sistemas Operacionais pela primeira vez. Use linguagem simples, mas preserve os termos técnicos importantes. Depois faça uma versão um pouco mais técnica.”

### 3. Comparação

> “Compare [CONCEITO A] e [CONCEITO B] usando somente as fontes deste notebook. Faça uma tabela com definição, objetivo, funcionamento, diferenças e exemplo prático.”

### 4. Quiz

> “Crie 10 questões de múltipla escolha sobre [TEMA], usando apenas as fontes deste notebook. Não mostre o gabarito ainda. Espere minhas respostas e depois corrija uma por uma, explicando meus erros.”

### 5. Prova simulada

> “Monte uma prova simulada de Sistemas Operacionais com 10 questões de dificuldade crescente, baseada nas fontes deste notebook. Misture perguntas conceituais e situações práticas. Não mostre o gabarito.”

### 6. Identificação de lacunas

> “Com base nas minhas respostas abaixo, identifique quais conceitos de Sistemas Operacionais ainda preciso revisar. Não me dê apenas a resposta correta: explique qual conceito está faltando.”

### 7. Verificação de afirmação

> “Verifique a afirmação: ‘[AFIRMAÇÃO]’. Classifique-a como correta, parcialmente correta ou incorreta somente com base nas fontes deste notebook. Explique o motivo e cite a fonte correspondente.”

### 8. Revisão rápida antes da prova

> “Faça uma revisão de 10 minutos sobre [TEMA]. Priorize os conceitos fundamentais, relações entre conceitos, termos técnicos e erros comuns. Termine com 5 perguntas para eu responder sem consultar o material.”

---

# 💡 O que este projeto demonstra

Este caderno não foi pensado apenas como um resumo do conteúdo. Ele demonstra um processo de estudo apoiado por IA:

**Curadoria → Pergunta → Teste do prompt → Verificação nas fontes → Identificação de lacunas → Revisão → Consolidação do conhecimento**

A principal aprendizagem relacionada à IA foi entender que **a qualidade da resposta depende também da qualidade da pergunta**. Ao especificar contexto, objetivo, nível de dificuldade, formato e fontes permitidas, o resultado tende a ser mais útil para aprendizagem.

---

# ✅ Checklist de entrega

Antes de enviar o projeto para a DIO:

- [ ] Criar o repositório no GitHub.
- [ ] Colocar este `README.md` na raiz.
- [ ] Substituir os nomes dos PDFs pelos nomes reais usados no NotebookLM.
- [ ] Confirmar que as fontes principais do README correspondem às fontes realmente utilizadas.
- [ ] Testar no NotebookLM pelo menos 2 prompts.
- [ ] Colar pequenos registros das respostas reais e suas referências.
- [ ] Registrar pelo menos 2 dificuldades e como o prompt foi melhorado.
- [ ] Revisar o miniguia e corrigir qualquer informação que não esteja de acordo com suas fontes.
- [ ] Fazer um commit final organizado.
- [ ] Enviar a URL do repositório na entrega da DIO.

---

## 📌 Observação final

Este projeto foi construído com foco em **aprendizagem ativa**. O NotebookLM foi utilizado para consultar fontes, fazer perguntas, testar o entendimento e organizar revisões. As respostas da IA devem ser confrontadas com as fontes utilizadas no caderno antes de serem tratadas como conhecimento consolidado.
