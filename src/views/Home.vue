<template>
  <div class="home">
    <div class="relative m-12">
        <label for="name" class="leading-7 text-sm text-gray-600">Name</label>
        <input type="text" id="name" v-model="search" class="w-full bg-white rounded border border-gray-300 focus:border-indigo-500 focus:ring-2 focus:ring-indigo-200 text-base outline-none text-gray-700 py-1 px-3 leading-8 transition-colors duration-200 ease-in-out">
      </div>
    <button @click="handelClick('title')" class="bg-blue-600 p-2 mx-4 text-white rounded-md">order by name</button>
    <button @click="handelClick('salary')" class="bg-blue-600 p-2 mx-4 text-white rounded-md">order by salary</button>
    <button @click="handelClick('location')" class="bg-blue-600 p-2 mx-4 text-white rounded-md">order by location</button>
    
    <JobListVue :jobs="jobs" :order='order'></JobListVue>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import JobListVue from '@/components/JobList.vue';
import Job from '@/types/Job'
import OrderItem from '@/types/OrderItem';
export default defineComponent({
  name: 'Home',
  components: {
    JobListVue
  },
  setup(){

    const jobs = ref<Job[]>([
      {title:'Full Stack Developer (PHP, VueJs)',location:'lon lon reach',salary:10000,id:'1'},
      {title:'Software Engineer (Backend)',location:'kathmandu',salary:21000,id:'2'},
      {title:'Agile Project Manager',location:'pokhera',salary:4000,id:'3'},
      {title:'DevOps Engineer',location:'lamki',salary:25000,id:'4'},
      {title:'Frontend Engineer',location:'lamki',salary:36000,id:'5'},
      {title:'Software Engineer(MERN)',location:'lamki',salary:15000,id:'6'},
      {title:'Flutter Developer',location:'lamki',salary:12000,id:'7'},
      {title:'Software Test Engineer',location:'lamki',salary:50000,id:'8'}
    ])
    const search = ref('')
    const order = ref<OrderItem>('title')
    const handelClick = (term: OrderItem)=>{
      order.value = term
    }
    return {jobs,handelClick,order,search}

  },
});
</script>
