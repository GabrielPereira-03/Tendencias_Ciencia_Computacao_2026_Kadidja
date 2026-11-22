# Unidade 4 — Aplicações e Limitações da Inteligência Artificial

**Disciplina:** Tendências em Ciência da Computação  
**Semestre:** 2026.2  
**Professora:** Kadidja Valéria  
**Material de referência:** Guia de Estudos A1 — Criação de Agentes de IA e Ética Aplicada  
**Atividade relacionada:** Aula de 05/11 — Desenvolvendo Chatbots (SPEC)  
**Situação do registro:** estudo dos conteúdos e organização das referências da unidade

---

## 1. Apresentação da unidade

Nesta unidade, o estudo passa da criação de respostas com IA para um assunto que exige mais cuidado: **o que acontece quando um sistema recebe informações, toma decisões e pode executar ações**.

A diferença fica mais clara em um exemplo simples. Pedir a uma IA para explicar uma política de reembolso é uma coisa. Permitir que um agente consulte o pedido de um cliente, verifique as regras da empresa e autorize uma devolução é outra. No segundo caso, entram em jogo permissões, histórico, privacidade e a necessidade de explicar por que determinada decisão foi tomada.

O [Guia de Estudos A1](Guia_A1_Agentes_de_IA_e_%C3%89tica%20%28Tendencias%29%20%281%29.pdf), disponibilizado na disciplina, organiza esse conteúdo em quatro frentes:

- Fundamentos técnicos dos agentes;
- Gestão de contexto e memória;
- Privacidade, vieses e formas de proteção;
- Ética e responsabilidade social.

A aula sobre chatbots complementa esse estudo com um exemplo de organização de projeto, usando como referência o fluxo de desenvolvimento do SerproBots.

---

## 2. De um modelo generativo a um agente de IA

O material da professora compara modelos generativos, voltados principalmente à produção de conteúdo, com agentes que trabalham a partir de objetivos, regras e ações coordenadas.

| Ponto de comparação | Modelo generativo em uma interação simples | Agente de IA |
|---|---|---|
| **Entrada** | Recebe uma pergunta ou instrução | Recebe um objetivo e informações do ambiente |
| **Comportamento** | Produz uma resposta | Pode consultar ferramentas, seguir etapas e executar ações |
| **Contexto** | Depende das informações fornecidas na interação | Pode usar histórico e mecanismos de memória |
| **Responsabilidade** | Exige verificação do conteúdo gerado | Exige também controle das ações e decisões |

Essa comparação é didática. Um modelo generativo também pode ter memória e acesso a ferramentas quando faz parte de uma aplicação. O que caracteriza o agente, neste estudo, é a organização dessas capacidades para realizar uma tarefa com algum grau de autonomia.

### As quatro camadas da arquitetura

O guia apresenta uma arquitetura dividida em **perceptiva, cognitiva, decisória e executiva**. Para visualizar as diferenças, considerei o exemplo de um pedido de reembolso:

| Camada | Papel | Exemplo |
|---|---|---|
| **Perceptiva** | Receber a solicitação e identificar os dados disponíveis | Ler a mensagem e localizar o número do pedido |
| **Cognitiva** | Interpretar a intenção e o contexto | Entender se o cliente quer devolver um produto ou acompanhar uma solicitação |
| **Decisória** | Conferir regras e condições | Verificar prazo, elegibilidade e necessidade de aprovação |
| **Executiva** | Realizar uma ação autorizada | Registrar a solicitação ou encaminhá-la a um atendente |

A separação ajuda a perceber onde uma falha pode ocorrer. Se o agente interpretar o pedido corretamente, mas aplicar a política errada, o problema está na etapa de decisão. Se executar uma devolução sem permissão, a falha está no controle da ação.

---

## 3. Engenharia de prompt e memória

Na Unidade 1, a preocupação era escrever prompts mais claros. Aqui, o prompt também precisa considerar dados que mudam durante a conversa: informações do usuário, histórico, regras da empresa e limites do que o agente pode fazer.

O material apresenta três formas de organizar a memória:

| Tipo | Finalidade | Cuidado necessário |
|---|---|---|
| **Curta** | Manter as últimas mensagens da conversa | Não perder uma informação importante ao avançar o atendimento |
| **Média** | Resumir interações recentes | Evitar resumos que alterem o sentido do que foi dito |
| **Longa** | Guardar padrões ou preferências para interações futuras | Definir o que realmente precisa ser armazenado e por quanto tempo |

Mais memória pode ajudar na continuidade do atendimento, mas também aumenta a quantidade de dados pessoais armazenados. Por isso, nem toda informação mencionada durante uma conversa precisa ser lembrada.

Um exemplo: se alguém pergunta o horário de atendimento de uma empresa, não há motivo para guardar o histórico completo dessa pessoa apenas para responder a essa dúvida.

---

## 4. Privacidade, vieses e limites de uso

O guia destaca que a proteção de dados deve fazer parte da arquitetura desde o início, e não ser uma correção feita depois que o sistema já está funcionando.

### Privacidade e proteção de dados

Três medidas apresentadas no material são especialmente importantes:

1. **Minimização:** solicitar somente os dados necessários para a tarefa;
2. **Criptografia:** proteger informações armazenadas e transmitidas;
3. **Controle de acesso:** limitar quais pessoas e componentes do sistema podem consultar dados sensíveis.

Também é necessário pensar em uma situação menos óbvia: um agente criado para atendimento técnico não deveria reutilizar conversas anteriores para outra finalidade sem uma base adequada e sem respeitar as exigências de proteção de dados, incluindo a LGPD.

### Viés algorítmico

O material divide o problema em três possibilidades:

- **Viés de dados:** a base de treinamento não representa bem todas as pessoas que usarão o sistema;
- **Viés de algoritmo:** escolhas de projeto ou variáveis produzem resultados injustos;
- **Viés de aplicação:** um modelo é utilizado em um cenário diferente daquele para o qual foi preparado.

Um chatbot treinado somente com expressões de uma região, por exemplo, pode ter dificuldade para compreender a maneira como pessoas de outras regiões escrevem. Nesse caso, corrigir apenas uma resposta isolada não resolve a limitação da base utilizada.

O guia também sugere auditorias regulares, acompanhamento de variáveis correlacionadas e participação de equipes diversas como medidas de mitigação.

---

## 5. Ética aplicada às decisões do agente

Uma decisão automatizada pode estar de acordo com uma regra e ainda assim causar um problema para o usuário. Por isso, o guia propõe avaliar decisões a partir de três perspectivas:

| Perspectiva | Pergunta principal |
|---|---|
| **Consequencialista** | Qual alternativa causa menos danos? |
| **Deontológica** | Quais regras e deveres precisam ser respeitados? |
| **Ética das virtudes** | A decisão demonstra integridade, responsabilidade e transparência? |

Voltando ao exemplo do reembolso: o agente pode identificar que uma solicitação está fora do prazo. Mesmo assim, precisa comunicar essa decisão com clareza e oferecer um caminho de atendimento humano quando houver uma situação excepcional que o sistema não consiga avaliar.

O material relaciona responsabilidade social a três pontos: **prestação de contas**, **participação das pessoas afetadas** e **possibilidade de contestar e corrigir decisões**. Isso é relevante porque quem utiliza um serviço precisa saber a quem recorrer quando a automação falha.

---

## 6. Referência prática: desenvolvimento de chatbots com SerproBots

Na aula de 05/11 foi indicado o guia [Desenvolvendo Chatbots — Fluxo de Trabalho](https://serprobots.estaleiro.serpro.gov.br/docs/dev/), da plataforma SerproBots.

A documentação descreve um caminho possível para organizar o desenvolvimento de um assistente virtual. O próprio guia ressalta que as etapas são sugestões de trabalho, não uma sequência obrigatória para todas as equipes.

| Etapa de referência | O que precisa ser definido |
|---|---|
| [Entender a necessidade](https://serprobots.estaleiro.serpro.gov.br/docs/dev/entender-necessidade/) | Qual problema o chatbot pretende resolver, quem vai utilizá-lo e quais assuntos ficam fora do escopo |
| [Modelar o chatbot](https://serprobots.estaleiro.serpro.gov.br/docs/dev/modelar-assistente/) | Perguntas previstas, respostas, caminhos de diálogo e estratégia de atendimento |
| [UX Writing](https://serprobots.estaleiro.serpro.gov.br/docs/dev/uxw/) | Linguagem simples, tom adequado e mensagens que o usuário consiga entender |
| [Testar o chatbot](https://serprobots.estaleiro.serpro.gov.br/docs/dev/testar-assistente/) | Perguntas ambíguas, exceções e mudanças que possam afetar respostas anteriores |

Entre essas etapas, a documentação completa também prevê estrutura do projeto, persona, coleta de conteúdo, implementação, homologação, implantação e curadoria.

### Exemplo de planejamento

Para relacionar o material teórico com a prática, um possível exercício seria planejar um chatbot de orientação acadêmica, capaz de responder perguntas sobre horários, documentos e procedimentos da instituição.

Antes de implementar, seria preciso definir:

- De quais fontes oficiais as respostas seriam obtidas;
- O que fazer quando uma pergunta estiver fora do assunto;
- Quando encaminhar a conversa para atendimento humano;
- Se alguma informação pessoal será necessária;
- Como testar respostas incorretas, incompletas ou ambíguas.

**Este é apenas um exemplo de planejamento.** Não há, nesta pasta, evidência de que um chatbot tenha sido implementado, publicado ou testado na plataforma.

---

## 7. Análise crítica: onde estão os principais riscos?

| Situação | Risco | Medida de prevenção |
|---|---|---|
| O agente responde sobre um assunto que não conhece | Informar algo incorreto com aparente segurança | Restringir o escopo, consultar fontes confiáveis e admitir quando não souber |
| O usuário compartilha dados sensíveis | Armazenamento ou exposição desnecessária | Coletar o mínimo necessário e definir regras de retenção e acesso |
| O agente toma uma decisão automaticamente | Aplicar uma regra de forma inadequada | Registrar critérios e exigir aprovação humana em ações de maior impacto |
| O sistema funciona bem em exemplos simples | Falhar diante de perguntas diferentes ou ambíguas | Testar exceções, variações de linguagem e casos extremos |
| A base de dados não representa todos os usuários | Atendimento desigual | Avaliar resultados por grupos e revisar dados e critérios |

Uma questão importante é que **acertar muitas respostas não significa, sozinho, que o chatbot está pronto para uso**. Também é preciso observar o comportamento diante de falhas, a possibilidade de contestação e o impacto das respostas na vida das pessoas.

---

## 8. Material disponível e preparação para a A1

**Material da disciplina:** [Guia de Estudos A1 — Criação de Agentes de IA e Ética Aplicada (PDF)](Guia_A1_Agentes_de_IA_e_%C3%89tica%20%28Tendencias%29%20%281%29.pdf).

Na última página, o guia apresenta cinco perguntas de revisão. Usei essas perguntas como roteiro para conferir os assuntos estudados:

- [ ] Consigo diferenciar um modelo generativo de um agente autônomo?
- [ ] Sei explicar as quatro camadas da arquitetura de um agente?
- [ ] Entendo os tipos de memória e os riscos de privacidade?
- [ ] Consigo reconhecer vieses de dados, algoritmo e aplicação?
- [ ] Sei analisar um caso usando os três referenciais éticos?

**Referência complementar:** [Documentação de desenvolvimento do SerproBots](https://serprobots.estaleiro.serpro.gov.br/docs/dev/).

O PDF e a documentação são materiais de estudo. Este README registra os conceitos e exemplos analisados a partir dessas referências; não substitui uma entrega prática que venha a ser solicitada pela professora.

---

## 9. Reflexão e próximos passos

O ponto que mais chama atenção nesta unidade é a diferença entre gerar uma resposta e permitir que um sistema aja a partir dela. Um texto incorreto já pode atrapalhar. Uma ação incorreta pode atingir dados, serviços ou direitos de alguém.

Por isso, o desenvolvimento de agentes exige decisões que vão além da escolha de um modelo de IA. É preciso saber quais dados serão usados, quem autoriza uma ação, como tratar exceções e o que acontece quando o usuário discorda do resultado.

Como continuidade deste registro, os próximos passos são estudar os fluxos de chatbot propostos pelo SerproBots e, caso haja uma atividade prática, documentar separadamente o que for implementado e testado, com resultados e evidências reais.
