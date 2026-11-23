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
Speaker notes placeholder.
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
      [One-line summary of what the talk covers.]
    </p>
  </div>

  <ol class="toc-list">
    <li class="toc-item">
      <span class="toc-num">01</span>
      <div>
        <h3>Section 01 title</h3>
        <p>Short description.</p>
      </div>
    </li>
    <li class="toc-item">
      <span class="toc-num">02</span>
      <div>
        <h3>Section 02 title</h3>
        <p>Short description.</p>
      </div>
    </li>
    <li class="toc-item">
      <span class="toc-num">03</span>
      <div>
        <h3>Inside <code>[function]()</code></h3>
        <p>How [input] becomes [output].</p>
      </div>
    </li>
    <li class="toc-item">
      <span class="toc-num">04</span>
      <div>
        <h3>Study Conclusions</h3>
        <p>Key takeaways from the analysis.</p>
      </div>
    </li>
    <li class="toc-item">
      <span class="toc-num">05</span>
      <div>
        <h3>Bibliography</h3>
        <p>References and further reading.</p>
      </div>
    </li>
  </ol>
</div>

---
layout: blank
transition: fade-out
class: h1-gradient
---

<Placeholder full label="Section 01 · main visual" hint="Full-slide diagram or component (like the Anthropic architecture slide)." />

---
layout: lava-cover
transition: fade-out
class: h1-gradient
---

# [Question that opens section 02?]

---
layout: lava-cover
transition: fade-out
class: h1-gradient
---

<div class="flex items-center justify-center gap-10 mt-12">
  <div class="w-60 h-60"><Placeholder label="Logo A" /></div>

  <span class="text-3xl font-bold text-gray-400">VS</span>

  <div class="w-60 h-60"><Placeholder label="Logo B" /></div>
</div>

---
layout: blank
transition: view-transition
class: h1-gradient
---

<Placeholder full label="Comparison table · A vs. B" />

---
layout: blank
transition: view-transition
---

<Placeholder full label="Comparison · focus on A" hint="Diagram for A revealed on click." />

---
layout: blank
transition: view-transition
---

<Placeholder full label="Comparison table · A vs. B" />

---
layout: blank
transition: fade-out
---

<Placeholder full label="Comparison · focus on B" hint="Diagram for B revealed on click." />

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
