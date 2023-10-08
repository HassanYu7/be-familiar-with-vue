
<template>

<div>

  
  <ToDoForm></ToDoForm>
  <DashboardForm></DashboardForm>  
  
</div>
</template>

<script>
import ToDoForm from "./components/ToDoForm.vue";
import DashboardForm from "./components/DashboardForm.vue";

export default {
  name: "App",
  components: {
    ToDoForm,
    DashboardForm

  },

  data() {
    return {
      title: "",
      assessments: [],
    };
  }
};
</script>

<style>
#app {
  font-family: 'almarai', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 120px;
}

body {
  background-color: #262f3f;
}
</style>
