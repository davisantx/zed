---
marp: true
theme: gaia
class: invert
paginate: true
style: |
  @import url('https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700;800&family=DM+Mono:wght@300;400;500&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap');

  :root {
    --bg-dark:    #0D0D0F;
    --bg-card:    #131317;
    --bg-mid:     #1A1A22;
    --accent:     #A78BFA;
    --accent-2:   #34D399;
    --accent-3:   #F472B6;
    --text-main:  #F0EEF8;
    --text-muted: #7B7A8E;
    --border:     rgba(167,139,250,0.15);
    --color-background: #0D0D0F;
    --color-background-code: #131317;
    --color-background-paginate: #0D0D0F;
    --color-foreground: #F0EEF8;
    --color-highlight: #A78BFA;
    --color-highlight-hover: #C4B5FD;
  }
 

  /* ── Força fundo escuro em TUDO — anula qualquer herança do tema ── */
  section,
  section *,
  section *::before,
  section *::after {
    box-sizing: border-box !important;
  }

  section {
    font-family: 'DM Sans', sans-serif !important;
    font-size: 30px !important;
    background-color: #0D0D0F !important;
    color: #F0EEF8 !important;
    padding: 44px 60px !important;
    overflow: visible !important;
    position: relative !important;
  }
  
  section::before {
    content: '' !important;
    position: absolute !important;
    inset: 0 !important;
    background:
      radial-gradient(ellipse 70% 50% at 85% 10%, rgba(167,139,250,0.08) 0%, transparent 60%),
      radial-gradient(ellipse 50% 40% at 10% 90%, rgba(52,211,153,0.06) 0%, transparent 55%) !important;
    pointer-events: none !important;
    z-index: 0 !important;
  }

  section::after {
    font-family: 'DM Mono', monospace !important;
    font-size: 10px !important;
    color: #7B7A8E !important;
    bottom: 18px !important;
    right: 60px !important;
    background: transparent !important;
  }

  /* ── Zera backgrounds brancos do tema em todos os elementos ── */
  section div, section span, section p,
  section ul, section ol, section li,
  section h1, section h2, section h3, section h4,
  section table, section thead, section tbody,
  section tr, section td, section th,
  section blockquote, section pre, section code,
  section figure, section figcaption, section header, section footer {
    background-color: transparent !important;
    background: transparent !important;
  }

  /* ── Headings ── */
  section h1, section h2, section h3 {
    font-family: 'Syne', sans-serif !important;
    letter-spacing: -0.03em !important;
    margin: 0 0 0.3em !important;
    color: #F0EEF8 !important;
  }

  section h1 { font-size: 3rem !important;    font-weight: 800 !important; line-height: 1.08 !important; }
  section h2 { font-size: 1.65rem !important; font-weight: 700 !important; }
  section h3 { font-size: 0.95rem !important; font-weight: 600 !important; color: #A78BFA !important; margin-bottom: 0.2em !important; }

  section p {
    font-size: 0.95rem !important;
    font-weight: 300 !important;
    line-height: 1.6 !important;
    color: #C2BFDA !important;
    margin: 0 0 0.55em !important;
  }

  section strong { color: #F0EEF8 !important; font-weight: 600 !important; }
  section em     { color: #34D399 !important; font-style: normal !important; font-weight: 400 !important; }

  section code {
    font-family: 'DM Mono', monospace !important;
    font-size: 0.82em !important;
    background-color: rgba(167,139,250,0.15) !important;
    border: 1px solid rgba(167,139,250,0.25) !important;
    border-radius: 5px !important;
    padding: 1px 5px !important;
    color: #C4B5FD !important;
  }

  section pre {
    background-color: #131317 !important;
    border: 1px solid rgba(167,139,250,0.15) !important;
    border-radius: 10px !important;
    padding: 14px 18px !important;
    font-family: 'DM Mono', monospace !important;
    font-size: 0.76rem !important;
    line-height: 1.55 !important;
    color: #A0E8C0 !important;
    overflow: hidden !important;
    margin: 0 !important;
  }

  section pre code {
    background: transparent !important;
    border: none !important;
    padding: 0 !important;
    color: #A0E8C0 !important;
    font-size: 1em !important;
  }

  section ul {
    list-style: none !important;
    padding: 0 !important;
    margin: 0 !important;
  }

  section ul li {
    padding: 0.28em 0 0.28em 1.4em !important;
    position: relative !important;
    font-size: 0.9rem !important;
    font-weight: 300 !important;
    color: #C2BFDA !important;
    line-height: 1.45 !important;
  }

  section ul li::before {
    content: '▸' !important;
    position: absolute !important;
    left: 0 !important;
    color: #A78BFA !important;
    font-size: 0.72em !important;
    top: 0.48em !important;
  }

  section hr {
    border: none !important;
    height: 1px !important;
    background: linear-gradient(90deg, #A78BFA 0%, transparent 100%) !important;
    margin: 0.9em 0 !important;
    opacity: 0.35 !important;
  }

  /* ── Tabelas de conteúdo (markdown) ── */
  section table:not(.cols) {
    width: 100% !important;
    border-collapse: collapse !important;
    font-size: 0.84rem !important;
  }

  section table:not(.cols) th {
    font-family: 'Syne', sans-serif !important;
    font-size: 0.72rem !important;
    font-weight: 700 !important;
    text-transform: uppercase !important;
    letter-spacing: 0.08em !important;
    color: #A78BFA !important;
    border-bottom: 1px solid rgba(167,139,250,0.15) !important;
    padding: 8px 12px !important;
    text-align: left !important;
    background: transparent !important;
  }
  
  section table:not(.cols) td {
    padding: 8px 12px !important;
    border-bottom: 1px solid rgba(255,255,255,0.01) !important;
    color: #C2BFDA !important;
    font-weight: 300 !important;
    background: transparent !important;
  }
  
  section table:not(.cols) {
    outline: 1px solid rgba(255,255,255,0.04) !important;
    outline-offset: 0px !important;
  }

  section table:not(.cols) td {
    padding: 8px 12px !important;
    border-bottom: none !important;        /* remove borda por linha */
    color: #C2BFDA !important;
    font-weight: 300 !important;
    background: transparent !important;
  }
  
  section table:not(.cols) th {
    border-bottom: 1px solid rgba(167,139,250,0.4) !important;  /* só o cabeçalho */
    padding: 8px 12px !important;
    /* resto igual */
  }
  
  section table:not(.cols) tbody tr {
    border-bottom: 1px solid rgba(255,255,255,0.04) !important;
  }

  .table-wrap {
    border: 1px solid rgba(255,255,255,1) !important;
    border-radius: 8px !important;
    overflow: overflow !important;
  }


  /* ── Blockquote ── */
  section blockquote {
    background-color: #131317 !important;
    border: 1px solid rgba(167,139,250,0.15) !important;
    border-left: 3px solid #A78BFA !important;
    border-radius: 10px !important;
    padding: 12px 18px !important;
    margin: 0.7em 0 0.7em !important;
    font-size: 0.9rem !important;
    color: #C2BFDA !important;
    font-style: normal !important;
  }

  section blockquote p      { margin: 0 !important; color: #C2BFDA !important; font-size: 0.9rem !important; }
  section blockquote strong { color: #A78BFA !important; }

  /* ════ SLIDE CLASSES ════ */

  section.hero {
    display: flex !important;
    flex-direction: column !important;
    justify-content: center !important;
    font-size: 26px !important;
    padding: 56px 68px !important;
    background-color: #0D0D0F !important;
  }

  section.hero h1 {
    font-size: 3.8rem !important;
    background: linear-gradient(135deg, #fff 30%, #A78BFA 70%, #34D399 100%) !important;
    -webkit-background-clip: text !important;
    -webkit-text-fill-color: transparent !important;
    background-clip: text !important;
    margin-bottom: 0.15em !important;
  }

  section.hero .subtitle {
    font-family: 'DM Mono', monospace !important;
    font-size: 0.88rem !important;
    color: #A78BFA !important;
    letter-spacing: 0.1em !important;
    text-transform: uppercase !important;
    margin-bottom: 1.2em !important;
    background: transparent !important;
  }

  section.hero p { max-width: 560px !important; font-size: 1rem !important; color: #A09EC0 !important; }

  section.divider {
    display: flex !important;
    flex-direction: column !important;
    justify-content: center !important;
    font-size: 25px !important;
    background-color: #1A1A22 !important;
  }

  section.divider h2 {
    font-family: 'Syne', sans-serif !important;
    font-size: 2.8rem !important;
    font-weight: 800 !important;
    letter-spacing: -0.04em !important;
    background: linear-gradient(120deg, #fff 0%, #A78BFA 100%) !important;
    -webkit-background-clip: text !important;
    -webkit-text-fill-color: transparent !important;
    background-clip: text !important;
    margin: 0 !important;
  }

  section.divider .label {
    font-family: 'DM Mono', monospace !important;
    font-size: 0.9rem !important;
    letter-spacing: 0.14em !important;
    text-transform: uppercase !important;
    color: #7B7A8E !important;
    margin-bottom: 0.5em !important;
    background: transparent !important;
  }

  section.closing {
    display: flex !important;
    flex-direction: column !important;
    justify-content: center !important;
    text-align: center !important;
    align-items: center !important;
    font-size: 25px !important;
    background-color: #0D0D0F !important;
  }

  section.closing h1 {
    font-size: 3.2rem !important;
    background: linear-gradient(135deg, #fff 20%, #A78BFA 60%, #34D399 100%) !important;
    -webkit-background-clip: text !important;
    -webkit-text-fill-color: transparent !important;
    background-clip: text !important;
  }

  section.closing p { max-width: 480px !important; text-align: center !important; }

  /* ════ COMPONENTS ════ */

  .card {
    background-color: #131317 !important;
    border: 1px solid rgba(167,139,250,0.15) !important;
    border-radius: 12px !important;
    padding: 16px 18px !important;
  }

  .card .num {
    font-family: 'Syne', sans-serif !important;
    font-size: 2.2rem !important;
    font-weight: 800 !important;
    color: #A78BFA !important;
    line-height: 1 !important;
    margin-bottom: 4px !important;
    background: transparent !important;
  }

  .card .label {
    font-family: 'DM Mono', monospace !important;
    font-size: 0.7rem !important;
    letter-spacing: 0.1em !important;
    text-transform: uppercase !important;
    color: #7B7A8E !important;
    background: transparent !important;
  }

  .card p { font-size: 0.82rem !important; margin: 6px 0 0 !important; color: #7B7A8E !important; line-height: 1.4 !important; }

  .tag {
    display: inline-block !important;
    font-family: 'DM Mono', monospace !important;
    font-size: 0.68rem !important;
    letter-spacing: 0.07em !important;
    text-transform: uppercase !important;
    padding: 3px 9px !important;
    border-radius: 100px !important;
    background-color: rgba(167,139,250,0.12) !important;
    border: 1px solid rgba(167,139,250,0.25) !important;
    color: #A78BFA !important;
    margin-right: 5px !important;
    margin-bottom: 5px !important;
  }

  .tag.green { background-color: rgba(52,211,153,0.1) !important;  border-color: rgba(52,211,153,0.25) !important;  color: #34D399 !important; }
  .tag.pink  { background-color: rgba(244,114,182,0.1) !important; border-color: rgba(244,114,182,0.25) !important; color: #F472B6 !important; }

  .feat {
    display: flex !important;
    align-items: flex-start !important;
    gap: 13px !important;
    padding: 12px 0 12px 0!important;
    border-bottom: 1px solid rgba(255,255,255,0.05) !important;
    background: transparent !important;
  }

  .feat:last-child { border-bottom: none !important; }

  .feat-icon {
    width: 34px !important;
    height: 34px !important;
    min-width: 34px !important;
    border-radius: 9px !important;
    background-color: rgba(167,139,250,0.12) !important;
    border: 1px solid rgba(167,139,250,0.2) !important;
    display: flex !important;
    align-items: center !important;
    justify-content: center !important;
    font-size: 1rem !important;
    margin-top: 1px !important;
  }

  .feat-body h3 { font-size: 0.88rem !important; color: #F0EEF8 !important; margin: 0 0 3px !important; background: transparent !important; }
  .feat-body p  { font-size: 0.8rem !important;  color: #7B7A8E !important; margin: 0 !important; line-height: 1.45 !important; }

  /* ── Tabela de layout de colunas (não-conteúdo) ── */
  table.cols, table.cols tr,
  table.cols td, table.cols th {
    border: none !important;
    background: transparent !important;
    padding: 0 12px 0px 12px !important;
    vertical-align: top !important;
    border-bottom: none !important;
  }

  
  .compare-col {
    background-color: #131317 !important;
    border: 1px solid rgba(167,139,250,0.15) !important;
    border-radius: 12px !important;
    padding: 16px 18px !important;
  }

  .compare-col.hl {
    border-color: rgba(167,139,250,0.4) !important;
    background-color: rgba(167,139,250,0.06) !important;
  }

  .compare-col h3 {
    font-size: 0.92rem !important;
    margin-bottom: 10px !important;
    padding-bottom: 10px !important;
    border-bottom: 1px solid rgba(167,139,250,0.15) !important;
    color: #F0EEF8 !important;
    background: transparent !important;
  }
  /* ── Tabelas de conteúdo (markdown) ── */
    section table:not(.cols) {
      width: 100% !important;
      border-collapse: collapse !important;
      font-size: 0.84rem !important;
    }
  
    /* Estilo do cabeçalho SEM bordas */
    section table:not(.cols) th {
      font-family: 'Syne', sans-serif !important;
      font-size: 0.72rem !important;
      font-weight: 700 !important;
      text-transform: uppercase !important;
      letter-spacing: 0.08em !important;
      color: #A78BFA !important;
      background: transparent !important;
      text-align: left !important;
      padding: 12px 12px !important;
      border: none !important; /* Remove a borda inferior do cabeçalho */
    }
    
    /* Estilo das células SEM bordas */
    section table:not(.cols) td {
      padding: 8px 12px !important;
      color: #C2BFDA !important;
      font-weight: 300 !important;
      background: transparent !important;
      border: none !important; /* Remove as bordas entre as linhas */
    }
  
    /* Garantia extra para remover qualquer borda aplicada diretamente na linha */
    section table:not(.cols) tr {
      border: none !important;
    }
  
    /* Mantém APENAS a borda externa do wrapper */
    .table-wrap {
      /* Usei 0.15 de opacidade para a borda branca ficar sutilmente visível. 
         Se quiser mais apagado, volte para 0.04 */
      border: 1px solid rgba(255, 255, 255, 0.15) !important; 
      border-radius: 8px !important;
      overflow: hidden !important; /* Impede que o fundo da tabela vaze pelas bordas arredondadas */
    }
  
---

<!-- _class: hero -->



# Zed
## O Editor que Pensa mais Rápido que o Desenvolvedor

<p>Construído em Rust do zero. Colaboração em tempo real nativa. GPU-accelerated. Um novo marco para desenvolvimento de software.</p>

<div style="margin-top:1.4em">
  <span class="tag">Código aberto</span>
  <span class="tag green">Rust</span>
  <span class="tag pink">Rendenização pela GPU</span>
  <span class="tag">Modo Multiplayer</span>
</div>
<br>
<div class="subtitle">Davi Santos de Mesquita</div>

---



<!-- _class: divider -->

<div class="label">01 — Apresentação</div>

## O que é o Zed?

<p style="max-width:520px;color:#A09EC0;margin-top:0.4em"> Uma análise da finalidade, público-alvo e principais funcionalidades.</p>


---

## Qual a finalidade do Zed?
<br>
<p> Em um mercado dominado por editores já consolidados, o Zed nasceu tentando ser diferente. A sua <strong>finalidade</strong> é eliminar o atrito entre o programador e a máquina.</p>



<p>Isso se deve ao fato dele ter sido projetado desde o zero com foco absoluto em <strong>extrema velocidade, latência quase nula e colaboração multiplayer nativa</strong>, resolvendo os problemas de lentidão de editores tradicionais como:</p>
<br>

<div style="margin-top:1.4em">
  <span class="tag">Vs Code</span>
  <span class="tag green">Cursor</span>
  <span class="tag pink">Intellij</span>
</div>

---

## Qual o público-alvo do Zed?
<br>
<p> De modo geral, o Zed foi construído para <strong>desenvolvedores que estão descontentes com a lentidão de outros editores de código</strong>, bem como para aqueles que querem um editor que consuma menos RAM.

Seu principal público-alvo são os <strong>programadores mais experientes</strong>, que já estão fadigados de outros editores e querem testar algo novo. 


---

## Quais são as principais funcionalidades?
<br>
<div style="margin-top:14px">
<div class="feat">
  <div class="feat-icon">⚡</div>
  <div class="feat-body">
    <h3>Edição de texto de alta perfomance</h3>
    <p>Editors baseados em Electron operam com um input lag mensurável, o que é imperceptível para muitos, mas insuportável para outros. Já o Zed, foi construído para ter uma <strong>latência quase nula</strong>, permitindo uma <strong>digitação e navegação com uma velocidade extrema.</strong>
    </p>
  
  </div>
</div>
<div class="feat">
  <div class="feat-icon">👥</div>
  <div class="feat-body">
    <h3>Colaboração multiplayer nativa</h3>
    <p>Diferentemente de outros editores, o Zed possui <strong>colaboração integrada por padrão</strong>, permitindo os desenvolvedores a <strong>utililiza-lo como um modo colaborativo em tempo real do Google Docs, mas com código</strong>.</p>
  </div>
</div>
<div class="feat">
  <div class="feat-icon">🤖</div>
  <div class="feat-body">
    <h3>Forte integração com ferramentas de inteligência artificial</h3>
    <p>O editor, seguindo as demandas modernas de desenvolvimento de software, oferece <strong>integração nativa com IA</strong>, permitindo utilizar assistentes de código <strong>de modo integrado no editor de modo que a performance da interface gráfica não seja afetada</strong>.</p>
  </div>
</div>
</div>

---
<!-- _class: divider -->

<div class="label">02 — Tecnologias envolvidas</div>

## Como o Zed foi construído?

<p style="max-width:520px;color:#A09EC0;margin-top:0.4em"> Uma explanação acerca da linguagem de programação, frameworks, bibliotecas e tipo de aplicação.</p>


---

## Linguagem de programação
<br>
<p> </p>
<img src="./rust-logo-blk.svg" width="470px">
<img src="./rust-mascote-oficial.png" width="610px">

---

## Linguagem de programação
<br>
<p> O Zed é totalmente escrito em <strong>Rust</strong>, uma linguagem de programação compilada de sistemas. </p>

<br>

<p> Mas, afinal: <strong>Porquê o Rust foi escolhido?</strong>

- Rust é uma <strong>linguagem extremamente rápida</strong>, construída <strong>sem Garbage Colector</strong> (Coletor de Lixo), de modo que o <strong>gerenciamento de memória RAM ocorre ainda em tempo de compilação</strong> através de regras rígidas de ownership (Propriedade), que, por fim, <strong>gera um código nativo de máquina demasiadamente eficiente</strong>.


---

## Frameworks
<br>
<p> A interface do Zed é construída através de um framework/engine que a própria equipe do Zed fez, o <strong>GPUI</strong>. </p>


<br>

<p> Um pouco sobre o <strong>GPUI</strong>:

- O GPUI é uma engine de interface gráfica proprietária que faz toda a rendenização da UI (Interface do Usuário) diretamente na GPU, se comunicando com a GPU através de APIs gráficas de baixo nível, como:
  - <strong>Metal</strong> no MacOS
  - <strong>Vulkan ou DirectX</strong> no Windows/Linux

---

## Frameworks (GPUI)
<br>
<p> Em contraponto a outros editores de código, como o VS Code, o Zed não utiliza Electron com JavaScript para a montagem de sua UI.</p>

<br>

<p> Qual a diferença do <strong>Electron</strong> pro <strong>GPUI</strong>?

- O Electron é um framework, usado no VS Code, que utiliza JavaScript para construir a UI e executa a rendenização através de uma engine de navegador, como o Chromium, que torna a aplicação mais pesada e lenta em comparação à solução nativa e de baixo nível adotada pelo GPUI do Zed.
- Esse controle de baixo nível faz com o que o GPUI não seja apenas um framework, mas uma verdadeira engine de rendenização.

---

## Tipo de aplicação
<br>
<p> O Zed é um software para desktop, disponível para:</p>

<div style="margin-top:1.4em">
  <span class="tag">MacOS</span>
  <span class="tag green">Linux</span>
  <span class="tag pink">Windows</span>
</div>

<br>


---

<!-- _class: divider -->

<div class="label">03 — Funcionamento</div>

## Como o Zed funciona?

<p style="max-width:520px;color:#A09EC0;margin-top:0.4em"> Uma investigação sobre o funcionamento: da interação do usuário com o sistema, da representação dos dados, do uso de processador, do uso da memória e das operações de entrada e saída.</p>


---

## Funcionamento da edição de código
<br>
<p> A interação do usuário ao editar código é, em suma, utilizar o teclado para adicionar, editar e excluir código.

<br>
<br>

### Exemplo:

- Se o usuário digitar a letra "D" no editor, o teclado envia um sinal elétrico bruto para o Sistema Operacional, que intercepta esse sinal físico e converte em um "evento de entrada" que o Zed pode "entender".


---

## Funcionamento da edição de código
<br>


### Mas como ocorre o processamento desse evento de entrada?

- Pelo fato dele ter sido feito inteiramente em Rust, que possui um ótimo suporte à concorrência segura, ele consegue utilizar o processamento multithreading de modo muito inteligente.
- Quando a CPU recebe o evento de digitação, a tarefa é distribuída entre os diferentes núcleos do processador.
- A Thread principal captura e imediatamente efetua a validação do caractere para que a interface do usuário não trave.
- Enquanto o usuário está digitando, outras Threads em segundo plano estão processando paralelamente a análise gramatical do texto, utilizando um componente chamado Tree-sitter.
---

## Funcionamento da edição de código
<br>

### Mas como ocorre o processamento desse evento de entrada? (Continuação)

- Sendo mais específico, essas <strong>Threads em segundo plano</strong> convertem o texto inserido (strings) em estruturas de dados complexas conhecidas como <strong>Árvores de Sintaxe Abstrata</strong> (Abstract Sintaxe Tree - AST), que servem, principalmente, para o editor saber onde colocar as cores (Sintax Highlight).

<br>

### Exemplo de código com Sintax Highlight:

```Rust
pub fn background_executor(&self) -> BackgroundExecutor {
    self.0.borrow().background_executor.clone()
}
```
<br>
<p>
Código retirado de: 
<a href="https://github.com/zed-industries/zed/blob/main/crates/gpui/src/app.rs">
  <span class="tag">zed/crates/gpui/src/app.rs
  </span>
  
</a>
</p>

---

## Como o Zed lida com memória?
<br>

### Memória secundária:

- Ao abrir um projeto, o software <strong>realiza grandes leituras paralelas no HD/SSD</strong> para carregar a árvore de diretórios, conseguindo carregar até milhares de arquivos de uma só vez.

<br>

### Memória principal:

- Editores, como VS Code, precisam carregar um navegador de internet oculto na memória (devido ao Electron), o que o torna pesado. Em contrapartida, o Zed <strong>aloca dados na RAM de modo nativo e de baixo nível</strong>, utilizando, especialmente, a técnica denominada Zero-copy, que reduz drasticamente a duplicação de textos e variáveis em diferentes blocos da memória RAM.

---

## Como o Zed exibe as saídas? (GPUI)
<br>


### O maior diferencial da rendenização pelo GPUI:

- Comumente, a rendenização ocorre  após a CPU calcular o texto e entregar para um framework desenha-lo. 
- Porém, no Zed, <strong>o GPUI transforma os dados de texto e as árvores de sintaxe</strong>, citados anteriomente, <strong>em dados geométricos vetoriais</strong>.
- As <strong>instruções matemáticas de desenho</strong> (exibição) <strong>são mandadas diretamente da CPU para GPU através de APIs gráficas</strong> como Metal, DirectX ou Vulkan, também citados anteriormente.
- Por fim, após todo esse processo, <strong>a GPU pinta os pixels na tela</strong>, exibindo a saída esperada.

---


<!-- _class: divider -->

<div class="label">04 — Representação de dados</div>

## Como o Zed representa e tranforma dados?

<p style="max-width:520px;color:#A09EC0;margin-top:0.4em"> Ampliando o entendimento sobre os dados e suas peculiaridades no software Zed.</p>

---

## Transformação de dados até chegar na exibição
<br>


### Dado bruto na memória (UTF-8):

- Quando o usuário digita algo no editor, esse <strong>texto simples</strong>, de <strong>codificação UTF-8</strong>, <strong>é salvo na memória RAM</strong>.
- Logo após isso, <strong>tal dado passa pela CPU via Tree-sitter</strong>, que <strong>atualiza o AST incrementalmente</strong>.
- O principal <strong>motivo pelo qual o AST é atualizado incrementalmente</strong> é que ele não precisa ser recriado. <strong>Trazendo otimização para o processo</strong>.

<br>


---

## Transformação de dados até chegar na exibição

### Dado um pouco mais elaborado (AST):
- Gera-se uma <strong>AST</strong> após um mapeamento, de modo que agora o software sabe informações precisas sobre a estrutura do código, reconhecendo o que é:
    - Função
    - Variável
    - Ou laço de repetição...


- Organizando tudo isso de forma hierarquica para definir a colaração da sintaxe (<strong>Sintax Highlight</strong>).

---


## Transformação de dados até chegar na exibição

### A exibição pelo GPUI (Matrizes matemáticas):

- Logo após tudo isso, <strong>o AST</strong> e sua árvore lógica <strong>são passados para o GPUI</strong> para serem <strong>convertidos em matrizes matemáticas geometricas vetoriais</strong>.
- Esse é o <strong>formato ideal para a GPU</strong> fazer os calculos e <strong>desenhar os pixels corretamente</strong>.

<br>

### Vale lembrar que:

- Tudo isso <strong>ocorre de forma extremamente rápida.</strong>
- Nem todo o processo entre a inserção de um texto no editor e sua exibição foi devidamente evidenciado e explanado nesta apresentação (devido a extensão e complexidade envolvida nisso).


---

<!-- _class: divider -->

<div class="label">05 — Requisitos computacionais</div>

## O que o Zed exige?

<p style="max-width:520px;color:#A09EC0;margin-top:0.4em"> Uma aferição das limitações de hardware e software para o uso do Zed.</p>

---

## Limitações de hardware

<br>

### Processador:

- Minimo: dual-core (2 núcleos).
- Recomendado: Processador quad-core (4 núcleos ou superior).

<br>

### Memória RAM:

- Minimo: 4GB.
- Recomendado: 8GB ou mais.
  - Para abrir projetos muito grandes, é essencial ter mais memória RAM (4GB pode ser pouco).



---

## Limitações de hardware

<br>

### Placa de Vídeo (GPU): 

- O Sistema deve suportar as APIs gráficas modernas.
- Uma GPU integrada moderna já é plenamente capaz de cumprir esse requisito.

---


## Limitações de software

<br>

### Sistema operacional: 

- MacOS 10.15+ (Com suporte a Metal)
- Linux (Com Vulkan 1.3+)
- Windows (Com DirectX 11+)
---

<!-- _class: closing -->

# Zed
## Velocidade é uma feature.

<div style="margin-top:1.6em;display:flex;gap:10px;justify-content:center;flex-wrap:wrap">
  <span class="tag">zed.dev</span>
  <span class="tag green">github.com/zed-industries/zed</span>
</div>


---



<br>

## Fontes

<br>

- <a href="zed.dev/blog/zed-is-1-0">Artigo: "Zed is 1.0"</a>
- <a href="zed.dev/blog/zed-is-our-office">Artigo: "Zed Is Our Office"</a>
- <a href="zed.dev/blog/videogame">Artigo de como o Zed construiu o GPUI: "Leveraging Rust and the GPU to render user interfaces at 120 FPS""</a>
- <a href="github.com/zed-industries/zed/tree/main/crates/gpui">Repositório Técnico do GPUI: Zed GitHub Repository</a>
- <a href="learnopengl.com/Getting-started/Hello-Triangle"> Artigo Técnico Prático sobre rendenização de baixo nível: "LearnOpenGL: Graphics Pipeline" de Joey de Vries</a>
- <a href="zed.dev/blog/why-the-big-rewrite">Artigo de Engenharia: "Why the big rewrite?"</a>


--- 

## Fontes

<br>

- <a href="tree-sitter.github.io/tree-sitter">Repositório oficial do Tree-sitter</a>
- <a href="github.com/zed-industries/zed">Repositório do código fonte do Zed</a>
- <a href="doc.rust-lang.org/book/ch04-00-understanding-ownership.html">Capítulo de Ownership: "The Rust Programming Language"</a>
- <a href="rust-unofficial.github.io/patterns/">Padrões de design de sistemas em Rust</a>
- <a href="zed.dev/docs/installation"> Página oficial de instalação do Zed</a>
