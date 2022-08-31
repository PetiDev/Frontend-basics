<template>
  <v-container>
    <h1>Gyakran használt elemek</h1>
    <section>
      <h2>p - paragraph</h2>
      <p>Bekezdés</p>
      <span>
        <v-btn
          icon
          @click.stop="copy('<p> Valami szöveg </p>')"
          ><v-icon>mdi-content-copy</v-icon></v-btn
        >
        <pre>
                <code v-highlight class="html">
&#60;p> Valami szöveg &#60;/p>
                </code>
                </pre>
                <img src="../assets/img/second/p.png">
      </span>
    </section>
    <section>
      <h2>h1-6 - header</h2>
      <p>1-6 -os szitű fejléc</p>
      <p>Az 1-es a legnagyobb és a 6-os a legkiseb</p>
      <span>
        <v-btn
          icon
          @click.stop="
            copy(
              '<h1>Fejléc</h1><h2>kisebb fejléc</h2>\n<h3>Még kisebb fejléc</h3>\n<h4>Annál is kisebb fejléc</h4>\n<h5>Még annál is kisebb fejléc</h5>\n<h6>Lehető legkisebb fejléc</h6>\n'
            )
          "
          ><v-icon>mdi-content-copy</v-icon></v-btn
        >

        <pre>
                    <code v-highlight class="html">
&#60;h1>Fejléc&#60;/h1>
&#60;h2>kisebb fejléc&#60;/h2>
&#60;h3>Még kisebb fejléc&#60;/h3>
&#60;h4>Annál is kisebb fejléc&#60;/h4>
&#60;h5>Még annál is kisebb fejléc&#60;/h5>
&#60;h6>Lehető legkisebb fejléc&#60;/h6>
                </code>
                </pre>
                <img src="../assets/img/second/h.png">
      </span>
    </section>
    <section>
      <h2>div - division</h2>
      <p>Osztály</p>
      <p>Logikailag külön osztja az elemeket</p>
      <span>
        

<v-btn
          icon
          @click.stop="
            copy(
              '<h1> hírek </h1>\n<div>\n    <h2> cím </h2>\n    <p> Valami valami</p> \n</div>\n<div>\n    <h2> Másik cím </h2>\n    <p> Valami valami</p> \n</div>\n'
            )
          "
          ><v-icon>mdi-content-copy</v-icon></v-btn
        >



        <pre>
                    <code v-highlight class="html">
&#60;h1> hírek &#60;/h1>
&#60;div>
    &#60;h2> cím &#60;/h2>
    &#60;p> Valami valami&#60;/p> 
&#60;/div>
&#60;div>
    &#60;h2> Másik cím &#60;/h2>
    &#60;p> Valami valami&#60;/p> 
&#60;/div>
                </code>
                </pre>
                <img src="../assets/img/second/div.png">
      </span>
    </section>
    <section>
      <h2>a - anchor</h2>
      <p>Link</p>
      <p>Hivatkozás egy másik oldalra</p>
      <span>
        <v-btn
          icon
          @click.stop="
            copy(`<a href='https://petidev.tk'> A weboldalam </a>`)
          "
          ><v-icon>mdi-content-copy</v-icon></v-btn
        >
      <pre>
                    <code v-highlight class="html">
&#60;a href="https://petidev.tk"> A weboldalam &#60;/a>
                </code>
                </pre>
                <img src="../assets/img/second/a.png">
      </span>
    </section>
    <section>
      <h2>b - bold</h2>
      <p>Félkövér szöveg</p>
      <span>
        <v-btn
          icon
          @click.stop="
            copy(`<b> Vastag söveg </b>\n<p> Ez még nem vastag,<b> de ez már igen </b></p>`)
          "
          ><v-icon>mdi-content-copy</v-icon></v-btn
        >
      <pre>
      <code v-highlight class="html">
&#60;b> Vastag söveg &#60;/b> 
&#60;p> Ez még nem vastag,&#60;b> de ez már igen &#60;/b>&#60;/p> 
      </code>

    </pre>
    <img src="../assets/img/second/b.png">
      </span>
    </section>


    <section>
      <h2>i - italic</h2>
      <p>Dőlt szöveg</p>

      <span>
        <v-btn
          icon
          @click.stop="
            copy(`<i> Dőlt söveg </i>\n<p> Ez még nem dőlt,<i> de ez már igen </i></p>`)
          "
          ><v-icon>mdi-content-copy</v-icon></v-btn
        >
      <pre>
      <code v-highlight class="html">
&#60;i> Dőlt söveg &#60;/i> 
&#60;p> Ez még nem dőlt,&#60;i> de ez már igen &#60;/i>&#60;/p> 
      </code>
    </pre>
    <img src="../assets/img/second/i.png">
      </span>
    </section>

    <section>
      <h2>img - image</h2>
      <p>Kép</p>
      <p class="error--text">Nincs lezáró eleme</p>
      <span>
        <v-btn
          icon
          @click.stop="
            copy(`<img src='fox.png' alt='Ha nem jelenne meg a kép, vagy valaki képernyő olvasót használ'>`)
          "
          ><v-icon>mdi-content-copy</v-icon></v-btn
        >
      <pre>
      <code v-highlight class="html">
&#60;img src="fox.png" alt="Ha nem jelenne meg a kép, vagy valaki képernyő olvasót használ">  
      </code>
    </pre>
    <img src="../assets/img/second/img.png">
    <img src="../assets/img/second/nem_img.png">
      </span>
    </section>
  </v-container>
</template>

<script>
export default {
    methods: {
        copy(text){
            navigator.clipboard.writeText(text)
        }
    }
}
</script>

<style>
.v-btn {
  float: right;
}
</style>