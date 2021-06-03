<template>
  <div class="mainContent">
    <div class="questionContainer">
      <input
        type="text"
        v-model="question"
        placeholder="Click to start typing your question"
      />
    </div>
    <div class="responseContainer">
      <div class="responseContain">
        <div class="response">
          <input
            v-for="(res, index) in resp"
            :key="index"
            ref="alt"
            type="text"
            placeholder="Response"
          />
        </div>
        <!-- Add response button -->
        <div @click="addResponse" class="addInputs">
          <img src="../assets/plus.png" class="addIcon" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  updated() {
    this.$emit("sendquestions", {
      question: this.question,
      answers: this.responses,
    });
  },

  unmounted() {
    (this.question = ""), (this.responses = "");
  },

  data() {
    return {
      responses: 2,
      alt: "",
      question: "",
      resp: ["fire", "dance"],
    };
  },
  methods: {
    addResponse() {
      this.resp.length += 1;
    },
  },
};
</script>

<style>
.mainContent {
  width: 100%;
  background: rgba(247, 247, 247, 0.856);
  padding: 40px;
  display: flex;
  flex-direction: column;
  height: 90vh;
}

.questionContainer {
  width: 100%;
}

.responseContainer {
  margin-top: 200px;
}

.responseContain {
  display: flex;
}

.questionContainer input {
  margin-top: 20px;
  width: 80%;
  font-size: 20px;
  font-weight: 600;
  padding: 10px;
  height: 40px;
  border-radius: 20px;
  border: 2px solid rgb(212, 212, 212);
}

.response {
  display: flex;
  flex-direction: column;
  margin: 0 auto;
  width: 50%;
}

.response input {
  height: 40px;
  margin-bottom: 20px;
  font-size: 16px;
  width: 100%;
  border-radius: 20px;
  border: 2px solid rgb(212, 212, 212);
  padding: 10px;
}

.addInputs {
  align-self: flex-end;
  margin: 0 0 10px 10px;
}

.addIcon {
  width: 50px;
  height: 50px;
  color: white;
  padding: 5px;
  border-radius: 50%;
  cursor: pointer;
}
</style>
