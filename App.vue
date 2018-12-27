<template>
  <div id="app">
    <h1>Sens3</h1>
    <sense></sense>
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
}

h1 {
  text-align: center;
}

input#message {
  padding: 10px;
  width: 80%;
  font-size: 15px;
  border-radius: 2px;
  border: 1px solid #f2f2f2;
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
