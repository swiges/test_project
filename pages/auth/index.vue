<template>
  <div>
    <Article :title="alert.title" :content="alert.content" type="danger" />
  </div>
</template>

<script>
export default {
  name: "index",
  data() {
    return {
      alert: {
        title: 'Warning!',
        content: 'You have to login.'
      }
    }
  }
}
</script>

<style scoped>

</style>
