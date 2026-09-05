[English](README.md) | Português

# config

Configuração pessoal de portfólio consumida pelo [GitHub Portfolio Generator](https://github.com/obrenoalvim/github-portfolio-generator).

O gerador procura por um repositório público chamado `config` com um arquivo `portfolio.json` na raiz e o usa para personalizar o portfólio renderizado em `/<username>` — cores do tema, texto do "sobre", lista de habilidades e a linha do tempo de experiência profissional.

## Como funciona

Ao abrir o portfólio de um usuário, o gerador busca:

```
https://api.github.com/repos/<username>/config/contents/portfolio.json
```

Se o arquivo existir, seus valores substituem os padrões (tema, sobre, habilidades, experiência). Se não existir, o portfólio usa dados puxados diretamente do perfil do GitHub.

## Estrutura do `portfolio.json`

```json
{
  "theme": {
    "primaryColor": "#003a45",
    "backgroundColor": "#F8FAFC",
    "textColor": "#0F172A"
  },
  "sections": {
    "about": "Desenvolvedor Full-Stack Web",
    "skills": ["TypeScript", "React", "Next", "Node", "C#", ".NET", "Laravel", "PostgreSQL"],
    "featured": ["repo1", "repo2", "repo3"],
    "experience": [
      {
        "title": "Desenvolvedor Full-Stack",
        "company": "Empresa",
        "period": "2023 - Atual",
        "summary": "O que você fez e o impacto que teve."
      }
    ]
  },
  "social": {
    "linkedin": "seu-usuario",
    "website": "https://seusite.com",
    "email": "voce@exemplo.com"
  }
}
```

### Campos

| Campo | Descrição |
|-------|-------------|
| `theme.primaryColor` | Cor de destaque (links, ícones) |
| `theme.backgroundColor` | Cor de fundo da página |
| `theme.textColor` | Cor de texto (opcional) |
| `sections.about` | Texto curto de apresentação |
| `sections.skills` | Habilidades exibidas como badges |
| `sections.featured` | Nomes dos repositórios a destacar (case-sensitive) |
| `sections.experience` | Itens da linha do tempo de experiência (`title`, `company`, `period`, `summary`) |
| `social.linkedin` | Perfil no LinkedIn (apenas usuário) |
| `social.website` | URL do site/portfólio pessoal |
| `social.email` | E-mail de contato |

## Uso

1. Crie um repositório **público** chamado `config` na sua conta do GitHub.
2. Adicione um arquivo `portfolio.json` na raiz seguindo a estrutura acima.
3. Abra `https://<host-do-portfolio-generator>/<seu-username>` para ver aplicado.

Veja o repositório do gerador para todos os detalhes: [obrenoalvim/github-portfolio-generator](https://github.com/obrenoalvim/github-portfolio-generator).
