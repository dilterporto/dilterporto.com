# Changelog

## [Unreleased] — 2026-06-10

### Adicionado
- Internacionalização (i18n) com detecção automática de idioma via `navigator.language`
- Botão PT/EN no nav para alternar entre português e inglês manualmente
- Preferência de idioma persistida em `localStorage`
- Script de early-lang no `<head>` para evitar flash do idioma errado antes do JS carregar

### Corrigido
- SVG do ícone LinkedIn corrompido durante reescrita (path `0 1.729v` havia sido alterado para `0 .774v`)
- `aria-label` do botão de idioma agora atualiza junto com a troca de idioma
- `connect-src` da CSP estava incompleto — adicionados `googletagmanager.com` e `analytics.google.com`

### Melhorado
- JS migrado de `var`/`function(){}` para `const`/`let` e arrow functions

---

## [0.4.0] — 2026-06-10

### Segurança
- Removido campo `email` do JSON-LD para reduzir exposição a bots de spam
- E-mail no footer substituído por label genérico ("Contato") — link `mailto:` mantido funcional
- Comentário HTML com template interno de posts removido do HTML público
- `rel="noopener noreferrer"` adicionado nos links externos (GitHub, LinkedIn)
- Content Security Policy (CSP) adicionada via `<meta http-equiv>`

---

## [0.3.0] — 2026-06-10

### Adicionado
- Metatags de SEO: `author`, `robots`, `canonical`
- Open Graph (`og:type`, `og:url`, `og:title`, `og:description`, `og:locale`)
- Twitter Card (`twitter:card`, `twitter:title`, `twitter:description`)
- Dados estruturados JSON-LD (`schema.org/Person`) com nome, cargo, URL e perfis sociais

---

## [0.2.0] — 2026-06-10

### Adicionado
- Google Analytics 4 (Measurement ID: `G-Q3RG3MN075`)

---

## [0.1.0] — 2026-06-10

### Adicionado
- Site pessoal estático em HTML/CSS — portfólio e blog
- Configuração de domínio personalizado via arquivo `CNAME` (`dilterporto.com`)
