<template>
  <div class="result-item">
    <input type="button" :class="card.title" :value="card.title" />
  </div>
</template>

<script>
export default {
  name: "ResultItem",
  props: ["card"],
};
</script>
<style></style>
