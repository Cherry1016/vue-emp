<template>
  <CardLayout>
    <form @submit.prevent="handleSubmit">
      <h1>Add New Employee</h1>
      <div class="form-field">
        <label for="name">Name</label>
        <input name="name" type="text" v-model="name" />
      </div>
      <div class="form-field">
        <label for="age">Age</label>
        <input name="age" type="number" v-model="age" />
      </div>
      <div class="form-field">
        <label>Gender</label>
        <div class="choice">
          <input type="radio" value="not_specified" v-model="gender" />
          <label for="not_specified">Not specified</label>
          <input type="radio" value="male" v-model="gender" />
          <label for="male">Male</label>
          <input type="radio" value="female" v-model="gender" />
          <label for="female">Female</label>
        </div>
      </div>
      <div class="form-field">
        <label for="education">Education</label>
        <select v-model="education">
          <option value="high_school">Hight school</option>
          <option value="bachelor">Bachelor Degree</option>
          <option value="master">Master Degree</option>
          <option value="phd">PhD Degree</option>
        </select>
      </div>
      <div class="form-field">
        <label>Language</label>
        <div class="choice">
          <input type="checkbox" value="thai" v-model="lang" />
          <label for="thai">Thai</label>
          <input type="checkbox" value="english" v-model="lang" />
          <label for="englist">English</label>
          <input type="checkbox" value="chinese" v-model="lang" />
          <label for="chinese">Chinese</label>
        </div>
      </div>
      <button type="submit">Add</button>
    </form>
  </CardLayout>
</template>

<script>
import CardLayout from "./CardLayout.vue";
export default {
  name: "AddEmployee",
  components: {
    CardLayout,
  },
  data() {
    return {
      name: "",
      age: "",
      gender: "not_specified",
      education: "",
      lang: [],
    };
  },
  methods: {
    handleSubmit() {
      const empData = {
        name: this.name,
        age: this.age,
        gender: this.gender,
        education: this.education,
        lang: this.lang,
      };
      this.$emit("addEmployee", empData);
    },
  },
};
</script>

<style scoped>
.form-field {
  padding: 0.5rem;
  display: flex;
}

.form-field > label {
  padding: 0.5rem;
  flex: 2;
  text-align: left;
  white-space: nowrap;
}

.form-field > input,
.form-field > select {
  flex: 10;
}

option {
  padding: 0.5rem;
}

div.choice {
  display: flex;
  flex: 10;
  align-items: center;
  justify-content: flex-start;
}
</style>