<template>
  <div class="home">
    <h1>Home</h1>
    <p ref="p">{{ lastName }} {{ firstName }}</p>
    <button @click="handleClick">green</button>
    <button @click="handle">blue</button>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'Home',
  components: {  },
  setup(){
    let firstName = 'Vorn'
    let lastName = 'Chhor'

    const p = ref(null)
    
    const handleClick = () => {
      console.log("You've clicked")
      p.value.classList.add('active')
    }
    const handle = () => {
      p.value.classList.remove('active')
    }

    return{
      firstName, 
      lastName,
      handleClick,
      handle,
      p
    }
  }
}
</script>

<style scoped>
.active {
  background: green;
}
</style>
