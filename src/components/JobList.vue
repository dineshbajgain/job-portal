<template>
<p>Order by {{order}}</p>
    <transition-group name="list"  tag="ul" >
            <li class="bg-white p-12 m-12 shadow hover:shadow-lg" v-for="job in orderedJobs " :key="job.id">
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
    </transition-group>
</template>
<script lang="ts">
import { computed, defineComponent, PropType } from 'vue'
import Job from '@/types/Job'
import OrderItem from '@/types/OrderItem'
export default defineComponent({
    name: 'JobList',
    props:{
        jobs:{
            type:Array as PropType<Job[]>,
            required: true
        },
        order:{
            type: String as PropType<OrderItem>,
            required: true
        }
    },
    setup(props){
        const orderedJobs= computed(()=>{
            return [...props.jobs].sort((a:Job,b:Job)=>{
                return a[props.order] > b[props.order]?1:-1
            })
        })
        return {orderedJobs}
    }
})
</script>
<style>
.list-move{
    transition:all 1s;
}
</style>