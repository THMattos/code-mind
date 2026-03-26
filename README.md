# 🧠 code-mind — Portfólio de Thiago de Mattos

> Página de portfólio pessoal com visual tech/IA, animações e blog de posts sobre desenvolvimento web. Feita do zero com HTML, CSS e JavaScript puro.

![HTML](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)
![Status](https://img.shields.io/badge/status-online-brightgreen)

---

## 📋 Índice

- [Sobre o Projeto](#-sobre-o-projeto)
- [Funcionalidades](#-funcionalidades)
- [Estrutura de Arquivos](#-estrutura-de-arquivos)
- [Como Funciona — HTML](#-como-funciona--indexhtml)
- [Como Funciona — CSS](#-como-funciona--cssstylesscss)
- [Como Funciona — JavaScript](#-como-funciona--jsmainjs)
- [Melhorias Realizadas](#-melhorias-realizadas)
- [Como Rodar Localmente](#-como-rodar-localmente)
- [Como Publicar no GitHub Pages](#-como-publicar-no-github-pages)
- [Personalização](#-personalização)
- [Contato](#-contato)

---

## 📖 Sobre o Projeto

Portfólio pessoal desenvolvido com **HTML, CSS e JavaScript puro**, com tema visual inspirado em tecnologia e inteligência artificial. A página apresenta informações pessoais, habilidades técnicas, posts de blog e formas de contato — tudo em um design moderno com animações e efeitos visuais.

🌐 **Acesse online:** [THMattos.github.io/code-mind](https://THMattos.github.io/code-mind/)

---

## ✨ Funcionalidades

| Funcionalidade | Descrição |
|---|---|
| 🌌 Fundo animado | Partículas conectadas por linhas se movendo no fundo da tela |
| 🟢 Badge "Disponível" | Indicador pulsante de disponibilidade para estágio |
| 💻 Cards de código flutuantes | Trechos de HTML, CSS e JS flutuando ao lado do avatar |
| 📊 Barras de habilidade | Skills com barras de progresso animadas |
| 📝 Blog de posts | Cards com posts sobre HTML, CSS e JavaScript |
| 📬 Seção de contato | Links para todas as redes sociais e e-mail |
| 🎞️ Animação de entrada | Cards aparecem suavemente ao rolar a página |
| 📱 Responsivo | Layout adaptado para celular e desktop |

---

## 📁 Estrutura de Arquivos

```
/
├── index.html        → Estrutura completa da página
├── css/
│   └── styles.css    → Todos os estilos, cores e animações
└── js/
    └── main.js       → Animação de partículas, scroll e interatividade
```

---

## 🧱 Como Funciona — `index.html`

O HTML define a **estrutura** de toda a página, dividida em seções.

### `<head>` — Configurações invisíveis

```html
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```
- `charset="UTF-8"` → suporta acentos e emojis
- `viewport` → faz a página funcionar bem em celulares

```html
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono..." rel="stylesheet" />
```
Importa duas fontes do Google Fonts: **JetBrains Mono** (usada nos elementos de código) e **DM Sans** (usada nos textos gerais).

---

### Fundo animado

```html
<canvas id="bg-canvas"></canvas>
<div class="noise"></div>
```
- `<canvas>` → elemento onde o JavaScript desenha as partículas animadas
- `.noise` → div com textura granulada aplicada via CSS para dar profundidade visual

---

### Navbar

```html
<nav id="navbar">
  <a class="nav-brand" href="#">&lt;THMattos/&gt;</a>
  <ul class="nav-list">
    <li><a href="#sobre">Sobre</a></li>
    ...
  </ul>
</nav>
```
A navbar é fixa no topo (`position: fixed`) e usa `backdrop-filter: blur` para criar o efeito de vidro fosco. Os links usam âncoras (`#sobre`, `#skills`) para navegar entre seções da mesma página.

---

### Seção Hero (apresentação)

A seção principal tem dois lados: texto à esquerda e visual à direita.

**Lado esquerdo — texto:**
```html
<p class="hero-tag"><span class="tag-dot"></span> Disponível para estágio</p>
<h1 class="hero-title">Olá, eu sou <span class="hero-name">Thiago de Mattos</span></h1>
```
O `tag-dot` é um círculo verde pulsante que indica disponibilidade. O nome tem gradiente de cor aplicado via CSS.

**Lado direito — visual:**
```html
<div class="avatar-frame">
  <div class="avatar-glow"></div>
  <img src="..." class="hero-avatar" />
  <div class="avatar-badge">...</div>
</div>
<div class="code-float code-float-1">...</div>
```
O `avatar-glow` é um anel com gradiente cônico que gira em volta da foto. Os `code-float` são cards de código que flutuam ao redor do avatar com animações CSS independentes.

---

### Seção Skills

```html
<div class="skill-card">
  <div class="skill-icon">🌐</div>
  <h3>HTML5</h3>
  <p>Descrição...</p>
  <div class="skill-bar"><div class="skill-fill" style="--w: 75%"></div></div>
</div>
```
Cada card tem uma barra de progresso. A porcentagem é passada via **CSS custom property** (`--w: 75%`) diretamente no HTML, e a barra se anima de 0% até esse valor ao carregar.

---

### Seção Posts (Blog)

```html
<article class="post-card post-featured">
  <div class="post-meta">
    <span class="post-tag tag-css">CSS</span>
    <span class="post-date">04 Out 2023</span>
  </div>
  <h3 class="post-title">O que é CSS?</h3>
  <p class="post-excerpt">...</p>
  <div class="post-footer">
    <span class="post-read">4 min de leitura</span>
    <a href="#" class="post-link">Ler mais →</a>
  </div>
</article>
```
Cada post usa `<article>` (tag semântica para conteúdo independente). A classe `post-featured` aplica um estilo diferenciado com borda roxa. O card `.post-soon` fica com opacidade reduzida indicando conteúdo futuro.

---

### Seção Contato

```html
<div class="contact-box">
  <a href="mailto:thiagodemattos25@gmail.com" class="contact-btn contact-btn-highlight">
    <span class="cb-icon">@</span> Enviar e-mail
  </a>
</div>
```
O `href="mailto:"` abre o aplicativo de e-mail do usuário ao clicar. O botão de e-mail tem classe `contact-btn-highlight` que o destaca com a cor de acento.

---

### Footer

```html
<footer>
  <div class="footer-inner">
    <span class="footer-brand">&lt;THMattos /&gt;</span>
    <span class="footer-copy">Feito com ❤ por Thiago de Mattos · 2024</span>
    <a href="#sobre" class="footer-top">↑ Topo</a>
  </div>
</footer>
```
Footer completo com marca, crédito e botão de voltar ao topo — algo que estava **completamente vazio** no código original.

---

## 🎨 Como Funciona — `css/styles.css`

### Variáveis de cor

```css
:root {
  --bg:     #03050f;      /* fundo: preto azulado profundo */
  --accent: #00e5ff;      /* ciano elétrico (cor principal) */
  --accent2:#7b2fff;      /* roxo (cor secundária) */
  --green:  #00ff88;      /* verde neon (indicadores) */
  --text:   #e8eaf6;      /* branco levemente azulado */
  --muted:  #5c6080;      /* cinza (textos secundários) */
}
```
Todas as cores são variáveis CSS reutilizadas em todo o arquivo. Para mudar o tema, basta alterar aqui.

---

### Efeito de vidro na navbar

```css
header {
  background: rgba(3, 5, 15, 0.85);
  backdrop-filter: blur(16px);
  border-bottom: 1px solid var(--border);
}
```
`backdrop-filter: blur` cria o efeito de vidro fosco — o fundo atrás da navbar fica borrado, dando profundidade à interface.

---

### Nome com gradiente de texto

```css
.hero-name {
  background: linear-gradient(135deg, var(--text), var(--accent));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
```
Aplica um gradiente como se fosse a cor do texto — técnica que usa o fundo como "tinta" e torna o texto transparente para mostrar o gradiente por baixo.

---

### Anel giratório do avatar

```css
.avatar-glow {
  background: conic-gradient(from 0deg, var(--accent), var(--accent2), var(--accent));
  animation: spin 5s linear infinite;
}

@keyframes spin { to { transform: rotate(360deg); } }
```
`conic-gradient` cria um gradiente que vai rodando ao redor do centro como um cone. A animação `spin` gira o elemento 360° continuamente.

---

### Barras de habilidade animadas

```css
.skill-fill {
  width: var(--w);
  animation: grow-bar 1.2s ease both;
}

@keyframes grow-bar {
  from { width: 0; }
  to   { width: var(--w); }
}
```
A barra parte de largura zero e cresce até o valor definido no HTML (`--w: 75%`). O `both` no animation faz a barra começar em 0 antes da animação rodar.

---

### Animação de entrada com Intersection Observer

No JavaScript, cada card começa invisível e translado:
```js
el.style.opacity = '0';
el.style.transform = 'translateY(24px)';
```
Quando o card entra na tela, o `IntersectionObserver` adiciona os valores finais e o CSS faz a transição suavemente.

---

## ⚙️ Como Funciona — `js/main.js`

### Sistema de partículas

```javascript
function drawParticles() {
  // Desenha linhas entre partículas próximas (dist < 120px)
  // Desenha os pontos
  // Move cada ponto
  // Rebote nas bordas
  requestAnimationFrame(drawParticles);
}
```
- `requestAnimationFrame` → chama a função de desenho no próximo frame do navegador (~60 vezes por segundo), criando a animação fluida
- Cada partícula tem posição (x,y), velocidade (dx,dy) e transparência (alpha)
- Quando duas partículas estão a menos de 120px de distância, uma linha semitransparente é desenhada entre elas

---

### Navbar com sombra ao rolar

```javascript
window.addEventListener('scroll', () => {
  if (window.scrollY > 40) {
    navbar.style.boxShadow = '0 4px 32px rgba(0,0,0,0.4)';
  } else {
    navbar.style.boxShadow = 'none';
  }
});
```
Ao rolar mais de 40px, a navbar ganha uma sombra para destacá-la do conteúdo.

---

### Intersection Observer para animações

```javascript
const observer = new IntersectionObserver(entries => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.style.opacity = '1';
      entry.target.style.transform = 'translateY(0)';
      observer.unobserve(entry.target);
    }
  });
}, { threshold: 0.1 });
```
`IntersectionObserver` dispara quando um elemento entra na tela. `threshold: 0.1` significa que o callback roda quando 10% do elemento está visível. `unobserve` para de observar após a animação rodar.

---

## 🔧 Melhorias Realizadas

| Arquivo | Problema original | Correção |
|---|---|---|
| `index.html` | `lang="en"` com conteúdo em português | Corrigido para `lang="pt-BR"` |
| `index.html` | Título `"Projeto Portifolio"` com erro | Corrigido para `"Thiago de Mattos — Portfólio"` |
| `index.html` | Footer completamente vazio | Footer completo com marca, crédito e link ao topo |
| `index.html` | Links da navbar (`Works`, `Blog`, `Contact`) sem destino | Todos os links agora apontam para seções reais |
| `index.html` | Botão "Download Resume" sem função | Substituído por botão de contato funcional |
| `index.html` | Sem seção de habilidades | Adicionada seção Skills com barras de progresso |
| `index.html` | Sem links de contato organizados | Seção de contato completa com todos os perfis |
| `css/` | CSS básico sem visual marcante | Redesign completo com tema tech/IA |
| `js/` | Sem JavaScript | Adicionado: partículas, scroll, animações de entrada |

---

## 🚀 Como Rodar Localmente

1. Baixe os arquivos mantendo a estrutura de pastas:
   ```
   /index.html
   /css/styles.css
   /js/main.js
   ```
2. Dê dois cliques em `index.html`
3. Abre no navegador e já funciona!

> Não precisa de servidor, instalação ou dependências.

---

## 🌐 Como Publicar no GitHub Pages

1. Suba os arquivos no repositório mantendo a estrutura de pastas
2. Vá em **Settings → Pages**
3. Selecione branch `main` → pasta `/ (root)` → **Save**
4. Acesse em: `https://THMattos.github.io/code-mind/`

---

## 🎨 Personalização

### Trocar nome e cargo
Em `index.html`, altere os textos dentro de `.hero-title` e `.hero-subtitle`.

### Trocar a foto
Altere o atributo `src` da tag `<img class="hero-avatar">`.

### Mudar as cores do tema
Em `css/styles.css`, altere as variáveis no `:root`:
```css
:root {
  --accent:  #00e5ff; /* cor principal */
  --accent2: #7b2fff; /* cor secundária */
}
```

### Adicionar um post
Copie um bloco `<article class="post-card">` em `index.html` e altere o conteúdo.

### Ajustar o nível das skills
No HTML de cada `.skill-card`, altere o valor de `--w`:
```html
<div class="skill-fill" style="--w: 80%"></div>
```

---

## 📬 Contato

- 💼 [LinkedIn](https://www.linkedin.com/in/thiagodemattos-/)
- 🐱 [GitHub](https://github.com/THMattos)
- 📸 [Instagram](https://www.instagram.com/thmattosrj/)
- 🐦 [Twitter/X](https://twitter.com/thmattos38)
- 📧 thiagodemattos25@gmail.com

---

<p align="center">Feito com ❤ por <strong>Thiago de Mattos</strong></p>
