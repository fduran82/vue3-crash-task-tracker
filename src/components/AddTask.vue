<template>
    <form @submit="onSubmit" class="add-form">
        <div class="form-control">
            <label>Task</label>
            <input type="text" v-model="text" name="text" placeholder="Add Task" />
        </div>
        <!-- {{ text }} -->
        <div class="form-control">
            <label>Day & Time</label>
            <input type="text" v-model="day" name="day" placeholder="Add Day & Time" />
        </div>
        <!-- {{ day }} -->
        <div class="form-control form-control-check">
            <input type="checkbox" v-model="reminder" name="reminder" />
            <label>Set Reminder</label>
        </div>
        <!-- {{ reminder }} -->
        <input type="submit" value="Save Task" class="btn btn-block" />
    </form>
</template>


<script>
    export default {
        name: 'AddTask',
        props: {

        },
        data() {
            return {
            text: '',
            day: '',
            reminder: false,
            }
        },
        methods: {
            onSubmit(e) {
                e.preventDefault()

                if (!this.text) {
                    alert('Please add a task')
                    return
                }
                const newTask = {
                    // id: Math.floor(Math.random() * 100000),
                    text: this.text,
                    day: this.day,
                    reminder: this.reminder,
                }

                // console.log(newTask);

                this.$emit('add-task', newTask)
                this.text = ''
                this.day = ''
                this.reminder = false
            },
        },
    }
</script>


<style scoped>
    .btn-block {
      border: none;
    }
    .add-form {
      margin-bottom: 10px;
      padding: 20px;
      background-color: #f4f4f4;
      border-radius: 10px;
      margin: 5px;
    }
    .form-control {
      margin: 20px 0;
    }
    .form-control label {
      display: block;
    }
    .form-control input {
      width: 100%;
      height: 40px;
      margin: 5px;
      padding: 3px 7px;
      font-size: 17px;
    }
    .form-control-check {
      display: flex;
      flex-direction: row;
      align-items: center;
      justify-content: flex-start;
    }
    .form-control-check label {

    }
    .form-control-check input {
      margin-right: 10px;
      height: 20px;
      width: 20px;
    }
    input {
      border-radius: 5px;
      border: 1px solid #7d7d7d;
    }
</style>