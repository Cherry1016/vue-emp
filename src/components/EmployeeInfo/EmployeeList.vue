<template>
  <div class="employee-list-container">
    <CardLayout v-for="(item, index) in employees" :key="index" :employee="item">
      <div>Name: {{ item.name }}</div>
      <div v-show="!!item.age">Age: {{ item.age }}</div>
      <div>Gender: {{ genderMap[item.gender] }}</div>
      <div v-show="!!item.education">Education: {{ item.education }}</div>
      <div v-show="item.lang.length > 0">Languages: {{ item.lang.join(", ") }}</div>
    </CardLayout>
  </div>
</template>

<script>
import CardLayout from "./CardLayout.vue";
export default {
  name: "EmployeeList",
  components: { CardLayout },
  data() {
    return {
      genderMap: {
        not_specified: "Not Specified",
        male: "Male",
        female: "Female",
      },
    };
  },
  methods: {},
  props: {
    employees: {
      default: [],
    },
  },
  watch: {},
};
</script>

<style scope>
.employee-list-container {
  border: 1px solid;
}
</style>
