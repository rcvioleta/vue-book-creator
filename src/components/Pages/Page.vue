<template>
  <div class="text-editor" contenteditable="true" @keydown="onkeydown">{{page.body}}</div>
</template>

<script>
export default {
  props: ["page", "onkeydown"],
  data() {
    return {};
  }
};
</script>

<style>
.text-editor__wrapper {
  overflow-y: hidden;
  overflow-x: hidden;
  margin: 2rem auto;
  padding: 2rem;
  height: 500px;
  width: 450px;
  border: 5px solid #ccc;
}

.text-editor {
  overflow-y: hidden;
  overflow-x: hidden;
  margin: 0 auto;
  height: 500px;
  width: 450px;
  border: 1px solid #ccc;
  text-align: left;
  box-sizing: border-box;
  outline: none;
}
</style>
