<template>
  <div class="home">
      {{jobs[0].title}}
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import Job from '../types/job'
export default defineComponent({
  name: 'Home',
  components: {
  },
  setup(){

    const jobs = ref<Job[]>([
      {title:'farm worker',location:'lon lon reach',salary:30000,id:'1'},
      {title:'businessman',location:'kathmandu',salary:60000,id:'2'},
      {title:'photographer',location:'pokhera',salary:40000,id:'3'},
      {title:'ok learn',location:'lamki',salary:50000,id:'4'}
    ])
    return {jobs}

  },
});
</script>
