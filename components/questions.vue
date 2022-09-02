<template>
  <section>
    <h1>Feladatok</h1>
    <pre
      v-for="task in data"
      :key="task.text"
      v-html="
        task.text
          .replace(/</g, '&#60;')
          .replace(/\>/g, '&#62;')
          .replace(
            /INPUT(\d+)(\w+)/g,
            `<input class='accent--text' maxlength='$1' id='$2'>`
          )
      "
    ></pre>
    <v-btn color="success" @click.stop="check()"
      ><b id="pointScreen" v-if="points">{{ points }} - </b> Kész
      <v-icon>mdi-check</v-icon></v-btn
    >
  </section>
</template>

<script>
export default {
  name: "questions",
  props: {
    data: Array,
  },
  methods: {
    check() {
      let points = 0;

      for (let x = 0; x < this.taskIDs.length; x++) {
        const taskID = this.taskIDs[x];
        let task = document.getElementById(taskID);
        console.log(task.value.toLowerCase());
        let userAns = task.value.toLowerCase();
        let ans = this.answerList[x].split("|");
        for (let y = 0; y < ans.length; y++) {
          if (userAns == ans[y]) {
            
            task.classList = "success--text right"
            points++;
            break;

          }

        task.classList = "error--text wrong"
        }
      }
      this.points = `${points} / ${this.taskIDs.length}`;
    },
  },
  data: () => ({
    points: "",
    taskIDs:[],
    answerList:[]
  }),
  mounted(){
    this.data.forEach(element => {
      this.taskIDs.push(...(element.text.match(/INPUT\d+(\w+)/g) || []).map(e => e.replace(/INPUT\d+/, '')))
      if (element.ans) {
        this.answerList.push(...element.ans)
      }
    });
    console.log(this.taskIDs);
    console.log(this.answerList)
  }
};
</script>

<style>
input {
  border-bottom: 2px solid white;
  text-align: center;
}
.wrong {
  border-bottom: 2px solid red;
  color: red;
}
.right {
  border-bottom: 2px solid greenyellow;
}

input[maxlength="6"] {
  width: 6ch;
}
input[maxlength="5"] {
  width: 5ch;
}
input[maxlength="4"] {
  width: 4ch;
}
input[maxlength="3"] {
  width: 3ch;
}
input[maxlength="2"] {
  width: 2ch;
}
input[maxlength="1"] {
  width: 1ch;
}
</style>