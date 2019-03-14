<template>
  <div class="card" :class="{'has-text-success': success,'has-background-dark': dark}">
    <div class="card-content">
      <p>
        Hello World
      </p>
    </div>
  </div>
</template>

<script>
  export default {
    name: "card"
  }
</script>

<style scoped>

</style>
