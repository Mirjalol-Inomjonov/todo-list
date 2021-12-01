<template>
  <div id="app">
    <div class="container">
      <Header :title="title"/>
    </div>
    <router-view />
  </div>
</template>

<script>
import Header from "./components/Header";
export default {
  components: {
    Header,
  },
  data() {
    return {
      title: 'Track'
    }
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@100;200;300;400;500;600;700;800;900&display=swap");
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
body {
  font-family: "Poppins", sans-serif;
}
#app {
  padding: 35px;
  min-height: 100vh;
  background: #eee;
}
.container {
  max-width: 500px;
  min-height: 300px;
  margin: 0 auto;
  overflow: auto;
  padding: 30px;
  border: 1px solid steelblue;
  border-radius: 5px;
  background: #fff;
}

.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
  &:focus {
    outline: none;
  }
  &:active {
    transform: scale(0.98);
  }
}

.btn-block {
  display: block;
  width: 100%;
}
</style>
