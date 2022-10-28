<template>
  <v-container>
    <h1>CSS</h1>
    <h3>
      Igen css, már most... de a HTML önmagában kb. annyi mint ami az előző
      kettőben le lett írva
    </h3>
    <section>
      <h2>Mi ez?</h2>
      <p>
        A CSS az angol „cascading style sheets” kifejezés rövidítése, ami
        magyarul „egymásba ágyazott stíluslapokat” jelent.<br>Ellentétben a HTML-el ez nem a weboldal szerkezetét határozza meg hanem a vizuális dolgokat:
         <ul>
            <li>Elrendezés</li>
            <li>Színek</li>
            <li>Betűkészlet</li>
            <li>Betűméret</li>
        </ul>
      </p>
    </section>
    <section>
        <h2>Hogyan?</h2>
        <p>
            Több módszer is van arra hogy css-t használjunk:
            <ul>
                <li>A HTML tag-ek ben</li>
                <li>A HTML file ban style tag-ek között</li>
                <li>És a külön file-ban</li>
            </ul>
            A példákban a 2. módszert fogom használni, az egyértelműség kedvéért <sub>(Meg mert egyszerűbb nekem megcsinálni)</sub>
            <br>
            Minden ami a style tag-ek között van külön fileban is megvalósítható, majd később kitérek rá hogy hogyan is.
        </p>
    </section>
    <section>
      <h2>Működése</h2>
      <p>
        A CSS-ben hivatkozni kell valamilyen módon a formázandó elemre.
        <ul>
          <li>
            class -al
            <ul>
              <li>Több elemre is rá lehet rakni</li>
              <li>css-ben: .classNev</li>
            </ul>
          </li>
          <li>id -vel
            <ul>
              <li>Csak egy elemhez tartozhat egy id</li>
              <li>css-ben: #classNev</li>
            </ul>
          </li>
          <li>A tag nevével
            <ul>
              <li>css-ben: tag</li>
            </ul>
          </li>
        </ul>
      </p>
      <pre>
        <code v-highlight class="html">
          &lt;head>
          &lt;style>
            .ezEgyClass{}
            #ezEgyId{}
            h3{}
            *{} &lt;!--Ez minden elemre hivatkozik-->
          &lt;/stlye>
          &lt;/head>
          &lt;body>
            &lt;p class="ezEgyClass">Class&lt;/p>
            &lt;p id="ezEgyId">ID&lt;/p>
            &lt;h3>tag&lt;/h3>
          &lt;/body>
        </code>
      </pre>
    </section>
    <section>
      <h2>Külön file</h2>
      <p>Célszerű így használni a CSS-t, hogy rendezetten tartsd a kódodat</p>
      <p>A <b>head</b>-tag ben kell hivatkozni a css file-ra ezen a módon</p>
      <pre>
      <code v-highlight class="html">
        <!DOCTYPE html>
        &lt;html>
        &lt;head>
          &lt;link rel="stylesheet" href="style.css"> &lt;!--A href-ban a css file elérésiútja van-->
        &lt;/head>
          ...
        &lt;/hml>
      </code>
      </pre>
    </section>
  </v-container>
</template>

<style scoped>
h3{
    text-align: center;
}
</style>