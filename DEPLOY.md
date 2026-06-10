# Deploy no GitHub Pages com domínio dilterporto.com

## 1. Criar repositório no GitHub

1. Acesse [github.com/new](https://github.com/new)
2. Nomeie o repositório como `dilterporto.com` (ou `portfolio`)
3. Deixe **público** e clique em **Create repository**

## 2. Enviar os arquivos

```bash
git init
git add index.html
git commit -m "feat: initial personal site"
git remote add origin https://github.com/SEU_USUARIO/dilterporto.com.git
git push -u origin main
```

## 3. Ativar GitHub Pages

1. No repositório, vá em **Settings → Pages**
2. Em **Source**, selecione **Deploy from a branch**
3. Escolha branch `main` e pasta `/ (root)`
4. Clique em **Save**

## 4. Configurar domínio personalizado (dilterporto.com)

### No GitHub:
1. Em **Settings → Pages → Custom domain**, digite `dilterporto.com`
2. Clique em **Save** — isso cria automaticamente um arquivo `CNAME` no repositório

### No seu registrador de domínio (GoDaddy, Registro.br, Cloudflare, etc.):
Adicione os seguintes registros DNS:

**Registros A** (apontam o domínio raiz para o GitHub):
```
Tipo: A    Host: @    Valor: 185.199.108.153
Tipo: A    Host: @    Valor: 185.199.109.153
Tipo: A    Host: @    Valor: 185.199.110.153
Tipo: A    Host: @    Valor: 185.199.111.153
```

**Registro CNAME** (para o subdomínio www):
```
Tipo: CNAME    Host: www    Valor: SEU_USUARIO.github.io
```

> A propagação de DNS pode levar até 24h, mas geralmente ocorre em minutos.

## 5. Ativar HTTPS

Após o DNS propagar, volte em **Settings → Pages** e marque:
- ✅ **Enforce HTTPS**

---

## Personalizando o site

Abra o `index.html` e edite:

- **Nome e bio** — seção `<section class="hero">`
- **Experiências** — seção `<section id="experiencia">`
- **Links sociais** — atributos `href` dos `.social-link` (GitHub, LinkedIn)
- **Tecnologias** — tags `.skill-tag`
- **Posts do blog** — descomente o template na seção `<section id="blog">`

## Adicionando posts

Para cada post, crie um arquivo HTML (ex: `posts/meu-primeiro-post.html`) e adicione um link no `index.html`:

```html
<a class="post-item" href="/posts/meu-primeiro-post.html">
  <span class="post-title">Meu primeiro post</span>
  <span class="post-date">Jun 2026</span>
</a>
```
