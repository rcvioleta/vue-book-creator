<template>
  <div class="text-editor__main-wrapper">
    <div class="text-editor__wrapper" v-for="page in pages" :key="page.id">
      <Page :page="page" :onkeydown="keydownHandler" />
    </div>
  </div>
</template>

<script>
import Page from "./Page";
import uuid from "uuidv4";
import uuidv4 from "uuidv4";

export default {
  components: {
    Page
  },
  data() {
    return {
      pages: [
        {
          id: uuid(),
          title: "Page Title",
          body: "Page Content"
        }
      ]
    };
  },
  methods: {
    keydownHandler(evt) {
      const target = evt.target;
      const xAxisLimit = target.offsetHeight < target.scrollHeight;
      const yAxisLimit = target.offsetWidth < target.scrollWidth;
      const limitReached = xAxisLimit || yAxisLimit;
      const parent = document.querySelector(".text-editor__main-wrapper");
      const nodeLen = parent.childNodes.length;

      // if (evt.which === 13 && limitReached) {
      //   this.pages.push({
      //     id: this.pages.length,
      //     title: `Page ${this.pages.length}`,
      //     body: `Page ${this.pages.length} Content`
      //   });
      //   parent.childNodes[nodeLen - 1].firstChild.focus();
      // }

      // console.log("offsetHeight", target.offsetHeight);
      // console.log("scrollHeight", target.scrollHeight);

      if (limitReached) {
        console.log("limit reach");

        this.pages.push({
          id: uuid(),
          title: "Page Title",
          body: "Page Content"
        });

        console.log("node length", nodeLen);
        console.log("child nodes", parent.childNodes);
        parent.childNodes[nodeLen].firstChild.focus();
      }
    }
  }
};
</script>