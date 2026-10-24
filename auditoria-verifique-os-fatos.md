# Verifique os Fatos: auditoria de dados, critérios e apresentação

**Recorte: 24/10/2026, resposta HTTP às 00:43:08, America/Fortaleza.** Commit `ac0b424f7413aebbb8f76d2a0bc8efb7a2df5da4`. Pesquisa com a skill ECC deep-research, inspeção local, navegador e fontes públicas. Firecrawl/Exa não estavam disponíveis; foram utilizados busca web, GitHub e leitura HTTP como alternativa.

## Conclusão

Há problemas demonstráveis de coerência editorial, rastreabilidade e apresentação estatística. A distribuição dos rótulos publicados é muito mais favorável a Lula. **Isso não demonstra, por si só, manipulação deliberada, falsificação dos dados de origem ou um algoritmo que atribui pesos diferentes aos candidatos.** O código aplica a mesma fórmula aos dois. Encontramos justificativas inadequadas em registros de ambos e revisões históricas que reduziram a pontuação de Lula e elevaram a de Flávio.

A formulação defensável é: **a plataforma apresenta resultados assimétricos e falhas que comprometem a auditabilidade; sua neutralidade editorial não foi demonstrada, e a intenção de favorecer candidato não foi comprovada nesta investigação.** Não confundir ausência de prova de manipulação com certificação de imparcialidade.

## O que foi examinado

- Todos os 75 registros da base capturada: contagem, campos, leitura de coerência entre fala e justificativa, referências e repetição temática.
- HTML/JavaScript, cálculo do Fatômetro, ordenação, compartilhamento, validador e testes; histórico público de alterações dos dados.
- Comparação entre `posts.json` público e o repositório; comparação do HTML público; verificação do resultado no navegador.
- Amostra dirigida de problemas editoriais, com consultas a fontes externas. **Não foi feita rechecagem factual independente integral de todas as 75 falas, nem transcrição audiovisual integral do debate.** A amostra de problemas não estima a taxa de erro da base.
- Issues e PRs pertinentes, usados como pistas e registro de discussão, nunca como prova autônoma de acusações.

O JSON de produção e o JSON do commit eram semanticamente iguais. O HTML era idêntico byte a byte. Isso confirma correspondência naquele acesso, não auditoria dos servidores, de outras regiões, de versões anteriores ou do processo privado de produção das checagens.

O post do X não pôde ser recuperado pela ferramenta (403). A imagem enviada pelo usuário foi tratada como registro fornecido, sem autenticação independente da thread. Nela, o autor apresenta uma iniciativa aberta e comunitária e ressalva que não é uma plataforma oficial. Isso contextualiza o projeto, mas não substitui critérios editoriais. Não houve contato nem publicação externa.

## 1. Distribuição da base e significado do placar

| Autor atribuído pelo campo n | Total | Verdadeiro | Parcial | Falso | Fatômetro |
|---|---:|---:|---:|---:|---:|
| Lula | 27 | 18 | 7 | 2 | 80% |
| Flávio | 48 | 2 | 22 | 24 | 27% |

Fonte: cálculo próprio sobre [snapshot versionado](https://github.com/felippe-regazio/verifiqueosfatos/blob/ac0b424f7413aebbb8f76d2a0bc8efb7a2df5da4/posts.json). O campo n identifica a pessoa a quem o site atribui a fala, não necessariamente o alvo da acusação.

O Fatômetro calcula `(verdadeiros + 0,5 × parciais) / total × 100`, com arredondamento, para ambos. Lula: 79,63%; Flávio: 27,08%. A proporção de registros estritamente classificados como verdadeiros é, respectivamente, **66,67% e 4,17%**. A interface acessível descreve a média como percentual verdadeiro. Não são a mesma medida. [Cálculo e rótulo](https://github.com/felippe-regazio/verifiqueosfatos/blob/ac0b424f7413aebbb8f76d2a0bc8efb7a2df5da4/index.html#L205).

A média ponderada é uma escolha editorial, não uma medição validada da honestidade global de uma pessoa. O código não demonstra que “parcial” corresponde a exatamente metade de uma verdade. Tampouco a base representa todas as declarações: não há universo elegível publicado, taxa de inclusão, recorte de seleção ou regra documentada para repetições. Os registros 31 e 32, por exemplo, abordam a mesma projeção de juros. Sem timecodes, não sabemos se são repetição real no debate ou dupla entrada; ambos contam para o indicador.

Mais checagens negativas de um candidato podem decorrer de mais afirmações falsas, seleção editorial, erros de classificação ou combinação desses fatores. O número bruto não separa as hipóteses. O [IFCN](https://ifcncodeofprinciples.poynter.org/the-commitments) pede critérios consistentes e transparência; a [AFP](https://factcheck.afp.com/How-we-work) explica que contagens podem variar conforme relevância e circulação de desinformação. Esses padrões são referências comparativas, não uma certificação alegada pelo projeto.

## 2. Fontes e rastreabilidade

Os 75 registros possuem apenas n, c, t e v. **Nenhum preenche s (fontes), e (errata), id, h (horário) ou a (assunto).** Dez registros contêm URL no texto da justificativa; os outros 65 não contêm URL HTTP(S). Há menções nominais a instituições e jornais, por isso seria incorreto dizer que todos estão “sem qualquer referência”.

O front tem recursos para fontes clicáveis e erratas, mas a base não os usa. URLs inseridas em v são texto escapado, não o bloco de links previsto em s. Não existe identificação de checador/revisor por registro nem timecode para reencontrar a fala. [Renderização das fontes e correções](https://github.com/felippe-regazio/verifiqueosfatos/blob/ac0b424f7413aebbb8f76d2a0bc8efb7a2df5da4/index.html#L154).

O código público exibe classificações previamente inseridas; não faz investigação factual automática. Não localizamos no repositório um pipeline de pesquisa/LLM que permita auditar como cada conclusão foi produzida. Isso não prova uso ou não uso de IA: o processo pode ocorrer fora do repositório. A [issue 77](https://github.com/felippe-regazio/verifiqueosfatos/issues/77) faz essa pergunta e estava sem comentários na consulta.

## 3. Casos concretos

Os números abaixo são posições de 1 a 75 no arquivo preservado, **não IDs estáveis do site**. A análise se limita à proposição cadastrada; contexto ausente pode mudar a avaliação da fala original.

| Registro | Achado | O que a evidência permite dizer |
|---|---|---|
| 10, Flávio, falso | A fala sobre morar em palácio é respondida com a informação de que o imóvel é residência oficial e não propriedade pessoal | A justificativa refuta propriedade, que não consta na afirmação cadastrada; não estabelece critério para o adjetivo luxo |
| 18, Lula, verdadeiro | Trazer a indústria automobilística ao Nordeste é justificado com expansão/consolidação posterior | O texto não prova pioneirismo; a Ford em Camaçari antecede a primeira presidência Lula. Pode faltar contexto específico sobre outra fábrica |
| 53 e 55, Lula, parcial/verdadeiro | Uma contagem é relativizada por incluir quadras/reformas; outra usa obras de educação básica para validar escolas | Há inconsistência de escopo dentro das checagens de um mesmo candidato |
| 47, Lula, parcial | Uma fala sobre anúncio de perdão de R$15 bilhões recebe explicação sobre leis de criação do MEI e participação do Congresso | A justificativa não verifica o valor nem o anúncio registrado |
| 29, Flávio, falso | A verificação reconhece aumento de preços, mas responde com renda/poder de compra e cita fala do adversário | Preços e poder de compra são variáveis distintas; o universal “tudo” também precisaria ser delimitado |
| 37 e 30/65, Lula verdadeiro e Flávio falso | Um plano de compra de dívidas é confirmado como anúncio; propostas de Flávio são rejeitadas com histórico ou existência prévia de programa | Possível aplicação de critérios diferentes a intenções futuras. Necessária regra uniforme: verificar anúncio, viabilidade ou cumprimento são tarefas distintas |
| 4, Lula, falso | A negativa de Flávio sobre pedir tarifas é usada como refutação | Autodeclaração, sozinha, é insuficiente. Esse problema beneficia Flávio, contraponto importante |
| 33, Flávio, parcial | O texto nega que CadÚnico seja benefício, mas o selo é parcial | Também há aparente tolerância na classificação de uma fala de Flávio; contexto completo pode explicar |
| 71, Flávio, falso | O excerto sobre Dark Horse trata de financiamento ligado a fraude; a frase cadastrada trata de origem pública e declaração da PF | O texto exibido não explicita o nexo completo. Ilegal e público não são sinônimos; isso não prova que os recursos eram privados ou lícitos |
| 72, Flávio, falso | A justificativa sobre filme de Lula resume a negativa de advogados como refutação da acusação | A fonte citada distingue ausência de depoimento formal, autenticidade não reconhecida e alegação de financiamento. Negativa/ausência de confirmação não basta, sozinha, para provar falsidade |

Evidência dos registros: [palácio](https://github.com/felippe-regazio/verifiqueosfatos/blob/ac0b424f7413aebbb8f76d2a0bc8efb7a2df5da4/posts.json#L56), [indústria](https://github.com/felippe-regazio/verifiqueosfatos/blob/ac0b424f7413aebbb8f76d2a0bc8efb7a2df5da4/posts.json#L104), [escolas](https://github.com/felippe-regazio/verifiqueosfatos/blob/ac0b424f7413aebbb8f76d2a0bc8efb7a2df5da4/posts.json#L314), [MEI](https://github.com/felippe-regazio/verifiqueosfatos/blob/ac0b424f7413aebbb8f76d2a0bc8efb7a2df5da4/posts.json#L278), [preços](https://github.com/felippe-regazio/verifiqueosfatos/blob/ac0b424f7413aebbb8f76d2a0bc8efb7a2df5da4/posts.json#L170), [propostas](https://github.com/felippe-regazio/verifiqueosfatos/blob/ac0b424f7413aebbb8f76d2a0bc8efb7a2df5da4/posts.json#L218), [tarifas](https://github.com/felippe-regazio/verifiqueosfatos/blob/ac0b424f7413aebbb8f76d2a0bc8efb7a2df5da4/posts.json#L20), [CadÚnico](https://github.com/felippe-regazio/verifiqueosfatos/blob/ac0b424f7413aebbb8f76d2a0bc8efb7a2df5da4/posts.json#L194), [filmes](https://github.com/felippe-regazio/verifiqueosfatos/blob/ac0b424f7413aebbb8f76d2a0bc8efb7a2df5da4/posts.json#L422).

Corroboração externa: a [Agência Senado, em 2001](https://www12.senado.leg.br/noticias/materias/2001/09/24/paulo-souto-bahia-entra-em-novo-ciclo-de-desenvolvimento-industrial), registrou a instalação da Ford na Bahia. O [relatório de gestão FNDE 2025](https://www.gov.br/fnde/pt-br/acesso-a-informacao/transparencia-e-prestacao-de-contas/prestacao-de-contas-anual/2025/relatorio-de-gestao-2025-versao-anual-adb-2.pdf) explica os universos de 3.641 e 2.001 obras adicionais, totalizando 5.642, incluindo tipologias além de escolas. O problema demonstrado é de escopo, não uma afirmação de que esses números foram inventados.

As reportagens do [Intercept](https://www.intercept.com.br/2026/10/23/documento-pf-flavio-dinheiro-ilegal-vorcaro-dark-horse/) e da [CNN](https://www.cnnbrasil.com.br/eleicoes/vorcaro-cita-r-30-milhoes-a-filme-de-lula-o-que-sabemos-ate-agora/) foram consultadas integralmente no texto acessível. A primeira traz investigação além do excerto e registra diligências sobre o percurso dos recursos; a segunda distingue o relato divulgado de sua formalização perante autoridades. Esta auditoria não teve acesso autônomo ao despacho completo da PF e não resolve as acusações sobre financiamento.

## 4. Histórico e contrapontos

O histórico contém mudanças de classificação, e elas não caminham todas na mesma direção. Por exemplo, a fala de Lula sobre Flávio pedir tarifas passou de verdadeiro a falso; seu registro sobre suposto emprego fantasma passou de verdadeiro a parcial. Há também revisões de falso para parcial em falas de Flávio. A ausência de errata no snapshot dificulta que o leitor comum perceba essas revisões. Histórico Git disponível é útil, mas não equivale a correção destacada no cartão.

Os exemplos iniciais foram alvo de uma [PR sobre neutralidade](https://github.com/felippe-regazio/verifiqueosfatos/pull/3). O autor [aceitou alterar os selos demonstrativos para verdadeiro para ambos](https://github.com/felippe-regazio/verifiqueosfatos/pull/3#issuecomment-6369688025), e existe commit correspondente. Não é correto usar o exemplo inicial isolado como prova de que o código atual força Lula a verdadeiro e Flávio a falso.

A [issue 68](https://github.com/felippe-regazio/verifiqueosfatos/issues/68) registra críticas editoriais; algumas já foram corrigidas no snapshot. Comentários ofensivos de terceiros e supostos prompts sem autenticação não foram usados como evidência de intenção.

### Verificação técnica adicional

O validador executado sobre a base real falha com 75 erros de ID ausente. Os 16 testes unitários do validador passam; eles testam estrutura, não veracidade. A interface aceita registros sem ID e usa posição do array como alternativa no compartilhamento. Uma remoção ou reordenação pode mudar o alvo de um link antigo. Não foi verificada a configuração remota de bloqueio de deploy/merge.

As imagens de compartilhamento limitam a justificativa a quatro linhas e não incluem o campo de fontes nem a errata. Isso pode retirar ressalvas quando um cartão circula separado do site; o comportamento vale para ambos os candidatos. [Código de compartilhamento](https://github.com/felippe-regazio/verifiqueosfatos/blob/ac0b424f7413aebbb8f76d2a0bc8efb7a2df5da4/share.js#L195).

Nove mudanças de rótulo foram encontradas comparando falas de texto idêntico no histórico, excluindo demonstrações: quatro reduziram a pontuação de Lula, duas reduziram a de Flávio e três elevaram a de Flávio. A comparação não captura revisões que mudam o próprio texto da fala. Exemplos: [tarifas](https://github.com/felippe-regazio/verifiqueosfatos/commit/2c6d1de8693260e0e16b6d0dfd5e2146740f95e2), [emprego fantasma](https://github.com/felippe-regazio/verifiqueosfatos/commit/9b71782792e14ed74f5d6766d77051229a48bbb0), [SUS](https://github.com/felippe-regazio/verifiqueosfatos/commit/0066ff40b5147a31c241a2637c33d1bacd0d78a8). Essas mudanças foram verificadas no Git, não revalidadas factualmente em sua totalidade.

## 5. O que falta para concluir sobre viés global

É necessário definir todas as falas verificáveis do debate, documentar exclusões e repetições, recuperar vídeo/timecode, separar afirmações factuais de opiniões/promessas e reclassificar com a mesma rubrica e revisão independente. Uma etapa pode ocultar a identidade do autor quando isso não retirar contexto indispensável. Depois, comparar inclusão e erro entre candidatos, temas e tipos de afirmação. Igualar artificialmente o número de verdadeiros e falsos não é solução.

Também faltam explicações públicas suficientemente detalhadas sobre quem seleciona, pesquisa, revisa e publica; ferramentas externas utilizadas; tratamento de conflito de interesses; revisão de selos; e razão para converter parcial em 0,5. Sem isso, não se pode medir com rigor quanto da assimetria vem dos fatos e quanto vem do processo editorial.

## Perguntas prontas para enviar ao responsável — não enviadas

1. Como as falas foram selecionadas e onde estão suas transcrições/timecodes?
2. Quem pesquisou e revisou cada registro, e quais ferramentas foram usadas?
3. Qual regra distingue falso, parcial e sem evidência suficiente, inclusive para propostas?
4. Por que os 75 registros não utilizam fontes estruturadas, IDs e erratas já suportados?
5. Como justificar os exemplos de descompasso acima e o rótulo percentual do Fatômetro?

## Evidências preservadas

- `posts-snapshot-2026-10-24.json`: cópia da base pública, SHA-256 `3d068df18fadbdc9c976561cdfcb2840e0a406e5d134b9d40a17ffc44f760cf8`.
- `base-auditada.csv`: 75 registros, rótulos, justificativas e links permanentes por linha.
- `manifesto-evidencias.json`: contagens, versão e comparações.
- `index-snapshot-2026-10-24.html` e `site-auditado.png`: interface capturada.

O material é uma auditoria pública de escopo definido. Não é perícia da infraestrutura, auditoria eleitoral, certificação jornalística ou prova de intenção do mantenedor.
