English | [Português](README.pt.md)

# config

Personal portfolio configuration consumed by the [GitHub Portfolio Generator](https://github.com/obrenoalvim/github-portfolio-generator).

The generator looks for a public repo named `config` with a `portfolio.json` file at its root and uses it to customize the portfolio rendered at `/<username>` — theme colors, the about text, the skills list and the professional experience timeline.

## How it works

When you open the portfolio for a user, the generator fetches:

```
https://api.github.com/repos/<username>/config/contents/portfolio.json
```

If the file exists, its values override the defaults (theme, about, skills, experience). If it does not, the portfolio falls back to data pulled straight from the GitHub profile.

## `portfolio.json` structure

```json
{
  "theme": {
    "primaryColor": "#003a45",
    "backgroundColor": "#F8FAFC",
    "textColor": "#0F172A"
  },
  "sections": {
    "about": "Full-Stack Web Developer",
    "skills": ["TypeScript", "React", "Next", "Node", "C#", ".NET", "Laravel", "PostgreSQL"],
    "featured": ["repo1", "repo2", "repo3"],
    "experience": [
      {
        "title": "Full-Stack Developer",
        "company": "Company",
        "period": "2023 - Present",
        "summary": "What you did and the impact it had."
      }
    ]
  },
  "social": {
    "linkedin": "your-username",
    "website": "https://yoursite.com",
    "email": "you@example.com"
  }
}
```

### Fields

| Field | Description |
|-------|-------------|
| `theme.primaryColor` | Accent color (links, icons) |
| `theme.backgroundColor` | Page background color |
| `theme.textColor` | Text color (optional) |
| `sections.about` | Short headline / about text |
| `sections.skills` | Skills shown as badges |
| `sections.featured` | Repo names to highlight (case-sensitive) |
| `sections.experience` | Experience timeline entries (`title`, `company`, `period`, `summary`) |
| `social.linkedin` | LinkedIn profile (username only) |
| `social.website` | Personal site/portfolio URL |
| `social.email` | Contact email |

## Usage

1. Create a **public** repo named `config` on your GitHub account.
2. Add a `portfolio.json` file at the root following the structure above.
3. Open `https://<portfolio-generator-host>/<your-username>` to see it applied.

See the generator repo for full details: [obrenoalvim/github-portfolio-generator](https://github.com/obrenoalvim/github-portfolio-generator).
