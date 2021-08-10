<template>
    <div class="add-todo">
        <input class="add-todo__input" type="text" v-model="input">
        <button class="add-todo__button" @click="addTodo()">Добавить задачу</button>
    </div>
</template>
<style lang="sass" scoped>
    @import "../assets/sass/color_variables.sass"
    @import "../assets/sass/mixins.sass"
    
    .add-todo
        margin-top: 50px
        @include flex-column
        justify-content: center
        .add-todo__input,.add-todo__button
            margin-top: 10px
        .add-todo__input
            height: 25px
            width: 200px
            border: 1px solid $main-color
            border-radius: 10px
            &:focus
                background: $main-color
        .add-todo__button
            background: $btn-color
            color: $btn-text-color
            border-radius: 20px
            border: none
            height: 25px
            width: 180px
            transition: 1s
            &:hover
                transition: 1s
                background: $btn-active-color
</style>
<script>
export default {
    name: "AddTodo",
    props: ["tasks"],
    data(){
        return{
            input: ""
        }
    },
    methods:{
        addTodo(){
            if(this.input.trim()) {
                const newTodo = {
                    id: Date.now(),
                    description: this.input,
                    completed: false
                }
                this.$emit("add-todo", newTodo)
                this.input = ""
            }
        }
    }
}
</script>