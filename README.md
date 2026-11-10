<div align="center">

# SuperForça

### Design das jornadas do MVP

![Projeto acadêmico](https://img.shields.io/badge/Projeto-Acad%C3%AAmico-003e1f?style=for-the-badge)
![Design](https://img.shields.io/badge/UI%2FUX-Figma-ffc300?style=for-the-badge&logo=figma&logoColor=111111)
![Escopo](https://img.shields.io/badge/Escopo-MVP-2a6f97?style=for-the-badge)
![Licença](https://img.shields.io/badge/Licen%C3%A7a-MIT-c1121f?style=for-the-badge)

**Conectando supermercados a profissionais para demandas sazonais e emergenciais.**

[Abrir o protótipo no Figma](https://www.figma.com/design/sucf2wudh5FRUMSHeWhfTi/SuperFor%C3%A7a-%E2%80%94-Telas-do-MVP?node-id=0-1)

</div>

---

## ✨ Sobre o projeto

O **SuperForça** é a proposta de uma plataforma digital para aproximar supermercados de São Paulo e profissionais disponíveis para serviços temporários. O MVP explora as jornadas de quem publica oportunidades e de quem busca trabalho, considerando função, qualificação quando necessária, proximidade, disponibilidade e valor do serviço.

Este repositório documenta o **design das interfaces no Figma**. Não contém a aplicação implementada nem os arquivos-fonte do protótipo.

## 🎯 Objetivos

- Apoiar supermercados no atendimento a demandas sazonais e emergenciais.
- Ajudar profissionais a encontrar oportunidades compatíveis com seu perfil e disponibilidade.
- Centralizar publicação de vagas, candidaturas, convites, confirmação de participação e avaliações.

## 🧭 Jornadas do MVP

O arquivo atual do Figma reúne **134 frames em 10 jornadas**, além de 19 frames/componentes reutilizáveis e 25 frames de toasts e confirmações. O material está apresentado em desktop, com referência de 1280 px. Os diagramas abaixo resumem os caminhos principais; telas de erro, listas vazias, modais e menus abertos são estados alternativos das respectivas jornadas. Os índices em [`telas/`](telas/) detalham cada fluxo, suas siglas, estados e uma sequência de interação.

| # | Jornada | Principais etapas |
|---|---|---|
| 1 | **Entrada e acesso** | Página inicial, identificação por e-mail, login e recuperação de senha |
| 2 | **Cadastro do supermercado** | Tipo de conta, empresa, responsável, unidades, senha e conclusão |
| 3 | **Supermercado: publicar e preencher vagas** | Painel, publicação, candidaturas, sugestões, seleção e realização |
| 4 | **Supermercado: histórico e unidades** | Vagas concluídas ou encerradas, detalhes e gestão de unidades |
| 5 | **Supermercado: minha conta** | Dados da empresa, conta e segurança |
| 6 | **Cadastro do profissional** | Dados pessoais, endereço e região, funções, experiências e disponibilidade |
| 7 | **Profissional: encontrar vagas e se candidatar** | Oportunidades, filtros, detalhes e candidatura |
| 8 | **Profissional: convites, serviços e histórico** | Convites, candidaturas, serviços confirmados e avaliações |
| 9 | **Profissional: minha conta** | Perfil, disponibilidade, prévia para o supermercado e segurança |
| 10 | **Administrador** | Gestão de usuários, empresas, vagas e serviços, avaliações, indicadores e chamados |

### Acesso e cadastro

```mermaid
flowchart LR
    LP["LP-01 · Página inicial"] --> EMAIL["AC-01 · Identificação por e-mail"]
    EMAIL -->|"Já tem conta"| LOGIN["AC-02 · Login"]
    LOGIN -->|"Esqueceu a senha"| SENT["AC-03 · Recuperação enviada"]
    SENT --> RESET["AC-04 · Redefinição de senha"]
    RESET -->|"Link expirado"| EXPIRED["AC-04 · Link expirado"]
    RESET --> LOGIN
    EMAIL -->|"Criar conta"| TYPE["CD-01 · Tipo de conta"]
    TYPE -->|"Supermercado"| SM1["CD-E1 · Dados da empresa"]
    SM1 --> SM2["CD-E2 · Responsável"]
    SM2 --> SM3["CD-E3 · Unidades"]
    SM3 --> SM4["CD-02 · Senha e termos"]
    SM4 --> SM5["CD-03 · Cadastro concluído"]
    TYPE -->|"Profissional"| TR1["CD-P1 · Dados pessoais"]
    TR1 --> TR2["CD-P2 · Endereço e região"]
    TR2 --> TR3["CD-P3 · Funções e experiências"]
    TR3 --> TR4["CD-P4 · Disponibilidade"]
    TR4 --> TR5["CD-02 · Senha e termos"]
    TR5 --> TR6["CD-03 · Cadastro concluído"]
```

### Jornada do supermercado

```mermaid
flowchart LR
    PANEL["SM-01 · Painel de vagas"] --> PUBLISH["SM-02 · Publicar vaga"]
    PUBLISH --> DETAIL["SM-03 · Detalhes da vaga"]
    DETAIL --> APPLICATIONS["SM-03 · Candidaturas"]
    DETAIL --> SUGGESTED["SM-03 · Profissionais sugeridos"]
    APPLICATIONS --> PROFILE["SM-04 · Perfil do profissional"]
    SUGGESTED --> PROFILE
    PROFILE -->|"Aceitar candidatura"| CONFIRMED["Participação confirmada"]
    PROFILE -->|"Recusar candidatura"| DECLINED["Candidatura recusada"]
    PROFILE -->|"Enviar convite"| INVITATION["Convite enviado"]
    INVITATION -->|"Profissional aceita"| CONFIRMED
    CONFIRMED --> SERVICE["SM-05 · Realização, presença e avaliação"]
    SERVICE --> HISTORY["SM-06 · Histórico"]
    HISTORY --> HISTORY_DETAIL["SM-08 · Detalhe no histórico"]
    PANEL --> UNITS["SM-07 · Unidades"]
    PANEL --> ACCOUNT["SM-09 · Dados da empresa"]
    ACCOUNT --> SECURITY["SM-10 · Conta e segurança"]
```

### Jornada do profissional

```mermaid
flowchart LR
    OPPORTUNITIES["TR-02 · Oportunidades"] --> FILTERS["TR-03 · Filtros"]
    FILTERS --> RESULTS["TR-02 · Resultados"]
    RESULTS --> JOB["TR-04 · Detalhes e candidatura"]
    JOB -->|"Enviar candidatura"| APPLICATION["TR-06 · Minhas candidaturas"]
    INVITES["TR-05 · Convites recebidos"] -->|"Aceitar convite"| CONFIRMED["TR-06 · Serviços confirmados"]
    APPLICATION -->|"Selecionado"| CONFIRMED
    CONFIRMED --> DETAIL["TR-06 · Detalhe do serviço"]
    DETAIL --> HISTORY["TR-07 · Histórico e avaliações"]
    PROFILE["TR-01 · Perfil e disponibilidade"] --> PREVIEW["TR-01 · Prévia para o supermercado"]
    PROFILE --> ACCOUNT["TR-08 · Conta e segurança"]
```

### Jornada do administrador

```mermaid
flowchart LR
    USERS["AD-01 · Usuários"] --> USER_DETAIL["Detalhe e bloqueio de usuário"]
    USERS --> COMPANIES["AD-02 · Empresas"]
    USERS --> JOBS["AD-03 · Vagas e serviços"]
    USERS --> REVIEWS["AD-04 · Avaliações"]
    USERS --> METRICS["AD-05 · Indicadores"]
    USERS --> SUPPORT["AD-06 · Chamados"]
    COMPANIES --> COMPANY_DETAIL["Detalhe da empresa"]
```

O Figma também inclui telas de suporte para supermercado (SM-11) e profissional (TR-09), e uma área administrativa de chamados (AD-06), além de estados de bloqueio e reativação. Consulte a [análise de cobertura e lacunas](analise-figma.md) e o [protótipo](https://www.figma.com/design/sucf2wudh5FRUMSHeWhfTi/SuperFor%C3%A7a-%E2%80%94-Telas-do-MVP?node-id=0-1) para ver os frames e estados.

## 🎨 Identidade visual

O design combina uma linguagem **brutalista**, com contraste preto e branco, bordas espessas, cantos retos e sombras duras deslocadas em 4 px. Os títulos usam **Archivo Black** e os textos, **Inter**.

| Uso | Cor |
|---|---|
| Cabeçalhos e ações principais | Verde `#003E1F` |
| Destaques, como item ativo e valor da vaga | Amarelo `#FFC300` |
| Ações negativas | Vermelho `#C1121F` |
| Vaga aberta | Azul `#2A6F97` |
| Vaga preenchida | Mostarda `#E9C46A` |
| Vaga a registrar | Terracota `#E76F51` |
| Vaga concluída | Verde `#226F54` |
| Vaga encerrada | Vermelho `#C1121F` |

O arquivo do Figma também agrupa componentes reutilizáveis — botões, campos, selos de status, abas, cabeçalhos, cards e notificações — para manter as telas consistentes.

## 📌 Escopo e limites

- O Figma atual também inclui telas de **administrador** (AD-01 a AD-06), embora elas não apareçam no resumo anterior em PDF.
- As telas descritas estão em formato desktop, com largura de referência de 1280 px. Uma versão mobile não está definida no escopo documentado.
- Pagamentos são realizados fora da plataforma no MVP.
- O foco inicial é a cidade de São Paulo, com possibilidade de expansão posterior para a Grande São Paulo.

## 📁 Materiais do repositório

O arquivo nativo do Figma está salvo como `index.fig`. O ZIP de origem fornece
uma imagem PNG por seção (não por frame); cada pasta em `telas/` contém essa
exportação e um `index.md` com diagrama de sequência, explicação das siglas e
descrição das telas/estados. As pastas `componentes/` e
`toasts-confirmacoes/` documentam elementos compartilhados sem tratá-los como
jornadas independentes.

```text
.
├── index.fig
├── README.md
├── LICENSE
├── analise-figma.md
├── canvas-superforca.md
├── pre-projeto.md
└── telas/
    ├── 01-entrada-acesso/
    ├── 02-cadastro-supermercado/
    ├── 03-publicar-preencher-vagas/
    ├── 04-historico-unidades/
    ├── 05-conta-supermercado/
    ├── 06-cadastro-profissional/
    ├── 07-encontrar-vagas/
    ├── 08-convites-servicos-historico/
    ├── 09-conta-profissional/
    ├── 10-administrador/
    ├── componentes/
    └── toasts-confirmacoes/
```

Os índices de cada pasta são o ponto de entrada para a documentação daquele
fluxo.

## 🎓 Contexto acadêmico

Projeto acadêmico da disciplina **Garantia da Qualidade de Software**, do curso de Ciência da Computação da **Universidade Anhembi Morumbi**.

## 📄 Licença

Distribuído sob a licença [MIT](LICENSE).
