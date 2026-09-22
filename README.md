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

1. **[NOME EXATO DO PDF/AULA 1]**
   - Tipo: PDF de aula
   - Uso: conceitos fundamentais de sistemas operacionais.

2. **[NOME EXATO DO PDF/AULA 2]**
   - Tipo: PDF de aula
   - Uso: processos, threads e/ou gerenciamento da CPU.

3. **[NOME EXATO DO PDF/AULA 3]**
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

> 🔎 **Cole aqui um pequeno resumo da resposta real obtida no NotebookLM.**

**Referências retornadas pelo NotebookLM:**

> 🔎 **Cole aqui as referências/citações mostradas pelo NotebookLM.**

---

### Experimento 2 — Explicação em diferentes níveis

**Prompt testado:**

> “Explique memória virtual.”

**Problema encontrado:** a resposta pode assumir conhecimentos prévios que ainda não foram consolidados.

**Prompt melhorado:**

> “Explique memória virtual em três níveis: primeiro como se eu nunca tivesse estudado o assunto; depois em nível universitário introdutório; por fim, explique os principais termos técnicos que aparecem nas fontes. Não use informações que não possam ser relacionadas às fontes deste notebook.”

**Resultado obtido:**

> 🔎 **Cole aqui o principal resultado observado no NotebookLM.**

**O que aprendi com o experimento:**

A mesma pergunta pode gerar respostas mais úteis quando o nível de conhecimento esperado é explicitamente definido. Isso melhora a progressão do estudo e evita receber uma explicação avançada antes de dominar a base.

---

### Experimento 3 — Comparação de conceitos

**Prompt:**

> “Compare processo e thread usando exclusivamente as fontes deste notebook. Monte uma tabela com: definição, memória, recursos, execução, comunicação e exemplo. Depois explique em linguagem simples por que um processo pode possuir várias threads.”

**Por que esse prompt é melhor:**

Ele transforma uma pergunta aberta em uma tarefa objetiva, permitindo revisar as diferenças entre dois conceitos parecidos sem depender apenas de um texto corrido.

**Resultado obtido:**

> 🔎 **Cole aqui o resultado do NotebookLM e as referências apresentadas.**

---

### Experimento 4 — Verificação e pensamento crítico

**Prompt:**

> “Analise esta afirmação: ‘um programa e um processo são a mesma coisa’. Diga se ela é correta, parcialmente correta ou incorreta. Explique o motivo usando as fontes do notebook, indique qual conceito está sendo confundido e apresente um exemplo prático.”

**Objetivo:**

Usar a IA não apenas para receber informação, mas para **testar meu entendimento** e descobrir possíveis confusões conceituais.

**Resultado obtido:**

> 🔎 **Cole aqui o resultado real do NotebookLM.**

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
- [ ] Testar no NotebookLM pelo menos 3 prompts.
- [ ] Colar pequenos registros das respostas reais e suas referências.
- [ ] Registrar pelo menos 2 dificuldades e como o prompt foi melhorado.
- [ ] Revisar o miniguia e corrigir qualquer informação que não esteja de acordo com suas fontes.
- [ ] Fazer um commit final organizado.
- [ ] Enviar a URL do repositório na entrega da DIO.

---

## 📌 Observação final

Este projeto foi construído com foco em **aprendizagem ativa**. O NotebookLM foi utilizado para consultar fontes, fazer perguntas, testar o entendimento e organizar revisões. As respostas da IA devem ser confrontadas com as fontes utilizadas no caderno antes de serem tratadas como conhecimento consolidado.
