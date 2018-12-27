<template>
  <div>
    <center>
      <input
        ref="message"
        id="message"
        value=""
        v-model="message"
        @keyup.enter="submitMessage();"
        autocomplete="off"
      />
    </center>
    <br />
    <div></div>
    <div v-if="result" id="results">
      <center id="phrase">"{{ messageSended }}"</center>

      <div id="result-bar">
        <center>
          <span>-</span>
          <input
            type="range"
            min="-3"
            max="3"
            v-bind:value="result.score"
            class="slider"
            id="myRange"
          />
          <span>+</span>
        </center>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      message: "the life is beautiful and awesome, it's make my happy",
      messageSended: "",
      result: ""
    };
  },

  mounted() {
    console.log(this.$refs.message.focus()); //.focus();
  },
  methods: {
    submitMessage() {
      this.messageSended = this.message;
      const { SentimentAnalyzer } = require("node-nlp");

      const sentiment = new SentimentAnalyzer({ language: "en" });
      this.result = sentiment.getSentiment(this.messageSended);
      console.log(this.result); // Score: -2, Comparative: -0.666
    }
  }
};
</script>
