<template>
  <div>
      <slot></slot>
  </div>
</template>

<script>
export default {
    name: "cardLayout"
}
</script>

<style scoped>
    div {
        border: 2px solid;
        border-radius: 10px;
        padding: .5rem;
        width: 500px;
        background: lightgrey;
    }
</style>