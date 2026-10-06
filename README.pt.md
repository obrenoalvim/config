<div align="center">

<img src=".github/logo.svg" alt="Logo do config" width="120" height="120">

# config

**Configuração pessoal de portfólio para o GitHub Portfolio Generator.**<br>
Um `portfolio.json` que define seu tema, texto "sobre", habilidades e linha do tempo de experiência. Use como modelo para o seu próprio repositório `config`.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/obrenoalvim/config?style=flat&logo=github&color=94a3b8)](https://github.com/obrenoalvim/config/stargazers)
[![Usado por](https://img.shields.io/badge/Usado_por-GitHub_Portfolio_Generator-a78bfa)](https://github.com/obrenoalvim/github-portfolio-generator)

[English](README.md) · **Português**

[Como funciona](#como-funciona) · [portfolio.json](#estrutura-do-portfoliojson) · [Uso](#uso) · [Perguntas frequentes](#perguntas-frequentes)

</div>

---

Configuração pessoal de portfólio consumida pelo [GitHub Portfolio Generator](https://github.com/obrenoalvim/github-portfolio-generator).

O gerador procura por um repositório público chamado `config` com um arquivo `portfolio.json` na raiz e o usa para personalizar o portfólio renderizado em `/<username>`: cores do tema, texto do "sobre", lista de habilidades e a linha do tempo de experiência profissional.

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

---

## Perguntas frequentes

**O repositório precisa se chamar `config`?**
Precisa. O gerador busca `https://api.github.com/repos/<username>/config/contents/portfolio.json`, então o nome do repositório e o nome do arquivo precisam bater.

**Precisa ser público?**
Precisa. O gerador lê pela API pública do GitHub.

**E se eu não criar?**
O portfólio usa dados puxados diretamente do seu perfil do GitHub.

**Quais campos são obrigatórios?**
Nenhum é marcado como obrigatório. Os valores que você informar substituem os padrões do gerador. Veja a [tabela de campos](#campos).

## Mais do mesmo autor

- [**github-portfolio-generator**](https://github.com/obrenoalvim/github-portfolio-generator): transforme qualquer perfil do GitHub num site de portfólio.
- [**linkedin-insights**](https://github.com/obrenoalvim/linkedin-insights): transforme a exportação de analytics do LinkedIn num dashboard.

## Licença

[MIT](LICENSE)

---

<div align="center">

Se isso te ajudou a montar o seu portfólio, uma ⭐ ajuda outras pessoas desenvolvedoras a encontrá-lo.

<sub>**Tópicos:** portfolio-config · github-portfolio · developer-portfolio · portfolio-json · configuration · json</sub>

</div>
