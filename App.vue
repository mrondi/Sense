<template>
  <div id="app">
    <center>
      <img
        src="http://icons.iconarchive.com/icons/diversity-avatars/avatars/128/robot-02-icon.png"
        width="100"
      /><br />
      <h1>Sens3</h1>

      <p id="how-to">
        Ingrese una frase arriba (en inglés) y esta inteligencia artificial<br />
        distinguira si su frase expresa algo positivo o negativo.
      </p>
    </center>
    <sense></sense>

    <center style="position:absolute; bottom:5px; right:5px">
      <small
        >BY MAURO RONDINELLI - BUILD WITH VUE.JS / NODE.JS / NODE-NLP</small
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
