<template>
  <div id="app">
    <center>
      <img src="../../assets/robot.png" width="130" /><br />
      <h1>Sens3</h1>

      <p id="how-to">
        Enter a text and Sens3 distinguish<br />
        if the phrase expresses something positive or negative
      </p>
    </center>
    <sense></sense>

    <center style="position:absolute; bottom:5px; right:5px">
      <small
        >BY <b>MAURO RONDINELLI</b> - BUILD WITH
        <b>VUE.JS / NODE.JS / NODE-NLP</b></small
      >
    </center>
  </div>
</template>

<script>
import Sense from "./components/Sense.vue";

export default {
  components: {
    Sense
  }
};
</script>

<style lang="scss">
@import "./variables.scss";

*,
*::before,
*::after {
  box-sizing: border-box;
}

#app {
  margin: 0 auto;
  line-height: 1.4;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: $vue-blue;
  text-align: center;
  max-width: 900px;
}

h1 {
  margin: 0px;
}

input#message {
  padding: 10px;
  width: 80%;
  font-size: 15px;
  border-radius: 2px;
  border: 1px solid #e3e3e3;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  text-align: center;
}

#results {
  background: #f2f2f2;
  padding: 35px 20px 30px 20px;
}

#phrase {
  font-size: 18px;
  text-transform: capitalize;
  font-style: italic;
  margin-bottom: 30px;
}

#result-bar span {
  font-size: 28px;
  font-weight: bold;
  display: inline-block;
  margin: 0px 10px;
}
</style>
