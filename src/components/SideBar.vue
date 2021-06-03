<template>
  <div class="sideBar">
    <h3>Question Type</h3>
    <div>
      <div class="questionTypes">
        <select v-model="questionType" name="text_response" id="responseType">
          <option>Text Response</option>
        </select>
      </div>
      <div class="timeLimit">
        <p>Timer Limit (Seconds)</p>
        <input
          type="range"
          min="5"
          v-model="limit"
          class="inputRange"
          max="60"
          step="5"
        />
        <div class="numberRanges">
          <p>5</p>
          <!-- <p>10</p> -->
          <p>20</p>
          <!-- <p>30</p> -->
          <p>40</p>
          <!-- <p>50</p> -->
          <p>60</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  updated() {
    this.$emit("types", { limit: this.limit, type: this.questionType });
    console.log("updated");
  },

  unmounted() {
    (this.limit = ""), (this.questionType = "");
    console.log("unmounted");
  },

  data() {
    return {
      limit: 5,
      questionType: "Text Response",
    };
  },
};
</script>

<style>
.sideBar {
  background: white;
  padding: 0 10px;
}

.questionTypes {
  padding-top: 20px;
  padding-bottom: 40px;
}

#responseType {
  width: 80%;
  border-radius: 10px;
  height: 50px;
  padding: 10px;
  font-size: 16px;
}

.timeLimit {
  border-top: 1px solid grey;
  padding-top: 40px;
}

.timeLimit p {
  padding-bottom: 10px;
  font-weight: 600;
}

.inputRange {
  width: 100%;
  /* padding: 10px; */
}

.numberRanges {
  display: flex;
  justify-content: space-between;
}

.numberRanges p {
  font-size: 18px;
  padding-right: 10px;
}
</style>
