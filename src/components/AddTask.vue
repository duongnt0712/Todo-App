<template>
<form @submit="onSubmit" class="add-form">
  <div class="form-control">
    <label>Task</label>
    <input type="text" v-model="text">
  </div>
  <div class="form-control">
    <label>Date</label>
    <input type="text" v-model="date">
  </div>
  <div class="form-control">
    <label>Set Reminder</label>
    <input type="checkbox" v-model="reminder">
  </div>

  <input type="submit" value="Save" class="btn-style btn-clock">
</form>
</template>

<script>
export default {
  name: 'AddTaskItem',
  data() {
    return {
      text: '',
      date: '',
      reminder: false
    }
  },
  methods: {
    onSubmit(e) {
      e.preventDefault() 

      if(!this.text) {
        alert('Please add a task')
        return
      }

      const newTask = {
        // id: Math.floor(Math.random() * 100000),
        text: this.text,
        date: this.date,
        reminder: this.reminder,
      }

      this.$emit('add-task', newTask)

      this.text= '',
      this.date= '',
      this.reminder= false
    }
  }
}
</script>

<style scoped>
.add-form {
  margin-bottom: 40px;
}
.form-control {
  margin: 20px 0;
}
.form-control label {
  display: block;
}
.form-control input {
  width: 90%;
  height: 20px;
  margin: 5px;
  padding: 3px 7px;
  font-size: 17px;
}
.form-control-check {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.form-control-check label {
  flex: 1;
}
.form-control-check input {
  flex: 2;
  height: 20px;
}
</style>