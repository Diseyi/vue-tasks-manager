<template>
  <div class="w-[90%] m-auto lg:w-2/5">
    <AppHeader title="Task Manager" />
    <AddTask />
    <div class="px-6 my-6">
      <Tasks
        @delete-task="deleteTask"
        @toggle-reminder="toggleReminder"
        :tasks="tasks"
      />
    </div>
  </div>
</template>

<script>
import AppHeader from "./components/AppHeader.vue";
import Tasks from "./components/Tasks.vue";
import AddTask from './components/AddTask.vue'

export default {
  name: "App",
  components: {
    AppHeader,
    Tasks,
    AddTask,
  },
  data() {
    return {
      tasks: [],
    };
  },

  methods: {
    deleteTask(id) {
        this.tasks = this.tasks.filter((task) => task.id !== id);
    },
    toggleReminder(id) {
      console.log(id);
      this.tasks = this.tasks.map((task) => 
      task.id === id ?
      {...task, reminder: !task.reminder} : task
       )
    },
  },
  created() {
    this.tasks = [
      {
        id: 1,
        text: "Doctor's Appointment",
        day: "February 13, at 4:30pm",
        reminder: true,
      },
      {
        id: 2,
        text: "Study DSA",
        day: "February 17, at 4:30pm",
        reminder: false,
      },
      {
        id: 3,
        text: "Play piano",
        day: "February 17, at 6:30pm",
        reminder: true,
      },
    ];
  },
};
</script>

<style>
</style>
