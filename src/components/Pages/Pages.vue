<template>
  <div id="pages">
    <h1>Pages Component</h1>
    <span v-for="page in pages" :key="page.id">
      <Page :page="page" />
    </span>
  </div>
</template>

<script>
import Page from "./Page";

export default {
  name: "Pages",
  components: {
    Page
  },
  data() {
    return {
      pages: [
        {
          id: 1,
          title: "Page 1",
          body: "Page 1 Content"
        },
        {
          id: 2,
          title: "Page 2",
          body: "Page 2 Content"
        },
        {
          id: 3,
          title: "Page 3",
          body: "Page 3 Content"
        },
        {
          id: 4,
          title: "Page 4",
          body: "Page 4 Content"
        },
        {
          id: 5,
          title: "Page 5",
          body: "Page 5 Content"
        }
      ]
    };
  }
};
</script>