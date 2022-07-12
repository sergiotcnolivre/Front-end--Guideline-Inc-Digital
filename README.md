# Front-end - Guideline - Inc. Digital
---
## 📖 Índice

1. [Git](#1-git)
2. [HTML](#2-html)
3. [CSS](#3-css)
4. [JavaScript](#4-javascript)
5. [Imagens](#5-imagens)
6. [WordPress](#6-wordpress)
7. [Deploy](#7-deploy)

<a name="git"></a>

## 1. Git

- 1.1 [Mensagens de  Commit](#11-commit-messages)

### 1.1 Mensagens de  Commit

Também usamos [mensagens de commit convencionais](https://www.conventionalcommits.org/en/v1.0.0/), ou seja, a mensagem de commit deve estar na forma de uma frase, sendo a primeira palavra uma ação, e o resto da frase um texto descritivo.


**✅ Bom:**

```powershell
git commit -m "feat: permite que o objeto de configuração fornecido estenda as configurações"
git commit -m "feat(lang): add tradução para ingles"
```

**❌ Ruim:**

```powershell
git commit -m "Add placeholder on input"
```

- 1.2 [Git Igore](#12-git-ignore)

### 1.2 Git Ignore

Sempre adicionar ao git ignore as pastas de configurações dos frameworks e uploads. Exemplo:

  * node_modules
  * vendor
  * uploads

**[⬆ voltar ao sumário](#-indice)**

---

<a name="html"></a>

## 2. HTML

Nossa principal referência para bons padrões HTML é [W3C](https://www.w3.org/TR/html/) e [MDN](https://developer.mozilla.org/en-US/docs/Web/HTML/Element), com esses documentos podemos aprender muito sobre semântica e outras boas práticas.

- 2.1 [HTML Escopo de Componente](#21-html-escopo-componente)

### 2.1 HTML Escopo de Componente

Quando iniciamos um novo componente, devemos usar uma tag semântica, como `section` ou `article` por exemplo

**✅ Bom:**

```html
<section class="component">
  <h1 class="title">Título</h1>
  <p>Parágrafo</p>
</section>
```

**❌ Ruim:**

```html
<div class="component">
  <h4 class="title">Título</h4>
  <p>Parágrafo</p>
</div>
```

- 2.2 [Acessibilidade e Performace  ](#22-acessibilidade-e-performace)

### 2.2 Acessibilidade e Performace

    * Utilizar os atributos height e width, melhorando o carregamento da página e ajudando no pagespeed
    * Utilizar o atributo alt e title, ajudando no SEO e acessibilidade
    * Melhorar este tópico

**✅ Bom:**

```html
<img src="..." height="200" width="400" title="Imagem de Dinossauro" alt="Imagem de um dinossauro herbivoro na floresta comendo uma planta.">
```

**❌ Ruim:**

```html
<div class="component">
  <h4 class="title">Título</h4>
  <p>Parágrafo</p>
</div>
```
**[⬆ voltar ao sumário](#-indice)**

---

<a name="css"></a>

## 3. CSS

As dicas abaixo podem ser usadas em qualquer framework ou pré-processador CSS, como SCSS, Styled Components e etc.

- 3.1 [Sintaxe de Código](#31-sintaxe-de-codigo))
- 3.2 [Ordem de Declaração](#32-ordem-de-declaracao)
- 3.3 [Nomes de Classes](#33-nome-de-classes)
- 3.4 [Boas Práticas](#34-boas-praticas)
- 3.5 [Media Queries](#35-media-queries)

### 3.1 Sintaxe de Código

Mantenha uma declaração por linha.

**✅ Bom:**

```css
.selector-1,
.selector-2,
.selector-3 {
  ...
}
```

**❌ Ruim:**

```css
.selector-1, .selector-2, .selector-3 {
  ...
}
```

Separe cada conjunto de regras por uma linha em branco.

**✅ Bom:**

```css
.selector-1 {
  ...
}

.selector-2 {
  ...
}
```

**❌ Ruim:**

```css
.selector-1 {
  ...
}
.selector-2 {
  ...
}
```

Use letras minúsculas e evite especificar unidades com valores zero.

**✅ Bom:**

```scss
.selector-1 {
  color: #aaaaaa;
  margin: 0;
}
```

**❌ Ruim:**

```scss
.selector-1 {
  color: #aaaaaa;
  margin: 0px;
}
```

### 3.2 Ordem de Declaração

As declarações devem ser adicionadas em ordem alfabética.

**✅ Bom:**

```css
.selector {
  background: #fff;
  border: #333 solid 1px;
  color: #333;
  display: flex;
  height: 200px;
  margin: 5px;
  padding: 5px;
  width: 200px;
}
```

**❌ Ruim:**

```css
.selector {
  padding: 5px;
  height: 200px;
  background: #fff;
  margin: 5px;
  width: 200px;
  color: #333;
  border: #333 solid 1px;
  display: flex;
}
```

### 3.3 Nomes de Classes

Mantenha a classe em letras minúsculas e use traços ou sublinhado para separar o nome da classe.

**✅ Bom:**

```css
.page-header { ... }
.page_header { ... }
```

**❌ Ruim:**

```css
.pageHeader { ... }
```

É uma boa ideia seguir uma [convenção de nomenclatura BEM](http://getbem.com/introduction/) para evitar conflitos com outros componentes.

O padrão principal é usar traço simples para nome do elemento, sublinhado duplo para bloco de elemento e traço duplo para modificação de estilo.

**✅ Bom:**

```css
/* Good */
.page-header__title { ... }
.page-header--active { ... }

.button--active { ... }
```

**❌ Ruim:**

```css
.page-header-title { ... }
.page-header-active { ... }

.active { ... }
.primary { ... }
```

Traços e sublinhados servem como quebras naturais na classe relacionada. Classe de prefixo com base no pai mais próximo ou na classe base.

**✅ Bom:**

```css
.nav { ... }
.nav__item { ... }
.nav__link { ... }
```

**❌ Ruim:**

```css
.item-nav { ... }
.link-nav { ... }
```

Evite dar nomes muito curtos para a classe e sempre escolha nomes significativos que forneçam a função de classe.

**✅ Bom:**

```css
.button { ... }
.page-header { ... }
.progress-bar { ... }
```

**❌ Ruim:**

```css
.s { ... }
.btn { ... }
.ph { ... }
.block { ... }
```

### 3.4 CSS Boas Práticas

Evite usar valores como cores, espaçamento e etc diretamente nos elementos, use variáveis ​​em vez disso, e podem ser variáveis ​​CSS.

**✅ Bom:**

```css
.button {
  color: var(--color-primary);
  padding: var(--space-sm);
}
```

**❌ Ruim:**

```css
.button {
  color: #333;
  padding: 16px;
}
```

Não estilize diretamente os elementos, isso criará muitos conflitos, sempre use classes.

**✅ Bom:**

```css
.form-control { ... }
.header { ... }
.section { ... }
```

**❌ Ruim:**

```css
input[type="text"] { ... }
header
section
```

Evite aninhar elementos, pois isso diminui o desempenho e aumenta a especificidade do CSS, sempre use classes.

**✅ Bom:**

```scss
.navbar { ... }
.nav { ... }
.nav__item { ... }
.nav__link { ... }
```

**❌ Ruim:**

```scss
.navbar ul { ... }
.navbar ul li { ... }
.navbar ul li a { ... }
```


**[⬆ voltar ao sumário](#-indice)**

---

<a name="javascript"></a>

## 4. JavaScript

**[⬆ voltar ao sumário](#-indice)**

---
<a name="imagens"></a>

## 5. Imagens

    * Sempre que possível utilizar formato .webp
    * Caso não seja possível o uso de .web, imagens com fundo transparente usar .png. Caso contrário .jpeg
    * Dimensionar imagem para o contexto no qual será utilizada.
    * Exportar imagem do layout salvando de forma otimizada (no PhotoShop, salvar para web)
    * Comprimir a imagem utilizando algum serviço. Sugestão, [TinyPNG](https://tinypng.com/)

**[⬆ voltar ao sumário](#-indice)**

---
<a name="wordpress"></a>

## 6. WordPress

### 6.1 Geral

    * Utilizar versão mais atual do WordPress
    * Indicar informações do tema no arquivo style.css 
    * Adicionar logomarca da Inc. Digital dentro da pasta do tema com o nome "screenshot.png"

### 6.2 Plugins mais usados

    * Advanced Custom Fields
    * Defender
    * Smush
    * Contact Form 7
    * Contact Form CFDB7
    * WP Mail SMTP

### 6.1 Configurações

    * Customizar painel de login com a logomarca do cliente
    * Adicionar favicon
    * Informações gerais (endereço, whatsapp, política de privacidade, etc...), devem estar no menu de Opções
    * Organizar os campos personalizados em abas. Usar nomes descritivos nas abas
    * Configurar SMTP
    * Chamar arquivos de estilo ou script, via functions.php da forma adequada.

**[⬆ voltar ao sumário](#-indice)**

---

<a name="deploy"></a>

## 7. Deploy

    * Sempre que possível, realizar o deploy da aplicação via git e adicionar a aplicação ao CloudFlare
    * Renomear o banco de dados de acordo com o ambiente. Ex: banco_dev, banco_hml, banco (produção)
    * Em projetos WordPress, executar o sql que realiza o update das informações no banco 
    * Em projetos Awesome, verificar permissôes das pastas e setar os novos valores no config.php
    * Limpar ambiente de homologação/desenvolvimento caso não estejam sendo utilizados

**✅ Bom:**

```powershell
192.168.0.1@root:~/htdocs/site.com.br/html$ git pull
```

**✅ Bom:**

    Caso não seja possível, zipar o arquivo, subir o arquivo único via ftp
    * Dar unzip no arquivo via ssh
    * Apagar .zip do servidor

**❌ Ruim:**

    * Subir arquivos manualmente via FTP   

**[⬆ voltar ao sumário](#-indice)**
