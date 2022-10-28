<template>
  <v-container>
    <h1>Bemenetek</h1>
    <section>
      <h3>Több típusa is lehet:</h3>
      <ol>
        <li>Szöveges</li>
        <li>Jelszó</li>
        <li>Számos</li>
        <li>Radio</li>
        <li>Checkbox</li>
        <li>Range</li>
        <li>Szín</li>
        <li>Gomb, submit</li>
        <li>email</li>
        <li>date</li>
      </ol>
    </section>
    <tagIntroCard v-for="tag in tags" :key="tag.title" :data="tag" />
  </v-container>
</template>

<script>
export default {
  data: () => ({
    tags: [
      {
        description: [
          {
            text: "Példák:",
            bold: true,
          },
        ],
        lang: "html",
        code: "<input type='text' placeholder='szöveg'>\n<input type='password' placeholder='jelszó'>\n<input type='number' placeholder='szám'>\n<br>\n<input type='radio' name='a'><input type='radio' name='a'>\n<input type='checkbox'>\n<input type='range'>\n<input type='color'>",
      },
      {
        title: "label",
        description: [
          {
            text: "Cimke az inputhoz",
            bold: true,
          },
          {
            text: "A label tagnek van egy",
            inline: true,
          },
          {
            text: "for='id'",
            inline: true,
            bold: true,
          },
          {
            text: "eleme, ebbe lehet megadni hogy melyik input-hoz tartozik id alapján",
            inline: true,
          },
          {
            text: "Ha a labelre kattintunk úgy veszi mintha a hozzá tartozó inputra kattintanánk",
          },
        ],
        lang: "html",
        code: "<label for='age'>Korod:</label>\n<br>\n<input id='age' type='number'>\n<br>\n<label for='check'>[Katt ide]</label>\n<br>\n<input id='check' type='checkbox'>",
      },
    ],
  }),
};
</script>
