<template>
  <div :class="'article-wrap ' + type ">
    <h3>{{ title }}</h3>
    <p>{{ content }}</p>
  </div>
</template>

<script>
export default {
  name: "Article",
  props: {
    title: String,
    content: String,
    type: String, // success, danger, warning
  }
}
</script>

<style scoped>
.article-wrap {
  border: 1px solid #d7d7d7;
  border-radius: 4px;
  background-color: #ececec;
  padding: 20px;
  margin-bottom: 20px;
}

.success {
  border-color: green;
}

.danger {
  border-color: red;
}

.warning {
  border-color: darkorange;
}
</style>
