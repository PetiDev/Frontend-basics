<template>
  <v-container>
    <h1>Gyakran használt elemek</h1>

    <tagIntroCard v-for="tag in tags" :key="tag.title" :data="tag" />

    <questions :data="questionList" />
  </v-container>
</template>

<script>
export default {
  data: () => ({
    points : '',
    questionList: [
      {
        text:"A legkisebb szintű fejléc: INPUT4a",
        ans:["h6|<h6>"]
      },
      {
        text:"<INPUT4b>",
        ans:["html"]
      },
      {
        text:"<head>"
      },
      {
        text:"< title > Az oldal címe <INPUT6c>",
        ans:["/title"]
      },
      {
        text:"</head>"
      },
      {
        text:"<body>"
      },
      {
        text:"<INPUT2d> Egyes szintű címsor <INPUT3e>",
        ans: ["h1","/h1"]
      },
      {
        text:"<INPUT1f> Ez egy bekezdés <INPUT2g>",
        ans: ["p","/p"]
      },
      {
        text:"</body>"
      },
      {
        text:"</html>"
      },
    ],
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
