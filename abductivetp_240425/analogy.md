---
marp: true

#theme: beamer
#theme: dracula
theme: gaia
#theme: uncover

math: mathjax
transition: fade
---

<!---
https://marp.app/docs
https://github.com/rnd195/my-marp-themes/blob/main/beamer.css
-->

<style>
section { font-size: 42px; }

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

figcaption {
    /*background-color: black;*/
    /*color: white;*/
    font-size: 30px;
    font-style: italic;
    padding: 1px;
    text-align: center;
}
.floatingb {
    position: absolute;
    bottom: 0;
}
.floatingt {
    position: absolute;
    top: 0;
}
.floatingl {
  float: left;
  width: 50%;
}
.floatingr {
  float: right;
  width: 50%;
}
</style>

# <!--fit--> Let AI Explain Math
<!-- _class: lead -->
<style scoped>
section { font-size: 45px; }
</style>
(Ongoing) AbductiveTP: Abduction via Analogical Divide-and-conquer Planning Facilitates Formal Mathematical Reasoning

Presented by Zory Zhang @ <a border="0" style="cursor:default" rel="nofollow"></a><img src="../figs/university-of-illinois-1.svg" width="2%">

Apr 25, 2024

# Is GPT Your Husband?
- Me: "Show $3 ∣ (n ^ 3 - n)$ for any n"
* ChatGPT 3.5 (Apr 20, 2024):
    <figure>
    <img src="../figs/smart_gpt.png" width="103%">
    <figcaption>https://chat.openai.com/share/0d69988d-aedd-4199-9c63-f5c7916c85e5</figcaption>
    </figure>

<!-- headingDivider: 2 -->
<!-- paginate: true -->

# Is GPT Your Husband? (cont')
<img src="../figs/noyes.png" style="width:60%;">

# 1 The Question
<!-- _class: lead -->
<style scoped>
section { font-size: 50px; }
</style>

##### "How well can AI explain a mathematical statement in _formal language_"
<!--(e.g. a homework problem that ask for a proof)-->

<!--* <span class="morph" style="--morph-name:m1;">Why explain</span>
* Why math-->

## 1.1 Formal Math
* Formal math $\approx$ a programming language
    * Compilation pass :arrow_right: **certifiably correct**
    * Proof in formal math $\approx$ validity **no worry** 

* **Lean 4**: programming language
* **lean prover**: proof assistant $\approx$ compiler

<!--- "checks that these proofs are correct down to their logical foundation"
- logical foundation: dependent type theory (DTT)-->

## 1.1 Formal Math (cont')
- Adapted from <a href="#footnote-4a">[4]</a>:
* <img src="../figs/atp1.png" alt="" width="100%">
* <img src="../figs/atp3.png" alt="" width="100%">

<div class="floatingb">
<h4></h4>
<sub><sub><sub><ol start="4">
    <li id="footnote-4a">Yang et, al. LeanDojo: Theorem Proving with Retrieval-Augmented Language Models. 2023.</li>
</ol></sub></sub></sub>
</div>

## 1.3 Contribution
<style scoped>
section { font-size: 50px; }
</style>

<!--pause here to wake people up-->
We show a technique that 
- improves the ability of *an AI system* 
- to explain mathematical statements 
- in formal language

# 2 What accounts for good explanations
<!-- _class: lead -->
<!-- code -> parsing tree -> show definition is easy -->
<!-- Click a concept -> see definition -->

## 2.1 Explaining what?
* What does the theorem say?
    * IS useful
    * :x: Yet Easy given formalization in code
* :heavy_check_mark: "Why this is a theorem"
    * The hardest part during math courses
    * "Math maturity"

## 2.2 What does a good explanation look like
<!-- 
- A valid proof showing the necessity of the assumptions (E.g. by counter-examples).

- A valid proof showing the sufficiency of the assumptions.

- Connects to knowledge and beliefs the performer already has.

- **Hierarchy/flexibility**: A proof that is structured and to the point in every local step.
-->

* **Necessity**: Why all assumptions are necessary
* **Validity**: Why conclusion follows
* **Past experience**: What does the audience already know
* **Hierarchy/flexibility**: In a moment

## 2.2 What does a good explanation look like (cont')
<!--
Is the yellow box an explanation?
Yes, a very brief one.
So-called “selected” explanation.
I call it hierarchical explanation: take whatever level of detail you want.
The most complete one: a certifiably valid proof.
-->
* Show $\sum_{n=1}^{\infty} \frac{1}{n(n+1)} =1$
* <img src="../figs/ex1_src_local.png" alt="" width="100%">

## 2.2 What does a good explanation look like (cont')
<style scoped>
section { font-size: 30px; }
</style>
<img src="../figs/ex1_src.png" alt="" width="75%">

# 3 Method: How to explain math
* **<span class="morph" style="--morph-name:m3;">Reflection of Human Reasoning</span>**

# 3.1 <span class="morph" style="--morph-name:m3;">Reflection of Human Reasoning</span>
- Analogy
- Planning

# 3.1.1 Analogy
<!--
Suppose Never learned "proof by induction"

Now you learned a technique without necessarily knowing the name.
* Most of the techniques are nameless.
* Yet you remember them to succeed in the exam.
-->
    
* Lecture: "Prove $2 ^ n > n$ for any n."
    * Can be solved by having inductive hypothesis ih
    * ih: $\forall m \in \mathbb{N}, 2^m > m \implies 2^{m+1} > m+1$
* Homework: "Prove $3 ∣ (n ^ 3 - n)$ for any n."
    * ih: $\forall m \in \mathbb{N}, 3 ∣ (m ^ 3 - m) \implies 3 ∣ ((m+1) ^ 3 - (m+1))$

# 3.1.2 Planning
<!--
If I try to explain A, I decompose it into B and C.
Since B and C are independent, I can explain them separately.
Suppose B is hard, I decompose it into D and E...
-->
* <img src="../figs/ex1_src_local.png" alt="" width="100%">

# 3 Method: How to explain math
<!-- _class: lead -->
<!-- ah, finally. are you ready? -->

- Reflection of human reasoning
- **<span class="morph" style="--morph-name:m4;">How to build AI systems to explain</span>**

## 3.2 <span class="morph" style="--morph-name:m4;">How to build AI systems to explain</span>
1. *Necessity*
2. *Validity*
3. *Past experience*
4. *Hierarchy/flexibility*

## 3.2.1 Necessity
<!--An example of a proof goal/state-->
<!--<figure>
<img src="../figs/proof_state.png" alt="" width="100%">
<figcaption>Two need justification: 5th and 7th</figcaption>
</figure>-->
* $$A,B \implies C$$
* $$\neg (B \implies C)$$
* $$B \wedge \neg C$$

## 3.2.2 Validity: **Formal Math**
Write proof in formal math $\approx$ validity checker :heavy_check_mark:
<!--A more complicated example:
<figure>
    <img src="../figs/ex2_src.png" alt="" width="100%">
    <figcaption>A hierarchical proof</figcaption>
</figure>-->

<!--<figure>
    <img src="https://leandojo.org/images/LeanDojo.jpg" alt="" width="100%">
    <figcaption></figcaption>
</figure>-->

## 3.2.3 Past experience: **Analogy**
<!--
Q: Analogy between what?
* A: Between the local action that captures the essence
-->

* Express past experience as a **knowledge corpus**
* Draw **analogies** between the current problem and problems in the corpus
* Transfer the whole proof? :x:
* Transfer the **key observation/hypothesis** will be enough

## 3.2.3 Past experience: Analogy (cont')
<!-- the same example. just want to show you this is sufficient -->
* Source
    - "Prove $2 ^ n > n$ for any n."
    - have $ih: \forall m \in \mathbb{N}, 2^m > m \implies 2^{m+1} > m+1$
* Target
    * "Prove $3 ∣ (n ^ 3 - n)$ for any n."
    * \<to_be_completed\>

## 3.2.4 Hierarchy/flexibility: **Search for plan tree**
<style scoped>
section { font-size: 30px; }
</style>
Recall: (from <a href="#footnote-4c">[4]</a>)
<img src="../figs/atp1.png" alt="" width="100%">
<img src="../figs/atp3.png" alt="" width="100%">

<div class="floatingb">
<h4></h4>
<sub><sub><sub><ol start="4">
    <li id="footnote-4c">Yang et, al. LeanDojo: Theorem Proving with Retrieval-Augmented Language Models. 2023.</li>
</ol></sub></sub></sub>
</div>

## 3.2.4 Hierarchy/flexibility: **Search for plan tree** (cont')
<style scoped>
section { font-size: 30px; }
</style>
<figure>
<img src="../figs/atp2.png" alt="" width="100%">
<figcaption>A search tree from <a href="#footnote-4b">[4]</a></figcaption>
</figure>

<div class="floatingb">
<h4></h4>
<sub><sub><sub><ol start="4">
    <li id="footnote-4b">Yang et, al. LeanDojo: Theorem Proving with Retrieval-Augmented Language Models. 2023.</li>
</ol></sub></sub></sub>
</div>

## 3.2.4 Hierarchy/flexibility: **Search for plan tree** (cont')
<!-- such search for sequential steps is mindless. people make plan before dirty works -->

<figure>
<img src="../figs/ex1_src_local.png" alt="" width="100%">
<figcaption>A plan tree</figcaption>
</figure>



## 3.2.4 Hierarchy/flexibility: **Search for plan tree** (cont')
<!-- yellow one and green one are independent. -->
<!-- if I make plan by pointing out key points and decompose the problem, we get a high-quality plan tree. -->

<style scoped>
section { font-size: 20px; }
</style>

<img src="../figs/ex1_src.png" alt="" width="80%">

## 3.2.4 Hierarchy/flexibility: **Search for plan tree** (cont')
<!--
BFSer is a baseline that searches sequentially.
DCSer instead, tries to find key observations and decompose the problem.
-->

<style scoped>
section { font-size: 20px; }
</style>

<img src="../figs/search_tree.png" alt="" width="60%">

## 3.2.3 Summary
* *Necessity*: drop a condition and prove the negated goal (flip quantifiers in assmptions as well) :arrow_right: Validity
* *Validity*: **Formal** math language
* *Past experience*: **Analogy**
* *Hierarchy/flexibility*: Search for the **plan tree**

# 4 Implementation
<style scoped>
section { font-size: 50px; }
</style>

Basically, a few LLMs talking to each other.

# 5 Experiment
<!-- distribution plot: block the result and only show axes first -->

- Dataset = **mathlib**: a unified library of formalized mathematics definitions & theorems in Lean, proven by human experts.
- Pass@1: time limit=10min per theorem, the percentage of theorems proven

# 5 Experiment (cont')
|                | Pass@1 on test set |
|:-----------------------:|:-------------------------------:|
| GPT-4 | 7.4%                               |
|    BFSer (ReProver) <a href="#footnote-4f">[4]</a>   | 30%                              |
|       DCSer[v1]       | 25%                               |

<div class="floatingb">
<h4></h4>
<sub><sub><sub><ol start="4">
    <li id="footnote-4f">Yang et, al. LeanDojo: Theorem Proving with Retrieval-Augmented Language Models. 2023.</li>
</ol></sub></sub></sub>
</div>

# 6 Implication
<style scoped>
section { font-size: 40px; }
</style>
~~Help with your homework~~

1. By producing lean proof (VScode extension called LeanDojo <a href="#footnote-4g">[4]</a>)
<img src="../figs/atp_leancopilot.png" alt="" width="100%">

<div class="floatingb">
<h4></h4>
<sub><sub><sub><ol start="4">
    <li id="footnote-4g">Yang et, al. LeanDojo: Theorem Proving with Retrieval-Augmented Language Models. 2023.</li>
</ol></sub></sub></sub>
</div>

# 6 Implication (cont')
<style scoped>
section { font-size: 20px; }
figcaption {
    font-size: 16px;
}
</style>

2. By ChatGPT Extension

<div class="floatingl">
    <figure>
        <img src="../figs/atp_gpt_ext.png" alt="" width="100%">
        <figcaption>LeanDojo paper.</figcaption>
    </figure>
</div>
<div class="floatingr">
    <img src="../figs/atp_gpt_ext2.png" alt="" width="100%">
</div>

# Takeaway
<!-- _class: lead -->

<style scoped>
section { font-size: 50px; }
</style>
Hierarchical divide-and-conquer planning improves the ability of an AI system to explain mathematical statements in formal language.

# Acknowledgement

<style scoped>
figcaption {
    font-size: 20px;
}
</style>

Supervisor: Dr. Jiaxuan You @ <a border="0" style="cursor:default" rel="nofollow"></a><img src="../figs/university-of-illinois-1.svg" width="2%">

Joint work with:
<div class="floatingl">
    <div class="floatingl">
        <figure>
        <img src="https://avatars.githubusercontent.com/u/91206366?v=4" alt="" width=200>
        <figcaption>Ziyu Zhou<br>https://subfish-zhou.github.io/</figcaption>
        </figure>
    </div>
    <div class="floatingr">
        <figure>
        <img src="https://haoranzhao419.github.io/images/haoran.jpg" alt="" width=200>
        <figcaption>Haoran Zhao<br>https://haoranzhao419.github.io/</figcaption>
        </figure>
    </div>
</div>
<div class="floatingr">
    <div class="floatingl">
        <figure>
        <img src="https://avatars.githubusercontent.com/u/90024054?v=4" alt="" width=200>
        <figcaption>Yicheng Wang<br>https://ywangmy.github.io/</figcaption>
        </figure>
    </div>
    <div class="floatingr">
        <figure>
        <img src="https://media.licdn.com/dms/image/D4E35AQHVaE2cqxnD_A/profile-framedphoto-shrink_800_800/0/1693258741848?e=1714284000&v=beta&t=J4mtHOJiCvJ09WMwz4Q60I6UpF3HPOja7hNxd62NQ50" alt="" width=200>
        <figcaption>Yan Li<br>@yan-li-8a2205225 on linkedin</figcaption>
        </figure>
    </div>
</div>

# Q&A
<!-- _class: lead -->
- Thank you for listening!
- Please contact Zory if you're willing to preview the paper draft / want to have copy of the slides.
- Get notified when it's on arxiv / the open-source software is out? Just follow `@zory_zhang` on X.

# Backup slides


# Is GPT Your Husband? (cont')
- Me: "Show $5 ∣ (n^{5}-5n^{3}+4n)$ for any n"
* Claude 3 Sonnet (Apr 20, 2024): <img src="../figs/smart_claude.png" width="100%">


## 1.1 <span class="morph" style="--morph-name:m1;">Why explain</span>
<!-- many explanation are causal: his early death cannot explain his smoking -->
<!-- many explanation are mechanistic: car is moving because the engine drives the wheel -->
1. Human (Education):
    - **Learn** through the process of explanation <a href="#footnote-1a">[1]</a>
        * Understanding: Evoke *category, causal & mechanistic* thinking
        * Updating: *Incomplete & inconsistent* knowledge from the past


<div class="floatingb">
<h4></h4>
<sub><sub><sub><ol>
    <li id="footnote-1a">Lombrozo. Explanation and Abductive Inference. In The Oxford Handbook of Thinking. 2012.</li>
</ol></sub></sub></sub>
</div>

## 1.1 Why explain (cont')
1. Human (Education):
    - **Learn** through the process of explanation
    * **Inference** based on explanation <a href="#footnote-1b">[1]</a>
        * Q: Why can't I find my key? 
        * Explanation: It must be in the car (therefore I can't find)
        * Inference: I should check the car
    * **Communication** & **retention**: highlight the key points


<div class="floatingb">
<h4></h4>
<sub><sub><sub><ol>
    <li id="footnote-1b">Lombrozo. Explanation and Abductive Inference. In The Oxford Handbook of Thinking. 2012.</li>
</ol></sub></sub></sub>
</div>

## 1.1 Why explain (cont')
<!--- knowledge corpus: a good place to draw analogy from-->
        
1. Human (Education)
2. AI (Scientific advances)
    * Explanation-based learning (EBL) <a href="#footnote-2">[2]</a>
        - Emulate "learning through the process of explanation"
    * Explanations (the product) as knowledge corpus <a href="#footnote-3">[3]</a>
        - Solve new problems by transfering seen explanations 


<div class="floatingb">
<h4></h4>
<sub><sub><sub><ol start="2">
    <li id="footnote-2">Dejong & Mooney. Explanation-based learning: An alternative view. 1986.</li>
    <li id="footnote-3">E.g. Yoo and Fisher. Concept Formation over Explanations and Problem-Solving Experience. 1991.</li>
</ol></sub></sub></sub>
</div>

## 1.2 Why (formal) math
1. ***Accurate*** measure of intelligence
    * (Explicitly) test **abstraction** ability
    * Closed-world
        - No missing information
        - No hidden common sense assumptions

## 1.2 Why (formal) math (cont')
<!--* Math demands and celebrates **understanding**-->

1. ***Accurate*** measure of intelligence
2. ***Easy*** to measure
    * Unambiguous / objective
    * Formal math: a programming language
        - Can be checked **automatically**
        - Compilation pass :arrow_right: **Correctness guaranteed**

- <span class="morph" style="--morph-name:m2;">What count as explanation</span>
- What does an good explanation look like

## 2.1 <span class="morph" style="--morph-name:m2;">What count as explanation</span>
* Type <a href="#footnote-1a">[1]</a>: 
    * **Mechanistic**: "It is moving because the engine drives the wheel to spin"
    * **Causal**: "It is moving because the wheel is spinning"
    * **Unification / subsumption**: "It is moving because it's a car"
* In math: Mechanistic :heavy_check_mark:

<div class="floatingb">
<h4></h4>
<sub><sub><sub><ol>
    <li id="footnote-1a">Lombrozo. Explanation and Abductive Inference. In The Oxford Handbook of Thinking. 2012.</li>
</ol></sub></sub></sub>
</div>

# 3.1.1 Planning
<!--- Experts make plans to solve hard problems.-->
<!--Blue ones are the subgoals that all their predecessors are proved.-->
<figure>
    <img src="https://terrytao.files.wordpress.com/2023/11/image.png" alt="" width="100%">
    <figcaption>https://terrytao.wordpress.com/2023/11/18/formalizing-the-proof-of-pfr-in-lean4-using-blueprint-a-short-tour/
</figcaption>
</figure>

## 3.2.3 Past experience: Analogy (cont')
<!--Where in the proof do you think that captures the essence of the problem?-->
<figure>
    <img src="../figs/ex2_src.png" alt="" width="100%">
    <figcaption></figcaption>
</figure>

Now: Prove $3 ∣ (n ^ 3 - n)$ for any n


## 3.2.3 Past experience: Analogy (cont')
<style scoped>
section { font-size: 30px; }
</style>
<!-- so although the proof is quite different, we draw analogy between essence -->
<img src="../figs/ex2_tgt.png" alt="" width="100%">


## 3.2.3 Past experience: Analogy (cont')
* <img src="../figs/ex1_src_local.png" alt="" width="70%">
* <img src="../figs/ex1_tgt_local.png" alt="" width="70%">

## 3.2.5 Plan tree and analogy
<style scoped>
section { font-size: 30px; }

.floatingl {
  float: left;
  width: 50%;
}
.floatingr {
  float: right;
  width: 40%;
}
</style>

Let's try the harder one.

<div class="floatingr">
<img src="../figs/ex1_src.png" alt="" width="100%">
</div>

## 3.2.5 Plan tree and analogy (cont')
<style scoped>
section { font-size: 30px; }

.floatingl {
  float: left;
  width: 59%;
}
.floatingr {
  float: right;
  width: 40%;
}
</style>

<!-- Now you get a homework. -->

<div class="floatingl">
<img src="../figs/ex1_tgt_local.png" alt="" width="100%">
</div>

<div class="floatingr">
<img src="../figs/ex1_src_local.png" alt="" width="100%">
</div>

## 3.2.5 Plan tree and analogy (cont')
<style scoped>
section { font-size: 30px; }

.floatingl {
  float: left;
  width: 59%;
}
.floatingr {
  float: right;
  width: 40%;
}
</style>

<!-- Now we might draw an analogy from another source to obtain another hypothesis in the green box. -->

<div class="floatingl">
<img src="../figs/ex1_tgt.png" alt="" width="100%">
</div>

<div class="floatingr">
Source: some other problem-proof pair in the knowledge corpus
</div>

# 4 Implementation
* Validity: ReProver <a href="#footnote-4e">[4]</a>
    - Lean as the **verifier**
* Search for **plan tree**
    - LLM as decomposition **proposer**
    - LLM as the evaluator to find the **best plan**: minimize the difficulty of the hardest subgoal after decomposition

<div class="floatingb">
<h4></h4>
<sub><sub><sub><ol start="4">
    <li id="footnote-4e">Yang et, al. LeanDojo: Theorem Proving with Retrieval-Augmented Language Models. 2023.</li>
</ol></sub></sub></sub>
</div>

# 4 Implementation (cont')
<embed src="../figs/analogyTP.drawio.pdf" width="100%" height=400px type="application/pdf">

# 4 Implementation (cont')
- Analogy: 
    - LLMs: GPT4 / Llama 3 / Claude 3 haiku
    - Learning and Inference with Schemas and Analogies (LISA) <a href="#footnote-5">[5]</a>
    - Structure-Mapping Engine (SME) <a href="#footnote-6">[6]</a>

<div class="floatingb">
<h4></h4>
<sub><sub><sub><ol start="5">
    <li id="footnote-5">Hummel & Holyoak. A symbolic-connectionist theory of relational inference and generalization. 2003.</li>
    <li id="footnote-6">Falkenhainer, Forbus & Gentner. The structure-mapping engine: Algorithm and examples. 1989.</li>
</ol></sub></sub></sub>
</div>

# 9. Future work
<!-- _class: lead -->
- Add analogy component.
- Further improve score by careful optimization techniques.

## Analogy

- Use analogical inference to suggest a hypothesis.
- Analogy is conducted by explicitly constructing a translation mapping between scenarios and translate the goal decomposition used in the target scenario back to the source scenario.
- E.g. Telescoping trick.


## Planning
- Interactive proof assistant can be viewed as a world model for theorem proving that predicts consequences of proposed actions, which enables planning.
    - IOW, formal math as a special case of general planning.
    - We suggest to implement inference-to-the-best-explanation via a new planning policy based on searching for a divide-and-conquer strategy that reduces the difficulty the most.

## Planning policy
<!-- backgroundColor: white -->
<img src="../figs/two_trees.png" alt="" width="80%">

---
<!-- backgroundColor: #{$bg} -->


- Assume we have a objective estimator to evaluate difficulty.
- Prioritize *search tree* branch (tactic) that minimize the value of cost function = $\max_{\text{existing subgoals } s} \{ \text{difficulty}(s) \}$, which is defined on *proof tree*.

# Conclusion
- While analogy provides motivation of the proof, the planning policy encourages the proof to be hierarchically structured and insightful.
- We implement this framework using a neural-symbolic architecture and show that it mitigate the gap between AI and human mathematician on the quality of the produced proof.

# Design elements
<style scoped>
section { font-size: 30px; }

.container {
position: relative;
text-align: center;
/*color: white;*/
}

/* Top left text */
.top-left {
position: absolute;
top: 8px;
left: 10%;
}

/* Top right text */
.top-right {
position: absolute;
top: 8px;
right: 10%;
}

/* Bottom left text */
.bottom-left {
position: absolute;
bottom: -450px;
left: 10%;
}

/* Bottom right text */
.bottom-right {
position: absolute;
bottom: -450px;
right: 10%;
}

/* Centered text */
.centered {
position: absolute;
top: 50%;
left: 50%;
transform: translate(-50%, -50%);
}

figcaption {
    font-size: 20px;
}
</style>

<div class="container"> 
    <div class="top-left">
        <figure>
        <img src="https://avatars.githubusercontent.com/u/91206366?v=4" alt="" width=100>
        <figcaption>Ziyu Zhou<br>https://subfish-zhou.github.io/ </figcaption>
        </figure>
    </div>
    <div class="top-right">
        <figure>
        <img src="https://haoranzhao419.github.io/images/haoran.jpg" alt="" width=100>
        <figcaption>Haoran Zhao<br>https://haoranzhao419.github.io/</figcaption>
        </figure>
    </div>
    <div class="bottom-left">
        <figure>
        <img src="https://avatars.githubusercontent.com/u/90024054?v=4" alt="" width=100>
        <figcaption>Yicheng Wang<br>https://ywangmy.github.io/</figcaption>
        </figure>
    </div>
    <div class="bottom-right">
        <figure>
        <img src="https://media.licdn.com/dms/image/D4E35AQHVaE2cqxnD_A/profile-framedphoto-shrink_800_800/0/1693258741848?e=1714284000&v=beta&t=J4mtHOJiCvJ09WMwz4Q60I6UpF3HPOja7hNxd62NQ50" alt="" width=100>
        <figcaption>Yan Li<br>@yan-li-8a2205225 on linkedin</figcaption>
        </figure>
    </div>
    <!--<div class="centered">Centered</div>-->
</div>