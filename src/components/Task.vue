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
      <span v-else @click="$emit('toggle-reminder', task.id)">Set Alarm</span>
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
  cursor: pointer;
  font-size: 0.9rem;
  border: 1px solid purple;
  border-radius: 5px;
  padding: 0 3px;
  background-color: purple;
  color: #fff;
}
span:hover {
  background-color: hotpink;
}
</style>
