<template>
  <v-container>
    <h1>A kezdetek</h1>
<section>
  <h2>File</h2>
  <h3>HTML</h3>
  <p>A HTML fileok kiterjesztése <b>.html</b></p>
  <p>Akárminek hívhatjuk a file-t, de a böngészők alapértelmezetten az <b>index.html </b> file-t nyitják meg</p>
  <h3>CSS</h3>
  <p>A CSS file-ok kitejesztése kreatívan <b>.css</b></p>
</section>
<section>
    <h2>Tag-ek</h2>
    <h3>Felépítés</h3>
    <p>Általában egy nyitó és egy záró elemből állnak</p>
    <p>Van néhány kivétel mint például a <b>input</b>, <b>link</b>, <b>img</b>, stb.</p>
    <h3>Hogyan néz ki?</h3>
    <p>&#60;tagneve>  &#60;/tagneve></p>
    <p>&#60;nyitó>  &#60;/záró></p>
</section>

    <section>
      <h2>Alap dokumentum felépítése</h2>
      <span>
        <v-btn icon @click.stop="copy('<!DOCTYPE html>\n<html>\n<head>\n   <title>Document&#60;/title>\n</head>\n<body>\n\n</body>\n</html>')"><v-icon>mdi-content-copy</v-icon></v-btn>

        <pre>
<code v-highlight class="html">&#60;!DOCTYPE html>
&#60;html>
&#60;head>
    &#60;title>Document&#60;/title> 
&#60;/head>
&#60;body>

&#60;/body>
&#60;/html>
</code>
        </pre>
        <ul>
            <li><b>&#60;!DOCTYPE html></b> elem adja meg a böngészőnek hogy ez egy HTML file</li>
            <li>
                A <b>&#60;html></b> elem kell és kész
            </li>
            <li><b>&#60;head></b> ide jön az oldal címe és a felhasználó számára nem látható részek</li>
            <li><b>&#60;title</b> Az oldal címe</li>
            <li><b>&#60;body</b> ide jön minden amit a felhasználónak látniakell</li>
        </ul>
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
};
</script>

<style scoped>

ul{
    text-align: left;
}
.v-btn{
    float: right;
}
</style>