# Análise do design no Figma

Esta análise considera o arquivo nativo `index.fig`, a árvore de nós disponível
na página **Telas** e o protótipo online. É uma revisão de cobertura visual e de
fluxos, não uma validação de regras de negócio nem de acessibilidade em todas as
telas.

## Cobertura observada

- 10 jornadas, com 134 frames principais.
- 13 frames e 6 símbolos reutilizáveis na seção Componentes.
- 25 frames na seção Toasts e confirmações.
- 172 PNGs individuais dos frames, armazenados junto aos índices de cada seção.
- 12 exportações PNG adicionais de seção, cada uma reunindo uma seção inteira.
- 7 pontos de início configurados no protótipo.
- Uma consulta às interações reportou ações de navegação em todas as seções
  (1.632 ações no total). Essa contagem comprova a existência de ligações, mas
  não valida se todos os destinos e decisões correspondem às regras esperadas.

## Pontos que precisam de decisão ou complemento

1. **Regras e validações de formulário:** explicitar campos obrigatórios,
   formatos, mensagens de erro, falha de envio e recuperação após erro para
   login, cadastro, publicação e edição.
2. **Estados de rede e carregamento:** documentar carregamento, indisponibilidade
   de resultados, falha de conexão, repetição e ações duplicadas. Estados vazios
   existem em algumas áreas, mas não equivalem a estados de falha.
3. **Ciclo de vida de vaga/serviço:** definir prazos de candidatura e convite,
   cancelamentos, desistência, não comparecimento, reabertura e efeitos sobre
   vagas preenchidas ou encerradas.
4. **Compatibilidade e filtros:** tornar explícitos requisitos eliminatórios,
   critérios das sugestões e o comportamento da busca ampliada, preservando
   requisitos obrigatórios conforme o pré-projeto.
5. **Privacidade e moderação:** definir visibilidade dos dados do profissional,
   permissões administrativas, justificativas e auditoria para bloqueios,
   reativações e tratamento de avaliações/chamados.
6. **Acessibilidade e responsividade:** o material está apresentado como desktop
   (referência de 1280 px); faltam especificações verificáveis para mobile,
   teclado/foco, contraste e tecnologias assistivas.
7. **Pagamento:** o pré-projeto informa que ocorre fora da plataforma. Manter
   esse limite explícito para que estados de serviço e indicadores não sugiram
   pagamento processado/confirmado pelo SuperForça.

## Atualizações do arquivo

O Figma atual contempla AD-06 (chamados) e telas de suporte SM-11/TR-09, além de
estados de bloqueio e reativação que não estavam descritos no README anterior.
As telas de cada seção e suas siglas estão nos
[índices em `ui-design/`](ui-design/).

## Limites desta revisão

Os sete pontos de início e as contagens de ações foram consultados via Figma MCP.
Não foi feita uma verificação manual clique a clique de todas as rotas; portanto,
não se afirma que o protótipo esteja sem links quebrados ou que todas as telas
tenham cobertura de erro. Os diagramas de sequência nos índices descrevem o
comportamento esperado em alto nível e identificam integrações conceituais, não
implementações existentes.
