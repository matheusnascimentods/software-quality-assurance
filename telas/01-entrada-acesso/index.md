# Entrada e acesso

Fluxo comum aos dois perfis: apresenta o serviço, identifica o e-mail e encaminha
para login, recuperação de senha ou cadastro.

![Exportação da seção Entrada e acesso](entrada-acesso.png)

## Sequência

```mermaid
sequenceDiagram
    actor Pessoa
    participant UI as SuperForça
    participant Auth as Autenticação (conceitual)
    Pessoa->>UI: Abre a página inicial (LP-01)
    Pessoa->>UI: Informa e-mail (AC-01)
    alt Já possui conta
        UI->>Pessoa: Exibe login (AC-02)
        Pessoa->>UI: Solicita recuperação (AC-03)
        UI->>Pessoa: Informa envio do link
        Pessoa->>UI: Redefine a senha (AC-04)
    else Ainda não possui conta
        UI->>Pessoa: Encaminha para tipo de conta (CD-01)
    end
    Pessoa->>Auth: Envia credenciais ou nova senha
    Auth-->>UI: Resultado de autenticação (a implementar)
```

O participante de autenticação representa o comportamento esperado do produto,
não uma integração implementada neste repositório. O Figma inclui estados de
senha incorreta, acesso bloqueado e link expirado.

## Telas e estados

| ID no Figma | Tela |
|---|---|
| `4:16` | LP-01 — Página inicial |
| `18:872` | AC-01 — Identificação por e-mail |
| `21:988` | AC-02 — Login |
| `52:1830` | AC-02 — Senha incorreta |
| `52:1861` | AC-02 — Acesso bloqueado |
| `52:1759` | AC-03 — Link de recuperação enviado |
| `52:1781` | AC-04 — Redefinição de senha |
| `52:1811` | AC-04 — Link expirado |

## Siglas

- **LP:** landing page, ou página inicial de apresentação.
- **AC:** acesso e autenticação.
- **CD:** cadastro.

Os IDs correspondem aos nós do [arquivo-fonte](../../index.fig). O protótipo
online começa em [AC-01](https://www.figma.com/design/sucf2wudh5FRUMSHeWhfTi/SuperFor%C3%A7a-%E2%80%94-Telas-do-MVP?node-id=18-872).
