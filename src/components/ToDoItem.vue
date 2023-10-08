<template>
  <div class="flex items-center p-2">


    <div class="pretty p-svg p-curve">
      <input type="checkbox" :id="'task_' + task.id" :checked="task.completed" @change="toggleCompleted" />
      <div class="state p-success">
        <svg class="svg svg-icon" viewBox="0 0 20 20">
          <path
            d="M7.629,14.566c0.125,0.125,0.291,0.188,0.456,0.188c0.164,0,0.329-0.062,0.456-0.188l8.219-8.221c0.252-0.252,0.252-0.659,0-0.911c-0.252-0.252-0.659-0.252-0.911,0l-7.764,7.763L4.152,9.267c-0.252-0.251-0.66-0.251-0.911,0c-0.252,0.252-0.252,0.66,0,0.911L7.629,14.566z"
            style="stroke: white;fill:white;"></path>
        </svg>
        <label class="flex items-center  rounded cursor-pointer hover:bg-gray-900" :for="'task_' + task.id"></label>
      </div>
    </div>



  <input
      type="text"
      class="mr-2 text-sm bg-gray-800 text-color-white rounded w-full py-2 px-3 focus:outline-none"
      :class="{ 'line-through text-gray-400': task.completed }"
      :value="task.title"
      @keyup.enter="updateTask(task.id, task.title)"
      @blur="updateTask(task.id, $event.target.value)"
    />



    <button
    type="button"
    @click="$emit('delete-task', task.id)"
      class="inline-flex items-center px-2 py-2 bg-red-600 hover:bg-red-700 text-white text-sm font-medium rounded-md">
      <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
          d="M19 7l-.867 12.142A2 2 0 0116.138 21H7.862a2 2 0 01-1.995-1.858L5 7m5 4v6m4-6v6m1-10V4a1 1 0 00-1-1h-4a1 1 0 00-1 1v3M4 7h16" />
      </svg>
    </button>
  </div>
</template>


<script>
export default {
  name: "ToDoItem",
  props: {
    task: Object,
  },
  methods: {
    toggleCompleted() {
      this.$emit("toggle-completed", this.task.id);
    }
    ,
    updateTask(id,newTitle) {
      this.$emit("update-task-title", id , newTitle);
    } ,
    
    
    

  },
};
</script>