<template>
  <div class="app">
    <div class="topNav">
      <button class="submitQuestion">Done</button>
    </div>
    <div class="content">
      <Duplicates class="duplicated" />
      <MainContent class="main" @sendQuestions="allQuestions" />
      <SideBar class="sideBared" @types="submitQuestion" />
    </div>
  </div>
</template>

<script>
import Duplicates from "./components/Duplicates.vue";
import MainContent from "./components/MainContent.vue";
import SideBar from "./components/SideBar.vue";

export default {
  name: "App",
  components: {
    Duplicates,
    MainContent,
    SideBar,
  },
  data() {
    return {
      questions: [],
      typoo: [],
    };
  },

  methods: {
    submitQuestion(value) {
      this.typoo = value;
    },
    allQuestions(value) {
      this.questions = value;
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

body {
  box-sizing: border-box;
}

.topNav {
  height: 60px;
  display: flex;
  justify-content: flex-end;
}

.submitQuestion {
  /* background: rgba(3, 199, 3, 0.822); */
  background: #d60303a1;
  padding: 10px 20px;
  color: white;
  border-radius: 20px;
  margin: 5px 10px 5px 5px;
  border: none;
  font-size: 20px;
  width: 10%;
}

.app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background: rgba(176, 191, 197, 0.308);
  width: 100%;
  text-align: center;
}

.content {
  display: flex;
}

.duplicated,
.sideBared {
  width: 25%;
  padding-top: 50px;
}

.main {
  width: 50%;
  padding-top: 20px;
}
</style>
