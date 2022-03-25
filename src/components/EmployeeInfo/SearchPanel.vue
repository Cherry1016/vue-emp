<template>
  <div>
    <input type="text" v-model="employeeName" />
    <button @click="handleSearch">Search</button>
  </div>
</template>

<script>
export default {
  name: "SearchPanel",
  data() {
    return {
      employeeName: "",
    };
  },
  methods: {
      handleSearch() {
          this.$emit("searchEmployee", this.employeeName)
      }
  }
};
</script>

<style scoped>
    button {
        margin: .5rem;
    }
</style>