<template>
  <section>
    <h2>{{ data.title }}</h2>
    <p v-for="p in data.description" :key="p.text" :style="`color:${p?.color}`">
      {{ p.text }}
    </p>
    <span class="wrap">
      <v-btn icon @click.stop="copy()"><v-icon>mdi-content-copy</v-icon></v-btn>
      <pre>
      <code v-highlight :class="data.lang">
{{data.code}}
      </code>
    </pre>
      <iframe :srcdoc="data.code" frameborder="0"></iframe>
    </span>
  </section>
</template>
<script>
export default {
  name: "tagIntroCard",
  props: {
    data: Object,
  },
  methods: {
    copy() {
      navigator.clipboard.writeText(this.data.code);
    },
  },
};
</script>
<style scoped>
iframe {
  background: white;
}
.v-btn {
 float: right;
}
</style>
