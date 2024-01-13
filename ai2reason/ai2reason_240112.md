---
marp: true

#theme: beamer
#theme: dracula
theme: gaia
#theme: uncover

transition: fade

style: |
  .morph {
    display: inline-block;
    view-transition-name: var(--morph-name);
    contain: layout;
    vertical-align: top;
  }

  /* Generic image styling for number icons */
  img:is([alt="1"], [alt="2"], [alt="3"], [alt="4"]) {
    height: 64px;
    position: relative;
    top: -0.1em;
    vertical-align: middle;
    width: 64px;
  }
---

<!---
https://marp.app/docs
https://github.com/rnd195/my-marp-themes/blob/main/beamer.css
-->

<style>
aside::before {
    content: "Speaker notes:";
    font-weight: bold;
}
aside {
    border: 1px black solid;
    padding: 10px 10px 10px 10px;
    font-size: 12px;
    line-height: 18px;
    background-color: #EFEFEF;
    position: relative;
    text-indent: 0.5em;
    display: none;
}
detaillevel1 {
    display: none;
}
detaillevel2 {
    display: none;
}
detaillevel3 {
    display: none;
}
</style>

# <!--fit--> AI2Reason
<style scoped>
section { font-size: 40px; }
</style>
Build and characterize artificial reasoning system that is truth-seeking, persuasive, and creative.

By Zory Zhang @ <a border="0" style="cursor:default" rel="nofollow"></a><img src="../figs/university-of-illinois-1.svg" width="2%">

<aside>
Version:
- elevator pitch (30s)
- talk with professors (10min): detaillevel0
- talk with interested senior (20min): detaillevel1
- talk with potential collaborators (40min): detaillevel2

Audience can ask for more elaboration on any part of the talk after the standard presentation.
</aside>

# Outline
Goal: introduce and ask for opinion on my long term vision of AI2Reason.

* <span class="morph" style="--morph-name:num1;">![1](https://icongr.am/material/numeric-1-circle.svg?color=666666)</span> What's AI2Reason
* ![2](https://icongr.am/material/numeric-2-circle.svg?color=666666) Why important at this moment
* ![3](https://icongr.am/material/numeric-3-circle.svg?color=666666) Why is it hard but promising now
* ![4](https://icongr.am/material/numeric-4-circle.svg?color=666666) My Next step

<!-- headingDivider: 2 -->
<!-- footer: 2024 Jan, Zory Zhang: Build and Characterize Artificial Reasoning System -->
<!-- paginate: true -->

# <span class="morph" style="--morph-name:num1;">![1](https://icongr.am/material/numeric-1-circle.svg?color=666666)</span> What's AI2Reason
<style scoped>
section { font-size: 30px; }
</style>
Outline recap:
1. #### **What's AI2Reason**
    - <span class="morph" style="--morph-name:letterA;">A. What's reasoning?</span>
    - B. Goal of AI2Reason
    - C. What aspects of intelligent system are covered?
    - D. What aspects of intelligent system are not covered?
2. Why important at this moment
3. Why is it hard but promising now
4. My Next step

## <span class="morph" style="--morph-name:letterA;">A. What's reasoning?</span>

* From everyday problem-solving to scientific innovation
* Let me examplify.

<aside>
To examplify this idea, I will cover three examples of reasoning abilities at different level ...
</aside>

---

### From **solving math word problems**
- Representative problem-solving skill
- Huge individual difference
- People think those who are good at math are smart

### To **general problem-solving**
- Detective games / "where did I put my key?"
- Plan a wedding
- ...

---

### To serve as a **scientific enquiry assistant**
<style scoped>
.floatingl {
  float: left;
  width: 60%;
}
.floatingr {
  float: right;
  width: 40%;
  font-size: 20px;
}
</style>
<div class="floatingl">

* Try to **explain** observation
* By generating **hypothesis**
* Reasoning on hypothesis
    * Get **implications**
    * Thought / real world **experiment**
</div>
<div class="floatingr">

<img src="https://plato.stanford.edu/entries/thought-experiment/figure6.jpg" width="80%">

(Counterexample: give conclusion without observation or experiment)

</div>

---

### To **develop new theory**
<style scoped>
.floatingl {
  float: left;
  width: 60%;
}
.floatingr {
  float: left;
  width: 40%;
}
</style>
<div class="floatingl">
<p>

- New schema
- :arrow_right:  New concepts
- :arrow_right:  Scientific concept / diagram innovation
- E.g. weight of object :arrow_right:  universal gravity
</p>
</div>
<div class="floatingr">

<img src="../figs/hypothesis.jpg" alt="From https://www.thoughtco.com/hypothesis-model-theory-and-law-2699066" width="100%">

</div>


<detaillevel3>

## B. Goal of AI2Reason
<style scoped>
.floatingl {
  float: left;
  width: 70%;
}
.floatingr {
  float: right;
  width: 30%;
  font-size: 30px;
}
</style>
<div class="floatingl">

1. **Qualities**
* **Truth-seeking** (objective): eliminate bias and fallacy
* **Persuasive** (show-your-step): provide reasoning steps as justification
* **Creative** (insightful): less patterned when possible
</div>
<div class="floatingr">
<a border="0" style="cursor:default" rel="nofollow"></a><img src="../figs/42.png" width="70%">

[When you don't show your reasoning...]
</div>

## B. Goal of AI2Reason (cont')

<style scoped>
section { font-size: 50px; }
</style>
* :x: Just *build* stronger computational model
* :heavy_check_mark: But **characterize** how to let AI reason in a **truth-seeking, persuasive, and creative** manner.

## C. What aspects of intelligent system are covered?
<aside>
These are just some terminalogies for people who happen to know them.
</aside>

<style scoped>
.floatingl {
  float: left;
  width: 70%;
}
.floatingr {
  float: right;
  width: 30%;
}
section { font-size: 32px; }
</style>
<div class="floatingl">
<p>

- **Deductive, inductive, abdutive reasoning**

- **Categorization and conceptualization**

- **Planning**

- **Causality**

- **Explanation seeking**

- (All of them are examplified in doing math)
</p>
</div>
<div class="floatingr">
  <detaillevel1>
  <img src="../figs/word_learning.png" alt="" width="70%">
  </detaillevel1>
</div>
<div class="floatingr">
  <detaillevel1>
  <img src="../figs/word_learning2.png" alt="" width="80%">
  </detaillevel1>
</div>

## D. What aspects of intelligent system are not covered?
<aside>
We are not as ambitious as you might think. I'd like to clarify some limitation of the diagram for now.
</aside>

- Perception / visual reasoning / embodied reasoning.
<aside>

- The input / output is already in / will be a symbolic form, e.g. mathematical formal language, causal relation graph, etc.
- Goal of reasoning is already given and assumed to be understood.

TODO: draw diagram on perception -> cognition
</aside>

- Decision making and ethics.
<aside>

- As an assistant.
</aside>

- Consciousness / self-awareness / active learning.
<aside>
The motivation of seeking explanatory power, creativity, and the desire to reason are hard-coded in the system. In other word, a zombie AI that has no consciousness.
</aside>

- Latency / efficiency / scalability.

</detaillevel3>

# 2 Why important at this moment
<style scoped>
section { font-size: 27px; }
</style>
Outline recap:
1. What's AI2Reason
2. #### **Why important at this moment**
    - <span class="morph" style="--morph-name:letterA;">A. Necessity</span>
    - B. Readiness
    - C. Mutual benefit
    - D. Social impact
3. Why is it hard but promising now
4. My Next step


## <span class="morph" style="--morph-name:letterA;">A. **Necessity**</span>
<detaillevel3>
- AGI should be able to **develop** **creative** yet still **persuasive** ideas by providing strong reasons to support them.
- Necessity of AI2Reason = necessity of AGI
- Why AGI? Self-improve intelligence :arrow_right: superintelligence :bangbang:
- ~~Who knows how far we are from meeting with aliens? As long as we don't destroy ourselves before that ...~~

<aside>
I'd like to claim the necessity of AI2Reason by reducing it as the question of necessity of AGI.
</aside>
</detaillevel3>

- LLMs **dream/hullucinate/bullshit**. They care about
    - :heavy_check_mark: what word will high likely follow the previous
    - :heavy_check_mark: entertain human
    -  :x: truth
- We :hearts: LLMs because
    - :heavy_check_mark: creativity
    -  :x: intelligent system with strong **generalizability** that can be said as doing "reasoning"

<detaillevel2>
<style scoped>
.floatingc {
  float: right;
  width: 85%;
}
</style>
- E.g. Ask "show me why gcd (n,n-1) = 1":
<div class="floatingc">
  <img src="../figs/chatgpt231214.png" alt="" width="83%">
</div>
</detaillevel2>


## B. **Readiness**
- More feasible than ever. We can
    - :repeat_one: **neuralize** many modules via auto-differentials
    - :speech_balloon: make use of the infinite expressive power of **natural language**
    - :thought_balloon: take LLMs as working (not satisfying) **creative engine**
- GPT-4 system:
    - A working (not that bad) example
## B. **Readiness** cont'
- **Cognitive scientist** have been studying reasoning for a while
    - Relatively complete charaterization of the analogical reasoning procedure
- **Formal method community / philosopher** have been studying logic for a while
    - Expressive formal logic: dependent type theory

## C. **Mutual benefit**
- Mutual benefit between "**building**" and "**characterizing**"
* :arrow_backward: Taking inspiration from theories on reasoning facilitates the development of AI.
* :arrow_forward: At the same time, building computational model is a good way to **complement/connect** current normative/philosophical/explanatory theory and descriptive/psychological understandings. (Thus this is a way to characterize what is plausible for such kind a system.)

<aside>
Connection: by providing implementation of descriptive theories, we can fill in practical gaps. By providing implementation of normative theories, we suggest feasible instantiation or alternatives.
</aside>

## D. **Social impact**
* :mortar_board: Educational **diagram** of reasoning for future generations.
* :two_men_holding_hands: Promote interdisciplinary collaboration. By promoting AI2Reason, we help foster an **environment** where researchers collaborate to advance AI technology more holistically.
* :high_brightness: Positive future for humanity: **advancing boundary** of intelligence, shape the future of humanity positively

<aside>
- AI2Reason can be an educational diagram for future generations to practice their reasoning skills, as an act to improve humanity.
- After all, researchers in academia are motivated by the desire to contribute to advancements that could shape the future of humanity positively.
</aside>

# 3 Why is it hard but promising now
<style scoped>
section { font-size: 26px; }
</style>
Outline recap:
1. What's AI2Reason
2. Why important at this moment
3. #### **Why is it hard but promising now**
    - <span class="morph" style="--morph-name:letterA;">A. Human is so smart</span>
    - B. My Point of view
    - C. Under this view, how to frame the problem?
    - D. What's different from before?
4. My Next step


## <span class="morph" style="--morph-name:letterA;">A. Human is so smart</span>
Human can capture concepts in so little context, mimic rules from so few examples, yet still be able to generalize to genuinely new situations.

<aside>
- "The word "five" has the Roman numeral "iv" in it? Show me how you developments your answer."
</aside>

<style scoped>
.floatingl {
  float: left;
  width: 30%;
}
.floatingr {
  float: left;
  width: 30%;
}
</style>

(Concept learning)
<div class="floatingl">
    <img src="../figs/induction1.png" alt="" width="100%">
</div>
<div class="floatingr">
    <img src="../figs/induction2.png" alt="" width="100%">
</div>

## B. My Point of view for AI2Reason
* People know LLM sucks in reasoning
    - Tried **heuristic-based** methods
    - Most try to improve its "performance" on "benchmarks".
* Yet few people **sit down and think about what is reasoning**.
    - Cognition >> pattern matching. Why expect solving reasoning in just a couple of years?
* Long history in philosophy and psychology. Why not learn from them?

## C. My framing of the problem
**Auto-differential neural-symbolic computational model.**
- A **preliminary** plan, only suitable for early stage
- :arrow_right: **High inductive bias**
- :arrow_right: **High data efficiency**
- :arrow_right: **Less flexible** (opposite to data-driven)

<detaillevel3>
<iframe src="./mindmap_231217.html" height="100%" width="100%" frameBorder="0"></iframe>
</detaillevel3>

## D. What's different from before?
Why haven't been solved before but promising now?
* Automated theorem proving is getting more and more attention. Better tools and **infrastructure** are built.
* Language is powerful.
    - LLMs enable the connection of different modules.
    - The stronger LLMs become, the better quantitative performance the system can show.

# 4 My Next step
Outline recap:
1. What's AI2Reason
2. Why important at this moment
3. Why is it hard but promising now
4. #### **My Next step**
    - Study reasoning process in doing math


## <!---fit---> Study reasoning process in doing math
* Humans favor **insightful** proofs
* Humans learn from **motivation** of proofs
* Humans perform **different kinds of reasoning** when doing math
    - Draw analogy to connect past experience with present
    - ...

## <!---fit---> Study reasoning process in doing math cont'

* AI4MATH? It is just a play ground. Math is the most abstract and formal yet established language we have. It is the best way to test the reasoning ability of an AI system.

* Automated theorem proving? Again, a play ground that is well-defined and established.

* **Verifiable** mathematical formal language: a preliminary interface between human and computer on doing proof

<detaillevel1>
<figure>
    <style>
        t {
        font-size: 10pt;
        }
    </style>
    <picture>
    <img src="../figs/proof_state.png" alt="An image" width="100%">
    </picture>
    <figcaption><t>A demo by Patrick Massot</t></figcaption>
</figure>
</detaillevel1>

# 5 Me >_<
<style scoped>
.floatingl {
  float: left;
  width: 60%;
}
.floatingr {
  float: right;
  width: 40%;
}
section { font-size: 30px; }
</style>
<div class="floatingl">
<p>

- https://zoryzhang.notion.site
- zoryz2@illinois.edu
- zory_zhang@X;
- zoryzhang@wechat

Join Discord right now to see what exciting things are happening! We welcome everyone who is interested in this direction.

Thank You! Q&A time!
</p>
</div>
<div class="floatingr">

**AI2Reason Community@Discord**
<a border="0" style="cursor:default" rel="nofollow"></a><img src="../figs/discord_qr.png" width="90%">
</div>
