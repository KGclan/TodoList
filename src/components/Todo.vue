<template>
    <div class="todo">
        <input class="todo__checkbox" type="checkbox" id="todo__checkbox" @change="task.completed = !task.completed">
        <p class="todo__p" :class="{ todo_completed: task.completed }">{{ task.description }}</p>
        <button class="todo__remove" @click="remove()">&#10006;</button>
    </div>
</template>
<style lang="sass" scoped>
    .todo
        margin-top: 2%
        width: 90%
        height: 8%
        background: #0E97FB
        padding: 1px 0px 1px 0px
        border-radius: 10px
        display: flex
        align-items: center
        justify-content: space-between
        .todo__p
    .todo_completed
        text-decoration: line-through   
    .todo__remove
        color: white
        background: red  
        border-radius: 50%
        border: 0
        font-size: 15px   
        margin-right: 10px
        transition: 1s
        &:hover
            transition: 1s
            background: blue
</style>
<script>
export default {
    name: "Todo",
    props:["task"],
    methods: {
        remove(){
            return this.$emit("remove-task", this.task.id)
        }
    }
}
</script>