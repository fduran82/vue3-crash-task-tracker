<template>
  <div
    @dblclick="$emit('toggle-reminder', task.id)"
    :class="[task.reminder ? 'reminder' : '', 'task']">
    <div class="btn-delete">
      <h3><i @click="$emit('delete-task', task.id)" class="fas fa-trash"></i></h3>
    </div>
    <h3>
      {{ task.text }}
      
    </h3>
    <p>{{ task.day }}</p>
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

<style scope>
.fas {
  color: #7d7d7d;
}
.fas:hover {
  color: red;
  transform: scale(0.95);
}
.task {
  background: #f4f4f4;
  border-left: 10px solid #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
  border-radius: 8px;
}
.task.reminder {
  border-left: 10px solid #30c83e;
}
.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.btn-delete {
  display: flex;
  justify-content: end;
}
</style>