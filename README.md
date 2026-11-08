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

O arquivo atual do Figma organiza cerca de 70 frames desktop (1280 px) em **10 jornadas**, além da seção de componentes. Os diagramas abaixo resumem os caminhos principais; telas de erro, listas vazias, modais e menus abertos são estados alternativos das respectivas jornadas.

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
| 10 | **Administrador** | Gestão de usuários, empresas, vagas e serviços, avaliações e indicadores |

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
    COMPANIES --> COMPANY_DETAIL["Detalhe da empresa"]
```

O Figma atual inclui, portanto, telas administrativas — uma atualização em relação ao resumo em PDF disponível nos materiais do projeto. Consulte o [protótipo](https://www.figma.com/design/sucf2wudh5FRUMSHeWhfTi/SuperFor%C3%A7a-%E2%80%94-Telas-do-MVP?node-id=0-1) para ver todos os frames e estados.

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

- O Figma atual também inclui telas de **administrador** (AD-01 a AD-05), embora elas não apareçam no resumo anterior em PDF.
- As telas descritas estão em formato desktop, com largura de referência de 1280 px. Uma versão mobile não está definida no escopo documentado.
- Pagamentos são realizados fora da plataforma no MVP.
- O foco inicial é a cidade de São Paulo, com possibilidade de expansão posterior para a Grande São Paulo.

## 📁 Estrutura-alvo do repositório

A árvore abaixo é uma **proposta de organização** para os materiais do projeto. No momento, este repositório contém apenas `README.md` e `LICENSE`; os arquivos listados como alvo ainda precisam ser exportados, convertidos ou adicionados.

O arquivo nativo exportado do Figma usa a extensão `.fig`, então o nome sugerido é `index.fig`. Cada frame pode ser exportado como PNG para `telas/`, usando o identificador da tela no nome do arquivo. O PDF do Canvas e o pré-projeto em Markdown ficam na raiz.

```text
.
├── index.fig
├── README.md
├── LICENSE
├── canvas-superforca.pdf
├── pre-projeto.md
└── telas/
    ├── 01-LP-01-pagina-inicial.png
    ├── 01-AC-01-identificacao-por-email.png
    ├── 01-AC-02-login.png
    ├── 02-CD-01-tipo-de-conta.png
    ├── 02-CD-E1-dados-da-empresa.png
    ├── 03-SM-01-painel-de-vagas.png
    ├── 03-SM-02-publicar-vaga.png
    ├── 04-SM-06-historico.png
    ├── 05-SM-09-dados-da-empresa.png
    ├── 06-CD-P1-dados-pessoais.png
    ├── 06-CD-P4-disponibilidade.png
    ├── 07-TR-02-oportunidades.png
    ├── 08-TR-05-convites-recebidos.png
    ├── 09-TR-01-perfil-e-disponibilidade.png
    ├── 10-AD-01-usuarios.png
    ├── 10-AD-05-indicadores.png
    └── ... (demais telas e estados do Figma)
```

## 🎓 Contexto acadêmico

Projeto acadêmico da disciplina **Garantia da Qualidade de Software**, do curso de Ciência da Computação da **Universidade Anhembi Morumbi**.

## 📄 Licença

Distribuído sob a licença [MIT](LICENSE).
