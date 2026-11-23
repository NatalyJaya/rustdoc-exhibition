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

<div class="toc">
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
        <h3>Inside <code>[function]()</code></h3>
        <p>How [input] becomes [output].</p>
      </div>
    </li>
    <li class="toc-item">
      <span class="toc-num">05</span>
      <div>
        <h3>Study Conclusions</h3>
        <p>Key takeaways from the analysis.</p>
      </div>
    </li>
    <li class="toc-item">
      <span class="toc-num">06</span>
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

# Study Conclusions
## [Subtitle for the conclusions]

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
        [Author 1]. ([Year]).
        <em>[Title 1]</em>.
      </p>
      <a class="biblio-url" href="https://example.com" target="_blank" rel="noreferrer">https://example.com</a>
    </li>
    <li class="biblio-item">
      <p class="biblio-cite">
        [Author 2]. ([Year]).
        <em>[Title 2]</em>.
      </p>
      <a class="biblio-url" href="https://example.com" target="_blank" rel="noreferrer">https://example.com</a>
    </li>
    <li class="biblio-item">
      <p class="biblio-cite">
        [Author 3]. ([Year]).
        <em>[Title 3]</em>.
      </p>
      <a class="biblio-url" href="https://example.com" target="_blank" rel="noreferrer">https://example.com</a>
    </li>
    <li class="biblio-item">
      <p class="biblio-cite">
        [Author 4]. ([Year]).
        <em>[Title 4]</em>.
      </p>
      <a class="biblio-url" href="https://example.com" target="_blank" rel="noreferrer">https://example.com</a>
    </li>
  </ol>
</div>
