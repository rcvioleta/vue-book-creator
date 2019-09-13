<template>
  <div id="page">
    <ul>
      <li>{{ page.title }}</li>
      <li>{{ page.body }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ["page"],
  data() {
    return {};
  }
};
</script>