<template>
    <div class="add-todo">
        <input class="add-todo__input" type="text" v-model="input">
        <button class="add-todo__button" @click="addTodo()">Добавить задачу</button>
    </div>
</template>
<style lang="sass" scoped>
    .add-todo
        display: flex
        flex-direction: column
        justify-content: center
        align-items: center
        .add-todo__input,.add-todo__button
            margin-top: 10px
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