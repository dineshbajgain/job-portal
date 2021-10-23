<template>
  <div class="home">
    <p>{{name}}</p>
    <p>{{age}}</p>
    <button @click="changeName('Dinesh')">Change Name</button>
    <button @click="changeAge('100')">Change Age</button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Home',
  components: {
  },
  data(){
    return{
      name:'Link',
      age:25 as number| string 
    }
  },
  methods:{
    changeName(name: string,){
      this.name = name
      return name
    },
    changeAge(age: number|string){
      this.age = age
    }
  }
});
</script>
