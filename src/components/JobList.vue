<template>
    <div >
        <ul>
            <li class="bg-white p-12 m-12 shadow hover:shadow-lg" v-for="job in jobs" :key="job.id">
                <h2>{{job.title}} in {{job.location}}</h2>
                <div>
                    <p class="text-red-600">{{job.salary}}</p>
                </div>
                <div>
                    <p>
                        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Et saepe earum veritatis, alias odio ipsam culpa libero temporibus hic repellendus accusantium nihil praesentium obcaecati, illum incidunt soluta eius dolores qui.
                    </p>
                </div>
            </li>
        </ul>
    </div>
</template>
<script lang="ts">
import { defineComponent, PropType } from 'vue'
import Job from "@/types/job"
export default defineComponent({
    props:{
        jobs:{
            type:Array as PropType<Job[]>,
            required: true
        }
    }

})
</script>
<style>
</style>