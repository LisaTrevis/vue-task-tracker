<template>
  <div class="task">
    <h3>
      {{ task.text }}
      <i @click="$emit('delete-task', task.id)" class="fas fa-times"></i>
    </h3>
    <p>
      {{ task.day }}
      <i
        @click="$emit('toggle-reminder', task.id)"
        v-if="task.reminder"
        class="fas fa-bell"
      ></i>
      <span v-else @click="$emit('toggle-reminder', task.id)"
        >Add reminder</span
      >
    </p>
  </div>
</template>

<script>
export default {
  name: 'Task',
  props: {
    task: Object,
  },
}
</script>

<style scoped>
.fa-times {
  color: hotpink;
  cursor: pointer;
}
.fa-bell {
  color: purple;
  cursor: pointer;
}
.task {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
}
.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.task p {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
span {
  box-sizing: border-box;
  cursor: pointer;
  border: 1px solid purple;
  border-radius: 10px;
  padding: 2px;
  font-size: 0.75rem;
}
</style>
