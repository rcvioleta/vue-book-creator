<template>
  <div id="text-editor__main-wrapper">
    <div class="text-editor__wrapper" v-for="page in pages" :key="page.key">
      <div
        class="text-editor"
        :contenteditable="page.editable"
        @keydown="handleKeydown($event, page.id)"
      ></div>
    </div>
  </div>
</template>

<script>
import uuid from "uuidv4";

export default {
  data() {
    return {
      pages: [
        {
          id: uuid(),
          title: "",
          content: "",
          editable: true
        }
      ]
    };
  },
  methods: {
    handleKeydown(evt, pageId) {
      const pageIndex = this.pages.findIndex(page => page.id === pageId);
      const page = this.pages[pageIndex];
      const target = evt.target;
      const heightLimit = target.offsetHeight < target.scrollHeight;
      const widthLimit = target.offsetWidth < target.scrollWidth;
      const parentTextEditor = document.getElementById(
        "text-editor__main-wrapper"
      );

      if (heightLimit || widthLimit) {
        this.pages[pageIndex].editable = false;
        this.pages.push({
          id: uuid(),
          title: "",
          content: "",
          editable: true
        });
        console.log(parentTextEditor.childNodes.length);
        console.log(parentTextEditor.childNodes[1].firstChild);
      }
    }
  }
};
</script>

<style scoped>
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