<template>
    <div class="main">
        <Counter :tasks_count="tasks_count" />
        <Todo v-for="task in tasks"
            :key="task"
            :task="task"
            :completed="task.completed"
            @remove-task="removeTask"
         />
        <AddTodo 
            :tasks="tasks"
            @add-todo="addTodo"    
        />
    </div>
</template>
<style lang="sass" scoped>
    .main
        width: 520px
        height: auto
        border-radius: 20px
        box-shadow: 10px 10px 10px 3px rgba(0, 0, 0, 0.5)
        display: flex
        justify-content: flex-start
        align-items: center
        flex-direction: column
</style>
<script>
import Counter from "@/components/Counter.vue"
import Todo from "@/components/Todo.vue"
import AddTodo from "@/components/AddTodo.vue"

export default {
    name: "Main",    
    components:{
        Counter,
        Todo,
        AddTodo
    },
    data(){
        return{
            tasks: [
                { id: 1, description: 'Купить хлеб', completed: false },
                { id: 2, description: 'Купить молоко', completed: false },
                { id: 3, description: 'Купить банан', completed: false },
                { id: 4, description: 'Купить водку', completed: false },
            ]
        }
    },
    computed:{
        tasks_count(){
            return this.tasks.length
        }
    },
    methods:{
        removeTask(id){
            this.tasks = this.tasks.filter(task => task.id !== id)
        },
        addTodo(newTodo){
            this.tasks.push(newTodo)
        }
    }
}
</script>