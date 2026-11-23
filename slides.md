---
theme: seriph
colorSchema: light
layout: lava-cover
title: RustDoc
info: |
  ## RustDoc Exhibition
  Presentation slides.
class: text-center
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: soft-rise | soft-fall
comark: true
duration: 35min
---

# RustDoc

Nataly Jaya

<div class="abs-br m-6 text-xl">
  <a href="https://github.com/NatalyJaya/rustdoc-exhibition" target="_blank" class="slidev-icon-btn">
    <carbon:logo-github />
  </a>
</div>

<!--
Introduce yourself and the topic: rustdoc, Rust's documentation tool.
-->

---
layout: lava-cover
transition: fade-out
class: h1-gradient
---

<div class="toc toc-compact">
  <div class="toc-intro">
    <span class="toc-eyebrow">OVERVIEW</span>
    <h1>Contents</h1>
    <p class="toc-lead">
      From what RustDoc is to how it turns comments into a documentation website.
    </p>
  </div>

  <ol class="toc-list">
    <li class="toc-item">
      <span class="toc-num">01</span>
      <div>
        <h3>Introduction to RustDoc</h3>
        <p>What it is, what it's for and why documentation matters.</p>
      </div>
    </li>
    <li class="toc-item">
      <span class="toc-num">02</span>
      <div>
        <h3>Key features</h3>
        <p>Doc comments, HTML output and compiler integration.</p>
      </div>
    </li>
    <li class="toc-item">
      <span class="toc-num">03</span>
      <div>
        <h3>Origin &amp; history</h3>
        <p>From 2011 to today, and the people behind it.</p>
      </div>
    </li>
    <li class="toc-item">
      <span class="toc-num">04</span>
      <div>
        <h3>Under the hood</h3>
        <p>Inputs, outputs, internals and Cargo.</p>
      </div>
    </li>
    <li class="toc-item">
      <span class="toc-num">05</span>
      <div>
        <h3>Open source</h3>
        <p>License, community and real pull requests.</p>
      </div>
    </li>
    <li class="toc-item">
      <span class="toc-num">06</span>
      <div>
        <h3>Getting started</h3>
        <p>Requirements, installing Rust, first docs.</p>
      </div>
    </li>
    <li class="toc-item">
      <span class="toc-num">07</span>
      <div>
        <h3>Inside <code>[function]()</code></h3>
        <p>How [input] becomes [output].</p>
      </div>
    </li>
    <li class="toc-item">
      <span class="toc-num">08</span>
      <div>
        <h3>Comparison</h3>
        <p>RustDoc vs. Javadoc vs. Doxygen.</p>
      </div>
    </li>
    <li class="toc-item">
      <span class="toc-num">09</span>
      <div>
        <h3>Conclusions</h3>
        <p>Advantages, limitations and when to use it.</p>
      </div>
    </li>
    <li class="toc-item">
      <span class="toc-num">10</span>
      <div>
        <h3>Bibliography</h3>
        <p>References and further reading.</p>
      </div>
    </li>
  </ol>
</div>

---
layout: lava-cover
transition: fade-out
class: h1-gradient
---

<div class="rd-split">
  <div class="rd-intro">
    <span class="rd-eyebrow">01 · INTRODUCTION</span>
    <h1>Introduction to <span class="rd-mono">rustdoc</span></h1>
    <p class="rd-lead">
      Rust's own answer to a familiar problem: documentation that is easy to
      write, pleasant to read and never out of date.
    </p>
  </div>
  <div class="rd-stack">
    <div v-click class="rd-card">
      <span class="rd-icon"><carbon:help /></span>
      <div>
        <h3>What is RustDoc?</h3>
        <p>The official documentation tool, shipped with the standard Rust distribution. No extra install needed.</p>
      </div>
    </div>
    <div v-click class="rd-card">
      <span class="rd-icon"><carbon:tools /></span>
      <div>
        <h3>What is it for?</h3>
        <p>It generates documentation as <strong>HTML, CSS and JavaScript</strong> from comments in your source code or from standalone Markdown files.</p>
      </div>
    </div>
    <div v-click class="rd-card">
      <span class="rd-icon"><carbon:checkmark-outline /></span>
      <div>
        <h3>Why document code?</h3>
        <p>Docs that drift from the code are misleading. RustDoc keeps them <strong>in sync</strong>: examples in the docs run as automated tests.</p>
      </div>
    </div>
  </div>
</div>

<!--
rustdoc ships with rustup, like rustc and cargo.
-->

---
layout: lava-cover
transition: fade-out
class: h1-gradient
---

# Key features
## What makes RustDoc stand out

---
layout: lava-cover
transition: soft-rise | soft-fall
class: h1-gradient
---

<div class="rd-overview">
  <span class="rd-eyebrow">02 · KEY FEATURES</span>
  <h1>Four ideas behind RustDoc</h1>
  <div class="rd-grid">
    <div v-click class="rd-card rd-card-col">
      <div class="rd-card-top"><span class="rd-icon"><carbon:magic-wand /></span><span class="rd-num">01</span></div>
      <h3>Automatic generation</h3>
      <p>Rust reads your code and builds the docs for you.</p>
    </div>
    <div v-click class="rd-card rd-card-col">
      <div class="rd-card-top"><span class="rd-icon"><carbon:chat /></span><span class="rd-num">02</span></div>
      <h3>Doc comments</h3>
      <p>Explanations live next to the code, with <code>///</code> and <code>//!</code>.</p>
    </div>
    <div v-click class="rd-card rd-card-col">
      <div class="rd-card-top"><span class="rd-icon"><carbon:application-web /></span><span class="rd-num">03</span></div>
      <h3>HTML output</h3>
      <p>A navigable website with search and links.</p>
    </div>
    <div v-click class="rd-card rd-card-col">
      <div class="rd-card-top"><span class="rd-icon"><carbon:code /></span><span class="rd-num">04</span></div>
      <h3>Compiler integration</h3>
      <p>Built on <code>rustc</code>, so the docs show the real types.</p>
    </div>
  </div>
</div>

---
layout: lava-cover
transition: soft-rise | soft-fall
class: h1-gradient
---

<div class="rd-feature">
  <span class="rd-eyebrow">FEATURE 01 / 04</span>
  <h1>Automatic generation</h1>
  <p class="rd-lead rd-lead-center">
    You don't build a website by hand. Rust reads your code and creates it on its own.
  </p>
  <div class="rd-flow">
    <div class="rd-node">
      <span class="rd-icon"><carbon:document /></span>
      <h3>src/lib.rs</h3>
      <p>Your code + doc comments</p>
    </div>
    <span v-click="1" class="rd-arrow"><carbon:arrow-right /></span>
    <div v-click="1" class="rd-node rd-node-accent">
      <span class="rd-icon"><carbon:settings /></span>
      <h3>rustdoc</h3>
      <p>Parses items, types &amp; Markdown</p>
    </div>
    <span v-click="2" class="rd-arrow"><carbon:arrow-right /></span>
    <div v-click="2" class="rd-node">
      <span class="rd-icon"><carbon:folder /></span>
      <h3>target/doc/</h3>
      <p>HTML · CSS · JS</p>
    </div>
  </div>
  <div v-click="3" class="rd-term">
    <span class="rd-term-prompt">$</span> cargo doc --open
  </div>
</div>

---
layout: lava-cover
transition: soft-rise | soft-fall
class: h1-gradient
---

<div class="rd-split rd-split-code">
  <div class="rd-intro">
    <span class="rd-eyebrow">FEATURE 02 / 04</span>
    <h1>Doc comments</h1>
    <p class="rd-lead">You write the explanation right next to the code.</p>
    <div class="rd-syntax" :class="{ 'is-on': $clicks === 1 }">
      <code class="rd-glyph">///</code>
      <p><strong>Outer doc.</strong> Describes the item <em>below</em> it: a function, struct, enum…</p>
    </div>
    <div class="rd-syntax" :class="{ 'is-on': $clicks === 2 }">
      <code class="rd-glyph">//!</code>
      <p><strong>Inner doc.</strong> Describes the module or crate you are <em>inside</em>.</p>
    </div>
  </div>
  <div class="rd-code">

````rust {all|4-12|1-2}
//! # mini_math
//! A tiny crate to show how rustdoc works.

/// Adds two numbers.
///
/// # Examples
/// ```
/// assert_eq!(mini_math::add(2, 3), 5);
/// ```
pub fn add(a: i32, b: i32) -> i32 {
    a + b
}
````

  </div>
</div>

<!--
Both are Markdown: headings, lists, links and code blocks all work.
-->

---
layout: lava-cover
transition: soft-rise | soft-fall
class: h1-gradient
---

<div class="rd-split rd-split-wide">
  <div class="rd-intro">
    <span class="rd-eyebrow">FEATURE 03 / 04</span>
    <h1>HTML output</h1>
    <p class="rd-lead">The result is a website you can browse, open locally or publish.</p>
    <ul class="rd-chips">
      <li v-click><carbon:search /> Built-in search</li>
      <li v-click><carbon:link /> Cross-links between items</li>
      <li v-click><carbon:launch /> Published on <strong>docs.rs</strong></li>
    </ul>
  </div>
  <div class="rd-browser">
    <div class="rd-browser-bar">
      <span class="dot" /><span class="dot" /><span class="dot" />
      <span class="rd-url">docs.rs/mini_math/latest/mini_math/fn.add.html</span>
    </div>
    <div class="rd-browser-body">
      <aside class="rd-side">
        <p class="rd-side-crate">mini_math</p>
        <p class="rd-side-h">Functions</p>
        <p class="rd-side-item is-active">add</p>
        <p class="rd-side-item">sub</p>
        <p class="rd-side-item">mul</p>
      </aside>
      <main class="rd-page">
        <div class="rd-search"><carbon:search /> Search mini_math…</div>
        <h4>Function <span class="rd-path">mini_math::</span><span class="rd-fn">add</span></h4>
        <pre class="rd-sig">pub fn add(a: <span class="rd-ty">i32</span>, b: <span class="rd-ty">i32</span>) -&gt; <span class="rd-ty">i32</span></pre>
        <p class="rd-desc">Adds two numbers.</p>
        <p class="rd-sec">Examples</p>
        <pre class="rd-ex">assert_eq!(mini_math::add(2, 3), 5);</pre>
      </main>
    </div>
  </div>
</div>

---
layout: lava-cover
transition: fade-out
class: h1-gradient
---

<div class="rd-split rd-split-wide">
  <div class="rd-intro">
    <span class="rd-eyebrow">FEATURE 04 / 04</span>
    <h1>Compiler integration</h1>
    <p class="rd-lead">RustDoc uses the compiler itself to understand your code.</p>
  </div>
  <div class="rd-stack">
    <div v-click class="rd-card">
      <span class="rd-icon"><carbon:code /></span>
      <div>
        <h3>Real types</h3>
        <p>Signatures come from <code>rustc</code>, not from parsing text, so the docs match the code.</p>
      </div>
    </div>
    <div v-click class="rd-card">
      <span class="rd-icon"><carbon:terminal /></span>
      <div>
        <h3>One command</h3>
        <p>Launched with <code>cargo doc</code>, together with your dependencies.</p>
      </div>
    </div>
    <div v-click class="rd-card">
      <span class="rd-icon"><carbon:checkmark-outline /></span>
      <div>
        <h3>Examples are tests</h3>
        <p>Code blocks in the docs are compiled and run by <code>cargo test</code>.</p>
      </div>
    </div>
    <div v-click class="rd-term rd-term-block">
<div><span class="rd-term-prompt">$</span> cargo test --doc</div>
<div class="rd-term-dim">   Doc-tests mini_math</div>
<div>test src/lib.rs - add (line 7) ... <span class="rd-ok">ok</span></div>
<div>test result: <span class="rd-ok">ok</span>. 1 passed; 0 failed</div>
    </div>
  </div>
</div>

---
layout: lava-cover
transition: soft-rise | soft-fall
class: h1-gradient
---

<div class="rd-split rd-split-wide">
  <div class="rd-intro">
    <span class="rd-eyebrow">03 · ORIGIN &amp; HISTORY</span>
    <h1>Born next to the compiler</h1>
    <p class="rd-lead">
      rustdoc has been part of Rust almost from the start, and it still lives
      inside the compiler's own source tree.
    </p>
  </div>
  <div class="rd-stack">
    <div class="rd-hist-top">
      <div v-click class="rd-card rd-stat">
        <span class="rd-stat-k">Dec 2011</span>
        <p>Development starts, almost at the same time as <code>rustc</code>.</p>
      </div>
      <div v-click class="rd-card rd-stat">
        <span class="rd-stat-k rd-stat-team"><carbon:user-multiple /> Rustdoc team</span>
        <p>The official Rust team that develops and maintains it.</p>
      </div>
    </div>
    <div v-click class="rd-tree">
      <p class="rd-tree-root"><carbon:folder /> rust-lang/rust</p>
      <p><span class="rd-tree-br">├─</span> compiler/ <span class="rd-tree-note">rustc</span></p>
      <p class="is-hl"><span class="rd-tree-br">├─</span> src/librustdoc/ <span class="rd-tree-note">the rustdoc library · lib.rs</span></p>
      <p><span class="rd-tree-br">└─</span> src/tools/rustdoc/ <span class="rd-tree-note">thin binary → calls rustdoc::main</span></p>
    </div>
  </div>
</div>

<!--
The real logic is the library in src/librustdoc; the rustdoc binary is only a wrapper that calls rustdoc::main.
-->

---
layout: lava-cover
transition: fade-out
class: h1-gradient
---

<div class="rd-timeline">
  <span class="rd-eyebrow">03 · ORIGIN &amp; HISTORY</span>
  <h1>From a basic HTML generator to core infrastructure</h1>
  <div class="rd-tl">
    <div class="rd-tl-track"><div class="rd-tl-progress" :style="{ width: Math.min($clicks, 5) / 5 * 100 + '%' }" /></div>
    <div v-click class="rd-tl-era">
      <span class="rd-tl-dot" />
      <span class="rd-tl-year">2011</span>
      <h3>Origin</h3>
      <p>Mozilla Research ships a first version: static HTML from source comments, inspired by Doxygen and Javadoc.</p>
      <p class="rd-tl-who">Brian Anderson · Graydon Hoare</p>
    </div>
    <div v-click class="rd-tl-era">
      <span class="rd-tl-dot" />
      <span class="rd-tl-year">2013–15</span>
      <h3>Redesign &amp; integration</h3>
      <p>Rewritten on top of the compiler's AST. Runnable doctests arrive and it connects to <code>cargo doc</code>.</p>
      <p class="rd-tl-who">Alex Crichton · Guillaume Gomez</p>
    </div>
    <div v-click class="rd-tl-era">
      <span class="rd-tl-dot" />
      <span class="rd-tl-year">2016–19</span>
      <h3>Consolidation &amp; docs.rs</h3>
      <p>docs.rs builds and hosts docs for every crate on crates.io. In-browser search improves.</p>
      <p class="rd-tl-who">Onur Aslan · Guillaume Gomez · Steve Klabnik · QuietMisdreavus</p>
    </div>
    <div v-click class="rd-tl-era">
      <span class="rd-tl-dot" />
      <span class="rd-tl-year">2019–20</span>
      <h3>Team split</h3>
      <p>One team maintains the rustdoc tool, another runs the docs.rs website.</p>
      <p class="rd-tl-who">Rustdoc team · docs.rs team</p>
    </div>
    <div v-click class="rd-tl-era is-now">
      <span class="rd-tl-dot" />
      <span class="rd-tl-year">2020–now</span>
      <h3>Modernization</h3>
      <p>New UI, intra-doc links (<code>[Item]</code>), lower memory use and experimental JSON output.</p>
      <p class="rd-tl-who">Rustdoc team</p>
    </div>
  </div>
</div>

---
layout: lava-cover
transition: soft-rise | soft-fall
class: h1-gradient
---

<div class="rd-feature">
  <span class="rd-eyebrow">04 · UNDER THE HOOD</span>
  <h1>What goes in, what comes out</h1>
  <div class="rd-langs">
    <span><carbon:code /> Written in Rust</span>
    <span><carbon:document /> Documents Rust</span>
    <span><carbon:text-annotation-toggle /> Comments in Markdown</span>
  </div>
  <div class="rd-io">
    <div class="rd-io-col">
      <span class="rd-io-k">INPUT</span>
      <div v-click="1" class="rd-card rd-io-item">
        <span class="rd-icon"><carbon:document /></span>
        <div>
          <h3><code>.rs</code> source files</h3>
          <p>With <code>///</code> and <code>//!</code> doc comments.</p>
        </div>
      </div>
      <div v-click="1" class="rd-card rd-io-item">
        <span class="rd-icon"><carbon:catalog /></span>
        <div>
          <h3>Standalone <code>.md</code> files</h3>
          <p>Guides or READMEs, rendered on their own.</p>
        </div>
      </div>
    </div>
    <div class="rd-io-mid">
      <span class="rd-arrow"><carbon:arrow-right /></span>
      <div class="rd-node rd-node-accent rd-io-core">
        <span class="rd-icon"><carbon:settings /></span>
        <h3>rustdoc</h3>
      </div>
      <span class="rd-arrow"><carbon:arrow-right /></span>
    </div>
    <div class="rd-io-col">
      <span class="rd-io-k">OUTPUT</span>
      <div v-click="2" class="rd-card rd-io-item">
        <span class="rd-icon"><carbon:application-web /></span>
        <div>
          <h3>HTML + CSS + JS <span class="rd-badge is-stable">stable</span></h3>
          <p>Browsable pages plus a <strong>search index</strong>.</p>
        </div>
      </div>
      <div v-click="3" class="rd-card rd-io-item is-dashed">
        <span class="rd-icon"><carbon:data-structured /></span>
        <div>
          <h3>JSON <span class="rd-badge is-nightly">nightly</span></h3>
          <p><code>--output-format json</code>, unstable. Lets other tools read the docs.</p>
        </div>
      </div>
    </div>
  </div>
</div>

---
layout: lava-cover
transition: soft-rise | soft-fall
class: h1-gradient
---

<div class="rd-split rd-split-pipe">
  <div class="rd-intro">
    <span class="rd-eyebrow">04 · UNDER THE HOOD</span>
    <h1>Inside the <span class="rd-mono">rustdoc</span> box</h1>
    <p class="rd-lead">
      Five steps, following our <code class="rd-inline">mini_math::add</code> example.
      Each one lives in its own part of <code class="rd-inline">src/librustdoc/</code>.
    </p>
  </div>
  <ol class="rd-pipe">
    <li v-click class="rd-pipe-step">
      <span class="rd-pipe-n">1</span>
      <div class="rd-pipe-txt">
        <h3>The compiler reads the code</h3>
        <p>rustc parses and type-checks it.</p>
        <span class="rd-pipe-dir">core.rs</span>
      </div>
      <code class="rd-pipe-snip">pub fn add(a: i32, b: i32) -&gt; i32</code>
    </li>
    <li v-click class="rd-pipe-step">
      <span class="rd-pipe-n">2</span>
      <div class="rd-pipe-txt">
        <h3>Comments become attributes</h3>
        <p><code>///</code> is sugar for <code>#[doc]</code>.</p>
        <span class="rd-pipe-dir">rustc parser</span>
      </div>
      <code class="rd-pipe-snip">#[doc = " Adds two numbers."]</code>
    </li>
    <li v-click class="rd-pipe-step">
      <span class="rd-pipe-n">3</span>
      <div class="rd-pipe-txt">
        <h3>Stored in a clean structure</h3>
        <p>Functions, types, traits and their docs.</p>
        <span class="rd-pipe-dir">clean/</span>
      </div>
      <code class="rd-pipe-snip">clean::Item { name: add, kind: Function }</code>
    </li>
    <li v-click class="rd-pipe-step">
      <span class="rd-pipe-n">4</span>
      <div class="rd-pipe-txt">
        <h3>Markdown → HTML + links</h3>
        <p>Resolves <code>[Item]</code> links between items.</p>
        <span class="rd-pipe-dir">passes/ · html/</span>
      </div>
      <code class="rd-pipe-snip">&lt;p&gt;Adds two numbers.&lt;/p&gt;</code>
    </li>
    <li v-click class="rd-pipe-step is-last">
      <span class="rd-pipe-n">5</span>
      <div class="rd-pipe-txt">
        <h3>Doctests are compiled &amp; run</h3>
        <p>Code blocks are extracted as tests.</p>
        <span class="rd-pipe-dir">doctest/</span>
      </div>
      <code class="rd-pipe-snip">assert_eq!(add(2, 3), 5); <span class="rd-ok-l">✓</span></code>
    </li>
  </ol>
</div>

<!--
This zooms into the middle box of the "Automatic generation" slide.
-->

---
layout: lava-cover
transition: fade-out
class: h1-gradient
---

<div class="rd-feature">
  <span class="rd-eyebrow">04 · UNDER THE HOOD</span>
  <h1>Cargo: from your laptop to docs.rs</h1>
  <p class="rd-lead rd-lead-center">
    <code class="rd-inline">cargo doc</code> calls rustdoc with the right options. Nothing to configure.
  </p>
  <div class="rd-stages">
    <div v-click class="rd-card rd-stage">
      <div class="rd-card-top"><span class="rd-icon"><carbon:tools /></span><span class="rd-num">BUILD</span></div>
      <div class="rd-cmds">
        <p><span class="rd-term-prompt">$</span>cargo doc</p>
        <p><span class="rd-term-prompt">$</span>cargo doc --open</p>
        <p><span class="rd-term-prompt">$</span>cargo doc --no-deps</p>
      </div>
      <p>Documents your crate <strong>and its dependencies</strong>. <code>--open</code> opens the browser, <code>--no-deps</code> keeps only your project.</p>
    </div>
    <span v-click class="rd-arrow"><carbon:arrow-right /></span>
    <div v-click class="rd-card rd-stage">
      <div class="rd-card-top"><span class="rd-icon"><carbon:checkmark-outline /></span><span class="rd-num">TEST</span></div>
      <div class="rd-cmds">
        <p><span class="rd-term-prompt">$</span>cargo test</p>
      </div>
      <p>Runs the <strong>doctests</strong> along with your unit tests, so a broken example makes the tests fail.</p>
    </div>
    <span v-click class="rd-arrow"><carbon:arrow-right /></span>
    <div v-click class="rd-card rd-stage rd-stage-accent">
      <div class="rd-card-top"><span class="rd-icon"><carbon:launch /></span><span class="rd-num">PUBLISH</span></div>
      <div class="rd-cmds">
        <p><span class="rd-term-prompt">$</span>cargo publish</p>
      </div>
      <p>Once on <strong>crates.io</strong>, docs.rs builds and hosts the docs automatically.</p>
    </div>
  </div>
</div>

---
layout: lava-cover
transition: soft-rise | soft-fall
class: h1-gradient
---

<div class="rd-split rd-split-wide">
  <div class="rd-intro">
    <span class="rd-eyebrow">05 · OPEN SOURCE</span>
    <h1>Free to use, open to read</h1>
    <p class="rd-lead">rustdoc is part of the Rust project, and so is its license.</p>
  </div>
  <div class="rd-stack">
    <div v-click class="rd-card rd-license">
      <span class="rd-icon"><carbon:certificate /></span>
      <div>
        <p class="rd-license-k">MIT <span>or</span> Apache-2.0</p>
        <p>Dual license, your choice. Use, modify and distribute it freely, <strong>commercial projects included</strong>.</p>
      </div>
    </div>
    <div v-click class="rd-tree">
      <p class="rd-tree-root"><carbon:logo-github /> rust-lang/rust <span class="rd-tree-note">no repo of its own</span></p>
      <p><span class="rd-tree-br">└─</span> src/librustdoc/</p>
      <p><span class="rd-tree-br">&nbsp;&nbsp;&nbsp;├─</span> clean/ · passes/ · doctest/ · json/ <span class="rd-tree-note">the engine</span></p>
      <p class="is-hl"><span class="rd-tree-br">&nbsp;&nbsp;&nbsp;└─</span> html/ <span class="rd-tree-note">the web interface</span></p>
      <p><span class="rd-tree-br">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;├─</span> static/ <span class="rd-tree-note">css · js · fonts</span></p>
      <p><span class="rd-tree-br">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└─</span> templates/ <span class="rd-tree-note">page layouts</span></p>
    </div>
  </div>
</div>

---
layout: lava-cover
transition: soft-rise | soft-fall
class: h1-gradient
---

<div class="rd-feature">
  <span class="rd-eyebrow">05 · OPEN SOURCE</span>
  <h1>How the community collaborates</h1>
  <div class="rd-flow rd-flow-5">
    <div v-click="1" class="rd-node rd-node-sm">
      <span class="rd-icon"><carbon:idea /></span>
      <h3>RFC</h3>
      <p>Big changes are discussed in public first · rust-lang/rfcs</p>
    </div>
    <span v-click="2" class="rd-arrow"><carbon:arrow-right /></span>
    <div v-click="2" class="rd-node rd-node-sm">
      <span class="rd-icon"><carbon:warning-alt /></span>
      <h3>Issue</h3>
      <p>Labelled <code>T-rustdoc</code> so the right people see it</p>
    </div>
    <span v-click="3" class="rd-arrow"><carbon:arrow-right /></span>
    <div v-click="3" class="rd-node rd-node-sm">
      <span class="rd-icon"><carbon:pull-request /></span>
      <h3>Pull request</h3>
      <p>Anyone can open one on GitHub</p>
    </div>
    <span v-click="4" class="rd-arrow"><carbon:arrow-right /></span>
    <div v-click="4" class="rd-node rd-node-sm rd-node-accent">
      <span class="rd-icon"><carbon:user-multiple /></span>
      <h3>Review</h3>
      <p>The rustdoc team reviews and approves</p>
    </div>
  </div>
  <div v-click="5" class="rd-channels">
    <div>
      <span class="rd-io-k">TALK</span>
      <p><carbon:chat /> Zulip · <code>#t-rustdoc</code></p>
      <p><carbon:forum /> users.rust-lang.org</p>
    </div>
    <div>
      <span class="rd-io-k">GET STARTED</span>
      <p><carbon:document /> CONTRIBUTING.md</p>
      <p><carbon:book /> rustc dev guide · Code of Conduct</p>
    </div>
  </div>
</div>

---
layout: lava-cover
transition: fade-out
class: h1-gradient
---

<div class="rd-prs">
  <div class="rd-prs-head">
    <div>
      <span class="rd-eyebrow">05 · OPEN SOURCE</span>
      <h1>Real pull requests</h1>
    </div>
    <p class="rd-lead">Four merged PRs in <code class="rd-inline">rust-lang/rust</code> behind features we've already seen.</p>
  </div>
  <div class="rd-pr-grid">
    <a v-click class="rd-card rd-pr" href="https://github.com/rust-lang/rust/pull/74430" target="_blank" rel="noreferrer">
      <div class="rd-pr-top"><span class="rd-merged"><carbon:pull-request /> Merged</span><span class="rd-pr-n">#74430</span></div>
      <h3>Stabilize intra-doc links</h3>
      <p>Made <code>[Item]</code> links stable, after a public final comment period.</p>
      <div class="rd-pr-meta"><span>@Manishearth</span><span>Sep 2020</span><span class="rd-diff"><b>+107</b> <i>−69</i></span></div>
      <div class="rd-pr-labels"><span>T-rustdoc</span><span>A-intra-doc-links</span><span>relnotes</span></div>
    </a>
    <a v-click class="rd-card rd-pr" href="https://github.com/rust-lang/rust/pull/79539" target="_blank" rel="noreferrer">
      <div class="rd-pr-top"><span class="rd-merged"><carbon:pull-request /> Merged</span><span class="rd-pr-n">#79539</span></div>
      <h3>Rustdoc: JSON backend experimental impl</h3>
      <p>The first JSON output. It picked up unfinished work from #75114 by @P1n3appl3.</p>
      <div class="rd-pr-meta"><span>@aDotInTheVoid</span><span>Dec 2020</span><span class="rd-diff"><b>+2192</b> <i>−21</i></span></div>
      <div class="rd-pr-labels"><span>T-rustdoc</span><span>A-rustdoc-json</span></div>
    </a>
    <a v-click class="rd-card rd-pr" href="https://github.com/rust-lang/rust/pull/84176" target="_blank" rel="noreferrer">
      <div class="rd-pr-top"><span class="rd-merged"><carbon:pull-request /> Merged</span><span class="rd-pr-n">#84176</span></div>
      <h3>Generate links to definition in source pages</h3>
      <p>Identifiers in the source code view become clickable links.</p>
      <div class="rd-pr-meta"><span>@GuillaumeGomez</span><span>Aug 2021</span><span class="rd-diff"><b>+707</b> <i>−131</i></span></div>
      <div class="rd-pr-labels"><span>T-rustdoc</span><span>A-rustdoc-ui</span></div>
    </a>
    <a v-click class="rd-card rd-pr" href="https://github.com/rust-lang/rust/pull/105848" target="_blank" rel="noreferrer">
      <div class="rd-pr-top"><span class="rd-merged"><carbon:pull-request /> Merged</span><span class="rd-pr-n">#105848</span></div>
      <h3>Add a new lint for broken inline code</h3>
      <p><code>rustdoc::unescaped_backticks</code> warns about stray backticks in docs.</p>
      <div class="rd-pr-meta"><span>@lukas-code</span><span>Apr 2023</span><span class="rd-diff"><b>+1775</b> <i>−5</i></span></div>
      <div class="rd-pr-labels"><span>T-rustdoc</span><span>A-lints</span><span>relnotes</span></div>
    </a>
  </div>
</div>

<!--
#74430 connects to "intra-doc links" in the timeline, #79539 to the JSON output, #84176 is by Guillaume Gomez from the timeline.
-->

---
layout: lava-cover
transition: fade-out
class: h1-gradient
---

<div class="rd-feature">
  <span class="rd-eyebrow">06 · GETTING STARTED</span>
  <h1>Up and running in three steps</h1>
  <div class="rd-stages rd-stages-start">
    <div v-click class="rd-card rd-stage">
      <div class="rd-card-top"><span class="rd-icon"><carbon:list-checked /></span><span class="rd-num">01 · REQUIREMENTS</span></div>
      <p>A terminal and a C linker:</p>
      <ul class="rd-mini">
        <li><b>macOS</b> Xcode command line tools</li>
        <li><b>Windows</b> Visual Studio C++ build tools</li>
        <li><b>Linux</b> gcc or clang</li>
      </ul>
    </div>
    <span v-click class="rd-arrow"><carbon:arrow-right /></span>
    <div v-click class="rd-card rd-stage">
      <div class="rd-card-top"><span class="rd-icon"><carbon:download /></span><span class="rd-num">02 · INSTALL RUST</span></div>
      <div class="rd-cmds">
        <p class="rd-nowrap"><span class="rd-term-prompt">$</span>curl https://sh.rustup.rs -sSf | sh</p>
        <p><span class="rd-term-prompt">$</span>rustdoc --version</p>
      </div>
      <p><strong>rustup</strong> installs rustc, cargo <strong>and rustdoc</strong>. Windows: rustup-init.exe.</p>
    </div>
    <span v-click class="rd-arrow"><carbon:arrow-right /></span>
    <div v-click class="rd-card rd-stage rd-stage-accent">
      <div class="rd-card-top"><span class="rd-icon"><carbon:play /></span><span class="rd-num">03 · USE IT</span></div>
      <div class="rd-cmds">
        <p><span class="rd-term-dim"># single file → ./doc</span></p>
        <p><span class="rd-term-prompt">$</span>rustdoc src/lib.rs</p>
        <p><span class="rd-term-dim"># cargo project → target/doc</span></p>
        <p><span class="rd-term-prompt">$</span>cargo doc --open</p>
      </div>
      <p>In practice you'll almost always use <code>cargo doc</code>.</p>
    </div>
  </div>
</div>

---
layout: lava-cover
transition: zoom-in | zoom-out
class: h1-gradient
---

# [Main research question of the code analysis?]
## An analysis of the [function]() method

---
layout: compile-split
transition: fade
step: '0 · example'
heading: '[Our example, before the call]'
---

```rust {1-3|5-7|9-11}{lines:true}
struct Example {
    field: Type,
}

fn setup() -> Builder {
    Builder::new()
}

fn main() {
    let out = setup().run();
}
```

::right::

<Placeholder :click="$clicks" label="Diagram · 0 · example" hint="Updates with each click." />

<!--
Speaker notes for step 0 · example.
-->

---
layout: compile-split
transition: fade
step: '1 / 9'
heading: '[Step 1 heading]'
---

```rust {1-2|3-4|5}{lines:true}
// Step 1: placeholder snippet
fn step_1(input: Input) -> Output {
    let value = input.prepare();
    let checked = validate(value)?;
    Output::from(checked)
}
```

::right::

<Placeholder :click="$clicks" label="Diagram · 1 / 9" hint="Updates with each click." />

<!--
Speaker notes for step 1 / 9.
-->

---
layout: compile-split
transition: fade
step: '2 / 9'
heading: '[Step 2 heading]'
---

```rust {1-2|3-4|5}{lines:true}
// Step 2: placeholder snippet
fn step_2(input: Input) -> Output {
    let value = input.prepare();
    let checked = validate(value)?;
    Output::from(checked)
}
```

::right::

<Placeholder :click="$clicks" label="Diagram · 2 / 9" hint="Updates with each click." />

<!--
Speaker notes for step 2 / 9.
-->

---
layout: compile-split
transition: fade
step: '3 / 9'
heading: '[Step 3 heading]'
---

```rust {1-2|3-4|5}{lines:true}
// Step 3: placeholder snippet
fn step_3(input: Input) -> Output {
    let value = input.prepare();
    let checked = validate(value)?;
    Output::from(checked)
}
```

::right::

<Placeholder :click="$clicks" label="Diagram · 3 / 9" hint="Updates with each click." />

<!--
Speaker notes for step 3 / 9.
-->

---
layout: compile-split
transition: fade
step: '4 / 9'
heading: '[Step 4 heading]'
---

```rust {1-2|3-4|5}{lines:true}
// Step 4: placeholder snippet
fn step_4(input: Input) -> Output {
    let value = input.prepare();
    let checked = validate(value)?;
    Output::from(checked)
}
```

::right::

<Placeholder :click="$clicks" label="Diagram · 4 / 9" hint="Updates with each click." />

<!--
Speaker notes for step 4 / 9.
-->

---
layout: compile-split
transition: fade
step: '5 / 9'
heading: '[Step 5 heading]'
---

```rust {1-2|3-4|5}{lines:true}
// Step 5: placeholder snippet
fn step_5(input: Input) -> Output {
    let value = input.prepare();
    let checked = validate(value)?;
    Output::from(checked)
}
```

::right::

<Placeholder :click="$clicks" label="Diagram · 5 / 9" hint="Updates with each click." />

<!--
Speaker notes for step 5 / 9.
-->

---
layout: compile-split
transition: fade
step: '6 / 9'
heading: '[Step 6 heading]'
---

```rust {1-2|3-4|5}{lines:true}
// Step 6: placeholder snippet
fn step_6(input: Input) -> Output {
    let value = input.prepare();
    let checked = validate(value)?;
    Output::from(checked)
}
```

::right::

<Placeholder :click="$clicks" label="Diagram · 6 / 9" hint="Updates with each click." />

<!--
Speaker notes for step 6 / 9.
-->

---
layout: compile-split
transition: fade
step: '7 / 9'
heading: '[Step 7 heading]'
---

```rust {1-2|3-4|5}{lines:true}
// Step 7: placeholder snippet
fn step_7(input: Input) -> Output {
    let value = input.prepare();
    let checked = validate(value)?;
    Output::from(checked)
}
```

::right::

<Placeholder :click="$clicks" label="Diagram · 7 / 9" hint="Updates with each click." />

<!--
Speaker notes for step 7 / 9.
-->

---
layout: compile-split
transition: fade
step: '8 / 9'
heading: '[Step 8 heading]'
---

```rust {1-2|3-4|5}{lines:true}
// Step 8: placeholder snippet
fn step_8(input: Input) -> Output {
    let value = input.prepare();
    let checked = validate(value)?;
    Output::from(checked)
}
```

::right::

<Placeholder :click="$clicks" label="Diagram · 8 / 9" hint="Updates with each click." />

<!--
Speaker notes for step 8 / 9.
-->

---
layout: compile-split
transition: fade
step: '9 / 9'
heading: '[Step 9 heading]'
---

```rust {1-2|3-4|5}{lines:true}
// Step 9: placeholder snippet
fn step_9(input: Input) -> Output {
    let value = input.prepare();
    let checked = validate(value)?;
    Output::from(checked)
}
```

::right::

<Placeholder :click="$clicks" label="Diagram · 9 / 9" hint="Updates with each click." />

<!--
Speaker notes for step 9 / 9.
-->

---
layout: lava-cover
transition: fade-out
class: h1-gradient
---

<div class="rd-cmp">
  <span class="rd-eyebrow">08 · COMPARISON</span>
  <h1>RustDoc vs. Javadoc vs. Doxygen</h1>
  <table class="rd-table">
    <thead>
      <tr><th></th><th class="is-rd">RustDoc</th><th>Javadoc</th><th>Doxygen</th></tr>
    </thead>
    <tbody>
      <tr><th>Languages</th><td class="is-rd">Rust</td><td>Java</td><td>C, C++, Java, Python…</td></tr>
      <tr><th>Comment style</th><td class="is-rd"><code>///</code> + Markdown</td><td><code>/** */</code> + <code>@param</code> tags</td><td><code>/** */</code> + <code>\brief</code> commands</td></tr>
      <tr><th>Ships with the toolchain</th><td class="is-rd"><span class="y">✓</span> rustup</td><td><span class="y">✓</span> JDK</td><td><span class="n">✗</span> separate install</td></tr>
      <tr><th>Examples run as tests</th><td class="is-rd"><span class="y">✓</span> doctests</td><td><span class="n">✗</span></td><td><span class="n">✗</span></td></tr>
      <tr><th>Output formats</th><td class="is-rd">HTML · JSON <em>(nightly)</em></td><td>HTML</td><td>HTML · PDF/LaTeX · XML · man</td></tr>
      <tr><th>Diagrams</th><td class="is-rd"><span class="n">✗</span></td><td><span class="n">✗</span></td><td><span class="y">✓</span> class &amp; call graphs</td></tr>
    </tbody>
  </table>
  <div v-click class="rd-verdict">
    <p><span class="y">＋</span> RustDoc: zero setup, Markdown, examples that can't go stale.</p>
    <p><span class="n">－</span> RustDoc: Rust only, HTML only, no diagrams. Doxygen wins on mixed-language projects.</p>
  </div>
</div>

---
layout: lava-cover
transition: fade-out
class: h1-gradient
---

# Study Conclusions
## Advantages, limitations and when to use it

---
layout: lava-cover
transition: fade-out
class: h1-gradient
---

<div class="rd-feature">
  <span class="rd-eyebrow">09 · CONCLUSIONS</span>
  <h1>Verdict</h1>
  <div class="rd-grid rd-grid-2">
    <div v-click class="rd-card rd-card-col">
      <div class="rd-card-top"><span class="rd-icon rd-icon-ok"><carbon:thumbs-up /></span><span class="rd-num">ADVANTAGES</span></div>
      <p>Comes with Rust · docs always in sync thanks to doctests · Markdown · search and links for free · same look across all crates on docs.rs.</p>
    </div>
    <div v-click class="rd-card rd-card-col">
      <div class="rd-card-top"><span class="rd-icon rd-icon-ko"><carbon:thumbs-down /></span><span class="rd-num">LIMITATIONS</span></div>
      <p>Rust only · HTML only (JSON still unstable) · no diagrams or PDF · little room to change the layout.</p>
    </div>
    <div v-click class="rd-card rd-card-col">
      <div class="rd-card-top"><span class="rd-icon"><carbon:face-satisfied /></span><span class="rd-num">EASE OF USE</span></div>
      <p>Very low barrier: if you can write Markdown, you can write rustdoc. One command, <code>cargo doc</code>, nothing to configure.</p>
    </div>
    <div v-click class="rd-card rd-card-col rd-stage-accent">
      <div class="rd-card-top"><span class="rd-icon"><carbon:recommend /></span><span class="rd-num">I'D RECOMMEND IT FOR</span></div>
      <p>Any Rust library, especially one published on crates.io · team projects where docs must stay up to date · learning, since examples double as tests. For long guides, pair it with <strong>mdBook</strong>.</p>
    </div>
  </div>
</div>

<!--
Add your personal experience here: what surprised you, what was hard, how long it took to get your first docs.
-->

---
layout: lava-cover
transition: fade-out
class: h1-gradient
---

<div class="concl">
  <div class="concl-intro">
    <span class="concl-eyebrow">01 · LESSONS LEARNED</span>
    <h1>What the code taught me</h1>
    <p class="concl-lead">
      [Lead sentence for the lessons.]
    </p>
  </div>

  <ol class="concl-list">
    <li v-click class="concl-item">
      <span class="concl-num">RS</span>
      <div>
        <h3>[Lesson 1]</h3>
        <p>[Description.]</p>
      </div>
    </li>
    <li v-click class="concl-item">
      <span class="concl-num">LIB</span>
      <div>
        <h3>[Lesson 2]</h3>
        <p>[Description.]</p>
      </div>
    </li>
    <li v-click class="concl-item">
      <span class="concl-num">IDEA</span>
      <div>
        <h3>[Lesson 3]</h3>
        <p>[Description.]</p>
      </div>
    </li>
    <li v-click class="concl-item">
      <span class="concl-num">UNI</span>
      <div>
        <h3>[Lesson 4]</h3>
        <p>[Description.]</p>
      </div>
    </li>
  </ol>
</div>

---
layout: lava-cover
transition: fade-out
class: h1-gradient
---

<div class="concl">
  <div class="concl-intro">
    <span class="concl-eyebrow">02 · AI-ASSISTED ANALYSIS</span>
    <h1>How I used AI</h1>
    <p class="concl-lead">
      [Which tools were used and for what.]
    </p>
  </div>

  <ol class="concl-list">
    <li v-click class="concl-item">
      <span class="concl-num">01</span>
      <div>
        <h3>[Phase 1 · Tool]</h3>
        <p>[Description.]</p>
      </div>
    </li>
    <li v-click class="concl-item">
      <span class="concl-num">02</span>
      <div>
        <h3>[Phase 2 · Tool]</h3>
        <p>[Description.]</p>
      </div>
    </li>
    <li v-click class="concl-item">
      <span class="concl-num">03</span>
      <div>
        <h3>[Phase 3 · Tool]</h3>
        <p>[Description.]</p>
      </div>
    </li>
  </ol>
</div>

---
layout: lava-cover
transition: fade-out
class: h1-gradient
---

<div class="biblio">
  <div class="biblio-intro">
    <span class="biblio-eyebrow">REFERENCES</span>
    <h1>Bibliography</h1>
    <p class="biblio-lead">
      Sources and further reading used throughout this presentation.
    </p>
  </div>
  <ol class="biblio-list">
    <li class="biblio-item">
      <p class="biblio-cite">
        The Rust Project.
        <em>What is rustdoc?</em>
        The rustdoc book.
      </p>
      <a class="biblio-url" href="https://doc.rust-lang.org/rustdoc/what-is-rustdoc.html" target="_blank" rel="noreferrer">https://doc.rust-lang.org/rustdoc/what-is-rustdoc.html</a>
    </li>
    <li class="biblio-item">
      <p class="biblio-cite">
        The Rust Project.
        <em>rust-lang/rust</em>
        [GitHub repository].
      </p>
      <a class="biblio-url" href="https://github.com/rust-lang/rust" target="_blank" rel="noreferrer">https://github.com/rust-lang/rust</a>
    </li>
    <li class="biblio-item">
      <p class="biblio-cite">
        The Rust Project.
        <em>src/librustdoc</em>
        [Source code folder].
      </p>
      <a class="biblio-url" href="https://github.com/rust-lang/rust/tree/main/src/librustdoc" target="_blank" rel="noreferrer">https://github.com/rust-lang/rust/tree/main/src/librustdoc</a>
    </li>
    <li class="biblio-item">
      <p class="biblio-cite">
        Manishearth; aDotInTheVoid; GuillaumeGomez; lukas-code. (2020–2023).
        <em>Merged rustdoc pull requests</em>
        [GitHub pull requests].
      </p>
      <span class="biblio-url"><a class="biblio-pr" href="https://github.com/rust-lang/rust/pull/74430" target="_blank" rel="noreferrer">#74430</a> · <a class="biblio-pr" href="https://github.com/rust-lang/rust/pull/79539" target="_blank" rel="noreferrer">#79539</a> · <a class="biblio-pr" href="https://github.com/rust-lang/rust/pull/84176" target="_blank" rel="noreferrer">#84176</a> · <a class="biblio-pr" href="https://github.com/rust-lang/rust/pull/105848" target="_blank" rel="noreferrer">#105848</a></span>
    </li>
    <li class="biblio-item">
      <p class="biblio-cite">
        DeepWiki.
        <em>rust-lang/rust</em>
        [AI-generated search results].
      </p>
      <a class="biblio-url" href="https://deepwiki.com/search/11d2f1a4-1eda-4f62-9560-2cb7fb1e51d3?mode=fast" target="_blank" rel="noreferrer">https://deepwiki.com/search/11d2f1a4-1eda-4f62-9560-2cb7fb1e51d3</a>
    </li>
    <li class="biblio-item">
      <p class="biblio-cite">
        The Rust Project.
        <em>rustup: the Rust toolchain installer</em>.
      </p>
      <a class="biblio-url" href="https://rustup.rs" target="_blank" rel="noreferrer">https://rustup.rs</a>
    </li>
  </ol>
</div>
