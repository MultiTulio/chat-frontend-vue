<template>
  <div>
    <Chat/>
  </div>
</template>

<script>
import Chat from './components/Chat.vue'
import Login from './components/Login.vue'

export default {
  path: '/chat',
  name: 'app',
  components: {
    Chat
  }

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
