<template>
  <v-container>
    
    <h1>Köszöntelek a fronend alapok kurzuson</h1>
    <p>A kurzus célja hogy megértsd a HTML-t és CSS-t kezdő szinten</p>



    <section>
      <h2>Ajánlott:</h2>
      <sub>Én ezeket fogom használni</sub>
      <ul>
        <li>PC</li>
        <li>Visual Studio Code <v-btn href="https://code.visualstudio.com/download" target="_blank" icon><v-icon>mdi-download</v-icon></v-btn></li>
        <li>Firefox <sub>(bármilyen böngésző megteszi, csak lehet másképp néznek ki egyes dolgok)</sub><v-btn href="https://www.mozilla.org/hu/firefox/new/" target="_blank" icon><v-icon>mdi-download</v-icon></v-btn></li>
        <li>Valami zene amit szeretsz mert szét unod magad</li>
      </ul>
    </section>
    <blockquote>
  “First, solve the problem. Then, write the code.”
  <footer>
    <em>—John Johnson</em>
  </footer>
</blockquote>
  </v-container>
</template>

<script>
export default {
  name: 'IndexPage',
  
}
</script>

<style scoped>
blockquote{
  margin-top: 1rem;
}
</style>
