<template>
<div class="task-grid">
    <template v-if="tasks.length">
        <Task v-for="(task,i) in tasks" :task="task" 
        @taskDeleted="$emit('taskDeleted',i)"
        @taskStateChanged="$emit('taskStateChanged',i)"
        :key='task.name'></Task>
    </template>
    <p v-else class="no-task">Enjoy</p>
</div>
</template>
    
<script>
import Task from './Task.vue'

export default {
    components:{Task},
    props:{
        tasks:{type:Array,required:true}
    }
}
</script>

<style>
.task-grid{
    display:flex;
    justify-content: center;
    flex-wrap: wrap;
}
.task-grid .task{
    margin: 10px;

}
.no-task{
    color: #aaaaaa;
    font-size: 1.7rem;
}
</style>