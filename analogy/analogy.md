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
    /*display: none;*/
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

By Zory Zhang

<!-- headingDivider: 2 -->
<!-- footer: 2023 Dec, Zory Zhang: Build and Characterize Artificial Reasoning System -->
<!-- paginate: true -->


# Outline
<embed src="telescope1.pdf" width="100%" height="100%" type="application/pdf">