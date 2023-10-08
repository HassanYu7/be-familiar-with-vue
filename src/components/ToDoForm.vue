<template>

<div class=" p-8 bg-gray-800 rounded-lg shadow-lg  w-23 h-21/5 lg:w-3/5 h-4/5  text-gray-200" dir="rtl">
      <div class="flex items-center mb-6">
        <svg class="h-8 w-8 text-indigo-500 stroke-current" xmlns="http://www.w3.org/2000/svg" fill="none"
          viewBox="0 0 24 24" stroke="currentColor">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
            d="M20 13V6a2 2 0 00-2-2H6a2 2 0 00-2 2v7m16 0v5a2 2 0 01-2 2H6a2 2 0 01-2-2v-5m16 0h-2.586a1 1 0 00-.707.293l-2.414 2.414a1 1 0 01-.707.293h-3.172a1 1 0 01-.707-.293l-2.414-2.414A1 1 0 006.586 13H4" />
        </svg>
        <h4 class="font-semibold mr-3 text-lg">مهام غير مكتملة</h4>
      </div>

      <ToDoList/>
      
      
    </div>

</template>

<script>
import ToDoList from "./ToDoList.vue";
    export default {
        name: "ToDoForm",
        components: {
            ToDoList,
        }

    }
</script>


<style scoped>
</style>