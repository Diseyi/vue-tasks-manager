<template>
  <div
    class=" px-2 py-1 my-2 rounded flex flex-row items-center justify-between bg-gray-200 "
    v-for="task in tasks"
    :key="task.id"
    :class="[task.reminder ? 'true': 'false' ] "
    @dblclick="$emit( 'toggle-reminder', task.id) "
  >
    <TaskList v-bind:task="task" />
    <button @click='onDelete((task.id)) ' class="">delete</button>
  </div>
</template>

<script>
import TaskList from "./TaskList.vue";
export default {
  name: "Tasks",

  components: {
    TaskList,
  },

  props: {
    tasks: Array,
  },
  methods: {
    onDelete(id) {
      this.$emit('delete-task', id)
    }
  }
};
</script>

<style>
.true {
  border-left: 5px solid green;
}

.false {
  border-left: 5px solid rgb(228, 228, 210);
}
</style>