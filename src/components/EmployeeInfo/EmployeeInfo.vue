<template>
  <div>
    <SearchPanel @search-employee="handleSearchEmployee"/>
    <EmployeeList :employees="filteredEmp"/>
  </div>
</template>

<script>
import SearchPanel from "./SearchPanel.vue";
import EmployeeList from "./EmployeeList.vue";

export default {
  name: "EmployeeInfo",
  components: { SearchPanel, EmployeeList },
  data() {
      return {
          filterVal: "",
          filteredEmp: []
      }
  },
  methods: {
      handleSearchEmployee(employeeName) {
          let newArr = [...this.employees.filter(item => item.name.includes(employeeName))]
          this.filteredEmp = newArr
          this.filterVal = employeeName
      }
  },
  props: {
      employees: {
          default: []
      }
  },
  watch: {
      employees(val) {
          let newArr = [...val.filter(item => item.name.includes(this.filterVal))]
          this.filteredEmp = newArr
      }
  }
};
</script>
