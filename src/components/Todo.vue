<template>
    <div class="todo">
        <input class="todo__checkbox" type="checkbox" id="todo__checkbox" @change="task.completed = !task.completed">
        <p class="todo__p" :class="{ todo_completed: task.completed }">{{ task.description }}</p>
        <button class="todo__remove" @click="remove()">&#10006;</button>
    </div>
</template>
<style lang="sass" scoped>
    @import "../assets/sass/color-variables.sass"
    @import "../assets/sass/mixins.sass"

    .todo
        margin-top: 2%
        width: 90%
        height: 8%
        background: $main-color
        padding: 1px 0px 1px 0px
        border-radius: 10px
        @include flex
        justify-content: space-between
        .todo__p
    .todo_completed
        text-decoration: line-through   
    .todo__remove
        color: $btn-text-color
        background: $btn-remove-color  
        border-radius: 50%
        border: 0
        font-size: 15px   
        margin-right: 10px
        transition: 1s
        &:hover
            transition: 1s
            background: $btn-active-color
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