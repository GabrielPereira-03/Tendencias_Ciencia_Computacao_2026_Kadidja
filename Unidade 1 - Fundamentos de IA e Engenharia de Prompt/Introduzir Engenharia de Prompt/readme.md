
# Aula 02 — Engenharia de Prompt

 ## 1\. Identificação

 **Disciplina:** Tendências em Ciências da Computação\
 **Turma:** N1\
 **Grupo:** Individual\
 **Data:** 21/08/2026\
 **Integrante:** Gabriel Tavares

---

 ## 2\. Problema escolhido

 ### Contexto

 Durante a criação de um sistema de software, o levantamento e a análise de requisitos são fundamentais para definir as funcionalidades que serão disponibilizadas e as características que o sistema deverá apresentar.

 Para estudantes que estão começando a estudar Computação, entretanto, pode ser difícil reconhecer quais informações representam requisitos funcionais e quais representam requisitos não funcionais. Também pode haver dificuldade em transformar uma descrição geral de um sistema em requisitos objetivos, organizados e fáceis de compreender.

 Nesse cenário, ferramentas de Inteligência Artificial Generativa podem ser utilizadas como apoio educacional, auxiliando na interpretação de uma descrição de sistema e na elaboração inicial de possíveis requisitos.

 ### Problema

 Como utilizar uma ferramenta de Inteligência Artificial Generativa para apoiar estudantes de Computação na identificação, classificação e organização dos requisitos de um sistema?

---

 ## 3\. Objetivo

 Aplicar uma ferramenta de Inteligência Artificial Generativa para auxiliar na elaboração de requisitos funcionais e não funcionais de um sistema acadêmico, analisando a qualidade das respostas produzidas e aprimorando o prompt para obter informações mais específicas, estruturadas e compatíveis com o contexto apresentado.

---

 ## 4\. Prompt inicial

```
Liste alguns requisitos funcionais e não funcionais que poderiam existir em um sistema acadêmico.
```

 ### Resultado inicial

 Com esse comando, a IA apresentou uma resposta semelhante à seguinte:

 **Requisitos funcionais:**

 1. Criar contas de estudantes.
2. Cadastrar professores.
3. Registrar matérias.
4. Permitir acesso por usuário e senha.
5. Consultar resultados acadêmicos.
6. Gerar documentos e relatórios.

 **Requisitos não funcionais:**

 1. O sistema deve possuir boa segurança.
2. O sistema deve apresentar bom desempenho.
3. A utilização deve ser simples.
4. O sistema deve funcionar de maneira estável.

 Apesar de apresentar sugestões relacionadas ao assunto, a resposta ainda é ampla e não está vinculada a um sistema acadêmico com características previamente definidas.

---

 ## 5\. Análise crítica

 ### O que funcionou?

 O prompt inicial conseguiu direcionar a ferramenta para o assunto de requisitos de software. A IA também conseguiu separar os exemplos em duas categorias e apresentou uma resposta de fácil leitura.

 ### O que poderia ser melhor?

 A principal limitação foi a ausência de informações sobre o sistema que estava sendo analisado. Não foram definidos os perfis dos usuários, as principais finalidades da aplicação ou as funcionalidades esperadas.

 Além disso, expressões como "ter boa segurança" ou "apresentar bom desempenho" não são suficientemente específicas para serem utilizadas como requisitos bem definidos.

 ### Quais informações estavam faltando?

 Seria necessário informar, por exemplo:

 - finalidade do sistema;
- perfis de usuários;
- principais atividades realizadas pelos usuários;
- quantidade de requisitos desejada;
- características que diferenciam requisitos funcionais e não funcionais;
- nível de detalhamento esperado;
- estrutura em que a resposta deveria ser apresentada;
- aspectos que deveriam ser analisados ou validados.

 ### O que deve ser validado?

 Os requisitos sugeridos precisam ser comparados com o funcionamento esperado do sistema. Também é importante verificar se cada item foi classificado corretamente e se realmente representa uma necessidade do projeto.

 ### A IA realizou alguma suposição?

 Sim. Como o comando inicial não apresentava detalhes suficientes, a IA precisou utilizar exemplos comuns de sistemas acadêmicos. Entretanto, essas funcionalidades podem não fazer parte do sistema que está sendo planejado.

---

 ## 6\. Prompt refinado

```
Atue como um analista de requisitos com experiência em Engenharia de Software e como um professor que está auxiliando estudantes iniciantes de Computação.

CONTEXTO DO SISTEMA:

Estamos estudando um sistema acadêmico que será desenvolvido por alunos de Computação. A aplicação possuirá três perfis principais: secretaria, docente e estudante.

O sistema terá como finalidade centralizar informações relacionadas à vida acadêmica. Entre suas atividades estão o controle de usuários, o gerenciamento de matérias, o acompanhamento de tarefas e o registro de resultados obtidos pelos estudantes.

O público desta análise possui conhecimentos introdutórios sobre Engenharia de Software. Portanto, os requisitos devem ser escritos de maneira simples, mas seguindo uma estrutura tecnicamente adequada.

OBJETIVO:

Produzir uma lista inicial de requisitos que possa ser utilizada pelos estudantes como base para estudar e analisar requisitos de software.

TAREFA:

1. Elabore 8 requisitos funcionais relacionados ao sistema.
2. Elabore 5 requisitos não funcionais.
3. Classifique cada requisito de acordo com seu tipo.
4. Explique de forma resumida o que cada requisito representa.
5. Para os requisitos funcionais, indique o perfil de usuário envolvido.
6. Após listar os requisitos, identifique situações que ainda dependem de confirmação ou esclarecimento.

REGRAS:

- Escreva de forma clara e objetiva.
- Evite funcionalidades que não tenham relação direta com o contexto informado.
- Não utilize descrições vagas quando for possível especificar melhor o requisito.
- Cada requisito deve representar uma necessidade individual do sistema.
- Utilize termos compreensíveis para estudantes que estão iniciando na área.

FORMATO DA RESPOSTA:

Organize os requisitos em duas tabelas.

A primeira tabela deve conter:
| Código | Requisito Funcional | Perfil | Explicação |

A segunda tabela deve conter:
| Código | Requisito Não Funcional | Tipo | Explicação |

Ao final, crie uma seção chamada "Questões em aberto" e liste informações que precisam ser discutidas ou confirmadas antes de considerar os requisitos definitivos.

CRITÉRIOS:

A resposta deve apresentar organização, clareza, coerência, especificidade e consistência técnica.
```

---

 ## 7\. Resultado refinado

 Depois da melhoria do prompt, a resposta da IA pode ser apresentada da seguinte forma:

 ### Requisitos funcionais

 | Código | Requisito Funcional | Perfil | Explicação |
| --- | --- | --- | --- |
| RF01 | Acessar a plataforma | Secretaria, Docente e Estudante | O sistema deve permitir que cada usuário entre na plataforma utilizando suas credenciais. |
| RF02 | Administrar contas | Secretaria | O sistema deve permitir criar, atualizar e remover contas de usuários. |
| RF03 | Organizar matérias | Secretaria e Docente | O sistema deve possibilitar o cadastro e a atualização dos dados referentes às matérias. |
| RF04 | Visualizar matérias vinculadas | Estudante | O estudante deve conseguir consultar as matérias associadas à sua matrícula. |
| RF05 | Criar tarefas acadêmicas | Docente | O professor deve poder cadastrar atividades relacionadas às matérias que ministra. |
| RF06 | Acompanhar tarefas | Estudante | O aluno deve conseguir visualizar as atividades disponibilizadas pelos docentes. |
| RF07 | Lançar resultados | Docente | O professor deve poder registrar e atualizar os resultados obtidos pelos estudantes. |
| RF08 | Consultar desempenho | Estudante | O estudante deve conseguir visualizar seus resultados acadêmicos registrados no sistema. |

 ### Requisitos não funcionais

 | Código | Requisito Não Funcional | Tipo | Explicação |
| --- | --- | --- | --- |
| RNF01 | Controle de acesso | Segurança | O sistema deve impedir que usuários sem autorização tenham acesso a informações restritas. |
| RNF02 | Facilidade de utilização | Usabilidade | As telas devem ser organizadas de forma que os diferentes perfis consigam utilizar as funções disponíveis sem dificuldade excessiva. |
| RNF03 | Tempo de resposta | Desempenho | As principais operações devem ser processadas em um período adequado para não prejudicar a utilização da plataforma. |
| RNF04 | Continuidade do serviço | Disponibilidade | O sistema deve permanecer acessível nos horários estabelecidos para seu funcionamento. |
| RNF05 | Confiabilidade dos dados | Integridade | As informações acadêmicas armazenadas devem permanecer consistentes durante as operações realizadas pelos usuários. |

 ### Questões em aberto

 Algumas informações ainda precisam ser discutidas antes que os requisitos sejam considerados definitivos:

 - Quais regras serão utilizadas para criar e recuperar as contas?
- Quais ações ficarão disponíveis exclusivamente para a secretaria?
- Um docente poderá alterar informações de qualquer matéria ou somente das matérias sob sua responsabilidade?
- Quais dados serão utilizados para representar o desempenho dos estudantes?
- Haverá um limite de tempo para o envio das atividades?
- Qual tempo máximo de resposta será considerado aceitável?
- Quais mecanismos serão utilizados para proteger informações acadêmicas?

---

 ## 8\. Técnicas utilizadas

 As técnicas de Engenharia de Prompt aplicadas foram:

 - [x] Role Prompting
- [ ] Few-Shot Prompting
- [x] Contexto
- [x] Restrições
- [x] Definição do formato de resposta
- [x] Divisão da tarefa em etapas
- [x] Refinamento iterativo
- [ ] Outra

 ### Justificativa

 **Role Prompting:** o comando determina que a IA atue como analista de requisitos e professor de Engenharia de Software, direcionando a perspectiva utilizada na resposta.

 **Contexto:** foram incluídas informações sobre a finalidade da aplicação, os usuários envolvidos e o nível de conhecimento do público.

 **Restrições:** foram definidas regras para reduzir respostas vagas, evitar funcionalidades desconectadas do cenário e manter os requisitos individuais.

 **Formato de resposta:** a estrutura das tabelas foi determinada previamente, facilitando a organização e comparação dos resultados.

 **Divisão em etapas:** o prompt separou a atividade em identificação, classificação, explicação e levantamento de questões pendentes.

 **Refinamento iterativo:** o segundo prompt foi elaborado depois da análise das limitações encontradas na primeira tentativa.

---

 ## 9\. Comparação

 | Critério | Prompt Inicial | Prompt Refinado |
| --- | --- | --- |
| Especificidade | Baixa | Alta |
| Quantidade de contexto | Pequena | Detalhada |
| Organização | Lista simples | Tabelas estruturadas |
| Adequação ao sistema | Genérica | Direcionada ao cenário |
| Clareza dos requisitos | Moderada | Maior |
| Possibilidade de validação | Limitada | Mais fácil de verificar |
| Utilidade para os estudantes | Introdução ao tema | Material mais adequado para estudo |

 ### Análise da comparação

 O prompt refinado apresentou melhores resultados porque forneceu mais informações sobre o cenário e estabeleceu claramente o que deveria ser produzido.

 Além de informar o papel que a IA deveria assumir, foram definidos o objetivo da análise, a quantidade de requisitos, as regras de escrita, os dados que deveriam acompanhar cada requisito e o formato da resposta.

 No primeiro prompt, a falta de informações obrigava a IA a preencher as lacunas utilizando conhecimentos gerais sobre sistemas acadêmicos. Já no prompt refinado, as possibilidades foram delimitadas, tornando o resultado mais próximo da situação estudada.

 Portanto, para o objetivo desta atividade, o **prompt refinado apresentou o resultado mais adequado**.

---

 ## 10\. Validação

 Os requisitos produzidos pela Inteligência Artificial devem ser tratados como uma proposta inicial, e não como uma especificação definitiva do sistema.

 A validação deve verificar se as informações geradas realmente correspondem às necessidades da aplicação e se não existem contradições ou requisitos desnecessários.

 Algumas formas de realizar essa validação são:

 1. Conferir se cada requisito está relacionado ao objetivo do sistema.
2. Avaliar se a classificação entre funcional e não funcional está correta.
3. Procurar termos vagos, incompletos ou que permitam interpretações diferentes.
4. Comparar os requisitos com as regras definidas para o projeto.
5. Revisar o conteúdo com auxílio de um professor, analista ou responsável pelo sistema.
6. Confirmar com o cliente as informações que ainda não foram definidas.

 Também é importante lembrar que uma IA pode gerar respostas convincentes mesmo quando determinadas informações não foram fornecidas. Por esse motivo, o conteúdo precisa passar por revisão humana antes de ser utilizado em um projeto real.

---

 ## 11\. Ética e responsabilidade

 A utilização de Inteligência Artificial Generativa na análise de requisitos pode facilitar o aprendizado e acelerar a elaboração de uma primeira versão dos requisitos. Entretanto, seu uso também exige atenção.

 Uma ferramenta de IA pode interpretar incorretamente uma informação, criar uma funcionalidade que não foi solicitada ou apresentar uma recomendação baseada em uma suposição.

 Por esse motivo, os resultados não devem ser aceitos simplesmente porque foram produzidos pela ferramenta. O estudante ou profissional deve analisar o conteúdo, identificar possíveis erros e confirmar as informações relevantes.

 Também é importante evitar o compartilhamento de dados confidenciais ou informações sensíveis do projeto sem autorização.

 Assim, a IA deve funcionar como um recurso de apoio à atividade humana. A decisão final sobre quais requisitos serão adotados deve permanecer sob responsabilidade das pessoas envolvidas no desenvolvimento e na análise do sistema.

---

 ## 12\. Take Away

 A atividade demonstrou que um prompt bem elaborado pode influenciar diretamente a qualidade da resposta produzida por uma ferramenta de Inteligência Artificial.

 Na primeira tentativa, a falta de informações fez com que a IA apresentasse exemplos genéricos. Depois da inclusão de contexto, função da IA, quantidade de itens, restrições, critérios e formato de saída, foi possível obter uma resposta mais organizada e próxima da situação proposta.

 Também foi possível compreender que criar um bom prompt envolve um processo de tentativa, análise e melhoria. Não basta apenas formular uma pergunta; é necessário avaliar o resultado obtido e identificar quais informações precisam ser adicionadas ou modificadas.

 A principal conclusão é que a Inteligência Artificial pode ser uma ferramenta útil para apoiar estudantes na Engenharia de Software, mas seus resultados precisam ser avaliados criticamente e validados por pessoas antes de serem considerados requisitos definitivos.

