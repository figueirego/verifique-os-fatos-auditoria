# De onde vêm as checagens do Verifique os Fatos?

Investigação complementar com ECC deep-research — 24/10/2026. Nova resposta HTTP às 00:53:41, America/Fortaleza. Base permanece com 75 registros, idêntica ao snapshot anterior. `origin/main` permanece em `ac0b424f7413aebbb8f76d2a0bc8efb7a2df5da4`.

## Resultado principal

Foi possível reconstruir a publicação e a distribuição dos resultados, mas não a coleta e a apuração que os produziram. O software recebe texto e classificação prontos. Não encontramos, nos arquivos atuais nem nos caminhos do histórico Git alcançável, um coletor do debate, transcritor, pesquisador de fontes, gerador de vereditos ou registro de revisão editorial.

Isso é uma lacuna de transparência do material público examinado. Não prova que o processo inexista, que seja exclusivamente manual, que use IA ou que haja intenção de enganar.

## Cadeia de dados

| Etapa | O que conseguimos verificar | O que permanece desconhecido |
|---|---|---|
| Captura da fala | Campo `t` contém um resumo atribuído a um candidato | Quem transcreveu; vídeo/timecode; cortes e contexto |
| Seleção | São publicados 75 itens no recorte | Universo de falas; critério de inclusão/exclusão; repetições |
| Pesquisa | Texto `v` menciona instituições/veículos e dez registros contêm URL | Consultas feitas; documentos exatos para os demais; checagem de consistência |
| Classificação | Campo `c` já chega preenchido: 1, 2 ou 3 | Quem decide; rubrica detalhada; uso de IA; segunda revisão |
| Edição/publicação | Histórico do `posts.json` e instruções de edição no README | Ferramenta externa de edição/geração; autenticação do autor humano |
| Distribuição | Browser consulta `/posts.json`; HTML e base coincidiam com o repositório na auditoria | Configuração privada de deploy e garantias de equivalência permanente |
| Correção | Git registra alterações; interface suporta errata | Política editorial e responsáveis; base atual não preenche erratas |

Fontes: [README, atualização](https://github.com/felippe-regazio/verifiqueosfatos/blob/ac0b424f7413aebbb8f76d2a0bc8efb7a2df5da4/README.md#L98), [consulta do arquivo](https://github.com/felippe-regazio/verifiqueosfatos/blob/ac0b424f7413aebbb8f76d2a0bc8efb7a2df5da4/index.html#L300), [base](https://github.com/felippe-regazio/verifiqueosfatos/blob/ac0b424f7413aebbb8f76d2a0bc8efb7a2df5da4/posts.json).

“Content Update automático”, no README, descreve atualização da interface. Não demonstra checagem factual automática. Também não há uma API pública de verificação identificada: o ponto de leitura da aplicação é o arquivo JSON.

## Quem aparece no histórico

O clone não é raso: contém 192 commits alcançáveis no recorte. O histórico de `posts.json` tem 96 entradas: 95 com autor e committer declarados como Felippe Regazio; uma atribuída a César O. Araújo, relativa à introdução de IDs. Essas são identidades declaradas nos metadados Git, não autenticação da pessoa que pesquisou cada fato.

A primeira declaração ainda presente na base aparece em [a4ea51e](https://github.com/felippe-regazio/verifiqueosfatos/commit/a4ea51ea43a4b5e98b064066ade8886335178123), em 23/10/2026 às 21:51:22 −03:00. A versão anterior examinada estava vazia. A partir dessa inserção, há 65 entradas do histórico do arquivo até 24/10 às 00:26:06, todas sob o nome declarado de Felippe Regazio.

Conclusão permitida: a publicação versionada está concentrada sob um autor declarado. Conclusão não permitida: uma única pessoa necessariamente pesquisou, redigiu e revisou todas as checagens.

Das 96 mensagens de commit, 87 são `sync` e sete são `changed posts.json`; as outras duas tratam de IDs e demonstrações. Esses nomes genéricos não explicam o raciocínio editorial nem identificam ferramenta de geração.

## Há IA?

Encontramos dois commits com autor declarado “Cursor Agent”: [c79e17e](https://github.com/felippe-regazio/verifiqueosfatos/commit/c79e17e6112dc8fd877b2829381576213ff8c8dd) e [0f8691f](https://github.com/felippe-regazio/verifiqueosfatos/commit/0f8691fc6536b1e07e1e63568bd0ec94b5242e19). Eles modificam `index.html` e `sw.js`, não as checagens em `posts.json`.

São indícios explícitos de assistência ao desenvolvimento da interface nos metadados, não prova de que uma IA produziu os vereditos. Texto com aparência de resposta de chatbot, velocidade das alterações e a palavra `sync` não identificam modelo, prompt ou método. Alegações de terceiros sobre um suposto prompt não autenticado foram descartadas como prova.

Os dois workflows disponíveis validam estrutura do JSON e versão do cache. Nenhum consulta fontes ou verifica verdade factual. [Validação](https://github.com/felippe-regazio/verifiqueosfatos/blob/ac0b424f7413aebbb8f76d2a0bc8efb7a2df5da4/.github/workflows/validate-posts.yml), [cache](https://github.com/felippe-regazio/verifiqueosfatos/blob/ac0b424f7413aebbb8f76d2a0bc8efb7a2df5da4/.github/workflows/check-cache-version.yml).

## Discussão pública examinada

A consulta enumerou 77 issues/PRs e 109 comentários gerais de issues/PRs, em duas páginas da API. Nove comentários desse conjunto eram do perfil do mantenedor. Isso não inclui necessariamente comentários inline de revisão, redes sociais, mensagens privadas ou conteúdo apagado.

A [issue 77](https://github.com/felippe-regazio/verifiqueosfatos/issues/77) pergunta diretamente se a coleta, pesquisa e classificação são manuais ou automatizadas externamente. Estava aberta e com zero comentários na consulta. Não escrever “o autor se recusou a responder”: não houve contato nosso, prazo de resposta nem evidência de recusa.

A [issue 23](https://github.com/felippe-regazio/verifiqueosfatos/issues/23) pede tema, horário e fontes. Um comentário registra que o software recebeu suporte aos campos. Isso não demonstra preenchimento editorial: nenhum dos 75 registros usa `s`, `h` ou `a`.

A API de branches listou apenas `main`. Esse resultado não alcança forks, refs de PR não inspecionadas, commits removidos ou processos privados. Buscas públicas pelo domínio, coleta e possíveis ferramentas não localizaram explicação independente autenticada do método. A thread do X segue sem leitura direta confirmada; a imagem do usuário não revela a cadeia de produção.

## Inventário das referências explícitas

São dez URLs em dez registros, distribuídas por oito hosts: Estadão (1), g1 (2), notícias UOL (2), Fórum (1), O Globo (1), Intercept (1), CNN (1) e piauí (1). “Host” não significa oito organizações independentes. Não há URL direta de órgão público nesses dez links, embora o texto de outros registros cite órgãos como IBGE, TCU e Banco Central. A contagem não classifica orientação política nem credibilidade desses veículos.

| Posição no snapshot | Referência textual | Questão de rastreabilidade |
|---:|---|---|
| 63 | Estadão Verifica, boato de roubo de celular | Link a checagem secundária |
| 64 | g1, caso Ana Clara, 2021 | Fonte de época exige atualização para situação processual posterior |
| 66 | g1, ilha e disputa envolvendo Richarlison | Texto remete a disputa em andamento |
| 67 | UOL Confere, 20/01/2023 | Fonte sobre Dino/episódio de 2022 não comprova fala atribuída a Lula em debate de 2026 |
| 68 | Fórum, indicação na SPU | Reportagem citada; não equivale a documento de nomeação ou prova autônoma da indicação política |
| 69 | UOL, mensagens sobre presente | URL acessível; justificativa omite mensagem de agradecimento atribuída a Lula, indício que não prova conclusivamente a entrega |
| 70 | O Globo, marcação de munições | Reportagem citada; projeto legislativo primário não é vinculado no registro |
| 71 | Intercept, financiamento de Dark Horse | Fonte trata investigação; o excerto não explicita todo o nexo para o selo |
| 72 | CNN, alegação sobre filme de Lula | Ausência de depoimento formal/negação é resumida de modo mais conclusivo no cartão |
| 73 | piauí, passeio de barco | Reportagem citada; ausência de timecode do debate |

Cinco originais foram lidos diretamente (UOL/Dino, UOL/uísque, CNN, Intercept e piauí), um foi conferido por republicação atribuída ao Estadão no Terra e quatro não puderam ser lidos (dois g1, Fórum e O Globo). Bloqueio ou indisponibilidade da ferramenta não demonstra link falso. A piauí identifica Flávio Bolsonaro como participante do passeio; a frase do cartão usa apenas o sobrenome, o que deixa ambiguidade, mas data e episódio correspondem à reportagem.

Esses apontamentos não são vereditos factuais completos das dez alegações. O inventário está preservado em CSV com as URLs exatas.

### Exemplo novo: referência correta, episódio diferente

O registro 67 interpreta como ato falho uma frase atribuída a Lula no debate de 23/10/2026. O link inserido é uma checagem do UOL publicada em 20/01/2023 sobre uma fala de Flávio Dino em coletiva de novembro de 2022. Essa fonte pode contextualizar um boato antigo, mas não comprova o conteúdo, a intenção ou o contexto do debate de 2026. Falta a fonte específica desse segundo episódio. [Registro](https://github.com/felippe-regazio/verifiqueosfatos/blob/ac0b424f7413aebbb8f76d2a0bc8efb7a2df5da4/posts.json#L398), [UOL](https://noticias.uol.com.br/confere/ultimas-noticias/2023/01/20/flavio-dino-extincao-policia-militar-checagem.htm).

### Exemplo novo: evidência omitida no resumo

No registro 69, a justificativa menciona encomenda de presente, mas não o relato de agradecimento atribuído a Lula que a própria reportagem apresenta. Isso não confirma a entrega, mas é um indício relevante que não deveria desaparecer da síntese. [Fonte UOL](https://noticias.uol.com.br/politica/ultimas-noticias/2026/10/22/uisque-que-vorcaro-teria-dado-a-lula-custou-r-500-mil-apontam-mensagens.ghtm).

## Responsabilidade e comparação com Choquei

É legítimo discutir consequências da circulação de informação falsa, mas a investigação técnica não estabelece crime. O art. 323 do Código Eleitoral trata da divulgação, em propaganda ou período de campanha, de fatos sabidamente inverídicos relativos a partidos/candidatos e capazes de influenciar o eleitorado. Demonstrar incoerência não demonstra automaticamente ciência da falsidade e os demais elementos. A responsabilização civil também exige análise do ato, do dano e do nexo, conforme o regime aplicável. [Código Eleitoral](https://www.tse.jus.br/legislacao/codigo-eleitoral/codigo-eleitoral-1/codigo-eleitoral-lei-nb0-4.737-de-15-de-julho-de-1965), [Código Civil, arts. 186 e 927](https://www.planalto.gov.br/ccivil_03/leis/2002/l10406compilada.htm).

Sobre Jéssica Canedo, a cobertura da conclusão policial de 06/03/2024 informa que uma internauta foi indiciada por instigação ao suicídio e que o responsável pela Choquei não foi indiciado naquele inquérito. Não localizamos decisão judicial primária posterior para estabelecer o estado definitivo do caso. Não indiciamento não equivale a certificação de qualidade editorial nem prova ausência de outras ações. [CNN](https://www.cnnbrasil.com.br/nacional/caso-choquei-policia-conclui-que-jovem-morta-forjou-mensagens-a-humorista/), [Estadão/UOL](https://noticias.uol.com.br/ultimas-noticias/agencia-estado/2024/03/06/policia-conclui-inquerito-sobre-jovem-que-se-matou-apos-fake-news.htm).

Portanto, não há base nesta pesquisa para afirmar que a Choquei foi condenada pela morte, nem usar o episódio para atribuir crime ao Verifique os Fatos. O caso pode ser mencionado para discutir dever de apuração e consequências da amplificação, sem reduzir suicídio a uma causa única ou equiparar situações distintas. [Orientações da OMS para cobertura](https://www.who.int/publications/i/item/9789240076846).

## Perguntas que continuam sem resposta — roteiro de apuração, não enviado

1. Quem coleta e transcreve as falas, e onde estão os vídeos/timecodes?
2. Como são escolhidas as afirmações e tratadas repetições, propostas e opiniões?
3. Quem produz e quem revisa os vereditos? Há IA, modelos, prompts ou automação externa?
4. Quais documentos e consultas sustentam cada conclusão, especialmente onde faltam URLs?
5. Como são registradas correções e prevenidas referências a episódios diferentes?
6. Qual é a relação entre autoria dos commits e responsabilidade editorial?

Não é possível revelar processos privados apenas pelo código público. Essas lacunas exigem documentação adicional ou resposta do responsável. Nenhuma mensagem, issue, denúncia ou postagem foi enviada nesta investigação.
