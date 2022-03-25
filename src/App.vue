<template>
  <section>
    <AddEmployee @add-employee="handleAddEmployee"/>
  </section>
  <section>
    <EmployeeInfo :employees="employees"/>
  </section>
</template>

<script>
import EmployeeInfo from "./components/EmployeeInfo/EmployeeInfo.vue";
import AddEmployee from "./components/EmployeeInfo/AddEmployee.vue";

export default {
  name: "App",
  components: {
    EmployeeInfo,
    AddEmployee,
  },
  data() {
    return {
      employees: [],
    };
  },
  methods: {
    handleAddEmployee(data) {
      this.employees = [...this.employees, data]
    }
  }
};
</script>

<style>
#app {
  text-align: center;
}

section {
  display: flex;
  justify-content: center;
}
</style>
