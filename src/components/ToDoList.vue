<template>
    <div>
        <div v-for="(task, index) in tasks" :key="index">
            <ToDoItem :task="task" 
            @toggle-completed="toggleTaskCompleted" 
            @delete-task="deleteTask"
            @update-task-title="updateTaskTitle"

             />
        </div>

        <button class="flex items-center w-full h-8 px-2 mt-2 text-sm font-medium rounded">
            <svg class="w-5 h-5 text-gray-400 fill-current" xmlns="http://www.w3.org/2000/svg" fill="none"
                viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6v6m0 0v6m0-6h6m-6 0H6" />
            </svg>
            <input class="flex-grow mr-4 p-2 bg-transparent focus:outline-none font-medium" type="text"
                placeholder="اضف مهمة جديدة" v-model="newTask" @keyup.enter="addTask" />
        </button>
    </div>
</template>
  
<script>
import ToDoItem from "./ToDoItem.vue";

export default {
    name: "ToDoList",
    components: {
        ToDoItem,
    },
    data() {
        return {
            tasks: [],
            newTask: "",
        };
    },
    methods: {
        addTask() {
            if (this.newTask.trim() !== "") {
                this.tasks.push({
                    id: this.tasks.length + 1,
                    title: this.newTask,
                    completed: false
                });
                this.newTask = "";
            }
        },
    
        toggleTaskCompleted(id) {
            this.tasks.find((task) => task.id === id).completed = !this.tasks.find((task) => task.id === id).completed;
        },
        deleteTask(id) {
            this.tasks = this.tasks.filter((task) => task.id !== id);
        },
        updateTaskTitle(id, newTitle) {
            this.tasks.find((task) => task.id === id).title = newTitle;
        }

    }
};
</script>
<style></style>
  