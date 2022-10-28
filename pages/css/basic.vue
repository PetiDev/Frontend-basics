<template>
  <v-container>
    <h1>Alap formázások</h1>
    <v-alert type="error">
        Még nincs kész
    </v-alert>
    <tagIntroCard v-for="tag in tags" :key="tag.title" :data="tag" />

  </v-container>
</template>

<script>
export default {
  data: () => ({
    tags: [
      {
        title: "color",
        description: [
          {
            text: "betűszín",
          },
        ],
        lang: "html",
        code: "<head>\n<style>\n    h2{\n        color: red;\n    }\n</style>\n</head>\n<body>\n    <h2>asdsad</h2>\n</body>",
      },
      {
        title: "font-family",
        description: [
          {
            text: "betűkészlet",
          },
        ],
        lang: "html",
        code: "<head>\n<style>\n    #a{\n        font-family: sans-serif;\n    }\n    #b{\n        font-family: \'Times New Roman\';\n    }\n</style>\n</head>\n<body>\n    <p id='a'>Árvíztűrő fúrógép</p>\n<p id='b'>Árvíztűrő fúrógép</p>\n</body>",
      },
    ],
  }),
};
</script>
