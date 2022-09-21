<template>

  <div class="container">
    <Header 
      @toggle-add-task="toggleAddTask"
      title="Task Tracker"
      :showAddTask="showAddTask" />
    
    <router-view :showAddTask="showAddTask" ></router-view>
    <Footer />
  </div>

</template>

<script>
import Header from './components/Header'
import Footer from './components/Footer.vue'


export default {
  name: 'App',
  components: {
    Header,
    Footer
},
  data() {
    return {
      showAddTask: false,
    }
  },
  methods: {
    toggleAddTask() {
      this.showAddTask = !this.showAddTask
    },
  },
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  body {
    font-family: 'Poppins', sans-serif;
  }
  .container {
    margin: 30px auto;
    overflow: auto;
    min-height: 300px;
    padding: 30px;
    border-radius: 5px;
  }
  .btn {
    display: inline-block;
    background: #30c83e;
    color: #fff;
    border: none;
    padding: 10px 20px;
    margin: 5px;
    border-radius: 5px;
    cursor: pointer;
    text-decoration: none;
    font-size: 15px;
    font-family: inherit;
    width:110px;
  }
  .btn:focus {
    outline: none;
  }
  .btn:active {
    transform: scale(0.98);
  }

  .btn:hover {
    transform: scale(0.98);
  }

  .btn-block {
    display: block;
    width: 120px;
  }
</style>
