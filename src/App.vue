<template>
  <div id="app">
    <TextEditor />
  </div>
</template>

<script>
import Pages from "./components/Pages/BookCreator";
import TextEditor from "./components/Pages/TextEditor";

export default {
  name: "app",
  components: {
    Pages,
    TextEditor
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
