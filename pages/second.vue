<template>
  <v-container>
    <h1>Gyakran használt elemek</h1>

    <tagIntroCard v-for="tag in tags" :key="tag.title" :data="tag" />

    <section>
      <h2>Feladat a leckéhez</h2>
      <div>
        <label for="a">A legkisebb szintű fejléc: </label>
        <input class="accent--text" type="text" maxlength="4" id="a" />
        <pre>
          <span>
&#60; <input class="accent--text"  type="text" maxlength="4" id="g"> &#62;
&#60; head &#62;
&#60; title &#62; Az oldal címe &#60; <input class="accent--text"  type="text" maxlength="6" id="b"> &#62;
&#60; /head &#62;
&#60; body &#62;
&#60; <input class="accent--text"  type="text" maxlength="2" id="c"> &#62; Egyes szintű címsor &#60; <input class="accent--text"  type="text" maxlength="3" id="d"> &#62;

&#60; <input class="accent--text"  type="text" maxlength="1" id="e"> &#62; Ez egy bekezdés &#60; <input class="accent--text"  type="text" maxlength="2" id="f"> &#62;

&#60; /body &#62;
&#60; /html &#62;
          </span>
        </pre>
        <v-btn color="success" @click.stop="check(['a','g','b','c','d','e','f'],['h6|<h6>','html','/title','h1','/h1','p','/p'])"><b id="pointScreen"></b> - Kész <v-icon>mdi-check</v-icon></v-btn>
        
      </div>

    </section>
  </v-container>
</template>

<script>
export default {
  methods: {
    copy(text) {
      navigator.clipboard.writeText(text);
    },
    check(tasks, answers){
      let pointScreen = document.getElementById("pointScreen")
      let points = 0
      for (let x = 0; x < tasks.length; x++) {
        const taskID = tasks[x];
        let task = document.getElementById(taskID)
        let userAns = task.value.toLowerCase()
        let ans = answers[x].split('|')

        for(let y = 0; y < ans.length; y++){
          if (userAns == ans[y]) {
            task.classList += " right"
            points++
            break
          }
        }
        task.classList += " wrong";

      }
    pointScreen.innerText = `${points} / ${tasks.length}`

    }
  },
  data: () => ({
    tags: [
      {
        title: "p - paragraph",
        description: [
          {
            text: "Bekezdés",
          },
        ],
        lang: "html",
        code: "<p> Valami szöveg </p>",
      },
      {
        title: "h1-6 - header",
        description: [
          {
            text: "1-6 -os szitű fejléc",
          },
          {
            text: "Az 1-es a legnagyobb és a 6-os a legkiseb",
          },
        ],
        lang: "html",
        code: "<h1>Fejléc</h1><h2>kisebb fejléc</h2>\n<h3>Még kisebb fejléc</h3>\n<h4>Annál is kisebb fejléc</h4>\n<h5>Még annál is kisebb fejléc</h5>\n<h6>Lehető legkisebb fejléc</h6>",
      },
      {
        title: "div - division",
        description: [
          {
            text: "Osztály",
          },
          {
            text: "Logikailag külön osztja az elemeket",
          },
        ],
        lang: "html",
        code: "<h1> hírek </h1>\n<div>\n    <h2> cím </h2>\n    <p> Valami valami</p> \n</div>\n<div>\n    <h2> Másik cím </h2>\n    <p> Valami valami</p> \n</div>",
      },
      {
        title: "a - anchor",
        description: [
          {
            text: "Link",
          },
          {
            text: "Hivatkozás egy másik oldalra",
          },
        ],
        lang: "html",
        code: "<a href='https://petidev.tk'> A weboldalam </a>",
      },

      {
        title: "b - bold",
        description: [
          {
            text: "Félkövér szöveg",
          },
        ],
        lang: "html",
        code: "<b> Vastag szöveg </b>\n<p> Ez még nem vastag,<b> de ez már igen </b></p>",
      },
      {
        title: "i - italic",
        description: [
          {
            text: "Dölt szöveg",
          },
        ],
        lang: "html",
        code: "<i> Dőlt szöveg </i>\n<p> Ez még nem dőlt,<i> de ez már igen </i></p>",
      },
      {
        title: "img - image",
        description: [
          {
            text: "Kép",
          },
          {
            text: "Nincs lezáró eleme",
            color: "#ff4757",
          },
        ],
        lang: "html",
        code: "<img src='https://www.petidev.tk/img/html.svg' title='EZ akkor jelenik meg ha ráhúzod az egered' width='45%' alt='Ha nem jelenne meg a kép, vagy valaki képernyő olvasót használ'>",
      },
    ],
  }),
};
</script>

<style>
input{
  border-bottom: 2px solid white;
  text-align: center;
}
.wrong{
  border-bottom: 2px solid red;
  color: red;
}
.right{
  border-bottom: 2px solid greenyellow;
}

input[maxlength="6"]{
  width: 6ch
}
input[maxlength="5"]{
  width: 5ch
}
input[maxlength="4"]{
  width: 4ch
}
input[maxlength="3"]{
  width: 3ch
}
input[maxlength="2"]{
  width: 2ch
}
input[maxlength="1"]{
  width: 1ch
}

</style>