<template>
  <div>
    <center>
      <input
        id="message"
        value=""
        v-model="message"
        @keyup.enter="submitMessage();"
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
    <div v-if="!result" id="how-to">
      <center>
        <img
          src="http://icons.iconarchive.com/icons/diversity-avatars/avatars/128/robot-02-icon.png"
          width="100"
        /><br />
        Ingrese una frase arriba (en inglés) y esta inteligencia artificial<br />
        distinguira si su frase expresa algo positivo o negativo.
      </center>
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
