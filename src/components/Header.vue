<template>
    <header>
        <div class="app-tilte">
            <h1>{{ title }}</h1>
        </div>
        <div class="btn-add-task">
            <Button v-show="homePage" @btn-click="$emit('toggle-add-task')" :text="showAddTask ? 'Close' : 'Add Task' " :color="showAddTask ? 'red' : '#30c83e' " />
        </div>
    </header>
</template>
  
<script>
    import Button from './Button.vue'


    export default {
        name: 'Header',
        props: {
            title: String,
            showAddTask: Boolean,
        },
        components: {
            Button,
        },
        computed: {
            homePage(){
                if(this.$route.path === '/') {
                    return true
                }else{
                    false
                }
            }
        }
    }

</script>

<style scoped>
    header {
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 20px;
    }
    h1,.h1 {
        font-weight:bold;
    }
    .app-tilte {
        align-self: flex-start;
    }
    .btn-add-task {
        align-self: flex-end;
    }
</style>