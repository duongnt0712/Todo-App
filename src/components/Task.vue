<template>
  <div @dblclick="$emit('toggle-reminder', task.id)" :class="[task.reminder?'reminder':'task']">
    <h3>{{ task.text }} 
      <i class="fas fa-times" @click="$emit('delete-task', task.id)"></i>
    </h3>
    <p>{{ task.date }}</p>
  </div>
  
</template>

<script>
export default {
  name: 'TaskItem',
  props: {
    task: Object
  },
  methods: {
    onDelete(id) {
      this.$emit('delete-task', id)
    }
  }
}   
</script>

<style>
.task {
  text-align: left;
  background: #eee;
  margin: 5px;
  padding: 10px 20px;
}
.reminder {
  border-left: 10px solid #333;
  background: #eee;
  margin: 5px;
  padding: 10px 20px;
}
h3 {
  display: flex;
  justify-content: space-between;

}
</style>